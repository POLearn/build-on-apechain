### **IPFS とメタデータのストレージ**

NFTのメタデータは通常、**IPFS (InterPlanetary File System)** に保存されます。これは分散型ストレージソリューションで、NFTデータが不変でアクセス可能であることを保証します。中央集権的なサーバーに頼る代わりに、IPFSはデータにユニークなコンテンツ識別子（CID）を割り当てます。例えば、以下のようになります：

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`

このCIDはメタデータファイルを指し示し、NFTデータへの信頼性の高い透明なアクセス方法を提供します。

### **シンプルなメタデータの例**

IPFSに保存された基本的なメタデータファイルを見てみましょう：

```json
{
  "name": "Ape Staking by POL",
  "description": "おめでとうございます！Ape NFTをステーキングする方法を学びました。Apeエコシステムの一員であることをありがとうございます。",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```

- **`name`**: NFTのタイトル。この場合は「Ape Staking by POL」です。
- **`description`**: NFTの簡単な説明。ここでは、ユーザーがApe NFTをステーキングしたことを祝います。
- **`image`**: NFTのビジュアル表現を指すCIDで、IPFSに保存されています。

### **メタデータの主な特徴**

1. **分散型**: IPFSに保存されたメタデータは改ざんに強く、長期的に保管されます。
2. **カスタマイズ可能**: メタデータには、特徴やレアリティのレベルなど、NFTの機能やユニークさを高める追加の属性を含めることができます。
3. **アクセス可能**: IPFSのCIDを使うことで、誰でもNFTのメタデータや画像を閲覧でき、透明性が確保されます。

### 🚀 クエスト: あなたのNFTをミントする

このコースの最終クエストでは、あなたのApeNFTの最初のNFTをミントします。以前、`safeMint` 関数を紹介しました。このメソッドはNFTを安全に作成するために重要です。NFTがミントされ、正当なアドレスに送信されることを保証します。さらに、すべてのNFTにはメタデータが必要で、これは **tokenURI** に保存されます。このtokenURIは、NFTに関する情報（名前、説明、画像など）へのリンクです。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)

1. **受信者アドレス**: ミント先のアドレスを選んでください（シンプルさのため、できれば自分のウォレットアドレスを選びましょう）。
2. **Token URI**: 以下の値をtokenURIとして使用します：
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

`safeMint` トランザクションを確認した後、このトランザクションを **PoL** に提出して、クエストの完了を証明してください。おめでとうございます 🎉

あなたはNFTを無事にミントし、このコースの最終クエストを完了しました！あなたの努力への報酬として、**POAP** をミントして、ApeChainエコシステムを通じたあなたの旅を祝ってください。知識を誇りに思い、ブロックチェーン革新の世界を引き続き探求し続けましょう！