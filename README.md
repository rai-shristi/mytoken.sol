### Project Title

MyToken Solidity smart contract

### Description

This Solidity smart contract implements a basic token functionality with features for minting and burning tokens. It includes public variables to store token details such as name, abbreviation, and total supply. The contract utilizes a mapping to track token balances for each address. The mint function increases the total supply and the balance of a specified address, while the burn function decreases both accordingly, with additional checks to ensure the balance is sufficient for burning.

### Getting Started

Executing program


To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. Copy and paste the following code into the file:


```
pragma solidity 0.8.18;
contract MyToken {

    // public variables
    string public TokenName = "BETA";
    string public TokenAbbrv = "BTA";
    uint public TotalSupply = 0;

    // mapping variable
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint value) public {
        TotalSupply += value;
        balances[_address] += value;
    }

    // burn function
    function burn(address _address, uint value) public {
        if (balances[_address] >= value) {
            TotalSupply -= value;
            balances[_address] -= value;
        }
    }
}
```


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" and then click on the "Compile" button.


Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.
Once the contract is deployed, you can interact with it. 

Call the variables TokenName and TokenAbbrv to see the name of the token and token abbreviation respectively.
Call the mint function and add the address(copy the address from the account) and the value. Click on the transact button to execute the function. Similarly, call the burn function( add address and value) and click on transact to burn the token. Call the balances function to check the balance. The total supply will be updated accordingly to the amount minted and burned.
### Author
Shristi Rai
