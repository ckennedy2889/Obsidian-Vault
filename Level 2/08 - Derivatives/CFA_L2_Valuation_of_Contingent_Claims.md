---
title: "CFA_L2_Valuation_of_Contingent_Claims"
subject: "Derivatives"
tags: [CFA-L2, derivatives]
aliases: []
---

# Valuation of Contingent Claims

> **CFA Level 2 — [[Derivatives|Derivatives]] (Volume 7, Learning Module 2)**
> *2025 Curriculum*

---

## Overview

A [[contingent claim]] is a [[Derivative]] instrument that gives its owner a **right but not an obligation** to a payoff determined by an [[underlying asset]], rate, or other [[Derivative|derivative]]. The most common [[Contingent claims|contingent claims]] are [[options]]. Because many investments contain [[Embedded options]], understanding option [[Valuation|valuation]] is vital for [[investment management]].

All [[option valuation models]] are built on the principle of [[no-arbitrage]] — the appropriate price of an option is the one that makes it impossible for any party to earn an [[Arbitrage]] profit at the expense of any other party.

---

## 1. The Binomial Option Valuation Model

### 1.1 What Is the Binomial Model?

The [[Binomial model]] is a discrete-time framework where the [[Underlying]] can move to only **two** possible values in each period — an **up move** or a **down move**. It is particularly useful for:

- Valuing [[path-dependent options]] (options whose values depend on *how* the [[Underlying]] got to its final price, not just the final price itself)
- Valuing [[American options]] (which can be [[early exercise|exercised early]])
- Understanding the intuition behind all [[option pricing]]

> **Real-World Example:** Imagine you own stock in a biotech company awaiting FDA approval. In one month, the stock will either jump to $80 (approval) or fall to $40 (rejection). There are only two outcomes — a natural binomial setting. An [[Option]] on this stock can be priced by figuring out how to replicate its payoff using just the stock and a [[risk-free bond]].

### 1.2 Key Assumptions

Throughout the [[Binomial model]], these assumptions hold:

1. [[Replicating instruments]] are identifiable and investable
2. [[Market frictions]] (transaction costs, taxes) are zero
3. [[Short selling]] is allowed with full use of proceeds
4. The [[Underlying]] price follows a known distribution
5. [[Borrowing]] and [[lending]] is available at a known [[risk-free rate]]

### 1.3 The Arbitrageur's Rules

The model is built on a [[no-arbitrage]] approach. The [[arbitrageur]] follows two rules:

| Rule | Description |
|------|-------------|
| **Rule 1** | Do not use your own money. Do not spend proceeds from [[Short selling]] on unrelated activities. |
| **Rule 2** | Do not take any [[market price risk]] related to the [[Underlying]] or [[Level 2/08 - Derivatives/Derivatives]]. |

### 1.4 Option Payoffs at Expiration

At [[expiration]], option values equal their [[Intrinsic value]] (also called [[Exercise value]]):

$$c_T = \max(0, S_T - X)$$

$$p_T = \max(0, X - S_T)$$

Where:
- $c_T$ = [[Call option]] value at [[expiration]]
- $p_T$ = [[Put option]] value at [[expiration]]
- $S_T$ = [[Underlying]] price at [[expiration]]
- $X$ = [[Exercise price]] (also called [[strike price]])

The difference between the [[Option]] market price and its [[Intrinsic value]] is called [[Time value]]. At [[expiration]], [[Time value]] is always zero.

---

## 2. One-Period Binomial Model

### 2.1 The Setup

```
            S⁺ = uS    (up move)
           /
    S ----
           \
            S⁻ = dS    (down move)
    
    Time 0          Time 1
```

Where:
- $S$ = current price of the [[Underlying]]
- $u$ = [[up factor]] (e.g., 1.35 means the stock rises 35%)
- $d$ = [[down factor]] (e.g., 0.74 means the stock falls 26%)
- $S^+ = uS$ = price after an up move
- $S^- = dS$ = price after a down move

### 2.2 The No-Arbitrage Approach

The idea is to build a [[replicating portfolio]] — a combination of the [[Underlying]] and [[risk-free bond|borrowing/lending]] that exactly matches the option's payoff in both states.

**Step 1: Calculate the [[Hedge ratio]]** (h):

$$h = \frac{c^+ - c^-}{S^+ - S^-}$$

