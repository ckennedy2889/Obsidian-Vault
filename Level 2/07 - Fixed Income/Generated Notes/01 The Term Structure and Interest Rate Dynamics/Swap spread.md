---
title: Swap spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, swap-curve, spreads, credit-risk, liquidity-risk]
aliases: [Swap spread, Swap spreads, Swap rate spread]
---

# Swap spread

## The Real-World Analogy

Imagine two borrowers standing side by side.

One is the government, which is usually treated as the lower-credit-risk borrower in its own currency. The other is the banking/swap market, where fixed swap rates reflect the credit and liquidity conditions of commercial banks and swap counterparties.

The [[Swap spread]] asks:

> "How much more is the swap market fixed rate than the same-maturity government bond yield?"

That "extra" is the spread between the private-sector swap benchmark and the government benchmark.

```text
Swap market fixed rate
        -
Government bond yield
        =
Swap spread
```

## Plain-English Definition

The [[Swap spread]] for a given maturity is the difference between the fixed rate on an [[Interest rate swap]] and the yield on an on-the-run government bond of the same maturity.

$$
\text{Swap spread}_T = \text{Swap rate}_T - \text{Government bond yield}_T
$$

The maturity match is not optional. A five-year swap spread uses the five-year swap rate and the five-year government yield.

## Why CFA Tests This

CFA tests swap spreads because they are a simple way to compare:

```text
private-sector / bank-related benchmark rates
against
government benchmark rates
```

The [[Swap rate curve]] reflects fixed rates on plain vanilla fixed-for-floating swaps. Those rates are connected to market reference rates and bank/intermediary credit conditions. Government bond yields reflect government funding conditions, sovereign credit risk, scarcity, liquidity, and safe-asset demand.

So the swap spread helps analysts interpret credit and liquidity conditions by comparing two major benchmark curves.

## Formula

For maturity $T$:

$$
SS_T = S_T - G_T
$$

where:

| Symbol | Meaning |
|---|---|
| $SS_T$ | Swap spread for maturity $T$ |
| $S_T$ | Fixed swap rate for maturity $T$ |
| $G_T$ | Government bond yield for maturity $T$ |

Convert percentage points to basis points:

$$
1.00\% = 100 \text{ bps}
$$

$$
0.01\% = 1 \text{ bp}
$$

## Worked Example 1: Basic Swap Spread

Suppose:

| Input | Value |
|---|---:|
| 2-year fixed-for-floating swap rate | 2.02% |
| 2-year Treasury yield | 1.61% |

Use:

$$
\text{Swap spread} = \text{Swap rate} - \text{Treasury yield}
$$

Plug in:

$$
\text{Swap spread} = 2.02\% - 1.61\%
$$

$$
\text{Swap spread} = 0.41\%
$$

Convert to basis points:

$$
0.41\% \times 100 = 41\text{ bps}
$$

So the two-year swap spread is:

$$
\boxed{41\text{ bps}}
$$

Interpretation: the two-year fixed swap rate is 41 bps above the two-year government benchmark yield.

## Worked Example 2: Widening And Tightening

Suppose the five-year swap rate stays at 3.00%, but the five-year government yield changes.

| Scenario | 5-year swap rate | 5-year government yield | Swap spread |
|---|---:|---:|---:|
| Initial | 3.00% | 2.50% | 50 bps |
| Later | 3.00% | 2.20% | 80 bps |

The swap spread widened from 50 bps to 80 bps.

Why? The government yield fell relative to the swap rate. That could happen because investors rushed into government bonds, pushing their prices up and yields down, or because bank/swap-market credit and liquidity concerns increased relative to government bonds.

Now reverse it:

| Scenario | 5-year swap rate | 5-year government yield | Swap spread |
|---|---:|---:|---:|
| Initial | 3.00% | 2.50% | 50 bps |
| Later | 2.80% | 2.55% | 25 bps |

The swap spread tightened from 50 bps to 25 bps.

Interpretation: swap rates fell relative to government yields, or government yields rose relative to swap rates.

## Mechanism: Why Swap Spreads Are Usually Positive

Swap spreads are usually positive because government bonds generally have lower credit risk than the commercial-bank-related rates embedded in the swap market.

```text
Government curve
  = lower credit risk / safe-asset benchmark

Swap curve
  = private-sector rate benchmark with bank credit and liquidity elements
```

So if the swap market demands more compensation than the government market:

$$
S_T > G_T
$$

then:

$$
SS_T > 0
$$

That positive spread can be interpreted as compensation for credit and liquidity risk in the swap-market benchmark relative to the government benchmark.

