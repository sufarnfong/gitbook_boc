# Mint & Burn rules

Here is a numerical example of minting and burning USDi tokens.

Assume that Alice deposits 100 USDT, 100 DAI and 100 USDC.

According to the BOC mint rule: the transaction price is 1 USD when the price from Chainlink is higher than 1 USD. Otherwise, the transaction price is equal to the price from Chainlink.

Thus, Alice will `mint` 299 USDi in total:

The current price from Chainlink is:

* 1 USDT = 1.01 USD
* 1 DAI = 0.99 USD
* 1 USDC = 1.00 USD

100 USDT = 100 x 1.00 = 100 USDi (price of Chainlink > 1 USD final price = 1 USD)\
100 DAI = 100 x 0.99 = 99 USDi (price of Chainlink < 1 USD final price = Chainlink price)\
100 USDC = 100 x 1.00 = 100 USDi (price of Chainlink = 1 USD final price = 1 USD)

![](../../.gitbook/assets/mint.png)

Now, Alice decides to `burn` the USDi to withdraw her stablecoins. She has 299 USDi now and when she burns depending on the proportion of USDT/USDC/DAI of the Vault. The burning smart contract will distribute the same proportion of the USDi on each stablecoin. In this case when we redeem there is slightly less USDT on the Vault, so the distribution will be 99 of them for USDT, 100 for DAI, and the rest 100 for USDC (assuming that the current price from Chainlink remains unchanged).

The rule of burning is opposite to that of minting: the transaction price is 1 USD when the price from Chainlink is less than 1 USD. Otherwise, the transaction price is equal to the price from Chainlink.

Therefore, Alice burns 299 USDi to withdraw:

Chainlink prices:

* 1 USDT = 1.01 USD
* 1 DAI = 0.99 USD
* 1 USDC = 1.01 USD

100 USDi = 100/1.01 = 99 USDT (price of Chainlink > 1 USD final price = Chainlink price)\
100 USDi = 100/1.00 = 100 DAI (price of Chainlink < 1 USD final price = 1 USD)\
100 USDi = 100/1.00 = 100 USDC (price of Chainlink = 1 USD final price = 1 USD)

![](../../.gitbook/assets/burn.png)

The numbers in the chart here are only numerical examples for a better understanding of the rules of minting and burning in BOC. In reality, the fluctuation of USDi is much smaller, indicating that users will never encounter such possible loss. In fact, the possible loss here will be less than 0.01%. The objectives of these rules are to avoid arbitrage and to protect the protocol's vault.
