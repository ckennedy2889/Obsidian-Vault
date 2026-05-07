---
title: Theories of Commodity Futures Returns
subject: Alternative Investments
tags:
  - CFA-L2
  - alternative-investments
  - commodities
  - futures
  - backwardation
  - contango
  - convenience-yield
  - insurance-theory
  - hedging-pressure
  - theory-of-storage
aliases:
  - insurance theory
  - normal backwardation theory
  - hedging pressure hypothesis
  - theory of storage
  - cost of carry model
  - commodity futures return theories
---

# Theories of Commodity Futures Returns

## The Real-World Analogy

Three different economists looked at commodity markets and asked the same question from different angles: "Why do futures prices differ from expected future spot prices, and who gets compensated for taking risk?"

Keynes thought it was all about producers buying insurance by selling futures cheap. Others thought it depended on which side of the market — producers or consumers — needed more protection. The most mechanical thinkers said: forget about who needs protection, just calculate the cost of physically storing the commodity and you'll have the answer.

These three perspectives are not mutually exclusive — they each capture a real force. Together, they explain why some commodity markets persistently trade in contango, others in backwardation, and why the shape can change with inventory levels and market participant composition.

## Plain-English Definition

The three main theories explain the **relationship between futures prices and expected future spot prices** in commodity markets, and what drives the roll return earned (or paid) by investors holding long futures positions.

---

## Why CFA Tests This

The LOS states: *"Compare theories of commodity futures returns."*

The exam tests:
- The name, premise, and implication of each theory
- Which market condition (contango or backwardation) each theory predicts
- The role of convenience yield in the theory of storage
- Critiques of each theory

---

## Overview: Three Theories

| Theory | Who Proposed | Key Variable | Predicts |
|---|---|---|---|
| Insurance Theory | Keynes | Producer hedging pressure | Normal backwardation (long investors earn a premium) |
| Hedging Pressure Hypothesis | Cootner, Hicks | Balance of producer vs. consumer hedging | Depends on which side dominates |
| Theory of Storage | Working, Kaldor | Storage costs, convenience yield | Contango when storage costs > convenience yield; backwardation when opposite |

---

## Theory 1: Insurance Theory (Normal Backwardation — Keynes)

### The Premise

Commodity producers (oil companies, wheat farmers, copper miners) are naturally long the physical good. They face price risk — if prices fall, their revenues fall. To manage this risk, they **sell futures contracts** to lock in future selling prices.

### The Mechanism

1. Producers persistently sell futures → supply pressure pushes futures prices down
2. Futures prices trade below the expected future spot price: $F_0 < E(S_T)$
3. Speculators go long (buy futures) to absorb this selling pressure
4. Speculators require compensation for bearing this risk → they buy at a discount to expected spot
5. As delivery approaches, futures prices converge upward to spot → long speculator profits

**The premium earned by the long speculator = futures price discount to expected spot price**

This discount is the "insurance premium" paid by the producer to the speculator.

### Forward Curve Implication

The futures curve is in **backwardation** — futures prices trade below spot (and below expected future spot):

$$F_0 < E(S_T) \quad \text{(normal backwardation condition)}$$

### Roll Return Implication

Because futures prices must converge upward toward spot, long investors earn a **positive roll return** in this framework.

### Critique

- Historical evidence does NOT consistently show backwardation is "normal"
- Many commodity markets (especially energy) spend extended periods in contango
- The theory ignores the role of consumers who may also use futures to hedge
- The risk premium paid to speculators is not reliably positive across all commodities

---

## Theory 2: Hedging Pressure Hypothesis

### The Premise

This is an extension of Keynes. It recognizes that *both* producers **and** consumers/end-users hedge using futures:

- **Producers** (naturally long) want to **sell** futures to lock in prices
- **Consumers** (e.g., airlines needing jet fuel, food manufacturers needing grain) are naturally short the commodity and want to **buy** futures to lock in prices

### The Mechanism

The forward curve shape reflects the **net hedging pressure** — which side of the market needs more protection:

| Hedging Balance | Direction | Forward Curve | Roll Return |
|---|---|---|---|
| Producer hedging > Consumer hedging | Net selling pressure | **Backwardation** | Positive |
| Consumer hedging > Producer hedging | Net buying pressure | **Contango** | Negative |
| Producer hedging = Consumer hedging | Balanced | **Flat** | Zero |

### Why This Matters

In **agricultural markets**, farmers persistently need to sell their harvests forward → producer hedging dominates → backwardation is more common.

In **industrial metals**, manufacturers that need copper, aluminum etc. to maintain production may buy forward aggressively → consumer hedging can dominate → contango possible.

In **energy**, the balance shifts: sometimes oil companies dominate with selling (backwardation), sometimes airlines dominate with buying (contango).

### Critique

- Extremely difficult to measure net hedging pressure in practice — the data isn't readily observable
- Producers are often more concentrated and better organized to hedge than diffuse consumers
- Market composition can shift rapidly with new entrants

---

## Theory 3: Theory of Storage (Cost of Carry Model)

### The Premise

Futures prices are mechanically determined by the economics of physically storing the commodity. This is the most quantitative and operationally grounded theory.

