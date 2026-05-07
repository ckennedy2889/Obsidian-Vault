---
title: Delta Hedging and Gamma Risk
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - delta-hedging
  - gamma-risk
  - dynamic-hedging
  - risk-management
aliases:
  - dynamic hedging
  - delta-neutral portfolio
  - gamma scalping
  - delta neutral
---

# Delta Hedging and Gamma Risk

## The Real-World Analogy

Imagine you're an insurance company that just sold 10,000 car insurance policies. Each policy pays out if the driver has an accident. You can't know which drivers will crash, but you can hedge your exposure by holding cash reserves proportional to the expected payout.

Here's the problem: as circumstances change — bad weather arrives, or a new driver demographic signs up — your expected payout changes too. You have to constantly adjust your reserves. You can never hedge once and forget.

Delta hedging is exactly this. You sold an option (took on risk). You offset that risk by holding shares of the underlying stock in proportion to the option's delta. But as the stock price moves, delta changes — so you must constantly rebalance. Gamma is the measure of how fast delta changes, and therefore how expensive and imperfect your hedge will be.

## Plain-English Definition

**Delta hedging** is a strategy that creates a position with zero net exposure to small moves in the underlying asset — a **delta-neutral portfolio**.

**Gamma risk** is the risk that delta drifts as the underlying moves, making the hedge increasingly inaccurate over time and requiring costly rebalancing.

Together, they form the core of the options market maker's daily job: sell options, delta-hedge, rebalance constantly, manage the cost of gamma.

---

## Why CFA Tests This

The LOS states:
- *"Describe how a delta hedge is executed"*
- *"Describe the role of gamma risk in options trading"*

Exam questions typically ask you to:
1. Calculate the number of shares needed to delta-hedge a position
2. Identify what happens to the hedge after a stock price move
3. Calculate the rebalancing trade required
4. Explain why gamma makes delta hedging imperfect

---

## Building a Delta-Neutral Hedge

### The Hedge Ratio

The **hedge ratio** ($h$) is simply the option's delta. It tells you how many shares of the underlying to hold per option in your portfolio.

In the [[Binomial Option Pricing Model|binomial model]]:

$$h = \frac{c^+ - c^-}{S^+ - S^-}$$

In the [[Black-Scholes-Merton Model|BSM model]] for a call:

$$h = \Delta = N(d_1)$$

### Long vs. Short Positions

| Your option position | Share position needed | Intuition |
|---|---|---|
| **Short call** | Long $h$ shares | You lose if stock rises → offset by owning stock |
| **Long call** | Short $h$ shares | You gain if stock rises → offset by shorting stock |
| **Short put** | Short $h$ shares | You lose if stock falls → offset by shorting stock |
| **Long put** | Long $h$ shares | You gain if stock falls → offset by owning stock |

**General rule:** The share position is always *opposite* in sign to the net delta of the option position you are hedging.

### Portfolio Value — Short Call Hedge

If you are short 1 call and long $h$ shares:

$$V = h \cdot S - c$$

At initiation, with the right $h$:

$$\frac{\partial V}{\partial S} = h - \Delta = 0 \quad \Rightarrow \quad h = \Delta$$

The portfolio is delta-neutral: $V$ does not change for small $\Delta S$.

---

## The Mechanics of Dynamic Rebalancing

A delta-neutral hedge is only "locally" (instantaneously) neutral. The moment the stock price moves, delta changes. The hedge must be updated continuously — this is called **dynamic hedging**.

### Why Delta Drifts: The Role of Gamma

Gamma is $\partial \Delta / \partial S$. Every time the stock moves by $\Delta S$, delta shifts by approximately:

$$\Delta(\text{new}) \approx \Delta(\text{old}) + \Gamma \cdot \Delta S$$

This drift means:
- After a stock price rise, call delta increases (call is more in-the-money)
- The hedger now holds too few shares → must buy more
- After a stock price fall, call delta decreases → hedger holds too many shares → must sell some

