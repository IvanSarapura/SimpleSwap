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

| Contract | Address |
|----------|-----------|
| SimpleSwap | `[TO BE COMPLETED]` |
| TokenA | `[TO BE COMPLETED]` |
| TokenB | `[TO BE COMPLETED]` |

---
*Developed as part of ETH KIPU Module 3*
