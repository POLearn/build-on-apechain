# セットアップ

まず、契約をロードしましょう: [ApeNFT.sol](https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol)

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)

```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

次に、NFTスマート契約の重要な部分を見ていきましょう。それは、OpenZeppelinのライブラリです。

OpenZeppelinは、ArbitrumやApeChainのようなEVM向けのモジュール式、再利用可能、かつ安全なスマートコントラクトコンポーネントの広く信頼されたライブラリです。業界のベストプラクティスに従い、開発者が強力な分散型アプリケーションを作成するためのツールを提供します。OpenZeppelinの契約は監査されており、その信頼性とセキュリティが確保されています。

OpenZeppelinのコアでは、**ERC20**、**ERC721**、**ERC1155**などの標準が実装されており、これらはそれぞれ、代替可能なトークン、ノン・ファンジブル・トークン（NFT）、およびマルチトークン標準に広く受け入れられたインターフェースを定義しています。これらの標準は、ブロックチェーンアプリケーション間での相互運用性を確保し、OpenZeppelinで作成されたトークンや契約が、ウォレット、マーケットプレイス、分散型金融（DeFi）プロトコルとシームレスに統合できることを保証します。

**ERC721**契約はNFTの基盤となるフレームワークを提供します。これにより、ユニークな所有権、転送メカニズム、メタデータのサポートなど、ノン・ファンジブル・トークンの基本的な機能が定義されます。この標準をインポートすることにより、契約はOpenSeaやMetaMaskなどのNFTをサポートするプラットフォームやウォレットとの互換性を確保します。

**ERC721Enumerable**拡張は、標準のERC721機能を強化し、流通しているすべてのトークンや特定のアドレスが所有するトークンを列挙できるようにします。これにより、「特定のユーザーが所有するトークンは何か？」や「存在するトークンは何個か？」といったデータを簡単に照会できます。特に、NFTコレクションを表示するマーケットプレイスやダッシュボードに役立ちます。

**ERC721URIStorage**拡張は、トークンメタデータを管理するための高度な機能を追加します。これにより、各トークンはユニークなURIを保存でき、個々のNFTに動的で詳細なメタデータを提供できます。これは、画像やその他の関連ファイルなど、豊富なコンテンツを持つトークンを作成するのに最適です。

**Ownable**契約は、特定の機能を契約の所有者のみが実行できるようにするシンプルなアクセス制御メカニズムを導入します。これには、所有権の移転や特定の機能（例えば、ミント）のアクセスを制限する機能が含まれています。これにより、重要な操作が不正なアクセスから保護されます。