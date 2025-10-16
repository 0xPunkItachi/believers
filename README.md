# believers

# 🏆 Milestone NFT Reward System (Flow Blockchain)

A decentralized smart contract that issues **non-transferable (soulbound) NFTs** as rewards for achieving milestones.  
Users can claim NFTs for completing specific milestones, which serve as permanent attestations of achievement.

> 🌐 **Deployed on Flow Blockchain (Testnet)**  
> **Contract Address:** `0xC04F60b8316dCa3884c744ECE85D9e9E7a4986Cf`

---

## 🧩 Overview

The **Milestone NFT Reward Contract** allows creators to define milestones and issue **achievement NFTs** to participants.  
Each NFT is **soulbound**, meaning it cannot be transferred or sold — perfect for recognizing accomplishments or badges.

Key characteristics:
- Single active milestone at a time.
- Users claim NFT rewards for completing milestones.
- Off-chain metadata can be linked to milestones via IPFS or other decentralized storage.
- Fully self-contained **Solidity contract**: no imports, no constructors, no input parameters in external functions.

---

## ✨ Key Features

✅ **Milestone-Based Rewards**  
Owner creates milestone rounds; participants earn NFT rewards for achieving them.

✅ **Soulbound NFTs**  
Issued NFTs are non-transferable and permanently associated with the recipient’s address.

✅ **On-Chain Claim Tracking**  
Each milestone tracks which addresses have claimed their rewards.

✅ **Metadata Support**  
Attach off-chain metadata (IPFS CID) to milestones for additional information.

✅ **Simple & Transparent**  
All actions are logged with events: creation, claim, metadata set, and NFT issuance.

---

## 🛠️ Technical Specifications

| Parameter | Description |
|-----------|-------------|
| **Blockchain** | Flow Blockchain (Testnet) |
| **Contract Address** | `0xC04F60b8316dCa3884c744ECE85D9e9E7a4986Cf` |
| **NFT Type** | Soulbound (non-transferable) |
| **Milestone Duration** | 7 days per milestone |
| **Claim Eligibility** | Off-chain verification recommended (not enforced on-chain) |
| **Ownership** | Owner manages milestones and metadata |
| **Security Level** | Educational / Testnet only |

---

## ⚙️ Smart Contract Functions

### 🏁 Initialization
| Function | Description |
|-----------|-------------|
| `initialize()` | Sets the contract owner. Must be called once after deployment. |

---

### 🏆 Milestone Management
| Function | Description |
|-----------|-------------|
| `createMilestone()` | Opens a new milestone round (single active milestone at a time). |
| `setMilestoneMetadataWithCalldata()` | Sets off-chain metadata (IPFS CID) for the active milestone via calldata bytes. |

---

### 🗳️ Reward Claiming
| Function | Description |
|-----------|-------------|
| `claimReward()` | Claim NFT reward for the active milestone (only once per milestone). |

---

### 🖼️ NFT Views
| Function | Description |
|-----------|-------------|
| `ownerOf(uint256 tokenId)` | Returns the owner of a token. |
| `balanceOf(address account)` | Returns the number of NFTs owned by an address. |
| `tokenURI(uint256 tokenId)` | Returns the metadata URI of a token. |
| `tokensOfOwner(address account)` | Returns all token IDs owned by an address. |
| `totalSupply()` | Returns the total number of NFTs minted. |

---

### ⚠️ Emergency & Utility
| Function | Description |
|-----------|-------------|
| `burnToken()` | Owner-only function to burn the last minted token. |
| `emergencyWithdrawAll()` | Owner-only function to withdraw all ETH from the contract. |

---

## 🧠 How It Works

1. **Initialize Contract**
   ```solidity
   initialize()
