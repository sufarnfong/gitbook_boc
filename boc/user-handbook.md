# User Handbook

Here is a quick guide to interact and invest with the BOC platform. To complete the investment in BOC, we first start off on the user investment page. Go to the [home page](https://bankofchain.io/#/) and click on the `LAUNCH APP` button. You will now be directed to the main page of the APP.

![](<../.gitbook/assets/launchapp.png>)

## Wallet Connection

We can interact with BOC through [wallets](../more/appendix.md#wallet). The APP is compatible with [MetaMask](https://metamask.io/) and [WalletConnect](https://walletconnect.com/). By clicking on the `CONNECT WALLET` button, your wallet could be connected. 

![](<../.gitbook/assets/connectwallet.png>)

After connecting your wallet, you can see the USDT balance in your account.

![](<../.gitbook/assets/pic-4.png>)

## Parameter Settings

### Cross-chain Bridge

BOC provides two [cross-chain bridge](../more/appendix.md#bridge) options, which are the Polygon Bridge and the BNB Bridge, to fulfill the demand of cross-chain operations.

![](<../.gitbook/assets/chainbridge.png>)

### Switch Chain

At present, BOC works on Ethereum, BNB Chain and Polygon. If chain switching is required, this could be carried out by clicking on `NETWORKS` to select the desired chain to be switched to.

![](<../.gitbook/assets/networkchange.png>)

## Investment and Redemption

### Deposit

Once your wallet has been successfully connected, you can deposit by selecting the desired vault, either the `Vault for USDi` or the `Vault for ETHi`. On the `USDi Vault` under the `DEPOSIT` tab, we have the stablecoins to be used (USDT, UTDC & DAI). By entering the desired amount for each and clicking on `DEPOSIT`, depositing is hence completed. 

![](<../.gitbook/assets/pic-7.png>)

As on the `ETHi Vault`, you could only invest ETH by entering the desired amount and clicking on `DEPOSIT`.

![](<../.gitbook/assets/depositpage\_eth.PNG>)

The main difference between the `ETHi Vault` and the `USDi Vault` is that the `ETHi Vault` has a gas fee estimation.

### Withdrawal

After successfully connecting your wallet, you can complete the withdrawal by selecting the vault you would wish to use. on the `USDi Vault`, there is an option to either withdraw a single type of stablecoin or mixed. You proceed with the desired USDi and click `WITHDRAW`.

![](../.gitbook/assets/pic-8.png)

On the `ETHi Vault`, only ETH could be withdrawn. Enter the desired amount of ETHi and click `WITHDRAW`.

![](../.gitbook/assets/withdraw\_eth.PNG)

**Exchanged**: Exchange function enablement. Each strategy in the BOC uses different stablecoins. Money is always withdrawn according to the strategy APY from low to high. If a non-USDT strategy is obtained, the stable currency of the corresponding strategy will be returned, e.g., if Yearn LUSD is obtained, LUSD will be returned and if the exchange is closed, the corresponding value of LUSD will be returned to your account. If redemption is enabled, the Slippage parameter needs to be set.

### Withdrawal Advanced Parameters

![](<../.gitbook/assets/advancesetting.png>)

The advanced setup parameters are:

**Max Loss**: The maximum loss on withdrawals. When we specify the amount of USDi to withdraw, the total assets at the current net value will be displayed, but these are not the funds that we would obtain eventually. Losses might also occur during the withdrawal process. These include the exchange slippage losses. If our total assets are estimated to be $1000 currently, and we choose the Max Loss to be 0.3%, then we will gain at least $997.

**Slippage**: [Slippage](../more/appendix.md#slippage) between different currencies. After enabling Exchanged, we need to specify the slippage that we could accept.

### Adding USDi and ETHi to your wallet

If the USDi is not shown on your wallet, you are required to add it manually by simply clicking on the `+` sign next to your USDi balance and press `Add Token`. You will then be able to view you USDi balance on your metamask wallet.

{% embed url="https://www.youtube.com/embed/53kB-HakZCk" %}

Analogously, ETHi can also be added to the wallet by following the same procedure.

![](<../.gitbook/assets/addtoken\_ethi.png>)

## Dashboard

From the [dashboard](../more/appendix.md#dashboard) you could obtain the next relevant information regarding your assets and protocols that interact with them.

[https://dashboard.bankofchain.io](https://dashboard.bankofchain.io)

![](<../.gitbook/assets/dashboard.jpg>)

The data presented are described as follows:

1. On-chain Vault lock-up amount, read the subgraph interface.
2. The number of investment users, read the subgraph interface.
3. APY for the last 30 days based on net worth.
4. Proportion of protocol funds, query the subgraph interface.
5. The total assets of each strategy, read the contract interface.
6. Official APY, regularly pulled every morning.
7. Currency standard weekly profit, weekly APY.
8. Strategy Address.
9. Vault operation records, displayed with the blockchain browser.

BOC subgraph:

* ETH: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-eth](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-eth)
* BNB: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-bsc](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-bsc)
* POLYGON: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-matic](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-matic)

## Strategy Details

Take SushiUsdcUsdtStrategy as an example, enter the strategy details page as shown in the figure:

![](<../.gitbook/assets/detail.jpg>)

The data presented are described as follows:

1. Strategy Details
   * Strategy name
   * Stablecoins accepted by the strategy
   * The current total assets of the strategy (valued in USDT)
   * The total assets of the strategy's historical investment (valued in USDT)
2. Strategy Historical Return APY Performance
   * Historical official APY(yellow line)
   * Historical weekly APY(blue line)
3. Total Strategy Assets (Currency Standard)
4. Strategy Operation Asset Changes (Currency Standard)
5. Strategy Action Type
   * “harvest:: The strategy completes a mine sale and reinvestment, and reports the total asset valuation
   * “lend”: Vault puts funds into the strategy, and this action occurs in fund allocation (“doHardWork”, “allocation”)
   * “redeem”: Vault withdraws funds from the strategy, and this action occurs in the allocation of funds (“allocation”)

## Personal Investment Analysis

Enter the personal investment analysis page to see the personal investment income.

![](<../.gitbook/assets/personalpage.jpg>) 

The data presented are described as follows:

1. Personal investment total asset valuation (calculated in USDT).
2. Acquired BOC share.
3. Pass 30 days [APY](../more/appendix.md#annual-yield-apy).
4. Unwithdrawn earnings (calculated in USDT).
5. Withdrawn earnings (calculated in USDT).
6. Historical personal total assets.
7. Monthly income.
