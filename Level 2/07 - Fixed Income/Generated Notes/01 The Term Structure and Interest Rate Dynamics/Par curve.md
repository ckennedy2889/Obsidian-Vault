---
title: Par Curve
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, par-rates, bootstrapping, yield-curve]
aliases: [Par curve, Par rate curve, Par yield curve, Benchmark par curve]
---

# Par Curve

## The Real-World Analogy

Imagine a store posts prices for bundles, not individual items.

A one-year bond is like a tiny bundle: one coupon plus principal at year 1. A two-year bond is a larger bundle: coupon at year 1, coupon plus principal at year 2. A five-year bond is a still larger bundle. The market often shows us the yield on each bundle when the bundle is priced exactly at face value.

That price board is the [[Par curve]].

The catch is that an analyst often does **not** really want the bundle yield. To value any bond correctly, we need the price of each dated cash flow. The par curve is therefore useful because it is the observable starting point from which we can uncover the cleaner [[Spot curve]].

```text
Observed market bundles
        |
        v
Par curve: coupon/YTM for par bonds
        |
        v
Bootstrapping
        |
        v
Spot curve: discount rates for individual cash-flow dates
```

![Par curve pipeline](../Resources/attachments/par-curve-pipeline.png)

## Plain-English Definition

A [[Par curve]] is the sequence of [[Yield to maturity|yields to maturity]] or coupon rates for bonds of different maturities that are all priced at par, usually 100.

For a bond trading at par:

```text
Price = face value
Coupon rate = yield to maturity
```

So the par curve answers:

> "For each maturity, what coupon rate would make a benchmark bond sell for exactly 100?"

In CFA fixed income, the par curve usually means the par rates for government or other benchmark bonds with the same currency, credit risk, liquidity, tax treatment, and compounding convention. The practical benchmark is often built from liquid, recently issued on-the-run coupon bonds because those are the instruments whose prices are most reliably observed.

## Why The Par Curve Exists

The par curve exists because actual markets usually give analysts liquid coupon-bond yields, not a complete set of pure zero-coupon rates.

A coupon bond is a bundle of dated payments:

```text
Year 1: coupon
Year 2: coupon
Year 3: coupon + principal
```

If the [[Yield curve]] is not flat, those payments should not all be discounted at the same rate. A year-1 cash flow and a year-10 cash flow have different interest-rate risk, reinvestment risk, and opportunity cost. The [[Spot rate]] for each date is the arbitrage-free discount rate for that date.

But spot rates may not be directly observable. Par bonds often are observable. The par curve is the bridge:

```text
Liquid benchmark par bonds -> par rates -> bootstrapped spot rates -> valuation
```

That is why CFA tests the par curve. It is not just a definition. It is the input that lets you derive the rates needed for [[Arbitrage-free valuation]].

## Formula Version

For an annual-pay bond with face value 100, maturity $T$, and par coupon rate $c_T$, the par bond price is:

$$
100=\sum_{t=1}^{T}\frac{100c_T}{(1+z_t)^t}+\frac{100}{(1+z_T)^T}
$$

where:

| Symbol | Meaning |
|---|---|
| $c_T$ | T-year par rate, stated as a coupon rate |
| $z_t$ | t-year [[Spot rate]] |
| $100c_T$ | Annual coupon paid by the par bond |
| $100$ | Principal repaid at maturity |

This equation says something very important:

```text
The T-year par rate is the coupon rate that makes the bond price equal 100
when every cash flow is discounted using the correct spot rate.
```

Rearranging with [[Discount factor|discount factors]], where $DF_t=\frac{1}{(1+z_t)^t}$:

$$
100=100c_T\sum_{t=1}^{T}DF_t+100DF_T
$$

Divide by 100:

$$
1=c_T\sum_{t=1}^{T}DF_t+DF_T
$$

Solve for the par rate:

$$
c_T=\frac{1-DF_T}{\sum_{t=1}^{T}DF_t}
$$

This formula is the cleanest way to see the mechanism. The numerator, $1-DF_T$, is the total discount from receiving principal in the future instead of today. The denominator is the present value of a 1-per-period annuity. The par coupon rate is the coupon that exactly compensates the investor for that discount.

## Why Coupon Rate Equals YTM At Par

For any coupon bond, price moves opposite to market yield.

| Coupon relative to market yield | Bond price |
|---|---|
| Coupon rate > YTM | Premium bond |
| Coupon rate = YTM | Par bond |
| Coupon rate < YTM | Discount bond |

The reason is mechanical. If the coupon is too high relative to the required return, investors pay more than face value to get those rich coupons. If the coupon is too low, investors pay less than face value. At exactly par, the coupon is neither too rich nor too weak, so coupon rate and YTM meet.

That is why each point on the par curve can be quoted as either:

```text
the coupon rate that makes the benchmark bond trade at 100
```

or:

```text
the YTM on a benchmark bond trading at 100
```

Those two descriptions are equivalent only because the bond is priced at par.

## Par Curve vs Spot Curve vs Forward Curve

