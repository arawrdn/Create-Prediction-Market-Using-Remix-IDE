# Base Prediction Market

This repository contains a simple **Prediction Market** smart contract deployable on the **Base Network** using Remix IDE. Users can bet on outcomes, and the winners receive the total pool proportionally.

---

## 1. Open Remix IDE

- Go to [https://remix.ethereum.org](https://remix.ethereum.org)  
- Connect your wallet (e.g., MetaMask, OKX, Bitget) to Base Testnet or Mainnet.

---

## 2. Create Contract File

- File path: `contracts/PredictionMarket.sol`  
- Paste the smart contract code from `PredictionMarket.sol`.

---

## 3. Compile Contract

- Solidity compiler: **0.8.13**  
- Enable optimization (optional)  
- Click **Compile PredictionMarket.sol**  

> Ensure there are no compilation errors.

---

## 4. Deploy Contract

- Environment: **Injected Web3**  
- Network: Base Testnet/Mainnet  
- Constructor parameters:  
  1. ERC20 token address (used for betting)  
  2. Array of outcome names, e.g.:  
     ```solidity
     ["TeamA Wins","TeamB Wins","Draw"]
     ```  
- Click **Deploy** and confirm in your wallet

---

## 5. Interact with Contract

### Place Bet
- `placeBet(outcomeId, amount)` → Place your bet on an outcome  
  - `outcomeId` starts from 0  
  - Approve Marketplace contract to spend your ERC20 tokens first  

### Close Market
- `closeMarket(winningOutcomeId)` → Owner closes the market and declares the winning outcome  

### Claim Payout
- `claimPayout()` → Winners can claim their share of the total pool  

### Admin Functions
- `withdrawTokens(amount)` → Owner can withdraw any ERC20 tokens from the contract  

---

## Notes

- Ensure the market has sufficient liquidity in ERC20 tokens.  
- Betting is **proportional**, payout is based on contribution to winning outcome.  
- For production, consider adding:  
  - Time-limited betting  
  - Security checks  
  - Multiple rounds  

