# Welcome to Alethea Network

```
    ◉─────◉
     ╲   ╱      ALETHEA NETWORK
      ◉─◉       Divine Truth for Modern Markets
```

> **Decentralized Oracle Platform on Linera Blockchain**

Alethea Network brings cryptographic truth verification to prediction markets and DeFi applications through commit-reveal voting and reputation-based consensus.

## 📚 What You'll Find Here

This documentation covers the fundamentals of Alethea Network:

* **Introduction** - What is Alethea and why it matters
* **Core Technology** - Greek goddess of truth meets blockchain
* **Key Concepts** - Architecture, voting, reputation, and economics

## 🎯 Quick Links

{% content-ref url="getting-started/introduction.md" %}
[introduction.md](getting-started/introduction.md)
{% endcontent-ref %}

{% content-ref url="getting-started/what-is-alethea.md" %}
[what-is-alethea.md](getting-started/what-is-alethea.md)
{% endcontent-ref %}

{% content-ref url="getting-started/key-concepts.md" %}
[key-concepts.md](getting-started/key-concepts.md)
{% endcontent-ref %}

## 🌟 Key Features

* **Commit-Reveal Voting** - Cryptographically secure, front-running proof
* **Reputation System** - Long-term accuracy tracking and incentives
* **AMM Markets** - Automated market maker for price discovery
* **Cross-Chain Ready** - Native Linera cross-chain messaging
* **GraphQL API** - Modern, developer-friendly interface

## 🌐 Live on Conway Testnet!

**Status**: ✅ **DEPLOYED & OPERATIONAL**

* **Network**: Linera Conway Testnet (Public)
* **Chain ID**: `8550ef0e...bd16`
* **Validators**: 14 active
* **Min Stake**: 1 token (testnet friendly!)

## 🚀 Quick Example

```graphql
mutation {
  createMarket(
    question: "Will Bitcoin reach $100k by Dec 31, 2025?"
    outcomes: ["Yes", "No"]
    resolutionDeadline: 1735689600000000
    initialLiquidity: "1000000"
  )
}
```

**Try it live**: [GraphiQL IDE](http://localhost:8080)

## 💡 Why Alethea?

Named after the Greek goddess of truth (Ἀλήθεια), daughter of Zeus, Alethea Network embodies the principles of honesty, transparency, and immutable truth in the blockchain world.

## 📊 Current Deployment

**Network**: 🌐 **Conway Testnet** (Public)  
**Status**: ✅ LIVE & OPERATIONAL  
**Chain ID**: `8550ef0ecb1ee0289b94c88d5bdec0183e5c3667d473ab1cedcf19f56ad6bd16`

**Applications**:
* Market Chain: `dbdd3588...96b` ✅ INTEGRATED
* Voter Chain: `333197de...bc40` ✅ (min_stake: 1, voting operational!)
* Oracle Coordinator: `d6e3e0e8...209` ✅ INTEGRATED

**Stats**:
* Validators: 14 active
* Block Height: 75
* Block Hash: `2aac5f8613064c5b67b69f6a66128509ba9a4bd0e3fbd308fe2dbd5efac01880`
* Markets: Deployment reset for integration testing
* Integration: ✅ FULLY INTEGRATED (Market ↔ Oracle ↔ Voter)
* Last Updated: Oct 28, 2025 12:19 UTC

## 🤝 Community

* [GitHub](https://github.com/alethea-network)
* [Discord](https://discord.gg/alethea)
* [Twitter](https://twitter.com/AletheaNetwork)
* [Telegram](https://t.me/aletheanetwork)

---

**Ready to start?** Head over to [Getting Started](getting-started/introduction.md) →

