# Setup

Let load up the contract https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)


```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

Let's first a look at a important section fo the NFT smart contract. That is the OpenZeppeling libraries. 

OpenZeppelin is a widely trusted library of modular, reusable, and secure smart contract components for EVM such as Arbtrum and ApeChain. It adheres to industry best practices and provides developers with tools to create robust decentralized applications. OpenZeppelin's contracts are audited, ensuring their reliability and security.

At its core, OpenZeppelin implements standards like **ERC20**, **ERC721**, and **ERC1155**, which define widely accepted interfaces for fungible tokens, non-fungible tokens (NFTs), and multi-token standards, respectively. These standards enable interoperability across blockchain applications, ensuring that tokens or contracts created with OpenZeppelin can integrate seamlessly with wallets, marketplaces, and decentralized finance (DeFi) protocols.

The **ERC721** contract provides the foundational framework for NFTs. It defines the basic functionality of non-fungible tokens, including unique ownership, transfer mechanisms, and metadata support. By importing this standard, the contract ensures compatibility with platforms or wallets supporting NFTs, such as OpenSea or MetaMask.

The **ERC721Enumerable** extension enhances the standard ERC721 functionality by enabling enumeration of all tokens in circulation or tokens owned by a specific address. This makes it easy to query data like "What tokens belong to a given user?" or "How many tokens are in existence?" It’s particularly useful for marketplaces or dashboards displaying NFT collections.

The **ERC721URIStorage** extension adds advanced functionality for managing token metadata. It allows each token to store a unique URI, enabling dynamic and detailed metadata for individual NFTs. This is ideal for creating tokens with rich content, such as images or other associated files.

The **Ownable** contract introduces a simple access control mechanism where certain functions can only be executed by the owner of the contract. It includes features like transferring ownership and restricting access to specific functions (e.g., minting). This ensures that critical operations are safeguarded against unauthorized access.