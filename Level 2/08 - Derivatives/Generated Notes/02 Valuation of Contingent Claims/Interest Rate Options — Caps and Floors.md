---
title: Interest Rate Options — Caps and Floors
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - interest-rate-options
  - caps
  - floors
  - caplets
  - floorlets
  - Black-model
  - collars
aliases:
  - interest rate cap
  - interest rate floor
  - caplet
  - floorlet
  - interest rate collar
  - cap and floor
---

# Interest Rate Options — Caps and Floors

## The Real-World Analogy

You have a variable-rate mortgage. Every time rates rise, your payment rises with it — unlimited upside risk on your borrowing cost. You'd love to cap your maximum payment at, say, 6%. That's exactly what an interest rate cap does.

Or imagine you manage a floating-rate bond portfolio. When rates fall, your income falls. You'd love a guaranteed floor — a minimum income level no matter how low rates go. That's an interest rate floor.

Caps and floors are insurance policies on interest rate movements, paid for with an upfront premium.

## Plain-English Definition

An **interest rate cap** is a series of European interest rate call options. It pays out whenever a reference rate (typically MRR — the Market Reference Rate) exceeds a pre-agreed **cap rate** at each reset date.

An **interest rate floor** is a series of European interest rate put options. It pays out whenever the reference rate falls below a pre-agreed **floor rate** at each reset date.

The individual option components are called **caplets** (for caps) and **floorlets** (for floors).

```
Cap payoff at each reset date:
  max(Reference Rate − Cap Rate, 0) × Notional × Accrual Period

Floor payoff at each reset date:
  max(Floor Rate − Reference Rate, 0) × Notional × Accrual Period
```

---

## Why CFA Tests This

The LOS states: *"Describe how the Black model is used to value European interest rate options and European swaptions."*

Interest rate caps and floors are exactly "European interest rate options" valued with the Black model. The exam tests:
- The caplet/floorlet structure and why it exists
- The Black model formula applied to a single caplet or floorlet
- The hedging use case (cap for borrowers, floor for investors)
- The collar relationship and equivalence to a swap

---

## Structure: Caps as a Strip of Caplets

A loan might reset quarterly. A 2-year cap on a quarterly reset loan consists of **8 individual caplets** — one for each reset date. Each caplet is a separate European call option on the reference rate for that specific quarter.

```
Cap = Caplet₁ + Caplet₂ + Caplet₃ + ... + Capletₙ

Timeline:
  |--Q1--|--Q2--|--Q3--|--Q4--|
    C1     C2     C3     C4    ← each is a separate caplet
```

**Why structure it this way?** Interest rate resets happen periodically, so each period needs its own option. The cap is the sum of all individual period options.

**Settlement in arrears:** The reference rate is observed at the *start* of each period (advanced set) but the payoff is made at the *end* of the period (settled in arrears). This is why the discount factor uses the payment date, not the option expiry date.

---

## The Black Model for Caplets and Floorlets

### Why Black Model, Not BSM?

The [[Black-Scholes-Merton Model|BSM model]] prices options on spot assets. Caplets are options on forward interest rates — the relevant underlying is the **forward rate** $F_0(T)$ for the accrual period, not a spot price. The Black model handles this naturally.

### Caplet Formula

$$\boxed{c = (NP)(AP)\left[F_0(T) \cdot N(d_1) - X_R \cdot N(d_2)\right] e^{-rT^*}}$$

### Floorlet Formula

$$\boxed{p = (NP)(AP)\left[X_R \cdot N(-d_2) - F_0(T) \cdot N(-d_1)\right] e^{-rT^*}}$$

### Components of $d_1$ and $d_2$

$$d_1 = \frac{\ln(F_0 / X_R) + \frac{1}{2}\sigma^2 T}{\sigma\sqrt{T}}$$

$$d_2 = d_1 - \sigma\sqrt{T}$$

### All Terms Defined

