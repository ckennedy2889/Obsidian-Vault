---
title: Black Model for Options on Forwards and Futures
subject: Derivatives
tags: [CFA-L2, derivatives, options, black-model, futures-options, swaptions, caplets, floorlets]
aliases: [Black model, Black 1976, Black-76, Futures option model, Forward option model, Options on futures]
---

# Black Model for Options on Forwards and Futures

## 1. The Real-World Analogy

Imagine you're buying an option on a *promise* of a barrel of oil six months from now, rather than on a barrel of oil sitting in a warehouse today. The warehouse barrel has *real costs* attached — storage, insurance, financing — and *real benefits* (you could lend it, sell it, hedge with it). The promise has none of that: a futures or forward contract costs nothing to enter into, and there's no oil in your basement leaking value.

That single difference — **a forward/futures contract is "costless to carry"** — is what lets us strip the cost-of-carry adjustments out of [[Black-Scholes-Merton Model|Black-Scholes-Merton]] and arrive at a cleaner formula: the **Black (1976) model**. The market has *already done* the cost-of-carry work for us by setting the forward price.

## 2. Plain-English Definition

The **Black model** prices European options whose underlying is a forward price, futures price, or forward rate, on the assumption that this forward price is lognormally distributed. It is a special case of [[Black-Scholes-Merton Model|BSM]] in which the spot price $S_0$ is replaced by the forward/futures price $F_0(T)$, and the entire bracketed payoff is discounted back to today at the risk-free rate.

## 3. Why It Exists — Black vs. BSM in One Picture

| | BSM (option on a stock) | Black (option on forward/futures) |
|---|---|---|
| Underlying input | Spot price $S_0$ | Forward / futures price $F_0(T)$ |
| Cost-of-carry adjustment | Needed (dividends, financing) | **Already embedded in $F_0(T)$** — no separate adjustment |
| Discounting | Only the strike term: $-Xe^{-rT}N(d_2)$ | **Whole bracket** is discounted by $e^{-rT}$ |
| $d_1$ uses | $\ln(S_0/X) + (r + \sigma^2/2)T$ | $\ln(F_0(T)/X) + \tfrac{1}{2}\sigma^2 T$ — **no $r$ in the numerator** |
| Underlying distribution | Lognormal spot price | Lognormal forward price |
| Suited for | Equity options | Options on futures, FRAs, swaps, commodities |

Why no $r$ in the Black $d_1$? Because the forward price already *is* the risk-neutral expected future spot price (under no-arbitrage), so the drift term $rT$ has been absorbed into $F_0(T)$ itself. Adding it again would double-count.

## 4. The Core Formulas — Options on Forwards/Futures

For a European **call** on a forward/futures contract:

$$
c = e^{-rT}\big[F_0(T)\,N(d_1) - X\,N(d_2)\big]
$$

For a European **put**:

$$
p = e^{-rT}\big[X\,N(-d_2) - F_0(T)\,N(-d_1)\big]
$$

with

$$
d_1 = \frac{\ln\!\big(F_0(T)/X\big) + \tfrac{1}{2}\sigma^2 T}{\sigma\sqrt{T}}, \qquad d_2 = d_1 - \sigma\sqrt{T}
$$

**Symbols:**
- $F_0(T)$ — current forward/futures price for delivery at the option's expiration $T$.
- $X$ — strike price.
- $r$ — continuously compounded risk-free rate over $[0,T]$.
- $\sigma$ — volatility of the forward/futures price.
- $N(\cdot)$ — standard normal CDF.

### Put-Call Parity (Black-model form)

$$
p + F_0(T)e^{-rT} = c + X e^{-rT}
$$

Equivalently:

$$
c - p = e^{-rT}\big[F_0(T) - X\big]
$$

This says: a long call + short put portfolio is worth the present value of the *forward minus strike*. Notice that **both** $F_0(T)$ and $X$ are discounted — symmetric, because both belong to the option-expiration date.

## 5. Mechanism — Why The Formula Works (Step Down The Ladder)

