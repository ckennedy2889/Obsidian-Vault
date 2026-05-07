---
title: Linear and Log-Linear Trend Models
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, time-series, trend-models, forecasting]
aliases: [Linear trend model, Log-linear trend model, Trend analysis, Exponential trend model]
---

# Linear and Log-Linear Trend Models

## The Real-World Analogy

A trend model is the simplest forecasting story: "this series has been moving in a regular direction, so project that direction forward." If a factory's capacity utilization has been rising by roughly 0.3 percentage points per quarter, a linear trend may fit. If sales have been growing by roughly 3% per quarter, a log-linear trend may fit.

The distinction is critical: linear trend means constant **amount** of change; log-linear trend means constant **rate** of change.

## The Big Idea

| Model | Best for | Forecast pattern |
|---|---|---|
| Linear trend | Constant absolute change | Adds the same amount each period |
| Log-linear trend | Constant percentage growth | Multiplies by the same growth rate each period |

Both models use time $t$ as the independent variable.

## Linear Trend Model

The linear trend model is:

$$
y_t=b_0+b_1t+\varepsilon_t
$$

The prediction equation is:

$$
\hat{y}_t=\hat{b}_0+\hat{b}_1t
$$

The slope $\hat{b}_1$ is the expected change in $y$ per period.

If:

$$
\hat{y}_t=2.7845-0.0037t
$$

then each additional period reduces the forecast by 0.0037 units.

## Log-Linear Trend Model

The log-linear trend model is:

$$
\ln(y_t)=b_0+b_1t+\varepsilon_t
$$

The prediction equation gives the predicted log value:

$$
\ln(\hat{y}_t)=\hat{b}_0+\hat{b}_1t
$$

To convert back to the original units:

$$
\hat{y}_t=e^{\hat{b}_0+\hat{b}_1t}
$$

The slope $b_1$ is the continuously compounded growth rate. The discrete periodic growth rate is:

$$
e^{b_1}-1
$$

## When To Use Each

Use a linear trend when the graph looks like a straight line in the original units:

```text
y
|        /
|      /
|    /
|  /
+------------ t
```

Use a log-linear trend when the graph curves upward in original units but becomes roughly straight after taking logs:

```text
y
|          __/
|       __/
|    __/
| __/
+------------ t
```

Financial and economic series often grow at rates rather than fixed dollar amounts, so log-linear models are common. But the model choice must be supported by the data and diagnostics, not by habit.

## Worked Example: Linear Trend Forecast

Suppose an inflation series is estimated as:

$$
\widehat{Inflation}_t=2.7845-0.0037t
$$

Forecast inflation for $t=306$:

$$
\hat{y}_{306}
=
2.7845-0.0037(306)
$$

$$
\hat{y}_{306}
=
2.7845-1.1322
=
1.6523
$$

The forecast is 1.6523%.

## Worked Example: Log-Linear Forecast

Suppose quarterly sales are modeled as:

$$
\ln(Sales_t)=6.7617+0.0295t
$$

Forecast sales for $t=75$.

First calculate the predicted log value:

$$
\ln(\widehat{Sales}_{75})
=
6.7617+0.0295(75)
$$

$$
\ln(\widehat{Sales}_{75})
=
6.7617+2.2125
=
8.9742
$$

Now exponentiate:

$$
\widehat{Sales}_{75}
=
e^{8.9742}
=
7{,}896.69
$$

If sales are measured in millions, the forecast is $7,896.69 million.

The periodic growth rate implied by $b_1=0.0295$ is:

$$
e^{0.0295}-1=0.02994=2.994\%
$$

## Limitations Of Trend Models

Trend models are simple, but financial and economic time series often change regime. A trend model can produce impressive-looking output while still being misspecified.

Watch for:

| Diagnostic issue | Meaning |
|---|---|
| Serially correlated residuals | Trend model has not captured the true time-series structure |
| Low Durbin-Watson statistic | Positive serial correlation may make trend model invalid |
| Structural break | Past trend may not apply after policy, crisis, or business-model change |
| Seasonality | A repeating calendar pattern may require seasonal lags |

If residuals are serially correlated, consider an [[AR(1) Model]] or another autoregressive specification.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Forgetting to exponentiate log-linear forecast | Reports $\ln(\hat{y})$ instead of $\hat{y}$ | Use $\hat{y}=e^{\hat{b}_0+\hat{b}_1t}$ |
| Interpreting log-linear slope as exact simple growth | Says $b_1=3\%$ means exactly 3% simple growth | Discrete growth is $e^{b_1}-1$ |
| Comparing $R^2$ across linear and log-linear models | Dependent variables differ | Use diagnostics and out-of-sample fit; do not rely on raw $R^2$ |
| Ignoring Durbin-Watson | Uses a trend model with serially correlated errors | Check residual diagnostics |
| Extrapolating blindly | Projects old trend through regime change | Consider structural breaks and model stability |

## Memory Hooks

**Linear trend adds. Log-linear trend compounds.**

**Log forecast is not the final forecast; exponentiate.**

**High $R^2$ does not rescue serially correlated residuals.**

## Related Concepts

- [[AR(1) Model]]
- [[Seasonality in Time-Series Models]]
- [[Serial Correlation]]
- [[Durbin-Watson Test]]
- [[Root Mean Squared Error (RMSE)]]
- [[Covariance stationary]]
- [[Time-Series Analysis]]
