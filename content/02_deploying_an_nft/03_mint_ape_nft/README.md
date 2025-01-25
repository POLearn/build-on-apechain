### **IPFS와 메타데이터 저장**  

NFT의 메타데이터는 일반적으로 **IPFS (InterPlanetary File System)**에 저장됩니다. IPFS는 분산 저장 솔루션으로, NFT 데이터가 변경 불가능하고 접근 가능한지 보장합니다. 중앙 서버에 의존하는 대신, IPFS는 데이터를 고유한 콘텐츠 식별자(CID)로 식별합니다. 예를 들어, CID는 이렇게 보일 수 있습니다:  

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`  

이 CID는 메타데이터 파일을 가리키며, NFT의 데이터를 신뢰할 수 있고 투명한 방식으로 접근할 수 있게 합니다.  

### **간단한 메타데이터 예시**  

다음은 IPFS에 저장된 기본적인 메타데이터 파일입니다:

```json
{
  "name": "Ape Staking by POL",
  "description": "Congratulations! You have successfully learned how to stake an Ape NFT. Thanks for being a part of Ape Ecosystem.",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```

- **`name`**: NFT의 제목. 이 경우 "Ape Staking by POL"입니다.  
- **`description`**: NFT에 대한 간단한 설명. 여기서는 사용자가 Ape NFT를 스테이킹하는 방법을 성공적으로 배운 것을 축하합니다.  
- **`image`**: NFT의 시각적 표현을 IPFS에 저장한 CID입니다.  

### **메타데이터의 주요 기능**  

1. **분산형**: IPFS에 저장되어 메타데이터는 변조에 강하고 장기적으로 보존됩니다.  
2. **커스터마이징 가능**: 메타데이터는 NFT의 기능과 고유성을 높이기 위해 특성이나 희귀도 수준과 같은 추가 속성을 포함할 수 있습니다.  
3. **접근 가능**: IPFS CID를 사용하여 누구나 NFT의 메타데이터와 이미지를 볼 수 있어 투명성을 보장합니다.  

### 🚀 퀘스트: 나만의 NFT 민팅하기  

이제 이 코스의 마지막 퀘스트입니다. ApeNFT에서 첫 번째 NFT를 민팅해 봅시다. 이전에 `safeMint` 함수에 대해 배웠습니다. 이 메서드는 NFT를 안전하게 생성하는 데 필수적입니다. 이 함수는 NFT가 민팅되어 유효한 주소로 전송되도록 보장합니다. 모든 NFT에는 메타데이터가 필요하며, 이는 **tokenURI**에 저장됩니다. 이 tokenURI는 NFT의 이름, 설명 및 이미지와 같은 정보를 연결합니다.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)  

1. **수신자 주소**: NFT를 민팅할 주소를 선택하세요 (간단하게 본인 지갑 주소를 선택하세요).  
2. **토큰 URI**: 아래의 값을 tokenURI로 사용하세요:  
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

`safeMint` 거래를 확인한 후, 이 거래를 **PoL**에 제출하여 퀘스트 완료를 증명하고 축하 메시지를 전하세요! 🎉

축하합니다! 이제 NFT를 성공적으로 민팅했고, 이 코스의 마지막 퀘스트를 완료했습니다. 여러분의 노력에 대한 보상으로 **POAP**을 민팅하여 ApeChain 생태계에서의 여정을 축하하세요. 여러분의 지식을 자랑스럽게 표시하고 블록체인 혁신의 세계를 계속 탐험하세요!