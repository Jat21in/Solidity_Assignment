# MyToken Project

A simple token contract implemented in Solidity for creating and managing custom tokens with minting and burning functionalities.

## Description

This project demonstrates a basic implementation of an ERC20-like token on the Ethereum blockchain. The contract allows for the creation (minting) and destruction (burning) of tokens. It includes features to keep track of token balances and total supply, ensuring the integrity and security of token operations.

## Getting Started

### Installing

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/mytoken-project.git
    cd mytoken-project
    ```

2. Install [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/).

3. Install [Truffle](https://www.trufflesuite.com/truffle):
    ```bash
    npm install -g truffle
    ```

4. Install dependencies:
    ```bash
    npm install
    ```

### Executing program

1. Compile the contract:
    ```bash
    truffle compile
    ```

2. Deploy the contract to a local development network:
    ```bash
    truffle develop
    truffle migrate
    ```

3. Interact with the contract using Truffle Console:
    ```bash
    truffle console
    ```

    In the console, you can execute commands to mint and burn tokens:
    ```javascript
    let instance = await MyToken.deployed();
    await instance.mint('0xYourAddress', 100);
    await instance.burn('0xYourAddress', 50);
    ```

## Help

If you encounter common issues:

- Ensure that you have the correct version of Node.js and npm installed.
- Make sure you have a local Ethereum network running (e.g., using `truffle develop` or [Ganache](https://www.trufflesuite.com/ganache)).
- Check your Solidity version compatibility in `truffle-config.js`.

For additional help, you can run:
```bash
truffle help
##Authors
Contributors names and contact info:

By MetaCrafters
-Nivedita
##License
This project is licensed under the MIT License
