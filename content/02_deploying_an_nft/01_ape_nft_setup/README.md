# 设置

让我们加载合同 https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)


```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

让我们首先看一下NFT智能合约中的一个重要部分。那就是OpenZeppeling库。

OpenZeppelin是一个广泛信任的EVM模块化、可重用且安全的智能合约组件库，例如Arbtrum和ApeChain。它遵循行业最佳实践，并为开发者提供创建强大去中心化应用程序的工具。OpenZeppelin的合约经过审计，确保其可靠性和安全性。

在其核心，OpenZeppelin实现了像**ERC20**、**ERC721**和**ERC1155**这样的标准，这些标准分别定义了广泛接受的可替代代币、非可替代代币（NFT）和多代币标准接口。这些标准使区块链应用程序之间的互操作性成为可能，确保使用OpenZeppelin创建的代币或合约能够与钱包、市场和去中心化金融（DeFi）协议无缝集成。

**ERC721**合约为NFT提供了基础框架。它定义了非可替代代币的基本功能，包括独特的所有权、转移机制和元数据支持。通过导入这个标准，合约确保与支持NFT的平台或钱包兼容，如OpenSea或MetaMask。

**ERC721Enumerable**扩展通过启用对所有流通中的代币或特定地址拥有的代币的枚举，增强了标准的ERC721功能。这使得查询诸如“某个用户拥有哪些代币？”或“当前有多少代币？”之类的数据变得容易。它对于显示NFT集合的市场或仪表板尤其有用。

**ERC721URIStorage**扩展为管理代币元数据添加了高级功能。它允许每个代币存储一个唯一的URI，从而为个别NFT提供动态和详细的元数据。这对于创建具有丰富内容的代币非常理想，例如图像或其他相关文件。

**Ownable**合约引入了一个简单的访问控制机制，只有合约的拥有者才能执行某些功能。它包括像转移所有权和限制访问特定功能（例如铸造）这样的功能。它确保关键操作受到未授权访问的保护。