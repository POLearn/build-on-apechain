# Configuración

Vamos a cargar el contrato [ApeNFT.sol](https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol)

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)

```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

Echemos primero un vistazo a una sección importante del contrato inteligente NFT. Estas son las bibliotecas de OpenZeppelin.

OpenZeppelin es una biblioteca ampliamente confiable de componentes modulares, reutilizables y seguros para contratos inteligentes en EVM, como Arbitrum y ApeChain. Se adhiere a las mejores prácticas de la industria y proporciona a los desarrolladores herramientas para crear aplicaciones descentralizadas robustas. Los contratos de OpenZeppelin están auditados, lo que garantiza su fiabilidad y seguridad.

En su núcleo, OpenZeppelin implementa estándares como **ERC20**, **ERC721** y **ERC1155**, que definen interfaces ampliamente aceptadas para tokens fungibles, tokens no fungibles (NFTs) y estándares de múltiples tokens, respectivamente. Estos estándares permiten la interoperabilidad entre aplicaciones blockchain, asegurando que los tokens o contratos creados con OpenZeppelin puedan integrarse sin problemas con billeteras, mercados y protocolos de finanzas descentralizadas (DeFi).

El contrato **ERC721** proporciona la base para los NFTs. Define la funcionalidad básica de los tokens no fungibles, incluida la propiedad única, los mecanismos de transferencia y el soporte de metadatos. Al importar este estándar, el contrato garantiza la compatibilidad con plataformas o billeteras que soportan NFTs, como OpenSea o MetaMask.

La extensión **ERC721Enumerable** mejora la funcionalidad estándar de ERC721 al permitir la enumeración de todos los tokens en circulación o los tokens que posee una dirección específica. Esto facilita la consulta de datos como "¿Qué tokens pertenecen a un usuario dado?" o "¿Cuántos tokens existen?". Es particularmente útil para mercados o paneles de control que muestran colecciones de NFTs.

La extensión **ERC721URIStorage** agrega funcionalidades avanzadas para gestionar los metadatos de los tokens. Permite que cada token almacene un URI único, habilitando metadatos dinámicos y detallados para NFTs individuales. Esto es ideal para crear tokens con contenido enriquecido, como imágenes u otros archivos asociados.

El contrato **Ownable** introduce un mecanismo simple de control de acceso donde ciertas funciones solo pueden ser ejecutadas por el propietario del contrato. Incluye características como la transferencia de propiedad y la restricción de acceso a funciones específicas (por ejemplo, la creación de nuevos tokens). Esto garantiza que las operaciones críticas estén protegidas contra accesos no autorizados.