The [[Hedge ratio]] tells you how many shares of the [[Underlying]] to buy (for a [[Call option|call]]) to replicate the option's payoff.

**Step 2: Value the option:**

$$c = hS + PV(-hS^- + c^-)$$

Where $PV$ means [[present value]] using the [[risk-free rate]].

> **Real-World Example:** A stock trades at €100. In one year it will be either €135 (up) or €74 (down). The [[risk-free rate]] is 5.15% and the [[Exercise price]] is €100.
>
> - $c^+ = \max(0, 135 - 100) = 35$
> - $c^- = \max(0, 74 - 100) = 0$
> - $h = (35 - 0)/(135 - 74) = 0.5738$
>
> You replicate the [[Call option|call]] by buying 0.5738 shares and borrowing the right amount. The [[Call option|call]] value works out to **€17.00**.

### 2.3 The Expectations Approach

An equivalent way to value the option uses [[risk-neutral probability|risk-neutral probabilities]]:

$$\pi = \frac{FV(1) - d}{u - d} = \frac{(1 + r) - d}{u - d}$$

Then:

$$c = PV[\pi c^+ + (1 - \pi)c^-]$$

$$p = PV[\pi p^+ + (1 - \pi)p^-]$$

**Key points about the [[Expectations approach]]:**

- The probability $\pi$ is **not** the actual probability of an up move — it is the [[risk-neutral probability]]
- The [[Discount rate]] is the [[risk-free rate]], **not** a [[risk-adjusted rate]]
- Both the [[No-arbitrage approach]] and [[Expectations approach]] give the **same** answer

> **Real-World Example:** Using the same numbers as above:
> - $\pi = (1.0515 - 0.74)/(1.35 - 0.74) = 0.5107$
> - $c = \frac{1}{1.0515}[0.5107 \times 35 + 0.4893 \times 0] = €17.00$ ✓

### 2.4 Put–Call Parity

[[Put-call parity]] connects the values of [[Call option|calls]] and [[Put option|puts]] with the same [[Exercise price]] and [[expiration]]:

$$S + p = PV(X) + c$$

You can rearrange this to find a [[Put option|put]] value from a known [[Call option|call]] value, or vice versa.

> **Real-World Example:** If the €100-strike [[Call option|call]] is worth €17.00, the stock is €100, and $PV(X) = 100/1.0515 = 95.10$, then:
> $p = PV(X) + c - S = 95.10 + 17.00 - 100 = €12.10$

---

## 3. Two-Period Binomial Model

### 3.1 Structure

The [[two-period binomial model]] is just **three [[one-period binomial model|one-period models]]** stitched together. You work **backward** through the tree.

```
                        S⁺⁺ = u²S
                       /
              S⁺ = uS
             /         \
    S ------             S⁺⁻ = udS = S⁻⁺
             \         /
              S⁻ = dS
                       \
                        S⁻⁻ = d²S

    Time 0    Time 1      Time 2
```

The lattice **recombines** — $S^{+-} = S^{-+}$ — which is computationally efficient.

Two critical concepts:
- **[[Self-financing]]**: The [[replicating portfolio]] requires no additional funds during the life of the strategy
- **[[Dynamic replication]]**: The option payoffs are exactly replicated through a planned trading strategy that is rebalanced at each node

### 3.2 Calculation Process (Calls)

**Step 1:** Calculate option payoffs at Time 2:
- $c^{++} = \max(0, S^{++} - X)$
- $c^{+-} = \max(0, S^{+-} - X)$
- $c^{--} = \max(0, S^{--} - X)$

**Step 2:** Work backward to Time 1 values using the [[Expectations approach]]:
- $c^+ = PV[\pi c^{++} + (1-\pi)c^{+-}]$
- $c^- = PV[\pi c^{+-} + (1-\pi)c^{--}]$

**Step 3:** Work backward to Time 0:
- $c = PV[\pi c^+ + (1-\pi)c^-]$

Or equivalently for [[European options]], directly:

$$c = \frac{\pi^2 c^{++} + 2\pi(1-\pi)c^{+-} + (1-\pi)^2 c^{--}}{(1+r)^2}$$