### The Mechanism

$$\boxed{F \approx S \cdot (1 + r + c - i)}$$

Where:
| Symbol | Meaning |
|---|---|
| $S$ | Current spot price |
| $r$ | Risk-free rate (opportunity cost of capital) |
| $c$ | Storage costs (warehousing, insurance, spoilage) |
| $i$ | Convenience yield (non-monetary benefit of physical ownership) |

The **net cost of carry** = $r + c - i$:

| Net Cost of Carry | Forward Curve | Market Condition |
|---|---|---|
| $r + c > i$ | $F > S$ (upward sloping) | **Contango** |
| $r + c < i$ | $F < S$ (downward sloping) | **Backwardation** |
| $r + c = i$ | $F = S$ (flat) | Neither |

### The Deep Concept: Convenience Yield

Convenience yield is the non-monetary benefit that accrues to whoever holds the *physical* commodity (rather than a futures contract). It arises from:

- Ensuring continuous production: a refinery holding physical oil can keep running even if supply chains are disrupted
- Maintaining optionality: physical holders can respond to unexpected demand spikes immediately
- Avoiding supply-chain disruption costs

**The critical relationship:**

$$\text{Convenience yield} \propto \frac{1}{\text{Inventory}}$$

- **When inventories are low:** Convenience yield is high (scarcity creates scramble for physical) → $i > r + c$ → backwardation
- **When inventories are high:** Convenience yield is low (plenty of stock, no urgency) → $r + c > i$ → contango

```
Inventory  →  Convenience Yield  →  Market Condition
  Low      →       High           →   Backwardation
  High     →       Low            →   Contango
```

### Roll Return Implication

- Storage theory explains *why* markets are in contango or backwardation
- It does not directly predict whether long investors earn a risk premium
- Roll return is positive in backwardation (when convenience yield > carrying costs) and negative in contango

### Critique

- Storage costs and convenience yields are often unobservable or proprietary
- The model assumes no frictions and continuous arbitrage
- Doesn't explain *who* earns the risk premium — just the price relationship

---

## Comparing the Three Theories

| | Insurance Theory | Hedging Pressure | Theory of Storage |
|---|---|---|---|
| **Focus** | Producer supply of risk | Relative hedging demands | Physical storage economics |
| **Key variable** | Producer hedging | Producer vs. consumer balance | Storage cost vs. convenience yield |
| **Predicts backwardation when** | Producers dominate | Producers > consumers | Convenience yield > storage costs |
| **Predicts contango when** | Theory doesn't directly address | Consumers > producers | Storage costs > convenience yield |
| **Roll return** | Positive (normal backwardation) | Depends on balance | Positive in backwrdation, negative in contango |
| **Testable?** | Partially (Keynes' prediction often fails) | Difficult (need to measure hedging) | Yes (via forward curve shape and inventory data) |
| **Most mechanistic** | No | No | **Yes** |

---

## The Connection to Total Return

All three theories connect to the roll return component of the [[Commodity Futures Total Return|total return framework]]:

$$\text{Total Return} = \text{Price Return} + \underbrace{\text{Roll Return}}_{\text{Explained by these theories}} + \text{Collateral Return}$$

- Insurance theory: roll return positive because futures are set below expected spot
- Hedging pressure: roll return depends on which side dominates
- Theory of storage: roll return determined by net cost of carry (storage − convenience yield)

---

## Exam Traps

> [!danger] Key Exam Traps

| Trap | Correct Understanding |
|---|---|
| "Normal backwardation" = markets are usually in backwardation | "Normal" means this is Keynes' *theoretical* baseline — empirically, many markets are persistently in contango |
| Insurance theory = theory of storage | They are different: insurance theory is about risk premium and hedging; theory of storage is about cost-of-carry mechanics |
| Convenience yield is directly observable | Convenience yield is implied from the relationship between spot and futures prices; it is rarely directly observable |
| High inventory → high convenience yield | Opposite: high inventory → low convenience yield (scarcity drives convenience) |
| Hedging pressure theory predicts backwardation always | Only if producer hedging > consumer hedging; consumers can dominate too |
| All three theories agree on curve shape | They do not always agree — they explain the curve shape from different mechanisms |

---

## Memory Hooks

- **Insurance Theory (Keynes)**: Producers sell insurance to speculators → futures at discount → longs earn a premium → backwardation
- **Hedging Pressure**: Whoever hedges more wins the curve in their direction. More producer selling → backwardation. More consumer buying → contango
- **Theory of Storage**: Futures = Spot + carry costs − convenience yield. Low inventory → high convenience yield → backwardation
- **Convenience yield ∝ 1/inventory**: Scarcity creates convenience, abundance destroys it
- **Three theories → one output: curve shape** → which determines roll return sign

---

## Related Concepts

- [[Contango and Backwardation]] — the two market states explained by these theories
- [[Commodity Futures Total Return]] — roll return is the channel through which these theories affect investor returns
- [[Commodities and Commodity Derivatives]] — sector overview and market participants
- [[Commodity Swaps]] — alternative exposure that avoids roll mechanics entirely
