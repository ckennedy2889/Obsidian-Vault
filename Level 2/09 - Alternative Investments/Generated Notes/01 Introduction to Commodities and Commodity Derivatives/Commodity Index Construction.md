---
title: "Commodity Index Construction"
subject: "Alternative Investments"
tags: [CFA-L2, alternative-investments, commodities, futures, indexes]
aliases:
  - Commodity indexes
  - Commodity index returns
  - Roll schedule
  - Collateral return
---

# Commodity Index Construction

Commodity indexes do not usually hold physical commodities. They are built from fully collateralized futures positions. That means index design choices, such as sector weights and roll rules, can materially change returns even when the underlying spot commodity prices are similar.

The core exam idea is: **commodity index return is not just spot price return.**

## Components of Commodity Futures Index Return

A fully collateralized commodity futures position has three return components:

$$
\text{Total return} = \text{Price return} + \text{Roll return} + \text{Collateral return}
$$

| Component | Meaning |
|---|---|
| Price return | Change in futures price or spot-related exposure |
| Roll return | Gain or loss from replacing expiring contracts with later contracts |
| Collateral return | Interest earned on collateral, often proxied by T-bills |

Because futures require margin rather than full cash payment, a fully collateralized index assumes the notional exposure is backed by cash or short-term securities.

## Roll Return

Commodity indexes must roll contracts before expiration to maintain exposure.

### Contango

In [[contango]], longer-dated futures prices are higher than near-term futures prices.

Rolling means:

1. Sell the cheaper expiring contract.
2. Buy the more expensive later contract.
3. End up with fewer contracts for the same notional exposure.

This creates negative roll return.

### Backwardation

In [[backwardation]], longer-dated futures prices are lower than near-term futures prices.

Rolling means:

1. Sell the more expensive expiring contract.
2. Buy the cheaper later contract.
3. End up with more contracts for the same notional exposure.

This creates positive roll return.

## Index Design Choices

| Design choice | Why it matters |
|---|---|
| Commodity universe | Determines breadth and diversification |
| Sector weights | Controls exposure to energy, metals, agriculture, livestock, etc. |
| Contract selection | Determines liquidity and curve exposure |
| Roll schedule | Determines timing and roll yield sensitivity |
| Rebalancing frequency | Affects performance in trending vs mean-reverting markets |
| Collateral assumption | Affects total return through short-term interest rates |
| Liquidity screens | Determines whether the index is investable |

## Sector Weighting

Commodity indexes can look diversified by contract count but still be concentrated by weight.

Common weighting approaches:

| Approach | Implication |
|---|---|
| Production-value weighted | Heavier weights in commodities with large global production value, often energy-heavy |
| Liquidity weighted | Favors heavily traded contracts |
| Capped sector weights | Prevents one sector, such as energy, from dominating |
| Fixed weights | Committee or rules set target allocations |

Exam trap: do not assume all broad commodity indexes have similar risk. An energy-heavy index will respond much more to oil shocks than a capped, diversified index.

## Contract Selection and Roll Methodology

Some indexes roll front-month contracts mechanically. Others choose contracts farther out on the curve to reduce negative roll yield or capture backwardation.

| Roll design | Effect |
|---|---|
| Front-month roll | High sensitivity to near-term futures curve shape |
| Deferred-contract roll | May reduce volatility or negative roll yield |
| Optimized roll | Attempts to maximize backwardation or minimize contango |

An optimized roll can improve return in persistent contango, but it may reduce transparency and increase implementation complexity.

## Rebalancing

Rebalancing restores target weights after price movements.

| Market behavior | Frequent rebalancing effect |
|---|---|
| Mean reversion | Can help by selling winners and buying losers |
| Trending markets | Can hurt by selling winners too early |

If oil trends upward for several months, an index with frequent rebalancing may sell oil exposure along the way, reducing participation in the trend.

## Investability

A commodity index is investable if market participants can realistically replicate it.

Investability depends on:

- Liquid futures contracts.
- Accessible exchanges.
- Reasonable transaction costs.
- Transparent rules.
- Manageable roll windows.
- Capacity relative to contract open interest.

An index that includes illiquid or obscure contracts may be less useful as a benchmark for actual investment products.

## Worked Roll Example

An index has \$1,000,000 exposure to a near-term copper futures contract priced at \$4.00. It holds:

$$
\frac{1{,}000{,}000}{4.00}=250{,}000
$$

contract units.

### Contango

The next contract costs \$4.20.

To maintain \$1,000,000 exposure:

$$
\frac{1{,}000{,}000}{4.20}=238{,}095
$$

units.

The index buys fewer units. The roll return is negative because it sells cheaper and buys more expensive.

### Backwardation

The next contract costs \$3.80.

To maintain \$1,000,000 exposure:

$$
\frac{1{,}000{,}000}{3.80}=263{,}158
$$

units.

The index buys more units. The roll return is positive because it sells more expensive and buys cheaper.

## Exam Traps

- **Contango creates negative roll return, not automatically negative total return.** Spot price return and collateral return can offset it.
- **Backwardation creates positive roll return, not automatically positive total return.**
- **In contango, the roll buys fewer contracts.** In backwardation, it buys more.
- **Index weights matter.** Broad commodity indexes can have very different energy exposure.
- **Rebalancing can help mean reversion and hurt trends.**
- **Front-month indexes are more exposed to near-term curve shape.**
- **Investable indexes need liquid, replicable contracts.**

## Memory Hook

**Commodity indexes are rules plus futures curves. The rules pick the exposure; the curve determines the roll.**
