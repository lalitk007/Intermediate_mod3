# Intermediate_mod3
# CustomERC20 Token

## Description

This repository contains a custom ERC20 token contract written in Solidity. The token is named "Jogi" with the symbol "Jg" and uses the OpenZeppelin ERC20 implementation as a base. This contract includes functionality for minting, burning, and explicitly transferring tokens, with additional controls for the contract owner.

## Features

- **Owner-Restricted Minting:** The contract owner can mint new tokens to any address.
- **Burning:** Any token holder can burn their own tokens.
- **Explicit Transfer:** Tokens can be transferred explicitly to a specific address.
- **Custom Decimals:** The token uses 3 decimal places instead of the standard 18.

## Contract Details

- **Name:** Jogi
- **Symbol:** Jg
- **Decimals:** 3

### Contract Functions

- **constructor()**
  - Sets the token name, symbol, and assigns the initial supply to the contract owner.

- **decimals()** (override)
  - Returns 3 as the number of decimal places for the token.

- **mint(address recipient_owner, uint256 amount)**
  - Mints new tokens to the specified address. Only the contract owner can call this function.

- **burn(uint256 amount)**
  - Allows any token holder to burn a specified amount of their tokens.

- **transferTokens(address recipient, uint256 amount)**
  - Explicitly transfers tokens from the caller to a specified recipient address.


### Interacting with the Contract

- **Mint Tokens:** As the owner, call the `mint` function with the recipient's address and the amount to mint.
- **Burn Tokens:** Any user can call the `burn` function to destroy a portion of their tokens.
- **Transfer Tokens:** Use the `transferTokens` function to send tokens to another address.
