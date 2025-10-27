# Key Concepts

Before diving into Alethea Network, it's important to understand the core concepts that make our decentralized oracle platform work.

## 🏗️ Architecture Overview

Alethea Network is built on **two independent smart contracts** that work together:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  ┌──────────────────┐          ┌──────────────────┐       │
│  │  MARKET CHAIN    │◄────────►│  VOTER CHAIN     │       │
│  │                  │  Cross-  │                  │       │
│  │  Trading Layer   │  Chain   │  Oracle Layer    │       │
│  │                  │  Message │                  │       │
│  └──────────────────┘          └──────────────────┘       │
│                                                             │
│            Built on Linera Mikrochains                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## 🎯 Core Components

### 1. Market Chain

The **Market Chain** handles all trading operations:

**Purpose:**
- Create prediction markets
- Manage liquidity pools
- Enable buying/selling shares
- Track user positions
- Calculate and distribute payouts

**Key Features:**
- ✅ Automated Market Maker (AMM) pricing
- ✅ Multi-outcome support
- ✅ Position tracking per user
- ✅ Fair payout calculation
- ✅ Market lifecycle management

**Market States:**
```
Open → Trading Active → Pending Resolution → Resolved → Payouts
```

### 2. Voter Chain

The **Voter Chain** provides decentralized oracle:

**Purpose:**
- Register voters with stake requirement
- Accept vote commitments (encrypted)
- Process vote reveals (verification)
- Calculate consensus
- Manage voter reputation

**Key Features:**
- ✅ Commit-reveal voting mechanism
- ✅ Cryptographic vote security
- ✅ Reputation system
- ✅ Stake-based participation
- ✅ Automated consensus

**Voting Flow:**
```
Register → Commit (secret) → Reveal (verify) → Consensus → Reward
```

## 🔐 Commit-Reveal Voting

The **commit-reveal** scheme is central to Alethea's security:

### Phase 1: Commit (Secret)

```rust
// Voter submits hash of vote + salt
vote_hash = SHA256(vote + salt)
// Hash stored on-chain, vote stays secret
```

**Why it matters:**
- Nobody can see your actual vote
- Prevents copying other voters
- Eliminates front-running
- Ensures independent voting

### Phase 2: Reveal (Verify)

```rust
// Voter reveals actual vote + salt
revealed_vote = "Yes"
revealed_salt = "abc123..."

// Contract verifies:
if SHA256(revealed_vote + revealed_salt) == stored_hash {
    vote_accepted = true
}
```

**Why it matters:**
- Cryptographic proof of commitment
- Impossible to change vote after commit
- Transparent verification
- Fair consensus

## 📊 Reputation System

Voters build **long-term reputation** based on accuracy:

### How It Works

```
Correct Vote → Reputation +10 points
Incorrect Vote → Reputation -5 points
Streak Bonus → +2 points per consecutive correct vote
```

### Benefits

**For Voters:**
- ✅ Higher voting power over time
- ✅ Increased rewards
- ✅ Unlock premium features
- ✅ Build credibility

**For Markets:**
- ✅ Attracts quality voters
- ✅ Improves accuracy
- ✅ Deters bad actors
- ✅ Long-term incentive alignment

### Reputation Levels

| Level | Points | Benefits |
|-------|--------|----------|
| Novice | 0-100 | Standard voting power |
| Trusted | 100-500 | 1.2x voting weight |
| Expert | 500-1000 | 1.5x voting weight |
| Oracle | 1000+ | 2x voting weight |

## 💰 Automated Market Maker (AMM)

The AMM provides **dynamic pricing** for prediction market shares:

### How AMM Works

**Liquidity Pools:**
```
Market: "Bitcoin > $100k?"
Pool A (Yes): 100,000 tokens
Pool B (No): 100,000 tokens
```

**Price Calculation:**
```
Price_Yes = Pool_Yes / (Pool_Yes + Pool_No)
Price_No = Pool_No / (Pool_Yes + Pool_No)
```

**Example:**
```
Initial: Yes = 50%, No = 50%

After buying "Yes":
Pool_Yes = 80,000 (↓)
Pool_No = 120,000 (↑)

New Price:
Yes = 40% (cheaper)
No = 60% (more expensive)
```

### Why AMM?

