# 설정

다음 링크에서 계약을 로드해봅시다: [ApeNFT.sol](https://github.com/POLearn/build-on-apechain/blob/master/contract/ApeNFT.sol)

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_load.png)

```solidity
import {ERC721} from "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import {ERC721Enumerable} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import {ERC721URIStorage} from "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```

먼저 NFT 스마트 계약에서 중요한 부분을 살펴보겠습니다. 그것은 OpenZeppelin 라이브러리입니다.

OpenZeppelin은 Arbtrum과 ApeChain 같은 EVM을 위한 모듈화되고 재사용 가능하며 안전한 스마트 계약 구성 요소의 신뢰받는 라이브러리입니다. 이 라이브러리는 업계 모범 사례를 따르며 개발자가 강력한 분산 애플리케이션을 만들 수 있는 도구를 제공합니다. OpenZeppelin의 계약은 감사가 완료되어 신뢰성과 보안을 보장합니다.

OpenZeppelin의 핵심은 **ERC20**, **ERC721**, **ERC1155**와 같은 표준을 구현하는 것으로, 이는 각각 대체 가능한 토큰, 대체 불가능한 토큰(NFT), 다중 토큰 표준을 위한 널리 받아들여진 인터페이스를 정의합니다. 이러한 표준은 블록체인 애플리케이션 간의 상호 운용성을 가능하게 하여, OpenZeppelin으로 생성된 토큰이나 계약이 지갑, 마켓플레이스, 탈중앙화 금융(DeFi) 프로토콜과 원활하게 통합될 수 있도록 합니다.

**ERC721** 계약은 NFT의 기본적인 프레임워크를 제공합니다. 이 계약은 고유한 소유권, 전송 메커니즘, 메타데이터 지원 등을 포함하여 대체 불가능한 토큰의 기본 기능을 정의합니다. 이 표준을 가져옴으로써, 계약은 OpenSea나 MetaMask와 같은 NFT를 지원하는 플랫폼 또는 지갑과의 호환성을 보장합니다.

**ERC721Enumerable** 확장은 표준 ERC721 기능을 향상시켜 모든 토큰이나 특정 주소가 소유한 토큰을 열거할 수 있게 합니다. 이를 통해 "주어진 사용자가 소유한 토큰은 무엇인가?" 또는 "현재 존재하는 토큰의 수는 얼마인가?"와 같은 데이터를 쉽게 쿼리할 수 있습니다. 이는 NFT 컬렉션을 표시하는 마켓플레이스나 대시보드에서 유용합니다.

**ERC721URIStorage** 확장은 토큰 메타데이터를 관리하는 고급 기능을 추가합니다. 이를 통해 각 토큰은 고유한 URI를 저장할 수 있으며, 이를 통해 개별 NFT에 대한 동적이고 상세한 메타데이터를 제공할 수 있습니다. 이는 이미지나 기타 관련 파일과 같은 풍부한 콘텐츠를 가진 토큰을 생성하는 데 이상적입니다.

**Ownable** 계약은 특정 기능을 계약 소유자만 실행할 수 있도록 하는 간단한 접근 제어 메커니즘을 도입합니다. 이에는 소유권 이전이나 특정 기능(예: 민팅)에 대한 접근을 제한하는 기능이 포함되어 있습니다. 이는 중요한 작업이 무단 접근으로부터 보호될 수 있도록 합니다.