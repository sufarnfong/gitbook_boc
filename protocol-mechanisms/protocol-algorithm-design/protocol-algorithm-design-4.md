# Fund allocation

### doHardWork

The inputs into the position adjustment of the algorithm are the official [APY](../../more/appendix.md#annual-yield-apy) of the third-party protocol, the gas required for investment of each strategy, the limit of exchange [slippage](../../more/appendix.md#slippage), and the [rules of fund allocation](https://github.com/Francisco-Rua/boc\_gitbook/blob/master/how-it-works/introduction-to-boc/README.md#fund-allocation-rules). Meanwhile, the strategy and amount of the funds to be invested are the outputs.

| Set parameters                                                                                           | ETH                     | BNB Chain               | Polygon                 |
| -------------------------------------------------------------------------------------------------------- | ----------------------- | ----------------------- | ----------------------- |
| Scheduled Task Trigger Cycle                                                                             | 7 am daily besides Mon. | 7 am daily besides Mon. | 7 am daily besides Mon. |
| Cost-benefit Calculation Period X (If the profit of investment X days >= cost, “doHardwork” can be done) | 365 days                | 365 days                | 365 days                |

### Allocation

Compared with `doHardWork`, `allocation` has an additional step: it withdraws the funds of the low APY strategy, then uses the official APY of the third-party protocols, the gas required for investment of each strategy, the exchange slippage limit, fund allocation rules, and the position adjustment algorithm as inputs, and the outputs are the strategy and the amount of the awaiting investment funds.

| Set parameters                                                                                            | ETH                           | BNB Chain                     | Polygon                       |
| --------------------------------------------------------------------------------------------------------- | ----------------------------- | ----------------------------- | ----------------------------- |
| Pre-adjusted position report trigger timing                                                               | every Sun. (after doHardWork) | every Sun. (after doHardWork) | every Sun. (after doHardWork) |
| Scheduled task trigger cycle                                                                              | 7 am every Monday             | 7 am every Monday             | 7 am every Monday             |
| Cost-benefit calculation period X (If the profit of rebalancing X days >= cost, “allocation” can be done) | 30 days                       | 30 days                       | 30 days                       |

### Fund allocation Algorithm

| Variable       | Meaning                                                                                                                                                                                                                   |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "durationDays" | The cycle of rebalancing needs to ensure that in a cycle after rebalancing, $$the profit after rebalancing - the profit before rebalancing - the cost of rebalancing > 0$$ (has to be greater than 0)                     |
| "yearDays"     | 365days                                                                                                                                                                                                                   |
| "asset1"       | The original assets of the strategy                                                                                                                                                                                       |
| "apr1"         | The strategy apr before the position adjustment (APY needs to be converted into apr). The current value of the APY of the position adjustment algorithm is the 7-day average of APY calculated outside the strategy chain |
| "deltaAsset"   | Assumed as the capital change value of the strategy rebalancing                                                                                                                                                           |
| "poolAssets1"  | The TVL of the strategic target investment pool is used as a parameter for the change of apr after the position adjustment                                                                                                |

**Profit before position adjustment**

$$
gain1 = \frac{asset1 \times apr1 \times durationDays}{yearDays}
$$

**Changed earnings**

$$
gain2 = \frac{(asset1+deltaAsset-exchangeLoss)\times apr2 \times durationDays}{yearDays}
$$

**Changed apr**

$$
apr2 = \frac{apr1 \times poolAssets1}{(poolAssets1+deltaAsset-exchangeLoss)}
$$

After substituting apr2 in gain2 using the above equation:

$$
gain2=\frac{apr1 \times durationDays/yearDays \times (asset1+deltaAsset) \times poolAssets1}{poolAssets1+deltaAsset-exchangeLoss}
$$

Hence the relationship between the changed income of a single strategy and the changed assets is:

$$
deltaGain = gain2-gain1 = \frac{deltaAsset \times (poolAsset1-asset1) \times apr1 \times durationDays}{(poolAsset1+deltaAsset-exchangeLoss) \times yearDays}
$$

**Cost of changing funds for a single strategy**

| variable name    | Details                                                                                        |
| ---------------- | ---------------------------------------------------------------------------------------------- |
| withdrawFee      | Withdrawal Fund Handling Fee                                                                   |
| lendFee          | Additional capital operation fee                                                               |
| exchangeLoss     | Exchange currency slippage loss                                                                |
| harvestFee       | “harvest” Funding Fees                                                                         |
| profitChangeFee  | Capital change cost                                                                            |
| withdrawGas      | withdrawGas is the gas consumed by the “withdraw” operation, which is estimated by pre-testing |
| lendGas          | lendGas is the gas consumed by the “lend” operation, which is estimated by pre-testing         |
| exchangeLossRate | Redeem Slippage                                                                                |

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

Find the maximum sum of `deltaGain` for all strategies:

$$
profitChange=MAX\sum_{i=1}^m(deltaGain_i -withdrawFee_i-lendFee_i - exchangeLoss_i-harvestFee_i)
$$

$$
profitChange=MAX\sum_{i=1}^m(\frac{deltaAsset_i \times (poolAsset_i-asset_i) \times apr_i * durationDays_i}{(poolAsset_i+deltaAsset_i-exchangeLoss_i) \times yearDays_i}
$$

$$
- operateFee_i - exchangeLoss_i - harvestFee_i)
$$

In the formula above (profitChange), the only variable is the deltaAsset for each strategy. Meanwhile, the solution needs to be limited by:

**Restrictions**

1. The same protocol strategy (multiple constraints) funds do not exceed 30% of the total funds.
2. The sum of all asset changes in and out is 0.

**Boundary conditions**

1. Strategic assets do not exceed 20% of the total assets.
2. The strategic funds do not exceed 50% of the targetted pool assets.

Use python scipy's `optimize.minimize` to find the current optimal rebalancing scheme.

#### Public Parameter Configuration

| Set parameters                                                                                | ETH                                           | BNB Chain  | Polygon    |
| --------------------------------------------------------------------------------------------- | --------------------------------------------- | ---------- | ---------- |
| Fund allocation calculation Exchange slippage settings                                        | 0.15%                                         | 0.15%      | 0.15%      |
| Gas configuration (including strategy deposit and withdrawal Gas, exchange Gas, harvest cost) | 0 (become actual gas when asset > $5 million) | Actual Gas | Actual Gas |

### Official APY Calculation Rules

The official APY rules are needed as a reference when allocating funds. The sources of official APY are as follows: vfat.tools, coingecko, zapper, Official APY, apy.vision Fee, etc. If the APY calculation of the protocol strategy is not included in the official APY source channel, BOC will copy the official APY calculation rules of the protocol strategy. In general, the official APY of the protocol strategy consists of market-making revenue and mining coin revenue. Taking the “ConvexLusdStrategy” strategy that BOC has already docked as an example, its APY consists of the contents in following table:

| APY Mark | APR         | APY              | Compound Interest | Calculation Method   | Data Source                                                                        |
| -------- | ----------- | ---------------- | ----------------- | -------------------- | ---------------------------------------------------------------------------------- |
| Trx Fee  | 0.0024      | Tx Fee           | N                 | API                  | https://www.convexfinance.com/api/curve-apys                                       |
| crv      | 0.023523458 | cvx mining coins | Y                 | API                  | https://www.convexfinance.com/api/curve-apys                                       |
| cvx      | 0.024132445 | cvx mining coins | Y                 | Contract Calculation | Issued according to time, one-year mining coin price/total pool assets can get APR |

$$
APY=(1+APR)^{periods}-1
$$

The “periods” parameter is the interest payment period.

### Strategy Actual APY Calculation Rules

The actual APY of the strategy is calculated based on the standard return of the strategy currency.
