# Create a Token on Solidity

The MyToken smart contract is simply implemented on EVM using various functions and variablees.

1. Custom Token Details: Sets the token name, abbreviation, and initial supply at the time of deployment.
2. Minting Tokens: Increases the supply by creating new tokens and assigning them to a specific address.
3. Burning Tokens: Decreases the supply by destroying tokens from a specific address, provided the address 
   has a sufficient balance. And in case the token to be burned are more than minted tokens then throw an error.

## Description

This project provides a basic understanding of creating and managing a custom token on the Ethereum Virtual Machine(EVM) using Solidity. 
It serves as an educational source for beginners who are learning about blockchain development, smart contracts, and token creation.

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
In it the Token has been created "Sparsh" and it's abreviation has also been created "SP". Intial value has been set to 0.
2. Mapping variables
```
   // mapping variable here
     mapping(address =>uint256) public balances;
```
The "balances" mapping associates each address (key) with a uint256 value (the balance of tokens for that address). This allows 
the contract to keep track of how many tokens are available on each token address.
3. minting of tokens
```
    // mint function
    function mint(address _to, uint256 _value) public{ //Private to make sure no one mints it
       totalSupply += _value;
       balances[_to] += _value;
    }
```
In it the value of tokenn get's increased;   totalSupply += _value adds the new value to the total supply and balances[_to] += _value 
deals with increase in balance of the tokens.

4. Burning of tokens
``` 
    // burn function
    function burn(address _from, uint256 _value)public { 
       require(balances[_from] >= _value, "Balance isn't sufficient");
       totalSupply -= _value;
       balances[_from] -= _value;
    }
```
require(balances[_from] >= _value, "Balance isn't sufficient") this code snippet deals with the exception that if the number of tokens to be 
burned are more than the current value then an exception error is thrown "Balance isn't sufficient". totalSupply -= _value; balances[_from] -= _value;
These both code snippet deals with the decrease in value of the current "balances" and the update it.



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
