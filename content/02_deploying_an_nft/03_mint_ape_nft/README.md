### **IPFS y Almacenamiento de Metadatos**  
Los metadatos de los NFTs se almacenan típicamente en **IPFS (Sistema de Archivos Interplanetarios)**, una solución de almacenamiento descentralizado que garantiza que los datos de tu NFT sean inmutables y accesibles. En lugar de depender de servidores centralizados, IPFS asigna un identificador único de contenido (CID) a tus datos, como este:

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`

Este CID apunta al archivo de metadatos, proporcionando una manera confiable y transparente de acceder a los datos de tu NFT.

### **Un Ejemplo Simple de Metadatos**  
Vamos a desglosar un archivo básico de metadatos almacenado en IPFS:

```json
{
  "name": "Ape Staking by POL",
  "description": "¡Felicidades! Has aprendido con éxito cómo poner en staking un Ape NFT. Gracias por ser parte del Ecosistema Ape.",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```

- **`name`**: El título del NFT. En este caso, es "Ape Staking by POL."
- **`description`**: Un breve resumen del NFT. Aquí, celebra el logro del usuario al poner en staking un Ape NFT.
- **`image`**: Un CID que apunta a la representación visual del NFT, almacenada en IPFS.

### **Características Clave de los Metadatos**  
1. **Descentralizado**: Almacenado en IPFS, los metadatos son resistentes a manipulaciones y aseguran longevidad.
2. **Personalizable**: Los metadatos pueden incluir atributos adicionales, como características o niveles de rareza, para mejorar la funcionalidad y singularidad del NFT.
3. **Accesible**: Usando el CID de IPFS, cualquiera puede ver los metadatos y la imagen del NFT, garantizando transparencia.

### 🚀 Misión: Mint tu NFT

Para la misión final de este curso, vamos a acuñar el primer NFT de tu ApeNFT. Anteriormente, exploramos la función `safeMint`. Este método es esencial para crear NFTs de manera segura. Garantiza que tu NFT sea acuñado y enviado a una dirección válida. Además, cada NFT necesita metadatos, que se almacenan en un **tokenURI**. Este tokenURI enlaza con información sobre tu NFT, como su nombre, descripción e imagen mencionados anteriormente.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)

1. **Dirección del receptor**: Elige la dirección a la que deseas acuñar el NFT (preferentemente tu propia dirección de billetera para mayor simplicidad).
2. **Token URI**: Usa este valor para el tokenURI:  
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

Después de confirmar la transacción `safeMint`, envía la transacción a **PoL** como prueba de que completaste esta misión y ¡Felicidades! 🎉

Has acuñado exitosamente un NFT y completado la misión final de este curso. Como recompensa por tu esfuerzo, acuña tu **POAP** para celebrar tu viaje a través del ecosistema ApeChain. ¡Lleva tu conocimiento con orgullo y continúa explorando el mundo de la innovación blockchain!
