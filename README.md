# FundMe Smart Contract

## Overview
FundMe is a decentralized crowdfunding smart contract built on Ethereum using Solidity. It allows users to contribute funds to a campaign and enables the contract owner to withdraw funds under certain conditions. The contract ensures transparency and security using best Solidity development practices.

## Features
- Accepts ETH contributions from users
- Tracks individual contributions
- Allows only the contract owner to withdraw funds
- Implements gas-efficient operations
- Uses Chainlink Oracles (if applicable) for price feeds

## Technologies Used
- Solidity
- Hardhat (for development and testing)
- Chainlink (for fetching price feeds)
- React (for frontend integration)

## Installation
### Prerequisites
Ensure you have the following installed:
- Node.js
- Hardhat
- MetaMask (for frontend interaction)

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/GURIROR/fundme-smart-contract.git
   cd fundme-smart-contract
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Compile the contract:
   ```sh
   npx hardhat compile
   ```
4. Deploy to a test network:
   ```sh
   npx hardhat run scripts/deploy.js --network goerli
   ```
5. Run tests:
   ```sh
   npx hardhat test
   ```

## Usage
### Interacting via Hardhat Console
To contribute funds:
```sh
npx hardhat console --network goerli
const contract = await ethers.getContractAt("FundMe", "<DEPLOYED_CONTRACT_ADDRESS>");
await contract.fund({ value: ethers.utils.parseEther("0.1") });
```

To withdraw funds (owner only):
```sh
await contract.withdraw();
```

### Frontend Integration
A React frontend can be used to interact with the smart contract. See the `frontend` directory for more details.

## Security Considerations
- Implemented onlyOwner modifier to restrict access
- Used Chainlink to prevent price manipulation
- Regularly audited and tested for vulnerabilities

## License
This project is licensed under the MIT License.