> **Real-World Example:** Consider an oil company stock at $72 with $X = 75$, $u = 1.356$, $d = 0.541$, $r = 3\%$ per period.
>
> - $S^{++} = 72 \times 1.356^2 = 132.39$ → $c^{++} = 57.39$
> - $S^{+-} = 72 \times 1.356 \times 0.541 = 52.82$ → $c^{+-} = 0$
> - $S^{--} = 72 \times 0.541^2 = 21.07$ → $c^{--} = 0$
> - $\pi = (1.03 - 0.541)/(1.356 - 0.541) = 0.60$
>
> Working backward: $c^+ = \frac{0.60 \times 57.39 + 0.40 \times 0}{1.03} = 33.43$
>
> Then: $c = \frac{0.60 \times 33.43 + 0.40 \times 0}{1.03} = \$19.47$

### 3.3 Identifying Arbitrage

If the market price of the option **differs** from the model value, an [[Arbitrage]] opportunity exists:

- **Option is overpriced**: Sell the option, buy the [[replicating portfolio]] (buy $h$ shares, borrow)
- **Option is underpriced**: Buy the option, sell the [[replicating portfolio]] ([[Short selling|short sell]] $h$ shares, lend)

> **Real-World Example:** If the model says a call is worth $3.71 but the market price is $4.50, you sell the call at $4.50, replicate it for $3.71, and pocket $0.79 in [[Arbitrage]] profit with zero risk.

### 3.4 Two-Period Put Options & American Options

For [[European put options|European puts]], the same backward process works. But for [[American options]], you must check at **every node** whether [[early exercise]] is more valuable than holding:

$$\text{American option value at node} = \max(\text{Exercise value}, \text{Model value})$$

The difference between the [[American option]] value and the [[European option]] value is the [[early exercise premium]].

> **Real-World Example:** Imagine a [[Put option]] on a stock at $26 with $X = 25$. If the stock drops to $17.06 after one period, the [[Exercise value]] is $\max(0, 25 - 17.06) = 7.94$, but the model value (holding to [[expiration]]) is only $7.44. You exercise early, capturing $0.50 more. This is why [[American put options]] can be worth more than their [[European option|European]] counterparts.

### 3.5 Role of Dividends (Escrow Method)

[[Dividends]] lower the stock price, hurting [[Call option|call]] holders. The [[escrow method]] splits the stock into:

$$\hat{S} = S - \gamma$$

Where $\gamma$ = [[present value]] of [[dividends]]. The [[Binomial model]] is then applied to $\hat{S}$ (the stock value *without* [[dividends]]). At [[expiration]], $\hat{S}_T = S_T$ since [[dividends]] have already been paid.

[[Dividends]] can motivate [[early exercise]] of [[American call options]] — the holder exercises just before the [[Ex-dividend date]] to capture the [[Dividend]].

---

## 4. Interest Rate Options and the Binomial Model

### 4.1 Key Differences

[[Interest rate options]] require a full [[term structure of interest rates]], not just a single [[risk-free rate]]. Key features:

- The [[Underlying]] is the [[Spot rate]] (or a [[Forward rate]])
- [[Interest rate call option]]: [[In the money|in the money]] when the [[Spot rate]] > [[exercise rate]]
- [[Interest rate put option]]: [[In the money|in the money]] when the [[Spot rate]] < [[exercise rate]]
- The [[risk-neutral probability]] at each node is typically assumed to be **50%**

### 4.2 Binomial Interest Rate Tree

Instead of modeling stock prices, we model a lattice of [[interest rates]] with corresponding [[Zero-coupon bond]] values at each node. The process is the same: work backward through the tree, discounting at the **node-specific rate** (not a constant rate).

> **Real-World Example:** A bank wants to price a [[Cap]] on a variable-rate loan. The current 1-year rate is 3.05%. In one year, rates could be 2.60% (down) or 3.91% (up). In two years, rates could be 2.26%, 3.25%, or 3.97%. The bank prices each [[Caplet]] by working backward through this tree, discounting at each node's rate.

---

## 5. The Multiperiod Model → BSM Bridge

As you increase the number of time steps in the [[Binomial model]] (slicing [[expiration]] into smaller and smaller periods), the model converges to the [[Black-Scholes-Merton model|BSM model]]. The [[binomial distribution]] with many steps converges to the [[Normal distribution]], which is the foundation of [[BSM model|BSM]].

---

## 6. Black–Scholes–Merton (BSM) Option Valuation Model

### 6.1 Assumptions

The [[BSM model]] assumes:

