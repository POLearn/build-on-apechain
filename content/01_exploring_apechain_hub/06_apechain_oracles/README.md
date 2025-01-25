### オラクルとは

Price Oracles for APEChainを探る前に、まずオラクルとは何かを簡単に説明しましょう。スマートコントラクトの世界で、オラクルはブロックチェーンにリアルワールドのデータを提供するサービスです。ブロックチェーンは外部の情報に直接アクセスできないため、オラクルはブリッジとして機能し、価格、天気、スポーツのスコアなどのオフチェーンデータをブロックチェーンに取り込みます。

APEChainにおけるオラクルサービスは、Pyth Networkによって提供されています。Pythは、リアルタイムで高品質な市場データを提供し、取引所や市場メイカーなどの信頼できるソースからデータを集約することで、正確性を確保し、操作リスクを最小限に抑えています。そのため、APEChainは最新で信頼性の高い情報をスマートコントラクトに利用することができます。

## ApeChain オラクル

最初に、APEChainのメインネットオラクルにコントラクトをロードします。具体的には、アドレス`0x2880aB155794e7179c9eE2e38200202908C17B43`にあるコントラクトを使用します。このコントラクトはAPEChainオラクル設定の一部です。

さらに、[こちらの完全なドキュメント](https://docs.apechain.com/oracles)をチェックして、オラクルがどのように機能するか、またどのようにプロジェクトに統合できるかについて深く理解することができます。

これをあなたの希望するIDEにロードしましょう。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

分散型アプリケーション（dApp）を構築する際、リアルタイムの価格データへのアクセスは非常に重要です。`getPriceNoOlderThan`メソッドを使用することで、特定の価格フィードIDに対して最も最近の価格オブジェクトを取得でき、指定した時間枠内でデータが最新であることを確認できます。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

`getPriceNoOlderThan`メソッドを呼び出す際には、2つの重要な引数を提供します。**価格フィードID**と**年齢**の値です。**ID**はどの価格フィードにアクセスするかを指定し、**年齢**はデータがどれくらい新しいかを定義します。これは、特定の時点で更新された価格や履歴の価格データが必要な場合に役立ちます。

価格フィードIDは[Pyth Network Price Feedページ](https://www.pyth.network/developers/price-feed-ids)で確認できます。例えば、利用可能な価格フィードIDの一つは**ApeCoin/USD**です。これを例として使用します。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

`getPriceNoOlderThan`メソッドは、以下の主要なフィールドを含む**価格オブジェクト**を返します：

- **price**: 価格フィードから取得した最も最近の資産価格。
- **conf**: 価格の信頼度を示す信頼レベル。
- **expo**: 価格をスケーリングするために使用される指数。
- **publishTime**: 価格フィードが最後に更新されたタイムスタンプ。

次のような価格オブジェクトが返される場合があります：

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 クエスト: コール

このPOAPの最後のセクションでは、`getPriceNoOlderThan`メソッドを呼び出して、指定した**価格フィードID**と**タイムスタンプ**を使用して**Ape/USD**の価格データを取得します。

使用する値は次の通りです：

- **価格フィードID**: `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864`（Ape/USD）
- **タイムスタンプ**: `1736651044`

このメソッドを呼び出して結果を取得する方法を見てみましょう！結果として、`99675229`という値が表示されます。この時点では、**0.99 USD**に相当します。この提出では、JSON全体を提出してください。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)