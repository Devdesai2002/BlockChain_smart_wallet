# Smart Token Wallet

## Overview

**Wallet** is a secure, production-ready smart contract for managing ERC20 tokens and Ether on the Ethereum blockchain.

It enables:
- Token & ETH deposits
- Signature-authorized withdrawals
- Fee accumulation & withdrawal
- Replay-protected nonce management
- HOT Protocol validator verification

The contract integrates with **HOT Protocol validators** and supports cross-chain authorization via MPC-backed signature validation.


---

## 🔐 Core Architecture

The contract is built around:

- **Owner-based administrative control**
- **ECDSA signature verification**
- **Nonce-based replay protection**
- **Timestamp enforcement**
- **HOT Protocol validation hooks**

---

## 🚀 Key Functionalities

---

### 1️⃣ Ownership & Access Control

The contract follows an **Ownable pattern**.

#### Owner Privileges

Only the owner can:

- `withdrawToken()` → Withdraw ERC20 tokens
- `withdrawEth()` → Withdraw Ether
- `withdrawFees()` → Withdraw accumulated protocol fees
- `changeOwner()` → Transfer ownership
- `close()` → Close contract (prevents further operations)

The owner is set at deployment.

---

### 2️⃣ Deposits

Users can deposit **ERC20 tokens or Ether**.

```solidity
deposit()