| Assumption | Description |
|-----------|-------------|
| [[Geometric Brownian Motion]] (GBM) | The [[Underlying]] follows GBM, implying [[continuously compounded returns]] are [[normally distributed]] |
| Continuous prices | No jumps — the price moves smoothly |
| [[Liquidity]] | The [[Underlying]] can be easily bought and sold |
| Continuous trading | Trading is possible at every instant |
| [[Short selling]] | Allowed with full use of proceeds |
| No [[market frictions]] | No [[transaction costs]], taxes, or regulatory constraints |
| No [[Arbitrage]] | No [[Arbitrage]] opportunities exist |
| [[European options]] only | No [[early exercise]] |
| Constant [[risk-free rate]] | Known and constant; [[borrowing]] and [[lending]] at this rate |
| Constant [[Volatility]] | The [[Volatility]] of the [[Underlying]]'s return is known and constant |
| Constant [[Dividend yield]] | If the [[Underlying]] pays income, it is a known continuous yield |

> **Real-World Example:** Think of [[GBM]] like this: if Apple stock is at $150 and has 30% annual [[Volatility]], a 10% move means $15. If Apple drifts up to $300, a 10% move is $30 — the absolute size of moves scales with the price level. The stock can never hit zero under GBM, which makes sense for [[limited liability]] companies.

### 6.2 The BSM Formulas

**For a non-[[Dividend]]-paying stock:**

$$c = S \cdot N(d_1) - e^{-rT} X \cdot N(d_2)$$

$$p = e^{-rT} X \cdot N(-d_2) - S \cdot N(-d_1)$$

Where:

$$d_1 = \frac{\ln(S/X) + (r + \sigma^2/2)T}{\sigma\sqrt{T}}$$

$$d_2 = d_1 - \sigma\sqrt{T}$$

- $N(\cdot)$ = [[cumulative standard normal distribution]] function
- $\sigma$ = [[Volatility]] (annualized [[Standard deviation]] of [[log returns]])
- $T$ = time to [[expiration]] (in years)
- $r$ = continuously compounded [[risk-free rate]]

### 6.3 Interpreting the BSM Components

The [[BSM model]] has a **stock component** and a **bond component**:

| Component | Calls | Puts |
|-----------|-------|------|
| Stock component | $S \cdot N(d_1)$ | $S \cdot N(-d_1)$ |
| Bond component | $e^{-rT}X \cdot N(d_2)$ | $e^{-rT}X \cdot N(-d_2)$ |
| Option value | Stock − Bond | Bond − Stock |

**As a [[replicating portfolio]]:**

$$\text{Option value} = n_S \cdot S + n_B \cdot B$$

| | Calls | Puts |
|--|-------|------|
| $n_S$ (shares) | $+N(d_1)$ → **buy** stock | $-N(-d_1)$ → **[[Short selling|short sell]]** stock |
| $n_B$ (bonds) | $-N(d_2)$ → **borrow** | $+N(-d_2)$ → **lend** |

**Key interpretation:** A [[Call option]] is a **[[leveraged position]]** in the stock — you are buying stock with borrowed money. A short [[Put option]] is an **over-[[leveraged position]]** because the borrowing exceeds 100% of the stock cost.

**What $N(d_1)$ and $N(d_2)$ tell us:**

- $N(d_1)$: The number of shares needed to replicate the option; the primary determinant of [[Delta]]; how much the option changes for a small change in $S$
- $N(d_2)$: The number of [[Zero-coupon bonds]] to trade; the basis for the [[risk-neutral probability]] that the option expires [[In the money]]

### 6.4 BSM with Carry Benefits (Equities & Currencies)

**For [[Dividend]]-paying stocks** (continuous [[Dividend yield]] $\delta$):

$$c = Se^{-\delta T}N(d_1) - Xe^{-rT}N(d_2)$$

$$p = Xe^{-rT}N(-d_2) - Se^{-\delta T}N(-d_1)$$

With:

$$d_1 = \frac{\ln(S/X) + (r - \delta + \sigma^2/2)T}{\sigma\sqrt{T}}$$

Higher [[dividends]] → lower [[Call option|call]] value, higher [[Put option|put]] value.

**For [[currency options]]** — the [[carry benefit]] $\gamma$ is the foreign [[risk-free rate]] ($r_f$):

