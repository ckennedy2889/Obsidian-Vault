---
title: Swaptions
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - swaptions
  - interest-rate-options
  - Black-model
  - fixed-income
aliases:
  - swap option
  - payer swaption
  - receiver swaption
  - option on a swap
---

# Swaptions

## The Real-World Analogy

Imagine you're a CFO who knows you'll need to borrow $100 million in one year for a five-year project. You'd like to fix your borrowing rate now — but you're not 100% sure you'll need the money, or maybe you're hoping rates might fall first.

A **swaption** solves this. You pay a small upfront premium today for the *right* (but not the obligation) to enter an interest rate swap at a pre-agreed rate one year from now. If rates have risen, you exercise: you lock in the old, lower rate. If rates fell, you walk away and enter a cheaper swap in the market.

It is, in essence, an option on an interest rate swap — combining the optionality of a call/put with the cash flow transformation of a swap.

## Plain-English Definition

A **swaption** gives the buyer the right, but not the obligation, to enter an [[Interest Rate Swaps|interest rate swap]] on a specified future date, at a pre-agreed fixed rate (the strike rate $X_r$), for a pre-agreed term.

The underlying is not a stock price — it is the **forward swap rate** (the fair fixed rate today for a swap starting at the swaption's expiry date).

### The Two Types

| Type | Right Granted | Rates View | Analogy |
|---|---|---|---|
| **Payer swaption** | Right to enter as fixed-rate **payer** (floating receiver) | Rates will **rise** | Call option on rates |
| **Receiver swaption** | Right to enter as fixed-rate **receiver** (floating payer) | Rates will **fall** | Put option on rates |

**Memory rule:**
- **Payer** = you want to **pay** a low locked rate when market rates are high. Exercise when $R_{\text{market}} > X_r$.
- **Receiver** = you want to **receive** a high locked rate when market rates are low. Exercise when $R_{\text{market}} < X_r$.

```
Payer Swaption Payoff at Expiry:
  max(R_fix - X_r, 0) × PVA × Notional

Receiver Swaption Payoff at Expiry:
  max(X_r - R_fix, 0) × PVA × Notional
```

Where $R_{\text{fix}}$ is the prevailing market swap rate at expiry and $X_r$ is the strike rate.

---

## Why CFA Tests This

The LOS explicitly states: *"Describe how the Black model is used to value European interest rate options and European swaptions."*

Swaptions appear in exam vignettes as:
- A calculation requiring you to apply the Black model formula
- A conceptual question on payer vs. receiver identification
- A question on why someone would buy a swaption (hedging floating-rate debt exposure, for example)

---

## The Black Model for Swaptions

### Why the Black Model (Not BSM)?

The [[Black-Scholes-Merton Model|BSM model]] prices options on assets with a spot price. An interest rate swap has no spot price — it is a forward contract on a rate. The **Black model** (a BSM extension) prices options on *forward prices*, treating the forward rate as the underlying.

For swaptions, the underlying is the **forward swap rate** $R_{\text{fix}}$: the no-arbitrage fixed rate today for a swap that starts when the swaption expires.

### The Formulas

**Payer Swaption:**

$$\boxed{V_{\text{pay}} = \left[ R_{\text{fix}} \cdot N(d_1) - X_r \cdot N(d_2) \right] \cdot PVA \cdot e^{-rT}}$$

**Receiver Swaption:**

$$\boxed{V_{\text{rec}} = \left[ X_r \cdot N(-d_2) - R_{\text{fix}} \cdot N(-d_1) \right] \cdot PVA \cdot e^{-rT}}$$

Where:

$$d_1 = \frac{\ln(R_{\text{fix}} / X_r) + \frac{1}{2}\sigma^2 T}{\sigma \sqrt{T}}$$

$$d_2 = d_1 - \sigma\sqrt{T}$$

### Terms Defined

| Symbol | Meaning |
|---|---|
| $R_{\text{fix}}$ | Current **forward swap rate** for a swap starting at swaption expiry |
| $X_r$ | **Strike rate** (exercise rate) agreed at swaption purchase |
| $PVA$ | Sum of discount factors for each payment date of the **underlying swap** |
| $e^{-rT}$ | Discount factor from swaption expiry back to today |
| $N(d_1), N(d_2)$ | Cumulative standard normal probabilities |
| $\sigma$ | Volatility of the forward swap rate |
| $T$ | Time (in years) until swaption expiry |

### What $PVA$ Is — and Why It Matters

The $PVA$ factor is the **sum of the present value of $1 annuity factors** for all payment dates of the underlying swap. It converts an annualized rate differential (like $R_{\text{fix}} - X_r$) into a total dollar value over the life of the swap.

$$PVA = \sum_{i=1}^{n} DF_i = \frac{1}{(1+r_1)} + \frac{1}{(1+r_2)^2} + \cdots + \frac{1}{(1+r_n)^n}$$

> [!warning] PVA Trap
> $PVA$ is not discounting back to today — that is done by $e^{-rT}$ separately. $PVA$ discounts the underlying swap's cash flows from the **swap start date** (= swaption expiry). If you see a 1-year swaption on a 2-year swap, the PVA sums discount factors for years 2 and 3 (the swap payment dates), not year 1.

---

## Assumptions of the Black Model

1. **Lognormal forward rates:** The forward swap rate follows a lognormal distribution — it cannot go negative
2. **Constant volatility:** $\sigma$ is known and constant over the swaption's life
3. **Constant risk-free rate:** The short-term rate used for discounting is known and constant
4. **No arbitrage:** Efficient markets, no transaction costs

> [!note] Limitation: Negative Rates
> The lognormal assumption means the Black model cannot accommodate negative interest rates (which were observed in Europe/Japan post-2010). Modified versions use "shifted lognormal" or normal (Bachelier) frameworks for negative-rate environments. The CFA exam stays with standard Black model unless explicitly stated otherwise.

---

## Worked Numerical Example

**Scenario:**
- 1-year swaption on a 2-year annual-pay interest rate swap
- Strike rate: $X_r = 3.0\%$
- Current forward swap rate: $R_{\text{fix}} = 3.5\%$ (rates have risen — payer is in the money)
- Sum of discount factors for years 2 and 3: $PVA = 1.85$
- Discount factor for swaption expiry (1 year): $e^{-rT} = 0.97$
- Given: $N(d_1) = 0.65$, $N(d_2) = 0.58$
- Notional principal: $10,000,000

**Step 1 — Payer swaption value per $1 of notional:**

$$V_{\text{pay}} = [R_{\text{fix}} \cdot N(d_1) - X_r \cdot N(d_2)] \times PVA \times e^{-rT}$$

$$= [0.035 \times 0.65 - 0.030 \times 0.58] \times 1.85 \times 0.97$$

$$= [0.02275 - 0.01740] \times 1.7945$$

$$= 0.00535 \times 1.7945 = \mathbf{0.009601}$$

**Step 2 — Scale to notional:**

$$V_{\text{pay}} = 0.009601 \times \$10{,}000{,}000 = \mathbf{\$96{,}010}$$

**Interpretation:** The right to pay 3.0% fixed when the market swap rate is 3.5% is worth ~$96,000 today on a $10M notional.

**Step 3 — Receiver swaption (same inputs):**

$$V_{\text{rec}} = [X_r \cdot N(-d_2) - R_{\text{fix}} \cdot N(-d_1)] \times PVA \times e^{-rT}$$

$$N(-d_2) = 1 - 0.58 = 0.42, \quad N(-d_1) = 1 - 0.65 = 0.35$$

$$= [0.030 \times 0.42 - 0.035 \times 0.35] \times 1.85 \times 0.97$$

$$= [0.01260 - 0.01225] \times 1.7945 = 0.00035 \times 1.7945 = \mathbf{0.000628}$$

The receiver swaption is nearly worthless here because the market rate ($3.5\%$) is above the strike ($3.0\%$) — the receiver would be locking in a below-market fixed rate.

---

## Comparison: Payer vs. Receiver

| | Payer Swaption | Receiver Swaption |
|---|---|---|
| Right to… | Pay fixed, receive floating | Receive fixed, pay floating |
| Exercise when… | $R_{\text{market}} > X_r$ | $R_{\text{market}} < X_r$ |
| Who uses it | Borrowers hedging floating-rate debt | Lenders / investors hedging fixed income |
| Analogy | Call option on interest rates | Put option on interest rates |
| Payoff formula | $\max(R_{\text{fix}} - X_r, 0) \times PVA$ | $\max(X_r - R_{\text{fix}}, 0) \times PVA$ |

---

## Real-World Uses

| User | Strategy | Why |
|---|---|---|
| Corporate treasurer | Buy payer swaption | Has floating-rate debt, fears rate rises — swaption converts to fixed if needed |
| Pension fund | Buy receiver swaption | Holds fixed-rate bonds, fears rate falls — swaption locks in receiving high fixed rate |
| Bank | Sell swaptions | Collect premium income; manage exposure via hedging |

---

## Exam Traps

> [!danger] Key Exam Traps for Swaptions

| Trap | Correct Understanding |
|---|---|
| Using spot swap rate instead of forward swap rate | Always use the **forward swap rate** $R_{\text{fix}}$ as the underlying |
| Wrong PVA dates | PVA uses discount factors for the **underlying swap's payment dates**, not for the swaption's expiry |
| Confusing payer/receiver | Payer = call on rates; Receiver = put on rates |
| Forgetting $e^{-rT}$ | The PVA discounts from swap start to today's value, but you also need to discount across the swaption's life |
| Black model assumptions | Black assumes lognormal rates → cannot go negative. Exam will not ask you to modify this, but may test the assumption itself |
| N(d₁) vs N(d₂) | $d_1$ goes with $R_{\text{fix}}$ (the "asset"), $d_2$ goes with $X_r$ (the "strike") — same as BSM for stocks |

---

## Memory Hooks

- **Payer swaption = call on rates** → exercise when rates RISE
- **Receiver swaption = put on rates** → exercise when rates FALL
- Formula structure: same as BSM but replace $S_0$ with $R_{\text{fix}}$ and $X$ with $X_r$, then multiply by $PVA \cdot e^{-rT}$
- $PVA$ = the "annuity multiplier" — it converts a rate difference into a dollar amount over the swap's life

---

## Related Concepts

- [[Interest Rate Swaps]] — the underlying instrument of a swaption
- [[Black-Scholes-Merton Model]] — parent model from which Black model derives
- [[Interest Rate Options]] — caps, floors, and caplets/floorlets priced with the same Black model
- [[Option Greeks]] — delta, gamma, vega apply to swaptions too
- [[Forward Rate Agreement]] — the simplest interest rate forward, conceptually related
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full treatment of the Black model framework
