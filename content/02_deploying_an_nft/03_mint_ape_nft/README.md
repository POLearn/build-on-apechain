### **IPFS and Metadata Storage**  
NFT metadata is typically stored on **IPFS (InterPlanetary File System)**, a decentralized storage solution that ensures your NFT data is immutable and accessible. Instead of relying on centralized servers, IPFS assigns a unique content identifier (CID) to your data, like this:  

`ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R`  

This CID points to the metadata file, providing a reliable and transparent way to access your NFT’s data.  

### **A Simple Metadata Example**  
Let’s break down a basic metadata file stored on IPFS:  

```json
{
  "name": "Ape Staking by POL",
  "description": "Congratulations! You have successfully learned how to stake an Ape NFT. Thanks for being a part of Ape Ecosystem.",
  "image": "ipfs://QmaFtQ4LTHcCb1BhPRTrKe1gVnsK9tZiXrLnzUwxB6Piag"
}
```  

- **`name`**: The title of the NFT. In this case, it’s "Ape Staking by POL."  
- **`description`**: A brief overview of the NFT. Here, it celebrates the user’s achievement in staking an Ape NFT.  
- **`image`**: A CID pointing to the visual representation of the NFT, stored on IPFS.  

### **Key Features of Metadata**  
1. **Decentralized**: Stored on IPFS, metadata is resistant to tampering and ensures longevity.  
2. **Customizable**: Metadata can include additional attributes, such as traits or rarity levels, to enhance the NFT’s functionality and uniqueness.  
3. **Accessible**: Using the IPFS CID, anyone can view the NFT’s metadata and image, ensuring transparency.  


### 🚀 Quest: Mint Your NFT

For the final quest of the this course, let's mint the first NFT for your ApeNFT. Earlier, we explored the `safeMint` function. This method is essential for securely creating NFTs. It ensures that your NFT is minted and sent to a valid address. Every NFT also needs metadata, which is stored in a **tokenURI**. This tokenURI links to information about your NFT, such as its name, description, and image described above.

![](https://raw.githubusercontent.com/POLearn/build-on-apechain/refs/heads/master/content/assets/images/nft_mint.png)  

1. **Recipient Address**: Choose the address to mint to (preferably your own wallet address for simplicity).  
2. **Token URI**: Use this value for the tokenURI:  
   ```
   ipfs://QmbS1hY1v158TXgEPAsxYwUe7BXFTZQXwAQA4BdJiStW9R
   ```

After confirming the `safeMint` transaction, submit the transaction to **PoL** as proof of completing this quest and Congratulations 🎉

You’ve successfully minted an NFT and completed the final quest of this course. As a reward for your efforts, mint your **POAP** to celebrate your journey through the ApeChain ecosystem. Wear your knowledge proudly and continue exploring the world of blockchain innovation!