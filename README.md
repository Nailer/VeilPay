<div align="center">

```
██╗   ██╗███████╗██╗██╗     ██████╗  █████╗ ██╗   ██╗
██║   ██║██╔════╝██║██║     ██╔══██╗██╔══██╗╚██╗ ██╔╝
██║   ██║█████╗  ██║██║     ██████╔╝███████║ ╚████╔╝ 
╚██╗ ██╔╝██╔══╝  ██║██║     ██╔═══╝ ██╔══██║  ╚██╔╝  
 ╚████╔╝ ███████╗██║███████╗██║     ██║  ██║   ██║   
  ╚═══╝  ╚══════╝╚═╝╚══════╝╚═╝     ╚═╝  ╚═╝   ╚═╝   
```

# VeilPay

### *The First Private Financial Operating System for Global Stablecoin Commerce*

**Built on Solana · Powered by Umbra SDK · USDC Native**

---

[![Solana](https://img.shields.io/badge/Solana-9945FF?style=for-the-badge&logo=solana&logoColor=white)](https://solana.com)
[![USDC](https://img.shields.io/badge/USDC-2775CA?style=for-the-badge&logo=circle&logoColor=white)](https://www.circle.com/usdc)
[![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-00E5FF?style=for-the-badge)](LICENSE)

---

> *"Crypto accidentally turned finance into public social media.*
> *VeilPay gives it back the dignity it deserves."*

---

</div>

## Table of Contents

- [The Problem We Solve](#-the-problem-we-solve)
- [What is VeilPay](#-what-is-veilpay)
- [How VeilPay Works — Complete System Architecture](#-how-veilpay-works--complete-system-architecture)
  - [High-Level System Overview](#1-high-level-system-overview)
  - [The GhostID Identity Layer](#2-the-ghostid-identity-layer)
  - [Private Payment Flow — Step by Step](#3-private-payment-flow--step-by-step)
  - [Umbra SDK Integration Architecture](#4-umbra-sdk-integration-architecture)
  - [AI Financial Agent System](#5-ai-financial-agent-system)
  - [Selective Compliance Engine](#6-selective-compliance-engine)
  - [Multi-Profile Identity System](#7-multi-profile-identity-system)
- [Core Features](#-core-features)
- [Use Cases](#-use-cases)
- [The Five Core Systems](#-the-five-core-systems)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [API Reference](#-api-reference)
- [Security Model](#-security-model)
- [Ecosystem & Bounties](#-ecosystem--bounties)
- [Roadmap](#-roadmap)
- [Team](#-team)
- [License](#-license)

---

## 🚨 The Problem We Solve

Right now, if you give someone your crypto wallet address — or if they find it anywhere — they immediately know:

```
Your wallet address → 0x742d35Cc6634...

PUBLIC INFORMATION exposed:
├── 💰  Your exact net worth (every token, every balance)
├── 📊  Your complete income history (every payment received)
├── 🔍  Every business you've transacted with
├── 👥  Your employees and their salaries
├── 🏢  Your company's entire treasury movement
├── 📅  Every subscription you pay for
├── 🤝  Your customers and clients
├── 📈  Your trading activity and strategies
└── 🔗  Your entire financial life — forever, immutably
```

This is not a minor inconvenience. This is a **fundamental structural flaw** in how blockchain-based finance works today. Every single transaction you have ever made is permanently and publicly visible to anyone with a browser.

Consider what this means in practice:

- A freelancer gets paid $15,000 for a project. Their client can now see every other client they have, what they earn, and their total net worth — permanently.
- A startup pays its 50 employees in USDC. Competitors, journalists, and anyone else can now see every salary, every payout, and the company's exact treasury balance.
- An AI agent executes treasury rebalancing trades. Front-runners can now watch every move in real time and arbitrage against the strategy.
- A DAO distributes grants to contributors. The entire funding history, recipient list, and amounts are permanently exposed on-chain.

**The biggest unsolved problem in crypto is no longer speed or scalability. It is financial dignity and privacy.**

VeilPay exists to solve this — completely, elegantly, and without sacrificing the compliance and regulatory capabilities that real-world finance demands.

---

## 🔐 What is VeilPay

VeilPay is **not a wallet**. It is not a payment app. It is not a privacy coin.

VeilPay is a **private financial operating system** — the infrastructure layer that sits on top of Solana and the Umbra SDK to enable every type of financial interaction to happen with the same level of privacy that people expect from traditional banking, but with the speed, programmability, and composability of blockchain technology.

Think of it this way:

```
Traditional Banking:   Privacy ✓   But: Slow, Centralized, Exclusionary, Opaque
Public Crypto:         Fast ✓      But: Zero Privacy, Fully Exposed, Unusable for Business
                       
VeilPay:               Privacy ✓   Fast ✓   Decentralized ✓   Programmable ✓   Compliant ✓
```

The vision: **Stripe-grade infrastructure + Revolut-grade UX + Swiss-bank privacy + Solana speed**.

VeilPay makes stablecoins usable for real life — not speculation, not trading, not memecoins. **Real commerce. Real business. Real people.**

---

## 🏗 How VeilPay Works — Complete System Architecture

This section provides a comprehensive, technical walkthrough of every component of the VeilPay system — how they interact, what they depend on, and how data flows through the platform from the moment a user initiates an action to the moment a private transaction is settled on-chain.

---

### 1. High-Level System Overview

The following diagram illustrates all major components of the VeilPay platform and how they interact:

```
╔══════════════════════════════════════════════════════════════════════════════════╗
║                          VEILPAY SYSTEM ARCHITECTURE                            ║
╠══════════════════════════════════════════════════════════════════════════════════╣
║                                                                                  ║
║   ┌─────────────────────────────────────────────────────────────────────────┐   ║
║   │                         USER INTERFACE LAYER                            │   ║
║   │                                                                         │   ║
║   │   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌───────────┐  │   ║
║   │   │  Dashboard   │  │   Payments   │  │  AI Agents   │  │ Payroll   │  │   ║
║   │   │  (Next.js)   │  │    Portal    │  │  Manager     │  │  Console  │  │   ║
║   │   └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └─────┬─────┘  │   ║
║   │          └─────────────────┴──────────────────┴────────────────┘        │   ║
║   │                                    │                                     │   ║
║   │                    Solana Wallet Adapter + RPC                           │   ║
║   └────────────────────────────────────┬────────────────────────────────────┘   ║
║                                        │                                         ║
║                                        ▼                                         ║
║   ┌─────────────────────────────────────────────────────────────────────────┐   ║
║   │                        VEILPAY APPLICATION CORE                         │   ║
║   │                                                                         │   ║
║   │   ┌───────────────────┐        ┌───────────────────────────────────┐    │   ║
║   │   │  GhostID Resolver │        │     Identity & Vault Manager      │    │   ║
║   │   │                   │        │                                   │    │   ║
║   │   │  @username ──────►│──────► │  Master Keys  │  Stealth Engine  │    │   ║
║   │   │  lookup / create  │        │  Vault State  │  Profile Router  │    │   ║
║   │   └───────────────────┘        └───────────────────────────────────┘    │   ║
║   │                                                                         │   ║
║   │   ┌───────────────────┐        ┌───────────────────────────────────┐    │   ║
║   │   │  Payment Router   │        │     Compliance Engine             │    │   ║
║   │   │                   │        │                                   │    │   ║
║   │   │  Amount Encoding  │        │  Viewing Keys  │  ZK Proofs      │    │   ║
║   │   │  Memo Encryption  │        │  Audit Export  │  Tax Reports    │    │   ║
║   │   └─────────┬─────────┘        └───────────────────────────────────┘    │   ║
║   │             │                                                            │   ║
║   │   ┌─────────▼─────────┐        ┌───────────────────────────────────┐    │   ║
║   │   │  AI Agent Layer   │        │     Ghost Commerce SDK            │    │   ║
║   │   │                   │        │                                   │    │   ║
║   │   │  Orchestration    │        │  Private Checkout  │  Invoicing   │    │   ║
║   │   │  Execution Engine │        │  Subscriptions     │  API Billing │    │   ║
║   │   └─────────┬─────────┘        └───────────────────────────────────┘    │   ║
║   └─────────────┼───────────────────────────────────────────────────────────┘   ║
║                 │                                                                ║
║                 ▼                                                                ║
║   ┌─────────────────────────────────────────────────────────────────────────┐   ║
║   │                         UMBRA SDK PRIVACY LAYER                         │   ║
║   │                    (Core Privacy Infrastructure)                        │   ║
║   │                                                                         │   ║
║   │   ┌───────────────┐  ┌───────────────┐  ┌────────────┐  ┌───────────┐  │   ║
║   │   │    Stealth    │  │   Encrypted   │  │  Viewing   │  │Nullifier  │  │   ║
║   │   │    Address    │  │    Balance    │  │    Key     │  │  System   │  │   ║
║   │   │   Generator   │  │   Manager    │  │  Registry  │  │           │  │   ║
║   │   └───────┬───────┘  └───────┬───────┘  └─────┬──────┘  └─────┬─────┘  │   ║
║   │           └──────────────────┴────────────────┴───────────────┘         │   ║
║   └────────────────────────────────────┬────────────────────────────────────┘   ║
║                                        │                                         ║
║                                        ▼                                         ║
║   ┌─────────────────────────────────────────────────────────────────────────┐   ║
║   │                         SOLANA BLOCKCHAIN LAYER                         │   ║
║   │                                                                         │   ║
║   │   ┌───────────────┐  ┌───────────────┐  ┌────────────┐  ┌───────────┐  │   ║
║   │   │  Confidential │  │    Private    │  │ Streaming  │  │  On-chain │  │   ║
║   │   │   Transfers   │  │     Swap      │  │  Payments  │  │  Payroll  │  │   ║
║   │   │   (Program)   │  │   Routing     │  │  Program   │  │  Program  │  │   ║
║   │   └───────────────┘  └───────────────┘  └────────────┘  └───────────┘  │   ║
║   │                                                                         │   ║
║   │                    USDC · SOL · SPL Tokens                              │   ║
║   └─────────────────────────────────────────────────────────────────────────┘   ║
║                                                                                  ║
╚══════════════════════════════════════════════════════════════════════════════════╝
```

Every interaction in VeilPay flows top-down through these four layers:
1. **UI Layer** — What the user sees and interacts with
2. **Application Core** — Business logic, routing, identity resolution, AI orchestration
3. **Umbra SDK Privacy Layer** — The cryptographic engine that shields all financial data
4. **Solana Blockchain** — The decentralized settlement and execution layer

---

### 2. The GhostID Identity Layer

The GhostID system is the foundational user-facing innovation of VeilPay. It replaces the hostile, error-prone experience of raw wallet addresses with human-readable identity handles — while maintaining complete cryptographic privacy underneath.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        GHOSTID IDENTITY ARCHITECTURE                        │
│                                                                             │
│                                                                             │
│   TRADITIONAL CRYPTO                      VEILPAY GHOSTID                  │
│   ─────────────────                       ───────────────                  │
│                                                                             │
│   "Send to:"                              "Send to:"                       │
│   0x742d35Cc6634C0532925a3b8D4C9...       @sukuna                          │
│                       │                              │                     │
│                       │                              │                     │
│                       ▼                              ▼                     │
│              ┌─────────────────┐         ┌──────────────────────┐         │
│              │  PUBLIC on-chain│         │  GhostID Registry    │         │
│              │                 │         │  (off-chain mapping) │         │
│              │  Your balance   │         │                      │         │
│              │  Your history   │         │  @sukuna             │         │
│              │  Your identity  │         │  → Public Spend Key  │         │
│              │  All EXPOSED    │         │  → Public View Key   │         │
│              └─────────────────┘         └──────────┬───────────┘         │
│                                                     │                     │
│                                                     │ Umbra SDK derives   │
│                                                     ▼                     │
│                                         ┌──────────────────────┐         │
│                                         │  One-Time Stealth    │         │
│                                         │  Receiving Address   │         │
│                                         │                      │         │
│                                         │  0x9f3a...b72c       │         │
│                                         │  (NEW for every tx)  │         │
│                                         └──────────────────────┘         │
│                                                     │                     │
│                                                     │                     │
│                                                     ▼                     │
│                                         ┌──────────────────────┐         │
│                                         │  BLOCKCHAIN SEES:    │         │
│                                         │                      │         │
│                                         │  Encrypted state     │         │
│                                         │  Unknown sender      │         │
│                                         │  Unknown receiver    │         │
│                                         │  Hidden amount       │         │
│                                         └──────────────────────┘         │
│                                                                             │
│                                                                             │
│   WHEN USER REGISTERS ON VEILPAY:                                           │
│   ─────────────────────────────────────────────────────────────────────   │
│                                                                             │
│   Step 1: Choose username          @alice                                  │
│                │                                                            │
│               ▼                                                             │
│   Step 2: System generates         Master Private Key (never leaves device)│
│                │                   Master View Key (for viewing txns)       │
│               ▼                   Public Spend Key (for address derivation) │
│   Step 3: Keys stored in          Encrypted local vault                    │
│                │                  Viewing key in registry (for receiving)  │
│               ▼                                                             │
│   Step 4: GhostID published       @alice → Public Spend Key (safe to share)│
│                                                                             │
│   RESULT: Anyone can SEND to @alice.                                        │
│           Nobody can FIND @alice on-chain.                                  │
│           Alice can RECEIVE privately, forever.                             │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Key Properties of GhostID:**

| Property | Description |
|----------|-------------|
| **Human-readable** | `@alice` instead of `0x742d35Cc...` |
| **Unlinkable** | Each payment generates a completely new on-chain address |
| **Non-custodial** | Private keys never leave the user's device |
| **Composable** | One user, multiple profiles (Personal, Business, DAO, AI) |
| **Publicly safe** | The GhostID itself can be shared on social media, business cards, invoices — with zero risk |

---

### 3. Private Payment Flow — Step by Step

This is the most critical flow in VeilPay. Every private transaction follows this exact path from initiation to settlement:

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║               COMPLETE PRIVATE PAYMENT FLOW — END TO END                     ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║   ALICE wants to send $500 USDC to BOB privately                             ║
║                                                                               ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 1: INITIATION (Alice's Device)                               │    ║
║   │                                                                     │    ║
║   │  Alice opens VeilPay                                                │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Types "@bobdesign" as recipient  ◄── Human readable. No addresses │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Enters $500 USDC + encrypted memo                                  │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Clicks "Send Privately"                                            │    ║
║   └─────────────────────────┬───────────────────────────────────────────┘    ║
║                             │                                                 ║
║                             ▼                                                 ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 2: IDENTITY RESOLUTION (VeilPay Core)                        │    ║
║   │                                                                     │    ║
║   │  GhostID Registry lookup: @bobdesign                                │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Returns Bob's PUBLIC SPEND KEY + PUBLIC VIEW KEY                   │    ║
║   │  (These are safe to share — they reveal nothing about Bob)          │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Alice's device validates Bob's keys                                │    ║
║   │  (No server involved — fully client-side cryptography)              │    ║
║   └─────────────────────────┬───────────────────────────────────────────┘    ║
║                             │                                                 ║
║                             ▼                                                 ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 3: STEALTH ADDRESS GENERATION (Umbra SDK)                    │    ║
║   │                                                                     │    ║
║   │  Alice's device calls Umbra SDK:                                    │    ║
║   │                                                                     │    ║
║   │  umbra.generateStealthAddress(                                      │    ║
║   │      recipientPublicSpendKey: Bob.spendKey,                         │    ║
║   │      recipientPublicViewKey:  Bob.viewKey,                          │    ║
║   │      ephemeralPrivateKey:     random()        ◄── new every time    │    ║
║   │  )                                                                  │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  OUTPUT:                                                            │    ║
║   │  ├── stealthAddress:    0x9f3a...b72c  (one-time receiving addr)    │    ║
║   │  └── ephemeralPubKey:   0xe4f1...a93d  (announcement key)          │    ║
║   │                                                                     │    ║
║   │  ⚠ IMPORTANT: This stealth address is mathematically derived        │    ║
║   │    from Bob's public keys — but CANNOT be linked back to Bob        │    ║
║   │    without Bob's private view key. Even Alice cannot prove          │    ║
║   │    she paid Bob without Bob's cooperation.                          │    ║
║   └─────────────────────────┬───────────────────────────────────────────┘    ║
║                             │                                                 ║
║                             ▼                                                 ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 4: TRANSACTION CONSTRUCTION & ENCRYPTION                     │    ║
║   │                                                                     │    ║
║   │  VeilPay constructs the transaction:                                │    ║
║   │                                                                     │    ║
║   │  Transaction {                                                      │    ║
║   │    to:          stealthAddress,     ◄── unlinkable to Bob           │    ║
║   │    amount:      encrypt(500 USDC),  ◄── hidden from observers       │    ║
║   │    memo:        encrypt("Invoice"), ◄── encrypted with Bob's key    │    ║
║   │    announcement:ephemeralPubKey,    ◄── lets Bob find the payment   │    ║
║   │    nullifier:   hash(secret+index)  ◄── prevents double-spend       │    ║
║   │  }                                                                  │    ║
║   │                                                                     │    ║
║   │  Alice signs with her wallet                                        │    ║
║   └─────────────────────────┬───────────────────────────────────────────┘    ║
║                             │                                                 ║
║                             ▼                                                 ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 5: ON-CHAIN SETTLEMENT (Solana)                              │    ║
║   │                                                                     │    ║
║   │  Transaction submitted to Solana                                    │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  ~400ms confirmation                                                │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  ON-CHAIN STATE (what the blockchain publicly shows):               │    ║
║   │  ├── Sender:    [ENCRYPTED]   ◄── Alice is anonymous               │    ║
║   │  ├── Receiver:  0x9f3a...b72c ◄── One-time addr, unlinked to Bob   │    ║
║   │  ├── Amount:    [ENCRYPTED]   ◄── $500 is hidden                   │    ║
║   │  ├── Memo:      [ENCRYPTED]   ◄── Content hidden                   │    ║
║   │  └── Ephemeral: 0xe4f1...a93d ◄── Only Bob can interpret this      │    ║
║   └─────────────────────────┬───────────────────────────────────────────┘    ║
║                             │                                                 ║
║                             ▼                                                 ║
║   ┌─────────────────────────────────────────────────────────────────────┐    ║
║   │  PHASE 6: RECIPIENT SCANNING & DISCOVERY (Bob's Device)             │    ║
║   │                                                                     │    ║
║   │  Bob's VeilPay runs background scan:                                │    ║
║   │                                                                     │    ║
║   │  For each announcement on-chain:                                    │    ║
║   │    try {                                                             │    ║
║   │      payment = umbra.checkForPayment(                               │    ║
║   │          announcement:   ephemeralPubKey,                           │    ║
║   │          myPrivateViewKey: Bob.viewKey    ◄── only Bob has this     │    ║
║   │      )                                                              │    ║
║   │      if (payment.belongsToMe) {                                     │    ║
║   │          addToVault(decrypt(payment.amount))                        │    ║
║   │          showNotification("You received funds privately")           │    ║
║   │      }                                                              │    ║
║   │    }                                                                │    ║
║   │       │                                                             │    ║
║   │       ▼                                                             │    ║
║   │  Bob's private vault updates: +$500 USDC                           │    ║
║   │  Bob sees:  "Received $500 USDC · Memo: Invoice"                   │    ║
║   │  World sees: nothing.                                               │    ║
║   └─────────────────────────────────────────────────────────────────────┘    ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

**What each party sees:**

| Observer | What They See | What They Know |
|----------|--------------|----------------|
| **Alice (Sender)** | Her private vault balance decreasing, confirmation | She sent $500 to @bobdesign |
| **Bob (Recipient)** | His private vault balance increasing, decrypted memo | He received $500 from someone |
| **Blockchain Explorer** | An encrypted state transition, a one-time address | Nothing meaningful |
| **Alice's Employer** | Nothing | Nothing — Alice's payment life is hidden |
| **Bob's Competitor** | Nothing | They cannot see Bob's income or clients |
| **Government Auditor** | Only what Bob explicitly unlocks via viewing key | Only what Bob authorizes |

---

### 4. Umbra SDK Integration Architecture

The Umbra SDK is the cryptographic foundation of everything VeilPay does. It is not an optional add-on or an integration layer — it is the core infrastructure. Without Umbra, none of VeilPay's privacy properties are possible.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    UMBRA SDK — VEILPAY INTEGRATION MAP                      │
│                                                                             │
│                                                                             │
│   VeilPay Feature              Umbra Primitive Used          How            │
│   ───────────────              ────────────────────          ───            │
│                                                                             │
│   GhostID Receiving  ────────► Stealth Address Gen  ──────► Per-tx unique  │
│                                                              address derive  │
│                                                                             │
│   Private Balances   ────────► Encrypted Balance    ──────► On-chain state │
│                                Manager               ──────► shielding      │
│                                                                             │
│   Compliance Keys    ────────► Viewing Key System   ──────► Selective read │
│                                                              access grants   │
│                                                                             │
│   Anti Double-spend  ────────► Nullifier Registry   ──────► Spent note     │
│                                                              tracking        │
│                                                                             │
│   Private Memos      ────────► Encrypted Metadata   ──────► ECDH memo      │
│                                                              encryption      │
│                                                                             │
│   AI Agent Privacy   ────────► Isolated Key Spaces  ──────► Per-agent      │
│                                                              vault isolation │
│                                                                             │
│                                                                             │
│   ═══════════════════════════════════════════════════════════════════════   │
│                                                                             │
│   UMBRA SDK INTERNAL COMPONENTS (as VeilPay uses them):                    │
│                                                                             │
│                                                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐  │
│   │                    STEALTH ADDRESS ENGINE                           │  │
│   │                                                                     │  │
│   │  Input:  Recipient's (spendPubKey, viewPubKey) + randomEphemeral   │  │
│   │                                                                     │  │
│   │  ECDH:   sharedSecret = ephemeralPrivKey × viewPubKey              │  │
│   │          hashedSecret = keccak256(sharedSecret)                    │  │
│   │                                                                     │  │
│   │  Output: stealthAddr = spendPubKey + hashedSecret × G              │  │
│   │          announcement = ephemeralPubKey (public, on-chain)         │  │
│   │                                                                     │  │
│   │  Verification (Bob side):                                           │  │
│   │          sharedSecret = viewPrivKey × ephemeralPubKey              │  │
│   │          hashedSecret = keccak256(sharedSecret)                    │  │
│   │          expected     = spendPubKey + hashedSecret × G             │  │
│   │          match?       = (expected == stealthAddr)  → MINE!         │  │
│   └─────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐  │
│   │                    ENCRYPTED BALANCE MANAGER                        │  │
│   │                                                                     │  │
│   │  All balances stored as:  Encrypt(amount, recipientViewKey)        │  │
│   │                                                                     │  │
│   │  Only the recipient's view key can decrypt the balance.            │  │
│   │  On-chain: just a ciphertext blob.                                 │  │
│   │  Observer: sees bytes, learns nothing about the amount.            │  │
│   └─────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐  │
│   │                        VIEWING KEY SYSTEM                           │  │
│   │                                                                     │  │
│   │  viewingKey = derive(masterViewKey, scope, timeRange)               │  │
│   │                                                                     │  │
│   │  Scoped access:  Only decrypts transactions matching the scope     │  │
│   │  Time-limited:   Key mathematically expires at a block height      │  │
│   │  Non-delegatable: Cannot be used to create further sub-keys        │  │
│   │                                                                     │  │
│   │  This is the compliance bridge:                                    │  │
│   │  Share only what regulators need. Nothing else.                    │  │
│   └─────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

### 5. AI Financial Agent System

VeilPay's AI Agent layer is one of the most significant technical and commercial differentiators of the platform. As AI systems become autonomous economic actors, they need the same financial privacy infrastructure that humans do — and arguably more, since their strategies are most at risk from on-chain surveillance.

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                      AI FINANCIAL AGENT ARCHITECTURE                        ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   USER CREATES AN AI AGENT                                                   ║
║        │                                                                     ║
║        ▼                                                                     ║
║   ┌────────────────────────────────────────────────────────────────────┐    ║
║   │  AGENT PROVISIONING                                                │    ║
║   │                                                                    │    ║
║   │  1. VeilPay creates isolated identity:                             │    ║
║   │     @treasurybot  (sub-profile of @maindao)                       │    ║
║   │                                                                    │    ║
║   │  2. Umbra SDK generates agent-specific keys:                       │    ║
║   │     agentSpendKey  → new keypair                                   │    ║
║   │     agentViewKey   → new keypair                                   │    ║
║   │     agentVault     → isolated encrypted balance container          │    ║
║   │                                                                    │    ║
║   │  3. User sets permissions:                                         │    ║
║   │     maxTxPerDay:   $50,000                                         │    ║
║   │     allowedTokens: [USDC, SOL]                                     │    ║
║   │     allowedActions:[swap, transfer, subscribe]                     │    ║
║   │     requireApproval: txns > $10,000                                │    ║
║   │     expiresAfter:  30 days                                         │    ║
║   └────────────────────────────┬───────────────────────────────────────┘    ║
║                                │                                             ║
║                                ▼                                             ║
║   ┌────────────────────────────────────────────────────────────────────┐    ║
║   │  AGENT RUNTIME — AUTONOMOUS OPERATION                              │    ║
║   │                                                                    │    ║
║   │  ┌──────────────────────────────────────────────────────────────┐ │    ║
║   │  │  AGENT DECISION ENGINE                                       │ │    ║
║   │  │                                                              │ │    ║
║   │  │  Input signals:                                              │ │    ║
║   │  │  ├── Market data feeds (price oracles)                       │ │    ║
║   │  │  ├── Treasury allocation thresholds (user-defined)           │ │    ║
║   │  │  ├── Subscription renewal schedules                          │ │    ║
║   │  │  ├── Payroll cycle calendar                                  │ │    ║
║   │  │  └── Incoming invoice queue                                  │ │    ║
║   │  │                                                              │ │    ║
║   │  │  Agent decides → Action → Permission check → Execute         │ │    ║
║   │  └──────────────────────────────┬───────────────────────────────┘ │    ║
║   │                                 │                                  │    ║
║   │                                 ▼                                  │    ║
║   │  ┌──────────────────────────────────────────────────────────────┐ │    ║
║   │  │  PRIVATE TRANSACTION EXECUTION                               │ │    ║
║   │  │                                                              │ │    ║
║   │  │  Agent uses its OWN GhostID stealth keys:                    │ │    ║
║   │  │                                                              │ │    ║
║   │  │  ├── Agent identity: @treasurybot                           │ │    ║
║   │  │  ├── Stealth send → API vendor (private)                    │ │    ║
║   │  │  ├── Amount encrypted → nobody knows spend                  │ │    ║
║   │  │  ├── Frequency hidden → strategy not leaked                 │ │    ║
║   │  │  └── Vault balance → invisible to front-runners             │ │    ║
║   │  └──────────────────────────────────────────────────────────────┘ │    ║
║   └────────────────────────────┬───────────────────────────────────────┘    ║
║                                │                                             ║
║                                ▼                                             ║
║   ┌────────────────────────────────────────────────────────────────────┐    ║
║   │  USER VISIBILITY (Owner sees everything; world sees nothing)       │    ║
║   │                                                                    │    ║
║   │  Owner Dashboard:                                                  │    ║
║   │  ├── Full agent activity log (decrypted with owner's view key)    │    ║
║   │  ├── Real-time spend tracking                                      │    ║
║   │  ├── Budget utilization                                            │    ║
║   │  └── Pause / terminate controls                                   │    ║
║   │                                                                    │    ║
║   │  On-chain (what observers see):                                   │    ║
║   │  ├── Encrypted state changes                                      │    ║
║   │  ├── No pattern linkage to owner                                  │    ║
║   │  └── No volume or frequency data                                  │    ║
║   └────────────────────────────────────────────────────────────────────┘    ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

**Available Agent Types:**

| Agent Type | Function | Privacy Benefit |
|-----------|----------|-----------------|
| **Treasury Bot** | Rebalances DAO/company treasury across assets | Competitors cannot see fund allocation strategy |
| **Payroll Agent** | Streams salaries to employees on schedule | Individual salaries invisible on-chain |
| **API Buyer** | Renews SaaS subscriptions automatically | Vendor stack hidden from competitors |
| **Invoice Collector** | Sends and follows up on invoices | Client list and revenue not exposed |
| **DCA Agent** | Dollar-cost averages into positions | Trade strategy hidden from front-runners |

---

### 6. Selective Compliance Engine

Privacy and compliance are not opposites. The Selective Compliance Engine is what makes VeilPay deployable in the real world — businesses can prove whatever regulators require without exposing everything.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      SELECTIVE COMPLIANCE ENGINE                            │
│                                                                             │
│                                                                             │
│   THE FUNDAMENTAL PROBLEM WITH OTHER PRIVACY SOLUTIONS:                     │
│                                                                             │
│   Option A:  Full transparency (normal crypto)                              │
│              → Everything visible                                           │
│              → Commercially unusable                                        │
│                                                                             │
│   Option B:  Full privacy (privacy coins like Monero)                       │
│              → Nothing visible                                              │
│              → Legally undeployable for businesses                          │
│                                                                             │
│   VeilPay Option C:  SELECTIVE DISCLOSURE                                   │
│              → Private by default                                           │
│              → Reveal only what is legally required                         │
│              → Cryptographically enforceable — cannot be expanded beyond    │
│                what the user explicitly authorized                           │
│                                                                             │
│                                                                             │
│   ═══════════════════════════════════════════════════════════════════════   │
│                                                                             │
│   HOW VIEWING KEYS WORK:                                                    │
│                                                                             │
│   USER has:  masterViewKey                                                  │
│       │                                                                     │
│       │  User wants to share tax info with accountant                       │
│       │                                                                     │
│       ▼                                                                     │
│   GENERATE scoped key:                                                      │
│       viewingKey = umbra.deriveViewingKey({                                 │
│           masterKey:    masterViewKey,                                      │
│           scope:        "income_only",          ◄── filters by category    │
│           dateFrom:     "2025-01-01",            ◄── time restriction      │
│           dateTo:       "2025-12-31",            ◄── time restriction      │
│           maxReveal:    "amounts_and_dates",     ◄── what can be seen      │
│           expiresAt:    blockHeight(2026-04-15)  ◄── auto-expires          │
│       })                                                                    │
│       │                                                                     │
│       ▼                                                                     │
│   SHARE key with accountant: vk_1qzp4m...f8x2                              │
│       │                                                                     │
│       ▼                                                                     │
│   ACCOUNTANT can see:                                                       │
│   ┌──────────────────────────────────────────────────────────────────────┐ │
│   │  Date        │  Amount    │  Category  │  Sender    │  Balance       │ │
│   │  ──────────  │  ────────  │  ────────  │  ────────  │  ─────────     │ │
│   │  2025-03-01  │  $12,500   │  Income    │  [HIDDEN]  │  [HIDDEN]      │ │
│   │  2025-03-15  │  $8,200    │  Income    │  [HIDDEN]  │  [HIDDEN]      │ │
│   │  2025-04-01  │  $15,000   │  Income    │  [HIDDEN]  │  [HIDDEN]      │ │
│   └──────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
│   ACCOUNTANT CANNOT see:                                                    │
│   ├── Outgoing payments                                                     │
│   ├── Wallet balance                                                        │
│   ├── Sender identities                                                     │
│   ├── Transactions outside the date range                                  │
│   └── Any other category of transaction                                    │
│                                                                             │
│                                                                             │
│   SUPPORTED DISCLOSURE SCOPES:                                              │
│   ─────────────────────────────────────────────────────────────────────   │
│                                                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐ │
│   │  Scope               │ Use Case              │ Audience             │ │
│   │  ────────────────    │ ─────────────────     │ ─────────────────   │ │
│   │  ANNUAL_TAX          │ Income reporting      │ Tax authority        │ │
│   │  PAYROLL_AUDIT       │ Employee pay records  │ Labor auditor        │ │
│   │  TREASURY_SNAPSHOT   │ Holdings at a date    │ Investor             │ │
│   │  INVOICE_VERIFY      │ Confirm 1 transaction │ Counterparty         │ │
│   │  INVESTOR_DISCLOSURE │ Fund composition      │ VC / LP              │ │
│   │  REGULATORY_INQUIRY  │ Custom legal scope    │ Regulator            │ │
│   │  PROOF_OF_FUNDS      │ Minimum balance proof │ Real estate / visa   │ │
│   └─────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

### 7. Multi-Profile Identity System

One of VeilPay's most powerful features is the ability for a single user to maintain multiple completely isolated financial identities — without managing multiple wallets, seed phrases, or accounts.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     MULTI-PROFILE IDENTITY SYSTEM                           │
│                                                                             │
│                                                                             │
│   SINGLE USER: Alex                                                         │
│   SINGLE MASTER KEY (one seed phrase, stored once)                         │
│        │                                                                    │
│        │  VeilPay derives isolated sub-profiles:                           │
│        │                                                                    │
│        ├──────────────────────────────────────────────────────────────┐    │
│        │                        @alex (Personal)                      │    │
│        │               ┌────────────────────────────────────────┐    │    │
│        │               │  Balance:    [encrypted]                │    │    │
│        │               │  History:    [isolated]                 │    │    │
│        │               │  Privacy:    Maximum                   │    │    │
│        │               │  Use case:   Personal payments, family  │    │    │
│        │               └────────────────────────────────────────┘    │    │
│        │                                                              │    │
│        ├──────────────────────────────────────────────────────────────┤    │
│        │                    @alexcorp (Business)                      │    │
│        │               ┌────────────────────────────────────────┐    │    │
│        │               │  Balance:    [encrypted, separate]      │    │    │
│        │               │  Payroll:    34 employees               │    │    │
│        │               │  Compliance: Accountant viewing key     │    │    │
│        │               │  Use case:   Business operations        │    │    │
│        │               └────────────────────────────────────────┘    │    │
│        │                                                              │    │
│        ├──────────────────────────────────────────────────────────────┤    │
│        │                      @alexdao (DAO)                          │    │
│        │               ┌────────────────────────────────────────┐    │    │
│        │               │  Balance:    [encrypted, treasury]      │    │    │
│        │               │  Governance: Multi-sig controls         │    │    │
│        │               │  Grants:     Private disbursement       │    │    │
│        │               │  Use case:   DAO treasury management    │    │    │
│        │               └────────────────────────────────────────┘    │    │
│        │                                                              │    │
│        ├──────────────────────────────────────────────────────────────┤    │
│        │                    @alexai (AI Agent)                        │    │
│        │               ┌────────────────────────────────────────┐    │    │
│        │               │  Budget:     $50K/month authorized      │    │    │
│        │               │  Actions:    Autonomous payments        │    │    │
│        │               │  Reporting:  Full visibility for owner  │    │    │
│        │               │  Use case:   Automated commerce         │    │    │
│        │               └────────────────────────────────────────┘    │    │
│        │                                                              │    │
│        └──────────────────────────────────────────────────────────────┘    │
│                                                                             │
│   KEY PROPERTIES:                                                           │
│   ├── Zero cross-contamination: Profile A cannot be linked to Profile B    │
│   ├── Single management UI: All profiles managed from one dashboard        │
│   ├── Independent vaults: Each profile has its own encrypted balance pool  │
│   ├── Independent compliance: Viewing keys are per-profile, not global     │
│   └── Independent history: Transactions are siloed per profile             │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## ✨ Core Features

### 🔐 Private Identity Vault
- Create human-readable `@GhostID` handles that replace wallet addresses
- Each GhostID routes to a cryptographically private stealth address system
- Multiple profiles per user (Personal, Business, DAO, AI Agent, Family)
- Non-custodial: private keys never leave your device

### 💸 Private Payments Infrastructure
- Send USDC privately — amount, sender, and receiver all shielded
- Encrypted payment memos (only readable by recipient)
- Payment links (`veilpay.app/pay/@yourname`) — shareable, wallet-unlinked
- Recurring and streaming payments with hidden amounts
- QR code support for in-person stealth transactions

### 🤖 AI Autonomous Finance Layer
- Deploy autonomous financial agents with spending permissions
- Private treasury bots, payroll agents, API buyers, invoice collectors
- Full owner visibility, zero external visibility
- Agent activity reporting via scoped viewing keys

### 🏢 Private Payroll System
- Pay unlimited employees — salary amounts invisible on-chain
- Contractor payouts with encrypted amounts
- Automated payroll scheduling
- Audit-ready reports via selective disclosure

### 📋 Selective Compliance Engine
- Generate scoped, time-limited cryptographic viewing keys
- Share only income, only payroll, only a single transaction — nothing else
- Keys expire automatically at a specified block height
- Zero-knowledge proof of payment (prove you paid, without revealing amount or parties)

### 🛒 Ghost Commerce SDK
- Private checkout integration for merchants
- Hidden subscription payments
- Encrypted invoicing system
- Creator tipping and monetization (private donation pages)
- Private API billing for AI-native applications

---

## 🎯 Use Cases

VeilPay is built for anyone who needs to participate in the digital economy without sacrificing the financial privacy they have always had with traditional banking.

---

### 👨‍💻 Freelancers & Solopreneurs

**Scenario:** Sarah is a full-stack developer who invoices clients in USDC. With a traditional wallet, every client she has ever worked with, every amount she has earned, and her total savings are permanently visible to anyone who finds her address — including future employers, ex-partners, tax authorities in other jurisdictions, and competitors.

**With VeilPay:**
- Sarah creates `@sarahdev` and shares it as her payment address everywhere
- Each client payment arrives via a fresh stealth address — they cannot see her other clients
- Her total balance is encrypted — nobody knows her net worth
- At tax time, she generates a viewing key scoped to income for the relevant year and shares it with her accountant

---

### 🏢 Businesses & Startups

**Scenario:** A 30-person startup pays its team in USDC. Competitors, journalists, and anyone who finds one employee's address can now calculate the entire payroll, identify every team member, and monitor the company's treasury movements in real time.

**With VeilPay:**
- The company creates `@startupxyz_payroll` as a business profile
- All 30 employees are added with their `@ghostid` handles
- Payroll runs on-chain — but salary amounts are encrypted per-employee
- The treasury dashboard shows the company its full picture
- On-chain observers see nothing useful
- The company's accountants get time-limited payroll viewing keys at year-end

---

### 🏛️ DAOs & Decentralized Organizations

**Scenario:** A DAO distributes grants to 50 contributors quarterly. Every grant amount, every recipient, and the DAO's total treasury is permanently public, creating political dynamics, targeted phishing attacks, and competitive intelligence leaks.

**With VeilPay:**
- DAO treasury operates under `@daoxyz_treasury`
- Grant distributions are made via private stealth payments
- Governance voting can still be public; financial execution is private
- The DAO can still publish aggregate totals (e.g., "We distributed $2M this quarter") without revealing individual grant amounts
- Multi-sig controls remain intact — privacy does not compromise governance

---

### 🤖 AI Agents & Autonomous Systems

**Scenario:** An AI agent is deployed to manage a DeFi treasury — buying compute, rebalancing assets, paying API subscriptions. With a public wallet, competitors can monitor every move, MEV bots can front-run every transaction, and the agent's entire strategy is exposed in real time.

**With VeilPay:**
- The AI agent operates from an isolated `@aiagent_treasury` profile
- Every outbound transaction uses a fresh stealth address
- Spending amounts are encrypted — MEV bots cannot observe the size
- Transaction frequency is unlinkable — strategy is hidden
- The owner has full visibility via owner-scoped viewing key
- Spending limits and multi-sig approval requirements are enforced at the protocol level

---

### 🎨 Creators & Content Platforms

**Scenario:** A YouTuber and Twitch streamer accepts USDC donations and paid subscriptions. Their wallet address shows exactly how much they earn, from how many people, at what frequency — exposing their livelihood to jealous peers, potential stalkers, and tax authorities in multiple jurisdictions.

**With VeilPay:**
- Creator publishes `veilpay.app/pay/@creator` on all their platforms
- Donors pay anonymously — the creator knows they received funds, not who from
- Monthly subscription payments are private — neither party's identity is linked
- Creator's total earnings are encrypted on-chain
- Tax reports are generated on demand via scoped annual viewing key

---

### 🌍 Global Remittances & Underbanked Populations

**Scenario:** A worker in one country sends money home regularly. In the current crypto paradigm, the transaction is permanently public — meaning the amount, frequency, and parties are visible to surveillance actors in authoritarian jurisdictions.

**With VeilPay:**
- Both sender and recipient operate under GhostIDs
- Transaction amounts are hidden on-chain
- The relationship between sender and receiver is unlinkable to external observers
- Fast Solana settlement (~400ms) with negligible fees (~$0.001)
- No bank account required — just a mobile device

---

### 🏥 Healthcare, Legal & Professional Services

**Scenario:** A therapist, lawyer, or doctor accepts stablecoin payments. Their clients' identity and transaction history with a healthcare or legal provider is sensitive information that should never be publicly traceable.

**With VeilPay:**
- Professional creates `@therapypractice` business profile
- Patient/client payments arrive via stealth addresses — permanently unlinkable
- Billing records are accessible to the professional only
- Insurance or legal compliance reports can be generated via scoped viewing keys
- Zero HIPAA / client confidentiality concerns

---

## 🧩 The Five Core Systems

VeilPay is organized around five deeply integrated core systems that together form a complete private financial OS:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                                                                             │
│   ┌─────────────────┐   ┌─────────────────┐   ┌──────────────────────┐    │
│   │   1. PRIVATE    │   │   2. PRIVATE    │   │  3. AI AUTONOMOUS    │    │
│   │    IDENTITY     │   │    PAYMENTS     │   │     FINANCE          │    │
│   │     VAULT       │   │ INFRASTRUCTURE  │   │      LAYER           │    │
│   │                 │   │                 │   │                      │    │
│   │  GhostIDs       │   │  Stealth sends  │   │  Treasury bots       │    │
│   │  Multi-profile  │   │  Hidden amounts │   │  Payroll agents      │    │
│   │  Encrypted      │   │  Private memos  │   │  API buyers          │    │
│   │  vaults         │   │  Recurring pay  │   │  Invoice collectors  │    │
│   └─────────────────┘   └─────────────────┘   └──────────────────────┘    │
│                                                                             │
│   ┌─────────────────────────────┐   ┌─────────────────────────────────┐    │
│   │   4. PRIVATE PAYROLL       │   │  5. SELECTIVE COMPLIANCE        │    │
│   │       SYSTEM               │   │        ENGINE                   │    │
│   │                            │   │                                 │    │
│   │  Employee management       │   │  Viewing key generation         │    │
│   │  Encrypted salaries        │   │  Scoped disclosure              │    │
│   │  Contractor payouts        │   │  Time-limited access            │    │
│   │  Automated scheduling      │   │  Tax & audit export             │    │
│   └─────────────────────────────┘   └─────────────────────────────────┘    │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🛠 Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend** | Next.js 14 (App Router) | Server-side rendering, routing |
| **Styling** | Tailwind CSS | Utility-first styling system |
| **Wallet** | Solana Wallet Adapter | Multi-wallet connection (Phantom, Backpack, etc.) |
| **Privacy Core** | Umbra SDK v3.2 | Stealth addresses, encrypted balances, viewing keys |
| **Blockchain** | Solana (Mainnet / Devnet) | Transaction settlement, program execution |
| **Stablecoin** | USDC (SPL Token) | Primary payment currency |
| **Payments** | Solana Pay + Streaming | Payment requests, streaming payroll |
| **AI Layer** | Custom orchestration engine | Autonomous agent decision-making |
| **Language** | TypeScript | Full-stack type safety |
| **Testing** | Jest + Anchor Test Suite | Unit and integration testing |

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

```bash
node >= 18.0.0
npm >= 9.0.0
git >= 2.30.0
```

You will also need:
- A Solana wallet (Phantom, Backpack, or any Solana Wallet Adapter-compatible wallet)
- Some SOL for transaction fees (devnet SOL is free — see below)
- The Umbra SDK credentials (see `.env.example`)

---

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/yourteam/veilpay.git
cd veilpay
```

**2. Install dependencies**

```bash
npm install
```

**3. Configure environment variables**

```bash
cp .env.example .env.local
```

Open `.env.local` and configure the following:

```env
# Solana Network
NEXT_PUBLIC_SOLANA_NETWORK=devnet
NEXT_PUBLIC_SOLANA_RPC_URL=https://api.devnet.solana.com

# Umbra SDK
NEXT_PUBLIC_UMBRA_API_KEY=your_umbra_api_key
NEXT_PUBLIC_UMBRA_REGISTRY_ADDRESS=your_registry_program_id

# VeilPay Registry (GhostID system)
NEXT_PUBLIC_GHOSTID_REGISTRY=your_ghostid_registry_address

# Optional: Analytics
NEXT_PUBLIC_ANALYTICS_ID=your_analytics_id
```

**4. Run database migrations (for off-chain registry)**

```bash
npm run db:migrate
```

**5. Start the development server**

```bash
npm run dev
```

The application will be running at `http://localhost:3000`.

---

### Getting Devnet SOL

To test on Solana devnet, you need free SOL for transaction fees:

```bash
# Using Solana CLI
solana airdrop 2 YOUR_WALLET_ADDRESS --url devnet

# Or visit: https://faucet.solana.com
```

---

### Getting Devnet USDC

For testing private payments with USDC on devnet:

```bash
# VeilPay includes a devnet USDC faucet
npm run faucet -- --wallet YOUR_WALLET_ADDRESS --amount 1000
```

---

### Running Tests

```bash
# Unit tests
npm run test

# Integration tests (requires running local validator)
npm run test:integration

# Umbra SDK integration tests
npm run test:umbra

# End-to-end tests (Playwright)
npm run test:e2e
```

---

### Building for Production

```bash
npm run build
npm run start
```

---

## 📁 Project Structure

```
veilpay/
├── app/                          # Next.js App Router
│   ├── (auth)/                   # Authentication routes
│   │   ├── onboarding/           # GhostID creation flow
│   │   └── connect/              # Wallet connection
│   ├── dashboard/                # Main application
│   │   ├── page.tsx              # Dashboard overview
│   │   ├── send/                 # Private payment flow
│   │   ├── agents/               # AI agent management
│   │   ├── payroll/              # Payroll system
│   │   └── compliance/           # Viewing key management
│   └── pay/
│       └── [ghostid]/            # Public payment pages
│
├── components/                   # Reusable UI components
│   ├── ui/                       # Base design system
│   ├── vault/                    # Vault components
│   ├── agents/                   # AI agent UI
│   └── charts/                   # Analytics visualizations
│
├── lib/                          # Core application logic
│   ├── umbra/                    # Umbra SDK integration
│   │   ├── stealth.ts            # Stealth address generation
│   │   ├── balances.ts           # Encrypted balance management
│   │   ├── viewing-keys.ts       # Viewing key system
│   │   └── nullifiers.ts         # Double-spend prevention
│   ├── ghostid/                  # GhostID system
│   │   ├── registry.ts           # On-chain registry interface
│   │   ├── resolver.ts           # Username → keys resolver
│   │   └── profiles.ts           # Multi-profile management
│   ├── agents/                   # AI agent system
│   │   ├── orchestrator.ts       # Agent decision engine
│   │   ├── executor.ts           # Transaction execution
│   │   └── permissions.ts        # Permission/limit checks
│   ├── payroll/                  # Payroll system
│   │   ├── scheduler.ts          # Payment scheduling
│   │   ├── employees.ts          # Employee management
│   │   └── reports.ts            # Compliance reports
│   └── compliance/               # Compliance engine
│       ├── viewing-keys.ts       # Key generation
│       └── disclosure.ts         # Selective disclosure
│
├── programs/                     # Solana on-chain programs (Anchor)
│   ├── veilpay-core/             # Core privacy program
│   ├── payroll/                  # Private payroll program
│   └── streaming/                # Payment streaming program
│
├── sdk/                          # Ghost Commerce SDK (for developers)
│   ├── checkout/                 # Private checkout components
│   ├── invoicing/                # Invoice system
│   └── subscriptions/            # Subscription management
│
└── tests/                        # Test suite
    ├── unit/
    ├── integration/
    └── e2e/
```

---

## 📡 API Reference

### GhostID Registry

```typescript
// Resolve a GhostID to cryptographic keys
const keys = await veilpay.ghostid.resolve("@alice");
// Returns: { spendKey: PublicKey, viewKey: PublicKey, profileType: string }

// Register a new GhostID
const identity = await veilpay.ghostid.register({
  username: "alice",
  profileType: "personal",  // personal | business | dao | ai | family
  wallet: connectedWallet
});

// Check availability
const available = await veilpay.ghostid.isAvailable("@alice");
```

### Private Payments

```typescript
// Send a private payment
const tx = await veilpay.send({
  to: "@alice",             // GhostID or public spend key
  amount: 500,              // Amount in USDC
  memo: "Invoice #42",      // Encrypted memo (optional)
  token: "USDC"
});

// Create a payment request link
const link = await veilpay.createPaymentLink({
  ghostId: "@alice",
  amount: 500,              // Optional: fix the amount
  memo: "Consulting fee"    // Optional: pre-fill memo
});
// Returns: "https://veilpay.app/pay/@alice?amount=500&memo=..."
```

### Vault Management

```typescript
// Get private balance (requires viewing key)
const balance = await veilpay.vault.getBalance({
  viewKey: myViewKey
});

// Scan for incoming payments
const payments = await veilpay.vault.scan({
  viewKey: myViewKey,
  fromBlock: lastScannedBlock
});
```

### Compliance

```typescript
// Generate a scoped viewing key
const viewingKey = await veilpay.compliance.generateViewingKey({
  masterViewKey: myMasterViewKey,
  scope: "ANNUAL_TAX",
  dateFrom: "2025-01-01",
  dateTo: "2025-12-31",
  expiresAtBlock: 350000000
});

// Generate a tax report
const report = await veilpay.compliance.generateTaxReport({
  viewingKey: viewingKey,
  format: "csv"  // csv | json | pdf
});
```

### AI Agents

```typescript
// Deploy an AI agent
const agent = await veilpay.agents.deploy({
  name: "Treasury Bot",
  type: "treasury",
  budget: {
    maxDaily: 50000,      // USD
    maxPerTx: 10000,
    requireApprovalAbove: 25000
  },
  allowedActions: ["transfer", "swap", "subscribe"],
  expiresAfter: 30  // days
});

// Get agent activity log
const activity = await veilpay.agents.getActivity({
  agentId: agent.id,
  ownerViewKey: myViewKey  // Required for decryption
});
```

---

## 🔒 Security Model

VeilPay's security rests on three pillars:

### 1. Non-Custodial Architecture
VeilPay never holds, sees, or stores your private keys. All cryptographic operations happen client-side on your device. Even if VeilPay's servers were completely compromised, your funds and private financial data would remain secure.

### 2. Cryptographic Privacy (Umbra SDK)
The privacy guarantees in VeilPay are not policy-based ("we promise not to look") — they are mathematically enforced. The Umbra SDK's stealth address system makes it computationally infeasible for any third party (including VeilPay) to link transactions to identities without the user's explicit cryptographic cooperation.

### 3. Selective and Auditable Trust
When users choose to share a viewing key for compliance, that disclosure is:
- **Scoped**: mathematically limited to what the user authorized
- **Time-limited**: automatically expires at the specified block height
- **Non-expandable**: the recipient cannot generate sub-keys or expand their access
- **Auditable**: the user can verify exactly what was disclosed

### Known Limitations & Trade-offs

| Limitation | Description |
|-----------|-------------|
| **Scanning latency** | Recipients must scan announcements to discover payments. VeilPay runs this automatically in the background, but there is inherent latency vs. direct transfers. |
| **Key management** | As with all non-custodial systems, losing your master key means losing access to your vault. VeilPay strongly recommends encrypted backup. |
| **Network fees** | Privacy operations are slightly more computationally expensive than plain transfers. Fees remain negligible on Solana (~$0.001) but are non-zero. |
| **Regulatory uncertainty** | Privacy technology exists in an evolving regulatory landscape. The selective compliance engine is designed to accommodate regulatory requirements, but users should understand their local legal context. |

---

## 🌐 Ecosystem & Bounties

VeilPay is funding the next generation of private finance infrastructure with a **$1.97M ecosystem fund**:

| Program | Pool | Description |
|---------|------|-------------|
| Enterprise Integration Program | $1,000,000 | Integrate VeilPay private payroll into HR software |
| AI Agent Challenge | $500,000 | Deploy autonomous AI financial agents via VeilPay |
| Privacy Commerce Grant | $250,000 | Build private e-commerce checkout with VeilPay SDK |
| Solana Privacy Accelerator | $100,000 | 3-month program for DeFi privacy primitives |
| Creator Economy Grant | $80,000 | Private monetization tools for creators |
| Developer Bounty Pool | $40,000 | Bug bounties, SDK improvements, documentation |

Apply at: [veilpay.app/ecosystem](https://veilpay.app/ecosystem)

---

## 🗺 Roadmap

### Phase 1 — Foundation ✅ (Current)
- [x] GhostID identity system
- [x] Private USDC transfers via Umbra SDK
- [x] Multi-profile vault management
- [x] Selective compliance engine
- [x] AI agent framework (v1)
- [x] Private payroll system

### Phase 2 — Ecosystem (Q3 2025)
- [ ] Ghost Commerce SDK public release
- [ ] Mobile app (iOS + Android)
- [ ] Multi-token support (SOL, USDT, EURC)
- [ ] AI agent marketplace
- [ ] Cross-chain privacy bridge (Ethereum)

### Phase 3 — Enterprise (Q4 2025)
- [ ] Enterprise API & white-label SDK
- [ ] FCA/FinCEN compliance module
- [ ] Institutional custody integration
- [ ] DAO treasury management suite
- [ ] Zero-knowledge proof of solvency

### Phase 4 — Global Scale (2026)
- [ ] 10M+ user infrastructure
- [ ] Private central bank digital currency (CBDC) integration
- [ ] AI-native financial OS licensing
- [ ] Global remittance corridors

---

## 👥 Team

VeilPay was built by a team with deep expertise in cryptography, fintech infrastructure, and AI systems, united by the belief that financial privacy is a fundamental human right — not a feature.

We are building VeilPay because we believe the next generation of global finance should be private by default, composable by design, and accessible to every human on the planet.

---

## 📄 License

VeilPay is released under the [MIT License](LICENSE).

The Umbra SDK is used under its respective license. See [Umbra SDK License](https://umbra.cash) for details.

---

<div align="center">

---

**VeilPay** · The Financial Operating System for the AI Economy

*Not a hackathon toy. The beginning of the next trillion-dollar financial network.*

**Built on Solana · Powered by Umbra SDK · USDC Native**

[Website](https://veilpay.app) · [Docs](https://docs.veilpay.app) · [Twitter](https://twitter.com/veilpay) · [Discord](https://discord.gg/veilpay)

---

</div>
