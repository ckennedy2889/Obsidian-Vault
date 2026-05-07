---
title: Implied Volatility
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - implied-volatility
  - BSM
  - volatility-smile
  - volatility-skew
  - VIX
aliases:
  - IV
  - implied vol
  - volatility smile
  - volatility skew
  - volatility surface
---

# Implied Volatility

## The Real-World Analogy

When you buy car insurance, the premium the insurer charges reflects their expectation of how likely you are to crash — their implied view of your "risk." If they charged you more than a driver with an identical history, you'd know the insurer expects you to be riskier going forward, regardless of the past.

Implied volatility works the same way. The option's market price contains the market's forward-looking expectation of how volatile the underlying will be. Strip out every other variable and what's left is the market's "insurance premium" on future uncertainty — implied volatility.

## Plain-English Definition

**Implied volatility (IV)** is the value of volatility ($\sigma$) that, when plugged into the [[Black-Scholes-Merton Model|BSM model]], produces the option's observed market price.

It is the market's **consensus expectation** of the underlying asset's volatility over the remaining life of the option. It is forward-looking, not backward-looking.

$$\underbrace{C_{\text{market}}}_{\text{observed price}} = \underbrace{f(S, X, r, T, \sigma_{\text{implied}})}_{\text{BSM model}}$$

Solve for $\sigma_{\text{implied}}$ given $C_{\text{market}}$.

---

## Why CFA Tests This

The LOS states: *"Define implied volatility and explain how it is used in options trading."*

The exam tests:
- The conceptual difference between IV and historical volatility
- Why IV cannot be solved algebraically (must use iteration)
- The shape of the volatility smile and skew, and why each exists
- How traders use IV to identify cheap/expensive options
- The VIX as the benchmark implied volatility index

---

## Historical vs. Implied Volatility