| Curve | What it represents | Main CFA use |
|---|---|---|
| [[Par curve]] | Coupon rates/YTMs for par bonds by maturity | Observable benchmark curve; input to [[Bootstrapping]] |
| [[Spot curve]] | Zero-coupon rates by maturity | Discount each cash flow directly |
| [[Forward curve]] | Future rates implied by spot rates | No-arbitrage future-period rates |

The important distinction:

```text
Par rate = yield on a coupon-bond package
Spot rate = discount rate for one maturity date
Forward rate = implied marginal future rate
```

A common exam trap is treating the five-year par rate as the five-year spot rate. That is usually wrong. The one-period par rate equals the one-period spot rate because there is only one cash-flow date. For longer maturities, the par rate is a blended coupon-bond yield.

More precisely, the par rate behaves like a weighted average of the spot rates attached to the bond's cash-flow dates. It is weighted heavily toward the maturity-date spot rate because the largest cash flow is principal repayment at maturity, but it is still pulled by the earlier coupon-date spot rates.

![Par, spot, and forward curve relationship](../Resources/attachments/par-spot-forward-relationship.png)

## Bootstrapping Implication

Level II explicitly tests how [[Spot rate|zero-coupon rates]] are obtained from the par curve through [[Bootstrapping]].

The logic is forward substitution:

```text
1-year par bond -> solve z1
2-year par bond + known z1 -> solve z2
3-year par bond + known z1 and z2 -> solve z3
Continue to longer maturities
```

For annual-pay bonds, the one-year spot rate equals the one-year par rate:

$$
z_1=c_1
$$

For the two-year par bond:

$$
100=\frac{100c_2}{1+z_1}+\frac{100+100c_2}{(1+z_2)^2}
$$

The only unknown is $z_2$, because $z_1$ was solved from the one-year par bond.

For the three-year par bond:

$$
100=\frac{100c_3}{1+z_1}+\frac{100c_3}{(1+z_2)^2}+\frac{100+100c_3}{(1+z_3)^3}
$$

The only unknown is $z_3$, because $z_1$ and $z_2$ are already known.

This is why the par curve is not the final valuation curve. It is the raw material used to build the spot curve.

![Bootstrapping from the par curve](../Resources/attachments/par-curve-bootstrapping-ladder.png)

## Worked Numerical Example

Assume annual-pay benchmark par bonds with face value 100:

| Maturity | Par rate |
|---|---:|
| 1 year | 5.00% |
| 2 years | 5.97% |
| 3 years | 6.91% |

### Step 1: Solve The One-Year Spot Rate

The one-year par bond has only one cash flow:

$$
100=\frac{105}{1+z_1}
$$

So:

$$
1+z_1=\frac{105}{100}=1.05
$$

$$
z_1=5.00\%
$$

### Step 2: Solve The Two-Year Spot Rate

The two-year par bond pays a 5.97 coupon in year 1 and 105.97 in year 2:

$$
100=\frac{5.97}{1.05}+\frac{105.97}{(1+z_2)^2}
$$

Discount the first coupon:

$$
\frac{5.97}{1.05}=5.6857
$$

Subtract it from the price:

$$
100-5.6857=94.3143
$$

So:

$$
94.3143=\frac{105.97}{(1+z_2)^2}
$$

Rearrange:

$$
(1+z_2)^2=\frac{105.97}{94.3143}=1.12358
$$

Take the square root:

$$
1+z_2=\sqrt{1.12358}=1.0600
$$

Therefore:

$$
z_2=6.00\%
$$

### Step 3: Solve The Three-Year Spot Rate

The three-year par bond pays 6.91 in years 1 and 2, then 106.91 in year 3:

$$
100=\frac{6.91}{1.05}+\frac{6.91}{(1.06)^2}+\frac{106.91}{(1+z_3)^3}
$$

Known present values:

$$
\frac{6.91}{1.05}=6.5810
$$

$$
\frac{6.91}{(1.06)^2}=\frac{6.91}{1.1236}=6.1499
$$

Subtract:

$$
100-6.5810-6.1499=87.2691
$$

So:

$$
87.2691=\frac{106.91}{(1+z_3)^3}
$$

Rearrange:

$$
(1+z_3)^3=\frac{106.91}{87.2691}=1.22506
$$

Take the cube root:

$$
1+z_3=1.22506^{1/3}=1.0700
$$

Therefore:

$$
z_3=7.00\%
$$

The par curve was:

```text
5.00%, 5.97%, 6.91%
```

The bootstrapped spot curve is:

```text
5.00%, 6.00%, 7.00%
```

The spot rates are higher than the same-maturity par rates at years 2 and 3 because this curve is upward sloping. The par rate is pulled down by earlier coupons that are discounted at lower short-maturity spot rates.

## Curve Shape Implications

When the par curve is flat, par rates, spot rates, and forward rates all line up at the same level.

When the par curve slopes, they separate:

