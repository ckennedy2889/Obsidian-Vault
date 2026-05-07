---
title: Relative VaR
subject: Portfolio Management
tags: [CFA-L2, glossary, portfolio-management, market-risk, active-management]
aliases: [Relative VaR, ex ante tracking error, tracking error VaR, active-return VaR]
---

# Relative VaR

## Definition

**Relative VaR** measures the [[Value at Risk (VaR)|VaR]] of a portfolio's active return relative to its benchmark. It is also referred to as [[Ex ante tracking error|ex ante tracking error]] in the Portfolio Management reading.

Plain English: relative VaR answers, "How badly could this portfolio underperform its benchmark because of the manager's active bets?"

## Calculation Logic

Relative VaR is based on the difference between portfolio return and benchmark return:

$$
R_{\text{active}} = R_P - R_B
$$

Then VaR is calculated on that active-return distribution:

$$
Relative\ VaR = VaR(R_P - R_B)
$$

Equivalently, it can be viewed as the VaR of a combined position that is long the subject portfolio and short the benchmark portfolio.

```text
Long portfolio
  +
Short benchmark
  =
Active exposure
  |
  v
Relative VaR
```

## Interpretation

A 5% monthly relative VaR of 2.5% means that, under the model, there is a 5% probability that the portfolio will underperform the benchmark by at least 2.5% over one month.

This is not the same as saying the portfolio will lose 2.5% in absolute terms. The portfolio could earn a positive return and still underperform the benchmark. Relative VaR is about benchmark-relative loss, not absolute capital loss.

## Why It Exists

Absolute VaR is useful for capital-at-risk questions, but active managers are often hired to beat a benchmark. Their key risk is not only "Can the portfolio lose money?" It is also "Can the manager's active positions fall badly behind the benchmark?"

Relative VaR isolates the risk created by active weights:

$$
\text{Active weight}_i = w_{P,i} - w_{B,i}
$$

If the portfolio matches the benchmark exactly, active weights are zero and relative VaR should be near zero. If the manager makes large sector, duration, currency, credit, or factor bets, relative VaR rises.

## Worked Example

Suppose a portfolio benchmark is the Bloomberg Aggregate Bond Index. The manager overweights credit risk and underweights government bonds.

The portfolio's expected monthly active-return distribution has:

- expected active return: +0.20%;
- 5% left-tail active return: -1.80%.

The 5% monthly relative VaR is 1.80%. The interpretation is:

> In the model's 5% left-tail case, the portfolio underperforms the benchmark by at least 1.80% over the month.

That underperformance could happen even if both the portfolio and benchmark have positive returns. For example:

| Portfolio return | Benchmark return | Active return |
|---:|---:|---:|
| +0.40% | +2.20% | -1.80% |

The portfolio made money, but it still realized the relative VaR threshold because it lagged the benchmark.

## Relative VaR vs Other VaR Measures

| Measure | What it measures | Best use |
|---|---|---|
| Absolute [[Value at Risk (VaR)|VaR]] | Potential portfolio loss in currency or percentage terms | Capital-at-risk and total loss control |
| [[Relative VaR]] | Potential underperformance versus benchmark | Active-manager risk control |
| [[Incremental VaR (IVaR)|Incremental VaR]] | Change in total VaR from a discrete trade | Trade approval |
| [[Marginal VaR (MVaR)|Marginal VaR]] | Approximate VaR change from a tiny position change | Marginal risk ranking |
| [[Conditional VaR (CVaR) and Expected Shortfall|Conditional VaR]] | Expected loss given that VaR is breached | Tail-loss severity |

## Exam Traps

- **Relative VaR is benchmark-relative.** It is not the same as absolute portfolio VaR.
- **Use active weights.** The relevant exposure is portfolio minus benchmark, not the portfolio holdings alone.
- **Positive absolute return can still be bad.** A portfolio can rise and still breach relative VaR if the benchmark rises more.
- **Relative VaR fits active manager monitoring.** If the vignette asks about active bets or benchmark underperformance, choose relative VaR/ex ante tracking error.
- **Do not confuse tracking error wording.** In this reading, ex ante tracking error is presented as relative VaR, while in active management readings tracking error often means the standard deviation of active returns.

## Related Concepts

- [[Value at Risk (VaR)]]
- [[Ex ante tracking error]]
- [[Active Return]]
- [[Active Risk and Tracking Error]]
- [[Information Ratio]]
- [[Incremental VaR (IVaR)]]
- [[Marginal VaR (MVaR)]]
- [[Measuring and Managing Market Risk]]
