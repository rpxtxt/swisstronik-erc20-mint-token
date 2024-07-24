# Swisstronik ERC20 Mint Token

This straightforward Hardhat project is designed to guide you in creating a basic smart contract for ERC20 token minting. Dive into deploying your contract and interact with it using scripts & SwisstronikJS 🚀

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Node.js and npm are installed
- Hardhat is installed globally or locally in your project
- You have a valid Ethereum private key

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/rpxtxt/swisstronik-erc20-mint-token.git
    cd swisstronik-erc20-mint-token
    ```

2. Install the dependencies:

    ```bash
    npm install
    ```

## Configuration

1. Rename `.env.example` to `.env`:

    ```bash
    mv .env.example .env
    ```

2. Open `.env` and update the following variables with your own:

    ```dotenv
    PRIVATE_KEY=your-32-byte-private-key
    INFURA_PROJECT_ID=your-infura-project-id
    ```

3. Update the Hardhat configuration file (`hardhat.config.js` or `hardhat.config.ts`) with your network details:

    ```javascript
    module.exports = {
      solidity: "0.8.4",
      networks: {
        swisstronik: {
          url: `https://your-network-url`,
          accounts: [`0x${process.env.PRIVATE_KEY}`]
        }
      }
    };
    ```

## Compile Contracts

To compile the smart contracts, run:

    ```bash
    npx hardhat compile
    ```

## Deploy Contracts

To deploy the smart contracts, run:

    ```bash
    npx hardhat run scripts/deploy.js --network swisstronik
    ```

Replace `swisstronik` with your network name if different.

## Interacting with the Contract

You can interact with your deployed contract using SwisstronikJS and the provided scripts.

1. To mint tokens:

    ```bash
    node scripts/mintTokens.js "recipient-address" "amount"
    ```

2. To check the balance of an address:

    ```bash
    node scripts/checkBalance.js "address"
    ```

## Verify Contracts

To verify the deployed contracts, you can use the Hardhat Etherscan plugin (if supported by your network):

1. Install the plugin:

    ```bash
    npm install --save-dev @nomiclabs/hardhat-etherscan
    ```

2. Update the Hardhat configuration file with your Etherscan API key:

    ```javascript
    require("@nomiclabs/hardhat-etherscan");

    module.exports = {
      solidity: "0.8.4",
      networks: {
        swisstronik: {
          url: `https://your-network-url`,
