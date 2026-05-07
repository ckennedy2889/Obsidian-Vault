---
title: Bootstrapping Spot Rates
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, spot-rates, par-rates, bootstrapping]
aliases: [Bootstrapping, Bootstrap spot rates, Bootstrapping the spot curve, Par curve bootstrapping]
---

# Bootstrapping Spot Rates

## The Real-World Analogy

Imagine you are trying to price a meal kit, but the grocery store only sells bundles.

The one-day bundle has one ingredient, so its price tells you that ingredient's price directly. The two-day bundle has the first ingredient plus a second ingredient. Once you know the first ingredient's price, you can subtract it out and solve for the second. The three-day bundle contains the first, second, and third ingredients. Once you know the first two, you can solve for the third.

That is [[Bootstrapping|bootstrapping]] in Fixed Income.

The market often gives us coupon-paying bonds priced at par. Those are bundles of dated cash flows. But [[Arbitrage-free valuation]] needs the pure price of each individual dated cash flow, which comes from the [[Spot rate|spot rate]] or [[Discount factor]] for that date.

Bootstrapping is the process of unpacking the bundle one maturity at a time.

## Plain-English Definition

Bootstrapping is the process of deriving [[Spot rate|spot rates]], also called zero-coupon rates, from the [[Par curve]].

The key idea:

```text
Use the shortest-maturity par bond to solve the shortest spot rate.
Then use that known spot rate to solve the next spot rate.
Continue from shortest maturity to longest maturity.
```

This is **forward substitution**. Each answer becomes an input for the next step.

## Why CFA Tests This

CFA tests bootstrapping because Level II Fixed Income is built around this distinction:

```text
Par rates are observable package yields.
Spot rates are the cash-flow-by-cash-flow valuation rates.
```

A coupon bond is not one cash flow. It is a package:

```text
Year 1 coupon
Year 2 coupon
Year 3 coupon + principal
```

If the [[Yield curve]] is not flat, each of those dates needs its own discount rate. A single [[Yield to maturity]] is a useful summary, but it is not the arbitrage-free discount rate for every cash flow.

Bootstrapping gives you the spot curve you need for:

| Use | Why bootstrapping matters |
|---|---|
| [[Arbitrage-free valuation]] | Each cash flow is discounted at its own spot rate |
| [[Forward rate]] calculations | Forward rates are implied from spot rates |
| [[Z-spread]] and spread analysis | Spreads are added to benchmark spot rates |
| [[Binomial tree]] calibration | The tree must match the observed term structure |
| [[Yield curve]] interpretation | Par, spot, and forward curves can differ when the curve slopes |

## Par Rates Versus Spot Rates

A [[Par rate]] is the coupon rate that makes a bond trade at par, usually 100.

For an annual-pay two-year par bond:

$$
100=\frac{C}{1+y}+\frac{100+C}{(1+y)^2}
$$

Here $y$ is the two-year par rate, which is also the bond's [[Yield to maturity]] when it trades at par.

But spot-rate valuation says:

$$
100=\frac{C}{1+z_1}+\frac{100+C}{(1+z_2)^2}
$$

where:

| Symbol | Meaning |
|---|---|
| $z_1$ | One-year spot rate |
| $z_2$ | Two-year spot rate |
| $C$ | Coupon on the two-year par bond |

The two equations both price the same par bond, but they tell different stories. The par rate is a whole-bond yield. The spot rates are the pure discount rates for each cash-flow date.

## The Bootstrapping Algorithm

For annual-pay par bonds with face value 100:

### Step 1: One-Year Spot Rate

A one-year annual-pay par bond has only one cash flow:

$$
100=\frac{100+C_1}{1+z_1}
$$

Because the bond trades at par, the one-year spot rate equals the one-year par rate:

$$
z_1=c_1
$$

where $c_1$ is the one-year par coupon rate.

### Step 2: Two-Year Spot Rate

Use the two-year par bond and the already-known $z_1$:

$$
100=\frac{C_2}{1+z_1}+\frac{100+C_2}{(1+z_2)^2}
$$

Solve for $z_2$:

$$
100-\frac{C_2}{1+z_1}=\frac{100+C_2}{(1+z_2)^2}
$$

$$
(1+z_2)^2=\frac{100+C_2}{100-\frac{C_2}{1+z_1}}
$$

$$
z_2=\left(\frac{100+C_2}{100-\frac{C_2}{1+z_1}}\right)^{1/2}-1
$$

### Step 3: Three-Year Spot Rate

Use the three-year par bond and the already-known $z_1$ and $z_2$:

$$
100=\frac{C_3}{1+z_1}+\frac{C_3}{(1+z_2)^2}+\frac{100+C_3}{(1+z_3)^3}
$$

Solve for the last unknown:

$$
100-\frac{C_3}{1+z_1}-\frac{C_3}{(1+z_2)^2}=\frac{100+C_3}{(1+z_3)^3}
$$

Then:

$$
z_3=\left(\frac{100+C_3}{100-\frac{C_3}{1+z_1}-\frac{C_3}{(1+z_2)^2}}\right)^{1/3}-1
$$

The pattern continues for longer maturities:

```text
Known earlier spot rates discount earlier coupons.
The only remaining unknown is the final maturity spot rate.
```

