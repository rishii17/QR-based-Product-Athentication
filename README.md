# Product Authentication using QR Codes & Blockchain

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Hardhat](https://img.shields.io/badge/Hardhat-20232A?style=for-the-badge&logo=hardhat&logoColor=white)](https://hardhat.org/)
[![Solidity](https://img.shields.io/badge/Solidity-e6e6e6?style=for-the-badge&logo=solidity&logoColor=black)](https://soliditylang.org/)

A decentralized application (dApp) to combat product counterfeiting. This system allows manufacturers to register their products on the Ethereum blockchain, generating a unique QR code for each item. Consumers can then scan this QR code to instantly verify the authenticity of the product.


---

## 📖 Table of Contents

-   [The Problem](#-the-problem)
-   [How It Works](#-how-it-works)
-   [✨ Features](#-features)
-   [🛠️ Tech Stack](#-tech-stack)
-   [📂 File Structure](#-file-structure)
-   [🚀 Getting Started](#-getting-started)
    -   [Prerequisites](#prerequisites)
    -   [Installation & Setup](#installation--setup)
-   [📜 Usage](#-usage)
-   [🤝 Contributing](#-contributing)
-   [📄 License](#-license)

---

## ❓ The Problem

Counterfeit goods cause significant financial losses for businesses and can pose serious health and safety risks to consumers. Traditional authentication methods are often easy to replicate. This project leverages the **immutability** and **transparency** of blockchain technology to provide a secure and reliable verification system that is difficult to forge.

## ⚙️ How It Works

The workflow is designed to be simple and intuitive for both manufacturers and consumers:

1.  **Product Registration (Manufacturer):**
    * A manufacturer connects their MetaMask wallet to the dApp.
    * They fill out a form with product details (e.g., name, model, manufacturing date).
    * Upon submission, a transaction is sent to the smart contract, which records the product and assigns it a unique serial number.
    * The dApp then generates a unique QR code that embeds this serial number and the contract address. This QR code is intended to be affixed to the physical product.

2.  **Product Verification (Consumer):**
    * A consumer scans the QR code on the product using their smartphone.
    * The QR code directs them to the React verification page, passing the serial number as a URL parameter.
    * The page automatically extracts the serial number and queries the smart contract on the blockchain.
    * The dApp displays the product's details if it's genuine or shows a clear warning if the serial number is invalid or has been previously marked as counterfeit.

## ✨ Features

-   **Decentralized & Secure:** All product data is stored on the Ethereum blockchain, making it tamper-proof.
-   **Easy Product Registration:** A simple web interface for manufacturers to add new products with a single transaction.
-   **Instant Verification:** Consumers get immediate, on-the-spot feedback on product authenticity.
-   **QR Code Generation:** Automatically creates a unique QR code for each registered product.
-   **MetaMask Integration:** Seamless and secure wallet connection for all blockchain interactions.
-   **Event-Driven Architecture:** The smart contract emits events for product registration, which can be used to build a more robust off-chain indexer or activity feed.

## 🛠️ Tech Stack

This project is built with a modern Web3 technology stack:

-   **Blockchain:**
    -   [**Hardhat**](https://hardhat.org/): An Ethereum development environment for compiling, deploying, testing, and debugging smart contracts.
    -   [**Solidity**](https://soliditylang.org/): The programming language for writing the smart contracts.
    -   [**Ethers.js**](https://docs.ethers.io/): A complete and compact library for interacting with the Ethereum blockchain and its ecosystem.
-   **Frontend:**
    -   [**React**](https://reactjs.org/): A JavaScript library for building dynamic and responsive user interfaces.
    -   [**qrcode.react**](https://www.npmjs.com/package/qrcode.react): A React component to generate QR codes in the browser.
    -   [**Tailwind CSS**](https://tailwindcss.com/): A utility-first CSS framework for rapid UI development.
-   **Wallet:**
    -   [**MetaMask**](https://metamask.io/): A crypto wallet that serves as a gateway to blockchain applications.

## 📂 File Structure

Here is a high-level overview of the key directories and files in this project:
product-auth-dapp/
├── contracts/
│   └── ProductAuth.sol       # The main Solidity smart contract
├── hardhat.config.js         # Hardhat configuration file (networks, compilers)
├── scripts/
│   └── deploy.js             # Script to deploy the smart contract
├── test/
│   └── test.js               # Tests for the smart contract (using Chai & Mocha)
├── src/                      # React frontend source code
│   ├── components/           # Reusable React components
│   │   ├── ManufacturerDashboard.js
│   │   └── Verifier.js
│   ├── App.js                # Main application component with routing
│   └── index.js              # Entry point for the React app
├── .env.example              # Example environment variables file
└── package.json              # Project dependencies and scripts



## 🚀 Getting Started

Follow these instructions to get a local copy up and running for development and testing.

### Prerequisites

Ensure you have the following installed on your system:

-   [Node.js](https://nodejs.org/) (v18 or later recommended)
-   [NPM](https://www.npmjs.com/) or [Yarn](https://yarnpkg.com/)
-   [MetaMask Browser Extension](https://metamask.io/download/)

### Installation & Setup

**Step 1: Clone the repository**

```sh
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

```

For local development, Hardhat provides an in-memory blockchain network that simulates a live network.
```
npx hardhat node
```
```
npx hardhat run scripts/deploy.js --network localhost
```
```
// Example: src/constants.js
export const contractAddress = "YOUR_DEPLOYED_CONTRACT_ADDRESS";
export const contractABI = [ /* ... your contract's ABI ... */ ];
```



