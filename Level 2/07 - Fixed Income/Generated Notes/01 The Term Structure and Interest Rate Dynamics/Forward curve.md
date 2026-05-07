---
title: Forward curve
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, forward-rates, active-management, yield-curve]
aliases: [Forward curve, Forward rate curve, Implied forward curve]
---

# Forward curve

## The Real-World Analogy

The [[Spot curve]] is your average speed from the starting line to each mile marker. The [[Forward curve]] is your speed between future mile markers.

If the average speed from mile 0 to mile 5 is higher than the average speed from mile 0 to mile 2, the later segment must be faster than the earlier average. That is the core intuition behind forward rates.

```text
Spot rates = cumulative average rates
Forward rates = marginal future-period rates
```

## Plain-English Definition

The forward curve is the term structure of [[Forward rate|forward rates]].

A forward rate is an interest rate agreed today for a loan that starts in the future. The forward curve shows those implied future-period rates across maturities.

## Why CFA Tests This

CFA tests the forward curve because it links:

| Topic | Forward curve role |
|---|---|
| [[Spot curve]] | Forward rates are implied by spot rates through no-arbitrage |
| [[Yield curve]] shape | Forward curve lies above/below spot curve depending on slope |
| Active bond management | Managers profit if future spot rates differ from today's forward curve |
| [[Rolling Down the Yield Curve]] | Roll-down relies on curve shape and future rate assumptions |
| Forward price evolution | If future spot rates evolve as implied by forwards, forward prices remain unchanged |

## Forward Rate Model

For spot rates $z_A$ and $z_B$, the no-arbitrage relationship is:

$$
(1+z_B)^B = (1+z_A)^A(1+f_{A,B-A})^{B-A}
$$

Solving:

$$
f_{A,B-A}=\left[\frac{(1+z_B)^B}{(1+z_A)^A}\right]^{\frac{1}{B-A}}-1
$$

where:

| Symbol | Meaning |
|---|---|
| $z_A$ | Spot rate to time $A$ |
| $z_B$ | Spot rate to time $B$ |
| $f_{A,B-A}$ | Forward rate starting at $A$ for $B-A$ periods |

The no-arbitrage mechanism:

```text
Invest to B years directly
must equal
invest to A years, then lock in a forward rate from A to B.
```

## Worked Example

Suppose:

$$
z_2=4\%, \qquad z_5=6\%
$$

Find the three-year forward rate starting two years from now:

$$
f_{2,3}
$$

Use:

$$
(1+z_5)^5=(1+z_2)^2(1+f_{2,3})^3
$$

Plug in:

$$
(1.06)^5=(1.04)^2(1+f_{2,3})^3
$$

Rearrange:

$$
(1+f_{2,3})^3=\frac{(1.06)^5}{(1.04)^2}
$$

Compute:

$$
(1.06)^5=1.338226
$$

$$
(1.04)^2=1.081600
$$

$$
\frac{1.338226}{1.081600}=1.237274
$$

Take the cube root:

$$
1+f_{2,3}=1.237274^{1/3}=1.0735
$$

So:

$$
f_{2,3}=7.35\%
$$

The forward rate is above the five-year spot rate because the spot curve is upward sloping. The later marginal rate must be high enough to pull the longer average up.

## Curve Shape Implications

| Spot curve shape | Forward curve position | Why |
|---|---|---|
| Upward sloping | Forward curve lies above the spot curve | Marginal future rates must exceed the rising average |
| Downward sloping | Forward curve lies below the spot curve | Marginal future rates must be below the falling average |
| Flat | Forward curve equals spot curve | Every period has the same rate |

This is an exam favorite. If the spot curve is downward sloping, the forward curve is most likely below the spot curve.

## Active Management Interpretation

If future spot rates evolve exactly as today's forward curve implies:

```text
All bonds earn the one-period risk-free rate over the holding period.
Forward prices remain unchanged.
```

Active bond management assumes the current forward curve may be wrong.

If a manager believes future spot rates will be lower than the current forward rates, bonds are attractive because the market is discounting future cash flows too heavily.

```text
Expected future spot rates < current forward rates
        ->
Buy bonds / extend exposure
```

If future spot rates turn out higher than forward rates, bond prices will be lower than expected.

## Forward Rates Are Not Automatically Forecasts

Forward rates are no-arbitrage implied rates.

Under [[Pure expectations theory]], forward rates may be interpreted as expected future spot rates. Under [[Liquidity preference theory]], forward rates include liquidity premiums and are upwardly biased estimates of future spot rates.

Safe CFA wording:

```text
Forward rates are implied by today's spot curve.
They are forecasts only under extra term-structure assumptions.
```

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Treating forwards as guaranteed future spot rates | They are implied rates, not necessarily forecasts |
| Forgetting the geometric relationship | Use compound returns, not simple subtraction |
| Thinking upward spot curve means forwards are just slightly above short rates | Forwards can be above the long spot rate |
| Reversing curve-shape rule | Upward spot curve -> forwards above; downward -> forwards below |
| Confusing forward curve with par curve | Forward curve is marginal future-period rates |

## Memory Hook

```text
Spot = average to a date.
Forward = marginal rate between dates.
```

If the average is rising:

```text
the marginal rate must be above the average.
```

## Related Concepts

- [[Forward rate]]
- [[Spot curve]]
- [[Spot rate]]
- [[Discount factor]]
- [[Par curve]]
- [[Term Structure Theories]]
- [[Rolling Down the Yield Curve]]
- [[Pure expectations theory]]
- [[Liquidity preference theory]]