$$c = Se^{-r_fT}N(d_1) - Xe^{-rT}N(d_2)$$

> **Real-World Example:** A Japanese camera exporter receives euros and worries the yen will strengthen. The [[Spot rate|spot rate]] is 135 ¥/€. To value a [[Put option]] on the euro (which is a [[Call option|call]] on the yen), the [[risk-free rate]] is the domestic (Japanese) rate of 0.25%, and the [[carry benefit]] is the foreign (European) rate of 1.00%.

---

## 7. The Black Model

### 7.1 European Options on Futures

The [[Black model]] (1976) is a modification of [[BSM model|BSM]] for [[Underlying|underlyings]] that are **costless to carry** — primarily [[futures contracts]], [[forward contracts]], and [[interest rate options]].

$$c = e^{-rT}[F_0(T) \cdot N(d_1) - X \cdot N(d_2)]$$

$$p = e^{-rT}[X \cdot N(-d_2) - F_0(T) \cdot N(-d_1)]$$

Where:

$$d_1 = \frac{\ln[F_0(T)/X] + (\sigma^2/2)T}{\sigma\sqrt{T}}, \quad d_2 = d_1 - \sigma\sqrt{T}$$

- $F_0(T)$ = current [[Futures price]] expiring at $T$

The [[Black model]] is identical to [[BSM model|BSM]] except the [[Futures price]] replaces the [[Spot price]], and there is no carry cost adjustment.

### 7.2 Interest Rate Options

[[Interest rate options]] use a modified [[Black model]] where:

- The [[Underlying]] is a [[Forward rate agreement|FRA]] rate
- There is an **[[accrual period]]** adjustment
- There is an [[Underlying]] [[Notional amount]]
- Care must be given to [[day-count conventions]]

$$c = (AP) \cdot e^{-r(t_{j-1}+t_m)}[FRA(0, t_{j-1}, t_m) \cdot N(d_1) - R_X \cdot N(d_2)]$$

$$p = (AP) \cdot e^{-r(t_{j-1}+t_m)}[R_X \cdot N(-d_2) - FRA(0, t_{j-1}, t_m) \cdot N(-d_1)]$$

Where $AP$ = [[accrual period]] in years, $R_X$ = [[exercise rate]].

**Key relationships:**

| Structure | Definition |
|-----------|------------|
| [[Interest rate cap]] | A portfolio of [[interest rate call options]] called [[caplets]], each with the same [[exercise rate]] and sequential maturities |
| [[Interest rate floor]] | A portfolio of [[interest rate put options]] called [[floorlets]], each with the same [[exercise rate]] and sequential maturities |
| Long [[Floor]] + Short [[Cap]] | = Receive [[fixed rate|fixed]], pay [[floating rate|floating]] [[Interest rate swap|swap]] |
| If $R_X$ = [[Swap rate]] | Then $V_{\text{cap}} = V_{\text{floor}}$ → net cost = 0 |

> **Real-World Example:** A company with a $50 million floating-rate loan buys an [[interest rate cap]] at 5% to protect against rising rates. The [[Cap]] is really a series of [[caplets]] — one for each reset date. Each [[Caplet]] pays the company when the reference rate exceeds 5% on that date. It's like buying insurance on each individual interest payment.

### 7.3 Swaptions

A [[swaption]] is an option on an [[Interest rate swap|swap]]:

| Type | Right to enter a swap to... |
|------|----------------------------|
| [[Payer swaption]] | Pay [[fixed rate|fixed]], receive [[floating rate|floating]] |
| [[Receiver swaption]] | Receive [[fixed rate|fixed]], pay [[floating rate|floating]] |

**[[Valuation|Valuation]]:**

$$\text{Payer SWN} = [R_{\text{fix}} \cdot N(d_1) - R_X \cdot N(d_2)] \times PVA$$

$$\text{Receiver SWN} = [R_X \cdot N(-d_2) - R_{\text{fix}} \cdot N(-d_1)] \times PVA$$

Where:
- $R_{\text{fix}}$ = current forward [[Swap rate]]
- $R_X$ = [[exercise rate]] (the pre-agreed [[Swap rate|swap rate]])
- $PVA$ = [[present value]] of an annuity corresponding to the swap payments

**Important relationship:** Long a [[Callable bond|callable fixed-rate bond]] = Long a straight [[fixed-rate bond]] + Short a [[receiver swaption]]

