# Upgradeable Box Contract

This repository contains two versions of a simple upgradeable smart contract, `BoxV1` and `BoxV2`. The contract allows storing and retrieving a single value, with the ability to upgrade the contract using the UUPS (Universal Upgradeable Proxy Standard) pattern.

The contract is upgradeable, meaning that it can evolve over time without losing its state or breaking the existing deployed instances.

## Features

- **Upgradeable Contract**: Uses UUPS pattern to allow for future upgrades without losing state.
- **Ownable**: Only the contract owner can perform specific actions (like upgrading).
- **Versioning**: Each contract version includes a method to return the current version.

### BoxV1 (Version 1)

- **Storage**: Stores a `uint256` value.
- **Getter**: Allows retrieving the stored value using `getValue()`.
- **Version**: Version 1 of the contract.

### BoxV2 (Version 2)

- **Setter and Getter**: Adds the ability to set the value using `setValue(uint256 newValue)` in addition to getting it.
- **Version**: Version 2 of the contract, which introduces the ability to update the stored value.

## How It Works

1. **Deployment**: The contract is deployed using an upgradeable proxy pattern. This allows for upgrades without losing the stored data (i.e., the value).
2. **Upgrade Process**: The contract uses the `UUPSUpgradeable` pattern for upgrading. Only the owner can authorize an upgrade to a new implementation.
3. **Versioning**: The contract has a `version()` function that returns the current version, allowing you to track upgrades.

## Installation

```bash
git clone https://github.com/mohamed-Decentralized/foundry-uups.git
cd foundry-uups
forge install
forge build
```