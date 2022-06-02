# Introduction to BOC

[BOC](https://v1.bankofchain.io/#/)（Bank Of Chain）是帮助普通投资者获取链上“无风险”保本理财的一款[去中心化金融](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%8E%BB%E4%B8%AD%E5%BF%83%E5%8C%96%E9%87%91%E8%9E%8Ddefi)[协议](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%8D%8F%E8%AE%AEprotocol)。

BOC平台连接加密生态系统内诸多协议，例如[AMM](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E8%87%AA%E5%8A%A8%E5%81%9A%E5%B8%82%E5%95%86amm)、[借贷协议](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%80%9F%E8%B4%B7%E5%8D%8F%E8%AE%AElending-protocol)、[收益聚合器等](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E6%94%B6%E7%9B%8A%E8%81%9A%E5%90%88%E5%99%A8yield-aggregators)(详情参见[Dashboard](https://dashboard-v1.bankofchain.io/#/))。通过接入高质量低风险的协议[策略](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E7%AD%96%E7%95%A5strategy)，BOC能实现比其他美元托管基金高300\~500个基点，这将是BOC吸引数亿美元的基础。

BOC对于加密行业的新人来说是进入数字资产投资回报生态系统的最佳渠道。作为一键复合理财平台，BOC将为行业带来新的革命。

## 为什么要开发BOC

现有的[DeFi](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%8E%BB%E4%B8%AD%E5%BF%83%E5%8C%96%E9%87%91%E8%9E%8Ddefi)协议存在如下问题：

1. 在[去中心化交易所](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%8E%BB%E4%B8%AD%E5%BF%83%E5%8C%96%E4%BA%A4%E6%98%93%E6%89%80-dex)里做市，存在[无偿损失](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E6%97%A0%E5%81%BF%E6%8D%9F%E5%A4%B1-impermanent-loss)。在2021年，UniswapV3做市收入约2亿美元收益，这些资金池遭受了2.6亿美元的无偿损失，导致6000万美元的净损失总额。
2. 部分收益聚合器存在[循环依赖](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%BE%AA%E7%8E%AF%E4%BE%9D%E8%B5%96-circular-dependency)的问题。
3. 部分协议投资门槛高。部分收益聚合器产品存在众多[机枪池](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E6%9C%BA%E6%9E%AA%E6%B1%A0vaults)，用户需要较高的知识储备才能正确选择投资哪些机枪池。同时，众多DeFi产品需要投资多种不同币种，需要用户自行兑换成所需币种。
4. 投资过程操作复杂。用户在投资再平衡过程中，需要实施取币、币种兑换和复投等复杂操作。

## 收益来源

1. 为[DEX](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%8E%BB%E4%B8%AD%E5%BF%83%E5%8C%96%E4%BA%A4%E6%98%93%E6%89%80-dex)提供做市资金收取的交易手续费 。
2. 为[超额抵押](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E8%B6%85%E9%A2%9D%E6%8A%B5%E6%8A%BC-over-collateralization)借贷提供借贷资金收取的利息 。
3. 在以上过程中获得的协议[治理币](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E6%B2%BB%E7%90%86%E5%B8%81governance-token)补贴。

## 资金分配规则

1. 优先分配给高收益的资金池 。
2. 单个资金池的投入资金，不能超过总投资资产的20% 。
3. 单个资金池的投入资金，不能超过其现有[锁仓量](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E9%94%81%E4%BB%93%E9%87%8F%E6%80%BB%E9%94%81%E5%AE%9A%E4%BB%B7%E5%80%BC-tvl)的50% 。
4. 同协议多个资金池的投入资金，不能超过总投资资产的30% 。
5. 定期进行收益评估，在调仓收益大于调仓成本时，对资金进行优化配置。

## 为何BOC与众不同

BOC作为开放式平台，通过连接加密生态众多协议实现分散投资，创建了长期的稳定的收益，避免了大部分风险。BOC竞争力体现在:

1. 易用：
   * 仅存取两项操作，无需进行[收割](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E6%94%B6%E5%89%B2-harvest)、兑换、调仓等复杂操作并支付费用。
   * 收益自动复投，资金随存随取。
   * 历史及动态收益直观可见。
2. 安全：
   * 合格稳定币已发行规模均超过10亿美元。
   * 合格区块链上的锁仓量已超过50亿美元。
   * BOC通过第三方严格审计。
   * 不使用第三方[跨链桥](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E8%B7%A8%E9%93%BE%E6%A1%A5bridge)。
   * 报价基于[Chainlink](https://chain.link/)。
3. 风控：
   * 稳定币脱锚风险：不使用算法稳定币，部分抵押稳定币，[长尾](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E9%95%BF%E5%B0%BE-the-long-tail)资产抵押生成稳定币。
   * 无偿损失的风险：做市限于稳定币资产交易对。
   * 连锁系统性风险：排除[嵌套代币](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E5%B5%8C%E5%A5%97%E4%BB%A3%E5%B8%81nested-tokens)和[乐高协议](https://github.com/Francisco-Rua/boc\_gitbook/blob/zh\_version/boc/appendix/README.md#%E4%B9%90%E9%AB%98%E5%BC%8F%E7%BB%84%E5%90%88-lego-combination)。
   * 长尾风险：不通过提供风险服务获取回报，如保险、期权。
   * 杠杆风险：未使用杠杆放大风险与回报。
4. 智能：
   * 定期评估各资金池收益变化，权衡调仓成本与收益。
   * 通过聚合器，寻找兑换最佳路径。
   * 进行外汇收益套利，并根据汇率和收益波动自动增减杠杆。
   * 设置复杂做市及借贷策略参数。

综上所述，BOC与市场上的类似产品相比，它在易用性、安全性、风控能力和智能投资方面，将带来行业革命和新市场增长。

|       竞品名称       |     [BOC](https://bankofchain.io)    |    [Yearn](http://yearn.finance/)   |     [OUSD](https://www.ousd.com/)     | [Aladdin DAO](https://aladdin.club/) | [enzyme](https://enzyme.finance/) |                     [Harvest](https://harvest.finance/)                    |        [beefy](https://beefy.finance/)        |                [alpha](https://alphafinance.io/)               | [yield app](https://www.yield.app/) |
| :--------------: | :----------------------------------: | :---------------------------------: | :-----------------------------------: | :----------------------------------: | :-------------------------------: | :------------------------------------------------------------------------: | :-------------------------------------------: | :------------------------------------------------------------: | :---------------------------------: |
|        分类        |                DeFi银行                |                收益聚合器                |                 算法稳定币                 |                 收益聚合器                |               链上资产管理              |                                    收益聚合器                                   |                     收益聚合器                     |                              收益聚合器                             |                DeFi银行               |
|       竞品介绍       | BOC是帮助普通投资者获取链上“无风险”保本理财的一款去中心化金融协议。 | Yearn Finance是区块链上的收益聚合器，由YFI持有人治理。 | Origin Dollar（OUSD）是在Ethereum上推出的稳定币。 |     AladdinDAO协议通过群体智慧优化DeFi资产分配。    |       Enzyme可以快速高效自定义构建投资策略。      | Harvest Finance是Ethereum、BNB Chain和Polygon上的收益聚合平台，使用户的资产在DeFi生态系统中获得最大收益。 | Beefy Finance是多链收益聚合器，使用户的资产在DeFi生态系统中获得最大收益。 | Alpha Finance Lab是一个跨链DeFi产品生态系统。Alpha Homora是第一款产品，是一种杠杆挖矿协议。 |    Yield App 是一个链接传统金融和去中心金融的桥梁。    |
|        支持链       |      Ethereum、BNB Chain、Polygon      |           Ethereum、Fantom           |                Ethereum               |               Ethereum               |              Ethereum             |                         Ethereum、BNB Chain、Polygon                         |           BNB Chain、Arbitrum、Fantom等          |                  Ethereum、BNB Chain、Avalanche                  |         Ethereum 、BNB Chain         |
| 锁仓量（截止2020年4月2日） |                  80万                 |                30.5亿                |                1.5582亿                |                 576万                 |              2.2931亿              |                                   2.2225亿                                  |                    10.215亿                    |                             8.278亿                             |               5.1271亿               |
|       治理代币       |                  暂无                  |                 YFI                 |                  OGN                  |                  ALD                 |                MLN                |                                    FARM                                    |                      BIFI                     |                              ALPHA                             |                 YLD                 |
|     是否需要KYC认证    |                   否                  |                  否                  |                   否                   |                   否                  |                 否                 |                                      否                                     |                       否                       |                                否                               |                  是                  |
|       是否开源       |                   是                  |                  是                  |                   是                   |                   是                  |                 是                 |                                      是                                     |                       是                       |                                是                               |                  否                  |
|      投资最小额度      |                   无                  |                  无                  |                   无                   |                   无                  |                 无                 |                                      无                                     |                       无                       |                                无                               |               100 USD               |
|      仅支持稳定币      |                   是                  |                  否                  |                   是                   |                   否                  |                 否                 |                                      否                                     |                       否                       |                                否                               |                  否                  |
|      稳定币实际回报     |                  8%                  |                5.46%                |                 8.97%                 |                 3.63%                |                 -                 |                                    5.42%                                   |                     4.41%                     |                              1.20%                             |                7-11%                |
|       池子数量       |                  2个                  |                  多个                 |                   1个                  |                  多个                  |                 多个                |                                     多个                                     |                       多个                      |                               多个                               |                  多个                 |
|      池子支持多策略     |                   是                  |                  是                  |                   是                   |                   否                  |                 是                 |                                      是                                     |                       否                       |                                否                               |                  未知                 |
|     支持自动资金调配     |                   是                  |               否，需要设置配额              |                   否                   |                   否                  |              否，基金经理调配             |                                  否，需要设置配额                                  |                       否                       |                                否                               |                  未知                 |
|    池子投资中会发生兑换    |                   是                  |                  否                  |                   否                   |                   否                  |                 是                 |                                      否                                     |                       否                       |                                否                               |                  未知                 |
|      策略挑选方式      |                 项目方严选                |                 社区投选                |                 项目方严选                 |                 社区投选                 |               基金经理严选              |                                    社区投选                                    |                      社区投选                     |                              社区投选                              |                项目方严选                |
|      考虑资金分散      |                   是                  |                  否                  |                   否                   |                   否                  |                 否                 |                                      否                                     |                       否                       |                                否                               |                  未知                 |
|      使用聚合兑换      |                   是                  |                  否                  |                   否                   |                   否                  |                 是                 |                                      否                                     |                       否                       |                                否                               |                  未知                 |
|     支持杠杆借贷投资     |                  暂无                  |                否，已剥离                |                   否                   |                   否                  |                 否                 |                                      否                                     |                       否                       |                                是                               |                  否                  |
|      支持随时提取      |                   是                  |                  是                  |                   是                   |                   是                  |                 是                 |                                      是                                     |                       是                       |                                是                               |                  是                  |
|       费用收取       |                 收益提成                 |               收益提成 管理费              |                收益提成 提取费               |                 收益提成                 |            收益提成、入场费、管理费           |                                    收益提成                                    |                    收益提成、管理费                   |                              收益提成                              |                 收益提成                |
