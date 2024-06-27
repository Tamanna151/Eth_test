# My token smart contract
MyToken is a simple ERC-20 like token implemented in Solidity. The contract includes functionalities to mint and burn tokens. It also maintains a mapping of addresses to their respective balances
# Description
MyToken is a custom cryptocurrency token built on the Ethereum blockchain using the Solidity programming language. This smart contract implements basic token functionality similar to the ERC-20 standard. The main goal of this project is to provide a simple and efficient way to manage a digital token, including minting new tokens and burning existing ones. This project is ideal for developers and blockchain enthusiasts who want to understand and experiment with fundamental token operations on the Ethereum network.

### Key Features
- **Token Name:** Tamanna
- **Token Abbreviation:** Singh
- **Total Supply:** Keeps track of the total supply of tokens, which is updated dynamically.
- **Mint Function:** Allows the creation of new tokens, increasing both the total supply and the balance of a specified address.
- **Burn Function:** Enables the destruction of tokens, decreasing both the total supply and the balance of a specified address, with checks to ensure sufficient balance.
- **Balances Mapping:** Maintains a mapping of addresses to their respective token balances, allowing easy tracking and management of token holdings.
- # getting started
- # executing program
- To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "Tamanna";
    string public tokenAbbrv = "Singh";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;


    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
     function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
    

}
# Description of mint function
## Mint Function

### `mint(address _to, uint256 _value)`

The `mint` function is designed to create new tokens and assign them to a specified address. This function is crucial for increasing the total supply of tokens and distributing them to users.

#### Parameters
- **_to**: The address to which the newly minted tokens will be assigned.
- **_value**: The number of tokens to be minted.

#### Functionality
1. **Increase Total Supply**: The function increases the `totalSupply` of the token by the specified `_value`.
2. **Update Balance**: The balance of the `_to` address is increased by the specified `_value`.

The mint function can be used to distribute tokens to multiple addresses as needed.
Proper access control mechanisms should be implemented in a production environment to restrict who can call the mint function


# Author
Tamanna Singh 
tamannasingh151@gmail.com
# Licence
This project is licensed under the MIT License