```
Rule  → Black uses F instead of S, and discounts the full bracket
Why   → A forward/futures contract is costless-to-carry; F already embeds rT and any income/yield
Mech. → Risk-neutral pricing: payoff at T is max(F_T − X, 0); E[F_T] = F_0(T) under risk-neutral measure
        ⇒ Expected payoff ≈ F_0 N(d_1) − X N(d_2); discount by e^{−rT} to get today's value
Assum.→ F_T is lognormal; constant volatility; constant risk-free rate; European exercise; no early exercise premium
Fail  → Negative rates break the lognormal assumption (ln of negative number is undefined). Heavy-tailed or vol-of-vol regimes break the constant-σ assumption (vol smile/skew)
Exam  → If the underlying is anything you can quote a forward price for (futures, FRA, swap rate), reach for Black, not BSM
```

## 6. Worked Example #1 — European Call On A Futures Contract

Inputs:

| | |
|---|---:|
| $F_0(T)$ | 100 |
| $X$ | 100 |
| $r$ | 5% |
| $T$ | 1 year |
| $\sigma$ | 20% |

$$d_1 = \frac{\ln(100/100) + \tfrac{1}{2}(0.20)^2(1)}{0.20\sqrt{1}} = \frac{0.02}{0.20} = 0.10$$

$$d_2 = 0.10 - 0.20 = -0.10$$

With $N(0.10) = 0.5398$ and $N(-0.10) = 0.4602$:

$$c = e^{-0.05}\big[100(0.5398) - 100(0.4602)\big] = 0.9512 \times 7.96 = \boxed{7.57}$$

The corresponding put, by parity ($F = X$ here so $c = p$): $p \approx 7.57$.

## 7. Extending Black To Interest-Rate Options — Caplets and Floorlets

An interest-rate **cap** is a portfolio of caplets — call options on a forward rate (the [[FRA]] rate). A **floor** is a portfolio of floorlets — puts on the forward rate. Two adaptations are required:

1. **Accrual-period scaling (AP).** Interest rates are quoted annualized; a caplet pays interest *only over its accrual window* (e.g., 90/360 = 0.25 of a year), so the payoff must be multiplied by AP.
2. **"Advanced set, settled in arrears."** The reference rate is *observed* at the start of the accrual period (option expiration $t$) but *paid* at the end of it ($t + \text{AP}$). Discounting must therefore reach back from the **payment date**, not the expiration date.

### Formulas

Caplet (call on the forward rate):

$$
c_{\text{caplet}} = \text{Notional} \times \text{AP} \times e^{-r(t + \text{AP})}\big[\text{FRA}\,N(d_1) - X_R\,N(d_2)\big]
$$

Floorlet (put on the forward rate):

$$
p_{\text{floorlet}} = \text{Notional} \times \text{AP} \times e^{-r(t + \text{AP})}\big[X_R\,N(-d_2) - \text{FRA}\,N(-d_1)\big]
$$

with

$$
d_1 = \frac{\ln(\text{FRA}/X_R) + \tfrac{1}{2}\sigma^2 t}{\sigma\sqrt{t}}, \quad d_2 = d_1 - \sigma\sqrt{t}
$$

Symbols: FRA = current forward rate for the accrual period; $X_R$ = strike rate; $t$ = time to option expiration; AP = accrual period in years; $\sigma$ = volatility *of the forward rate*.

→ See [[Interest Rate Options — Caps and Floors]].

## 8. Extending Black To Swaptions

A [[Swaptions|swaption]] gives the right to enter a swap at a pre-agreed fixed rate $X_R$. The underlying is the **forward swap rate** $R_{\text{fix}}$ (sometimes denoted $s_F$). Because a swap pays a *series* of cash flows, the simple $e^{-rT}$ discount factor is replaced by the **PV of an annuity** (PVA) — the sum of discount factors across all swap settlement dates.

$$
\text{PaySWN} = \text{Notional} \times \text{PVA} \times \big[R_{\text{fix}}\,N(d_1) - X_R\,N(d_2)\big]
$$

