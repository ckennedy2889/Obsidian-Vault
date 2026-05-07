---
title: Random Walks and Covariance Stationarity
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, time-series, random-walks, stationarity]
aliases: [Random walk, Random walk with drift, Covariance stationary time series, Mean reversion, Unit root process]
---

# Random Walks and Covariance Stationarity

## The Real-World Analogy

A covariance-stationary series is like a dog on a leash. It may wander, but it keeps getting pulled back toward a stable long-run level. A [[Random walk]] is like cutting the leash. Every shock permanently changes where the series starts from next period, so the path can drift farther and farther away without a stable anchor.

That difference matters because AR models assume the leash exists. If the series is a random walk, the usual regression statistics can look impressive while the model is actually unreliable.

## Covariance Stationarity

A time series is [[Covariance stationary]] if it has:

| Requirement | Meaning |
|---|---|
| Constant finite mean | The long-run average does not drift over time |
| Constant finite variance | The dispersion does not explode or change over time |
| Constant finite autocovariances | The covariance between $x_t$ and $x_{t-k}$ depends only on lag $k$, not calendar time |

Covariance-stationary series exhibit [[Mean reversion]]. When the series is above its long-run level, it tends to move down. When it is below the long-run level, it tends to move up.

For an AR(1):

$$
x_t=b_0+b_1x_{t-1}+\varepsilon_t
$$

the mean-reverting level is:

$$
\frac{b_0}{1-b_1}
$$

This is finite only if $b_1 \ne 1$.

## Random Walk Without Drift

A simple random walk is:

$$
x_t=x_{t-1}+\varepsilon_t
$$

This is an AR(1) with:

$$
b_0=0
$$

$$
b_1=1
$$

The best forecast of next period's value is today's value because the expected shock is zero:

$$
E(x_{t+1})=x_t
$$

The level is unpredictable in direction, but today's level persists.

## Random Walk With Drift

A random walk with drift is:

$$
x_t=b_0+x_{t-1}+\varepsilon_t
$$

The drift term $b_0$ creates an expected increase or decrease each period. For example, if $b_0=0.5$, the expected level rises by 0.5 per period, plus a random shock.

The series still has a unit root because:

$$
b_1=1
$$

So it is still not covariance stationary.

## Why Random Walks Are Nonstationary

There are two core reasons.

First, the mean-reverting level is undefined:

$$
\frac{b_0}{1-b_1}
=
\frac{b_0}{1-1}
=
\frac{b_0}{0}
$$

Second, the variance grows over time. A random walk accumulates shocks:

$$
x_t=x_0+\varepsilon_1+\varepsilon_2+\cdots+\varepsilon_t
$$

If each shock has variance $\sigma^2$, then:

$$
Var(x_t)=t\sigma^2
$$

The variance depends on time and increases without bound. That violates covariance stationarity.

## Unit Roots

A [[Unit root]] occurs when the AR(1) lag coefficient equals 1:

$$
b_1=1
$$

All random walks have unit roots. A unit root means shocks are permanent. If a random shock raises the series today, that higher level becomes tomorrow's starting point.

## Forecast Implications

Random walks can produce high $R^2$ values in regressions of $x_t$ on $x_{t-1}$ because today's level is highly related to yesterday's level. That does not mean the model predicts changes well.

| Series type | Forecast implication |
|---|---|
| Covariance-stationary | Long-horizon forecasts move toward mean-reverting level |
| Random walk | Best forecast of future level is current level, plus drift if present |
| First-differenced random walk | Changes may be stationary even if levels are not |

## First Differencing

If:

$$
x_t=x_{t-1}+\varepsilon_t
$$

then first differencing gives:

$$
\Delta x_t=x_t-x_{t-1}=\varepsilon_t
$$

The differenced series can be covariance stationary even though the level series is not.

This is why CFA's workflow is:

```text
Suspect nonstationarity
  |
  v
Test for unit root using Dickey-Fuller
  |
  v
If unit root exists, first-difference
  |
  v
Model the transformed stationary series
```

## Worked Numerical Example

Suppose an exchange-rate series follows:

$$
x_t=0.8409+0.9919x_{t-1}+\varepsilon_t
$$

The coefficient 0.9919 is close to 1. You should not simply use an ordinary t-test to decide whether it differs from 1 because the usual distribution does not apply under a unit root.

Instead, use the [[Dickey-Fuller Test]]:

$$
\Delta x_t=b_0+g x_{t-1}+\varepsilon_t
$$

where:

$$
g=b_1-1
$$

The null is:

$$
H_0:g=0
$$

which means the series has a unit root.

If the Dickey-Fuller test fails to reject, first-difference the series:

$$
y_t=x_t-x_{t-1}
$$

Then estimate an AR model on $y_t$. If the differenced model has insignificant lag coefficients and very low $R^2$, the interpretation is not that the model is broken. The interpretation is that exchange-rate changes are difficult to forecast from their own history.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating high $R^2$ as forecast power | A random walk level regression can look excellent | Ask whether changes are predictable |
| Using a standard t-test for $b_1=1$ | Applies wrong distribution under nonstationarity | Use Dickey-Fuller critical values |
| Thinking drift makes a series stationary | Drift creates trend but does not fix $b_1=1$ | Random walk with drift still has unit root |
| Forgetting variance growth | Focuses only on mean | Random walk variance grows with time |
| Modeling levels after finding a unit root | Produces spurious inference | First-difference before AR modeling unless cointegration applies |

## Memory Hooks

**Random walk = today's value plus shock.**

**Unit root means shocks are permanent.**

**Stationary series has a leash; random walk has no leash.**

## Related Concepts

- [[Unit root]]
- [[Dickey-Fuller Test]]
- [[Cointegration]]
- [[Spurious Correlation]]
- [[AR(1) Model]]
- [[Mean reversion]]
- [[Covariance stationary]]
- [[First-differencing]]
