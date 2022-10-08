# 资金调配

### doHardWork

将第三方协议官方APY、每个策略投资/赎回所需要的gas、兑换滑点限制、[资金调配规则](../../more/appendix.md#资金分配规则)等作为调仓算法入参，输出待投资金应投资的策略以及金额。

| 设置参数                                    | Ethereum     | Polygon      |
| --------------------------------------- | ------------ | ------------ |
| 定时任务触发周期                                | 除周一外每天上午7:00 | 除周一外每天上午7:00 |
| 成本收益计算周期X （投资X天的收益 >= 成本，则`doHardWork`） | 365天         | 365天         |

### allocation

与`doHardWork`相比，`allocation`多做了一步：将低APY策略的资金取出，然后再将第三方协议官方APY、每个策略投资/赎回所需要的gas、兑换滑点限制、[资金调配规则](../../more/appendix.md#资金分配规则)等作为调仓算法入参，输出应投资的策略以及待投金额。

| 设置参数                                      | Ethereum       | Polygon        |
| ----------------------------------------- | -------------- | -------------- |
| 预调仓报告触发时机                                 | 每周天doHardWork后 | 每周天doHardWork后 |
| 定时任务触发周期                                  | 每周一上午7:00      | 每周一上午7:00      |
| 成本收益计算周期X （调仓X天的收益 >= 成本，则可做`allocation`） | 30天            | 30天            |

### 资金调配算法

| 变量名          | 变量含义                                                |
| ------------ | --------------------------------------------------- |
| durationDays | 调仓的周期，需要保证在调仓后的一个周期内，调仓后的收益-调仓前的收益-调仓的成本>0          |
| yearDays     | 365天                                                |
| asset1       | 策略的原有资产                                             |
| apr1         | 调仓前的策略APR（APY需要转换成APR），调仓算法的APY目前取值为策略链外计算APY的7天平均值 |
| deltaAsset   | 假设策略调仓的资金变更值                                        |
| poolAssets1  | 策略目标投资池子的TVL，作为调仓后APR变化的参数                          |

**未调仓前收益**

$$
gain1 = \frac{asset1 \times apr1 \times durationDays}{yearDays}
$$

**变更后的收益**

$$
gain2 = \frac{(asset1+deltaAsset-exchangeLoss)\times apr2 \times durationDays}{yearDays}
$$

**变更后的APR**

$$
apr2 = \frac{apr1 \times poolAssets1}{(poolAssets1+deltaAsset-exchangeLoss)}
$$

将 gain2 中的 apr2 使用上面的等式代入后：

$$
gain2=\frac{apr1 \times durationDays/yearDays \times (asset1+deltaAsset) \times poolAssets1}{poolAssets1+deltaAsset-exchangeLoss}
$$

​那么单个策略的变更后的收益和变更资产的关系为：

$$
deltaGain = gain2-gain1 = \frac{deltaAsset \times (poolAsset1-asset1) \times apr1 \times durationDays}{(poolAsset1+deltaAsset-exchangeLoss) \times yearDays}
$$

​**单个策略资金变更成本**

****

| 变量名              | 变量含义                                      |
| ---------------- | ----------------------------------------- |
| withdrawFee      | 退出资金操作费                                   |
| lendFee          | 追加资金操作费                                   |
| exchangeLoss     | 兑换币种滑点损失                                  |
| harvestFee       | `harvest`资金费用                             |
| profitChangeFee  | 资金变更成本                                    |
| withdrawGas      | withdawGas为`withdraw`操作消耗的gas，通过预先测试预估得到的 |
| lendGas          | lendGas为`lend`操作消耗的gas，通过预先测试预估得到的        |
| exchangeLossRate | 兑换滑点                                      |

$$
profitChangeFee=withdrawFee+lendFee+exchangeLoss+harvestFee
$$

$$
withdrawFee = gasPrice \times withdrawGas
$$

$$
lendFee= gasPrice \times lendGas
$$

$$
exchangeLoss=deltaAsset \times exchangeLossRate
$$

$$
harvestFee=harvestGas \times durationDays
$$

求解所有策略的 deltaGain 的总和最大值：

$$
profitChange=MAX\sum_{i=1}^m(deltaGain_i -withdrawFee_i-lendFee_i - exchangeLoss_i-harvestFee_i)
$$

$$
profitChange=MAX\sum_{i=1}^m(\frac{deltaAsset_i \times (poolAsset_i-asset_i) \times apr_i * durationDays_i}{(poolAsset_i+deltaAsset_i-exchangeLoss_i) \times yearDays_i}
$$

$$
- operateFee_i - exchangeLoss_i - harvestFee_i)
$$

​该公式中，唯一的变量为每个策略的deltaAsset。同时求解还需要受限于

**约束条件**

1. 同协议策略（多个约束）资金不超过总资金的30%。
2. 所有资产变更进出总和为0。

**边界条件**

1. 策略资产不能超过总资产20%。
2. 策略资金不能超过目标池子资产的50%。

使用python scipy的`optimize.minimize`求得当前最佳调仓方案。

### 公共参数配置

| 参数设置                                  | Ethereum                 | Polygon |
| ------------------------------------- | ------------------------ | ------- |
| 资金调配计算兑换滑点设置                          | 0.15%                    | 0.15%   |
| gas 配置 （包括策略存取款gas、兑换gas、`harvest`成本） | 0 (等资金量超过$500W后配置为实际gas) | 实际gas   |

### 策略APY计算

策略的收益主要有以下4种：

* 矿币激励
* DEX做市收益
* 借出利息收益
* ETH2.0质押收益

特别的，针对ConvexIronBank类协议，BoC需要支付一笔借入利息，收益为负。

### 官方APY计算规则

#### 矿币收益

1. 分别获取开始区块、结束区块的池子的发矿速率、发矿的覆盖周期。
2. 根据第一步的数据，算出一天内的平均发矿速率，进而算出该池一天能收到的矿币总数。
3. 根据24小时内的加权totalSupply数量，算出奖励池的总本金。
4. 用该池收到的矿币总价值，除以该池的总本金，并年化该收益即得到CRV奖励的APR。
5. 将APR转换成APY。

#### DEX做市收益

取标的合约LP的净值变化率。以在Curve中提供流动性收益为例，程序取过去一天内24小时之间两个区块高度`getVirtualPrice()`获得两个区块virtualPrice，计算出变化率并年化。

$$
baseApr = \frac{endVirtualPrice - startVirtualPrice}{startVirtualPrice} \times 365
$$

#### 借出利息收益

取标的合约借贷率接口的值。以在DForce中提供借出收益为例，程序取过去一天内24小时之间两个区块高度`getSupplyTokenData()`获得两个区块借贷率值并年化。

$$
baseApr = \frac{startSupplyTokenData[0]- endSupplyTokenData[0]}{2}
$$

#### ETH2.0质押收益

持有wstETH与rETH的协议策略将享有ETH2.0质押收益。以持有wstETH的协议策略为例，程序取过去一天内24小时之间两个区块高度`stEthPerToken()`获得两个区块净值变化并年化。

$$
baseApr = \frac{endstEthPerToken - startstEthPerToken}{startstEthPerToken} \times 365
$$

#### 借入利息

针对ConvexIronBank类协议（Convex），为了规避持有外汇币种的风险敞口，外汇将通过在IronBank协议抵押USDC借入。因此BoC需要支付一笔借入利息，收益为负。

程序取Iron Bank外币合约过去一天内24小时之间两个区块高度的借贷率`getBorrowInterest()`，取均值后年化借入利息。

$$
baseApr = -\frac{endBorrowInterest + startBorrowInterest}{2} \times oneDayBlocks \times 365
$$

### Verified APY计算规则

BoC Verified APY包括Realized APY（已实现收益APY）和Unrealized APY（未实现收益APY）。程序每日定时任务生成昨日Verified APY：

$$
Verified APY = Realized APY + Unrealized APY
$$

#### 矿币收益

策略矿币收益是通过执行`harvest()`方法收回。

web3.0支持模拟调用合约的写方法得到返回结果，这是程序能得到Unrealized APY的基础。程序通过模拟计算每日起止区块下的`harvest()`方法得到策略本次harvest可收回的矿币种类及数量。

目前策略的运营逻辑是在 UTC 22:00:00时间做harvest。无论策略当日是否做Harvest，策略每日都将存在Unrealized APY。这是因为在UTC 22:00:00\~UTC 23:59:59之间，在策略harvest后仍有未收回的收益，存在Unrealized APY。

对于Unrealized APY的收益部分，由于实际未做卖矿动作，因此通过获取当前区块下矿币兑USD/ETH的汇率来预估计算当日APY，而在下次真正做卖矿时会回写更新矿币价格，并将Unrealized APY转化为确定的Realized APY。

#### ​DEX做市收益

通过累加策略一日内操作时段间的收益计算当日基础收益，默认DEX做市收益实时发放，属于Realized APY。以在Curve中提供流动性收益为例，计算主要流程：

1. 读取策略在一日范围内的操作：lend/withdraw/redeem/harvest。
2. 通过Curve的`getVirtualPrice()`计算一日范围内每次操作段内的收益。
3. 累加每段收益后，与当日加权本金计算APR。

#### 借出利息收益

同DEX做市收益类似，程序通过累加策略一日内所有操作时段间的利息和与当日加权本金计算APR。默认利息是实时收取的，属于Realized APY。

#### ETH2.0质押收益

同DEX做市收益类似，程序通过累加策略一日内所有操作时段间的质押收益和与当日加权本金计算APR。默认质押收益是实时收取的，属于Realized APY。

#### 借入利息

同DEX做市收益类似，程序通过累加策略一日内所有操作时段间的借入利息和与当日加权本金计算APR。默认借入利息是实时收取的，属于Realized APY。
