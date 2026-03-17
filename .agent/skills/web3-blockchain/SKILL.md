---
name: web3-blockchain
description: Blockchain development fundamentals. Smart contracts, dApps, wallets, and Web3 integration patterns. Use when building decentralized applications.
---

# Web3 & Blockchain

> Decentralized. Trustless. Immutable. Build applications without intermediaries.

---

## 1. Technology Stack

### Blockchain Selection

| Blockchain | Best For | Language |
|-----------|----------|---------|
| **Ethereum** | DeFi, NFTs, dApps | Solidity |
| **Solana** | High throughput, low fees | Rust |
| **Polygon** | Ethereum L2, low cost | Solidity |
| **Base** | Coinbase L2, consumer apps | Solidity |
| **Near** | Developer-friendly | Rust/JS |

### Development Tools

| Tool | Purpose |
|------|---------|
| **Hardhat** | Ethereum dev environment |
| **Foundry** | Fast, Solidity-native testing |
| **Remix IDE** | Browser-based Solidity IDE |
| **Anchor** | Solana framework |
| **ethers.js / viem** | JS blockchain interaction |
| **wagmi** | React hooks for Ethereum |

---

## 2. Smart Contract Principles

### Solidity Best Practices

| Principle | Application |
|-----------|-------------|
| **Checks-Effects-Interactions** | Validate → update state → external calls |
| **Minimal storage** | Storage is expensive ($$$) |
| **Reentrancy guard** | Use OpenZeppelin ReentrancyGuard |
| **Access control** | Ownable, roles-based |
| **Events** | Emit for all state changes |
| **Upgradability** | Proxy pattern (with caution) |

---

## 3. dApp Architecture

### Frontend Integration

```
User → Wallet (MetaMask) → dApp Frontend → Smart Contract → Blockchain
                               ↓
                          Backend (indexer, APIs)
```

| Layer | Technology |
|-------|-----------|
| **Frontend** | React + wagmi + viem |
| **Wallet** | MetaMask, WalletConnect, Coinbase Wallet |
| **Indexing** | The Graph, custom indexer |
| **Storage** | IPFS, Arweave (off-chain data) |
| **Backend** | Node.js for off-chain logic |

---

## 4. Security

### Common Vulnerabilities

| Vulnerability | Prevention |
|--------------|-----------|
| **Reentrancy** | Checks-Effects-Interactions, ReentrancyGuard |
| **Integer overflow** | Solidity 0.8+ (built-in checks) |
| **Front-running** | Commit-reveal schemes |
| **Access control** | Role-based, multi-sig |
| **Oracle manipulation** | Use Chainlink, multiple sources |

### Audit Process

| Step | Action |
|------|--------|
| 1 | Unit tests with 100% coverage |
| 2 | Static analysis (Slither, Mythril) |
| 3 | Professional audit |
| 4 | Bug bounty program |
| 5 | Gradual deployment (testnet → mainnet) |

---

## 5. Testing

| Type | Tool |
|------|------|
| **Unit** | Hardhat/Foundry tests |
| **Fork testing** | Mainnet fork simulation |
| **Fuzzing** | Foundry fuzzer, Echidna |
| **Formal verification** | Certora, K Framework |

---

## 6. Gas Optimization

| Technique | Savings |
|-----------|---------|
| Pack storage variables | Significant |
| Use calldata over memory | Moderate |
| Short-circuit conditions | Minor |
| Batch operations | Significant |
| Use mappings over arrays | Moderate |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Deploy without audit | Professional security audit |
| Store secrets on-chain | Everything on-chain is public |
| Skip testnet | Always test on testnet first |
| Complex upgrade logic | Keep contracts simple |
| Trust user input | Validate everything in contract |

---

> **Remember:** Smart contracts are immutable once deployed. Bugs can't be patched — they can only be migrated. Test obsessively, audit thoroughly, deploy carefully.
