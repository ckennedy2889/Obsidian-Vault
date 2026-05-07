---
title: Seasonality in Time-Series Models
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, time-series, seasonality, autoregressive-models]
aliases: [Seasonal lag, Seasonal autocorrelation, AR model with seasonal lag, Time-series seasonality]
---

# Seasonality in Time-Series Models

## The Real-World Analogy

Seasonality is the calendar leaving fingerprints on the data. A resort hotel may be full every summer. Retail sales may jump every December. Utility demand may spike every winter. If you model that series using only last period's value, the model will keep being surprised by patterns that repeat every year.

The fix is to tell the model: "This quarter may depend not only on last quarter, but also on the same quarter last year."

## The Big Idea

[[Seasonality]] is a recurring within-year pattern. If a time series is seasonal and the model omits the seasonal structure, the model is misspecified.

| Data frequency | Seasonal lag |
|---|---:|
| Quarterly | $t-4$ |
| Monthly | $t-12$ |
| Weekly | Often $t-52$ |

For quarterly data, fourth quarter 2026 may be related to third quarter 2026 and fourth quarter 2025. That is why the seasonal lag is 4.

## Detecting Seasonality

CFA typically has you estimate an initial AR model and inspect the autocorrelations of the residuals.

If the residual autocorrelation at the seasonal lag is significantly different from zero, the model has failed to capture seasonality.

For quarterly data:

$$
H_0: \rho_4 = 0
$$

If:

$$
|t_{\rho_4}| > t_{critical}
$$

reject the null and conclude that seasonality is present.

For monthly data, test lag 12.

## Correcting Seasonality

Suppose the original model is an AR(1):

$$
x_t=b_0+b_1x_{t-1}+\varepsilon_t
$$

If quarterly seasonality is present, add the fourth lag:

$$
x_t=b_0+b_1x_{t-1}+b_2x_{t-4}+\varepsilon_t
$$

This is not an AR(2) model. It is an AR(1) model with a seasonal lag. The model includes one ordinary lag and one seasonal lag.

## Why The Seasonal Lag Works

Without the seasonal lag, the residuals still contain predictable calendar structure:

```text
Actual series = AR pattern + seasonal pattern + noise
Model captures = AR pattern
Residuals contain = seasonal pattern + noise
```

Adding the seasonal lag moves the repeating calendar pattern from the residuals into the model:

```text
Actual series = AR pattern + seasonal pattern + noise
Model captures = AR pattern + seasonal pattern
Residuals contain = noise
```

That is why the goal is not merely a higher $R^2$. The goal is a correctly specified model with residuals that no longer show significant seasonal autocorrelation.

## Worked Numerical Example

Suppose a monthly retail-sales model shows a significant 12th residual autocorrelation. The corrected model is:

$$
SalesGrowth_t
=
b_0+b_1SalesGrowth_{t-1}+b_2SalesGrowth_{t-12}+\varepsilon_t
$$

Estimated coefficients:

| Coefficient | Value |
|---|---:|
| $b_0$ | 0.2371 |
| $b_1$ | -0.0792 |
| $b_2$ | 0.7798 |

Last month's sales growth was 10%, and sales growth 12 months ago was 5%.

The forecast is:

$$
\hat{x}_t =
0.2371-0.0792(0.10)+0.7798(0.05)
$$

$$
\hat{x}_t =
0.2371-0.00792+0.03899
$$

$$
\hat{x}_t =
0.26817
=
26.82\%
$$

The seasonal lag has a strong positive coefficient, so the model heavily weights what happened in the same month last year.

## Quarterly Example: Detecting The Problem

Suppose a quarterly hotel-occupancy AR(1) model provides residual autocorrelation t-statistics:

| Lag | t-statistic |
|---:|---:|
| 1 | 0.80 |
| 2 | -1.10 |
| 3 | 1.25 |
| 4 | 5.45 |

If the 5% critical t-value is 2.03, lag 4 is significant:

$$
|5.45|>2.03
$$

The model is misspecified because it omitted quarterly seasonality. Add $x_{t-4}$.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Looking only at coefficient significance | Misses seasonal residual autocorrelation | Always inspect residual autocorrelations |
| Using lag 4 for monthly data | Mismatches data frequency | Quarterly = 4, monthly = 12 |
| Calling the corrected model AR(2) | Treats $x_{t-4}$ as the second ordinary lag | It is AR(1) with a seasonal lag |
| Adding seasonal lag only to raise $R^2$ | Misunderstands the diagnostic | Add it to fix misspecification and residual autocorrelation |
| Forecasting with wrong historical value | Uses $x_{t-2}$ instead of $x_{t-4}$ or $x_{t-12}$ | Map the lag to the same period last year |

## Memory Hooks

**Seasonality means same period last year matters.**

**Quarterly seasonality = lag 4. Monthly seasonality = lag 12.**

**Seasonal lag fixes residual autocorrelation, not just low $R^2$.**

## Related Concepts

- [[AR(1) Model]]
- [[Serial Correlation]]
- [[Covariance stationary]]
- [[Dickey-Fuller Test]]
- [[ARCH Models]]
- [[Root Mean Squared Error (RMSE)]]
- [[Time-Series Analysis]]
