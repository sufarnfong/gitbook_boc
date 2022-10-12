# Harvest

The `harvestTrigger` is triggered daily to determine whether the `harvest` conditions are met. The two conditions are:

1. &#x20;Maximum time interval is exceeded.
2. &#x20;The harvest rules are met:

$$
Profit  > harvest cost
$$

If any of the above conditions are met, the strategy can perform `harvest`:

1. Execute the yield transfer Harvester (for the strategy with yield production and reach the yield selling threshold);
2. Report the current asset from the strategy.

| Set parameters                                                                                                                                                                                               | ETH               | Polygon           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- | ----------------- |
| Scheduled task trigger cycle                                                                                                                                                                                 | 22:00 daily (UTC) | 22:00 daily (UTC) |
| The maximum time interval for triggering the strategy `harvest` (if the interval between the current `harvest` and the last `harvest` or the last `lend` is greater than this value, `harvest` must be done) | 3 days            | 1 day             |
| The benefit-cost ratio factor X to trigger the strategy “harvest” ( if “harvest” profit >= cost\*X, “harvest” can be done.)                                                                                  | 5                 | 5                 |

###

####

