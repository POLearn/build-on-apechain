# Configuração

Vamos carregar o contrato [ApeNFT.sol](https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol)

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)

```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

Vamos dar uma olhada em uma seção importante do contrato NFT. São as bibliotecas da OpenZeppelin.

A OpenZeppelin é uma biblioteca amplamente confiável de componentes modulares, reutilizáveis e seguros para contratos inteligentes no EVM, como Arbitrum e ApeChain. Ela segue as melhores práticas do setor e oferece aos desenvolvedores ferramentas para criar aplicativos descentralizados robustos. Os contratos da OpenZeppelin são auditados, garantindo sua confiabilidade e segurança.

No seu núcleo, a OpenZeppelin implementa padrões como **ERC20**, **ERC721** e **ERC1155**, que definem interfaces amplamente aceitas para tokens fungíveis, tokens não fungíveis (NFTs) e padrões de múltiplos tokens, respectivamente. Esses padrões permitem a interoperabilidade entre aplicações blockchain, garantindo que tokens ou contratos criados com a OpenZeppelin possam ser integrados facilmente com carteiras, marketplaces e protocolos de finanças descentralizadas (DeFi).

O contrato **ERC721** fornece a estrutura fundamental para NFTs. Ele define a funcionalidade básica dos tokens não fungíveis, incluindo a propriedade única, mecanismos de transferência e suporte a metadados. Ao importar esse padrão, o contrato garante compatibilidade com plataformas ou carteiras que suportam NFTs, como OpenSea ou MetaMask.

A extensão **ERC721Enumerable** aprimora a funcionalidade do ERC721 padrão, permitindo a enumeração de todos os tokens em circulação ou tokens pertencentes a um endereço específico. Isso facilita consultas como "Quais tokens pertencem a um determinado usuário?" ou "Quantos tokens existem?" É particularmente útil para marketplaces ou dashboards que exibem coleções de NFTs.

A extensão **ERC721URIStorage** adiciona funcionalidades avançadas para gerenciar os metadados dos tokens. Ela permite que cada token armazene uma URI única, possibilitando metadados dinâmicos e detalhados para NFTs individuais. Isso é ideal para criar tokens com conteúdo rico, como imagens ou outros arquivos associados.

O contrato **Ownable** introduz um mecanismo simples de controle de acesso, onde certas funções só podem ser executadas pelo proprietário do contrato. Ele inclui funcionalidades como transferir a propriedade e restringir o acesso a funções específicas (por exemplo, mintagem). Isso garante que operações críticas estejam protegidas contra acessos não autorizados.