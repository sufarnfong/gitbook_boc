# Security Risks

The DeFi ecosystem is a new financial ecosystem. Before entering DeFi, users must understand investment and smart contract risks. This section focuses on the risks associated with BOC.

The following is a non-exhaustive list of security measures that were implemented.

1. To be able to avoid losses caused by code vulnerabilities, all protocols shall be audited by reputable auditors.
2. To reduce the risk of oracle attack, the quotation of the stablecoin must be based on a [decentralized oracle](https://chain.link/).
3. In order to avoid the chain system risk caused by nested tokens and LEGO combinations, the access to the aggregated financial management protocol needs to have a long-term security operation record and obtain the voting permission of the community.
4. In order to avoid impermanent losses caused by market fluctuations, the protocol for obtaining capital returns by providing risky services will not be accessed for the time being. At the same time leverage is not being used to magnify capital returns for the time being.

## Yield Dilution Risk

The increased liquidity from big whales can further dilute the yield of investing funds in a particular pool during rebalancing intervals.

## Smart Contract Risk

Smart contracts due to the complexities, even audited by professionals, can still post risk and are prone to hacks and unforeseeable events.

## Market Risk

The counterparty on the borrower's side lending protocols are also in default risk that cannot be rectified by liquidation in an extreme case of market fluctuation.

## Transaction Cost Risk

The automatic rebalancing that was triggered by network congestion will result in high transaction fee (gas fee) and affects the final yield rate.

## Oracle Attack Risk

Oracles are the bridge between the blockchain and the real world. Oracles act as on-chain APIs that can be queried for information to smart contracts including but not limited to price information and weather forecasts.

An oracle attack is when an oracle is corrupted/attacked and then the data being delivered on-chain may be highly incorrect and lead to smart contracts executing very wrong outcomes. If the oracle used by the third-party protocol strategy connected by BOC is attacked, the benefits of the protocol will no longer be real. This will affect the BOC to make wrong investment decisions based on the wrong quotation, which in turn affects the APY of the BOC.

Truly overcoming the oracle problem appear decentralized oracles to prevent data manipulation, inaccuracy, and downtime. A Decentralized Oracle Network, or DON for short, combines multiple independent oracle node operators and multiple reliable data sources to establish end-to-end decentralization. BOC uses [Chainlink](https://chain.link/) a high-rated decentralized oracle, making oracle attacks really improbable.
