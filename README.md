# Hello World

This Solidity program is a simple "Create Token" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to burn the user values and mint the user values . 
## Description

This Solidity contract defines a simple token with public variables for its name, symbol, and total supply. It includes a mapping to keep track of token balances for each address. The contract provides two main functions:
mint: To create and assign new tokens to an address, increasing the total supply.
burn: To destroy tokens from an address, decreasing the total supply and ensuring the address has sufficient tokens before burning.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., mytoken.sol). Copy and paste the following code into the file:

```
//SPDX-License-identifier:MIT
pragma solidity 0.8.18;

/*REQUIREMENTS 
1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)

2. Your contract will have a mapping of addresses to balances (address => uint)

3. You will have a mint function that takes two parameters: an address and a value,
   The function then increases the total supply by that number and increases the balance of the address by that amount.

4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens,
   It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.

5. Lastly, your burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.*/


contract MyToken{

    //Public variable to store token details
    string public tokenName="Necklace";
    string public tokenAbbry="Ncklc";
    uint public totalSupply=0;

    // mapping addresss to balances
    mapping(address=>uint)public balances;

    //Mint function to create new token 

    function mint(address _adr , uint _value) public {
        totalSupply += _value;
        balances[_adr] += _value;
    }

    //Burn function
    function burn(address _adr ,uint _value) public{
        if(_value<=balances[_adr])
        totalSupply -= _value;
        balances[_adr] -= _value;
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.

## Authors

Anmol Prashar  
[@anmolprashar016@gmail.com]


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