## Worked Numerical Example

Assume annual-pay par bonds with face value 100:

| Maturity | Par rate |
|---|---:|
| 1 year | 5.00% |
| 2 years | 5.97% |
| 3 years | 6.91% |

### Step 1: Solve $z_1$

For a one-year annual-pay par bond, the one-year par rate equals the one-year spot rate:

$$
z_1=5.00\%
$$

### Step 2: Solve $z_2$

The two-year par bond pays a 5.97 coupon and returns 100 principal at maturity:

$$
100=\frac{5.97}{1.05}+\frac{105.97}{(1+z_2)^2}
$$

Discount the first coupon using the known one-year spot rate:

$$
\frac{5.97}{1.05}=5.6857
$$

Subtract the known present value from the bond price:

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

### Step 3: Solve $z_3$

The three-year par bond pays a 6.91 coupon:

$$
100=\frac{6.91}{1.05}+\frac{6.91}{(1.06)^2}+\frac{106.91}{(1+z_3)^3}
$$

Discount the known earlier coupons:

$$
\frac{6.91}{1.05}=6.5810
$$

$$
\frac{6.91}{(1.06)^2}=\frac{6.91}{1.1236}=6.1499
$$

Subtract those known present values:

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

The par curve gave us:

```text
5.00%, 5.97%, 6.91%
```

Bootstrapping extracted the spot curve:

```text
5.00%, 6.00%, 7.00%
```

## Discount Factor Version

Bootstrapping can also be done with [[Discount factor|discount factors]].

A discount factor is the present value of $1 paid at time $t$:

$$
DF_t=\frac{1}{(1+z_t)^t}
$$

For a par bond:

$$
100=C(DF_1+DF_2+\cdots+DF_T)+100DF_T
$$

or:

$$
100=C\sum_{t=1}^{T}DF_t+100DF_T
$$

When earlier discount factors are known, solve for the final one:

$$
DF_T=\frac{100-C\sum_{t=1}^{T-1}DF_t}{100+C}
$$

Then convert the discount factor into the spot rate:

$$
z_T=\left(\frac{1}{DF_T}\right)^{1/T}-1
$$

This version often feels cleaner because it shows the true object being uncovered: the price today of each future $1.

## Why the Method Is Arbitrage-Free

A coupon bond can be decomposed into zero-coupon pieces:

```text
Coupon at year 1     -> one zero-coupon bond maturing in year 1
Coupon at year 2     -> one zero-coupon bond maturing in year 2
Coupon + principal   -> one zero-coupon bond maturing in final year
```

If the coupon bond's price does not equal the sum of those zero-coupon pieces, arbitrage becomes possible. Traders could buy the cheaper package and sell the more expensive pieces, or vice versa.

That is the no-arbitrage foundation:

$$
\text{Coupon bond price}=\sum \text{PV of each dated cash flow}
$$

Bootstrapping extracts the spot rates that make this equality hold across the par curve.

## Shape of the Curve

When the par curve is flat, the spot curve and forward curve are also flat at the same rate.

When the par curve slopes, the curves differ:

| Par curve shape | Typical relationship |
|---|---|
| Upward sloping | Longer-maturity spot rates tend to be above same-maturity par rates |
| Downward sloping | Longer-maturity spot rates tend to be below same-maturity par rates |
| Flat | Par rates, spot rates, and forward rates are equal |

Why? A multi-year par rate is a coupon-bond yield. It blends the discount rates for all cash-flow dates. The final spot rate is a pure rate for the final cash flow only.

## Exam Traps

| Trap | Why it is tempting | Correct exam reflex |
|---|---|---|
| Calling it backward substitution | Later formulas have longer maturities | Bootstrapping works from shortest to longest: forward substitution |
| Treating par rates as spot rates | Both are quoted as yields | Only the one-period par rate equals the one-period spot rate |
| Forgetting the coupon in the final cash flow | Principal is visually dominant | Final cash flow is $100+C$ |
| Using YTM for every cash flow | YTM prices the whole bond | Arbitrage-free valuation uses spot rates by maturity |
| Mixing annual and semiannual inputs | CFA often changes compounding frequency | Match coupon, periods, and rates |
| Thinking bootstrapping is statistical resampling | Same word appears in Quant | In Fixed Income, it means extracting spot rates from par rates |
| Confusing with backward induction | Both appear in Fixed Income | Backward induction values bonds in a binomial tree; bootstrapping builds the spot curve |

## Memory Hooks

Bootstrapping means:

```text
Build the curve by pulling yourself up one maturity at a time.
```

Use this chain:

```text
Par curve -> known par bond prices -> solve z1 -> solve z2 -> solve z3 -> spot curve
```

And the exam-day mantra:

```text
Par rates are package rates.
Spot rates are single-date rates.
Bootstrapping unpackages the par curve.
```

## Related Concepts

- [[Par curve]]
- [[Par rate]]
- [[Spot rate]]
- [[Spot curve]]
- [[Discount factor]]
- [[Forward rate]]
- [[Yield to maturity]]
- [[Arbitrage-free valuation]]
- [[Z-spread]]
- [[Binomial tree]]
- [[Backward induction]]
- [[Term structure of interest rates]]