| Symbol | Meaning |
|---|---|
| $NP$ | Notional principal |
| $AP$ | Accrual period (e.g., 0.25 for a 90-day quarter, 0.5 for semi-annual) |
| $F_0(T)$ | Current **forward rate** for the accrual period (from an FRA or yield curve) |
| $X_R$ | **Cap rate** (for caplet) or **floor rate** (for floorlet) |
| $\sigma$ | Volatility of the forward rate |
| $T$ | Time to **option expiry** (start of the accrual period) |
| $T^*$ | Time to **payment date** (end of the accrual period = $T + AP$) |
| $N(d_1), N(d_2)$ | Cumulative standard normal probabilities |

> [!warning] Key Distinction: $T$ vs $T^*$
> The option expires at the start of the accrual period ($T$), but payment is made at the end ($T^* = T + AP$). The discount factor $e^{-rT^*}$ uses the payment date. Getting this wrong changes your answer on the exam.

### Moneyness

| Condition | Caplet | Floorlet |
|---|---|---|
| ITM | Reference rate > $X_R$ | Reference rate < $X_R$ |
| ATM | Reference rate = $X_R$ | Reference rate = $X_R$ |
| OTM | Reference rate < $X_R$ | Reference rate > $X_R$ |

---

## Worked Numerical Example — Caplet Valuation

**Setup:**
- Notional principal: \$10,000,000
- Cap rate ($X_R$): 8.0%
- Current forward rate ($F_0$): 7.0%
- Accrual period ($AP$): 0.25 years (90-day quarter)
- Time to option expiry ($T$): 1.0 year
- Time to payment ($T^*$): 1.25 years
- Volatility ($\sigma$): 20%
- Risk-free rate: 6.5% (continuously compounded)

**Step 1 — Compute discount factor to payment date:**

$$e^{-0.065 \times 1.25} = 0.9220$$

**Step 2 — Compute $d_1$ and $d_2$:**

$$d_1 = \frac{\ln(0.07/0.08) + \frac{1}{2}(0.20)^2 \times 1.0}{0.20 \times \sqrt{1.0}} = \frac{-0.1335 + 0.02}{0.20} = \frac{-0.1135}{0.20} = -0.5677$$

$$d_2 = -0.5677 - 0.20 = -0.7677$$

**Step 3 — Look up normal probabilities:**

$$N(-0.5677) \approx 0.2851 \qquad N(-0.7677) \approx 0.2213$$

**Step 4 — Compute caplet value:**

$$c = (10{,}000{,}000)(0.25)(0.9220)\left[(0.07)(0.2851) - (0.08)(0.2213)\right]$$

$$= 2{,}305{,}000 \times [0.01996 - 0.01770]$$

$$= 2{,}305{,}000 \times 0.00226 = \mathbf{\$5{,}209}$$

**Interpretation:** This caplet costs \$5,209. If rates are above 8% at the reset date in 1 year, the cap pays out; otherwise it expires worthless.

Note the caplet is **out of the money** here (forward rate 7% < cap rate 8%), hence its low value. If rates rise above 8% before expiry, the caplet gains value.

---

## Hedging Use Cases

### Floating Rate Borrower → Buy Cap

A company has a $10M floating rate loan at MRR + 100bps. They fear rising rates.

**Action:** Buy an interest rate cap with cap rate = 5%.

