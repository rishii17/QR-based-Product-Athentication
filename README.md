Product Authentication using QR Codes & Blockchain
A decentralized application (dApp) to combat product counterfeiting. This system allows manufacturers to register their products on the Ethereum blockchain, generating a unique QR code for each item. Consumers can then scan this QR code to instantly verify the authenticity of the product.

A placeholder for your application's screenshot or GIF.

📖 Table of Contents
The Problem

How It Works

✨ Features

🛠️ Tech Stack

📂 File Structure

🚀 Getting Started

Prerequisites

Installation & Setup

📜 Usage

🤝 Contributing

📄 License

❓ The Problem
Counterfeit goods cause significant financial losses for businesses and can pose serious health and safety risks to consumers. Traditional authentication methods are often easy to replicate. This project leverages the immutability and transparency of blockchain technology to provide a secure and reliable verification system.

⚙️ How It Works
The workflow is designed to be simple for both manufacturers and consumers:

Product Registration (Manufacturer):

A manufacturer connects their MetaMask wallet to the dApp.

They fill out a form with product details (e.g., name, model, manufacturing date).

Upon submission, a transaction is sent to the smart contract, which records the product and assigns it a unique serial number.

The dApp then generates a unique QR code that embeds this serial number. This QR code is affixed to the physical product.

Product Verification (Consumer):

A consumer scans the QR code on the product using their smartphone.

The QR code directs them to the React verification page.

The page automatically extracts the serial number and queries the smart contract on the blockchain.

The dApp displays the product's details if it's genuine or shows a warning if the serial number is invalid or has been previously marked as counterfeit.

✨ Features
Decentralized & Secure: All product data is stored on the Ethereum blockchain, making it tamper-proof.

Easy Product Registration: A simple web interface for manufacturers to add new products.

Instant Verification: Consumers get immediate feedback on product authenticity.

QR Code Generation: Automatically creates a unique QR code for each registered product.

MetaMask Integration: Seamless and secure wallet connection for blockchain interactions.

🛠️ Tech Stack
Blockchain:

Hardhat: Ethereum development environment for compiling, deploying, and testing smart contracts.

Solidity: Language for writing the smart contracts.

Ethers.js: Library for interacting with the Ethereum blockchain.

Frontend:

React: JavaScript library for building the user interface.

QR Code Generator Library: To generate QR codes in the browser.

Wallet:

MetaMask: A crypto wallet & gateway to blockchain apps.

📂 File Structure
Here is a high-level overview of the key directories and files in this project:

product-auth-dapp/
├── contracts/
│   └── ProductAuth.sol       # The main Solidity smart contract
├── hardhat.config.js         # Hardhat configuration file
├── scripts/
│   └── deploy.js             # Script to deploy the smart contract
├── test/
│   └── test.js               # Tests for the smart contract
├── src/                      # React frontend source code
│   ├── components/           # Reusable React components
│   │   ├── ManufacturerDashboard.js
│   │   └── Verifier.js
│   ├── App.js                # Main application component
│   └── index.js              # Entry point for the React app
└── package.json

🚀 Getting Started
Follow these instructions to get a local copy up and running for development and testing.

Prerequisites
Node.js (v18 or later recommended)

NPM or Yarn

MetaMask Browser Extension

Installation & Setup
Step 1: Clone the repository

git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

Step 2: Install Backend Dependencies

Install the necessary packages for Hardhat.

npm install

Step 3: Set up Environment Variables

Create a .env file in the root directory. This will store your private key for deployment and your RPC URL.

# .env

# Your private key from a test account (e.g., from MetaMask)
# IMPORTANT: DO NOT USE A MAINNET KEY WITH REAL FUNDS
PRIVATE_KEY="YOUR_METAMASK_PRIVATE_KEY"

# An RPC URL (e.g., from Alchemy or Infura for a testnet like Sepolia)
RPC_URL="YOUR_RPC_URL"

Security Note: The .env file is included in .gitignore to prevent you from accidentally committing your private keys.

Step 4: Run a Local Blockchain Node

For local development, Hardhat provides an in-memory blockchain network.

npx hardhat node

This will start a local node and provide you with several test accounts and their private keys. You can use one of these for deployment.

Step 5: Deploy the Smart Contract

In a new terminal window, deploy the ProductAuth.sol contract to your local Hardhat network.

npx hardhat run scripts/deploy.js --network localhost

After deployment, copy the contract address printed in the terminal. You will need it for the frontend.

Step 6: Set up the Frontend

Navigate to the src directory (or wherever your React app is initialized) and install its dependencies. If your package.json for React is in the root, you can skip the cd command.

# If your React app is in a sub-folder like 'client' or 'frontend'
# cd client

npm install

Next, find the configuration file in your React app where you'll store the contract address (e.g., src/config.js or directly in App.js).

// src/config.js or inside App.js
export const contractAddress = "YOUR_DEPLOYED_CONTRACT_ADDRESS";

Step 7: Start the React Application

npm start

Your browser should open to http://localhost:3000, and you can now interact with the dApp. Make sure your MetaMask is connected to the localhost:8545 network.

📜 Usage
Connect Wallet: Click the "Connect Wallet" button to link your MetaMask account.

Manufacturer: Navigate to the "Register Product" section, fill in the details, and submit the transaction. A QR code will be generated upon success.

Consumer: Scan a product's QR code. This will open the verification page (e.g., http://localhost:3000/verify?id=123). The page will automatically check the product's status and display the results.

🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

📄 License
Distributed under the MIT License. See LICENSE for more information.
