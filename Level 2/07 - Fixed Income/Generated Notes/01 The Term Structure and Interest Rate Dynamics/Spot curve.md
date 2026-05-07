---
title: Spot curve
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, spot-rates, valuation, zero-coupon-rates]
aliases: [Spot curve, Spot yield curve, Zero curve, Zero-coupon curve, Strip curve]
---

# Spot curve

## The Real-World Analogy

The [[Spot curve]] is like a price list for delivery dates.

If you want \$1 delivered in one year, use the one-year spot rate. If you want \$1 delivered in ten years, use the ten-year spot rate. The spot curve tells you the correct discount rate for each future cash-flow date.

```text
Cash flow date -> maturity-matched spot rate -> discount factor -> present value
```

## Plain-English Definition

The spot curve is the term structure of [[Spot rate|spot rates]], also called zero-coupon rates.

A spot rate is the yield on a risk-free zero-coupon payment at a specific maturity. Therefore, the spot curve is the set of rates used to discount individual cash flows at different dates.

## Why CFA Tests This

CFA tests the spot curve because it is the main valuation curve for option-free fixed cash flows.

For any option-free bond:

$$
P_0 = \sum_{t=1}^{T}\frac{CF_t}{(1+z_t)^t}
$$

where $z_t$ is the spot rate for cash flow date $t$.

The mechanism:

```text
Each cash flow has its own maturity.
Each maturity has its own spot rate.
Each spot rate creates its own discount factor.
```

## Spot Curve vs Par Curve vs Forward Curve

| Curve | What it shows | Main use |
|---|---|---|
| [[Spot curve]] | Zero-coupon rates by maturity | Discount each dated cash flow |
| [[Par curve]] | Coupon rates/YTMs for bonds priced at par | Observable benchmark input; bootstrapping |
| [[Forward curve]] | Future rates implied by today's spot curve | No-arbitrage future-period rates and active-rate views |

The spot curve is usually the valuation engine. The par curve is often the observable input. The forward curve is implied by the spot curve.

## Formula Link To Discount Factors

For maturity $T$:

$$
DF_T=\frac{1}{(1+z_T)^T}
$$

For a single cash flow:

$$
PV_0=CF_T \times DF_T
$$

or:

$$
PV_0=\frac{CF_T}{(1+z_T)^T}
$$

## Worked Example

Suppose a three-year annual-pay bond has:

| Cash flow date | Cash flow | Spot rate |
|---|---:|---:|
| Year 1 | 40 | 5% |
| Year 2 | 40 | 6% |
| Year 3 | 1,040 | 7% |

Value:

$$
P_0=\frac{40}{1.05}+\frac{40}{(1.06)^2}+\frac{1{,}040}{(1.07)^3}
$$

Compute:

$$
\frac{40}{1.05}=38.10
$$

$$
\frac{40}{(1.06)^2}=35.60
$$

$$
\frac{1{,}040}{(1.07)^3}=848.95
$$

So:

$$
P_0=38.10+35.60+848.95=922.65
$$

The spot curve tells you why the bond is below par: the coupon is low relative to the maturity-specific discount rates.

## Curve Shape Implications

When the spot curve is flat, spot rates, par rates, and forward rates are equal.

When the spot curve slopes:

| Spot curve shape | Forward curve implication |
|---|---|
| Upward sloping | Forward rates lie above spot rates |
| Downward sloping | Forward rates lie below spot rates |
| Flat | Forward rates equal spot rates |

Why? A long spot rate is a geometric average of shorter spot and forward rates. If the average is rising, the marginal future rates must be above the average.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Treating YTM as the spot rate | YTM is one blended bond yield; spot rates are date-specific |
| Using par rates directly for valuation | Bootstrap the spot curve first |
| Forgetting spot rates are zero-coupon rates | One cash-flow date, one discount rate |
| Thinking forward rates are automatically forecasts | They are no-arbitrage implied rates unless assumptions say otherwise |
| Using spot curve for embedded-option exercise decisions | Use a rate tree/path framework for callable and putable bonds |

## Memory Hook

```text
Spot curve prices the pieces.
Par curve prices the package.
Forward curve prices the future segments.
```

## Related Concepts

- [[Spot rate]]
- [[Discount factor]]
- [[Forward curve]]
- [[Par curve]]
- [[Bootstrapping]]
- [[Arbitrage-free valuation]]
- [[Z-Spread]]
- [[Yield to maturity]]
- [[Binomial Interest Rate Tree]]
