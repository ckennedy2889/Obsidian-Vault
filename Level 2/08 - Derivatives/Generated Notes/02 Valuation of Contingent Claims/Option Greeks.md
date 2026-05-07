---
title: Option Greeks
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - greeks
  - delta
  - gamma
  - theta
  - vega
  - rho
  - BSM
  - risk-management
aliases:
  - Greeks
  - option sensitivities
  - delta gamma theta vega rho
---

# Option Greeks

## The Real-World Analogy

Imagine you own a house and you're trying to understand all the different forces that affect its value. You know roughly that a 1% rise in the local economy lifts prices by £5,000 (your "delta"). But the relationship is curved — in a booming market, the same 1% rise gives you even more than £5,000 (your "gamma"). Meanwhile, every year that passes erodes your option to renovate cheaply (your "theta"). Uncertainty in the market amplifies everything (your "vega"). And the interest rate at which you're financing determines how attractive holding the house really is (your "rho").

Option Greeks are exactly these partial derivatives — each one isolates a single force acting on your option's price while holding everything else constant.

## Plain-English Definition

The **option Greeks** measure how sensitive an option's price is to changes in specific underlying parameters. They come from differentiating the [[Black-Scholes-Merton Model|BSM]] pricing formula with respect to each input.

| Greek | Symbol | "Sensitivity to…" | Mnemonic |
|---|---|---|---|
| Delta | $\Delta$ | Underlying asset price | **D**irection of the stock |
| Gamma | $\Gamma$ | Delta itself | **G**ap in the hedge |
| Theta | $\Theta$ | Passage of time | **T**ime ticking away |
| Vega | $\nu$ | Volatility ($\sigma$) | **V**olatility value |
| Rho | $\rho$ | Risk-free interest rate | **R**ate effect |

> [!note] Vega is not a Greek letter
> Vega ($\nu$) is actually the letter "nu" used as a proxy. The name "vega" was coined by traders. On the exam, you may see it written as $\nu$ or simply "vega."

---

## Why CFA Tests This

Every Greek has at least one dedicated LOS. The exam tests:
- The **sign** of each Greek for calls vs. puts
- What happens to each Greek as the option moves in/out of the money
- The **delta-gamma approximation** formula (numerical calculation)
- How to construct and rebalance a **delta-neutral hedge**
- Why **gamma risk** makes delta hedging imperfect

---

## The Five Greeks — Deep Dive

### 1. Delta ($\Delta$) — The Hedge Ratio

**What it is:** Delta is the change in option price per $1 change in the underlying asset price. It is also the number of shares you need to hold to replicate the option (the hedge ratio).

$$\boxed{\Delta = \frac{\partial c}{\partial S}}$$

In the [[Binomial Option Pricing Model|binomial model]]:

$$\Delta = \frac{c^+ - c^-}{S^+ - S^-}$$

In the [[Black-Scholes-Merton Model|BSM model]] for a call:

$$\Delta_{\text{call}} = N(d_1)$$

For a put:

$$\Delta_{\text{put}} = N(d_1) - 1 = -N(-d_1)$$

**Sign and range:**

| Option | Delta Range | Intuition |
|---|---|---|
| Long call | 0 to +1 | Call gains value as stock rises |
| Long put | −1 to 0 | Put loses value as stock rises |
| Short call | −1 to 0 | Mirror of long call |
| Short put | 0 to +1 | Mirror of long put |

**How moneyness affects delta:**

```
Deep ITM call   →   Δ ≈ +1.0   (moves almost 1-for-1 with stock)
At-the-money    →   Δ ≈ +0.5   (50/50 chance of expiring ITM)
Deep OTM call   →   Δ ≈ 0      (barely responds to stock moves)
```

**The BSM interpretation:** $N(d_1)$ is the risk-neutral probability-adjusted exposure to the stock. A call option at $\Delta = 0.6$ behaves like holding 0.6 shares of stock, fully leveraged.

> [!warning] Exam Trap — Delta Drifts
> Delta is not constant. Every time the stock price moves, delta changes. This is exactly what Gamma measures. A delta-neutral hedge constructed today will be wrong tomorrow.

---

### 2. Gamma ($\Gamma$) — The Curvature

