# Qu'est-ce qu'un Oracle

Avant d'explorer les Oracles de Prix pour APEChain, voyons brièvement ce qu'est un oracle. Dans le monde des contrats intelligents, un oracle est un service qui fournit des données réelles aux blockchains. Étant donné que les blockchains ne peuvent pas accéder directement à des informations externes, les oracles agissent comme des ponts, apportant des données off-chain—comme les prix, la météo ou les scores sportifs—sur la blockchain.

Pour APEChain, le service oracle est fourni par Pyth Network, qui délivre des données de marché en temps réel de haute qualité. Pyth agrège des données provenant de sources fiables comme les échanges et les market makers, garantissant l'exactitude et minimisant les risques de manipulation, afin qu'APEChain puisse s'appuyer sur des informations à jour et fiables pour ses contrats intelligents.

## Oracle ApeChain

Nous commencerons par charger un contrat sur l'Oracle du réseau principal d'ApeChain. Plus précisément, nous utiliserons le contrat à l'adresse `0x2880aB155794e7179c9eE2e38200202908C17B43`, qui fait partie de la configuration de l'Oracle d'ApeChain.

Vous pouvez également consulter la [documentation complète ici](https://docs.apechain.com/oracles) pour une compréhension plus approfondie du fonctionnement des oracles et de la façon dont vous pouvez les intégrer dans vos projets.

Chargons cela dans votre IDE préféré.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_load.png)

### `getPriceNoOlderThan`

L'accès aux données de prix en temps réel est crucial lors de la création d'applications décentralisées (dApps). La méthode `getPriceNoOlderThan` vous permet de récupérer l'objet de prix le plus récent pour un identifiant de flux de prix spécifique, en veillant à ce que les données de prix soient à jour dans une période que vous spécifiez.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_method.png)

Lorsque vous appelez la méthode `getPriceNoOlderThan`, vous fournissez deux arguments clés : l'**identifiant du flux de prix** et une valeur d'**âge**. L'**ID** spécifie le flux de prix auquel vous souhaitez accéder, tandis que l'**âge** définit à quel point les données peuvent être récentes. Cela est utile lorsque vous avez besoin d'un prix qui a été mis à jour à un moment spécifique ou pour des données historiques sur les prix.

Vous pouvez trouver les identifiants de flux de prix sur la [page des flux de prix de Pyth Network](https://www.pyth.network/developers/price-feed-ids). Par exemple, l'un des identifiants de flux de prix disponibles est pour **ApeCoin/USD**, qui est l'ID que nous utiliserons pour notre exemple.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/pyth_id.png)

La méthode `getPriceNoOlderThan` renvoie un **objet de prix** contenant les champs clés suivants :

- **price** : Le prix le plus récent de l'actif à partir du flux de prix.
- **conf** : Le niveau de confiance du prix, indiquant la fiabilité du flux de prix.
- **expo** : L'exposant utilisé pour l'échelle du prix.
- **publishTime** : Le timestamp indiquant quand le flux de prix a été mis à jour pour la dernière fois.

Voici un exemple d'objet de prix que vous pourriez recevoir :

```json
{
    price: 123456789n,
    conf: 180726074n,
    expo: -8,
    publishTime: 1721765108n
}
```

### 🚀 Quête : Appel

Pour cette dernière section du POAP, appelons la méthode `getPriceNoOlderThan` pour récupérer les données de prix pour **Ape/USD** en utilisant l'**Identifiant du Flux de Prix** et le **timestamp** spécifiés.

Voici ce que nous allons utiliser :

- **Identifiant du Flux de Prix** : `0x15add95022ae13563a11992e727c91bdb6b55bc183d9d747436c80a483d8c864` (pour Ape/USD)
- **Timestamp** : `1736651044`

Maintenant, voyons comment appeler cette méthode et obtenir le résultat ! Nous pouvons voir une valeur de `99675229`, qui à ce moment-là était **0.99 USD**. Pour cette soumission, soumettons l'ensemble du JSON.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/oracle_result.png)