# 🎓 University Degree Verification NFT

A blockchain-based University Degree Verification System built using **Solidity** and **OpenZeppelin ERC-721** standards. This project allows universities to issue digital degrees as NFTs, enabling graduates to securely claim and verify their academic credentials on-chain.

Additionally, the project includes an implementation of **cross-chain ERC-721 NFT transfers** using **Router Protocol's CrossTalk framework**, allowing NFTs to be transferred across supported blockchain networks.

---

## 📌 Features

- 🎓 Issue university degrees as NFTs
- 🔐 Only the university (contract owner) can authorize degree issuance
- 🪪 Students claim their issued degree independently
- 📄 Metadata stored through ERC721 URI Storage
- ✅ Public verification of issued degrees
- 🌉 Cross-chain NFT transfer support using Router Protocol
- 🔒 Ownership and access control

---

## 🛠 Tech Stack

- Solidity ^0.8.x
- OpenZeppelin Contracts
- ERC-721
- ERC721URIStorage
- Router Protocol CrossTalk
- Ethereum Compatible Networks

---

## 📂 Project Structure

```
contracts/
│
├── UniversityDegree.sol
├── XERC721.sol
└── OpenZeppelin Libraries
```

---

## 📜 Smart Contracts

### 1. UniversityDegree

Main NFT contract responsible for issuing and claiming university degree NFTs.

### Functions

#### issueDegree(address student)

- Can only be called by the contract owner.
- Grants permission for a student to claim a degree.

#### claimDegree(string tokenURI)

- Called by the student.
- Mints an NFT containing the supplied metadata.
- Stores the degree information.

#### checkDegreeOfPerson(address student)

Returns the stored degree metadata URI for a student.

---

### 2. XERC721

An ERC-721 implementation supporting cross-chain NFT transfers through Router Protocol.

### Functions

- transferCrossChain()
- setContractOnChain()
- handleRequestFromSource()
- handleCrossTalkAck()

---

## 🔄 Workflow

### University Degree Flow

```
University
     │
Issue Degree
     │
Student Eligible
     │
Claim Degree
     │
NFT Minted
     │
Metadata Stored
     │
Degree Verification
```

---

### Cross-Chain NFT Flow

```
Source Chain
     │
Transfer Request
     │
Router Protocol Gateway
     │
Destination Chain
     │
Mint NFT
```

---

## 📖 Example Usage

### University issues a degree

```solidity
issueDegree(studentAddress);
```

### Student claims degree

```solidity
claimDegree("ipfs://Qm...metadata.json");
```

### Verify degree

```solidity
checkDegreeOfPerson(studentAddress);
```

---

## 🔐 Access Control

| Function | Access |
|----------|--------|
| issueDegree | Owner Only |
| claimDegree | Eligible Student |
| checkDegreeOfPerson | Public |
| transferCrossChain | NFT Owner |

---

## 🌐 Cross-Chain Support

The project integrates with **Router Protocol CrossTalk** to enable secure NFT transfers between supported EVM-compatible chains.

Cross-chain features include:

- Destination contract mapping
- Cross-chain payload encoding
- Gateway verification
- NFT minting on destination chain

---

## 🔒 Security

- Owner-only degree issuance
- Students can only claim issued degrees
- Duplicate claims prevented
- Gateway validation for cross-chain transfers
- Source contract verification before minting

---

## 📈 Future Enhancements

- Degree revocation
- Multi-university support
- Soulbound (non-transferable) degree NFTs
- QR code verification portal
- Web3 frontend integration
- Employer verification dashboard
- Batch degree issuance
- Role-based access control

---

## 📜 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

Developed as a blockchain-based decentralized application demonstrating secure NFT-powered academic credential management and cross-chain interoperability using Solidity, OpenZeppelin, and Router Protocol.
