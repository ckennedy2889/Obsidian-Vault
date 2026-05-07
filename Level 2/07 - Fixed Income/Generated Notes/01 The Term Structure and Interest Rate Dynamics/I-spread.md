---
title: I-spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, spreads, swap-curve, credit-risk, liquidity-risk]
aliases: [I-spread, Interpolated spread, Interpolated spread over swaps, I spread]
---

# I-spread

## The Real-World Analogy

Think of the [[Swap curve]] as the "banking-sector benchmark road." It tells you the market's base interest rate for different maturities using fixed rates on standard interest rate swaps.

Now imagine a corporate bond is driving on that same road, but it has extra baggage: [[Credit risk]], [[Liquidity risk]], and possibly some issue-specific cheapness or richness. The I-spread measures how much extra yield that bond offers above the swap-road benchmark at the same maturity.

```text
Corporate bond yield
        -
same-maturity swap rate
        =
I-spread
```

The "I" stands for **interpolated** because the exact swap maturity often does not exist. If the bond matures in 1.6 years and the swap curve gives 1.5-year and 2-year rates, you interpolate the 1.6-year swap rate.

## Plain-English Definition

The [[I-spread]], or [[Interpolated spread]], is the difference between a credit-risky bond's [[Yield to maturity]] and the same-maturity rate from the [[Swap rate curve]].

$$
\text{I-spread} = \text{Bond YTM} - \text{Interpolated swap rate}
$$

If the bond's exact maturity is quoted on the swap curve, use that swap rate. If not, estimate the missing same-maturity swap rate by [[Linear interpolation]].

## Why CFA Tests This

CFA tests I-spread because analysts need a way to separate:

```text
time value of money
from
credit/liquidity compensation
```

A bond's yield contains both:

| Yield component | Meaning |
|---|---|
| Benchmark rate | Compensation for time value of money, using the swap curve |
| Spread | Extra compensation for credit risk, liquidity risk, and relative value |

The I-spread uses the [[Swap curve]] as the benchmark, not the government curve. That matters because many market participants, especially wholesale banks and derivatives users, view the swap curve as a more relevant benchmark than the government yield curve.

## Formula

The basic formula is:

$$
I_T = y_T - s_T
$$

where:

| Symbol | Meaning |
|---|---|
| $I_T$ | I-spread for maturity $T$ |
| $y_T$ | Bond yield to maturity for maturity $T$ |
| $s_T$ | Same-maturity swap rate from the swap curve |

When the exact maturity is missing, first interpolate:

$$
s_T = s_L + \frac{T-L}{U-L}(s_U-s_L)
$$

where:

| Symbol | Meaning |
|---|---|
| $L$ | Lower maturity available on the swap curve |
| $U$ | Upper maturity available on the swap curve |
| $T$ | Bond maturity between $L$ and $U$ |
| $s_L$ | Swap rate at lower maturity |
| $s_U$ | Swap rate at upper maturity |

Then:

$$
I_T = y_T - s_T
$$

## Worked Example

A 6% Zinni, Inc. bond matures in 1.6 years and yields 2.35%. The swap curve does not quote a 1.6-year swap rate, but it gives:

| Maturity | Swap rate |
|---|---:|
| 1.5 years | 1.35% |
| 2.0 years | 1.50% |

### Step 1: Identify the interval

The bond's 1.6-year maturity falls between 1.5 years and 2.0 years.

```text
1.5 years ---- 1.6 years ---------------- 2.0 years
```

The bond is 0.1 years above the lower bound. The total interval is 0.5 years.

$$
\frac{T-L}{U-L}=\frac{1.6-1.5}{2.0-1.5}=\frac{0.1}{0.5}=0.20
$$

So 1.6 years is 20% of the way from 1.5 years to 2.0 years.

### Step 2: Interpolate the swap rate

$$
s_{1.6}=s_{1.5}+\frac{1.6-1.5}{2.0-1.5}(s_{2.0}-s_{1.5})
$$

Plug in:

$$
s_{1.6}=1.35\%+0.20(1.50\%-1.35\%)
$$

$$
s_{1.6}=1.35\%+0.20(0.15\%)
$$

$$
s_{1.6}=1.35\%+0.03\%=1.38\%
$$

### Step 3: Calculate the I-spread

$$
\text{I-spread}=2.35\%-1.38\%
$$

$$
\text{I-spread}=0.97\%=97\text{ bps}
$$

Interpretation: Zinni's bond yields 97 bps more than the interpolated swap benchmark for the same maturity.

## Mechanism: What The I-spread Is Really Doing

A bond yield by itself is hard to interpret. A 5% yield might be high or low depending on the benchmark curve. The I-spread asks:

> "How much extra yield does this bond offer over the swap-market benchmark at the same maturity?"

That matters because the swap curve already reflects a broad private-sector or bank-related benchmark rate. The I-spread then isolates the bond's extra compensation relative to that benchmark.

```text
Bond yield
  = swap benchmark rate
  + credit/liquidity/relative-value spread
```

So a higher I-spread usually indicates higher compensation for:

| Source | Why it widens the I-spread |
|---|---|
| Credit risk | Investors demand more yield for default or downgrade risk |
| Liquidity risk | Investors demand more yield for harder-to-trade bonds |
| Cheapness / mispricing | The bond may be cheap relative to the swap curve |

## I-spread vs Swap Spread vs G-spread vs Z-spread

| Spread | Benchmark | Formula / idea | Main limitation |
|---|---|---|---|
| [[I-spread]] | Swap curve | Bond YTM - interpolated swap rate | One-point yield comparison; does not discount each cash flow |
| [[Swap spread]] | Government bond yield | Swap rate - same-maturity government yield | Describes swap curve vs government curve, not a specific risky bond's spread over swaps |
| [[G-spread]] | Government yield curve | Bond YTM - interpolated government yield | Uses government curve, not swap curve |
| [[Z-spread]] | Spot curve | Constant spread added to every spot rate to match market price | More precise, but assumes no interest rate volatility and is not enough for embedded options |
| [[Option-Adjusted Spread]] | Interest-rate tree / paths | Spread after removing embedded option value | Model-dependent |

The key distinction:

```text
I-spread compares one bond YTM to one interpolated swap rate.
Z-spread reprices every cash flow using a full spot curve.
```

That is why the [[Z-Spread]] is usually more precise for valuation. The I-spread is simpler and faster.

## Exam Traps

| Trap | Why it is tempting | Correct reflex |
|---|---|---|
| Using Treasury yields | Many spreads are over governments | I-spread uses the swap curve |
| Forgetting interpolation | Bond maturity rarely matches a quoted swap tenor | Interpolate the swap rate to the bond maturity |
| Subtracting in the wrong direction | Both are yields | I-spread = bond yield - swap rate |
| Treating I-spread as a cash-flow valuation spread | It feels like Z-spread | I-spread is a YTM-to-benchmark comparison |
| Calling the spread pure credit risk | Credit risk is important | It can also include liquidity risk and relative mispricing |
| Forgetting basis points | 0.97% is not 0.97 bps | 0.97% = 97 bps |

## Memory Hooks

```text
I = Interpolated.
I-spread = bond yield over interpolated swap rate.
```

Exam-day chain:

```text
Find bond YTM
Find/interpolate same-maturity swap rate
Subtract: bond yield - swap rate
Convert to bps
```

## Related Concepts

- [[Swap curve]]
- [[Swap rate curve]]
- [[Swap spread]]
- [[G-spread]]
- [[Z-Spread]]
- [[Option-Adjusted Spread]]
- [[Yield to maturity]]
- [[Linear interpolation]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Term Structure of Credit Spreads]]