**Effect:**
- If MRR rises to 7%: loan costs MRR + 1% = 8%, but cap pays out 7% − 5% = 2% per period → effective cost = 6%
- If MRR stays at 3%: cap expires worthless, loan costs 4% (fine — rates didn't rise)
- The cap converts a floating-rate liability into a **capped floating rate** (never above cap rate + spread)

### Floating Rate Investor → Buy Floor

A bond manager holds floating-rate notes. They fear falling rates eroding income.

**Action:** Buy an interest rate floor with floor rate = 3%.

**Effect:**
- If MRR falls to 1%: bond earns 1%, but floor pays 3% − 1% = 2% per period → minimum income = 3%
- If MRR stays at 4%: floor expires worthless, bond earns 4% (fine — rates didn't fall)
- The floor converts floating-rate income into a **floored floating rate** (never below floor rate)

---

## Caps, Floors, and Collars

### Interest Rate Collar

A **collar** combines a long cap and a short floor (or vice versa):

$$\text{Long Collar} = \text{Long Cap} + \text{Short Floor (same strike)}$$

**Borrower strategy:** Buy cap (cap borrowing cost) + sell floor (give up benefit if rates fall). The floor premium received offsets the cap premium paid.

**Zero-cost collar:** Choose cap rate and floor rate such that cap premium = floor premium → no upfront cost.

### Equivalence to Swaps (Put-Call Parity for Rates)

A key relationship:

$$\text{Long Cap} - \text{Long Floor} = \text{Receive-Floating, Pay-Fixed Swap}$$

Or equivalently:

$$\text{Long Cap} = \text{Long Floor} + \text{Receive-Floating, Pay-Fixed Swap}$$

This is put-call parity applied to interest rate options. A cap (call on rates) minus a floor (put on rates) with the same strike equals a [[Interest Rate Swaps|pay-fixed swap]].

**Implication:** If you have a pay-fixed swap and buy a floor at the fixed rate, you've replicated a cap. This relationship creates arbitrage constraints that keep cap/floor pricing consistent with swap rates.

---

## Summary Comparison Table

| | Cap | Floor |
|---|---|---|
| **Made of** | Strip of caplets (call options) | Strip of floorlets (put options) |
| **Pays when** | Reference rate > cap rate | Reference rate < floor rate |
| **Who buys** | Floating-rate borrowers | Floating-rate investors/lenders |
| **Analogy** | Insurance against rising rates | Insurance against falling rates |
| **Black model input** | Forward rate vs cap rate | Forward rate vs floor rate |

---

## Exam Traps

> [!danger] Key Exam Traps

| Trap | Correct Understanding |
|---|---|
| Discount to expiry date ($T$), not payment date ($T^*$) | Always discount to the payment date ($T + AP$) because settlement is in arrears |
| Cap is a single option | A cap is a **strip** of caplets — one per reset period |
| Caplet uses spot rate, not forward rate | Must use the **forward rate** $F_0(T)$ as the underlying — same Black model logic as swaptions |
| Cap is in the money when rates are low | Caplets are ITM when reference rate > cap rate (they're call options on rates) |
| Floor is in the money when rates are high | Floorlets are ITM when reference rate < floor rate (they're put options on rates) |
| Long cap + short floor ≠ swap | Actually, long cap − long floor = receive-floating swap; know this put-call parity relationship |
| Volatility input is the stock's vol | The volatility used is that of the **forward interest rate**, not any equity |

---

## Memory Hooks

- **Cap = call on rates**: pays when rates RISE above cap rate
- **Floor = put on rates**: pays when rates FALL below floor rate
- **Borrower buys cap** (protects against rising cost), **investor buys floor** (protects against falling income)
- **Caplet discount factor**: use $T^* = T + AP$ (payment date), not just $T$ (expiry date)
- **Cap − Floor = Swap**: put-call parity for interest rates
- **AP factor**: multiply by the accrual period to convert an annual rate difference into a payment for the period

---

## Related Concepts

- [[Swaptions]] — options on entire swaps; also priced with the Black model
- [[Black-Scholes-Merton Model]] — parent model; Black model extends it to forward rates
- [[Interest Rate Swaps]] — the instrument equivalent to long cap + short floor
- [[Forward Rate Agreement]] — the underlying forward rates used in caplet pricing
- [[Option Greeks]] — Greeks (especially vega) apply to caps/floors too
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full Black model treatment including swaptions
