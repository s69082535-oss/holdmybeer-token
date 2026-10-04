# HOLDMYBEER ($HMB) — Official Documentation & Entity Hub

[![Network: Polygon](https://img.shields.io/badge/Network-Polygon_PoS-8247E5?style=flat&logo=polygon)](https://polygonscan.com/token/0x4Fc68a545F56e04E12E2f98b4AA4Fa6ea160596c)
[![Standard: ERC-20](https://img.shields.io/badge/Standard-ERC--20-blue.svg)](https://eips.ethereum.org/EIPS/eip-20)
[![Tax: 0%](https://img.shields.io/badge/Tax-0%25-brightgreen.svg)]()
[![Campaign: 20 Airdrops](https://img.shields.io/badge/Campaign-20_Airdrops-orange.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Official technical repository, entity proof, and distribution architecture for the **HOLDMYBEER ($HMB)** token deployed on the Polygon PoS network.

---

## 1. Technical Specification

| Property | Value |
| :--- | :--- |
| **Token Name** | HOLDMYBEER |
| **Token Symbol** | HMB |
| **Network** | Polygon PoS (Chain ID: `137`) |
| **Contract Address (CA)** | `0x4Fc68a545F56e04E12E2f98b4AA4Fa6ea160596c` |
| **Token Standard** | ERC-20 |
| **Decimals** | 18 |
| **Total Supply** | 1,000,000,000,000,000 HMB (Fixed / Immutable) |
| **Buy / Sell Tax** | 0% (Zero Fee) |
| **Liquidity Pools** | QuickSwap (HMB/USDT, HMB/POL) |

---

## 2. Smart Contract Status & Static Bytecode Audit

> **Verification Notice**: The smart contract source code is currently unverified on Polygonscan due to omitted metadata during factory generation. To ensure full security and transparency, this repository serves as the public source of truth.

The deployed EVM bytecode at `0x4Fc68a545F56e04E12E2f98b4AA4Fa6ea160596c` was statically decompiled and analyzed. Full machine-readable audit proofs are available in [`evidence.json`](./evidence.json).

### Compiler & Core Architecture
* **Solidity Compiler Version**: `v0.7.4+commit.3f05b770` (`solc 0.7.4`)
* **Framework**: OpenZeppelin Standard ERC-20 implementation with `SafeMath`.
* **Bytecode Metadata (IPFS)**: `dc5005de4f4f5f3916bc5f9ad90cafa1b5d28c3a239463a80d26da06de9f5806`

### Exhaustive Function Selectors Table
The dispatcher contains strictly **9 standard functions**:

| Selector | Signature | Security Verdict |
| :--- | :--- | :--- |
| `0x06fdde03` | `name()` | Pure view standard |
| `0x095ea7b3` | `approve(address,uint256)` | Standard ERC-20 |
| `0x18160ddd` | `totalSupply()` | Pure view standard |
| `0x23b872dd` | `transferFrom(address,address,uint256)` | Standard ERC-20 (0% deduction) |
| `0x313ce567` | `decimals()` | Pure view standard |
| `0x39509351` | `increaseAllowance(address,uint256)` | OpenZeppelin safe utility |
| `0x70a08231` | `balanceOf(address)` | Pure view standard |
| `0x95d89b41` | `symbol()` | Pure view standard |
| `0xa457c2d7` | `decreaseAllowance(address,uint256)` | OpenZeppelin safe utility |
| `0xa9059cbb` | `transfer(address,uint256)` | Standard ERC-20 (0% deduction) |
| `0xdd62ed3e` | `allowance(address,address)` | Pure view standard |

### Security Guarantees Proven by Bytecode:
* **No Hidden Mint**: `mint()` function does NOT exist. Supply is capped forever.
* **No Blacklist / Freezing**: Zero blacklist mapping or conditional wallet blocking.
* **No Pausable Functions**: Transfers cannot be halted.
* **0% Transfer Tax**: Math opcodes subtract $X$ from sender and add exactly $X$ to recipient.
* **No Selfdestruct**: Opcode `0xff` is absent.
* **No Owner Privileges**: Standard unextended contract without admin/backdoor access.

---

## 3. Tokenomics & Distribution Strategy

The total supply was 100% pre-minted at deployment. Initial decentralized exchange (DEX) liquidity was added solely to initialize market routing and price discovery.

### Two-Pillar Distribution Model
1. **Market Circulation**: Systematic, gradual release of project-controlled tokens directly into open decentralized market mechanisms.
2. **20 Community Airdrops**: Progressive distribution directly to qualified holders across 20 independent milestone events.

---

## 4. Community Campaign: 20 Airdrops Hub

The token distribution campaign consists of 20 sequential rounds. Every round operates under clear on-chain criteria without tasks, off-chain points, or third-party KYC.

### Current Active Event: Airdrop #1

* **Pool Allocation**: `20,000,000,000 HMB`
* **Qualification Threshold**: Hold at least `200,000,000 HMB` in a single non-custodial wallet.
* **Eligible Participants**: Top-100 qualified holders by balance at final snapshot.

#### Reward Distribution Breakdown:
* **1st Place**: 2,500,000,000 HMB
* **2nd – 5th Places** (4 wallets): 1,500,000,000 HMB each (*6,000,000,000 HMB total*)
* **6th – 20th Places** (15 wallets): 500,000,000 HMB each (*7,500,000,000 HMB total*)
* **21st – 100th Places** (80 wallets): 50,000,000 HMB each (*4,000,000,000 HMB total*)
* **Total Round Pool**: **20,000,000,000 HMB** (100% matched)

#### Execution Phases:
1. **Phase 1: Activation (Current Phase)**: Condition monitoring. Round 1 officially activates as soon as the Polygon ledger confirms **100 independent holder wallets** holding $\ge 200,000,000\text{ HMB}$.
2. **Phase 2: Holding & Snapshot (10 Days)**: A 10-day retention countdown commences upon activation. A snapshot is executed on Polygon block height to determine the final Top-100 winners.
*Exclusions: Exchange wallets, liquidity pools, service addresses, and smart contracts are filtered out.*

---

## 5. Official Links & Canonical Resources

* **Official Website (GitHub Pages)**: [s69082535-oss.github.io/holdmybeer-token](https://s69082535-oss.github.io/holdmybeer-token/)
* **Official X (Twitter)**: [@HmbToken72656](https://x.com/HmbToken72656)
* **Block Explorer (Polygonscan)**: [0x4Fc68a545F56e04E12E2f98b4AA4Fa6ea160596c](https://polygonscan.com/token/0x4Fc68a545F56e04E12E2f98b4AA4Fa6ea160596c)
* **QuickSwap DEX Pairs (GeckoTerminal Tracking)**:
  * [HMB / USDT Pool](https://www.geckoterminal.com/polygon_pos/pools/0x88c86cc2dfb3cebba152798f72d1c1da5d1690a8)
  * [HMB / POL Pool](https://www.geckoterminal.com/polygon_pos/pools/0x1bc87a450a3083ae73ac9200b0b4662fa875c0cf)
