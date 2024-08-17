# CustomERC20 Token Contract

## Overview

This repository contains the source code for a custom ERC20 token implemented in Solidity. The token is named **"Jogi"** with the symbol **"Jg"** and uses the OpenZeppelin ERC20 standard library. The contract includes additional features such as owner-restricted minting, token burning, and an explicit transfer function. 

## Features

- **Token Name:** Jogi
- **Token Symbol:** Jg
- **Decimals:** 3 (customized from the standard 18)
- **Initial Supply:** 100000 Jg (allocated to the contract owner)

### Core Functionalities:

1. **Minting (Owner Only):**
   - The contract owner can mint new tokens to any specified address.

2. **Burning:**
   - Any token holder can burn (destroy) tokens.

3. **Explicit Transfer:**
   - Allows token holders to transfer tokens to a specified address explicitly through a dedicated function.

## Contract Details

### Contract Structure:

- **contractOwner:** An address that stores the owner of the contract.
  
- **onlyOwner modifier:** Restricts certain functions, such as minting, to the contract owner.

### Functions:

1. **constructor():**
   - Initializes the contract, setting the token name, symbol, and allocating the initial supply of tokens to the contract owner.

2. **decimals():**
   - Returns the number of decimal places for the token, which is overridden to be 3.

3. **mint(address recipient_owner, uint256 amount):**
   - Allows the contract owner to mint new tokens to a specified address.

4. **burn(uint256 amount):**
   - Allows any token holder to burn their own tokens.

5. **transferTokens(address recipient, uint256 amount):**
   - Allows any token holder to transfer tokens to another address explicitly.

## Getting Started

### Prerequisites

- **Remix IDE**: Recommended for deploying and interacting with the contract.
  
### Deployment

1. **Open Remix IDE**:
   - Visit [Remix IDE](https://remix.ethereum.org/).

2. **Create a New File**:
   - Create a new Solidity file (e.g., `CustomERC20.sol`) and paste the contract code into it.

3. **Compile the Contract**:
   - Navigate to the "Solidity Compiler" tab and compile the contract using the Solidity version `^0.8.0`.

4. **Deploy the Contract**:
   - Go to the "Deploy & Run Transactions" tab.
   - Deploy the contract. The contract's owner will be the address that deploys it.

## Execution

### Interacting with the Contract in Remix

After deploying the contract, you can execute its functions directly from the Remix IDE. Below are instructions on how to use the key functions:

1. **Minting Tokens (Owner Only)**:
   - In the "Deployed Contracts" section in Remix, expand your contract's interface.
   - Locate the `mint` function.
   - Enter the recipient's address and the amount of tokens to mint (remember the token has 3 decimals, so to mint 1 Jg, input `1000`).
   - Click the `transact` button. If you're the contract owner, the tokens will be minted to the specified address.

2. **Burning Tokens**:
   - Find the `burn` function in the contract interface.
   - Enter the amount of tokens you want to burn (e.g., `1000` to burn 1 Jg).
   - Click `transact` to burn the specified amount of tokens from your balance.

3. **Transferring Tokens**:
   - Locate the `transferTokens` function.
   - Enter the recipient's address and the amount of tokens to transfer.
   - Click `transact` to execute the transfer.

4. **Check Balances**:
   - Use the `balanceOf` function to check the token balance of any address. 
   - Enter the address you want to check and click `call` to view the balance.

### Additional Notes:

- **Gas Fees:** All transactions on the Ethereum network require gas. Ensure you have enough ETH in your wallet to cover these costs.
- **Decimals:** Since the token uses 3 decimals, the amount inputted in functions like `mint`, `burn`, and `transferTokens` should be adjusted accordingly (e.g., to transfer 2 Jg, input `2000`).

## License

This project is licensed under the MIT License.

## Author

- **Lalit Kumar**

## Acknowledgments

- [OpenZeppelin](https://openzeppelin.com/) for providing secure and community-vetted Solidity libraries.
- [Remix IDE](https://remix.ethereum.org/) for being a powerful and accessible tool for smart contract development.
