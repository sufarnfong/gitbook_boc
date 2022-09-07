# 铸造(Mint)/销毁(Burn)规则

### 铸造(Mint)/销毁(Burn)流程示意图

<figure><img src="../../.gitbook/assets/mint.png" alt=""><figcaption><p>铸造 (Mint)</p></figcaption></figure>

上图为用户存入稳定币并`mint`出等价的USDi的规则流程图。

用户将手中的三大稳定币（USDT、USDC、DAI）以任意组合、任意数量存入，根据当下预言机Chainlink的价格，铸造出等价的USDi作为抵押凭证。

假设用户存入USDT, DAI和USDC各100，此时预言机的价格为：

1 USDT = 1.01 USD\
1 DAI = 0.99 USD\
1 USDC = 1.00 USD

根据BOC的`mint`规则：预言机价格高于1USD时按1USD算，低于1USD时按预言机价格算。

则最终用户能`mint`出299 USDi ：

100 USDT = 100 x 1.00 = 100 USDi (预言机价格 > 1USD，按1USD算)\
100 DAI = 100 x 0.99 = 99 USDi (预言机价格 < 1USD，按预言机价格算)\
100 USDC = 100 x 1.00 = 100 USDi (预言机价格 = 1USD，按1USD算)

<figure><img src="../../.gitbook/assets/burn.png" alt=""><figcaption><p>销毁 (Burn)</p></figcaption></figure>

当用户取出池中稳定币时，需要提供并销毁(`burn`)手上的抵押凭证USDi。

BOC的销毁规则与铸造币时相反：预言机价格高于1USD时按预言机价格算，低于1USD时按1USD算。假设预言机价格不变。

用户销毁(`burn`)手中的299 USDi以取出其对应的稳定币 (假设用户将100 USDi用来取USDT, 99 USDi用来取DAI, 100 USDi用来取USDT)：

100 USDi = 100/1.01 = 99 USDT (预言机价格 > 1USD，按预言机价格算)\
100 USDi = 100/1.00 = 100 DAI (预言机价格 < 1USD，按1USD算)\
100 USDi = 100/1.00 = 100 USDC (预言机价格 = 1USD，按1USD算)

此机制的目的是保护协议，防止套利和预言机被攻击。

###



