# Fund allocation

### doHardWork

The inputs into the [position adjustment](protocol-algorithm-design-4.md#undefined) of the algorithm are the official [APY](../../more/appendix.md#annual-yield-apy) of the third-party protocol, the gas required for investment of each strategy, the limit of exchange [slippage](../../more/appendix.md#slippage), and the [rules of fund allocation](../../#fund-allocation-rules). Meanwhile, the strategy and amount of the funds to be invested are the outputs.

| Set parameters                                                                                           | ETH                     | Polygon                 |
| -------------------------------------------------------------------------------------------------------- | ----------------------- | ----------------------- |
| Scheduled Task Trigger Cycle                                                                             | 7 am daily besides Mon. | 7 am daily besides Mon. |
| Cost-benefit Calculation Period X (If the profit of investment X days >= cost, “doHardwork” can be done) | 365 days                | 365 days                |

### Position Adjustment

The position adjusting process mainly includes the following steps:

1. Invoke the optimal matching algorithm, allocate Vault funds, and issue a position adjustment report.
2. Lock-up; users will not be able to perform investment and redemption operations at this time.
3. According to the position adjustment report, perform the redeem operation on the strategy that needs to withdraw funds to return the funds to the Vault.
4. Calculate the currencies (token type(s)) and the amount needed for strategies investments.
5. Execute tokens swapping.
6. Invest the funds (swapped tokens) into the strategies.
7. Terminate the lock-up and complete the position adjustment.

### Allocation

Compared with `doHardWork`, `allocation` has an additional step: it withdraws the funds of the low APY strategy, then uses the official APY of the third-party protocols, the gas required for investment of each strategy, the exchange slippage limit, fund allocation rules, and the position adjustment algorithm as inputs, and the outputs are the strategy and the amount of the awaiting investment funds.

| Set parameters                                                                                            | ETH                           | Polygon                       |
| --------------------------------------------------------------------------------------------------------- | ----------------------------- | ----------------------------- |
| Pre-adjusted position report trigger timing                                                               | every Sun. (after doHardWork) | every Sun. (after doHardWork) |
| Scheduled task trigger cycle                                                                              | 7 am every Monday             | 7 am every Monday             |
| Cost-benefit calculation period X (If the profit of rebalancing X days >= cost, “allocation” can be done) | 30 days                       | 30 days                       |

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

| Set parameters                                                                                | ETH                                           | Polygon    |
| --------------------------------------------------------------------------------------------- | --------------------------------------------- | ---------- |
| Fund allocation calculation Exchange slippage settings                                        | 0.15%                                         | 0.15%      |
| Gas configuration (including strategy deposit and withdrawal Gas, exchange Gas, harvest cost) | 0 (become actual gas when asset > $5 million) | Actual Gas |

### Strategy APY Calculation

Strategy profits are mainly obtained from the four sources of yield as below:&#x20;

* Governance token rewards.
* DEX market-making fees.
* Interest from over-collateralized lending.
* Rewards from ETH2.0 staking.

In particular, for the ConvexIronBank protocol, BoC needs to pay a borrowing interest, therefore yields are negative.

### Official APY Calculation Rules

#### Governance tokens yield

1. Obtain the mining rate and mining coverage period of the pool of the start block and the end block respectively.
2. According to the data obtained in Step 1 above, calculate the average mining rate in a day, and calculate the total number of governance tokens that can be received by the pool in a day&#x20;
3. Based on the weighted totalSupply amount within 24 hours, the total principal of the reward pool is calculated.
4. Divide the total value of governance tokens received by the pool by the total principal of the pool, and annualize the income to obtain the APR rewarded by CRV.
5. Convert APR to APY.

#### DEX market-making fees

To obtain the rate of change of the targeted contract LP in net value. Taking the liquidity income provided by Curve as an example, the program obtains the two block heights within 24 hours in the past day, and obtains the virtualPrice of the two blocks using `getVirtualPrice()`. The rate of change is then calculated and annualized.

$$
baseApr = \frac{endVirtualPrice - startVirtualPrice}{startVirtualPrice} \times 365
$$

#### Interest from over-collateralized lending

To obtain the value of the loan rate interface of the targeted contract. Taking the lending interest provided by DForce as an example, the program obtains the two block heights within 24 hours of the past day, and uses `getSupplyTokenData()` to obtain the lending rate values ​​of the two blocks before annualizing them.

$$
baseApr = \frac{startSupplyTokenData[0]- endSupplyTokenData[0]}{2}
$$

#### Rewards from ETH2.0 staking

The protocol strategies holding wstETH and rETH will enjoy ETH2.0 staking rewards. Taking the protocol strategy holding wstETH as an example, the program obtains the two block heights within 24 hours in the past day, and uses `stEthPerToken()` to obtain the change of the net value of the two blocks before annualizing them.

$$
baseApr = \frac{endstEthPerToken - startstEthPerToken}{startstEthPerToken} \times 365
$$

#### Interest borrowing​

In order to avoid the risk exposure of holding foreign exchange tokens\[particularly the ConvexIronBank-like protocol(Convex)], foreign exchange will be borrowed by mortgaging USDC in the IronBank protocol. Therefore, the BoC needs to pay a borrowing interest, the yield is thus negative.&#x20;

The program obtains the borrowing rate of the two block heights in the IronBank foreign tokens contract within 24 hours in the past day by using `getBorrowInterest()`, and annualizing the averaged value of that to borrow interest.

$$
baseApr = -\frac{endBorrowInterest + startBorrowInterest}{2} \times oneDayBlocks \times 365
$$

### Verified APY Calculation Rules

BoC Verified APY includes Realized APY and Unrealized APY. The daily scheduled task of the program generates the Verified APY of the day before:

$$
Verified APY = Realized APY + Unrealized APY
$$

#### Governance tokens yield

The strategy's governance token revenue is recovered by executing the `harvest()` method.

web3 supports simulating the writing method of calling the contract to get the returned result, which is the basis for the program to obtain Unrealized APY. The program calculates the `harvest()` method under the daily start and end blocks to obtain the type and quantity of governance tokens that can be recovered by the strategy in that particular harvest.

The operational logic of the current strategy is to do the harvest at UTC 22:00:00. Regardless of whether the strategy does Harvest on that day, the strategy will have daily Unrealized APY. This is due to the presence of uncovered profits after the strategy harvest  between UTC 22:00:00\~UTC 23:59:59, which is also categorized as Unrealized APY.

As for the yield of Unrealized APY, since there is no actual selling action, the APY of the day is estimated and calculated by obtaining the exchange rate of the governance token to USD/ETH under the current block, and the next time when the actual selling is done, the price will be written back and updated. Unrealized APY will also be verified and converted into Realized APY.&#x20;

#### DEX market-making fees

The basic income of the day is calculated by accumulating the income during the operation period of the strategy in that day. By default, the DEX market-making income is issued in real time, which is categorized as Realized APY. Taking the liquidity income provided by Curve as an example, the main calculation process is as follows:

1. &#x20;Read the operations of the strategy on a daily basis: lend/withdraw/redeem/harvest.
2. Calculate the profit in each operation segment within the one-day range through Curve's `getVirtualPrice()`.
3. After accumulating the income of each segment, calculate the APR with the weighted principal of the day.

#### Interest from over-collateralized lending

Similar to the DEX market-making income, the program calculates the APR by accumulating the interest sum of all operating periods of the strategy within a day and the weighted principal of that day. The default interest is charged in real time, which is categorized as Realized APY.

#### Rewards from ETH2.0 staking

Similar to the DEX market-making income, the program calculates the APR by accumulating the staking profit of all operating periods of the strategy within a day and the weighted principal of that day. The default staking profit is charged in real time, which is categorized as Realized APY.

#### Interest borrowing​

Similar to the DEX market-making income, the program calculates the APR by accumulating the interest borrowed sum of all operating periods of the strategy within a day and the weighted principal of that day. The default interest borrowed is charged in real time, which is categorized as Realized APY.
