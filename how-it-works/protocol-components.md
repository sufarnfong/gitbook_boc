# 协议模块

## 区块链选择

BoC选择兼容[EVM](../more/appendix.md#以太坊虚拟机evm)的区块链，目前已经对接Ethereum 和 Polygon链。

### Ethereum

[**以太坊**](https://ethereum.org/en/)是一个去中心化的开源的有智能合约功能的公共区块链平台。以太币是以太坊的原生加密货币。

以太坊的概念在2013至2014年间由程序员Vitalik Buterin受比特币启发后首次提出，意为“下一代加密货币与去中心化应用平台”。以太坊在2014年通过ICO众筹得以开始发展。

### Polygon

[**Polygon**](https://wallet.polygon.technology/)是一种用于构建和互连与以太坊兼容的区块链网络的协议。

Polygon于2017年在印度启动，最初的名称是Matic Network。2021年2月，项目更名为Polygon。Polygon项目的加密货币名称为MATIC。

## 稳定币选择

为避免数字货币价格大幅度波动产生的心理恐惧，并引发做市资金的[无偿损失](../more/appendix.md#无偿损失-impermanent-loss)，BoC协议只针对[稳定币](../more/appendix.md#稳定币stablecoin)资产，且仅限于由法币提供足额抵押或由蓝筹数字资产提供超额抵押生成的稳定币。稳定币需要满足以下条件：

1. 其发行者需通过严格审核。
2. 具有保险。
3. 为减少[预言机](../more/appendix.md#预言机-oracle)攻击， 稳定币报价必须基于[Chainlink](https://chain.link/)而不是协议本身。
4. 规模大于5亿美元/20万ETH。

目前挑选出的策略稳定币种有：DAI、USDC、USDT、BUSD、USDP、TUSD、LUSD。

### DAI

[**DAI**](https://makerdao.com/en/)是一种稳定币加密货币，旨在通过以太坊区块链上的智能合约自动化系统将其价值保持在尽可能接近一美元的水平。

### USDC

[**USD Coin**](https://www.centre.io/usdc)（USDC）是与美元挂钩的数字稳定币，可在以太坊，Stellar，Algorand，Hedera Hashgraph和Solana区块链上运行。截至2022年1月，流通中的USDC为452亿美元。

### USDT

[**USDT**](https://tether.to/en/)，是由Tether Limited发行的有争议的加密货币，而Tether Limited由Bitfinex的所有者控制。USDT是一种将加密货币与法定货币美元挂钩的虚拟货币。每一枚USDT都会象征性的与政府支持的法定货币关联。USDT是一种保存在外汇储备账户、获得法定货币支持的虚拟货币。该种方式可以有效的防止加密货币出现价格大幅波动，基本上一个USDT价值就等1美元。

### BUSD

[**Binance USD**](https://www.binance.com/en/busd)（BUSD）是Binance和Paxos合作推出的新的稳定币，它以 1:1 的锚定美元。

### USDP

[**Pax Dollar**](https://paxos.com/usdp/)（USDP）是一种法定抵押的稳定币，它以 1:1 的锚定美元。

### TUSD

[**TrueUSD**](https://www.trusttoken.com)（TUSD）是由Trusttoken发行的一种稳定币，它以 1:1 的锚定美元。

### LUSD

[**LUSD**](https://www.liquity.org/)是由 Liquity 协议发行的一种稳定币，它以 1:1 的锚定美元。

## 协议策略选择

当选定稳定币后，BoC挑选的[策略](../more/appendix.md#策略strategy)将只使用到这些稳定币，且策略需要满足以下条件：

* 无提取费。
* 无入场费。
* 无锁定期（部分策略存在锁定期，短时间内无法取回资金）。
* 无投资限额（部分策略对资金有限额）。
* 所有的协议均经过严格审计，避免代码漏洞造成的损失。
* 为避免[嵌套代币](../more/appendix.md#嵌套代币nested-tokens)、[乐高组合](../more/appendix.md#乐高式组合-lego-combination)产生的连锁性系统风险，接入的聚合理财协议需要有长期的安全运营记录，并得到社区投票许可。
* 为避免市场波动导致损失，暂不接入通过提供风险服务获取资金回报的协议，暂不通过杠杆放大资金回报。
* 首批接入的[DEX](../more/appendix.md#去中心化交易所-dex)和[借贷协议](../more/appendix.md#借贷协议lending-protocol)均为各区块链上的首选一线协议，并有良好的安全运营记录。
* 协议提供资金链内择优分配服务，该分配兼具回报最大化及资金风险分散两项原则。

目前挑选出的协议主要有：

* Ethereum：Convex、DODO、SushiSwap、Balancer等。
* Polygon：DODO、Synapse、Quickswap、Balancer、Aave、Curve、SushiSwap等。

### Aave

[**Aave**](https://app.aave.com/)是一个开源的去中心化借贷协议, 为用户提供存款和借贷服务。借贷双方用户的存款利率与贷款利率根据平台借款量和存款量计算得到，并且平台采用Chainlink预言机保证抵押物价格的公平性。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Aave的总资金锁仓量约为117.9亿美元，DeFi应用[锁仓量](../more/appendix.md#锁仓量总锁定价值-tvl)排名第2名。

### Curve

[**Curve**](https://curve.fi/)是部署在以太坊上的去中心化交易所。Curve通过自动化做市商协议，专为以低手续费和滑点进行稳定币之间的交易而设计。它是一个去中心化的流动性聚合器，任何人都可以将自己的资产添加到流动性资金池中，赚取做市收益。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Curve的总资金锁仓量约为107.9亿美元，DeFi应用锁仓量排名第3名。

### Convex

[**Convex**](https://www.convexfinance.com/)是以太坊上一个致力于简化Curve使用流程的"CRV 质押和流动性挖矿一站式平台"。作为以太坊链上的收益聚合器，Convex旨在借助CVX代币，通过简单易用的界面，简化Curve和CRV锁定、质押的过程，并提高CRV持币者、流动性提供者的报酬，以此促进CRV生态系统发展。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Convex的总资金锁仓量约为101亿美元，DeFi应用锁仓量排名第4名。

### Uniswap

[**Uniswap**](https://uniswap.org/)是部署在以太坊上的去中心化交易所。Uniswap协议通过使用智能合约促进以太坊区块链上的加密货币之间的自动化交易。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Uniswap的总资金锁仓量约为70.4亿美元，DeFi应用锁仓量排名第6名。

### Balancer

[**Balancer**](https://balancer.fi/)是部署在以太坊上的去中心化交易所。Balancer使用\[自动做市商]协议(appendix#自动做市商amm)，任何人都可以将自己的资产添加到流动性资金池中，赚取做市收益。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Balancer的总资金锁仓量约为21.9亿美元，DeFi应用锁仓量排名第6名。

### SushiSwap

[**SushiSwap**](https://app.sushi.com/swap)最初是Uniswap的分叉，以Uniswap的代码为基础构建而成，同时引入了一些关键差异，即流动性提供者的奖励以协议的原生代币SUSHI发放。与Uniswap不同，即使在停止提供流动性之后，SUSHI持有者仍能继续赚取收益。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Sushiswap的总资金锁仓量约为16.8亿美元，DeFi应用锁仓量排名第11名。

### Quickswap

[**Quickswap**](https://quickswap.exchange/#/)是一个layer2的去中心化交易所，与Uniswap、Sushiswap相似，Quickswap使用自动做市商协议，任何人都可以将自己的资产添加到流动性资金池中，赚取做市收益，并且再次质押流动性代币来赚取收益。QUICK是Quickswap的治理代币。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，Quickswap的总资金锁仓量约为4.73亿美元，DeFi应用锁仓量排名第22名。

### DODO

[**DODO**](https://app.dodoex.io/)是一个去中心化交易所，它使用独创的[主动做市商（PMM）](../more/appendix.md#主动做市商-pmm)算法为Web3资产提供高效的链上流动性，让每个人都能轻松地发行和交易Web3资产。DODO既自己提供流动性，也聚合其它交易所的流动性。这使得DODO可以提供全网较好好的价格。

根据[DeFi Pulse](https://www.defipulse.com/)的资料，截止2022年3月30日，DODO的总资金锁仓量约为4.77千万美元，DeFi应用锁仓量排名第52名。

### dForce

**dForce** 致力于构建一个集成、互通的开放式金融协议和货币协议矩阵，包括借贷协议（全球流动性池、生息市场、资产类协议（多货币稳定币、合成资产等）流动性协议（交易聚合器、自动做市商）三大类。

截止于2022年3月30日，dForce的总资金锁仓量约为1.54千万美元，DeFi应用锁仓量排名第69名。

### Synapse

[**Synapse**](https://synapseprotocol.com/landing)是一个跨链的去中心化交易所和去中心化金融生态系统。该协议结合了新的代币、高收益流动性矿池、跨链桥等，为用户创造了无缝的去中心化金融体验。Synapse由原BNB Chain上的匿名跨链流动性协议Nerve Finance升级更名而来。

## 预言机选择

预言机是将区块链连接到链外、真实世界信息的数据源，以便可以在智能合约中查询数据。它允许确定的智能合约对不确定的外部世界作出反应，是智能合约与外部进行数据交互的唯一途径，也是区块链与现实世界进行数据交互的接口。

### Chainlink

[**Chainlink**](https://chain.link/)是一个去中心化的预言机网络，它弥合了智能合约（如以太坊上的合约）与其外部数据之间的差距。 区块链本身无法以受信任的方式连接到外部应用程序。Chainlink不是一个单一的预言机网络，而是一个由许多并行运行的去中心化预言机网络组成的生态系统。Chainlink平台代币为LINK。

## 对接的第三方协议

### Ethereum

| BOC合约                                                                                                   | 第三方协议合约                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Vault](https://etherscan.io/address/0xd5C7A01E49ab534e31ABcf63bA5a394fF1E5EfAC)                        |                                                                                                                                                                                                        |
| [Balancer3CrvStrategy](https://etherscan.io/address/0xa4bc7002d89ef7966c5b2fd70963eaa7a632bb19)         | [Balancer Vault](https://etherscan.io/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                              |
| [DodoUsdtUsdcStrategy](https://etherscan.io/address/0x88b7068a365a92fe648c6d6a99cc58a583756df5)         | [DSP](https://etherscan.io/address/0xC9f93163c99695c6526b799EbcA2207Fdf7D61aD)、[DODOMine](https://etherscan.io/address/0xaeD7384F03844Af886b830862FF0a7AFce0a632C)                                     |
| [DodoDaiUsdtStrategy](https://etherscan.io/address/0xcace5387e7154594e0e95aa82f7779b2a0d8c9dc)          | [DSP](https://etherscan.io/address/0x3058EF90929cb8180174D74C507176ccA6835D73) [DODOMine](https://etherscan.io/address/0x1A4F8705E1C0428D020e1558A371b7E6134455A2)                                     |
| [SushiKashiUsdcLinkStrategy](https://etherscan.io/address/0x839672fff7bf86a273c9c1eb4ee72ca2496c7142)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0x4f68e70e3a5308d759961643AfcadfC6f74B30f4)                                                                                                       |
| [SushiKashiUsdtXsushiStrategy](https://etherscan.io/address/0xae4556510a43ff37df27d16a7ae8a08440a132da) | [KashiPairMediumRiskV1](https://etherscan.io/address/0xC84Fb1F76cbdd3b3491E81FE3ff811248d0407e9)                                                                                                       |
| [SushiKashiUsdtWethStrategy](https://etherscan.io/address/0x0adbfc6db10efd02786e3f590127079e74e4c128)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xfF7D29c7277D8A8850c473f0b71d7e5c4Af45A50)                                                                                                       |
| [SushiKashiUsdcWethStrategy](https://etherscan.io/address/0xfc3dd2cabf81999eb9e48ffb248ab048fccf348d)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xB7b45754167d65347C93F3B28797887b4b6cd2F3)                                                                                                       |
| [SushiKashiUsdcXsushiStrategy](https://etherscan.io/address/0x58c505ca34d908d7cb8349aaf6df7b942fe31a2e) | [KashiPairMediumRiskV1](https://etherscan.io/address/0x6EAFe077df3AD19Ade1CE1abDf8bdf2133704f89)                                                                                                       |
| [ConvexIronBankKrwStrategy](https://etherscan.io/address/0xb7e3eb6bbdd0cb9206ebd7c4d8351b52f61ca42b)    | [Iron Ban iKrw](https://etherscan.io/address/0x3c9f5385c288cE438Ed55620938A4B967c080101)、[Curve.fi Factory Plain Pool ibKRW](https://etherscan.io/address/0x8461A004b50d321CB22B7d034969cE6803911899)  |
| [ConvexIronBankJpyStrategy](https://etherscan.io/address/0x0e0963f34560bc337513319c4a7bf65f4c083907)    | [Iron Ban iJPY](https://etherscan.io/address/0x215F34af6557A6598DbdA9aa11cc556F5AE264B1)、[Curve.fi Factory Plain Pool ibJPY](https://etherscan.io/address/0x8818a9bb44Fbf33502bE7c15c500d0C783B73067)  |
| [ConvexIronBankGbpStrategy](https://etherscan.io/address/0x562c03b7822c9bcb9d19749a328d468eb8a15f48)    | [Iron Ban iGBP](https://etherscan.io/address/0xecaB2C76f1A8359A06fAB5fA0CEea51280A97eCF)、[Curve.fi Factory Plain Pool ibGBP](https://etherscan.io/address/0xD6Ac1CB9019137a896343Da59dDE6d097F710538)  |
| [ConvexIronBankEurStrategy](https://etherscan.io/address/0x809491dc62e9177733e0ce11b0f73cd873d47ed3)    | [Iron Ban iEUR](https://etherscan.io/address/0x00e5c0774A5F065c285068170b20393925C84BF3)、[Curve.fi Factory Plain Pool ibEUR](https://etherscan.io/address/0x19b080FE1ffA0553469D20Ca36219F17Fcf03859)  |
| [ConvexIronBankChfStrategy](https://etherscan.io/address/0x560419b9183db2c9fb8ae32dbc93bef5b34c7826)    | [Iron Ban iCHF](https://etherscan.io/address/0x1b3E95E8ECF7A7caB6c4De1b344F94865aBD12d5)、[Curve.fi Factory Plain Pool ibCHF](https://etherscan.io/address/0x9c2C8910F113181783c249d8F6Aa41b51Cde0f0c)  |
| [ConvexIronBankAudStrategy](https://etherscan.io/address/0xca41275733bba2831487206631cb46ad40bfda5d)    | [Iron Ban iUSDT](https://etherscan.io/address/0x48759F220ED983dB51fA7A8C0D2AAb8f3ce4166a)、[Curve.fi Factory Plain Pool ibAUD](https://etherscan.io/address/0x3F1B0278A9ee595635B61817630cC19DE792f506) |
| [Convex3CrvStrategy](https://etherscan.io/address/0x4d4700c777be1e11ec3af9465c90280788329964)           | [Curve.fi DAI/USDC/USDT Pool](https://etherscan.io/address/0xbEbc44782C7dB0a1A60Cb6fe97d0b483032FF1C7)                                                                                                 |
| [ConvexBusdStrategy](https://etherscan.io/address/0x264644dfbab5df335a05532a730421491808a7e5)           | [Curve.fi BUSD Swap](https://etherscan.io/address/0x79a8C46DeA5aDa233ABaFFD40F3A0A2B1e5A4F27)                                                                                                          |
| [ConvexLusdStrategy](https://etherscan.io/address/0x1f20dfb2b2ddbef30ea7c404d31970614dc5d6b5)           | [LUSD3CRV-f](https://etherscan.io/address/0xEd279fDD11cA84bEef15AF5D39BB4d4bEE23F0cA)                                                                                                                  |
| [ConvexBusdV2Strategy](https://etherscan.io/address/0x12896914a7fe92236d167c0c498b490d3aefd3e2)         | [Curve.fi BUSD V2](https://etherscan.io/address/0x4807862AA8b2bF68830e4C8dc86D0e9A998e085a)                                                                                                            |
| [ConvexYStrategy](https://etherscan.io/address/0x22ffc3b6b250c8bedee7e67c8e3ca6e2aaac63a4)              | [Curve.fi y Swap](https://etherscan.io/address/0x45F783CCE6B7FF23B2ab2D70e416cdb7D6055f51)                                                                                                             |
| [ConvexUsdtStrategy](https://etherscan.io/address/0x23a25fa21584b4b8f1348ac74396bf0ee8a72b6f)           | [Curve.fi USDT Swap](https://etherscan.io/address/0x52EA46506B9CC5Ef470C5bf89f17Dc28bB35D85C)                                                                                                          |
| [ConvexTusdStrategy](https://etherscan.io/address/0x968ebccd0e77644242ffb4468abe93774f75f34f)           | [TUSD3CRV-f](https://etherscan.io/address/0xEcd5e75AFb02eFa118AF914515D6521aaBd189F1)                                                                                                                  |
| [ConvexPaxStrategy](https://etherscan.io/address/0xf08fda0293cc8706ae1e280a9dc194c137cb63be)            | [pax-usdp3](https://etherscan.io/address/0xc270b3B858c335B6BA5D5b10e2Da8a09976005ad)                                                                                                                   |
| [ConvexCompoundStrategy](https://etherscan.io/address/0x02733188d0cbc87b4046b5ad12b9f3c8f3879c14)       | [Curve.fi Compound Swap](https://etherscan.io/address/0xA2B47E3D5c44877cca798226B7B8118F9BFb7A56)                                                                                                      |
| [ConvexAaveStrategy](https://etherscan.io/address/0x7f3bd67d7366dbc6b149f606cfa9c8fcdb72d9e2)           | [Curve.fi aDAI/aUSDC/aUSDT Pool](https://etherscan.io/address/0xDeBF20617708857ebe4F679508E7b7863a8A8EeE)                                                                                              |
| [YearnEarnTusdStrategy](https://etherscan.io/address/0x5c09ab7a2e09cc0f1d2e7f7ed189a7477c8e9623)        | [yearn yTUSD Token](https://etherscan.io/address/0x73a052500105205d34Daf004eAb301916DA8190f)                                                                                                           |
| [GUniUsdcDai100Strategy](https://etherscan.io/address/0x6488b7756e4338d73b85c61a67ca33921be59c88)       | [Gelato Uniswap DAI/USDC LP](https://etherscan.io/address/0x50379f632ca68D36E50cfBC8F78fe16bd1499d1e)                                                                                                  |

### Polygon

| BOC合约                                                                                                         | 第三方协议合约                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://polygonscan.com/address/0xd3feAe6c4fdfDE73Bd2fE99c8fE6944904DAA68A)                           |                                                                                                                                                                                                                |
| [Curve3CrvStrategy](https://polygonscan.com/address/0x1f84a8c8c31674b89a4723521ead5a48579b8bf7)               | [Curve.fi Aave Pool](https://polygonscan.com/address/0x445FE580eF8d70FF569aB36e80c647af338db351)、[Curve.fi Aave Gauge](https://polygonscan.com/address/0x19793B454D3AfC7b454F206Ffe95aDE26cA6912c)             |
| [AaveUsdtStrategy](https://polygonscan.com/address/0xb80a44d494acb8db24ff7047514a16bb554290e4)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf)、[Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [AaveUsdcStrategy](https://polygonscan.com/address/0x5c9a02f7a45c5407bef7e98d69ca324a29803b15)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf)、[Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [BalancerUsdcUsdtDaiTusdStrategy](https://polygonscan.com/address/0x23c75b1397ad73b3b572ccc9c3eb3ecede9682c4) | [Balancer Vault](https://polygonscan.com/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                                   |
| [QuickswapDaiUsdtStrategy](https://polygonscan.com/address/0xd55001d2508b58a7bc197c50c64ebbd0ae587300)        | [StakingRewards](https://polygonscan.com/address/0xc45aB79526Dd16B00505EB39222E6B1Aed0Ef079)                                                                                                                   |
| [QuickswapUsdcDaiStrategy](https://polygonscan.com/address/0x73341635f65cb51b450288bfcca653ba4fdaa261)        | [StakingRewards](https://polygonscan.com/address/0xACb9EB5B52F495F09bA98aC96D8e61257F3daE14)                                                                                                                   |
| [QuickswapUsdcUsdtStrategy](https://polygonscan.com/address/0xa3851408642cbe4babf85514f92f06c6fcef0cdf)       | [StakingRewards](https://polygonscan.com/address/0xAFB76771C98351Aa7fCA13B130c9972181612b54)                                                                                                                   |
| [SushiUsdcUsdtStrategy](https://polygonscan.com/address/0x4717eaa5da97f11bda3a3f021a20fd8cb72eab64)           | [SushiSwap Router](https://polygonscan.com/address/0x1b02dA8Cb0d097eB8D57A175b88c7D8b47997506)、[SushiSwap MiniChef](https://polygonscan.com/address/0x0769fd68dFb93167989C6f7254cd0D766Fb2841F)                |
| [SushiUsdcDaiStrategy](https://polygonscan.com/address/0xce531a4ecd1143b93dffaa054245a8f27a3e03fe)            |                                                                                                                                                                                                                |
| [Synapse4UStrategy](https://polygonscan.com/address/0x38d77bbfb522844e50dae8ec8ec62942d0de98c0)               | [SwapFlashLoan](https://polygonscan.com/address/0x85fCD7Dd0a1e1A9FCD5FD886ED522dE8221C3EE5)、[Synapse MiniChef](https://polygonscan.com/address/0x7875Af1a6878bdA1C129a4e2356A3fD040418Be5)                     |
| [DodoUsdtUsdcStrategy](https://polygonscan.com/address/0x257223fcc6f33e5067260c9c18620d2f6d524b61)            | [DODO](https://polygonscan.com/address/0x813FddecCD0401c4Fa73B092b074802440544E52)、[DODOMine](https://polygonscan.com/address/0xB14dA65459DB957BCEec86a79086036dEa6fc3AD)                                      |
