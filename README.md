# Raffle Project

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Solidity](https://img.shields.io/badge/solidity-0.8.19-brightgreen)
![Chainlink](https://img.shields.io/badge/chainlink-VRF-orange)

## Overview

This project implements a decentralized raffle system using Solidity, Foundry, and Chainlink VRF (Verifiable Random Function). Users can enter the raffle by paying a fee, and a random winner is selected at the end of each interval using Chainlink VRF, ensuring a fair and tamper-proof selection process.

## Features

- **Decentralized Raffle**: Users enter the raffle by paying a specified entrance fee.
- **Random Winner Selection**: Uses Chainlink VRF for provably fair random winner selection.
- **Interval-Based Draws**: Automatically selects a winner at the end of each interval.
- **Comprehensive Tests and Scripts**: Includes unit tests and deployment scripts for ease of use.


## Getting Started
### Prerequisites
- **Foundry**: Installation Guide
- **Chainlink VRF Subscription**: Set up a Chainlink VRF subscription.
   
### Installation
1. **Clone the repository:**

```
git clone https://github.com/yourusername/raffle-foundry.git
cd raffle-foundry
```
2. **Install dependencies:**

```
forge install
```
3. **Set up environment variables:**

- Create a .env file and add your private key and Sepolia RPC URL.

```
touch .env
```
- env
```
PRIVATE_KEY=your_private_key
SEPOLIA_RPC_URL=your_sepolia_rpc_url
```

### Deployment
1. **Deploy to Sepolia:**
```
forge script script/DeployRaffle.s.sol:DeployRaffle --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast
```
2. **Update Subscription ID:**

After deploying, update the subscription ID in HelperConfig.s.sol with the one generated from your Chainlink VRF subscription.

### Testing
Run the tests using Foundry:
```
forge test -vvvv
```

### Usage
After deployment, users can enter the raffle by sending the required entrance fee. The contract will automatically select a winner after each interval using Chainlink VRF.

## Scripts
- **DeployRaffle.s.sol:** Script for deploying the Raffle contract.
  
- **HelperConfig.s.sol:** Script for configuring contract parameters like entrance fee, interval, VRF Coordinator address, etc.

- **Interactions.s.sol:** Script for adding consumer and interactions.
  
## Chainlink VRF Integration
The project leverages Chainlink VRF to ensure randomness in selecting the raffle winner. This integration provides security and fairness by preventing tampering with the random number generation process.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements
Chainlink for the VRF service.
Foundry for the development toolkit.