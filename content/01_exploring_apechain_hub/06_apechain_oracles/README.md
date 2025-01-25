# 什么是预言机 (Oracle)

在深入了解适用于 APEChain 的价格预言机之前，我们先快速了解一下什么是预言机。在智能合约的世界里，预言机是一种为区块链提供现实世界数据的服务。由于区块链无法直接访问外部信息，预言机就像桥梁一样，将链下数据（如价格、天气或体育比赛比分）带到区块链上。

对于 APEChain，预言机服务由 Pyth Network 提供。Pyth 提供实时、高质量的市场数据，通过汇总来自交易所和做市商等可信来源的数据，确保数据的准确性并最大程度地减少操纵风险，从而为 APEChain 的智能合约提供可靠的最新信息。

## ApeChain 预言机

我们将从将一个合约加载到 ApeChain 主网预言机开始。具体来说，我们将使用地址为 `0x2880aB155794e7179c9eE2e38200202908C17B43` 的合约，这是 ApeChain 预言机设置的一部分。

您还可以查看 [完整文档](https://docs.apechain.com/oracles)，以更深入地了解预言机的工作原理以及如何将其集成到您的项目中。

现在，我们将在您选择的 IDE 中加载它。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan` 方法

在构建去中心化应用程序 (dApp) 时，实时价格数据的访问至关重要。`getPriceNoOlderThan` 方法允许您获取特定价格源 ID 的最新价格对象，确保价格数据在您指定的时间范围内是最新的。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

调用 `getPriceNoOlderThan` 方法时，您需要提供两个关键参数：**价格源 ID** 和 **时间范围值**。**ID** 指定您想访问的价格源，而 **时间范围值** 定义了数据的更新时效。这在您需要某个特定时间点更新的价格或历史价格数据时非常有用。

您可以在 [Pyth Network Price Feed 页面](https://www.pyth.network/developers/price-feed-ids) 上找到价格源 ID。例如，**ApeCoin/USD** 的价格源 ID 是我们将在示例中使用的一个。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

`getPriceNoOlderThan` 方法会返回一个 **价格对象**，其中包含以下关键字段：

- **price**：价格源提供的资产最新价格。
- **conf**：价格的置信度，指示价格源的可靠性。
- **expo**：用于缩放价格的指数。
- **publishTime**：价格源上次更新时的时间戳。

以下是您可能收到的价格对象示例：

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 任务：调用

在 POAP 的最后部分，让我们调用 `getPriceNoOlderThan` 方法，以通过指定的 **价格源 ID** 和 **时间戳** 获取 **Ape/USD** 的价格数据。

我们将使用以下信息：

- **价格源 ID**：`0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` （对应 Ape/USD）
- **时间戳**：`1736651044`

现在，让我们看看如何调用此方法并获取结果！我们可以看到一个值为 `99675229`，当时相当于 **0.99 美元**。提交时，请提交完整的 JSON。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)