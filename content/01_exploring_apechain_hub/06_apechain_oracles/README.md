# O que é um Oracle

Antes de explorar os Price Oracles para a APEChain, vamos rapidamente entender o que é um oracle. No mundo dos contratos inteligentes, um oracle é um serviço que fornece dados do mundo real para blockchains. Como as blockchains não podem acessar informações externas diretamente, os oracles atuam como pontes, trazendo dados off-chain—como preços, clima ou placares esportivos—para a blockchain.

Para a APEChain, o serviço de oracle é fornecido pela Pyth Network, que entrega dados de mercado em tempo real e de alta qualidade. A Pyth agrega dados de fontes confiáveis, como exchanges e market makers, garantindo precisão e minimizando os riscos de manipulação, para que a APEChain possa confiar em informações confiáveis e atualizadas para seus contratos inteligentes.

## ApeChain Oracle

Vamos começar carregando um contrato na ApeChain mainnet Oracle. Especificamente, vamos usar o contrato no endereço `0x2880aB155794e7179c9eE2e38200202908C17B43`, que faz parte da configuração do ApeChain Oracle.

Você também pode conferir a [documentação completa aqui](https://docs.apechain.com/oracles) para um entendimento mais profundo sobre como os oracles funcionam e como você pode integrá-los em seus projetos.

Vamos carregar isso no seu IDE desejado.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

O acesso a dados de preço em tempo real é crucial ao construir aplicativos descentralizados (dApps). O método `getPriceNoOlderThan` permite recuperar o objeto de preço mais recente para um ID específico de feed de preço, garantindo que os dados de preço estejam atualizados dentro do intervalo de tempo que você especificar.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

Quando você chama o método `getPriceNoOlderThan`, você fornecerá dois argumentos principais: o **ID do feed de preço** e um valor de **idade**. O **ID** especifica qual feed de preço você deseja acessar, enquanto a **idade** define quão recente os dados podem ser. Isso é útil quando você precisa de um preço que foi atualizado em um momento específico ou para dados históricos de preços.

Você pode encontrar os IDs dos feeds de preço na [página de Price Feed da Pyth Network](https://www.pyth.network/developers/price-feed-ids). Por exemplo, um dos IDs de feed de preço disponíveis é para **ApeCoin/USD**, que é o ID que vamos usar em nosso exemplo.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

O método `getPriceNoOlderThan` retorna um **objeto de preço** que contém os seguintes campos principais:

- **price**: O preço mais recente do ativo no feed de preço.
- **conf**: O nível de confiança do preço, indicando a confiabilidade do feed de preço.
- **expo**: O expoente usado para escalonar o preço.
- **publishTime**: O timestamp indicando quando o feed de preço foi atualizado pela última vez.

Aqui está um exemplo de um objeto de preço que você pode receber:

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 Quest: Chamada

Para esta última seção do POAP, vamos chamar o método `getPriceNoOlderThan` para recuperar os dados de preço para **Ape/USD** usando o **ID de Feed de Preço** especificado e o **timestamp**.

Aqui está o que usaremos:

- **ID de Feed de Preço**: `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` (para Ape/USD)
- **Timestamp**: `1736651044`

Agora, vamos ver como chamar este método e obter o resultado! Podemos ver um valor de `99675229`, que na época era **0,99 USD**. Para esta submissão, vamos enviar o JSON completo.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)