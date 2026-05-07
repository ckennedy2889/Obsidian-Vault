---
title: Contango and Backwardation
subject: Alternative Investments
tags:
  - CFA-L2
  - alternative-investments
  - commodities
  - futures
  - contango
  - backwardation
  - roll-return
  - convenience-yield
  - cost-of-carry
aliases:
  - contango
  - backwardation
  - commodity forward curve
  - normal backwardation
  - inverted market
---

# Contango and Backwardation

## The Real-World Analogy

Imagine you need crude oil. You can buy it today and store it in a tank (pay storage costs) or you can sign a contract to buy it in three months at a price agreed today (a futures contract).

If storage is cheap and there's plenty of oil around, the futures price will be higher than today's spot price — you're paying for the convenience of deferring delivery. This is **contango**.

But if there's an oil shortage and refineries are scrambling for supply *right now*, you'd pay a premium for immediate delivery. The spot price rises above futures prices — you're paying for the certainty of having oil in hand today. This is **backwardation**.

## Plain-English Definitions

**Contango:** Futures prices are *higher* than the current spot price. The forward curve slopes upward.

$$F > S \quad \Rightarrow \quad \text{Contango}$$

**Backwardation:** Spot price is *higher* than futures prices. The forward curve slopes downward (inverted).

$$S > F \quad \Rightarrow \quad \text{Backwardation}$$

```
Contango (normal market):           Backwardation (inverted market):
Price                               Price
  ^                                   ^
  |         /  /  /                   |  \  \  \
  |        /  /  /                    |   \  \  \
  |       /  /  /                     |    \  \  \
  |______/  /  /                      |_____\  \  \
  +-------------------------->        +-------------------------->
     Near   Mid   Far  Maturity          Near  Mid   Far  Maturity
```

---

## Why CFA Tests This

The LOS requires you to:
- *"Analyze the relationship between spot prices and futures prices in markets in contango and markets in backwardation"*
- *"Describe, calculate, and interpret the components of total return for a fully collateralized commodity futures contract"*

Roll return — which depends entirely on contango vs backwardation — is one of the three components of total return and is a frequent calculation question.

---

## The Cost of Carry Model

The no-arbitrage relationship between spot and futures prices:

$$\boxed{F \approx S \times (1 + r + c - i)}$$

Or in continuous time:

$$F = S \cdot e^{(r + c - i)T}$$

Where:
| Symbol | Meaning |
|---|---|
| $S$ | Current spot price |
| $r$ | Risk-free interest rate (opportunity cost of capital) |
| $c$ | Storage costs (as % of spot price) |
| $i$ | Convenience yield (non-monetary benefit of holding physical) |
| $T$ | Time to futures delivery (years) |

**Net cost of carry** = $r + c - i$

| Net Cost of Carry | Futures vs Spot | Market Condition |
|---|---|---|
| $r + c > i$ (positive carry) | $F > S$ | **Contango** |
| $r + c < i$ (negative carry) | $F < S$ | **Backwardation** |
| $r + c = i$ (zero carry) | $F = S$ | Flat forward curve |

---

## Convenience Yield — The Key Driver