$$
\text{RecSWN} = \text{Notional} \times \text{PVA} \times \big[X_R\,N(-d_2) - R_{\text{fix}}\,N(-d_1)\big]
$$

with the usual

$$
d_1 = \frac{\ln(R_{\text{fix}}/X_R) + \tfrac{1}{2}\sigma^2 T}{\sigma\sqrt{T}}, \quad d_2 = d_1 - \sigma\sqrt{T}
$$

**Mnemonic:** payer swaption ↔ pay fixed ↔ behaves like a *put* on bonds (gains when rates rise). Receiver swaption ↔ receive fixed ↔ behaves like a *call* on bonds (gains when rates fall).

## 9. Worked Example #2 — Payer Swaption

Right to pay fixed at $X_R = 6.2\%$ on a 3-year semiannual swap starting in 5 years; notional $100M; current forward swap rate $R_{\text{fix}} = 6.194\%$; $\sigma = 20\%$; flat zero curve $r = 6\%$ continuous.

**Step 1 — PVA.** Sum 6 semiannual discount factors at swap-payment dates 5.5, 6.0, 6.5, 7.0, 7.5, 8.0:

$$
\text{PVA} = \sum_{i=1}^{6} e^{-0.06\,t_i} \approx 2.0035
$$

**Step 2 — d₁, d₂.**

$$
d_1 = \frac{\ln(0.06194/0.062) + \tfrac{1}{2}(0.20)^2(5)}{0.20\sqrt{5}} = \frac{-0.000968 + 0.10}{0.4472} \approx 0.2214
$$

$$
d_2 = 0.2214 - 0.4472 \approx -0.2258
$$

**Step 3 — Plug in.** Using $N(0.2214) \approx 0.5876$ and $N(-0.2258) \approx 0.4107$:

$$
\text{PaySWN} = 100{,}000{,}000 \times 2.0035 \times \big[0.06194(0.5876) - 0.062(0.4107)\big]
$$

$$
= 100{,}000{,}000 \times 2.0035 \times \big[0.03640 - 0.02546\big] = 100{,}000{,}000 \times 2.0035 \times 0.01094
$$

$$
\approx \$2.19\text{ million}
$$

**Sanity check:** the swaption is roughly at-the-money ($R_{\text{fix}} \approx X_R$), 5 years out, with 20% vol. A premium near 2.2% of notional is reasonable.

## 10. Assumptions and Failure Modes

1. **Lognormal forward / forward rate.** Implies the rate is strictly positive — fine in normal regimes, broken in a negative-rate world (post-GFC EUR, JPY rates).
2. **Constant volatility.** Real markets exhibit a vol smile/skew — Black gives one number per strike, hence "implied vol" varies across strikes.
3. **Constant risk-free rate.** Fine for short-dated equity-like options; less defensible for long-dated rate options where the discount rate itself is the underlying.
4. **European exercise.** No early-exercise value captured — apply [[Binomial Option Pricing Model|binomial]] for American options.
5. **No transaction costs / continuous trading** — same as BSM.

### Negative-rate fix

When the forward rate can be ≤ 0, practitioners switch to:
- **Shifted (displaced) lognormal:** model $r + \alpha$ as lognormal for some positive shift $\alpha$, then back out $r$.
- **Bachelier / normal model:** assume the forward rate is *normally* distributed, allowing negative values.

## 11. Comparison Summary — One Formula, Many Flavors

| Instrument | Underlying in Black | Discount-factor adjustment |
|---|---|---|
| Option on futures / forward | Futures price $F_0(T)$ | $e^{-rT}$ on whole bracket |
| Caplet / floorlet | Forward rate (FRA rate) | $e^{-r(t+\text{AP})}$ × AP × notional |
| Swaption | Forward swap rate $R_{\text{fix}}$ | PVA × notional |
| Equity index option | Spot, with continuous dividend yield $q$ | Use BSM with $q$, or quote $F = S e^{(r-q)T}$ and use Black |

