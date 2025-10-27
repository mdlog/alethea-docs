# Introduction

## What is Alethea Network?

**Alethea Network** is a decentralized oracle platform built on Linera blockchain that provides cryptographically secure truth verification for prediction markets and decentralized applications.

Named after the Greek goddess of truth (Ἀλήθεια), daughter of Zeus, Alethea embodies the principles of honesty, transparency, and immutable truth in the Web3 world.

## The Problem

Traditional prediction markets and oracles face critical challenges:

* 🔴 **Centralization Risk** - Single points of failure
* 🔴 **Trust Dependencies** - Reliance on third parties
* 🔴 **Front-Running** - Coordinated attacks on voting
* 🔴 **Manipulation** - Dishonest oracle reporting
* 🔴 **High Costs** - Expensive external oracle services

## Our Solution

Alethea Network solves these problems through:

### ✅ Commit-Reveal Cryptography

Voters submit encrypted votes first (commit phase), then reveal them later. This prevents:
- Front-running attacks
- Coordination between voters
- Manipulation of consensus

### ✅ Reputation System

Long-term accuracy tracking incentivizes honest behavior:
- Streak bonuses for consecutive correct votes
- Confidence-weighted voting power
- Reputation decay for bad actors

### ✅ Decentralized Architecture

Built on Linera's mikrochains:
- No single point of failure
- Native cross-chain messaging
- Fast, scalable consensus

### ✅ Automated Market Maker

Dynamic pricing for prediction markets:
- Liquidity pools for each outcome
- Price discovery through trading
- Fair, transparent pricing

## Key Features

| Feature | Description |
|---------|-------------|
| **Commit-Reveal Voting** | SHA-256 cryptographic commitments prevent front-running |
| **Reputation Tracking** | Long-term accuracy scores with streak bonuses |
| **AMM Markets** | Automated market maker for prediction market pricing |
| **Cross-Chain Ready** | Native Linera cross-chain message passing |
| **GraphQL API** | Modern, developer-friendly interface |
| **WASM Contracts** | Deterministic execution on Linera |

## Architecture Overview

Alethea Network consists of two main smart contracts:

```
┌─────────────────────────────────────────────────┐
│                                                 │
│  ┌──────────────────┐   ┌──────────────────┐  │
│  │  MARKET CHAIN    │   │  VOTER CHAIN     │  │
│  │                  │   │                  │  │
│  │  • AMM Trading   │◄─►│  • Commit Vote   │  │
│  │  • Liquidity     │   │  • Reveal Vote   │  │
│  │  • Positions     │   │  • Reputation    │  │
│  │  • Payouts       │   │  • Consensus     │  │
│  └──────────────────┘   └──────────────────┘  │
│                                                 │
│         Built on Linera Blockchain             │
│                                                 │
└─────────────────────────────────────────────────┘
```

### Market Chain

Handles all trading operations:
- Market creation with initial liquidity
- Buy/sell shares (AMM-based pricing)
- Position tracking
- Payout distribution after resolution

### Voter Chain

Provides decentralized oracle:
- Voter registration with stake requirement
- Commit-reveal voting mechanism
- Reputation system management
- Consensus determination

## Quick Stats

- **Status:** ✅ Deployed & Operational
- **Blockchain:** Linera v0.15.4
- **Language:** Rust + WASM
- **API:** GraphQL
- **Active Markets:** 2
- **Total Liquidity:** 3M tokens

## Use Cases

Alethea Network enables:

* 📊 **Prediction Markets** - Bitcoin price, election outcomes
* 🏆 **Sports Betting** - Trustless sports results verification
* 🛡️ **Insurance** - Parametric insurance claims resolution
* 💱 **DeFi Oracles** - Price feeds, data verification
* 🗳️ **Governance** - DAO proposal outcomes

## Why Choose Alethea?

| Aspect | Traditional Oracles | Alethea Network |
|--------|-------------------|-----------------|
| **Decentralization** | Centralized or semi-centralized | Fully decentralized |
| **Security** | Trust-based | Cryptographic proof |
| **Front-Running** | Vulnerable | Impossible (commit-reveal) |
| **Cost** | High ($10-100 per query) | Low (blockchain fees only) |
| **Speed** | Hours-days | Minutes-hours |
| **Transparency** | Limited | Full on-chain transparency |

## Next Steps

Ready to get started?

{% content-ref url="installation.md" %}
[installation.md](installation.md)
{% endcontent-ref %}

{% content-ref url="quick-start.md" %}
[quick-start.md](quick-start.md)
{% endcontent-ref %}

---

**Alethea Network** - Divine Truth for Modern Markets 🏛️

