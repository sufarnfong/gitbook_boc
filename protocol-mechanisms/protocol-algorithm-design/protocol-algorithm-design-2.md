# Harvest

The `harvestTrigger` is triggered daily to determine whether the `harvest` conditions are met. The two conditions are:

1. Maximum time interval is exceeded.
2. The harvest rules are met:

$$
Profit \times 20\% > harvest cost
$$

If any of the above conditions are met, the strategy can perform `harvest`:

1. Execute the yield transfer Harvester (for the strategy with yield production and reach the yield selling threshold);
2. Report the current asset from the strategy.

| Set parameters                                                                                                                                                             | ETH           | BNB Chain     | Polygon       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------- | ------------- |
| Scheduled task trigger cycle                                                                                                                                               | 6:00 am daily | 6:00 am daily | 6:00 am daily |
| Maximum time interval for triggering strategie “harvest” (if the interval between current “harvest” and last “harvest” is greater than this value, “harvest” must be done) | 3 days        | 1 day         | 1 day         |
| The benefit-cost ratio factor X of the trigger strategy “harvest” (“harvest” profit>=cost\*X, then “harvest” can be done.)                                                 | 5             | 5             | 5             |

###

####

