# Create a Token on Solidity

The MyToken smart contract is a simple implementation of an ERC-20 like token in Solidity. 
It allows for the creation and management of a custom token with the following features:

1. Custom Token Details: Set the token name, abbreviation, and initial supply at the time of deployment.
2. Minting Tokens: Increase the total supply by creating new tokens and assigning them to a specific address.
3. Burning Tokens: Decrease the total supply by destroying tokens from a specific address, provided the address 
   has a sufficient balance. And in case the token to be burned are more than mointed tokens then throw an error.

## Description

This project provides a basic understanding of creating and managing a custom token on the Ethereum Virtual Machine(EVM) using Solidity. It serves as an educational source for beginners who are learning about blockchain development, smart contracts, and token creation.

## Getting Started

### Installing

This program runs on EVM along with ".sol" as extension. We can either run it on websites like REmix or even on Visual Studios.

### Executing program

We need a solidity compatible virtual machine in order to run this program.
Create a new file with ".sol" extension

1. Creating variables
```
// public variables here
    string public tokenName = "Sparsh";
    string public tokenAbbrv = "SP";
    uint256 public totalSupply = 0; //Initial token supply
```
2. Mapping variables
```
   // mapping variable here
     mapping(address =>uint256) public balances;
```
3. minting of tokens
```
    // mint function
    function mint(address _to, uint256 _value) public{ //Private to make sure no one mints it
       totalSupply += _value;
       balances[_to] += _value;
    }
```
4. Burning of tokens
``` 
    // burn function
    function burn(address _from, uint256 _value)public { 
       require(balances[_from] >= _value, "Balance isn't sufficient");
       totalSupply -= _value;
       balances[_from] -= _value;
    }
```
Once done implementing it you are required to press "Ctrl + S" or Compile the program.

After compiling, it;s time to deploy, deploy the program and look out for the various functions created in order to make the program feasible.


## Help

You can either use 'if' statement instead of 'require' statement in burning statement.


## Authors

Contributors names and contact info

ex. Sparsh Shandil 
ex. [@Allegiantshark](https://linktr.ee/allegiantshark)


## License

This project is licensed under the Sparsh Shandil License - see the LICENSE.md file for details
