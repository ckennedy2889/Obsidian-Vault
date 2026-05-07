---
title: MRR-OIS Spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, spreads, banking-risk, liquidity-risk, credit-risk]
aliases: [MRR-OIS spread, Libor-OIS spread, LIBOR-OIS spread, OIS spread]
---

# MRR-OIS Spread

## The Real-World Analogy

Think of two very short-term rates.

One rate is the market reference rate, or MRR, which includes some bank credit and liquidity risk. The other is the OIS rate, tied to overnight lending and treated as having minimal counterparty credit risk.

The MRR-OIS spread measures the extra rate investors demand for bank-related term funding over a near-risk-free overnight swap benchmark.

```text
MRR
 -
OIS rate
 =
MRR-OIS spread
```

## Plain-English Definition

The [[MRR-OIS Spread]] is the amount by which the market reference rate exceeds the overnight indexed swap rate.

$$
\text{MRR-OIS spread} = \text{MRR} - \text{OIS rate}
$$

Historically, this was called the LIBOR-OIS spread. CFA now uses MRR language because LIBOR has been replaced by other market reference rates in many contexts.

## Why CFA Tests This

CFA tests MRR-OIS spread because it is a clean short-term indicator of banking-sector credit and liquidity stress.

The comparison is powerful because:

| Rate | What it contains |
|---|---|
| MRR | Term bank/reference-rate credit and liquidity risk |
| OIS rate | Overnight indexed swap rate with minimal counterparty credit risk |

So the spread isolates the market's concern about bank funding conditions more directly than many longer-term spreads.

## Formula

$$
\text{MRR-OIS spread} = \text{MRR} - \text{OIS rate}
$$

Use rates with comparable maturities.

## Worked Example

Suppose:

| Input | Value |
|---|---:|
| 3-month MRR | 1.20% |
| 3-month OIS rate | 0.85% |

Then:

$$
\text{MRR-OIS spread}=1.20\%-0.85\%=0.35\%
$$

Convert to basis points:

$$
0.35\%=35\text{ bps}
$$

Interpretation: the market reference rate is 35 bps above the OIS benchmark, suggesting compensation for bank funding credit/liquidity risk.

## Interpretation

| Movement | Interpretation |
|---|---|
| Spread widens | Bank funding stress, credit risk, or liquidity risk is increasing |
| Spread narrows | Funding conditions are improving or perceived bank risk is falling |

The OIS rate is useful because it is linked to overnight rates and contains minimal counterparty credit risk. That makes it a cleaner reference point for isolating the risky component in MRR.

## MRR-OIS vs TED Spread

| Spread | Formula | Benchmark | Main interpretation |
|---|---|---|---|
| [[MRR-OIS Spread]] | MRR - OIS | Near-risk-free overnight indexed swap rate | Bank funding stress and liquidity risk |
| [[TED spread]] | MRR - T-bill rate | Short-term government bill | Bank credit/liquidity risk plus flight-to-quality effects |

Both spreads widen when perceived banking-sector stress rises. The MRR-OIS spread is often viewed as more directly focused on bank funding risk because OIS is a swap benchmark with minimal credit risk.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Using T-bill rate | That is [[TED spread]], not MRR-OIS |
| Reversing the formula | MRR-OIS = MRR - OIS |
| Treating OIS as high credit risk | OIS includes minimal counterparty credit risk |
| Ignoring current terminology | CFA may say MRR-OIS instead of LIBOR-OIS |
| Calling it a bond spread | It is a short-term rate spread, not a corporate bond yield spread |

## Memory Hook

```text
OIS is the cleaner overnight benchmark.
MRR-OIS is the extra bank funding stress over that cleaner benchmark.
```

## Related Concepts

- [[TED spread]]
- [[Swap spread]]
- [[I-spread]]
- [[Market reference rate]]
- [[Overnight Indexed Swap]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Bank funding risk]]