## What A Higher Swap Spread Means

A higher swap spread usually indicates more compensation for:

| Driver | Intuition |
|---|---|
| Bank credit risk | Swap rates reflect private-sector/bank-related credit conditions |
| Liquidity risk | Investors may demand compensation for less liquid instruments or funding stress |
| Flight to quality | Government bond demand can push government yields down, widening the spread |
| Relative-value pressure | Supply/demand, dealer balance sheets, and hedging flows can move swap rates and Treasury yields differently |

The careful wording is:

> Higher swap spreads generally indicate higher perceived credit and liquidity risk relative to the government benchmark.

Do not say they are a pure credit-risk measure. Liquidity and technical factors can matter.

As a broad macro signal, swap spreads often widen during recessions or banking stress, when perceived credit and liquidity risk rises. They often narrow during expansions, when funding conditions and risk appetite improve. This is a directional interpretation, not a mechanical law.

## Default-Free Bond Caveat

For a default-free bond, the swap spread does **not** represent the bond's default risk. The bond is default-free by assumption.

For a default-free bond, a swap-spread comparison is more likely telling you about:

| Possibility | Meaning |
|---|---|
| Liquidity | The bond may be less liquid than the benchmark government bond |
| Mispricing | The bond may be cheap or rich relative to the swap benchmark |
| Benchmark differences | Swap and government curves reflect different market structures |

Exam reflex:

```text
Default-free bond + swap spread question
        ->
Do not choose default risk as the explanation.
Think liquidity or mispricing.
```

## Negative Swap Spread Caveat

CFA source summaries often say swap spreads are almost always positive, but real markets can show negative swap spreads in some maturities.

A negative swap spread means:

$$
\text{Swap rate}_T < \text{Government bond yield}_T
$$

That can happen when forces other than simple bank credit risk dominate, such as:

| Force | Effect |
|---|---|
| Heavy demand for receiving fixed in swaps | Pushes fixed swap rates lower |
| High government bond supply or reduced demand | Pushes government yields higher |
| Dealer balance sheet and regulatory constraints | Can make arbitrage difficult |
| Long-duration hedging flows | Can distort long-maturity swap spreads |

Exam wording matters. If CFA asks for the standard relationship, swap spreads are usually positive because governments generally have lower credit risk. If CFA asks whether they **must** be positive, the answer is no.

## Swap Spread vs I-spread vs TED/MRR-OIS

| Spread | Formula | Benchmark comparison | What it is mainly used for |
|---|---|---|---|
| [[Swap spread]] | Swap rate - government yield | Swap curve vs government curve | Private-sector benchmark risk relative to government benchmark |
| [[I-spread]] | Bond YTM - interpolated swap rate | Specific bond vs swap curve | Bond compensation over swap benchmark |
| [[TED spread]] | MRR/bank rate - T-bill rate | Bank borrowing vs short government rate | Short-term banking-system credit/liquidity stress |
| [[MRR-OIS Spread]] | MRR - OIS rate | Term bank reference rate vs near-risk-free overnight swap rate | Bank funding stress and liquidity risk |

The mistake to avoid:

```text
Swap spread is not bond yield minus swap rate.
That is I-spread.
```

## Exam Traps

| Trap | Why it is tempting | Correct reflex |
|---|---|---|
| Reversing the subtraction | Both are benchmark rates | Swap spread = swap rate - government yield |
| Using a risky corporate bond yield | You just studied I-spread and Z-spread | Swap spread uses swap rate and government yield |
| Mismatching maturities | The numbers may look close | Use same-maturity swap rate and government bond yield |
| Calling it pure default risk | Swap rates include credit elements | Interpret as credit plus liquidity plus market technicals |
| Saying swap spreads must be positive | Usually positive in curriculum examples | They can be negative in real markets |
| For default-free bond, choosing default risk | Spread language suggests credit | For a default-free bond, think liquidity or mispricing |
| Forgetting basis points | Percent and bps are easy to mix | 0.41% = 41 bps |

## Memory Hooks

```text
Swap spread = swap minus sovereign.
```

Use the order:

```text
S before G:
Swap rate - Government yield
```

And the comparison:

```text
Swap spread: swap curve over government curve.
I-spread: bond yield over interpolated swap curve.
```

## Related Concepts

- [[Swap rate curve]]
- [[Swap curve]]
- [[Swap Rate Curve and Swap Spreads]]
- [[I-spread]]
- [[G-spread]]
- [[Z-Spread]]
- [[TED spread]]
- [[MRR-OIS Spread]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[On-the-run]]
- [[Government bond yield curve]]
