# MyToken

MyToken is a simple smart contract for creating, minting, and burning a custom ERC-20 like token on the Ethereum blockchain. This contract allows for managing the total supply of the token and provides basic functionalities to mint and burn tokens.

## Features

1. **Public Variables**: The contract has public variables to store the token details such as Token Name, Token Abbreviation, and Total Supply.
2. **Address Balances Mapping**: It maintains a mapping of addresses to their respective token balances.
3. **Mint Function**: Allows creating new tokens and adding them to a specified address.
4. **Burn Function**: Allows destroying tokens from a specified address, with checks to ensure sufficient balance.

## Contract Details

### Public Variables

- `name`: The name of the token.
- `symbol`: The abbreviation of the token.
- `totalSupply`: The total supply of the token.

### Mapping

- `balances`: A mapping that keeps track of each address's token balance.

### Constructor

The constructor initializes the token with a name, symbol, and total supply. The total supply is assigned to the contract deployer's address.

```solidity
constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
    name = _name;
    symbol = _symbol;
    totalSupply = _totalSupply;
    balances[msg.sender] = _totalSupply;
}
```

### Mint Function

The mint function increases the total supply of the token and credits the specified address with the minted tokens.

```solidity
function mint(address _recipient, uint256 _value) public {
    totalSupply += _value;
    balances[_recipient] += _value;
}
```

### Burn Function

The burn function decreases the total supply of the token and debits the specified address, provided the address has sufficient balance.

```solidity
function burn(address _owner, uint256 _value) public {
    require(balances[_owner] >= _value, "Insufficient balance");
    totalSupply -= _value;
    balances[_owner] -= _value;
}
```

## Usage

### Deploying the Contract

To deploy the contract, you need to provide the token name, symbol, and initial total supply.

```solidity
MyToken myToken = new MyToken("Token Name", "TKN", 1000000);
```

### Minting Tokens

To mint new tokens, call the `mint` function with the recipient address and the amount of tokens to mint.

```solidity
myToken.mint(recipientAddress, 1000);
```

### Burning Tokens

To burn tokens, call the `burn` function with the owner's address and the amount of tokens to burn.

```solidity
myToken.burn(ownerAddress, 500);
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to contribute and enhance the functionality of MyToken. If you encounter any issues or have suggestions, please open an issue or submit a pull request.
