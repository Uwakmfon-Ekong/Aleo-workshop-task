# Aleo Workshop Task: Program Building and Deployment Guide

## Overview
This guide details the process followed during our workshop to build and deploy three distinct Aleo programs. These programs cover fundamental arithmetic operations, token minting and transfer, and a simple voice messaging system utilizing Aleo's privacy-focused smart contracts. Each section explains the program's purpose, the implementation details, and the deployment commands used to deploy these programs to the Aleo network.

## Deployment Command
To deploy any of the programs to the Aleo network, use the following command:

```bash
leo deploy --network testnet
```

---

## Task 1: Hello World

### Purpose
The `moovbootcamp_kufre` program demonstrates a basic arithmetic operation (addition) using Aleo's smart contract functionality.

### Functionality
This program defines a `main` function that accepts two public `u32` integers, `a` and `b`, adds them together, and returns the result as `c`.

### Program Execution Command
To execute the program, run the following command:

```bash
leo run main 3u32 2u32
```

### Deployment Link
View the deployed program on the Aleo explorer [here](https://explorer.aleo.org/transaction/at1wuyvymd52l74fvdd47rhc6wk76nagpy7jkfstqnmel8njmcxq5fq8utacw).

---

## Task 2: Token Minting and Transfer

### Purpose
The `moovbootcamp_token_kufre` program provides a basic example of minting and transferring a token on the Aleo network.

### Functionality
This program defines a `Token` record and includes two transitions:

1. **Mint**: Creates a new token with a specified amount for an owner.
2. **Transfer**: Transfers a specified amount of tokens to another address.

### Program Execution Commands

1. **Minting a Token**: 
   ```bash
   leo run mint <aleo_address> <amount>u64
   ```

2. **Transferring a Token**: 
   ```bash
   leo run transfer "<Token_Record>" <to_address> <amount>u64
   ```
   Use the record generated from the mint command as the first input in the transfer command, followed by the destination address and the amount to transfer.

### Deployment Link
View the deployed program on the Aleo explorer [here](https://explorer.aleo.org/transaction/at1a8u5f52t05j5h262qvr0ndmks5yxqf6gz4ar8xsrrsuvzv5wmu9sf5jdda).

---

## Task 3: Voice Messaging System

### Purpose
The `moovbootcamp_voice_kufre` program demonstrates a more complex example of sending voice messages between users on the Aleo network, ensuring privacy and data integrity.

### Functionality
This program allows users to securely send and receive voice messages. It includes functions that:

- Send voice messages.
- Update the on-chain state.
- Combine hash values of the sender (owner) and receiver for secure storage and processing on the Aleo blockchain.

### Program Execution Command
To execute the program, use the following command:

```bash
leo run combine_hash_owner_receiver <owner_address> <receiver_address>
```
- The first input is the owner’s address (`self.caller`).
- The second input is the receiver's address.

### Deployment Link
View the deployed program on the Aleo explorer [here](https://explorer.aleo.org/transaction/at1lsu2pft7kcr4tjt3yz6hk39k4pf9cqzlx3p8lv2kjzanlaudrgzs2zzt5w).

---

## Conclusion
Throughout the workshop, we successfully developed and deployed three Aleo programs:

1. **Arithmetic Operation** - A simple program for adding two numbers.
2. **Token Minting and Transfer** - A basic implementation for creating and transferring tokens.
3. **Voice Messaging System** - A complex application for securely managing and sending voice messages on-chain.
