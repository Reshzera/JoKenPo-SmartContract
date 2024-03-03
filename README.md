# JoKenPo Smart Contract

## Overview

The JoKenPo smart contract is a blockchain-based implementation of the classic game Rock, Paper, Scissors. This contract allows two players to compete in the game with Ethereum as a bet. The contract is deployed on the Ethereum network and is written in Solidity, a contract-oriented programming language.

## Features

- **Decentralized Game Logic**: The game logic is executed on the Ethereum blockchain, ensuring transparency and fairness.
- **Ether Bets**: Players can bet Ethereum (ETH) on the outcome of the game.
- **Automatic Payouts**: Winnings are automatically transferred to the winner's address.
- **Win Tracking**: The contract keeps track of the number of wins for each player.

## How It Works

1. **Game Initialization**: When the contract is deployed, the contract owner is set, and the game is ready to accept players.
2. **Playing the Game**: Players call the `play` function with their choice (Rock, Paper, or Scissors) and a bet in ETH. The first player to call `play` sets their choice, and the second player's call resolves the game.
3. **Determining the Winner**: The contract evaluates the choices based on the classic rules of Rock, Paper, Scissors, transfers 90% of the total bet amount to the winner, and the remaining 10% to the contract owner as a fee.
4. **Updating Winners**: The contract updates the win count for the winning player.

## How to Interact with the Contract

### Prerequisites

- An Ethereum wallet with ETH for betting and paying gas fees.
- A Solidity-compatible wallet interface (like MetaMask).

### Functions

- **play(Choice \_choice)**: Players call this function to play their hand. Requires a payable amount (minimum 0.01 ETH) and a choice (Rock, Paper, or Scissors). The choice is an enum with values `0` for None, `1` for Rock, `2` for Paper, and `3` for Scissors.
- **result**: A public string that displays the result of the last game.

## Important Considerations

- The contract does not support simultaneous games; players must wait for the current game to conclude before starting a new one.
- In case of a draw, the game's result is updated, but no ETH is transferred.
- The contract owner receives a 10% fee from each game's bet amount.

## Security Features

- The contract uses Solidity ^0.8.0, which includes overflow checks by default.
- The owner's address is immutable, ensuring that the recipient of the contract fees cannot be changed after deployment.

## Testing and Deployment

Before deploying this contract on the main Ethereum network, thorough testing on testnets (like Rinkeby or Ropsten) is highly recommended. Use tools like Hardhat or Truffle for local testing and deployment.

## Conclusion

The JoKenPo smart contract offers a fun and transparent way to play Rock, Paper, Scissors on the Ethereum blockchain. It showcases the potential of smart contracts to mediate and automate traditional games with the added security and transparency of blockchain technology.
