# AVAX-PROOF
ETH + AVAX PROOF

##Smart Contract Project
For this project, write a smart contract that implements the require(), assert() and revert() statements.

## EXECUTING THE PROGRAM
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., FileName.sol). Copy and paste the following code into the file:

## Getting Started

To interact with this contract, you will need an Ethereum wallet and some Ether to pay for transaction fees. You can then deploy the contract to the Ethereum network using a service like [Remix](https://remix.ethereum.org/).

CODE: 

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ExampleContract {
    address public owner;
    uint256 public balance;

    constructor() {
        owner = msg.sender;
        balance = 0;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can perform this action");
        _;
    }

    function deposit(uint256 amount) public {
        balance += amount;
    }

    function withdraw(uint256 amount) public onlyOwner {
        require(balance >= amount, "Insufficient balance");
        balance -= amount;
        payable(owner).transfer(amount);
    }

    function assertExample(uint256 a, uint256 b) public pure returns (uint256) {
        // Use assert to check for conditions that should never be false
        assert(a >= b);
        return a - b;
    }

    function revertExample(uint256 a, uint256 b) public pure returns (uint256) {
        // Use revert to handle conditions that are expected to be false and revert the transaction
        if (a < b) {
            revert("a must be greater than or equal to b");
        }
        return a - b;
    }
}





========= END OF CODE ==========

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Filename.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the function.

## Authors

- Femeru