| | Historical (Realized) Volatility | Implied Volatility |
|---|---|---|
| **Direction** | Backward-looking | Forward-looking |
| **Calculation** | Annualized std dev of past returns | Backed out from option market price |
| **Nature** | Objective (measured from data) | Subjective (market's forecast) |
| **Formula** | $\sigma = \sqrt{\frac{252}{n}\sum(r_t - \bar{r})^2}$ | BSM inverted numerically |
| **Use** | Benchmarking realized risk | Pricing options, trading volatility |

**Key insight:** Historical volatility tells you what happened. Implied volatility tells you what the market thinks will happen. The gap between them is where trading opportunities live.

---

## How to Back Out Implied Volatility

The BSM formula cannot be algebraically inverted to solve for $\sigma$. Instead, it requires **numerical iteration**:

```
Step 1: Observe the market price of the option (C_market)
Step 2: Start with an initial guess for σ (e.g., 20%)
Step 3: Plug σ into BSM → compute C_model
Step 4: Compare C_model to C_market
   If C_model > C_market → σ was too high → lower σ
   If C_model < C_market → σ was too low → raise σ
Step 5: Repeat until C_model ≈ C_market
Step 6: That σ is the implied volatility
```

This is essentially a **root-finding problem**. Modern computers do this in milliseconds using Newton-Raphson or bisection methods.

> [!note] Exam Trap — No Algebraic Solution
> The BSM cannot be inverted for $\sigma$. Implied volatility is always found iteratively. Any exam answer claiming there is a closed-form solution for IV is wrong.

---

## The Volatility Smile and Skew

If BSM's assumption of **constant volatility** held perfectly, all options on the same underlying with the same expiry would have identical IV regardless of strike. In practice, they do not.

### Volatility Smile (FX Markets)

A **U-shaped** IV curve: IV is lowest for ATM options and higher for both deep ITM and deep OTM options.

```
IV
 |  \               /
 |   \             /
 |    \           /
 |     \         /
 |      \_______/
 |
 +-----------------------------  Strike
  Low (OTM put)  ATM  High (OTM call)
```

**Why it exists in FX markets:**
- Currency pairs exhibit **fat tails and jumps** — large sudden moves are more frequent than a normal distribution predicts
- Both OTM puts (fear of currency crash) and OTM calls (fear of currency squeeze) are in demand
- The smile reflects that BSM underprices both extremes

### Volatility Skew / Smirk (Equity Markets)

A **downward-sloping** IV curve: IV is highest for low-strike (OTM put / ITM call) options and decreases as strike rises.

```
IV
 |
 |\
 | \
 |  \
 |   \
 |    \____
 |
 +-----------------------------  Strike
  Low (OTM put)  ATM  High (OTM call)
```

**Why it exists in equity markets:**

1. **Leverage effect:** As stock prices fall, debt-to-equity rises → firm becomes riskier → equity volatility increases
2. **Crashophobia:** After the 1987 stock market crash, investors persistently over-pay for OTM puts as crash insurance, bidding up their IV
3. **Asymmetric crash risk:** Stock markets have fat *left* tails (crashes) — BSM with constant $\sigma$ underestimates downside risk

**Practical implication:** An equity hedger buying protective puts pays a higher effective volatility than the market-wide average.

### The Volatility Surface

Plotting IV against both **strike price** and **time to maturity** produces a 3D **volatility surface**.

```
IV
^
|     /  /  /
|    /  /  /    ← term structure of volatility
|   /  /  /
+--/--/--/-----------> Strike
  Low  ATM  High
```

- The smile/skew varies by expiration
- Near-term options often show steeper skews
- Long-dated options tend toward a flatter surface (mean-reversion of volatility)
- The surface must be **arbitrage-free** — options at different strikes/maturities must price consistently

---

## The VIX Index

The **CBOE Volatility Index (VIX)** measures the 30-day implied volatility of S&P 500 index options.

- Often called the **"fear gauge"** or **"fear index"**
- Derived from a wide range of S&P 500 option prices (not just ATM)
- Expressed as an annualized percentage: VIX = 20 means the market expects ~20% annualized vol over the next 30 days

**Daily implied move:** $\text{Expected daily move} \approx \frac{VIX}{16}$ (since $\sqrt{252} \approx 16$)

**Relationship with equity markets:**
- VIX is **negatively correlated** with S&P 500 returns
- When markets fall sharply → VIX spikes (uncertainty and demand for puts rises)
- When markets are calm → VIX falls

| VIX Level | Market Signal |
|---|---|
| Below 15 | Low fear, complacency |
| 15–25 | Normal uncertainty |
| 25–35 | Elevated stress |
| Above 35 | Crisis/panic conditions |

---

## How Traders Use Implied Volatility

### 1. Quoting in Volatility Terms

In options markets, especially FX and fixed income, options are quoted as an IV percentage rather than a dollar price. This allows:
- Direct comparison of options across different strikes and expirations
- Stripping out differences in underlying price, rate, and time

### 2. Relative Value — Cheap vs. Expensive Options

Compare current IV to:
- **Historical realized volatility:** If $IV > \sigma_{\text{historical}}$, options are "expensive" → consider selling
- **Own historical IV:** If current IV is at the bottom of its historical range, options are cheap → consider buying
- **Related assets:** Pairs trading on vol (e.g., long vol in one index, short vol in another)

### 3. Expressing Volatility Views

| View | Strategy |
|---|---|
| Expect large move, unknown direction | Buy straddle (long call + long put at same strike) — delta-neutral, long vega |
| Expect calm market | Sell straddle — collect theta, short vega |
| Expect vol to rise | Buy options (positive vega) |
| Expect vol to fall | Sell options, delta-hedge |

> [!example] The Straddle as a Pure Volatility Bet
> A straddle is delta-neutral at initiation but has positive vega. The trader profits if the underlying moves more than the implied move priced into the straddle, regardless of direction. This is "trading volatility" — betting on the size of the move, not its direction.

---

## Exam Traps

> [!danger] Key Exam Traps

| Trap | Correct Understanding |
|---|---|
| IV = historical vol | IV is forward-looking; historical vol is backward-looking — they often diverge significantly |
| IV can be solved algebraically | Must use numerical iteration — no closed-form solution exists |
| Low IV = cheap options | Only relative to expectations — if realized vol is also low, the option may be fairly priced |
| Smile only in equity markets | Smile (U-shape) is common in FX; skew (downward slope) is common in equities |
| Higher strike = higher IV in equities | Opposite is true — lower strike = higher IV in equities (skew slopes down) |
| Vega highest for OTM options (highest IV) | Vega is highest for **ATM** options in absolute dollar terms, even though OTM IV may be higher |
| Rising IV always benefits the option holder | True for long options (positive vega) but not for short options (negative vega) |

---

## Memory Hooks

- **IV = market's insurance premium** — it's what buyers pay for the uncertainty of future moves
- **Historical vol = rearview mirror; IV = windshield** — one looks back, one looks forward
- **Equity skew = crash fear**: OTM puts cost more because investors buy crash insurance
- **FX smile = fat tails on both sides**: Extreme moves in either direction are feared
- **VIX and stocks move opposite**: When fear rises (VIX up), stocks fall
- **Finding IV = trial and error**: Plug in $\sigma$, adjust until BSM matches market price

---

## Related Concepts

- [[Black-Scholes-Merton Model]] — the model into which IV is input
- [[Option Greeks]] — Vega is the Greek that measures sensitivity to volatility
- [[Delta Hedging and Gamma Risk]] — delta-hedged short options are a bet on IV vs realized vol
- [[Swaptions]] — IV of the forward swap rate is the key input to the Black model
- [[Interest Rate Options]] — caps/floors also have an implied vol input in the Black model
- [[CFA_L2_Valuation_of_Contingent_Claims]] — BSM model detail and numerical examples
