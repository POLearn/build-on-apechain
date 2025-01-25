# Oracle이란 무엇인가요

APEChain의 Price Oracle을 살펴보기 전에, Oracle이 무엇인지 간단히 설명하겠습니다. 스마트 계약의 세계에서 Oracle은 블록체인에 실시간 데이터를 제공하는 서비스입니다. 블록체인이 외부 정보를 직접 접근할 수 없기 때문에, Oracle은 오프체인 데이터를 블록체인으로 가져오는 다리 역할을 합니다. 예를 들어 가격, 날씨, 스포츠 점수와 같은 데이터를 블록체인에 전달합니다.

APEChain에서는 Pyth Network가 Oracle 서비스를 제공하며, 실시간 고품질의 시장 데이터를 전달합니다. Pyth는 거래소 및 시장 조성자와 같은 신뢰할 수 있는 출처에서 데이터를 집계하여 정확성을 보장하고 조작 위험을 최소화하며, APEChain은 최신의 신뢰할 수 있는 정보를 스마트 계약에 활용할 수 있습니다.

## ApeChain Oracle

우리는 ApeChain 메인넷 Oracle에 계약을 로드하는 것으로 시작합니다. 구체적으로 `0x2880aB155794e7179c9eE2e38200202908C17B43` 주소에 있는 계약을 사용할 것입니다. 이 계약은 ApeChain Oracle 설정의 일부입니다.

Oracle이 어떻게 작동하는지, 그리고 이를 프로젝트에 어떻게 통합할 수 있는지에 대해 더 깊이 이해하고 싶다면 [전체 문서](https://docs.apechain.com/oracles)를 참조하십시오.

원하는 IDE에 이 계약을 로드해 봅시다.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

탈중앙화 애플리케이션(dApp)을 구축할 때 실시간 가격 데이터에 접근하는 것은 매우 중요합니다. `getPriceNoOlderThan` 메서드는 특정 가격 피드 ID에 대한 가장 최근의 가격 객체를 가져올 수 있게 해주며, 지정한 시간 내에 가격 데이터가 최신임을 보장합니다.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

`getPriceNoOlderThan` 메서드를 호출할 때, 두 가지 주요 인수를 제공합니다: **가격 피드 ID**와 **연령** 값입니다. **ID**는 접근하려는 가격 피드를 지정하고, **연령**은 데이터가 얼마나 최근이어야 하는지 정의합니다. 이는 특정 시점에 업데이트된 가격 또는 역사적 가격 데이터를 필요로 할 때 유용합니다.

가격 피드 ID는 [Pyth Network Price Feed 페이지](https://www.pyth.network/developers/price-feed-ids)에서 확인할 수 있습니다. 예를 들어, 사용할 수 있는 가격 피드 ID 중 하나는 **ApeCoin/USD**입니다.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

`getPriceNoOlderThan` 메서드는 다음과 같은 주요 필드를 포함한 **가격 객체**를 반환합니다:

- **price**: 가격 피드에서 가져온 자산의 가장 최근 가격.
- **conf**: 가격의 신뢰도 수준, 가격 피드의 신뢰성을 나타냅니다.
- **expo**: 가격을 스케일링하는 데 사용되는 지수.
- **publishTime**: 가격 피드가 마지막으로 업데이트된 시점을 나타내는 타임스탬프.

다음은 받을 수 있는 가격 객체의 예입니다:

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 퀘스트: 호출하기

POAP의 마지막 부분에서는 `getPriceNoOlderThan` 메서드를 호출하여 **Ape/USD**에 대한 가격 데이터를 **가격 피드 ID**와 **타임스탬프**를 사용해 가져오는 방법을 살펴봅시다.

우리가 사용할 값은 다음과 같습니다:

- **가격 피드 ID**: `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` (Ape/USD용)
- **타임스탬프**: `1736651044`

이제 이 메서드를 호출하여 결과를 얻는 방법을 살펴봅시다! 우리는 `99675229` 값을 볼 수 있으며, 이는 당시 **0.99 USD**였습니다. 이 제출을 위해 전체 JSON을 제출합시다.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)