> **Real-World Example:** A corporate treasurer expects to need a 5-year fixed-rate loan in 3 months but worries rates will rise. She buys a [[payer swaption]] expiring in 3 months at a 2.65% strike. If rates rise above 2.65%, she exercises and locks in borrowing at 2.65%. If rates fall, she lets the [[swaption]] expire and borrows at the lower market rate.

---

## 8. Option Greeks

The [[Greeks]] measure how sensitive an [[Option]] value is to changes in various factors. They are **static risk measures** — each measures the effect of changing one factor while holding everything else constant.

### 8.1 Delta (Δ)

[[Delta]] = the change in [[Option]] value for a small change in the [[Underlying]] price.

| Position | Delta |
|----------|-------|
| Long stock | +1.0 |
| Short stock | −1.0 |
| Long [[call option\|call]] | Between 0 and +1 (= $N(d_1)$ for [[European options|European]] with no [[dividends]]) |
| Long [[put option\|put]] | Between −1 and 0 (= $-N(-d_1)$) |
| At expiration (ITM) | Call: +1, Put: −1 |
| At expiration (OTM) | 0 |

**Key relationship:** For a given [[Exercise price]], $|\Delta_c| + |\Delta_p| = 1.0$ (approximately, for [[European options]] on non-[[Dividend]] paying stocks via [[put-call parity]]).

**[[Delta approximation]]:**

$$\hat{c} - c \approx \Delta_c(\hat{S} - S)$$

This is a **linear** approximation of a **non-linear** relationship, so it works well only for small moves in $S$.

> **Real-World Example:** You own a [[Call option|call]] on Tesla with [[Delta]] = 0.60. If Tesla's stock rises $1, your option rises roughly $0.60. If Tesla drops $2, your option drops about $1.20. But for a $20 move, the [[delta approximation]] becomes less accurate because of the option's [[Curvature|curvature]] ([[Gamma]]).

### 8.2 Delta Hedging

[[Delta hedging]] neutralizes exposure to the [[Underlying]]:

$$N_H = \frac{-\text{Portfolio delta}}{\Delta_H}$$

Where $N_H$ = number of [[Hedging]] units and $\Delta_H$ = [[Delta]] of the hedging instrument.

A [[delta neutral]] portfolio has a total [[Delta]] of zero.

