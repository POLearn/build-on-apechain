### **IPFS和元数据存储**  
NFT的元数据通常存储在**IPFS（InterPlanetary File System）**上，这是一个去中心化的存储解决方案，确保你的NFT数据是不可篡改且可访问的。与依赖于中心化服务器不同，IPFS会为你的数据分配一个唯一的内容标识符（CID），例如：

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`

这个CID指向元数据文件，提供了一种可靠且透明的方式来访问你NFT的数据。

### **一个简单的元数据示例**  
让我们解析一下存储在IPFS上的一个基本元数据文件：

```json
{
  "name": "Ape Staking by POL",
  "description": "Congratulations! You have successfully learned how to stake an Ape NFT. Thanks for being a part of Ape Ecosystem.",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```

- **`name`**：NFT的名称。在这个例子中，它是 "Ape Staking by POL"。  
- **`description`**：NFT的简要描述。这里，它庆祝用户在Ape NFT质押中的成就。  
- **`image`**：一个CID，指向存储在IPFS上的NFT视觉表示。

### **元数据的关键特点**  
1. **去中心化**：存储在IPFS上，元数据抗篡改且确保持久性。  
2. **可定制**：元数据可以包含额外的属性，例如特征或稀有度级别，以增强NFT的功能性和独特性。  
3. **可访问性**：使用IPFS CID，任何人都可以查看NFT的元数据和图像，确保透明性。

### 🚀 任务：铸造你的NFT

作为本课程的最终任务，让我们为你的ApeNFT铸造第一个NFT。之前，我们探讨了 `safeMint` 函数。这个方法对于安全地创建NFT至关重要。它确保你的NFT被铸造并发送到有效的地址。每个NFT还需要元数据，这些元数据存储在**tokenURI**中。这个tokenURI链接到关于你的NFT的信息，例如它的名称、描述和图像，如上所述。

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)

1. **接收地址**：选择一个地址来铸造NFT（为了简单起见，最好选择你自己的钱包地址）。  
2. **Token URI**：使用这个值作为tokenURI：  
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

确认 `safeMint` 交易后，将交易提交到**PoL**，作为完成此任务的证明，恭喜🎉

你已经成功铸造了一个NFT，并完成了本课程的最终任务。作为奖励，铸造你的**POAP**来庆祝你在ApeChain生态系统中的旅程。骄傲地展示你的知识，继续探索区块链创新的世界！