
# 🖼️ Basic NFT Minter

A simple, self-contained ERC-721-compatible NFT minter written in Solidity. Users can mint NFTs by paying a small fee and supplying metadata (token URI).

---

## 🌐 Deployment Details

- **Network:** Base Sepolia Testnet
- **Contract Name:** `BasicNFTMinter`
- **Contract Address:** [`0xcDE092fC96b84c784028651BF1819F7Dda617c33`](https://sepolia.basescan.org/address/0xcDE092fC96b84c784028651BF1819F7Dda617c33)
- **Deployed By:** `0x[YOUR_DEPLOYER_ADDRESS]`
- **Verification:** ✅ Verified on BaseScan

---

## ⚙️ Features

- Users can mint NFTs with a custom metadata URI
- Each mint requires payment (default: 0.001 ETH)
- Owner can update mint price and withdraw collected ETH
- Tracks total minted, individual balances, and ownership
- Compliant with ERC721 and ERC721Metadata
- Fully self-contained, no OpenZeppelin dependencies
- Ideal for use in Remix or lightweight custom dapps

---



### Query NFTs by Wallet

```solidity
getOwnedTokens("0xYourAddress");
```

---

## 📌 Important Functions

| Function                                      | Description                           |
| --------------------------------------------- | ------------------------------------- |
| `mintNFT(address to, string memory tokenURI)` | Mint a new NFT to `to` address        |
| `setMintPrice(uint256 newPrice)`              | Owner-only: update mint cost          |
| `withdraw()`                                  | Owner-only: withdraw ETH balance      |
| `getOwnedTokens(address)`                     | Get all token IDs owned by an address |
| `getNFTDetails(tokenId)`                      | Returns owner and URI of given token  |
| `getContractStats()`                          | Get mint count, price, and balance    |

---

## 🧾 Example Deployment Script (Hardhat)

```js
const hre = require("hardhat");

async function main() {
  const Contract = await hre.ethers.getContractFactory("BasicNFTMinter");
  const nftMinter = await Contract.deploy();
  await nftMinter.deployed();
  console.log("Deployed to:", nftMinter.address);
}

main().catch((err) => {
  console.error(err);
  process.exit(1);
});
```

---

## 📜 License

MIT

---

## 🤝 Contributing

Feel free to fork this repository, improve the contract, or integrate with your frontend. PRs are welcome.

````

---

## 🧪 Optional: `.gitignore` File

If you're using Hardhat or Node.js, add this:

```gitignore
node_modules/
.env
artifacts/
cache/
````

---

