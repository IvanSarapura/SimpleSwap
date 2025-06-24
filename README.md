# SimpleSwap

SimpleSwap is a decentralized exchange contract that allows:
- Token swapping without intermediaries
- Adding liquidity and obtain LP tokens
- Automatic price calculation

## Contracts

### SimpleSwap.sol
The main contract that handles all swaps and liquidity.

### TokenA.sol and TokenB.sol
Two example tokens for testing the system.

## Main Functions

### `addLiquidity()`
Deposits two tokens into the pool and receives LP tokens in return.

**Important parameters:**
- `tokenA`, `tokenB`: The token addresses
- `amountADesired`, `amountBDesired`: Amounts you want to deposit
- `amountAMin`, `amountBMin`: Minimum amounts

### `removeLiquidity()` 
Burns LP tokens and receives back the original tokens.

### `swapExactTokensForTokens()`
Swaps an exact amount of one token for another.

**Important parameters:**
- `amountIn`: Amount you give
- `amountOutMin`: Minimum amount you expect to receive
- `path`: [input token, output token]

### `getReserves()`
Shows how many tokens are in the pool.

### `getPrice()`
Calculates the current price between two tokens.

## How to Use

### To swap tokens:
1. Approve the token you want to give
2. Call `swapExactTokensForTokens()` with the parameters
3. Receive the new tokens

### To add liquidity:
1. Approve both tokens
2. Call `addLiquidity()` with the amounts
3. Receive LP tokens

### To remove liquidity:
1. Call `removeLiquidity()` with your LP tokens
2. Receive back both tokens

## Test Tokens

### TokenA and TokenB
- **Initial supply**: 1,000,000 tokens each
- **Symbols**: "TACC" and "TBCC"
- **Mint function**: To create more tokens if needed

## Security Features

- **Slippage protection**: Minimum amounts to avoid losses
- **Time validation**: Transactions expire if they take too long
- **Reserve verification**: Ensures there are enough tokens

## Error Messages

| Error | Cause |
|-------|-------|
| `"Same token"` | Using identical token addresses |
| `"Zero address"` | Using null address (0x0) |
| `"Expired"` | Transaction past deadline |
| `"Insufficient amountA/B"` | Amount below minimum threshold |
| `"Insufficient output"` | Swap output below expected minimum |
| `"Invalid reserves"` | Pool has zero reserves |
| `"No liquidity"` | Pool has no liquidity |
| `"Insufficient liquidity"` | Cannot mint LP tokens |
| `"Zero amount"` | Input amount is zero |
| `"Invalid path"` | Path must have exactly 2 tokens |

## Contract Addresses

| Contract | Address | Etherscan Link |
|----------|---------|----------------|
| SimpleSwap | `0x48DaB4616698d9FE5A3A465F97b5E3c1C6d4bCda` | https://sepolia.etherscan.io/address/0x48dab4616698d9fe5a3a465f97b5e3c1c6d4bcda |
| TokenA | `0x03b104c673D55b5DdA4eC698991A2D5A7D444033` | https://sepolia.etherscan.io/address/0x03b104c673d55b5dda4ec698991a2d5a7d444033 |
| TokenB | `0xDEc57cc08821B8BeA347C83F4A624BBdAE1536FE` | https://sepolia.etherscan.io/address/0xdec57cc08821b8bea347c83f4a624bbdae1536fe |

---
*Developed as part of ETH KIPU Module 3*