- ✅ **Always Liquid** - Can always buy/sell
- ✅ **Fair Pricing** - Supply and demand
- ✅ **No Order Books** - Automatic execution
- ✅ **Transparent** - All on-chain

## 🔗 Cross-Chain Messaging

Alethea uses **Linera's native cross-chain** communication:

### How It Works

```
1. Market Chain → "Need resolution for Market #5"
   ↓
2. Message sent to Voter Chain
   ↓
3. Voter Chain → Voting process
   ↓
4. Consensus reached
   ↓
5. Voter Chain → "Market #5: Winner is 'Yes'"
   ↓
6. Market Chain → Distribute payouts
```

### Benefits

- ✅ **No Bridges** - Native protocol support
- ✅ **Fast** - Sub-second messaging
- ✅ **Secure** - No external dependencies
- ✅ **Atomic** - Either all succeed or all fail

## 🛡️ Security Model

Alethea's security comes from **multiple layers**:

### 1. Cryptographic Security
- SHA-256 hashing
- Commit-reveal scheme
- Digital signatures

### 2. Economic Security
- Voter stake requirement (100k+ tokens)
- Reputation at risk
- Slashing for bad behavior

### 3. Consensus Security
- Majority voting (51%+)
- Multiple independent voters
- Byzantine Fault Tolerance ready

### 4. Smart Contract Security
- Rust memory safety
- WASM deterministic execution
- Formal verification ready

## 💎 Token Economics

### Stake Requirements

**Voters:**
```
Minimum Stake: 100,000 tokens
Purpose: Skin in the game
Unlocked: After voting period
```

**Market Creators:**
```
Initial Liquidity: 10,000+ tokens
Purpose: Bootstrap AMM
Returns: When market closes + trading fees
```

### Fee Structure

```
Trading Fee: 0.3% per trade
Market Creation: 1000 tokens
Oracle Request: 500 tokens

Fee Distribution:
- 50% to liquidity providers
- 30% to voters
- 20% to protocol treasury
```

## 📈 Market Lifecycle

### 1. Creation
```
Creator provides:
- Question
- Outcomes (e.g., Yes/No)
- Resolution deadline
- Initial liquidity
```

### 2. Trading
```
Users:
- Buy shares
- Sell shares
- Provide liquidity
- Monitor prices
```

### 3. Resolution Request
```
Deadline reached:
- Market locks trading
- Request sent to Voter Chain
- Voters have 24h to vote
```

### 4. Voting
```
Phase 1 (12h): Commit votes
Phase 2 (12h): Reveal votes
Consensus: Majority wins
```

### 5. Payout
```
Winning shares: 1 token each
Losing shares: 0 tokens
Liquidity: Returned to providers
```

## 🎮 User Roles

### Trader
- Buy/sell market shares
- Speculate on outcomes
- Profit from price movements

### Liquidity Provider
- Add liquidity to pools
- Earn trading fees
- Help market efficiency

### Voter
- Stake tokens
- Vote on outcomes
- Earn rewards
- Build reputation

### Market Creator
- Define markets
- Provide initial liquidity
- Earn fees on trading volume

## 🔄 Data Flow

Complete data flow in Alethea Network:

```
1. User creates market on Market Chain
   ↓
2. Other users trade shares (AMM pricing)
   ↓
3. Deadline reached → Market locks
   ↓
4. Market Chain sends resolution request to Voter Chain
   ↓
5. Voters commit encrypted votes
   ↓
6. Voters reveal votes (verification)
   ↓
7. Voter Chain calculates consensus
   ↓
8. Result sent back to Market Chain
   ↓
9. Market Chain distributes payouts
   ↓
10. Voters receive reputation + rewards
```

## 🌟 Why These Concepts Matter

Understanding these concepts helps you:

1. **Trade Effectively** - Know how prices work
2. **Vote Accurately** - Understand the process
3. **Build Integrations** - Use the right APIs
4. **Trust the System** - See the security guarantees

## Next Steps

Now that you understand the key concepts:

{% content-ref url="installation.md" %}
[installation.md](installation.md)
{% endcontent-ref %}

{% content-ref url="../core-concepts/architecture.md" %}
[architecture.md](../core-concepts/architecture.md)
{% endcontent-ref %}

---

**Alethea Network** - Where Truth Meets Technology 🏛️

