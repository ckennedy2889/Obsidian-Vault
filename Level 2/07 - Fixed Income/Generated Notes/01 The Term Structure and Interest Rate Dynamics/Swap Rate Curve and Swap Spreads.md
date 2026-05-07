---
title: Swap Rate Curve and Swap Spreads
subject: Fixed Income
tags: [CFA-L2, FixedIncome, Swaps, Spreads, TermStructure]
aliases: [swap rate curve, swap curve, swap spread, I-spread, MRR-OIS spread, TED spread]
---

# Swap Rate Curve and Swap Spreads

## The Real-World Analogy

The government yield curve is like the public road system. The swap curve is like the private banking highway.

Both help market participants move through the interest-rate world, but they reflect different risks and different users.

## Swap Rate Curve

The [[swap rate curve]] is the term structure of fixed rates on plain vanilla fixed-for-floating interest rate swaps.

In a standard swap:

| Leg | Payment |
|---|---|
| Fixed leg | Pays the fixed swap rate |
| Floating leg | Pays a market reference rate, such as SOFR or another MRR |

The swap fixed rate is the rate that makes the swap value zero at initiation.

## Why Market Participants Use The Swap Curve

| Reason | Explanation |
|---|---|
| Bank credit benchmark | Swap rates reflect commercial bank credit risk rather than sovereign risk |
| Cross-country comparability | Swap markets are less tied to each government's bond market structure |
| More maturity points | Swap quotes may exist at more tenors than on-the-run government bonds |
| Bank valuation | Wholesale banks often hedge and value using swaps |

Retail banks are more likely to use government curves; wholesale banks are more likely to use swap curves.

## Swap Fixed Rate As A Par Rate

The swap fixed rate can be thought of as the coupon rate on a par bond priced from the relevant spot curve.

For annual payments and notional of 1:

$$
1 = \sum_{t=1}^{T} \frac{SFR_T}{(1+z_t)^t} + \frac{1}{(1+z_T)^T}
$$

Solving:

$$
SFR_T = \frac{1 - DF_T}{\sum_{t=1}^{T} DF_t}
$$

where:

| Term | Meaning |
|---|---|
| $SFR_T$ | Swap fixed rate for maturity $T$ |
| $DF_t$ | Discount factor for period $t$ |
| $z_t$ | Spot rate for maturity $t$ |

## Swap Spread

The [[swap spread]] is:

$$
\boxed{
\text{Swap spread}_T = \text{Swap rate}_T - \text{Government bond yield}_T
}
$$

Example:

| Input | Value |
|---|---:|
| 2-year swap rate | 2.02% |
| 2-year Treasury yield | 1.61% |

$$
\text{Swap spread} = 2.02\% - 1.61\% = 0.41\% = 41 \text{ bps}
$$

## Interpretation

Swap spreads are usually positive because swap rates reflect commercial bank credit risk, while government bonds are generally lower credit risk.

Higher swap spreads indicate more compensation for:

| Risk | Meaning |
|---|---|
| Credit risk | Bank/reference-rate credit concerns |
| Liquidity risk | Relative difficulty trading or financing |
| Mispricing | Especially for default-free bonds |

For a default-free bond, a swap spread does not represent default risk of that bond. It more likely reflects liquidity or mispricing relative to the swap benchmark.

## Short-Term Risk Spreads

Short-term rate spreads help gauge economy-wide credit and liquidity risk.

| Spread | Formula / Idea | Interpretation |
|---|---|---|
| TED spread | MRR or bank borrowing rate minus T-bill rate | Banking-system credit and liquidity risk |
| MRR-OIS spread | Market reference rate minus overnight indexed swap rate | Bank funding stress and liquidity risk |
| I-spread | Risky bond yield minus interpolated swap rate | Bond spread over swap benchmark |

Rising spreads usually signal rising perceived credit risk, liquidity stress, or flight to quality.

## Exam Traps

| Trap | Correction |
|---|---|
| Saying swap rate is the floating rate | The swap rate is the fixed rate. |
| Using mismatched maturities | Swap spread uses same-maturity swap rate and government yield. |
| Forgetting bps conversion | 0.41% = 41 bps. |
| Saying swap spreads must always be positive | They are usually positive, but negative swap spreads can occur. |
| Treating I-spread as Treasury spread | I-spread is spread over the swap curve, interpolated if needed. |
| Saying TED spread is a long-term credit spread | It is a short-term banking-sector credit/liquidity gauge. |

## Memory Hook

```text
Swap curve = fixed rates on swaps.
Swap spread = swap rate minus Treasury.
TED/MRR-OIS = short-term stress thermometers.
```

## Related Concepts

- [[Swap spread]]
- [[Swap rate curve]]
- [[I-spread]]
- [[TED spread]]
- [[Liquidity risk]]
- [[Credit risk]]
- [[Term Structure of Credit Spreads]]