| Par curve shape | Typical implication |
|---|---|
| Upward sloping | Longer-maturity spot rates tend to be above same-maturity par rates; forward rates tend to be above spot rates |
| Downward sloping | Longer-maturity spot rates tend to be below same-maturity par rates; forward rates tend to be below spot rates |
| Flat | Par rates, spot rates, and forward rates are equal |

Why? A multi-period par rate is a coupon-bond yield. It averages the discounting effect across early coupons and final principal. A spot rate belongs to one final date. A forward rate is the marginal rate between dates.

Think of the spot rate as the average speed from the start of a trip to a given mile marker. The forward rate is the speed over the next segment. If the average speed is rising, the marginal segment speed must be above the average. If the average is falling, the marginal segment speed must be below the average.

## Valuation Implications

The par curve itself is not the best tool for valuing an arbitrary coupon bond. The usual sequence is:

```text
Par curve -> bootstrap spot curve -> discount each cash flow
```

For a bond with cash flows $CF_t$:

$$
P_0=\sum_{t=1}^{T}\frac{CF_t}{(1+z_t)^t}
$$

If you instead discount every cash flow at one maturity-matched par rate, you are using a blended yield as if it were a cash-flow-specific discount rate. That only works cleanly when the curve is flat or when the bond is itself the par benchmark whose yield is being quoted.

This matters for:

| Application | Why the par curve matters |
|---|---|
| [[Arbitrage-free valuation]] | Par rates are converted into spot rates used to value cash flows |
| [[Z-spread]] | The spread is added to benchmark spot rates, not simply to one par yield |
| [[Binomial tree]] calibration | The tree should reproduce prices implied by the benchmark term structure |
| [[Swap Rate Curve and Swap Spreads|Swap rates]] | A swap fixed rate is economically a par rate because the fixed leg is set so the swap has zero value at initiation |
| [[Key Rate Duration]] | Curve risk is often measured by shocking individual par rates |

## Key Rate Duration Implication

The par curve also matters for yield-curve risk.

[[Key Rate Duration]] measures sensitivity to a change in one specific maturity point on the curve while holding other key rates constant. CFA often describes those key rates as par rates on the benchmark curve.

That means a bond or portfolio can have different exposures to:

```text
1-year par rate
5-year par rate
10-year par rate
30-year par rate
```

This is more precise than [[Effective duration]] when yield curve shifts are not parallel.

For example, a portfolio may be much more sensitive to a 10-year par-rate shock than to a 2-year par-rate shock. Effective duration would compress that information into one number. Key rate duration decomposes the risk by maturity.

For an option-free par bond, the clean intuition is especially sharp: its value is most directly tied to the maturity-matched par rate. In the idealized par-bond setup, the maturity key rate duration equals the bond's effective duration, while the other key rate durations are zero. For non-par bonds, low-coupon bonds, and bonds with embedded options, the key rate duration profile can spread across maturities and can even show negative exposures at some points.

![Key rate duration par-rate shocks](../Resources/attachments/par-curve-key-rate-duration.png)

Exam implication:

```text
Use effective duration for a roughly parallel benchmark yield shift.
Use key rate duration for changes in curve shape.
```

## Common Exam Traps

| Trap | Why it is tempting | Correct exam reflex |
|---|---|---|
| Treating every par rate as a spot rate | Both are quoted as yields by maturity | Only the one-period par rate equals the one-period spot rate, unless the curve is flat |
| Forgetting that a par rate is a coupon-bond yield | The word "rate" sounds like a discount rate | A par rate prices a whole coupon-bond package |
| Using the par curve directly for arbitrary cash-flow valuation | It feels like the benchmark yield curve | Bootstrap the spot curve, then discount each dated cash flow |
| Thinking an upward par curve means the par rate equals the expected future short rate | Curve theories differ | Forward rates are implied by no-arbitrage; expectations require extra assumptions |
| Ignoring compounding frequency | Annual examples are easy | Match coupon frequency, compounding, and periods |
| Confusing [[Bootstrapping]] with [[Backward induction]] | Both appear in Level II fixed income | Bootstrapping extracts spot rates; backward induction values bonds in a tree |
| Thinking key rate duration shocks spot rates only | Some summaries use "yield" loosely | CFA often frames key rates as individual benchmark par rates |

## Memory Hooks

Par curve:

```text
The coupon rates that make benchmark bonds price at par.
```

Bootstrapping:

```text
Par curve gives package yields.
Bootstrapping unpackages them.
Spot curve prices the pieces.
```

Exam-day reflex:

```text
If the question gives par rates and asks for valuation rates, bootstrap.
If it asks about curve-shape risk, think key rate duration.
If it asks for a par bond, coupon rate = YTM = par rate.
```

## Related Concepts

- [[Par rate]]
- [[Spot rate]]
- [[Spot curve]]
- [[Forward rate]]
- [[Forward curve]]
- [[Bootstrapping]]
- [[Discount factor]]
- [[Yield to maturity]]
- [[Arbitrage-free valuation]]
- [[Z-spread]]
- [[Binomial tree]]
- [[Key Rate Duration]]
- [[Effective duration]]
- [[Swap Rate Curve and Swap Spreads]]
