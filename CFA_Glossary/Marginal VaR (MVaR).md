---
title: Marginal VaR (MVaR)
subject: Portfolio Management
tags: [CFA-L2, glossary, portfolio-management, market-risk, VaR]
aliases: [Marginal VaR, MVaR, Marginal Value at Risk]
---

# Marginal VaR (MVaR)

## Definition

**Marginal VaR (MVaR)** measures the approximate effect on total [[Value at Risk (VaR)|portfolio VaR]] from a very small change in a position's size or portfolio weight.

Plain English: MVaR answers, "If I nudge this position slightly larger, how much does total portfolio VaR change?"

## CFA Interpretation

MVaR is estimated as the slope of the curve that plots portfolio VaR against the weight of a security in the portfolio.

$$
MVaR_i \approx \frac{\partial VaR_P}{\partial w_i}
$$

Because it is a slope at the current portfolio weight, MVaR is a local sensitivity measure. It is often interpreted as the approximate change in VaR for a 1% increase in the security's portfolio weight, but that is only an approximation because the true measure is a point-slope, not a wide before-and-after difference.

## Why It Exists

Portfolio VaR is not additive across securities because correlations and diversification matter. A risky asset can add little VaR if it diversifies the portfolio, while a lower-volatility asset can add more VaR if it is highly correlated with the existing book.

MVaR gives the manager a risk-sensitivity ranking:

```text
Small increase in position weight
  |
  v
Change in total portfolio VaR
  |
  v
Estimate which position adds the most risk at the margin
```

## MVaR vs IVaR vs Component VaR

| Measure | Question answered | Change size | Exam use |
|---|---|---|---|
| [[Marginal VaR (MVaR)|Marginal VaR]] | How much does VaR change if I slightly increase this position? | Tiny/local change | Optimization and marginal risk ranking |
| [[Incremental VaR (IVaR)|Incremental VaR]] | How much does VaR change after this specific trade? | Discrete before-and-after trade | Trade approval and risk-budget checks |
| [[Component VaR]] | How much of current portfolio VaR is attributable to this position? | Current risk contribution | Risk attribution; components sum to total VaR |

The common relationship is:

$$
\text{Component VaR}_i \approx MVaR_i \times \text{position size}_i
$$

Component VaRs can be summed to explain total portfolio VaR. [[Incremental VaR (IVaR)|Incremental VaRs]] generally should not be summed because each IVaR is a separate before-and-after trade calculation.

## Worked Example

Suppose a portfolio's current one-month VaR is $\$1{,}000{,}000$. A risk model estimates that increasing Asset A's weight by 1 percentage point would increase total VaR by about $\$18{,}000$.

Asset A's MVaR is approximately:

$$
MVaR_A \approx \$18{,}000 \text{ per 1 percentage point of portfolio weight}
$$

If the manager is considering only a tiny rebalance, MVaR is useful. If the manager is considering a large $\$10$ million purchase, use [[Incremental VaR (IVaR)|Incremental VaR]] instead, because the portfolio's correlations and nonlinear risk profile may change over a larger move.

## Exam Traps

- **MVaR is marginal, not discrete.** Use it for a small position change, not a major allocation shift.
- **MVaR is a slope.** It is not exactly the same as the VaR change from a full 1% move unless the VaR curve is locally linear.
- **MVaR is not standalone VaR.** It measures contribution to portfolio risk after diversification, not the position's risk in isolation.
- **Do not confuse Component VaR with Conditional VaR.** In CFA usage, [[Conditional VaR (CVaR) and Expected Shortfall|CVaR]] means expected shortfall, not component VaR.

## Related Concepts

- [[Value at Risk (VaR)]]
- [[Incremental VaR (IVaR)]]
- [[Component VaR]]
- [[Relative VaR]]
- [[Measuring and Managing Market Risk]]
