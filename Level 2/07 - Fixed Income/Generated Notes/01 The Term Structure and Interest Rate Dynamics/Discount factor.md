---
title: Discount factor
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, spot-rates, valuation, present-value]
aliases: [Discount factor, Discount factors, Zero-coupon price, Present value factor]
---

# Discount factor

## The Real-World Analogy

A [[Discount factor]] is the price tag today for one risk-free dollar delivered in the future.

If someone promises you \$1 one year from now, you should not pay \$1 today because you could earn interest elsewhere. The discount factor tells you the fair price today.

```text
Future \$1
   |
   v
Discount by the spot rate for that date
   |
   v
Price today = discount factor
```

## Plain-English Definition

A discount factor is the present value of one unit of currency to be received at a specific future date.

For maturity $T$:

$$
DF_T = \frac{1}{(1+z_T)^T}
$$

where $z_T$ is the $T$-period [[Spot rate]].

If spot rates are continuously compounded:

$$
DF_T = e^{-z_TT}
$$

## Why CFA Tests This

Discount factors are the hidden engine behind almost every Level II Fixed Income valuation formula.

They show up in:

| Use | Why discount factors matter |
|---|---|
| [[Arbitrage-free valuation]] | Each dated cash flow is multiplied by its own discount factor |
| [[Bootstrapping]] | Par bonds can be solved into discount factors or spot rates |
| [[Par curve]] | Par rates are coupon rates that make discounted cash flows equal par |
| [[Z-Spread]] | Cash flows are discounted with benchmark rates plus a spread |
| [[Credit Valuation Adjustment]] | Expected exposures and expected losses are discounted |
| [[Swap Rate Curve and Swap Spreads]] | Swap fixed rates can be solved from discount factors |

The reason is simple: fixed income is about dated cash flows. A discount factor is the cleanest price of each date.

## Formula And Mechanics

For a cash flow $CF_T$ paid at time $T$:

$$
PV_0 = CF_T \times DF_T
$$

Using a spot rate:

$$
PV_0 = \frac{CF_T}{(1+z_T)^T}
$$

So:

$$
DF_T = \frac{PV_0}{CF_T}
$$

For a risk-free zero-coupon bond paying 100 at maturity:

$$
P_0 = 100 \times DF_T
$$

Therefore:

$$
DF_T = \frac{P_0}{100}
$$

## Worked Example

Suppose the two-year spot rate is 6%.

$$
DF_2=\frac{1}{(1.06)^2}
$$

$$
(1.06)^2=1.1236
$$

$$
DF_2=\frac{1}{1.1236}=0.8900
$$

Interpretation: one risk-free dollar paid in two years is worth about \$0.89 today.

If a bond pays \$1,000 in two years and no other cash flows:

$$
PV_0=1{,}000(0.8900)=890.00
$$

## Discount Factors In Coupon Bond Valuation

A coupon bond is a package of cash flows:

```text
Year 1 coupon
Year 2 coupon
Year 3 coupon + principal
```

Each date gets its own discount factor:

$$
P_0 = CF_1DF_1 + CF_2DF_2 + \cdots + CF_TDF_T
$$

This is the same as:

$$
P_0 = \sum_{t=1}^{T} CF_tDF_t
$$

This is why [[Yield to maturity]] can be dangerous as a shortcut. YTM uses one blended rate for all cash flows. Discount factors let you value each date directly.

## Discount Factors And Par Rates

For a par bond with face value 100 and annual coupon rate $c_T$:

$$
100=100c_T(DF_1+DF_2+\cdots+DF_T)+100DF_T
$$

Divide by 100:

$$
1=c_T\sum_{t=1}^{T}DF_t+DF_T
$$

Solve for the par rate:

$$
c_T=\frac{1-DF_T}{\sum_{t=1}^{T}DF_t}
$$

That is why the swap fixed rate and par bond coupon rate have the same structure. Both are fixed payments set so the present value equals par at initiation.

## Discount Factors And Forward Prices

Discount factors also connect to [[Forward price|forward prices]].

If $DF_A$ is the price today of \$1 delivered at time $A$, and $DF_B$ is the price today of \$1 delivered at time $B$, then the forward price for delivery from $A$ to $B$ is the bridge between them:

$$
DF_B = DF_A \times FP_{A,B-A}
$$

So:

$$
FP_{A,B-A}=\frac{DF_B}{DF_A}
$$

This says:

```text
Price today for delivery at B
  =
Price today for delivery at A
  x
Forward price from A to B
```

That is the price version of the same no-arbitrage logic behind forward rates.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Treating discount factor as a rate | It is a price today for \$1 in the future |
| Using the wrong maturity spot rate | Match each cash flow date to its own discount factor |
| Forgetting exponent $T$ | $DF_T=1/(1+z_T)^T$, not just $1/(1+z_T)$ unless $T=1$ |
| Mixing annual and semiannual periods | Match spot-rate compounding and cash-flow timing |
| Using YTM for every cash flow | Arbitrage-free valuation uses date-specific discount factors |

## Memory Hook

```text
Discount factor = price today of one future dollar.
```

If the discount factor is 0.89:

```text
\$1 later costs \$0.89 today.
```

## Related Concepts

- [[Spot rate]]
- [[Spot curve]]
- [[Par curve]]
- [[Bootstrapping]]
- [[Yield to maturity]]
- [[Arbitrage-free valuation]]
- [[Z-Spread]]
- [[Swap Rate Curve and Swap Spreads]]
- [[Credit Valuation Adjustment]]