```
Time 0:  S = 50, Δ = 0.58 → hold 5,800 shares per 10,000 calls
                               ↓ stock rises to $55
Time 1:  S = 55, Δ = 0.70 → need 7,000 shares
                               → BUY 1,200 more shares (at higher price!)
                               ↓ stock falls back to $50
Time 2:  S = 50, Δ = 0.58 → need 5,800 shares again
                               → SELL 1,200 shares (at lower price!)
```

Notice the pattern: you are forced to **buy high and sell low**. This is the cost of gamma for a short-option hedger. Every oscillation in the stock price costs you money.

---

## Worked Numerical Example

**Setup:**
- You are **short 10,000 European call options**
- Strike: $X = \$50$, Time to expiry: 1 year
- $S_0 = \$50$, $r = 2\%$, $\sigma = 30\%$
- BSM gives: $\Delta_0 = 0.58577$, Gamma $\approx 0.02354$

### Step 1 — Initial Delta-Neutral Hedge

$$\text{Shares to buy} = 10{,}000 \times 0.58577 = \mathbf{5{,}858 \text{ shares}}$$

Portfolio is delta-neutral: a $1 move in the stock changes the short call value by $+$10,000 × 0.58577 = $5,858, exactly offset by the $5,858 gain from the 5,858 shares.

### Step 2 — Stock Price Rises to $55

New delta from BSM at $S = 55$: $\Delta_1 = 0.70346$

Delta drift check using gamma:
$$\Delta_1 \approx 0.58577 + 0.02354 \times 5 = 0.58577 + 0.11770 = 0.703$$

✓ Matches BSM directly.

**The hedge is now wrong:**
- You hold 5,858 shares
- You need $10{,}000 \times 0.70346 = 7{,}035$ shares
- **Gap: 1,177 shares short**

### Step 3 — Rebalancing Trade

$$\text{Buy } 7{,}035 - 5{,}858 = \mathbf{1{,}177 \text{ additional shares at \$55}}$$

Cost of rebalancing: $1{,}177 \times \$55 = \$64{,}735$

### Step 4 — Suppose Stock Falls Back to $50

New delta back to $\approx 0.58577$, so you only need 5,858 shares again.

$$\text{Sell } 7{,}035 - 5{,}858 = \mathbf{1{,}177 \text{ shares at \$50}}$$

Revenue: $1{,}177 \times \$50 = \$58{,}850$

**Round-trip cost of one oscillation:**
$$\$64{,}735 - \$58{,}850 = \$5{,}885 \text{ loss}$$

This loss is the real-world cost of gamma for a short-option position. It represents what the option seller loses by being forced to buy high and sell low during rebalancing.

---

## Gamma Risk — The Full Picture

### Why Gamma Makes Hedging Imperfect

Delta provides only a **linear approximation** of the option's price curve. The actual relationship is **convex** (curved). For large moves:

$$\Delta C_{\text{actual}} > \Delta C_{\text{delta only}}$$

The gap between the actual price change and the delta approximation grows with the square of the price move:

$$\text{Approximation error} \approx \frac{1}{2} \Gamma (\Delta S)^2$$

