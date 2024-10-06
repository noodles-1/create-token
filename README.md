# Create a Token

This Solidity program is a token creation program that allows the creation of tokens.

## Description

The program features token minting, which creates and add values to an existing address, and token burning, which deducts a value from a specific address.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., CreateToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT

pragma solidity >= 0.8.7;

contract MyToken {
    string public tokenName = "NOODLE";
    string public tokenAbbrv = "NDL";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;

    function mint(address addr, uint val) external {
        totalSupply += val;
        balances[addr] += val;
    }

    function burn(address addr, uint val) external {
        if (val <= balances[addr]) {
            totalSupply -= val;
            balances[addr] -= val;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" or newer, and then click on the "Compile CreateToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint or burn function. You can also check the values of the public state variables by clicking on them.

## Authors

Adriane Gil Roa  


## License

This project is licensed under the MIT License - see the LICENSE file for details