## 12. Vignette / Real-World Scenarios

- **A treasurer hedging floating-rate debt** buys an interest-rate cap to protect against rates rising above 5%. To value each caplet, you reach for Black, not BSM, because the underlying is a forward rate, not a stock.
- **An asset manager preparing for a 5-year corporate refinancing** in 12 months buys a *payer* swaption to lock in a fixed-rate ceiling. Black with $R_{\text{fix}}$ and PVA prices the optionality.
- **A commodity trader writing options on Brent futures** uses Black directly — no spot-price contortions, just $F_0(T)$ off the screen.

## 13. Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Using spot price $S_0$ instead of $F_0(T)$ | Defaults to BSM mechanically | The instant the underlying is "futures," "forward," "FRA," "swap rate" → Black |
| Forgetting to discount the **whole** bracket | Discounts only the strike term | Multiply $[\ldots]$ by $e^{-rT}$ — *both* terms inside |
| Adding $r$ in $d_1$ | BSM-habit error | Black $d_1$ has only $\ln(F/X) + \tfrac12\sigma^2 T$ in the numerator |
| Wrong discounting for caplets | Discounting from option expiration $t$ instead of payment date $t+\text{AP}$ | Caplets are "advanced set, settled in arrears" |
| Forgetting AP (caplets) or PVA (swaptions) multiplier | Bracket value is correct but missing scaling | Always multiply by Notional × scaling factor (AP or PVA) |
| Using percentages instead of decimals in $d_1$ | "5" vs "0.05" → enormous $d_1$ | Always work in decimals inside Black formulas |
| Applying Black to American options | Misses early-exercise value | Black is European-only; use [[Binomial Option Pricing Model|binomial]] for early exercise |
| Confusing payer vs receiver swaption | Reverses the call/put logic | Payer = pay fixed = put on bonds = gain when rates rise |
| Using Black at negative forward rates | $\ln$ of negative blows up | Switch to shifted lognormal or Bachelier |
| Treating futures-option payoff as the futures contract value itself | Daily settlement ≠ option payoff | Option payoff is $\max(F_T - X, 0)$, not the futures mark-to-market |

## 14. Memory Hooks

- **"Black = BSM with F replacing S, and discount the whole bracket."**
- **No $r$ in Black's $d_1$ — the forward already carries the asset.**
- **AP for caps, PVA for swaptions.** Plain Black stands alone for futures.
- **Payer = put, Receiver = call** (on bonds).
- **Lognormal dies when rates can be negative** — pivot to Bachelier.

## 15. Exam-Day Checklist

When a question describes an option, ask in order:

1. **Is the underlying a forward, futures, FRA, or swap rate?** → Black, not BSM.
2. **Is exercise European?** → Black ok. American? → binomial.
3. **Interest-rate option?** → caplet/floorlet → AP, advance-set/arrears discounting.
4. **Swaption?** → PVA replaces $e^{-rT}$; payer ↔ put, receiver ↔ call (on bonds).
5. **Are inputs decimals?** → 0.05 not 5.
6. **Negative-rate environment?** → shifted lognormal or Bachelier, not vanilla Black.
7. **Did I discount *both* terms inside the bracket?** → if not, you've made the most common Black error.

## 16. Related Concepts

- [[Black-Scholes-Merton Model]] — parent model
- [[Binomial Option Pricing Model]] — handles American exercise where Black can't
- [[Interest Rate Options — Caps and Floors]] — caplet/floorlet application
- [[Swaptions]] — swaption application with PVA
- [[Implied Volatility]] — what you back out of an observed Black price
- [[Option Greeks]]
- [[Put-Call Parity and Option Arbitrage]]
- [[Risk-Neutral Probabilities]] — why $E[F_T] = F_0$
- [[N(d1)]] · [[N(d2)]] — interpretation of the normal-CDF terms
- [[FRA]] — underlying for caplets/floorlets
- [[Forward Rate]] · [[Forward contract]] · [[Futures contract]]