> **Real-World Example:** You are short [[Put option|puts]] on 10,000 shares of a stock. $\Delta_p = -0.419$, so your portfolio [[Delta]] = $-10{,}000 \times (-0.419) = +4{,}190$ (positive because you're *short* a negative-delta instrument).
>
> **Hedge with stock:** Short 4,190 shares (each with $\Delta = 1$)
>
> **Hedge with calls:** Short $4{,}190 / 0.532 = 7{,}876$ calls

### 8.3 Gamma (Γ)

[[Gamma]] = the change in [[Delta]] for a small change in the [[Underlying]] price. It measures the **[[Curvature|curvature]]** of the option price vs. the stock price.

| Property | Detail |
|----------|--------|
| $\Gamma_c = \Gamma_p$ | [[Gamma]] is the same for [[call option\|calls]] and [[put option\|puts]] at the same strike |
| Long options | Positive [[Gamma]] |
| Short options | Negative [[Gamma]] |
| Stock | [[Gamma]] = 0 (because stock [[Delta]] is always 1) |
| [[At-the-money options\|ATM]], near expiration | [[Gamma]] is highest |

**[[Delta-plus-gamma approximation]]:**

$$\hat{c} - c \approx \Delta_c(\hat{S} - S) + \frac{1}{2}\Gamma_c(\hat{S} - S)^2$$

This corrects for the error in the [[delta approximation]] by accounting for [[Curvature|curvature]].

### 8.4 Gamma Risk

[[Gamma risk]] is the risk that the [[Underlying]] price **jumps** rather than moves smoothly, leaving you suddenly un-hedged. Under the [[BSM model]] assumption of continuous trading, there would be no [[gamma risk]]. In reality, prices *do* jump, creating this risk.

- Buying options **increases** portfolio [[Gamma]]
- Selling options **decreases** portfolio [[Gamma]]
- A [[gamma neutral]] portfolio minimizes exposure to large price jumps

> **Real-World Example:** A market maker sells [[Call option|calls]] on an S&P 500 [[ETF]] and [[Delta]] hedges with [[futures]]. If the index suddenly drops 5% on a flash crash, [[Delta]] changes dramatically, and the hedge is no longer effective. The loss from this mismatch is [[gamma risk]]. Buying back some options would reduce this risk.

### 8.5 Theta (Θ)

[[Theta]] = the change in [[Option]] value for a small change in calendar time (i.e., time passing), holding everything else constant.

| Position | Theta |
|----------|-------|
| Long options | Negative (options lose value as time passes) |
| Short options | Positive (benefit from [[time decay]]) |
| Stock | 0 |

[[Theta]] is fundamentally different from [[Delta]] and [[Gamma]] — the passage of time involves **no uncertainty**. [[Time decay]] accelerates as [[expiration]] approaches (especially for [[at-the-money options|ATM options]]).

> **Real-World Example:** You buy a 30-day [[at-the-money options|ATM]] call on Netflix for $5.00. If nothing changes for 10 days, the option might drop to $3.80 just from [[time decay]]. This loss of $1.20 is [[Theta]] in action. Sellers of options profit from this — it's why "selling [[Premium]]" strategies exist.

### 8.6 Vega (ν)

[[Vega]] = the change in [[Option]] value for a small change in [[Volatility]].

| Position | Vega |
|----------|------|
| Long options (calls or puts) | Positive |
| Short options | Negative |
| $\text{Vega}_c = \text{Vega}_p$ | Equal for same-strike options ([[put-call parity]]) |

[[Vega]] is based on an **unobservable** [[Parameter|parameter]] — future [[Volatility]]. Of the five [[BSM model|BSM]] inputs, an option's value is **most sensitive** to [[Volatility]] changes.

> **Real-World Example:** Before an earnings announcement, [[Implied volatility]] on a tech stock's options spikes from 25% to 45%. If you owned a $3.00 call, [[Vega]] might push it to $5.50 — even if the stock price didn't change. After earnings, [[Volatility]] collapses ("vol crush"), and the option price drops. This is why [[Vega]] matters for event-driven trading.

### 8.7 Rho (ρ)

[[Rho]] = the change in [[Option]] value for a small change in the [[risk-free rate]].

| Position | Rho | Intuition |
|----------|-----|-----------|
| Calls | Positive | Higher rates raise the [[Cost of carry]] ($Se^{rT}$) |
| Puts | Negative | Higher rates lower the PV of the [[Exercise price]] ($Xe^{-rT}$) |

[[Rho]] is typically the **least impactful** [[Greeks|Greek]] for short-dated options, but matters more for long-dated options.

---

## 9. Implied Volatility

### 9.1 Definition

[[Implied volatility]] is the [[Volatility]] value that, when input into the [[BSM model]], produces the **observed market price** of the option. It is found by **inverting** the [[BSM model]].

| Concept | Description |
|---------|-------------|
| [[Historical volatility]] | Backward-looking — calculated from past returns |
| [[Implied volatility]] | Forward-looking — inferred from current option prices |

[[Implied volatility]] tells you what the **market collectively believes** future [[Volatility]] will be, plus any [[Risk premium]] for option demand.

### 9.2 Volatility Smile, Skew, and Surface

In theory (under [[BSM model|BSM]] assumptions), [[Implied volatility]] should be the same for all [[Exercise price|exercise prices]] and [[expiration|expirations]]. In practice, it is not:

| Pattern | What It Is |
|---------|-----------|
| [[Volatility smile]] | [[Implied volatility]] is higher for deep [[In the money|ITM]] and deep [[Out of the money|OTM]] options, forming a U-shape across [[Exercise price|exercise prices]] |
| [[Volatility skew]] | [[Implied volatility]] is higher for lower [[Exercise price|exercise prices]] (common in equity markets — reflects crash fear) |
| [[Term structure of volatility]] | [[Implied volatility]] varies across [[expiration|expirations]] |
| [[Volatility surface]] | A 3D plot combining smile/skew and [[Term structure|term structure]] |

If [[BSM model|BSM]] assumptions were perfectly true, the [[volatility surface]] would be flat.

### 9.3 The VIX

The [[VIX]] ([[CBOE Volatility Index|CBOE Volatility Index]]atility]] Index) measures the [[Implied volatility]] of S&P 500 options over the next 30 days. It is often called the "**fear index**" because rising [[VIX]] signals greater market uncertainty. During the [[2008 financial crisis]], the [[VIX]] spiked dramatically.

