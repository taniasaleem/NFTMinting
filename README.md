# NFT Minting Smart Contract

The `Minting` contract is an ERC-1155 based smart contract built in Solidity, enabling the creation and management of unique, multi-token assets. This contract supports functionalities like minting new tokens, setting token URIs, and batch minting, all managed by the contract owner.

## Features

- **ERC-1155 Compatibility**: The contract inherits from ERC-1155, a standard for creating semi-fungible tokens.
- **Token Minting**: The owner can mint individual or batches of tokens.
- **Burnable Tokens**: Token holders can burn their tokens if they choose to.
- **URI Management**: The contract owner can set or update the URI for each token type.

## Contract Functions

### `constructor(string memory _name)`

- **Description**: Initializes the contract with a given name that is set as the base URI.
- **Parameters**:
    - `_name` - The initial URI for the tokens.

### `setURI(string memory newuri)`

- **Description**: Allows the contract owner to set a new URI for token metadata.
- **Parameters**:
    - `newuri` - The new URI to be set for the tokens.

### `mint(address account, uint256 id, uint256 amount, bytes memory data, string memory tokenuri)`

- **Description**: Allows the contract owner to mint a specific token type with a designated ID and amount.
- **Parameters**:
    - `account` - The address that will receive the minted tokens.
    - `id` - The unique identifier for the token type.
    - `amount` - The number of tokens to mint.
    - `data` - Additional data to pass to the minting function.
    - `tokenuri` - URI for the minted token.

### `mintBatch(address to, uint256[] memory ids, uint256[] memory amounts, bytes memory data)`

- **Description**: Allows the contract owner to mint multiple types of tokens in a single transaction.
- **Parameters**:
    - `to` - The address that will receive the minted tokens.
    - `ids` - An array of unique identifiers for each token type.
    - `amounts` - An array containing the number of tokens to mint for each token type.
    - `data` - Additional data to pass to the minting function.

## Prerequisites

This contract is written in Solidity version ^0.8.2. Ensure your environment supports this version and you have access to tools like Remix or [Hardhat](https://hardhat.org/) for contract deployment and testing.

## Access Control

The contract uses an `onlyOwner` modifier to restrict minting and URI updates to the contract owner. This ensures only the owner has the ability to create, modify, and manage tokens within the contract.

## Usage

1. **Deploy** the contract with an initial URI.
2. Use the **`mint`** function to create new tokens, setting the token ID, amount, and metadata URI.
3. Use the **`mintBatch`** function to mint multiple tokens at once.
