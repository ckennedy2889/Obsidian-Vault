---
title: TED spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, spreads, banking-risk, liquidity-risk, credit-risk]
aliases: [TED spread, TED spreads]
---

# TED spread

## The Real-World Analogy

Imagine two short-term borrowers asking for money.

One is the government, represented by short-term T-bills. The other is the banking system, represented by a market reference rate such as MRR. The TED spread measures how much more the market charges banks than the government for short-term borrowing.

```text
Bank borrowing rate
        -
T-bill rate
        =
TED spread
```

If that gap widens, the market is saying, "I want more compensation to lend to banks instead of holding very safe government bills."

## Plain-English Definition

The [[TED spread]] is the difference between a short-term market reference rate and the yield on a same-maturity T-bill.

In current CFA wording:

$$
\text{TED spread} = \text{MRR} - \text{T-bill rate}
$$

Historically, TED referred to the difference between LIBOR and the T-bill yield. CFA now uses generic [[Market reference rate|market reference rate]] language as LIBOR replacements such as SOFR and other MRRs are used.

## Why CFA Tests This

CFA tests TED spread because it is a short-term stress indicator.

The intuition is:

| Rate | What it represents |
|---|---|
| MRR / bank borrowing rate | Short-term rate that includes bank credit and liquidity risk |
| T-bill rate | Short-term government rate, treated as very low credit risk |

So:

```text
Wider TED spread
  -> more perceived bank credit/liquidity stress

Narrower TED spread
  -> less perceived bank credit/liquidity stress
```

## Formula

$$
\text{TED spread} = \text{MRR} - \text{T-bill rate}
$$

Use matching maturities. A three-month TED spread uses a three-month MRR and a three-month T-bill rate.

## Worked Example

Suppose:

| Input | Value |
|---|---:|
| 3-month MRR | 0.33% |
| 3-month T-bill rate | 0.03% |

Then:

$$
\text{TED spread}=0.33\%-0.03\%=0.30\%
$$

Convert to basis points:

$$
0.30\%=30\text{ bps}
$$

Interpretation: the market reference rate is 30 bps above the same-maturity T-bill rate.

## Interpretation

The TED spread is used as an indication of perceived credit and liquidity risk in the banking sector.

| TED spread movement | Interpretation |
|---|---|
| Widening | Bank credit/liquidity stress is rising, or demand for T-bills is increasing |
| Narrowing | Bank funding stress is easing, or T-bill demand is normalizing |

Why T-bill demand matters: in a flight to quality, investors may buy T-bills aggressively. T-bill prices rise, T-bill yields fall, and the TED spread can widen even if the MRR does not move much.

## TED Spread vs MRR-OIS Spread vs Swap Spread

| Spread | Formula | Main signal |
|---|---|---|
| [[TED spread]] | MRR - T-bill rate | Bank credit/liquidity stress versus government bills |
| [[MRR-OIS Spread]] | MRR - OIS rate | Bank funding stress versus near-risk-free overnight swap benchmark |
| [[Swap spread]] | Swap rate - government yield | Swap curve versus government curve for a given maturity |
| [[I-spread]] | Bond YTM - interpolated swap rate | Specific bond spread over swap benchmark |

The TED spread is a short-term banking-sector risk gauge. It is not a long-term corporate bond spread.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Using a long-term Treasury yield | TED spread is short-term and same-maturity |
| Reversing the formula | TED = MRR - T-bill rate |
| Confusing with swap spread | Swap spread = swap rate - government yield |
| Saying it only measures default risk | It also reflects liquidity and flight-to-quality effects |
| Ignoring LIBOR replacement language | CFA now uses MRR terminology |

## Memory Hook

```text
TED = bank short rate over T-bill.
Wider TED = more banking-system stress.
```

## Related Concepts

- [[MRR-OIS Spread]]
- [[Swap spread]]
- [[I-spread]]
- [[Market reference rate]]
- [[T-bill]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Flight to quality]]
