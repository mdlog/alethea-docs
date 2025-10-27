# 🏛️ Welcome to Alethea Network

> **Divine Truth for Modern Markets**

Alethea Network is a decentralized oracle platform built on Linera blockchain that brings cryptographic truth verification to prediction markets and DeFi applications.

## 📚 What You'll Find Here

This documentation covers everything you need to know about Alethea Network:

* **Getting Started** - Quick setup and first steps
* **Core Concepts** - Understanding how Alethea works
* **Developer Guide** - Building with Alethea
* **API Reference** - Complete GraphQL API documentation
* **Integration Guide** - Connect your DApp to Alethea
* **Deployment** - Running your own oracle node

## 🎯 Quick Links

{% content-ref url="getting-started/introduction.md" %}
[introduction.md](getting-started/introduction.md)
{% endcontent-ref %}

{% content-ref url="core-concepts/architecture.md" %}
[architecture.md](core-concepts/architecture.md)
{% endcontent-ref %}

{% content-ref url="developer-guide/quickstart.md" %}
[quickstart.md](developer-guide/quickstart.md)
{% endcontent-ref %}

## 🌟 Key Features

* **Commit-Reveal Voting** - Cryptographically secure, front-running proof
* **Reputation System** - Long-term accuracy tracking and incentives
* **AMM Markets** - Automated market maker for price discovery
* **Cross-Chain Ready** - Native Linera cross-chain messaging
* **GraphQL API** - Modern, developer-friendly interface

## 🚀 Quick Example

```graphql
mutation {
  createMarket(
    question: "Will Bitcoin reach $100k by Dec 31, 2025?"
    outcomes: ["Yes", "No"]
    resolutionDeadline: 1735689600000000
    initialLiquidity: 1000000
  )
}
```

## 💡 Why Alethea?

Named after the Greek goddess of truth (Ἀλήθεια), daughter of Zeus, Alethea Network embodies the principles of honesty, transparency, and immutable truth in the blockchain world.

## 🤝 Community

* [GitHub](https://github.com/alethea-network)
* [Discord](https://discord.gg/alethea)
* [Twitter](https://twitter.com/AletheaNetwork)
* [Telegram](https://t.me/aletheanetwork)

---

**Ready to start?** Head over to [Getting Started](getting-started/introduction.md) →