### 9.4 Uses in Trading

[[Implied volatility]] is used to:

1. **Quote options**: Traders sometimes quote options in [[Implied volatility]] terms rather than dollar prices
2. **Identify [[Mispricing|mispricing]]**: If your view of future [[Volatility]] differs from [[Implied volatility]], you may see a trading opportunity
3. **Compare options**: Standardizes comparison across different [[Underlying|underlyings]], [[Exercise price|exercise prices]], and [[expiration|expirations]]
4. **Manage [[Vega]] exposure**: Traders combine positions to go long or short [[Volatility]]

> **Real-World Example:** Suppose you see a 3-month [[at-the-money options|ATM]] call on a tech index quoted at 19% [[Implied volatility]], and a 1-month [[In the money|ITM]] put on one of the index components quoted at 24% [[Implied volatility]]. If you believe the component's true [[Volatility]] is only 20% and the index's true [[Volatility]] is 25%, you might buy the index call (going long [[Volatility]] cheaply) and sell the component put (going short [[Volatility]] at a premium).

---

## 10. Summary Comparison of Models

| Feature | [[Binomial model]] | [[BSM Model]] | [[Black Model]] |
|---------|-----------------|-------------|---------------|
| Time | Discrete | Continuous | Continuous |
| [[Underlying]] | Any asset | Spot asset | [[Futures]]/[[Forward]] |
| Option style | [[European options\|European]] & [[American options\|American]] | [[European options\|European]] only | [[European options\|European]] only |
| Key terms | $h$, $\pi$, $u$, $d$ | $N(d_1)$, $N(d_2)$ | $N(d_1)$, $N(d_2)$ |
| [[Carry costs]] | Handled via tree adjustments | Incorporated via $\delta$ | No carry (costless to carry) |
| [[Replication|Replication]] analog | $h$ ↔ $N(d_1)$ | $N(d_1)$ shares + $N(d_2)$ bonds | $F_0(T)$ component + bond component |

---

## 11. Key Formulas Quick Reference

### Binomial Model

$$h = \frac{c^+ - c^-}{S^+ - S^-} \qquad \pi = \frac{(1+r) - d}{u - d}$$

$$c = PV[\pi c^+ + (1-\pi)c^-] \qquad p = PV[\pi p^+ + (1-\pi)p^-]$$

### BSM Model

$$c = Se^{-\delta T}N(d_1) - Xe^{-rT}N(d_2)$$

$$p = Xe^{-rT}N(-d_2) - Se^{-\delta T}N(-d_1)$$

### Black Model (Futures)

$$c = e^{-rT}[F_0(T)N(d_1) - XN(d_2)]$$

$$p = e^{-rT}[XN(-d_2) - F_0(T)N(-d_1)]$$

### Swaptions

$$\text{Payer} = [R_{\text{fix}}N(d_1) - R_XN(d_2)] \times PVA$$

$$\text{Receiver} = [R_XN(-d_2) - R_{\text{fix}}N(-d_1)] \times PVA$$

### Delta Hedge

$$N_H = \frac{-\text{Portfolio delta}}{\Delta_H}$$

### Delta-Plus-Gamma Approximation

$$\Delta c \approx \Delta_c(\Delta S) + \frac{1}{2}\Gamma_c(\Delta S)^2$$

---

## 12. Practice Mnemonics

- **"BOVM"** = [[Binomial]] → works backward; is the bridge to [[BSM model|BSM]]
- **Call = Stock − Bond** (buying stock with borrowed money = [[leveraged position]])
- **Put = Bond − Stock** (lending money, shorting stock)
- **$|Δ_c| + |Δ_p| = 1$** for same-strike options
- **$Γ_c = Γ_p$** and **$ν_c = ν_p$** — gamma and vega are the same for calls and puts
- **Long options → +Γ, −Θ, +ν** (you gain from moves and vol, lose from time)
- **Short options → −Γ, +Θ, −ν** (you gain from time, lose from moves and vol)
- **Caps = strip of caplets (calls); Floors = strip of floorlets (puts)**
- **Long floor + Short cap = pay-fixed swap** (when strike = [[Swap rate|swap rate]], cost = 0)

---
