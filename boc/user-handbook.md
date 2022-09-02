# User Handbook

## User Handbook

Here is a quick guide on interacting and investing with the BoC platform. To complete the investment in BoC, we first start off from the user investment page. Go to the [home page](https://bankofchain.io/#/) and click on the `LAUNCH APP` button. You will now be directed to the main page of the APP.

### Wallet Connection

We can interact with BoC through [wallets](../more/appendix.md#wallet). The APP is compatible with [MetaMask](https://metamask.io/) and [WalletConnect](https://walletconnect.com/). By clicking on the `CONNECT WALLET` button, your wallet could be connected.

![](../.gitbook/assets/user\_handbook\_ConnectWallet.png)

If your wallet has been successfully connected, your wallet address will appear on the `CONNECT WALLET` button.

![](../.gitbook/assets/user\_handbook\_wallet\_connected.png)

### Parameter Settings

#### Cross-chain Bridge

BoC provides two [cross-chain bridge](../more/appendix.md#bridge) options, which are the Polygon Bridge and the BNB Bridge, to fulfil the demand of cross-chain operations.

![](../.gitbook/assets/user\_handbook\_bridge.png)

#### Switch Chain

At present, BoC works on Ethereum, BNB Chain and Polygon. If chain switching is required, this could be carried out by clicking on `NETWORKS` to select the desired chain to be switched to.

![](../.gitbook/assets/user\_handbook\_network.png)

### Investment and Redemption

#### Deposit

Once your wallet has been successfully connected, you can deposit by entering the desired amount of any combinations of the stablecoin. The figure below uses `USDi Vault` as an example. Under the `DEPOSIT` tab, we have the stablecoins to be used (USDT, UTDC & DAI). By entering the desired amount for each and clicking on `DEPOSIT`, depositing is hence completed.

![](../.gitbook/assets/user\_handbook\_deposit2.png)

To demonstrate, we will deposit 10000 USDT, 20000 USDC and 30000 DAI into the protocol. The steps are illustrated by the four screenshots as follows:

**Figure 1:** Enter the desired amount for each type of stablecoins.

![](../.gitbook/assets/user\_handbook\_deposit\_exp.png)

**Figure 2:** After hitting the `DEPOSIT` button, we will proceed to the next step, which is to obtain the USDi ticket and to reconfirm the deposit amounts.

![](../.gitbook/assets/user\_handbook\_est\_USDi\_ticket.png)

**Figure 3:** After hitting `CONTINUE`, the METAMASK window appears, displaying the approved amount, protocol address and other related details for confirmation. This process repeats for each stablecoins (USDT, USDC and DAI). Figure 3 here only displays that of USDT.

![](../.gitbook/assets/user\_handbook\_deposit\_confirmation.png)

After confirming on the details, you shall be redirected to the deposit main page. If the stablecoins have been successfully deposited into the Vault, your current balance of each stablecoin should be updated and displayed as shown. The BoC protocol will allocate your funds into third-party protocols based on the fund allocation rules, which prioritizes liquidity pool of higher yields and adjusts automatically to ensure the most cost-efficient position. During this allocation process, your USDi ticket balance will be shown on-screen.

**Figure 4:** USDi ticket balance during fund allocation.

![](../.gitbook/assets/user\_handbook\_deposit\_completed.png)

After the fund allocation, the protocol exchanges the USDi ticket for USDi. After deducting the first allocation fee, USDi will then be distributed into your account, with the balance now viewable.

By hitting the `Switch to ETHi` tab, users will be directed to the ETHi Vault page for ETH depositing.

![](../.gitbook/assets/user\_handbook\_switchtoETHi.png)

The figure below illustrates the ETHi page for depositing:

![](../.gitbook/assets/user\_handbook\_ETHi.png)

As on the ETHi Vault, you could only invest ETH by entering the desired amount and clicking on `DEPOSIT`. The main difference between the ETHi Vault and the USDi Vault is that the former has a gas fee estimation, as shown in the figure above.

#### Withdrawal

After successfully depositing and ensuring that your wallet remains connected, you are now prepared to withdraw your funds. For instance on the USDi Vault, there is an option to either withdraw a single type of stablecoin or mixed. You are also required to enter the desired amount of each stablecoin to withdraw or you could simply select `Max` to withdraw all funds. After all parameters were entered correctly, you then proceed and click `WITHDRAW`.

![](../.gitbook/assets/user\_handbook\_withdraw\_exp.png)

To demonstrate, we will withdraw 40000 USDi into USDC. Withdrawal steps are illustrated by the three screenshots below:

**Figure 1:** Set the USDi amount to 40000 and select USDC as the stablecoin type before hitting `WITHDRAW`.

![](../.gitbook/assets/user\_handbook\_withdraw\_process.png)

**Figure 2:** After hitting `WITHDRAW` the METAMASK window appears, displaying details such as the estimated gas fee for confirmation.

![](../.gitbook/assets/user\_handbook\_withdraw\_confirmation.png)

**Figure 3:** After confirming on the details, you will be redirected to the withdrawal main page. You can then check to confirm whether withdrawal was successful by referring to the updated USDi balance.

![](../.gitbook/assets/user\_handbook\_withdraw\_complete.png)

By hitting the `Switch to ETHi` tab, users will be directed to the ETHi Vault page for ETH withdrawal.

![](../.gitbook/assets/user\_handbook\_switchtoETHi\_w.png)

The figure below illustrates the ETHi page for withdrawal:

![](../.gitbook/assets/user\_handbook\_ETHi\_w.png)

**Exchanged**: Exchange function enablement. Each strategy in the BoC uses different stablecoins. Money is always withdrawn according to the strategy APY from low to high. If a non-USDT strategy is obtained, the stable currency of the corresponding strategy will be returned, e.g., if Yearn LUSD is obtained, LUSD will be returned and if the exchange is closed, the corresponding value of LUSD will be returned to your account. If redemption is enabled, the Slippage parameter needs to be set.

#### Withdrawal Advanced Parameters

![](../.gitbook/assets/user\_handbook\_advancedPara.png)

The advanced setup parameters are:

**Max Loss**: The maximum loss on withdrawals. When we specify the amount of USDi to withdraw, the total assets at the current net value will be displayed, but these are not the funds that we would obtain eventually. Losses might also occur during the withdrawal process. These include the exchange slippage losses. If our total assets are estimated to be $1000 currently, and we choose the Max Loss to be 0.3%, then we will gain at least $997.

**Slippage**: [Slippage](../more/appendix.md#slippage) between different currencies. After enabling Exchanged, we need to specify the slippage that we could accept.

#### Adding USDi and ETHi to your wallet

If the USDi tokens deposited are not visible in your wallet, you will be required to import the tokens manually. As illustrated in the figure below, hit the `+` sign followed by `Add Token`.

![](../.gitbook/assets/user\_handbook\_addtoken\_manual.png)

See here for detailed tutorials:

{% embed url="https://www.youtube.com/embed/53kB-HakZCk" %}

Analogously, ETHi can also be added to the wallet by following the same procedure.

![](../.gitbook/assets/user\_handbook\_add\_token\_manual\_ETHi.png)

### Dashboard

From the [dashboard](../more/appendix.md#dashboard) you could obtain the next relevant information regarding your assets and protocols that interact with them.

[https://dashboard.bankofchain.io](https://dashboard.bankofchain.io)

![](../.gitbook/assets/user\_handbook\_dashboard.png)

The data presented are described as follows:

1. On-chain Vault lock-up amount, read from the subgraph interface.
2. The number of investment users, read from the subgraph nterface.
3. APY for the last 30 days based on net worth.
4. Proportion of protocol funds, queried from the subgraph interface.
5. The total assets of each strategy, read the contract interface.
6. Official APY, regularly pulled weekly.
7. APY from the harvest realized in the past 7 days.
8. APY from the unharvested profits in the past 7 days.
9. Weekly profit generated by the corresponding strategy, obtained after harvest has been executed.
10. Strategy Address.
11. Vault operation records (of recent activities), displayed with the blockchain browser.

BoC subgraph:

* ETH: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-eth](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-eth)
* BNB: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-bsc](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-bsc)
* POLYGON: [https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-matic](https://api.thegraph.com/subgraphs/name/bankofchain/boc-subgraph-matic)

### Strategy Details

Using UniswapV3UsdcUsdt500Strategy as an example, enter the strategy details page as shown in the figure:

![](../.gitbook/assets/user\_handbook\_strategy\_details.png)

The data presented are described as follows:

1. Strategy information:
   * Strategy name.
   * Stablecoins/Tokens accepted by the strategy.
   * The current total assets of the strategy (valued in USD).
   * The current status of the strategy.
2. Strategy historical return APY performance:
   * Historical official weekly APY(purple line).
   * Historical weekly APY(green line).
3. Value locked by the strategy (daily/weekly).
4. Profits generated by the strategy.
5. Official APY of the strategy.
6. APY measured by BoC.
7. Total strategy assets (currency standard).
8. Strategy operation asset changes (currency standard).
9. Strategy operation date.
10. Position details.

### Personal Investment Analysis

Enter the personal investment analysis page to see the personal investment income.

![](../.gitbook/assets/user\_handbook\_personal\_dashboard.png)

The data presented are described as follows:

1. Personal USDi balance.
2. To-harvest profit generated by third-party strategies, which transforms into realized profit once harvest is successfully executed (calculated in USDi).
3. Withdrawable profit in the BoC Vault gained after harvest (calculated in USDi).
4. Last 7 days [APY](../more/appendix.md#annual-yield-apy).
5. Last 30 days APY.
6. Daily USDi amount.
7. Monthly income.

## Withdrawal of funds from BoC Alpha version UI.

In September 2022, the BoC Beta version will be deployed, indicating that USDi holders will be required to withdraw all of their funds from the BoC Alpha version and redeposit into the BoC Beta version. Here is the tutorial on how to withdraw your funds from the BoC Alpha version.

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=QSfJgT8k6u0" %}

