---
title: Coefficient Instability in Time-Series Models
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, time-series, forecasting, coefficient-instability]
aliases: [Instability of coefficients, Structural breaks, Regime changes, Out-of-sample forecast failure]
---

# Coefficient Instability in Time-Series Models

## The Real-World Analogy

A time-series model is like a map. If the roads stay in the same place, an old map can still guide you. If the city gets rebuilt, the old map becomes dangerous. Coefficient instability is the statistical version of that problem: the relationship estimated in one period may not hold in another period.

This is why time-series models can look excellent in-sample but fail badly out-of-sample.

## The Big Idea

Coefficient instability means the estimated regression coefficients change materially depending on the sample period used.

For an AR(1):

$$
x_t=b_0+b_1x_{t-1}+\varepsilon_t
$$

the model may estimate one $b_1$ using 1995-2005 data and a very different $b_1$ using 2005-2015 data.

If the true economic relationship changes, one fixed coefficient is trying to summarize multiple regimes. That weakens forecasts and can violate the assumption that the series is stable enough to model.

## In-Sample Versus Out-of-Sample

| Forecast type | Meaning | Why CFA cares |
|---|---|---|
| In-sample | Forecasts for periods used to estimate the model | Can look good because the model is fit to those exact observations |
| Out-of-sample | Forecasts for periods not used to estimate the model | Better test of real forecasting ability |

The future is always out-of-sample. A model that explains the past beautifully but fails on new data is not useful for forecasting.

## Why High In-Sample Fit Can Fail

High in-sample $R^2$ can come from:

| Cause | Why it misleads |
|---|---|
| Overfitting | Model memorizes noise that will not repeat |
| Structural break | Old relationship no longer applies |
| Regime change | Policy, market structure, or volatility environment shifts |
| Nonstationarity | Mean, variance, or covariances change over time |

Examples:

- Exchange rates behave differently after a country moves from a fixed to a floating regime.
- Inflation volatility changes after a central bank adopts a credible inflation-targeting policy.
- Credit spreads behave differently during a financial crisis than during a calm expansion.

## More Data Is Not Always Better

Large samples are usually helpful, but time-series data have a special problem: older data may come from a different regime.

```text
Long sample
  |
  +-- more observations
  |
  +-- higher chance of crossing a structural break
```

If the old regime is no longer relevant, a shorter but more stable sample can forecast better than a longer sample.

## Forecast Accuracy And RMSE

Use [[Root Mean Squared Error (RMSE)]] to compare out-of-sample forecast accuracy:

$$
RMSE=
\sqrt{
\frac{\sum_{t=1}^{n}(y_t-\hat{y}_t)^2}{n}
}
$$

The model with the lower out-of-sample RMSE has smaller typical forecast errors over the test period.

Do not select a forecasting model based only on in-sample $R^2$.

## Worked Numerical Example

Suppose actual quarterly sales growth over a three-quarter out-of-sample test period is:

| Quarter | Actual |
|---|---:|
| Q1 | 2.0% |
| Q2 | 4.0% |
| Q3 | -1.0% |

Two models produce forecasts:

| Quarter | Model A forecast | Model B forecast |
|---|---:|---:|
| Q1 | 1.5% | 2.5% |
| Q2 | 5.0% | 4.5% |
| Q3 | 1.0% | -0.5% |

Model A squared errors:

$$
(2.0-1.5)^2=0.25
$$

$$
(4.0-5.0)^2=1.00
$$

$$
(-1.0-1.0)^2=4.00
$$

$$
SSE_A=5.25
$$

$$
RMSE_A=\sqrt{5.25/3}=\sqrt{1.75}=1.32\%
$$

Model B squared errors:

$$
(2.0-2.5)^2=0.25
$$

$$
(4.0-4.5)^2=0.25
$$

$$
(-1.0-(-0.5))^2=0.25
$$

$$
SSE_B=0.75
$$

$$
RMSE_B=\sqrt{0.75/3}=\sqrt{0.25}=0.50\%
$$

Model B has better out-of-sample forecasting accuracy, even if Model A had a higher in-sample $R^2$.

## How To Think On Exam Day

If a vignette says the coefficients are unstable, the model is unreliable for forecasting. If it says a structural break occurred, be skeptical of models estimated across the break. If it gives both in-sample fit and out-of-sample RMSE, prefer the model with lower out-of-sample RMSE for forecasting.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| More data is always better | Uses long sample across regime change | Prefer stable, relevant data |
| Highest in-sample $R^2$ wins | Chooses model that explains past best | Forecasting uses out-of-sample performance |
| Ignoring coefficient stability | Treats coefficients as timeless | Check whether estimates change across subperiods |
| Confusing RMSE with fit | Uses in-sample RMSE only | Out-of-sample RMSE is the forecasting test |
| Treating structural breaks as noise | Averages across fundamentally different regimes | Consider separate models or shorter samples |

## Memory Hooks

**Forecasting is judged out-of-sample.**

**A high $R^2$ can be a memorized past, not a useful future.**

**Stable coefficients are part of model validity, not a nice-to-have.**

## Related Concepts

- [[Root Mean Squared Error (RMSE)]]
- [[AR(1) Model]]
- [[Random Walks and Covariance Stationarity]]
- [[Dickey-Fuller Test]]
- [[Spurious Correlation]]
- [[Overfitting]]
- [[Model Misspecification]]