**Convenience yield** ($i$) is the non-monetary benefit of holding a physical commodity rather than a futures contract. It captures the value of:
- Ensuring continuous production (a refinery doesn't want to shut down due to oil shortage)
- Being able to react to unexpected supply disruptions
- Having immediate availability for trading or manufacturing

**Crucial relationship:**

$$\text{Convenience yield} \propto \frac{1}{\text{Inventory level}}$$

- **Low inventory** → high convenience yield → market more likely in **backwardation**
- **High inventory** → low convenience yield → market more likely in **contango**

> [!example] Crude Oil Example
> In 2020, oil storage tanks were nearly full (COVID demand collapse). Convenience yield was near zero. Storage costs were high. Futures prices were far above spot → extreme contango. In fact, WTI futures briefly went negative because storage costs exceeded the value of the oil.

---

## Theories of Commodity Futures Returns

### Theory 1: Insurance Theory (Normal Backwardation — Keynes)

**Premise:** Producers of commodities (farmers, miners, oil companies) are naturally long the physical good. They want to hedge price risk by selling futures.

**Mechanism:**
- Producers persistently sell futures → supply pressure → futures prices pushed below the expected future spot price
- Speculators accept the price risk and go long → they expect to earn a risk premium
- Futures price < expected future spot price → this discount is what entices speculators in

**Result:** Futures markets should "normally" be in backwardation.

**Critique:** Historical evidence shows this is not reliable. Many markets persist in contango for extended periods. The "normal" qualifier is misleading.

### Theory 2: Hedging Pressure Hypothesis

An extension of Keynes: whether a market is in contango or backwardation depends on the **relative balance** of hedgers on each side:

- If producers (natural sellers of futures) dominate → backwardation (futures discounted to attract buyers)
- If consumers (natural buyers of futures, e.g., airlines buying jet fuel futures) dominate → contango (futures at a premium to attract sellers)

### Theory 3: Theory of Storage (Cost of Carry)

The forward curve shape reflects purely the economics of storing the physical commodity:
- High storage costs → contango
- High convenience yield (scarcity premium) → backwardation

This is the most mechanistic and quantitative theory, and underpins the cost of carry model above.

---

## Roll Return — The Critical Exam Concept

### What It Is

A commodity futures investor must **roll** their position periodically — sell the expiring near-term contract and buy the next one — to maintain continuous exposure. The price difference between these contracts creates a **roll return**.

### Formula

$$\boxed{\text{Roll return} = \frac{F_{\text{near}} - F_{\text{far}}}{F_{\text{near}}} \times \% \text{ rolled}}$$

Or simply: the return from selling the near contract and buying the far contract.

### Roll Return in Contango vs. Backwardation

| Market | Near Price | Far Price | Rolling Means… | Roll Return |
|---|---|---|---|---|
| **Contango** | Lower | Higher | Sell low, buy high | **Negative** |
| **Backwardation** | Higher | Lower | Sell high, buy low | **Positive** |

**Intuition:**
- In contango, you sell your expiring contract at the near price and must buy the farther contract at a *higher* price — you lose on the roll
- In backwardation, you sell high and buy low — you gain on the roll

> [!warning] Exam Trap — Contango Destroys Returns
> Contango means persistent negative roll return. Even if the spot price of a commodity is rising, a commodity ETF or futures investor can lose money if the roll return drag exceeds the spot return. This is the "contango trap" that affected many commodity ETFs in 2009–2015.

---

## Worked Numerical Examples

### Example 1: Roll Return Calculation

**Scenario:** An investor holds long crude oil futures and must roll from March to April.

- March (near) price: \$52.64
- April (far) price: \$53.00
- Roll: 100% of position

$$\text{Roll return} = \frac{52.64 - 53.00}{52.64} = \frac{-0.36}{52.64} = -0.68\%$$

**Interpretation:** Negative roll return → market is in contango. The investor lost 0.68% from the roll alone, separate from any change in the spot price.

### Example 2: Maintaining Exposure in Backwardation

**Scenario:** $10,000 exposure in long corn futures.

- Near-term contract price: \$4.00
- Farther-term contract price: \$2.50

Step 1 — Sell near-term contracts:

$$\frac{\$10{,}000}{\$4.00} = 2{,}500 \text{ contracts sold}$$

Step 2 — Buy farther-term contracts to maintain $10,000 exposure:

$$\frac{\$10{,}000}{\$2.50} = 4{,}000 \text{ contracts bought}$$

**Conclusion:** In backwardation, rolling requires buying *more* contracts (4,000 > 2,500) because the farther contract is cheaper. This generates a positive roll return.

### Example 3: Total Return Calculation

**Scenario:** A fully collateralized commodity futures position held for one year.

| Component | Return |
|---|---|
| Price return (spot yield) | +5.0% |
| Roll return | +2.5% |
| Collateral return | +2.0% |
| **Total return** | **+9.5%** |

If the market were instead in contango with a −2.5% roll return:

$$\text{Total return} = 5.0\% + (-2.5\%) + 2.0\% = \mathbf{4.5\%}$$

The same spot return produces a very different total return depending on whether the market is in contango or backwardation.

---

## Contango vs. Backwardation — Full Comparison Table

| | Contango | Backwardation |
|---|---|---|
| **Condition** | $F > S$ | $S > F$ |
| **Forward curve** | Upward-sloping | Downward-sloping (inverted) |
| **Cause** | High inventory, low convenience yield | Low inventory, high convenience yield |
| **Net carry** | Positive ($r + c > i$) | Negative ($r + c < i$) |
| **Roll return** | Negative | Positive |
| **Basis** | Negative (spot < futures) | Positive (spot > futures) |
| **Typical market** | Oil (when oversupplied) | Gold (low storage, high interest rates) |
| **Impact on investors** | Roll drag erodes returns | Roll gain boosts returns |

---

## Basis

**Basis** = Spot price − Futures price

| Market | Basis Sign | Example |
|---|---|---|
| Contango | Negative ($S - F < 0$) | Spot $50, Futures $52 → Basis = −$2 |
| Backwardation | Positive ($S - F > 0$) | Spot $55, Futures $52 → Basis = +$3 |

As a futures contract approaches expiration, **basis converges to zero** regardless of market condition (spot and futures must equal at delivery).

---

## Exam Traps

> [!danger] Key Exam Traps

| Trap | Correct Answer |
|---|---|
| "Normal backwardation" = markets are normally in backwardation | Wrong — empirical evidence shows many markets persist in contango |
| Contango = futures prices falling over time | No — in contango, the futures *curve* slopes up; individual contracts converge down toward spot as they mature |
| Backwardation always means spot > futures for all maturities | Yes — the entire forward curve is inverted (each near contract > each far contract) |
| Roll return formula uses absolute prices | Roll return uses *percentage* (near − far) / near |
| High convenience yield → contango | Opposite: high convenience yield reduces net carry → pushes toward **backwardation** |
| Contango is good for commodity producers who are long physical | Contango is irrelevant for the physical holder — roll return only affects futures investors |

---

## Memory Hooks

- **Contango = Can't get it cheap later (you pay more for future delivery)** → futures > spot
- **Backwardation = Back to wanting it NOW (immediate scarcity premium)** → spot > futures
- **Roll in contango = sell cheap, buy expensive = negative roll return**
- **Roll in backwardation = sell expensive, buy cheap = positive roll return**
- **Convenience yield inversely with inventory**: Low inventory → high convenience yield → backwardation

---

## Related Concepts

- [[Commodity Futures Total Return]] — spot return + roll return + collateral return
- [[Theories of Commodity Futures Returns]] — insurance theory, hedging pressure, theory of storage
- [[Commodity Swaps]] — using swaps to gain commodity exposure without roll issues
- [[Commodities and Commodity Derivatives]] — overview of commodity sectors and market structure
- [[Forward Rate Agreement]] — similar cost of carry logic applies to interest rate forwards
