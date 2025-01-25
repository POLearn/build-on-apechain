### **IPFS e Armazenamento de Metadados**  
Os metadados de NFT geralmente são armazenados no **IPFS (InterPlanetary File System)**, uma solução de armazenamento descentralizada que garante que os dados do seu NFT sejam imutáveis e acessíveis. Em vez de depender de servidores centralizados, o IPFS atribui um identificador único de conteúdo (CID) aos seus dados, como este:

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`

Este CID aponta para o arquivo de metadados, fornecendo uma maneira confiável e transparente de acessar os dados do seu NFT.

### **Exemplo Simples de Metadados**  
Vamos analisar um arquivo básico de metadados armazenado no IPFS:

```json
{
  "name": "Ape Staking by POL",
  "description": "Parabéns! Você aprendeu com sucesso como fazer o staking de um Ape NFT. Obrigado por fazer parte do Ape Ecosystem.",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```

- **`name`**: O título do NFT. Neste caso, é "Ape Staking by POL."
- **`description`**: Uma visão geral do NFT. Aqui, ele celebra a conquista do usuário em fazer staking de um Ape NFT.
- **`image`**: Um CID apontando para a representação visual do NFT, armazenada no IPFS.

### **Principais Características dos Metadados**  
1. **Descentralizado**: Armazenado no IPFS, os metadados são resistentes a alterações e garantem longevidade.
2. **Personalizável**: Os metadados podem incluir atributos adicionais, como características ou níveis de raridade, para aprimorar a funcionalidade e a exclusividade do NFT.
3. **Acessível**: Usando o CID do IPFS, qualquer pessoa pode visualizar os metadados e a imagem do NFT, garantindo transparência.

### 🚀 Missão: Cunhe Seu NFT

Para a missão final deste curso, vamos cunhar o primeiro NFT para o seu ApeNFT. Mais cedo, exploramos a função `safeMint`. Este método é essencial para criar NFTs de forma segura. Ele garante que seu NFT seja cunhado e enviado para um endereço válido. Todo NFT também precisa de metadados, que são armazenados em um **tokenURI**. Este tokenURI vincula as informações sobre o seu NFT, como seu nome, descrição e imagem descritos acima.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)

1. **Endereço do Destinatário**: Escolha o endereço para o qual o NFT será cunhado (preferencialmente o seu próprio endereço de carteira para simplicidade).
2. **Token URI**: Use este valor para o tokenURI:  
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

Após confirmar a transação `safeMint`, envie a transação para o **PoL** como prova de conclusão desta missão. Parabéns 🎉

Você cunhou com sucesso um NFT e completou a missão final deste curso. Como recompensa pelos seus esforços, cunhe seu **POAP** para celebrar sua jornada pelo ecossistema ApeChain. Exiba seu conhecimento com orgulho e continue explorando o mundo da inovação blockchain!