This is exactly the gamma term in the [[Option Greeks#The Delta-Gamma Approximation|delta-gamma approximation]].

### Where Gamma Is Largest

```
           Gamma
             ^
             |
        _____|_____
       /     |     \
      /       |      \
_____/        |        \______
   Deep OTM   ATM    Deep ITM
              ↑
         Gamma peaks here
```

Gamma is highest for:
- **ATM options** — delta is most sensitive to small moves near ATM
- **Near expiration** — with little time left, an ATM option can jump from $\Delta = 0.5$ to $\Delta \approx 0$ or $\Delta \approx 1$ on a tiny move

### Gamma Risk Near Expiration

An ATM call with 1 day to expiry is the most dramatic example:
- $\Delta \approx 0.5$ right now
- Tomorrow, if $S > X$: expires ITM, $\Delta$ jumps to 1
- Tomorrow, if $S < X$: expires OTM, $\Delta$ drops to 0
- A $0.01 move can cause a $\Delta$ swing of $0.5

For a delta-hedged seller, this is catastrophic — the hedge oscillates violently, transaction costs explode, and any imprecision in rebalancing creates large losses.

---

## The Theta-Gamma Trade-off

For a long option position, there is a fundamental tension:

| | Long Option (Buyer) | Short Option (Seller) |
|---|---|---|
| Gamma | Positive (benefits from large moves) | Negative (hurt by large moves) |
| Theta | Negative (pays time decay every day) | Positive (collects time decay every day) |
| Who wins? | Buyer wins if large moves occur | Seller wins if market stays quiet |

**The trade-off:** Long gamma → pays theta. Short gamma → collects theta.

A delta-hedged short option seller is essentially:
- Betting that the stock will **not move much** (gamma loss stays small)
- Collecting **theta** (time decay premium) as compensation for bearing gamma risk

If the stock moves a lot, gamma losses exceed theta collected → seller loses.
If the stock stays calm, theta collected exceeds gamma losses → seller profits.

> [!example] Real-World: The Option Seller's Daily P&L
> An options market maker who sells calls and delta-hedges wakes up each day asking: "Did the stock move more than the implied volatility predicted?" If yes, gamma losses exceeded theta income (bad day). If no, theta exceeded gamma losses (good day). This is why implied volatility is the market's "price" of gamma risk.

---

## The Number of Options to Hedge a Portfolio

If you need to hedge a **stock portfolio** using options (e.g., buying puts for protection):

$$N_{\text{options}} = -\frac{\Delta_{\text{portfolio}}}{\Delta_{\text{option}}}$$

**Example:** You hold a $1,000,000 equity portfolio with $\Delta = 1.0$ (it moves 1-for-1 with the index). You want to buy puts with $\Delta = -0.40$ to hedge.

$$N_{\text{puts}} = -\frac{1.0}{-0.40} = 2.5 \text{ units of put per unit of portfolio}$$

For $1,000,000 at $400 per option contract (100 shares):

$$N = \frac{1{,}000{,}000 / 400}{0.40} = 6{,}250 \text{ put contracts}$$

---

## Exam Traps

> [!danger] Delta Hedging Exam Traps

| Trap | Correct Understanding |
|---|---|
| Hedge is "done" once built | Delta hedges require **continuous rebalancing** — they are never static |
| Short gamma is always bad | Short gamma collects theta — it's a deliberate trade-off, not a pure risk |
| Rebalancing always costs money | For a long gamma position (long option, delta-hedged), rebalancing is profitable — you buy low and sell high |
| Gamma always hurts | Gamma hurts **short option** hedgers; it helps **long option** hedgers |
| Delta hedging eliminates all risk | It eliminates **linear** (delta) risk only; gamma, vega, and theta risks remain |
| High gamma = always near expiry | High gamma = ATM options; maturity also matters but ATM is the key driver |

---

## Memory Hooks

- **Short gamma = short gamma scalping**: You pay out on every oscillation. Theta is your compensation
- **Long gamma = free convexity**: Large moves benefit you more than delta predicts. You pay for this via theta
- **Rebalancing rule**: Short call hedger always buys when stock rises, sells when stock falls → buying high, selling low → gamma loss
- **Gamma peaks ATM**: The delta of an ATM option is most sensitive to moves → most dangerous place to be for a short gamma hedger
- **Theta-Gamma = flip sides of the same coin**: You cannot get one without the other in an options position

---

## Related Concepts

- [[Option Greeks]] — full treatment of all five Greeks and the delta-gamma approximation formula
- [[Black-Scholes-Merton Model]] — source of BSM delta $= N(d_1)$
- [[Binomial Option Pricing Model]] — binomial delta and hedge ratio construction
- [[Implied Volatility]] — the market price of gamma risk embedded in option premiums
- [[Swaptions]] — delta and gamma apply to interest rate options too
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full module including delta hedging examples
