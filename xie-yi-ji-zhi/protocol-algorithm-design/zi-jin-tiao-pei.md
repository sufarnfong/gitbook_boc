# 资金调配

### doHardWork

将第三方协议官方APY、每个策略投资/赎回所需要的gas、兑换滑点限制、[资金调配规则](../../more/appendix.md#资金分配规则)等作为调仓算法入参，输出待投资金应投资的策略以及金额。

| 设置参数                                  | Ethereum     | BNB Chain    | Polygon      |
| ------------------------------------- | ------------ | ------------ | ------------ |
| 定时任务触发周期                              | 除周一外每天上午7:00 | 除周一外每天上午7:00 | 除周一外每天上午7:00 |
| 成本收益计算周期X （投资X天的收益>=成本，则`doHardWork`） | 365天         | 365天         | 365天         |

### allocation

与`doHardWork`相比，`allocation`多做了一步：将低APY策略的资金取出，然后再将第三方协议官方APY、每个策略投资/赎回所需要的gas、兑换滑点限制、[资金调配规则](../../more/appendix.md#资金分配规则)等作为调仓算法入参，输出应投资的策略以及待投金额。

| 设置参数                                    | Ethereum       | BNB Chain      | Polygon        |
| --------------------------------------- | -------------- | -------------- | -------------- |
| 预调仓报告触发时机                               | 每周天doHardWork后 | 每周天doHardWork后 | 每周天doHardWork后 |
| 定时任务触发周期                                | 每周一上午7:00      | 每周一上午7:00      | 每周一上午7:00      |
| 成本收益计算周期X （调仓X天的收益>=成本，则可做`allocation`） | 30天            | 30天            | 30天            |

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

| 设置参数                                  | Ethereum                 | BNB Chain | Polygon |
| ------------------------------------- | ------------------------ | --------- | ------- |
| 资金调配计算兑换滑点设置                          | 0.15%                    | 0.15%     | 0.15%   |
| gas 配置 （包括策略存取款gas、兑换gas、`harvest`成本） | 0 (等资金量超过$500W后配置为实际gas) | 实际gas     | 实际gas   |

### 官方APY计算规则

在资金调配时需要传入官方APY作为参考。官方APY的来源渠道有以下几种：vfat.tools、coingecko、zapper、Official APY、apy.vision Fee等。如果官方APY来源渠道未包含该协议策略的APY计算，BOC直接通过复刻协议策略的官方APY计算规则。

一般而言，协议策略的官方APY由做市收益与矿币收益组成。以BOC已经对接的ConvexLusdStrategy策略为例，其APY由以下表格内容组成

| 收益来源  | APR         | 是否复利 | 计算方式 | 数据来源                                                                                         |
| ----- | ----------- | ---- | ---- | -------------------------------------------------------------------------------------------- |
| 交易手续费 | 0.0024      | 否    | 接口获取 | [https://www.convexfinance.com/api/curve-apys](https://www.convexfinance.com/api/curve-apys) |
| crv矿币 | 0.023523458 | 是    | 接口获取 | [https://www.convexfinance.com/api/curve-apys](https://www.convexfinance.com/api/curve-apys) |
| cvx矿币 | 0.024132445 | 是    | 读取合约 | 按时间发放，一年矿币价格/池子总资产，得到APR                                                                     |

其中“是否复利”是指该收益来源是否可以复利。交易手续费是无法复利的，而矿币收益是可以不断复利，具体APR转换为APY的公示如下：

$$
APY=(1+APR)^{periods}-1
$$

​其中periods参数是利息发放周期。

### 策略实际APY计算规则

策略实际APY是以策略币本位收益进行计算。
