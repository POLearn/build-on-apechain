# ¿Qué es un Oracle?

Antes de explorar los Price Oracles para APEChain, primero cubramos rápidamente qué es un oracle. En el mundo de los contratos inteligentes, un oracle es un servicio que proporciona datos del mundo real a las blockchains. Dado que las blockchains no pueden acceder a información externa directamente, los oracles actúan como puentes, llevando datos fuera de la cadena, como precios, clima o resultados deportivos, hacia la blockchain.

Para APEChain, el servicio de oracle es proporcionado por Pyth Network, que entrega datos de mercado en tiempo real y de alta calidad. Pyth agrega datos de fuentes confiables como intercambios y formadores de mercado, asegurando precisión y minimizando los riesgos de manipulación, de modo que APEChain pueda confiar en información actualizada y confiable para sus contratos inteligentes.

## ApeChain Oracle

Comenzaremos cargando un contrato en el Oracle de ApeChain en la red principal. Específicamente, utilizaremos el contrato en la dirección `0x2880aB155794e7179c9eE2e38200202908C17B43`, que forma parte de la configuración del Oracle de ApeChain.

También puedes consultar la [documentación completa aquí](https://docs.apechain.com/oracles) para obtener una comprensión más profunda de cómo funcionan los oracles y cómo puedes integrarlos en tus proyectos.

Vamos a cargar esto en tu IDE deseado.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

Acceder a datos de precios en tiempo real es crucial al construir aplicaciones descentralizadas (dApps). El método `getPriceNoOlderThan` te permite recuperar el objeto de precio más reciente para un **Price Feed ID** específico, asegurando que los datos del precio estén actualizados dentro de un plazo que especifiques.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

Cuando llamas al método `getPriceNoOlderThan`, proporcionarás dos argumentos clave: el **Price Feed ID** y un valor de **edad**. El **ID** especifica qué feed de precios deseas acceder, mientras que la **edad** define cuán recientes pueden ser los datos. Esto es útil cuando necesitas un precio que fue actualizado en un punto específico en el tiempo o para datos históricos de precios.

Puedes encontrar los **Price Feed IDs** en la [Pyth Network Price Feed page](https://www.pyth.network/developers/price-feed-ids). Por ejemplo, uno de los Price Feed IDs disponibles es para **ApeCoin/USD**, que es el ID que usaremos en este ejemplo.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

El método `getPriceNoOlderThan` devuelve un **objeto de precio** que contiene los siguientes campos clave:

- **price**: El precio más reciente del activo desde el feed de precios.
- **conf**: El nivel de confianza del precio, que indica qué tan confiable es el feed de precios.
- **expo**: El exponente utilizado para escalar el precio.
- **publishTime**: La marca de tiempo que indica cuándo se actualizó por última vez el feed de precios.

Aquí tienes un ejemplo de un objeto de precio que podrías recibir:

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 Quest: Llamada al Método Oracle

En esta última sección del POAP, llamaremos al método `getPriceNoOlderThan` para obtener los datos de precio de **Ape/USD** usando el **Price Feed ID** y el **timestamp** especificados.

Aquí están los datos que usaremos:

- **Price Feed ID**: `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` (para Ape/USD)
- **Timestamp**: `1736651044`

Ahora, veamos cómo llamar a este método y obtener el resultado. Podemos ver un valor de `99675229`, que en ese momento era **0.99 USD**. Para esta presentación, vamos a enviar el JSON completo.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)
