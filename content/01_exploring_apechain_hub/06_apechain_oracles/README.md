# What is an Oracle

Before exploring Price Oracles for APEChain, let’s quickly cover what an oracle is. In the world of smart contracts, an oracle is a service that provides real-world data to blockchains. Since blockchains can't access external information directly, oracles act as bridges, bringing off-chain data—like prices, weather, or sports scores—onto the blockchain.

For APEChain, the oracle service is provided by Pyth Network, which delivers real-time, high-quality market data. Pyth aggregates data from trusted sources like exchanges and market makers, ensuring accuracy and minimizing manipulation risks, so APEChain can rely on up-to-date, reliable information for its smart contracts

## ApeChain Oracle

We'll start by loading a contract onto the ApeChain mainnet Oracle. Specifically, we'll use the contract at address `0x2880aB155794e7179c9eE2e38200202908C17B43`, which is part of the ApeChain Oracle setup.

You can also check out the [full documentation here](https://docs.apechain.com/oracles) for a deeper understanding of how oracles work and how you can integrate them into your projects.

Let's load this in your desired IDE.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

Access to real-time price data is crucial when building decentralized applications (dApps). The `getPriceNoOlderThan` method allows you to retrieve the most recent price object for a specific price feed ID, ensuring that the price data is up-to-date within a time frame you specify.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

When you call the `getPriceNoOlderThan` method, you’ll provide two key arguments: the **price feed ID** and an **age** value. The **ID** specifies which price feed you want to access, while the **age** defines how recent the data can be. This is useful when you need a price that was updated at a specific point in time or for historical price data.

You can find the price feed IDs on the [Pyth Network Price Feed page](https://www.pyth.network/developers/price-feed-ids). For example, one of the price feed IDs available is for **ApeCoin/USD**, which is the ID we will use for our example.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

The `getPriceNoOlderThan` method returns a **price object** that contains the following key fields:

- **price**: The most recent price of the asset from the price feed.
- **conf**: The confidence level of the price, indicating how reliable the price feed is.
- **expo**: The exponent used for scaling the price.
- **publishTime**: The timestamp indicating when the price feed was last updated.

Here’s an example of a price object you might receive:

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 Quest: Calling

For this final section of the POAP, let's call the `getPriceNoOlderThan` method to retrieve the price data for **Ape/USD** using the specified **Price Feed ID** and **timestamp**.

Here’s what we’ll use:

- **Price Feed ID**: `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` (for Ape/USD)
- **Timestamp**: `1736651044`

Now, let's see how to call this method and get the result! We can see a value of `99675229`, which at the time was **0.99 USD**. For this submission, let's submit the entire JSON.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)