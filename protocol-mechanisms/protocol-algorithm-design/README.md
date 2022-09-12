# Protocol Algorithm Design

BOC provides the [USD Stablecoins Farming](./#usd-stablecoins-farming-mechanism) and [ETH Farming](broken-reference).

## USD Stablecoins Farming Mechanism

### Process Description

<figure><img src="../../.gitbook/assets/Diagrama sin título.drawio.png" alt=""><figcaption></figcaption></figure>

1. **“Deposit”** - The BOC protocol supports users with the `deposit` function - to deposit the three major stablecoins (USDT, USDC, DAI) in any desired combination and amount. BOC also allows minting of USDi of the corresponding value to be returned to the user.\
   **“Withdraw”** - Users can `withdraw` USDi which consists of the three major stablecoins at their convenience through the BOC protocol. By default, they will be returned according to the proportion of the three major stablecoins in the [Vault](../../more/appendix.md#vaults) at that time, or they can specify a certain currency to be returned.
2. After the Vault receives the stablecoin, `queryTokenPrice` queries the price of the user's transfer of the [stablecoin](../../more/appendix.md#stablecoin) through an external oracle. When the price returned by the [oracle](../../more/appendix.md#oracle) is higher than 1 USD, it is calculated at 1 USD, whereas while it is lower than 1 USD, it is calculated at the price of the oracle.
3. Based on the calculated value, `mint/burn` will [mint/burn](protocol-algorithm-design-1.md) an equivalent value of USDi tickets.
4. The [Keeper](../../more/appendix.md#keeper) module reaches the trigger condition `doHardWork` and triggers `doHardWork`.
5. After the Keeper trigger `doHardWork` the vault allocates the funds and exchanges the USDi tickets (burn) for USDi (mint).&#x20;
6. Vault calls the aggregate exchange module `swapTokenToWants`.
7. The aggregated exchange module `swapTokens` completes the exchange.
8. Vault receives the targetted currency exchanged by the aggregate exchange module.
9. Vault puts stablecoin `deposits` into the strategy according to the currency required by the strategy.
10. The [strategy](../../more/appendix.md#strategy) invests stablecoin `deposits` into third-party protocols.
11. The Keeper module reaches the `harvest` trigger condition and triggers the `harvest`.
12. Harvester triggers each strategy to execute `harvest`.
13. Each strategy executes `claimRewards` to collect mining.
14. Each strategy transfers mining coins `transferRewards` to Harvester.
15. Harvester sells miners `sellRewards` into stablecoins through the aggregated exchange.
16. Harvester `sendProfitToVault` transfers stablecoins into Vault.
17. The Keeper module reaches the `rebase` trigger condition and triggers the `rebase`.
18. Vault calls `changeTotalSupply` to issue additional USDi.
19. Vault collects 20% of the yield, which is transferred to the `Treasury`.
20. The [treasury](../../more/appendix.md#daos-treasury) will benefit users by using `buyback` to repurchase the BOC governance token.

### ETH Farming Mechanism

The mechanism of ETH farming is exactly the same as that of the USD stablecoins farming at present. The only difference is that the collateral of USD stablecoins is USDi, thus that of ETH is called ETHi.



{% content-ref url="protocol-algorithm-design.md" %}
[protocol-algorithm-design.md](protocol-algorithm-design.md)
{% endcontent-ref %}

{% content-ref url="protocol-algorithm-design-1.md" %}
[protocol-algorithm-design-1.md](protocol-algorithm-design-1.md)
{% endcontent-ref %}

{% content-ref url="protocol-algorithm-design-2.md" %}
[protocol-algorithm-design-2.md](protocol-algorithm-design-2.md)
{% endcontent-ref %}

{% content-ref url="protocol-algorithm-design-3.md" %}
[protocol-algorithm-design-3.md](protocol-algorithm-design-3.md)
{% endcontent-ref %}

{% content-ref url="protocol-algorithm-design-4.md" %}
[protocol-algorithm-design-4.md](protocol-algorithm-design-4.md)
{% endcontent-ref %}

