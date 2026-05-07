---
title: Black-Scholes-Merton Model
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - BSM
  - Black-Scholes
  - option-pricing
  - European-options
  - no-arbitrage
aliases:
  - BSM
  - Black-Scholes
  - Black-Scholes-Merton
  - BSM model
  - option valuation model
---

# Black-Scholes-Merton Model

## The Real-World Analogy

Imagine you want to price a bet on whether a coin will land heads or tails — but it's not a fair coin, and you don't know exactly how biased it is. Fischer Black, Myron Scholes, and Robert Merton solved the analogous problem for options: given a stock that moves randomly (but with known volatility), what is the fair price today for the right to buy it at a fixed price in the future?

Their breakthrough was showing that you can construct a **perfectly hedged portfolio** — combining an option with shares of the stock — that earns exactly the risk-free rate. This no-arbitrage condition pins down the exact option price. The result is the BSM formula.

## Plain-English Definition

The **Black-Scholes-Merton (BSM) model** is a closed-form formula that gives the no-arbitrage price of European call and put options on stocks. It is the limiting case of the [[Binomial Option Pricing Model|binomial model]] as the time step approaches zero.

The model says: if you can continuously rebalance a hedge between the option and the stock, the option's price must satisfy a specific partial differential equation. Solving it gives the BSM formula.

---

## Why CFA Tests This

The LOS requires you to:
- *"Identify assumptions of the Black-Scholes-Merton option valuation model"*
- *"Interpret the components of the BSM model as applied to call options in terms of a leveraged position in the underlying"*
- *"Describe how the BSM model is used to value European options on equities and currencies"*

The exam tests assumptions (and what breaks when they fail), the formula interpretation, and adjustments for dividends and currency options.

---

## The BSM Assumptions

### The Six Core Assumptions

