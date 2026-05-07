---
title: G-spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, spreads, government-yield-curve, credit-risk, liquidity-risk]
aliases: [G-spread, Government spread, Spread over government bond, Nominal spread]
---

# G-spread

## The Real-World Analogy

Think of the government yield curve as the "clean baseline" price of borrowing in a currency. A corporate bond yield is usually higher because the corporate borrower brings extra baggage: [[Credit risk]], [[Liquidity risk]], and possibly issue-specific cheapness.

The [[G-spread]] asks a simple question:

> "How much extra yield does this bond offer over the government bond benchmark at the same maturity?"

```text
Corporate bond yield
        -
same-maturity government yield
        =
G-spread
```

## Plain-English Definition

The G-spread is the yield spread of a credit security over an actual or interpolated government bond yield of the same maturity.

$$
\text{G-spread}_T = \text{Bond YTM}_T - \text{Government yield}_T
$$

If there is no government bond with the exact same maturity, estimate the same-maturity government yield with [[Linear interpolation]].

## Why CFA Tests This

CFA tests G-spread because it is one of the simplest spread measures. It helps you separate:

```text
bond yield
  = government benchmark yield
  + compensation for credit/liquidity/relative value
```

The G-spread is quick and intuitive, but it is not the most precise valuation spread because it compares one bond yield to one benchmark yield.

## Formula

For maturity $T$:

$$
G_T = y_T - g_T
$$

where:

| Symbol | Meaning |
|---|---|
| $G_T$ | G-spread for maturity $T$ |
| $y_T$ | Bond yield to maturity |
| $g_T$ | Actual or interpolated same-maturity government yield |

If the government yield must be interpolated:

$$
g_T = g_L + \frac{T-L}{U-L}(g_U-g_L)
$$

where $L$ and $U$ are the lower and upper available government maturities around the bond maturity.

## Worked Example

A corporate bond matures in 4 years and yields 5.10%. The four-year government yield is 3.80%.

$$
\text{G-spread}=5.10\%-3.80\%=1.30\%
$$

Convert to basis points:

$$
1.30\% = 130\text{ bps}
$$

Interpretation: the bond offers 130 bps more than the same-maturity government benchmark.

## Interpolation Example

A bond matures in 3.4 years and yields 4.85%. The government curve gives:

| Maturity | Government yield |
|---|---:|
| 3.0 years | 3.20% |
| 4.0 years | 3.60% |

First interpolate the 3.4-year government yield:

$$
g_{3.4}=3.20\%+\frac{3.4-3.0}{4.0-3.0}(3.60\%-3.20\%)
$$

$$
g_{3.4}=3.20\%+0.40(0.40\%)=3.36\%
$$

Then calculate the G-spread:

$$
\text{G-spread}=4.85\%-3.36\%=1.49\%=149\text{ bps}
$$

## Interpretation

A higher G-spread generally means investors require more compensation above the government benchmark.

That compensation may reflect:

| Driver | Meaning |
|---|---|
| Credit risk | Higher default or downgrade concern |
| Liquidity risk | Harder-to-trade bond requires extra yield |
| Relative value | Bond may be cheap/rich versus the government curve |
| Tax or technical effects | Market structure can distort the benchmark comparison |

Do not call the G-spread pure default risk. It is a simple yield spread, and spreads can contain several risk and market components.

## G-spread vs I-spread vs Z-spread

| Spread | Benchmark | Formula / idea | Main limitation |
|---|---|---|---|
| [[G-spread]] | Government yield curve | Bond YTM - same-maturity government yield | One-point YTM comparison |
| [[I-spread]] | [[Swap curve]] | Bond YTM - same-maturity swap rate | One-point YTM comparison, but over swaps |
| [[Z-Spread]] | Benchmark spot curve | Constant spread added to every spot rate to match price | Better cash-flow valuation, but not option adjusted |
| [[Option-Adjusted Spread]] | Interest-rate tree / path model | Spread after removing embedded option value | Model-dependent |

The key mechanism:

```text
G-spread and I-spread compare yields.
Z-spread discounts every cash flow.
OAS adjusts for embedded option value.
```

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Using the swap curve | That is [[I-spread]], not G-spread |
| Forgetting interpolation | If exact maturity is missing, interpolate the government yield |
| Using spot rates cash-flow by cash-flow | That is closer to [[Z-Spread]] |
| Calling it option adjusted | G-spread does not adjust for embedded options |
| Forgetting bps conversion | 1.30% = 130 bps |

## Memory Hook

```text
G = Government.
G-spread = bond yield over government yield.
```

## Related Concepts

- [[I-spread]]
- [[Z-Spread]]
- [[Option-Adjusted Spread]]
- [[Swap spread]]
- [[Government bond yield curve]]
- [[Yield to maturity]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Linear interpolation]]
