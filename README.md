# KaseiCoin-ERC20
KaseiCoin will be a fungible token that is ERC-20 compliant. Also contains a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin


# KaseiCoin Token Contract

Welcome to the KaseiCoin token contract! This contract demonstrates how to create an ERC20 token using the OpenZeppelin library. The token is named KaseiCoin (KSC) and inherits the standard ERC20 functionalities along with minting capabilities.

## Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.5.17;

// Import the following contracts from the OpenZeppelin library:
// * `ERC20`
// * `ERC20Detailed`
// * `ERC20Mintable`
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Detailed.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Mintable.sol";

// Create a contract called KaseiCoin that inherits from the ERC20, ERC20Detailed, and ERC20Mintable contracts.
contract KaseiCoin is ERC20, ERC20Detailed, ERC20Mintable {
    constructor(
        string memory name,
        string memory symbol,
        uint256 initialSupply // Changed to uint256 for consistency with ERC20 standard
    )
        ERC20Detailed(name, symbol, 18) // Initialize the ERC20Detailed with the provided name, symbol, and decimal places
        public
    {
        // Mint initialSupply amount of tokens to the contract deployer
        _mint(msg.sender, initialSupply * (10 ** uint256(decimals())));
    }
}
# How to Use

To utilize the KaseiCoin token contract, follow these steps:

1. Deploy the `KaseiCoin` contract to the Ethereum blockchain using a Solidity development environment like Remix, Truffle, or Hardhat.

2. Provide the necessary parameters to the constructor:
   - `name`: The name of the token (e.g., "KaseiCoin")
   - `symbol`: The symbol of the token (e.g., "KSC")
   - `initialSupply`: The initial supply of tokens to mint during deployment.

Once deployed, the KaseiCoin token will be accessible on the blockchain, featuring the specified name, symbol, and initial supply.

Feel free to customize and expand upon this contract to suit your particular use case.

## License

This contract is licensed under the MIT License. You have the freedom to employ, modify, and distribute the code based on the license's terms.