| Assumption | What It Says | What Breaks When It Fails |
|---|---|---|
| **Geometric Brownian Motion** | Asset prices move continuously, no jumps; lognormally distributed | Price jumps (earnings, mergers, crashes) create [[Option Greeks#Gamma Risk|gamma risk]] — delta hedge instantly wrong |
| **Constant, known volatility** | $\sigma$ is fixed over the option's life | Reality: volatility is stochastic → explains the [[Implied Volatility#The Volatility Smile and Skew|volatility smile/skew]] that BSM cannot produce |
| **Constant, known risk-free rate** | $r$ is continuous and fixed | Rate changes affect option value (measured by rho) |
| **No frictions** | No transaction costs, taxes, or short-selling restrictions | High transaction costs make continuous delta-hedging impractical |
| **European-style options** | No early exercise permitted | BSM understates value of American calls on dividend-paying stocks and deep ITM American puts |
| **No dividends** | Underlying pays no cash flows during option's life | Adjusted with dividend yield modification (see below) |

> [!important] Why Lognormal?
> Stock prices cannot go below zero (limited liability). The log-normal distribution respects this because $\ln(S)$ can be any real number (positive or negative), so $S = e^{\ln(S)}$ is always positive. A normal distribution for prices would allow negative prices, which is impossible.

---

## The BSM Formulas

### European Call Price

$$\boxed{c = S \cdot N(d_1) - X \cdot e^{-rT} \cdot N(d_2)}$$

### European Put Price

$$\boxed{p = X \cdot e^{-rT} \cdot N(-d_2) - S \cdot N(-d_1)}$$

### The $d_1$ and $d_2$ Terms

$$d_1 = \frac{\ln(S/X) + \left(r + \frac{\sigma^2}{2}\right)T}{\sigma\sqrt{T}}$$

$$d_2 = d_1 - \sigma\sqrt{T}$$

### All Variables Defined

| Symbol | Meaning |
|---|---|
| $S$ | Current stock price |
| $X$ | Exercise (strike) price |
| $r$ | Continuously compounded risk-free rate |
| $T$ | Time to expiration (in years) |
| $\sigma$ | Annual volatility of the underlying's returns |
| $N(\cdot)$ | Cumulative standard normal CDF |
| $e^{-rT}$ | Discount factor |

> [!warning] Continuously Compounded Rate
> BSM requires the continuously compounded risk-free rate. If given an annual rate of 5%, the continuously compounded equivalent is $\ln(1.05) \approx 4.879\%$. Using the wrong convention is a common exam error.

---

## Interpreting the BSM Formula — The Leveraged Position

The BSM call price can be read as:

$$c = \underbrace{S \cdot N(d_1)}_{\text{Stock component}} - \underbrace{X \cdot e^{-rT} \cdot N(d_2)}_{\text{Bond component (borrowed)}}$$

**This is the cost of replicating the call option by:**

1. **Buying $N(d_1)$ shares** of the stock
2. **Borrowing $X \cdot e^{-rT} \cdot N(d_2)$** (the PV of what you'd pay at expiry if exercised)

The call option is equivalent to a **leveraged long position in the stock** — you own a fraction of a share, funded partly by borrowing. The premium you pay ($c$) is the equity component of this levered trade.

**Why "leveraged"?** You spend $c$ but control a position worth $S \cdot N(d_1)$ in shares, with borrowed funds making up the rest. The ratio $S \cdot N(d_1) / c$ is the effective leverage.

### The Meaning of $N(d_1)$ and $N(d_2)$

| Term | Meaning | Greek Connection |
|---|---|---|
| $N(d_1)$ | **Delta** — the hedge ratio; number of shares to replicate the option | $\Delta = N(d_1)$; see [[N(d1)]] |
| $N(d_2)$ | **Risk-neutral probability** that the call expires in the money ($S_T > X$) | Related to $N(-d_2) = $ probability put expires ITM; see [[N(d2)]] |

> [!warning] Exam Trap — $N(d_1)$ vs $N(d_2)$
> $N(d_2)$ is the probability of expiring ITM; $N(d_1)$ is the hedge ratio (delta). They are NOT the same. $d_1 > d_2$ always (since $d_1 = d_2 + \sigma\sqrt{T}$), so $N(d_1) > N(d_2)$ always. The extra $\sigma\sqrt{T}$ in $d_1$ accounts for the fact that the expected stock price, conditional on expiring ITM, is higher than just the probability-weighted value.

---

## Worked Numerical Example

**Setup:** ATM European call and put.

$S = 100$, $X = 100$, $r = 5\%$ (continuously compounded), $T = 1.0$ year, $\sigma = 30\%$

**Step 1 — Compute $d_1$:**

$$d_1 = \frac{\ln(100/100) + (0.05 + 0.30^2/2)(1.0)}{0.30\sqrt{1.0}} = \frac{0 + 0.05 + 0.045}{0.30} = \frac{0.095}{0.30} = 0.3167$$

**Step 2 — Compute $d_2$:**

$$d_2 = 0.3167 - 0.30\sqrt{1.0} = 0.3167 - 0.30 = 0.0167$$

**Step 3 — Look up cumulative normal probabilities:**

$$N(d_1) = N(0.3167) = 0.624$$
$$N(d_2) = N(0.0167) = 0.507$$
$$N(-d_1) = 1 - 0.624 = 0.376$$
$$N(-d_2) = 1 - 0.507 = 0.493$$

**Step 4 — Call price:**

$$c = 100 \times 0.624 - 100 \times e^{-0.05} \times 0.507$$
$$= 62.40 - 95.12 \times 0.507 = 62.40 - 48.23 = \mathbf{\$14.17}$$

**Step 5 — Put price:**

$$p = 100 \times e^{-0.05} \times 0.493 - 100 \times 0.376$$
$$= 95.12 \times 0.493 - 37.60 = 46.90 - 37.60 = \mathbf{\$9.30}$$

**Verify with put-call parity:**

$$c - p = S - X \cdot e^{-rT}$$
$$14.17 - 9.30 = 4.87$$
$$100 - 100 \times e^{-0.05} = 100 - 95.12 = 4.88 \checkmark$$

**Interpretation:**
- Call delta = 0.624: each call behaves like owning 0.624 shares
- Probability of expiring ITM = 50.7% (barely above 50% — ATM with small positive drift from $r$)
- The call "replication": buy 0.624 shares at $100 = $62.40, borrow $48.23 at 5%, net cost = $14.17

---

## Adjustments for Carry Benefits

When the underlying asset provides cash flows or benefits that reduce the expected future price, $S$ is replaced by $S \cdot e^{-\gamma T}$ where $\gamma$ is the carry benefit yield.

### Equities with Dividend Yield ($\gamma = \delta$)

$$c = S \cdot e^{-\delta T} \cdot N(d_1) - X \cdot e^{-rT} \cdot N(d_2)$$

Modified $d_1$:

$$d_1 = \frac{\ln(S/X) + (r - \delta + \frac{\sigma^2}{2})T}{\sigma\sqrt{T}}$$

**Intuition:** Dividends reduce the stock price (ex-dividend). The forward price of the stock is $S \cdot e^{(r-\delta)T}$ rather than $S \cdot e^{rT}$. A higher dividend yield → lower call value, higher put value.

### Currency Options ($\gamma = r_f$, the foreign interest rate)

$$c = S \cdot e^{-r_f T} \cdot N(d_1) - X \cdot e^{-r T} \cdot N(d_2)$$

Where $r$ is the domestic rate and $r_f$ is the foreign rate. This is the **Garman-Kohlhagen model** — the CFA curriculum covers it as a BSM extension.

**Intuition:** Holding foreign currency earns the foreign risk-free rate — this is the "dividend" of holding currency. It reduces the call value on foreign currency for the same reason dividends reduce equity call value.

### Generalized Formula

$$d_1 = \frac{\ln(S/X) + (r - \gamma + \frac{\sigma^2}{2})T}{\sigma\sqrt{T}}$$

| Asset type | $\gamma$ |
|---|---|
| Non-dividend stock | 0 |
| Dividend-paying stock | $\delta$ (dividend yield) |
| Currency | $r_f$ (foreign interest rate) |
| Futures | $r$ (cost of carry = 0 → this gives the Black model) |

---

## BSM vs. Binomial Model — Key Comparison

| | BSM | Binomial |
|---|---|---|
| **Time** | Continuous | Discrete (finite steps) |
| **Option style** | European only | European and American |
| **Formula** | Closed-form | Backward induction |
| **Early exercise** | Cannot handle | Can handle (compare exercise vs. hold) |
| **Dividends** | Via yield adjustment | Via escrow/discrete dividends |
| **Convergence** | BSM is the limit as binomial steps → ∞ | Approaches BSM with enough steps |

---

## Exam Traps

> [!danger] Key BSM Exam Traps

| Trap | Correct Understanding |
|---|---|
| $N(d_1)$ = probability of expiring ITM | $N(d_2)$ is the probability; $N(d_1)$ is the delta (hedge ratio) |
| Plug in periodic compounding rate | Must use **continuously compounded** rate |
| BSM works for American options | BSM is for **European options only** — use binomial for American options |
| Dividends don't affect BSM | Dividend yield $\delta$ lowers $d_1$ and the effective stock price — reduces call, increases put |
| Call is cheap if $IV < \sigma_{hist}$ | Low IV could mean the option is fairly priced if future vol is also expected to be low |
| BSM prices increase with volatility for all options | True for both calls and puts (positive vega) — but sometimes confused with signs |
| For currency: use only domestic rate | Need both rates: domestic $r$ for discounting the strike, foreign $r_f$ as the carry benefit |

---

## Memory Hooks

- **BSM = continuous binomial**: as the time step → 0, the binomial model converges to BSM
- **Call = stock component − bond component**: $S \cdot N(d_1)$ minus $PV(X) \cdot N(d_2)$
- **$N(d_1)$ = delta (hedge ratio)**: $N(d_2)$ = probability of expiring ITM
- **$d_1$ > $d_2$ always**: by exactly $\sigma\sqrt{T}$
- **Carry benefits reduce calls, boost puts**: dividends or foreign rates lower the effective forward price
- **"CLVS" assumptions**: Continuous prices, Lognormal distribution, Volatility constant, Short-selling allowed

---

## Related Concepts

- [[Binomial Option Pricing Model]] — discrete precursor; converges to BSM as steps → ∞
- [[Option Greeks]] — all Greeks (delta, gamma, theta, vega, rho) derived from BSM
- [[Implied Volatility]] — the BSM is inverted to back out market's implied $\sigma$
- [[Delta Hedging and Gamma Risk]] — the BSM hedge ratio $N(d_1)$ forms the delta hedge
- [[Swaptions]] — Black model (an extension of BSM) values interest rate swaptions
- [[Interest Rate Options — Caps and Floors]] — Black model again; same conceptual framework
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full module including binomial and BSM
