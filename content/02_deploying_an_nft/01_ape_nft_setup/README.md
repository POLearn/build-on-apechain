# Configuration

Chargons le contrat [ApeNFT.sol](https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol)

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)

```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

Examinons d'abord une section importante du contrat NFT. Il s'agit des bibliothèques OpenZeppelin.

OpenZeppelin est une bibliothèque largement approuvée de composants modulaires, réutilisables et sécurisés pour les contrats intelligents EVM tels qu'Arbitrum et ApeChain. Elle adhère aux meilleures pratiques de l'industrie et fournit aux développeurs des outils pour créer des applications décentralisées robustes. Les contrats d'OpenZeppelin sont audités, garantissant leur fiabilité et leur sécurité.

Au cœur d'OpenZeppelin se trouvent des standards comme **ERC20**, **ERC721**, et **ERC1155**, qui définissent des interfaces largement acceptées pour les tokens fongibles, les tokens non fongibles (NFTs) et les standards multi-token, respectivement. Ces standards permettent l'interopérabilité entre les applications blockchain, garantissant que les tokens ou contrats créés avec OpenZeppelin peuvent s'intégrer parfaitement avec les portefeuilles, les places de marché et les protocoles de finance décentralisée (DeFi).

Le contrat **ERC721** fournit le cadre de base pour les NFTs. Il définit la fonctionnalité de base des tokens non fongibles, y compris la propriété unique, les mécanismes de transfert et le support des métadonnées. En important ce standard, le contrat garantit la compatibilité avec les plateformes ou portefeuilles prenant en charge les NFTs, tels qu'OpenSea ou MetaMask.

L'extension **ERC721Enumerable** améliore la fonctionnalité de base d'ERC721 en permettant l'énumération de tous les tokens en circulation ou des tokens appartenant à une adresse spécifique. Cela facilite l'interrogation de données telles que "Quels tokens appartiennent à un utilisateur donné ?" ou "Combien de tokens existent-il ?" Elle est particulièrement utile pour les places de marché ou les tableaux de bord affichant des collections de NFTs.

L'extension **ERC721URIStorage** ajoute des fonctionnalités avancées pour la gestion des métadonnées des tokens. Elle permet à chaque token de stocker un URI unique, offrant des métadonnées dynamiques et détaillées pour chaque NFT. Cela est idéal pour créer des tokens avec du contenu riche, comme des images ou d'autres fichiers associés.

Le contrat **Ownable** introduit un mécanisme simple de contrôle d'accès où certaines fonctions ne peuvent être exécutées que par le propriétaire du contrat. Il comprend des fonctionnalités telles que le transfert de propriété et la restriction de l'accès à des fonctions spécifiques (par exemple, la frappe). Cela garantit que les opérations critiques sont protégées contre tout accès non autorisé.