**What it is:** Gamma is the rate of change of delta per $1 change in the underlying. It captures the *curvature* (convexity) of the option price curve.

$$\boxed{\Gamma = \frac{\partial \Delta}{\partial S} = \frac{\partial^2 c}{\partial S^2}}$$

**Key properties:**
- **Both calls and puts have positive gamma** for long positions
- Gamma is highest when the option is **at-the-money** (ATM)
- Gamma is highest **near expiration** for ATM options — the delta can swing violently from 0.5 toward 0 or 1 in a short period

```
                Gamma
                  |
              ----+----
             /    |    \
            /     |     \
           /      |      \
----------/       |       \----------
      Deep OTM   ATM    Deep ITM
```

**Why positive gamma is good for option buyers:** If you are long a call and the stock rises, your delta increases (you're "more long"), so you benefit more than a linear approximation would predict. This is the source of the option's convex payoff.

**Analogy to bonds:** Just like a bond's price-yield relationship has convexity (making duration-only estimates imprecise), an option's delta-based estimate needs a gamma correction. The delta-gamma approximation is the options equivalent of the duration-convexity formula.

> [!warning] Exam Trap — Gamma Risk
> High gamma = unstable hedge. ATM options near expiration have extreme gamma — a tiny move in the stock creates a large change in delta, forcing expensive rebalancing.

---

### 3. Theta ($\Theta$) — Time Decay

**What it is:** Theta measures how much the option price decreases as one day passes, all else equal.

$$\boxed{\Theta = \frac{\partial c}{\partial t}}$$

**Sign:** Theta is almost always **negative** — options lose value as they approach expiration because there is less time for a favorable move to occur.

**The exception:** A deep **in-the-money European put** can have **positive theta**. Here's why: a deep ITM European put is nearly certain to pay $X - S$. But the holder cannot exercise early (European-style), so the put's value is the present value of a nearly-certain payoff. As time passes and the discount period shortens, the PV increases. The option gains value from time passing.

**ATM options decay fastest near expiration** — theta is largest in magnitude for ATM options in the final weeks before expiry.

| Option Type | Typical Theta | Exception |
|---|---|---|
| Long call | Negative | None (always loses value from time) |
| Long put | Negative | Deep ITM European put (positive theta) |
| Short call | Positive | Short positions gain from time decay |
| Short put | Positive | — |

> [!tip] Theta-Gamma Trade-off
> Long options: you pay theta (time decay) but benefit from gamma (convexity). Short options: you collect theta but suffer from gamma risk. This is the fundamental tension in options trading.

---

### 4. Vega ($\nu$) — Volatility Sensitivity

**What it is:** Vega measures how much the option price changes per 1 percentage point increase in implied volatility.

$$\boxed{\nu = \frac{\partial c}{\partial \sigma}}$$

**Sign:** **Both calls and puts have positive vega.** Higher volatility increases the probability of a large favorable move, making both types of options more valuable.

**Moneyness and time:**
- Vega is highest for **ATM options** with **longer time to expiration**
- Deep ITM or OTM options have lower vega — their value is already determined by intrinsic value or is nearly zero

**Why volatility is so important:** The entire value of an out-of-the-money option is time value, and time value is essentially a function of volatility. Volatility is what makes options worth buying at all.

| | Long Option | Short Option |
|---|---|---|
| Volatility rises | Gain | Lose |
| Volatility falls | Lose | Gain |

---

### 5. Rho ($\rho$) — Interest Rate Sensitivity

**What it is:** Rho measures the change in option price per 1 percentage point increase in the risk-free rate.

$$\boxed{\rho = \frac{\partial c}{\partial r}}$$

**Sign:**
- **Calls: positive rho.** A higher risk-free rate reduces the present value of the exercise price (you pay $X$ later, worth less in PV terms), so the call is worth more.
- **Puts: negative rho.** A higher rate reduces the PV of the cash you receive upon exercise.

**When rho matters:**
- Rho is the least important Greek for short-term equity options
- It becomes significant for **long-dated options (LEAPS)** or **interest rate derivatives** such as [[Swaptions|swaptions]] or [[Interest Rate Options|caps and floors]]

---

## Summary Comparison Table

| Factor Increases | Call Value | Put Value | Relevant Greek |
|---|---|---|---|
| Underlying price $S$ ↑ | ↑ | ↓ | $\Delta$ |
| Volatility $\sigma$ ↑ | ↑ | ↑ | $\nu$ (Vega) |
| Time to expiration $T$ ↑ | ↑ | ↑ (usually) | $\Theta$ (negative) |
| Risk-free rate $r$ ↑ | ↑ | ↓ | $\rho$ |
| Exercise price $X$ ↑ | ↓ | ↑ | — |

---

## The Delta-Gamma Approximation

### Formula

The change in option price given a change $\Delta S$ in the underlying:

$$\boxed{\Delta C \approx \Delta \cdot \Delta S + \frac{1}{2} \cdot \Gamma \cdot (\Delta S)^2}$$

This is a second-order Taylor expansion. The first term is the linear delta effect; the second term corrects for curvature.

**Bond analogy:**

$$\Delta P \approx -\text{Duration} \cdot \Delta y + \frac{1}{2} \cdot \text{Convexity} \cdot (\Delta y)^2$$

The structure is identical. Delta = (negative) duration. Gamma = convexity.

### Worked Numerical Example

**Setup:** A 1-year European call. $S_0 = 50$, $X = 50$, $r = 2\%$, $\sigma = 30\%$.

From BSM:
- Call price: $c_0 = 6.411$
- Delta: $\Delta = 0.5858$
- Gamma: $\Gamma = 0.02354$ (computed as $\Delta\Delta / \Delta S$ when $S$ moves to 55)

**Question:** Estimate the new call price if $S$ rises to $55$ ($\Delta S = +5$).

**Step 1 — Delta only (linear approximation):**

$$\Delta_{\text{only}} = 0.5858 \times 5 = 2.929$$
$$\hat{c} = 6.411 + 2.929 = 9.340$$

**Step 2 — Add gamma correction:**

$$\text{Gamma term} = \frac{1}{2} \times 0.02354 \times 5^2 = \frac{1}{2} \times 0.02354 \times 25 = 0.294$$

$$\Delta C \approx 2.929 + 0.294 = 3.223$$
$$\hat{c} = 6.411 + 3.223 = \mathbf{9.634}$$

**Actual BSM price at $S = 55$:** $c = 9.644$

| Method | Estimated Price | Error |
|---|---|---|
| Delta only | 9.340 | −0.304 |
| Delta + Gamma | 9.634 | −0.010 |
| Actual BSM | 9.644 | — |

The gamma correction reduces the error from 0.304 to 0.010 — a 97% improvement.

---

## Delta Hedging — Mechanics

### Constructing a Delta-Neutral Portfolio

To hedge a **short call** position (you wrote the call, so you face losses if the stock rises):

$$\text{Hedge: Buy } \Delta \text{ shares per call written}$$

$$V = \Delta \cdot S - c = 0 \quad \text{(delta-neutral)}$$

**Example:** You wrote 100 calls, each with $\Delta = 0.58$. You must own $100 \times 0.58 = 58$ shares.

### Why You Must Rebalance

Delta drifts as the stock price moves. This is Gamma. Suppose the stock rises:

```
S rises → call goes deeper ITM → Δ increases from 0.58 → 0.65
→ You now hold too few shares (58 shares, need 65)
→ Must buy 7 more shares to stay delta-neutral
```

This continuous rebalancing is called **dynamic delta hedging** or **gamma scalping** (from the option buyer's perspective).

### Gamma Risk — Why the Hedge Is Never Perfect

A delta hedge is only instantaneously neutral. Between rebalancing intervals:

1. **Price drift (Gamma):** If the stock makes a large move, the quadratic term $\frac{1}{2}\Gamma(\Delta S)^2$ creates hedging error that grows with the square of the price move
2. **Time decay (Theta):** Even with no stock movement, delta changes as expiry approaches
3. **Transaction costs:** Continuous rebalancing is theoretically required but practically costly

The hedger faces a **theta-gamma trade-off**:
- Long gamma (long option) → benefits from large moves but pays theta
- Short gamma (short option) → collects theta but bleeds on large moves

> [!example] Gamma Risk at Expiration
> An ATM call with 1 day to expiry has extreme gamma — it has a delta of ~0.5 but will expire at either $\Delta = 0$ (OTM) or $\Delta = 1$ (ITM) depending on a tiny move. A delta-neutral hedger is extremely exposed in this window.

---

## Implied Volatility

### What It Is

[[Implied volatility]] is the value of $\sigma$ that, when plugged into the BSM model, produces the observed market price of the option. It is the market's forward-looking estimate of volatility.

$$\text{Observed market price} \xrightarrow{\text{BSM inverse}} \sigma_{\text{implied}}$$

You cannot solve this analytically — it requires numerical iteration (trial and error).

### The Volatility Smile and Skew

In a perfect BSM world, implied volatility would be constant across all strikes and maturities. In practice, it is not.

**Volatility Smile:** IV is higher for deep ITM and deep OTM options than for ATM options (U-shaped). Common in FX markets.

**Volatility Skew (Smirk):** IV is higher for low-strike (OTM put / ITM call) options than high-strike options. Common in equity markets — investors pay more for downside protection (puts).

```
IV
 |         \
 |          \
 |     ----  \
 |   /       ----
 |  /
 |
 +----------------------------  Strike
   Low        ATM        High
   (OTM put)        (OTM call)
```

**Why the skew exists:**
- Demand for protective puts is high (crash insurance) → OTM puts are bid up → high IV at low strikes
- Equity markets have fat left tails (crashes) — BSM underestimates this risk

### The VIX

The **CBOE VIX** index measures the 30-day implied volatility of S&P 500 options. It is sometimes called the "fear gauge" — it rises during market stress and falls in calm periods.

### How Traders Use Implied Volatility

1. **Relative value:** Compare IV to historical (realized) volatility. If $IV > \sigma_{\text{hist}}$, options are "expensive" — consider selling
2. **Trading volatility directly:** Options traders often trade vol itself, not direction
3. **Pricing derivatives:** IV is the market's consensus input for models

---

## Exam Traps

> [!danger] Top Exam Traps

| Trap | What to Watch For |
|---|---|
| Delta = probability | Delta $\approx$ probability of expiring ITM, but it is not exactly equal to it — $N(d_2)$ is the BSM probability |
| Vega sign | Both calls AND puts have positive vega — a common wrong-answer choice reverses put vega |
| Theta exception | Deep ITM European puts have positive theta — most options have negative theta, but not all |
| Rho for puts | Puts have negative rho — higher rates hurt put values |
| Gamma is always positive for long positions | Short positions have negative gamma |
| Delta-gamma formula | Remember the $\frac{1}{2}$ in front of the gamma term — omitting it is the most common error |
| Gamma peaks ATM | Not at max moneyness — at ATM and near expiry |

---

## Memory Hooks

- **DGTV-R** = Delta, Gamma, Theta, Vega, Rho — "**D**arn **G**reeks **T**ake **V**ery **R**eal time to learn"
- **Delta**: direction — positive for calls, negative for puts
- **Gamma**: always positive for buyers (curvature is always convex), always negative for sellers
- **Theta**: the "rent" you pay for holding an option — almost always negative
- **Vega**: "**V**olatility **V**alue" — both calls and puts gain from higher vol
- **Rho**: "**R**ate **R**ewards calls" — calls benefit from higher rates, puts do not
- **Delta-Gamma approx**: same structure as Duration + Convexity — $\Delta c \approx \Delta \cdot \Delta S + \frac{1}{2}\Gamma(\Delta S)^2$

---

## Related Concepts

- [[Black-Scholes-Merton Model]] — the source of BSM Greeks
- [[Binomial Option Pricing Model]] — binomial delta = $(c^+ - c^-) / (S^+ - S^-)$
- [[Delta Hedging]] — constructing and maintaining delta-neutral portfolios
- [[Implied Volatility]] — backing out $\sigma$ from market prices
- [[Put-Call Parity]] — relationships between call and put Greeks
- [[Swaptions]] — interest rate options where Greeks apply to rate-based payoffs
- [[Interest Rate Options]] — caps, floors, and the Black model
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full treatment of binomial and BSM models
