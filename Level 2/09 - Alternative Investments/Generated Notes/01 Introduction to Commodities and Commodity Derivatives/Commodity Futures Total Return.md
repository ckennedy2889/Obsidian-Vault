---
title: Commodity Futures Total Return
subject: Alternative Investments
tags:
  - CFA-L2
  - alternative-investments
  - commodities
  - futures
  - total-return
  - roll-return
  - collateral-return
  - price-return
  - fully-collateralized
aliases:
  - commodity total return
  - spot yield
  - roll yield
  - collateral yield
  - commodity futures return components
---

# Commodity Futures Total Return

## The Real-World Analogy

Owning commodity futures is not the same as owning the commodity. If you buy crude oil futures, you never touch a barrel — you're making a financial bet on the price. But your actual return has three completely separate engines driving it simultaneously:

1. **Did the commodity price go up?** (Price return)
2. **Were you selling expensive near-term contracts and buying cheaper far-term ones, or the opposite?** (Roll return)
3. **While you waited, what were you earning on the cash you posted as collateral?** (Collateral return)

Miss any one of these, and you fundamentally misunderstand why commodity investors make or lose money.

## Plain-English Definition

The **total return of a fully collateralized commodity futures contract** has three components:

$$\boxed{\text{Total Return} = \text{Price Return} + \text{Roll Return} + \text{Collateral Return}}$$

Each component is independent, can be positive or negative, and can dominate the total return in different market environments.

---

## Why CFA Tests This

The LOS states: *"Describe, calculate, and interpret the components of total return for a fully collateralized commodity futures contract."*

The exam tests:
- Calculating all three components from given data
- Understanding what makes roll return positive vs negative
- The difference between fully collateralized and leveraged positions
- Why a commodity ETF can lose money even when the commodity price rises

---

## The Three Components

### Component 1: Price Return (Spot Yield)

**What it is:** The percentage change in the price of the **front-month (near-term) futures contract** from the beginning to the end of the holding period.

$$\boxed{\text{Price Return} = \frac{F_{\text{end}} - F_{\text{start}}}{F_{\text{start}}}}$$

**Important:** This is based on the front-month futures price, not the spot price, because investors hold futures contracts, not the physical commodity. The front-month futures price tracks the spot price closely but not perfectly.

**What drives it:**
- Changes in supply/demand fundamentals
- Macroeconomic conditions
- Geopolitical events
- Seasonal patterns (e.g., natural gas prices peak in winter)

### Component 2: Roll Return (Roll Yield)

**What it is:** The gain or loss generated when an investor rolls an expiring near-term contract into the next farther-term contract to maintain continuous exposure.

$$\boxed{\text{Roll Return} = \frac{F_{\text{near}} - F_{\text{far}}}{F_{\text{near}}} \times \% \text{ rolled}}$$

**The mechanism in plain English:**

A futures investor cannot hold a contract forever — it expires. To maintain exposure, they must:
1. Sell the expiring near-term contract
2. Buy the next farther-term contract

If the farther-term contract is *cheaper* (backwardation) → sell high, buy low → **positive roll return**
If the farther-term contract is *more expensive* (contango) → sell low, buy high → **negative roll return**

| Market Condition | Near vs. Far Price | Roll Action | Roll Return |
|---|---|---|---|
| **Backwardation** | Near > Far | Sell high, buy low | **Positive** |
| **Contango** | Near < Far | Sell low, buy high | **Negative** |

> [!warning] The Contango Trap
> Many commodity ETFs and index funds systematically lose money on roll return when markets are in persistent contango. This is why a commodity ETF tracking oil can lose money over a year even when oil prices are flat or slightly rising. The roll drag destroys value.

### Component 3: Collateral Return (Collateral Yield)

**What it is:** The interest earned on the cash or high-quality bonds (typically T-bills) deposited as collateral to support the futures position.

$$\boxed{\text{Collateral Return} = \text{HPY on collateral} \times \frac{\text{holding period}}{\text{year}}}$$

**Why it exists:** Futures contracts are leveraged instruments — you only need to post margin (a fraction of notional value) to hold a futures position. But in a "fully collateralized" position, the investor deliberately posts 100% of the notional value in safe assets.

**The collateral earns the risk-free rate.** This is why commodity futures are sometimes described as "free" exposure to commodity prices — you're getting the price return plus a risk-free rate on your collateral.

---

## Fully Collateralized vs. Leveraged

| | Fully Collateralized | Leveraged |
|---|---|---|
| **Collateral posted** | 100% of notional value | Only initial margin (e.g., 10% of notional) |
| **Collateral return** | Earned on full notional | Earned on margin only |
| **Price return** | Same % as leveraged | Amplified relative to cash invested |
| **Risk** | Proportional to position size | Magnified — can lose more than invested |
| **CFA context** | Benchmark for index returns | Real-world trading |

The CFA curriculum focuses on fully collateralized positions because commodity indexes (like S&P GSCI) are constructed on a fully collateralized basis — they represent the return of a passive, unleveraged investment.

---

## Worked Numerical Examples

### Example A: Simple Annual Return

An investor holds a fully collateralized long crude oil futures position for one year.

| Component | Return |
|---|---|
| Price return (front-month rose 5%) | +5.0% |
| Roll return (market in backwardation) | +2.5% |
| Collateral return (T-bill rate = 2%) | +2.0% |
| **Total return** | **+9.5%** |

**Contrast — if market were in contango:**

