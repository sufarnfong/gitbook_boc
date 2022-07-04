# Protocol Components

## Incorporated Blockchains

BOC protocol is designed to be compatible with [Ethereum Virtual Machine (EVM)](../more/appendix.md#ethereum-virtual-machine-evm), actually BOC is connected with Ethereum, BNB Chain and Polygon chain.

### Ethereum

[**Ethereum**](https://ethereum.org) is a decentralized open source blockchain platform with [smart contract](../more/appendix.md#smart-contract) functions, whose native [cryptocurrency](../more/appendix.md#cryptocurrency) is ETH. In December 2021, Ethereum became the second most valuable cryptocurrency by market capitalization after Bitcoin, and the most widely used blockchain.

The concept of Ethereum was first proposed between 2013 and 2014 by the programmer Vitalik Buterin after being inspired by Bitcoin as "the next generation of cryptocurrency and decentralized application platform". Ethereum's development started through ICO crowdfunding in 2014.

Ethereum is also known as the "second-generation blockchain platform", second only to Bitcoin.

### BNB

[**Binance Smart Chain**](https://www.bnbchain.world/en) (formerly called BSC) is a blockchain compatible with the Ethereum virtual machine in parallel to the Binance Chain. It is a cutting-edge project in the crypto asset industry. By introducing the Proof of Stake Authority (PoSA) consensus mechanism, BNB creates a validating ecosystem that allows nodes, token holders, developers and users to enjoy the full benefit of the blockchain, such as higher performance and abundance of innovation space.

On February 15, 2022, the cryptocurrency exchange Binance announced that the original Binance Smart Chain (BSC) would be renamed to BNB Chain. BNB is the Binance Exchange platform cryptocurrency that powers the BNB Chain Ecosystem, and is one of the world’s most popular utility tokens.

### Polygon

[**Polygon**](https://wallet.polygon.technology/) is a protocol for building and interconnecting Ethereum-compatible blockchain networks. The project was launched in India in 2017 under the original name Matic Network. In February 2021, the project name was changed to Polygon. The cryptocurrency of the Polygon project is MATIC, one of the top 20 cryptocurrencies by market cap traded on major exchanges.

## Incorporated Stablecoins

In order to avoid the psychological fear caused by the fluctuations of digital currency value and the losses of market-making funds, BOC has selected only stable currency assets([stablecoins](../more/appendix.md#stablecoin)), and is only limited to those with full [collateral](../more/appendix.md#collateral) provided by fiat currency or by stablecoins.

Stablecoins need to meet the following conditions:

* The corresponding issuers should pass our due diligence check. 
* No algorithmic stablecoin allowed.
* Insurance available.
* Stablecoin quotes must be based on ChainLink.
* Market capital greater than $500 million / 200,000 ETH.

The currently selected strategic stablecoins are: DAI, USDC, USDT, BUSD, USDP, TUSD, LUSD.

### DAI

[**DAI**](https://makerdao.com/en/) is a stablecoin cryptocurrency designed to keep its value as close to a dollar as possible through an automated system of smart contracts on the Ethereum blockchain.

### USDC

[**USD Coin**](https://www.centre.io/usdc) (USDC) is a digital stablecoin pegged to the U.S. dollar that operates on the Ethereum, Stellar, Algorand, Hedera Hashgraph, and Solana blockchains. As of January 2022, USDC in circulation is $45.2 billion.

### USDT

[**USDT**](https://tether.to/en/), also known as USDT, is a controversial cryptocurrency issued by Tether Limited, which is controlled by the owners of Bitfinex. USDT is a stable currency. Launched in 2014, the coin is a blockchain-based platform that digitally facilitates the use of fiat currencies.

### BUSD

[**Binance USD**](https://www.binance.com/en/busd) (BUSD) is a new stablecoin launched by Binance and Paxos, which is pegged 1:1 to the US dollar.

### USDP

[**Pax Dollar**](https://paxos.com/usdp/) (USDP) is a fiat-collateralized stablecoin pegged 1:1 to the U.S. dollar.

### TUSD

[**TrueUSD**](https://www.trusttoken.com) (TUSD) is a USD-pegged stablecoin issued by Trusttoken.

### LUSD

[**LUSD**](https://www.liquity.org/) is a USD-pegged stablecoin issued by liquidity Protocol.

## Protocol strategy selection

After the stablecoin is selected, its corresponding strategies should meet the following conditions:

* Don't have a deposit or withdrawal fees.
* Don't have a lock-up period, so funds can be withdrawn rapidly.
* No limitation on the amount of funds for an investor.
* All protocols should be audited to keep away from potential losses caused by code vulnerabilities.
* The aggregated financial management protocol should count on a long-term safety operation record and obtains communities' permission via voting. Therefore, the risks caused by nested tokens and LEGO combinations can be circumvented.
* Don't use protocols that obtaining/magnifying capital returns by providing risky services or leverage.
* The first accessed DEX and lending protocol should be the preferred first-line protocols on every blockchain and also count with good safety operation records.
* The protocol should allocate their funds intelligently, which always obeys two rules: maximizing yields and decentralizing capital risks.

The following are selected protocols at present:

* in Ethereum: Convex, DODO, SushiSwap, Balancer, etc.
* in BNB Chain: DForce, Synapse, Venus, DODO, Belt, Pancakeswap, Alpaca, etc.
* in Polygon: DODO, Synapse, Quickswap, Balancer, Aave, Curve, SushiSwap, etc.

### Aave

[**Aave**](https://app.aave.com/) is an open-source decentralized lending protocol that provides users with deposit and lending services. The deposit and loan interest rates of users on both sides of the borrower and lenders are calculated by algorithms based on the platform's borrowing volume and deposit volume, and the platform uses Chainlink's oracle to ensure the fairness of the collateral price. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, Aave's total fund lock-up volume was approximately US$11.79 billion, ranking second in DeFi application lock-up volume.

### Curve

[**Curve**](https://curve.fi/) is a decentralized exchange deployed on Ethereum. Curve is designed for trading between stablecoins with low fees and slippage through an automated market maker protocol. It is a decentralized liquidity aggregator, and anyone can add their own assets to the liquidity pool to earn market-making benefits. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, Curve's total fund lock-up volume was approximately US$10.79 billion, ranking third in DeFi application lock-up volume.

### Convex

[**Convex**](https://www.convexfinance.com/) is a one-stop platform for CRV staking and liquidity mining on Ethereum that is dedicated to simplifying the use of Curve. As a yield aggregator on the Ethereum chain, Convex aims to use the CVX token to simplify the process of locking and staking Curve and CRV through a simple and easy-to-use interface, and to improve the compensation of CRV token holders and liquidity providers. This facilitates the development of the CRV ecosystem. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, Convex's total locked funds amounted to about $10.1 billion, ranking fourth in DeFi applications.

### Uniswap

[**Uniswap**](https://uniswap.org/) is a decentralized exchange deployed on Ethereum. The Uniswap protocol facilitates automated transactions between cryptocurrency tokens on the Ethereum blockchain through smart contracts. As of October 2020, Uniswap is estimated to be the largest decentralized exchange and the fourth largest cryptocurrency exchange by daily trading volume. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, Uniswap's total locked funds amounted to about $7.04 billion, ranking sixth in DeFi applications.

### Balancer

[**Balancer**](https://balancer.fi/) is a [decentralized exchange](../more/appendix.md#decentralized-finance-defi) deployed on Ethereum. Balancer uses automatic market makers to achieve the function of decentralized transactions. Transaction users can choose trading pairs to trade and pay transaction fees, while liquidity providers can get a share of the fees. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, Balancer's total fund lock-up volume was about 2.19 billion US dollars, ranking 6th in DeFi application lock-up volume.

### SushiSwap

[**SushiSwap**](https://app.sushi.com/swap) was originally a fork of Uniswap, built upon Uniswap's code, while introducing some key differences. One of the biggest differences is that rewards are issued in SUSHI tokens. SushiSwap's liquidity providers are rewarded with the protocol's native token, SUSHI, which is also a governance token. Unlike Uniswap (UNI), SUSHI holders can continue to earn yields even after they cease to provide liquidity. According to [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, among the rankings of centralized exchanges, Sushiswap's total lock-up volume of funds was approximately US$1.68 billion, ranking 11th in DeFi application lock-up volume.

### Quickswap

[**Quickswap**](https://quickswap.exchange/#/) is a layer2 decentralized exchange, similar to Uniswap and Sushiswap, using the AMM method. Anyone can invest money on Quickswap, provide liquidity, and earn income by staking liquidity tokens again. Quickswap's token, QUICK, is used as a governance token, and holders can submit proposals for changes to the protocol. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, among the rankings of centralized exchanges, Quickswap's total locked funds amounted to about US$473 million, ranking 22nd among DeFi applications.

### DODO

[**DODO**](https://app.dodoex.io/) is a decentralized trading platform that uses an original Proactive Market Maker (PMM) algorithm to provide efficient on-chain liquidity for Web3 assets, allowing everyone to easily issue and trade Web3 assets. DODO not only provides liquidity by itself, but also aggregates the liquidity of other exchanges. This allows DODO to offer the best prices on the entire network. According to the data of [DeFi Pulse](https://www.defipulse.com/), as of March 30, 2022, DODO's total fund lock-up volume was approximately US$47,700 million, ranking 52nd in DeFi application lock-up volume.

### dForce

[**dForce**](https://dforce.network/) is committed to building an integrated and interoperable matrix of open financial protocols and currency protocols, including lending protocols (global liquidity pools, interest-earning markets), asset-based protocols (multi-currency stablecoins, synthetic assets, etc.), liquidity aggregators, automatic market makers, etc. As of March 30, 2022, dForce's total lock-up volume of funds was approximately US$15,400, and DeFi applications ranked 69th in lock-up volume.

### Synapse

[**Synapse**](https://synapseprotocol.com/landing) was upgraded and renamed from Nerve Finance, an anonymous cross-chain liquidity protocol on the original BNB Chain.

Synapse adopts cross-chain multi-party computation (MPC) validator and threshold signature scheme to support assets, smart contract calls, etc. Synapse connects different blockchains for easy and secure interoperability; developers can also build real cross-chain applications, including cross-chain DEXs, lending platforms, margin systems, derivatives markets, income aggregators, and more.

### Venus

[**Venus**](https://app.venus.io/dashboard) is a synthetic stablecoin-driven decentralized currency market system on the BNB Chain, providing users with cryptocurrency lending solutions without the need for any third-party custody of funds or centralized entities to exercise more control over the protocol.

Borrowers on Venus can get instant loans in stablecoins after holding cryptocurrency. This enables users to obtain additional funds without having to sell their non-stablecoin digital assets. On the other hand, lenders can deposit stablecoins (and other different cryptocurrencies) on the platform to earn passive income. What makes Venus unique is how it promotes its own synthetic stablecoin within the cryptocurrency ecosystem. The synthetic stablecoins can maintain stable long-term value without holding the real-world assets they are pegged to (such as through algorithms, ecosystem incentive schemes, or using other forms of collateral).

### Pancakeswap

[**Pancakeswap**](https://pancakeswap.finance/) is a decentralized exchange on BNB Chain. Users can earn market-making income by providing liquidity to the platform, and earn Cake tokens by staking.

### Alpaca

[**Alpaca**](https://app.alpacafinance.org/lend) is the largest lending protocol on the BNB Chain that provides leveraged farms. Alpaca helps lenders earn income and provides borrowers with leveraged farm position loans with insufficient collateral, which maximizes the principal benefit of farmers' mining and can generate multiple returns.

## Incorporated Oracle

Oracles are data sources that connect Ethereum to off-chain, real-world information so that user can query data in smart contracts. It allows certain smart contracts to respond to the uncertain external world, and is the only way for smart contracts to interact with the outside world, and it is also the interface between blockchain and the real world.

### Chainlink

[**Chainlink**](https://chain.link/) is a decentralized oracle network that bridges the gap between smart contracts (like those on Ethereum) and their external data. The blockchain itself cannot connect to external applications in a trusted manner. Chainlink is not a single network of oracles, but an ecosystem of many decentralized oracle networks running in parallel, whose token is LINK.

## Protocol Contract Address

### Ethereum

| BOC Contract                                                                                            | 3rd Party Protocol Contract                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://etherscan.io/address/0xd5C7A01E49ab534e31ABcf63bA5a394fF1E5EfAC)                        |                                                                                                                                                                                                         |
| [Balancer3CrvStrategy](https://etherscan.io/address/0xa4bc7002d89ef7966c5b2fd70963eaa7a632bb19)         | [Balancer Vault](https://etherscan.io/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                               |
| [DodoUsdtUsdcStrategy](https://etherscan.io/address/0x88b7068a365a92fe648c6d6a99cc58a583756df5)         | [DSP](https://etherscan.io/address/0xC9f93163c99695c6526b799EbcA2207Fdf7D61aD) [DODOMine](https://etherscan.io/address/0xaeD7384F03844Af886b830862FF0a7AFce0a632C)                                      |
| [DodoDaiUsdtStrategy](https://etherscan.io/address/0xcace5387e7154594e0e95aa82f7779b2a0d8c9dc)          | [DSP](https://etherscan.io/address/0x3058EF90929cb8180174D74C507176ccA6835D73) [DODOMine](https://etherscan.io/address/0x1A4F8705E1C0428D020e1558A371b7E6134455A2)                                      |
| [SushiKashiUsdcLinkStrategy](https://etherscan.io/address/0x839672fff7bf86a273c9c1eb4ee72ca2496c7142)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0x4f68e70e3a5308d759961643AfcadfC6f74B30f4)                                                                                                        |
| [SushiKashiUsdtXsushiStrategy](https://etherscan.io/address/0xae4556510a43ff37df27d16a7ae8a08440a132da) | [KashiPairMediumRiskV1](https://etherscan.io/address/0xC84Fb1F76cbdd3b3491E81FE3ff811248d0407e9)                                                                                                        |
| [SushiKashiUsdtWethStrategy](https://etherscan.io/address/0x0adbfc6db10efd02786e3f590127079e74e4c128)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xfF7D29c7277D8A8850c473f0b71d7e5c4Af45A50)                                                                                                        |
| [SushiKashiUsdcWethStrategy](https://etherscan.io/address/0xfc3dd2cabf81999eb9e48ffb248ab048fccf348d)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xB7b45754167d65347C93F3B28797887b4b6cd2F3)                                                                                                        |
| [SushiKashiUsdcXsushiStrategy](https://etherscan.io/address/0x58c505ca34d908d7cb8349aaf6df7b942fe31a2e) | [KashiPairMediumRiskV1](https://etherscan.io/address/0x6EAFe077df3AD19Ade1CE1abDf8bdf2133704f89)                                                                                                        |
| [ConvexIronBankKrwStrategy](https://etherscan.io/address/0xb7e3eb6bbdd0cb9206ebd7c4d8351b52f61ca42b)    | [Iron Ban iKrw](https://etherscan.io/address/0x3c9f5385c288cE438Ed55620938A4B967c080101), [Curve.fi Factory Plain Pool ibKRW](https://etherscan.io/address/0x8461A004b50d321CB22B7d034969cE6803911899)  |
| [ConvexIronBankJpyStrategy](https://etherscan.io/address/0x0e0963f34560bc337513319c4a7bf65f4c083907)    | [Iron Ban iJPY](https://etherscan.io/address/0x215F34af6557A6598DbdA9aa11cc556F5AE264B1), [Curve.fi Factory Plain Pool ibJPY](https://etherscan.io/address/0x8818a9bb44Fbf33502bE7c15c500d0C783B73067)  |
| [ConvexIronBankGbpStrategy](https://etherscan.io/address/0x562c03b7822c9bcb9d19749a328d468eb8a15f48)    | [Iron Ban iGBP](https://etherscan.io/address/0xecaB2C76f1A8359A06fAB5fA0CEea51280A97eCF), [Curve.fi Factory Plain Pool ibGBP](https://etherscan.io/address/0xD6Ac1CB9019137a896343Da59dDE6d097F710538)  |
| [ConvexIronBankEurStrategy](https://etherscan.io/address/0x809491dc62e9177733e0ce11b0f73cd873d47ed3)    | [Iron Ban iEUR](https://etherscan.io/address/0x00e5c0774A5F065c285068170b20393925C84BF3), [Curve.fi Factory Plain Pool ibEUR](https://etherscan.io/address/0x19b080FE1ffA0553469D20Ca36219F17Fcf03859)  |
| [ConvexIronBankChfStrategy](https://etherscan.io/address/0x560419b9183db2c9fb8ae32dbc93bef5b34c7826)    | [Iron Ban iCHF](https://etherscan.io/address/0x1b3E95E8ECF7A7caB6c4De1b344F94865aBD12d5), [Curve.fi Factory Plain Pool ibCHF](https://etherscan.io/address/0x9c2C8910F113181783c249d8F6Aa41b51Cde0f0c)  |
| [ConvexIronBankAudStrategy](https://etherscan.io/address/0xca41275733bba2831487206631cb46ad40bfda5d)    | [Iron Ban iUSDT](https://etherscan.io/address/0x48759F220ED983dB51fA7A8C0D2AAb8f3ce4166a), [Curve.fi Factory Plain Pool ibAUD](https://etherscan.io/address/0x3F1B0278A9ee595635B61817630cC19DE792f506) |
| [Convex3CrvStrategy](https://etherscan.io/address/0x4d4700c777be1e11ec3af9465c90280788329964)           | [Curve.fi DAI/USDC/USDT Pool](https://etherscan.io/address/0xbEbc44782C7dB0a1A60Cb6fe97d0b483032FF1C7)                                                                                                  |
| [ConvexBusdStrategy](https://etherscan.io/address/0x264644dfbab5df335a05532a730421491808a7e5)           | [Curve.fi BUSD Swap](https://etherscan.io/address/0x79a8C46DeA5aDa233ABaFFD40F3A0A2B1e5A4F27)                                                                                                           |
| [ConvexLusdStrategy](https://etherscan.io/address/0x1f20dfb2b2ddbef30ea7c404d31970614dc5d6b5)           | [LUSD3CRV-f](https://etherscan.io/address/0xEd279fDD11cA84bEef15AF5D39BB4d4bEE23F0cA)                                                                                                                   |
| [ConvexBusdV2Strategy](https://etherscan.io/address/0x12896914a7fe92236d167c0c498b490d3aefd3e2)         | [Curve.fi BUSD V2](https://etherscan.io/address/0x4807862AA8b2bF68830e4C8dc86D0e9A998e085a)                                                                                                             |
| [ConvexYStrategy](https://etherscan.io/address/0x22ffc3b6b250c8bedee7e67c8e3ca6e2aaac63a4)              | [Curve.fi y Swap](https://etherscan.io/address/0x45F783CCE6B7FF23B2ab2D70e416cdb7D6055f51)                                                                                                              |
| [ConvexUsdtStrategy](https://etherscan.io/address/0x23a25fa21584b4b8f1348ac74396bf0ee8a72b6f)           | [Curve.fi USDT Swap](https://etherscan.io/address/0x52EA46506B9CC5Ef470C5bf89f17Dc28bB35D85C)                                                                                                           |
| [ConvexTusdStrategy](https://etherscan.io/address/0x968ebccd0e77644242ffb4468abe93774f75f34f)           | [TUSD3CRV-f](https://etherscan.io/address/0xEcd5e75AFb02eFa118AF914515D6521aaBd189F1)                                                                                                                   |
| [ConvexPaxStrategy](https://etherscan.io/address/0xf08fda0293cc8706ae1e280a9dc194c137cb63be)            | [pax-usdp3](https://etherscan.io/address/0xc270b3B858c335B6BA5D5b10e2Da8a09976005ad)                                                                                                                    |
| [ConvexCompoundStrategy](https://etherscan.io/address/0x02733188d0cbc87b4046b5ad12b9f3c8f3879c14)       | [Curve.fi Compound Swap](https://etherscan.io/address/0xA2B47E3D5c44877cca798226B7B8118F9BFb7A56)                                                                                                       |
| [ConvexAaveStrategy](https://etherscan.io/address/0x7f3bd67d7366dbc6b149f606cfa9c8fcdb72d9e2)           | [Curve.fi aDAI/aUSDC/aUSDT Pool](https://etherscan.io/address/0xDeBF20617708857ebe4F679508E7b7863a8A8EeE)                                                                                               |
| [YearnEarnTusdStrategy](https://etherscan.io/address/0x5c09ab7a2e09cc0f1d2e7f7ed189a7477c8e9623)        | [yearn yTUSD Token](https://etherscan.io/address/0x73a052500105205d34Daf004eAb301916DA8190f)                                                                                                            |
| [GUniUsdcDai100Strategy](https://etherscan.io/address/0x6488b7756e4338d73b85c61a67ca33921be59c88)       | [Gelato Uniswap DAI/USDC LP](https://etherscan.io/address/0x50379f632ca68D36E50cfBC8F78fe16bd1499d1e)                                                                                                   |

### BNB Chain

| BOC Contract                                                                                      | 3rd Party Protocol Contract                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://bscscan.com/address/0x76609c83dD684F0D4c0F0c9849db0a1b5a96CAB2)                   |                                                                                                                                                                                                             |
| [PancakeDaiBusdStrategy](https://bscscan.com/address/0x3fa2b30bfa5816b115b648d42955d3c3cb7bc368)  | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeTusdBusdStrategy](https://bscscan.com/address/0x3c87c8a62bc56b9663a256999c5aa333ce459857) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdcBusdStrategy](https://bscscan.com/address/0x05898f26ebfb39de28c55a7dc3d2ff062aa8defa) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdcUsdtStrategy](https://bscscan.com/address/0x06695568007119a0f79720cb0ad481c9ce640e9c) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdtBusdStrategy](https://bscscan.com/address/0xeccc75f9e1ba708c25202c744ea61dc93dc9a2f0) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [AlpacaTusdStrategy](https://bscscan.com/address/0x7983b99faf9854d82bbd100302defff4f6fd9b51)      | [ibTUSD](https://bscscan.com/address/0x3282d2a151ca00BfE7ed17Aa16E42880248CD3Cd)                                                                                                                            |
| [AlpacaUsdtStrategy](https://bscscan.com/address/0x568dced4cb4114359854f052fc5b776f6c6d12dc)      | [ibUSDT](https://bscscan.com/address/0x158Da805682BdC8ee32d52833aD41E74bb951E59)                                                                                                                            |
| [AlpacaBusdStrategy](https://bscscan.com/address/0x8178f4a3c7acc168cba50c8a70b4de8b63d6d892)      | [ibBUSD](https://bscscan.com/address/0x7C9e73d4C71dae564d41F78d56439bB4ba87592f)                                                                                                                            |
| [VenusTusdStrategy](https://bscscan.com/address/0x175724af9ec5e3e7b71934d31b5db4f8c4146db4)       | [vTUSD](https://bscscan.com/address/0x08CEB3F4a7ed3500cA0982bcd0FC7816688084c3)                                                                                                                             |
| [VenusUsdtStrategy](https://bscscan.com/address/0x21b31dc834588f81d2ae3fe64f3ce3c5bdbd070d)       | [VUSDT](https://bscscan.com/address/0xfD5840Cd36d94D7229439859C0112a4185BC0255)                                                                                                                             |
| [VenusUsdcStrategy](https://bscscan.com/address/0x1623cb1cd01e01d0dff7e5091197a8e261fb5596)       | [vUSDC](https://bscscan.com/address/0xecA88125a5ADbe82614ffC12D0DB554E2e2867C8)                                                                                                                             |
| [VenusDaiStrategy](https://bscscan.com/address/0xc0ce366cedbe7ba63036820c72c1ea7bccd8963f)        | [vDAI](https://bscscan.com/address/0x334b3eCB4DCa3593BCCC3c7EBD1A1C1d1780FBF1)                                                                                                                              |
| [VenusBusdStrategy](https://bscscan.com/address/0x65ab000d3474dcd0fa347935dba68f0dda354c88)       | [vBUSD](https://bscscan.com/address/0x95c78222B3D6e262426483D42CfA53685A67Ab9D)                                                                                                                             |
| [Belt4BeltStrategy](https://bscscan.com/address/0xa59d8ff6c63eefc8001c8d5501bde62fca564bc6)       | [beltPair](https://bscscan.com/address/0xF6e65B33370Ee6A49eB0dbCaA9f43839C1AC04d5) [MasterBelt](https://bscscan.com/address/0xD4BbC80b9B102b77B21A06cb77E954049605E6c1)                                     |
| [DodoBusdUsdcStrategy](https://bscscan.com/address/0x466cc0484a2077b769420bec7b0620bba5ffebd1)    | [DODO](https://bscscan.com/address/0x6064DBD0fF10BFeD5a797807042e9f63F18Cfe10)                                                                                                                              |
| [DodoBusdUsdtStrategy](https://bscscan.com/address/0xd1f9f90492ad3fccf0f1772be9f0a6bdaed27e84)    | [DODO](https://bscscan.com/address/0xBe60d4c4250438344bEC816Ec2deC99925dEb4c7)                                                                                                                              |
| [DForceLendBusdStrategy](https://bscscan.com/address/0x5960f21b3e388f4435ad61cb6b74440cb93de232)  | [iBUSD](https://bscscan.com/address/0x5511b64Ae77452C7130670C79298DEC978204a47)                                                                                                                             |
| [DForceLendDaiStrategy](https://bscscan.com/address/0x1a235ea7fee8ed513c271d19f46d8a66c66aacbc)   | [iDAI](https://bscscan.com/address/0xAD5Ec11426970c32dA48f58c92b1039bC50e5492)                                                                                                                              |
| [DForceLendUsdcStrategy](https://bscscan.com/address/0xdabf728c63e50c8655bd591200cdaed850270f97)  | [iUSDC](https://bscscan.com/address/0xAF9c10b341f55465E8785F0F81DBB52a9Bfe005d)                                                                                                                             |
| [DForceLendUsdtStrategy](https://bscscan.com/address/0xf0565751ed9cf38763a34a695060536092b4aa2f)  | [iUSDT](https://bscscan.com/address/0x0BF8C72d618B5d46b055165e21d661400008fa0F)                                                                                                                             |
| [Synapse4UStrategy](https://bscscan.com/address/0x1d63e9ef24a41582b003c3908b685fa9e9655e2b)       | [SwapFlashLoan](https://bscscan.com/address/0x28ec0B36F0819ecB5005cAB836F4ED5a2eCa4D13) [Synapse MiniChef](https://bscscan.com/address/0x8F5BBB2BB8c2Ee94639E55d5F41de9b4839C1280)                          |

### Polygon

| BOC Contract                                                                                                  | 3rd Party Protocol Contract                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://polygonscan.com/address/0xd3feAe6c4fdfDE73Bd2fE99c8fE6944904DAA68A)                           |                                                                                                                                                                                                                |
| [Curve3CrvStrategy](https://polygonscan.com/address/0x1f84a8c8c31674b89a4723521ead5a48579b8bf7)               | [Curve.fi Aave Pool](https://polygonscan.com/address/0x445FE580eF8d70FF569aB36e80c647af338db351) [Curve.fi Aave Gauge](https://polygonscan.com/address/0x19793B454D3AfC7b454F206Ffe95aDE26cA6912c)             |
| [AaveUsdtStrategy](https://polygonscan.com/address/0xb80a44d494acb8db24ff7047514a16bb554290e4)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf) [Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [AaveUsdcStrategy](https://polygonscan.com/address/0x5c9a02f7a45c5407bef7e98d69ca324a29803b15)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf) [Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [BalancerUsdcUsdtDaiTusdStrategy](https://polygonscan.com/address/0x23c75b1397ad73b3b572ccc9c3eb3ecede9682c4) | [Balancer Vault](https://polygonscan.com/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                                   |
| [QuickswapDaiUsdtStrategy](https://polygonscan.com/address/0xd55001d2508b58a7bc197c50c64ebbd0ae587300)        | [StakingRewards](https://polygonscan.com/address/0xc45aB79526Dd16B00505EB39222E6B1Aed0Ef079)                                                                                                                   |
| [QuickswapUsdcDaiStrategy](https://polygonscan.com/address/0x73341635f65cb51b450288bfcca653ba4fdaa261)        | [StakingRewards](https://polygonscan.com/address/0xACb9EB5B52F495F09bA98aC96D8e61257F3daE14)                                                                                                                   |
| [QuickswapUsdcUsdtStrategy](https://polygonscan.com/address/0xa3851408642cbe4babf85514f92f06c6fcef0cdf)       | [StakingRewards](https://polygonscan.com/address/0xAFB76771C98351Aa7fCA13B130c9972181612b54)                                                                                                                   |
| [SushiUsdcUsdtStrategy](https://polygonscan.com/address/0x4717eaa5da97f11bda3a3f021a20fd8cb72eab64)           | [SushiSwap Router](https://polygonscan.com/address/0x1b02dA8Cb0d097eB8D57A175b88c7D8b47997506) [SushiSwap MiniChef](https://polygonscan.com/address/0x0769fd68dFb93167989C6f7254cd0D766Fb2841F)                |
| [SushiUsdcDaiStrategy](https://polygonscan.com/address/0xce531a4ecd1143b93dffaa054245a8f27a3e03fe)            |                                                                                                                                                                                                                |
| [Synapse4UStrategy](https://polygonscan.com/address/0x38d77bbfb522844e50dae8ec8ec62942d0de98c0)               | [SwapFlashLoan](https://polygonscan.com/address/0x85fCD7Dd0a1e1A9FCD5FD886ED522dE8221C3EE5) [Synapse MiniChef](https://polygonscan.com/address/0x7875Af1a6878bdA1C129a4e2356A3fD040418Be5)                     |
| [DodoUsdtUsdcStrategy](https://polygonscan.com/address/0x257223fcc6f33e5067260c9c18620d2f6d524b61)            | [DODO](https://polygonscan.com/address/0x813FddecCD0401c4Fa73B092b074802440544E52) [DODOMine](https://polygonscan.com/address/0xB14dA65459DB957BCEec86a79086036dEa6fc3AD)                                      |
