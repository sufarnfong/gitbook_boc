# Risk On 策略

{% hint style="info" %}
注：Risk On策略尚在开发优化中，最新版本内容将会根据进度持续更新。
{% endhint %}

<figure><img src="../../.gitbook/assets/risk_on_flowmap.png" alt=""><figcaption><p>图1：Risk On 策略结构图</p></figcaption></figure>

### Risk On 策略描述&#x20;

1. 两种资产ETH和USDC，用户存入A资产后，为该用户单独创建一个Vault \[ 类似于MakerDao的Collateralized Debt Position (CDP) ]。
2. 每1份A资产拆分为33%和66%两份，1%作为管理费用于支付调仓Gas。
3. 66%A资产在AAVE以50%的抵押率借贷33%资产等额的B资产。
4. 将33%的A资产与33%的B资产构建Uniswap V3 USDC-ETH 500 LP，基于BoC的Uniswap V3的算法做市。
5. 当抵押率升高到75%（A资产下跌33%），从LP中归还部分B资产，将抵押率降低到50%，继续做市。
6. 当抵押率降低到37.5%（A资产上升33%），借贷更多B资产加入LP，将抵押率调高到50%，继续做市。
7. 做市回报小于AAVE借贷利率两倍，暂停做市。

### Risk On 策略做市报告&#x20;

1. $$净做市资金 = 累计投入资金 - 已提取资金（A资产）$$
2. AAVE未偿还借贷本息 （B资产）&#x20;
3. AAVE抵押资金 （A资产）&#x20;
4. Uniswap LP Token净值（以A资产计价）&#x20;
5. 做市利润 （4+3）-（2+1）&#x20;
6. 计算IRR（不同于APY）

预留20%利润进入Treasury的开关。