| Component | Return |
|---|---|
| Price return | +5.0% |
| Roll return (contango = negative) | −2.5% |
| Collateral return | +2.0% |
| **Total return** | **+4.5%** |

Same spot return, but a 5% difference in total return purely from roll return. This illustrates how critical the forward curve shape is.

### Example B: Full Three-Component Calculation (Quarterly)

**The Apex Fund holds long soybean futures:**

- Entry price (front-month): 865.0 cents/bushel
- End of quarter price (new front-month): 877.0 cents/bushel
- Next farther-term price at roll: 883.0 cents/bushel
- 100% of position rolled
- Annualized collateral rate: 0.60%
- Holding period: 3 months (0.25 years)

**Step 1 — Price Return:**

$$\text{Price Return} = \frac{877 - 865}{865} = \frac{12}{865} = +1.387\%$$

**Step 2 — Roll Return:**

$$\text{Roll Return} = \frac{877 - 883}{877} \times 100\% = \frac{-6}{877} = -0.684\%$$

The negative roll return tells us this market is in **contango** — the far contract (883) is more expensive than the near contract (877).

**Step 3 — Collateral Return (pro-rated quarterly):**

$$\text{Collateral Return} = 0.60\% \times \frac{3}{12} = 0.15\%$$

**Step 4 — Total Return:**

$$\text{Total Return} = 1.387\% + (-0.684\%) + 0.15\% = \mathbf{0.853\%}$$

**Interpretation:** The price return of 1.4% was largely eaten up by the negative roll return (−0.68%), leaving only 0.85% net of roll drag after collateral income.

### Example C: Maintaining Exposure During a Roll

An investor has $10,000 exposure in natural gas futures.

**In backwardation:**
- Near-term price: \$4.00
- Far-term price: \$2.50

Step 1: Sell near contracts → $\frac{\$10{,}000}{\$4.00} = 2{,}500$ contracts sold

Step 2: Buy far contracts to maintain $10,000 exposure → $\frac{\$10{,}000}{\$2.50} = 4{,}000$ contracts bought

You buy **more** contracts because the far contract is cheaper. The gain = 4,000 contracts × $2.50 = $10,000 exposure maintained with a favorable roll.

**In contango (same numbers reversed):**
- Near-term price: \$4.00
- Far-term price: \$5.00

Step 1: Sell near → 2,500 contracts, receive $10,000

Step 2: Buy far → $\frac{\$10{,}000}{\$5.00} = 2{,}000$ contracts

You buy **fewer** contracts because the far contract is more expensive. You lose some exposure (or equivalently, you paid $10,000 to get only $10,000 of exposure at a worse price).

---

## Why the Three Components Matter Separately

### Historical Evidence

Empirically, the three components have contributed very differently over time:
- **Collateral return** is steady and predictable (the risk-free rate)
- **Price return** is volatile and unpredictable
- **Roll return** has been the most persistently negative component for many commodity indexes in contango markets (2005–2015 for energy commodities)

This is why many commodity investors have shifted to **enhanced roll strategies** — trying to minimize negative roll return by rolling into the least contango portion of the curve, or using long-dated contracts.

### The "Futures Return ≠ Spot Return" Lesson

The total return of a commodity futures investment systematically differs from the return of the physical commodity:

$$\text{Futures total return} = \text{Spot price change} + \text{Roll return} + \text{Collateral return}$$

A commodity index can have:
- Spot price up 10%
- Roll return −12% (severe contango)
- Collateral 2%
- Total return = 0%

Meanwhile, the physical commodity gained 10%.

> [!example] Real-World Example — Oil ETFs in 2009
> After the 2008 crash, crude oil spot prices recovered strongly in 2009. But oil ETFs using front-month futures severely underperformed spot oil because the oil market was in extreme contango (storage was full). The roll drag destroyed most of the spot return. This is why "buying oil" via an ETF is not the same as owning physical oil.

---

## Exam Traps

> [!danger] Key Exam Traps

| Trap | Correct Understanding |
|---|---|
| Positive price return = positive total return | Not if roll return is large and negative (contango markets) |
| Roll return = price return | Roll return is a separate component measuring only the futures curve shape |
| Collateral return = zero | A fully collateralized investor earns the risk-free rate on 100% of notional |
| Use annual collateral rate directly | Must pro-rate to the holding period (e.g., quarterly = divide by 4) |
| In backwardation, buy fewer contracts when rolling | Opposite: buy **more** contracts in backwardation (they're cheaper) |
| Roll return can be isolated as a standalone return | Roll return is an accounting calculation within the index methodology, not a tradeable return on its own |

---

## Memory Hooks

- **Total return = Price + Roll + Collateral** — memorize as "**PRC**"
- **Roll in backwardation = positive** (sell high near, buy low far)
- **Roll in contango = negative** (sell low near, buy high far)
- **Contango = ETF investors get burned**: spot rises but total return lags
- **Fully collateralized = invest 100%, earn T-bill rate on the whole amount**
- **Roll more contracts in backwardation, fewer in contango**: cheap far contract → need more to maintain dollar exposure

---

## Related Concepts

- [[Contango and Backwardation]] — the market conditions that determine roll return sign
- [[Theories of Commodity Futures Returns]] — insurance theory, hedging pressure, and theory of storage
- [[Commodity Swaps]] — alternative to futures for gaining commodity exposure without roll exposure
- [[Commodities and Commodity Derivatives]] — sector overview and market structure
- [[Forward Rate Agreement]] — similar cost-of-carry logic governs interest rate forwards
