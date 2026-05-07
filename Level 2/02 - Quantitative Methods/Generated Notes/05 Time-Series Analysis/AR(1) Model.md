---
title: AR(1) Model
subject: 02 - Quantitative Methods
tags: [CFA-L2, time-series, AR-models, autoregressive, forecasting, stationarity]
aliases: [AR(1), first-order autoregressive model, autoregressive model of order 1]
---

# AR(1) Model

## The Real-World Analogy

Think about predicting tomorrow's temperature in the city you live in. You don't need a weather satellite — your single best, cheap estimate is *today's temperature, slightly pulled toward the seasonal average*. If today is unusually hot, tomorrow will probably also be hot, but a little cooler. If today is unusually cold, tomorrow will probably also be cold, but a little warmer.

That's the entire intuition of an AR(1) model: **the past doesn't fully determine the present, but it leaves a fingerprint that fades.** Today's value is partly explained by yesterday's value (the fingerprint), partly by a long-run anchor (the seasonal average), and partly by today's random surprise (a cold front rolls in). The "1" in AR(1) means we look back exactly *one* period — yesterday — to make our forecast.

This is the workhorse forecasting model of CFA Level 2 time-series analysis. It's the bridge between simple linear regression (which you've seen) and the world of dynamic models (which you'll meet shortly).

---

## The Formal Equation

The first-order autoregressive model is:

$$x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$$

| Term | Meaning |
|------|---------|
| $x_t$ | The value of the series **today** (or at time $t$) — the dependent variable |
| $x_{t-1}$ | The value **one period ago** — the lagged dependent variable serving as our single regressor |
| $b_0$ | Intercept — the constant "drift" each period |
| $b_1$ | Slope on the lagged value — the **autoregressive coefficient**; how strongly the past pulls on the present |
| $\varepsilon_t$ | Error term — the random shock at time $t$, capturing everything the model can't explain |

The structure is just an OLS regression with one twist: **the regressor is the dependent variable shifted back by one period**. That's all "autoregressive" means — *self-regression*.

### What $b_1$ tells you, geometrically

| $b_1$ value | Behavior |
|-------------|----------|
| $b_1 = 0$ | No memory — series is just $b_0 + \varepsilon_t$, white noise around a constant |
| $0 < b_1 < 1$ | Positive memory, mean-reverting — high values tend to be followed by slightly lower values |
| $b_1 < 0$ | Negative memory, oscillating — high values tend to be followed by lower values |
| $\lvert b_1 \rvert = 1$ | **Unit root** — non-stationary, shocks are permanent |
| $\lvert b_1 \rvert > 1$ | Explosive — shocks amplify; economically implausible |

The CFA Level 2 sweet spot is $0 < b_1 < 1$ — a series with fading memory that mean-reverts to a long-run average.

---

## Assumptions for OLS to Work

You can't just slap OLS on any time series and trust the output. The AR(1) requires:

### 1. Covariance stationarity of $\{x_t\}$

The series itself must have a constant mean, constant finite variance, and lag-only covariances. See [[Covariance stationary]]. If it's non-stationary (a [[Unit root]] is the prime offender), the OLS estimates are biased and inferences are spurious. **Why?** Because the standard error formulas assume the regressor's variance is finite and stable — a property that breaks down for non-stationary $x_{t-1}$.

### 2. Error term properties

The shocks $\varepsilon_t$ must satisfy:

- $E[\varepsilon_t] = 0$ — mean zero (otherwise the intercept absorbs the bias)
- $\text{Var}(\varepsilon_t) = \sigma_\varepsilon^2$ — constant variance (homoscedasticity)
- $\text{Cov}(\varepsilon_t, \varepsilon_s) = 0$ for $t \neq s$ — **no serial correlation in the residuals**

The third point is the one you must verify after fitting an AR(1). If residuals are still correlated, the model has missed structure — see "Testing for serial correlation" below.

### 3. No correlation between regressor and current error

Specifically, $\text{Cov}(x_{t-1}, \varepsilon_t) = 0$. This is automatic if errors are well-behaved, because $x_{t-1}$ is fully determined by shocks up to time $t-1$, and $\varepsilon_t$ is the *new* shock at time $t$.

---

## Estimating $b_0$ and $b_1$ in Practice

In practice, you hand the data to software (Excel, Python, R, Stata) and it runs OLS minimizing the sum of squared residuals. The mechanics are identical to a standard regression — set up two columns:

| $t$ | $x_t$ (dependent) | $x_{t-1}$ (regressor) |
|-----|-------------------|------------------------|
| 2 | $x_2$ | $x_1$ |
| 3 | $x_3$ | $x_2$ |
| ⋮ | ⋮ | ⋮ |
| $T$ | $x_T$ | $x_{T-1}$ |

You lose one observation (the very first one has no lag). With $T$ raw data points, you fit on $T-1$ pairs.

The OLS formulas reduce to the same ones you know:

$$\hat{b}_1 = \frac{\sum_{t=2}^{T} (x_{t-1} - \bar{x}_{-1})(x_t - \bar{x})}{\sum_{t=2}^{T} (x_{t-1} - \bar{x}_{-1})^2}, \qquad \hat{b}_0 = \bar{x} - \hat{b}_1 \bar{x}_{-1}$$

where $\bar{x}$ is the mean of $x_2, \dots, x_T$ and $\bar{x}_{-1}$ is the mean of $x_1, \dots, x_{T-1}$.

Provided stationarity holds, $\hat{b}_0$ and $\hat{b}_1$ are *consistent* — they converge to the true values as the sample size grows. (They are not unbiased in finite samples, but the bias vanishes asymptotically.)

---

## The Mean-Reverting Level — The Anchor

The most important interpretive result for AR(1). At the long-run mean $\mu$, the series has settled — by definition, if there are no shocks, the value next period equals the value this period:

$$\mu = b_0 + b_1 \mu$$

Solving for $\mu$:

$$\boxed{\mu = \frac{b_0}{1 - b_1}}$$

### What this means economically

- The series **gravitates toward $\mu$**. Above it, $b_1 < 1$ pulls down. Below it, $b_0$ pushes up. Together they create equilibrium at $\mu$.
- The model is **mean-reverting** if and only if $\lvert b_1 \rvert < 1$. That's the mathematical statement of "memory fades."
- When $b_1 = 1$, the formula $b_0 / 0$ is undefined — and in fact there *is* no mean-reverting level. That series is a [[random walk]] (a unit-root process). It can wander anywhere; it has no anchor.

### The forecast interpretation

Decomposing the AR(1) around the mean: $x_t - \mu = b_1(x_{t-1} - \mu) + \varepsilon_t$. So the *deviation from the mean* shrinks by a factor of $b_1$ each period. After $k$ periods, the expected deviation is $b_1^k \cdot (x_t - \mu)$ — geometrically decaying when $\lvert b_1 \rvert < 1$.

---

## Forecasting: One Step and Beyond

### One-step-ahead forecast

Plug the most recent observation into the fitted equation:

$$\hat{x}_{t+1} = \hat{b}_0 + \hat{b}_1 x_t$$

The expected value of $\varepsilon_{t+1}$ is zero, so it drops out.

### Multi-step forecasts — the chain rule of forecasting

You don't have $x_{t+1}$ yet (you just forecast it). For two steps ahead, plug your *forecast* back in:

$$\hat{x}_{t+2} = \hat{b}_0 + \hat{b}_1 \hat{x}_{t+1}$$

For three steps:

$$\hat{x}_{t+3} = \hat{b}_0 + \hat{b}_1 \hat{x}_{t+2}$$

…and so on. Each forecast uses the previous forecast as its "lag." This is called the **chain rule of forecasting** — each link depends on the previous link.

### What the chain rule reveals

Substituting recursively:

$$\hat{x}_{t+k} = \mu + b_1^k (x_t - \mu)$$

As $k \to \infty$, $b_1^k \to 0$ (when $\lvert b_1 \rvert < 1$), so $\hat{x}_{t+k} \to \mu$. **All long-horizon forecasts converge to the mean-reverting level.** That's the deep reason why a stationary AR(1) is only useful for short-horizon forecasts — beyond a certain point, you're just predicting the mean.

### Forecast uncertainty

Standard errors of forecasts grow with horizon, but for a stationary AR(1) they grow toward a *finite* asymptotic variance (the unconditional variance of the series). For a unit-root process, they grow without bound — see [[Unit root]].

---

## Testing for Serial Correlation in Residuals

This is the diagnostic that separates a believable AR(1) fit from a misspecified one.

### Why Durbin-Watson is wrong here

In a standard regression, [[Durbin-Watson Test]] flags first-order serial correlation in residuals. **It is invalid for an AR model.** The reason: DW assumes the regressors are not the lagged dependent variable. In an AR(1), the regressor *is* a lagged version of $y$ — the very assumption DW relies on is violated. Using DW on an AR(1) gives biased (toward 2) results that fail to detect real serial correlation.

### The correct test: t-tests on residual autocorrelations

Compute the residuals $\hat{\varepsilon}_t$ from the fitted model. For each lag $k$ you care about, compute the residual autocorrelation:

$$\hat{\rho}_k = \frac{\sum_{t=k+1}^{T} \hat{\varepsilon}_t \hat{\varepsilon}_{t-k}}{\sum_{t=1}^{T} \hat{\varepsilon}_t^2}$$

Under the null that the residuals are truly white noise, the standard error of $\hat{\rho}_k$ is approximately $1/\sqrt{T}$. So the test statistic is:

$$t_k = \frac{\hat{\rho}_k}{1/\sqrt{T}} = \hat{\rho}_k \sqrt{T}$$

Compare to standard t critical values (≈ ±2 for 5% significance). If *any* lag's autocorrelation is statistically significant, reject the null — the model has missed structure.

### What it means if you reject

The AR(1) is **misspecified**. The residuals contain pattern that an AR(1) cannot capture. Two interpretations:

1. The series needs more lags — go to AR(2), AR(3), …, AR(p).
2. The series needs a different structure (seasonal terms, moving-average terms — out of CFA scope).

For CFA Level 2, the answer is almost always "add more lags."

---

## When AR(1) Isn't Enough: AR(p)

The natural generalization:

$$x_t = b_0 + b_1 x_{t-1} + b_2 x_{t-2} + \cdots + b_p x_{t-p} + \varepsilon_t$$

This is an **AR(p) model**. You include $p$ lags as separate regressors. Procedure:

1. Start with AR(1). Fit it. Test residual autocorrelations at lag 1, 2, 3, … (typically through 4 or so for monthly data, more for daily).
2. If lag 1 residual autocorrelation is significant, fit AR(2). Re-test residuals.
3. Repeat until no residual autocorrelation is statistically significant. The model is now well-specified.

### Choosing $p$: AIC and BIC

You don't want to over-fit by piling on lags forever. The principle is **parsimony** — explain the data with as few parameters as possible. Two information criteria balance fit against complexity:

- [[AIC and BIC|AIC]] (Akaike) — penalizes complexity less; tends to pick larger models
- [[AIC and BIC|BIC]] (Schwarz / Bayesian) — penalizes complexity more; tends to pick smaller, more parsimonious models

**Rule:** lower is better. Compare AIC (or BIC) across candidate AR(p) specifications and pick the minimum.

For forecasting, BIC is often preferred because over-parameterized models forecast badly out-of-sample.

### How AR(p) coefficients differ from AR(1)

In an AR(2), the lag-1 coefficient $b_1$ generally **differs** from the $b_1$ you'd get in an AR(1) on the same data. That's because the AR(2) controls for the additional information in $x_{t-2}$. The mean-reverting level formula also generalizes:

$$\mu = \frac{b_0}{1 - b_1 - b_2 - \cdots - b_p}$$

---

## The Connection to Non-Stationarity

If you've followed this note in order, you've seen the bridge: **the AR(1) coefficient $b_1$ is the diagnostic for stationarity itself.**

- $\lvert b_1 \rvert < 1$ → stationary, mean-reverts to $b_0/(1-b_1)$, AR(1) is valid.
- $b_1 = 1$ → unit root, random walk, AR(1) estimates are unreliable. Difference the data first.
- $b_1 > 1$ → explosive, doesn't happen in real economic series.

The Dickey-Fuller test (covered in [[Unit root]]) is precisely a formal test of $b_1 = 1$ vs. $b_1 < 1$ — i.e., a test of whether AR(1) is a legitimate framework for the data, or whether you need to first-difference and model the changes instead.

This is why you cannot study AR(1) without also studying [[Covariance stationary|covariance stationarity]] and [[Unit root|unit roots]]. They are three angles on the same object.

---

## Worked Numerical Example

A portfolio manager models a company's monthly inventory levels (in millions of dollars). Six monthly observations:

| Month $t$ | Inventory $x_t$ |
|:-:|:-:|
| 1 | 10 |
| 2 | 12 |
| 3 | 11 |
| 4 | 13 |
| 5 | 12 |
| 6 | 14 |

### Step 1 — Build the lag pairs

Set up the regression dataset by aligning each observation with its lag:

| $t$ | $x_t$ (dep.) | $x_{t-1}$ (regressor) |
|:-:|:-:|:-:|
| 2 | 12 | 10 |
| 3 | 11 | 12 |
| 4 | 13 | 11 |
| 5 | 12 | 13 |
| 6 | 14 | 12 |

Five pairs from six raw observations.

### Step 2 — Compute means

$$\bar{x} = \frac{12+11+13+12+14}{5} = \frac{62}{5} = 12.4$$
$$\bar{x}_{-1} = \frac{10+12+11+13+12}{5} = \frac{58}{5} = 11.6$$

### Step 3 — Compute slope $\hat{b}_1$ via OLS

Numerator $= \sum (x_{t-1} - \bar{x}_{-1})(x_t - \bar{x})$:

| $x_{t-1} - 11.6$ | $x_t - 12.4$ | Product |
|:-:|:-:|:-:|
| −1.6 | −0.4 | 0.64 |
| 0.4 | −1.4 | −0.56 |
| −0.6 | 0.6 | −0.36 |
| 1.4 | −0.4 | −0.56 |
| 0.4 | 1.6 | 0.64 |
| **Sum** | | **−0.20** |

Denominator $= \sum (x_{t-1} - \bar{x}_{-1})^2$:

| $x_{t-1} - 11.6$ | Squared |
|:-:|:-:|
| −1.6 | 2.56 |
| 0.4 | 0.16 |
| −0.6 | 0.36 |
| 1.4 | 1.96 |
| 0.4 | 0.16 |
| **Sum** | **5.20** |

$$\hat{b}_1 = \frac{-0.20}{5.20} = -0.0385$$

In a typical CFA textbook problem you'd be *given* the regression output. To match the textbook example here, suppose the analyst's full sample (much larger than 6 months) yielded $\hat{b}_0 = 4.0$ and $\hat{b}_1 = 0.60$:

$$\hat{x}_t = 4.0 + 0.60 \, x_{t-1}$$

(I'll use these textbook values for the rest of the example, since they illustrate mean-reversion cleanly.)

### Step 4 — Mean-reverting level

$$\mu = \frac{4.0}{1 - 0.60} = \frac{4.0}{0.40} = 10.0$$

The model says inventory will gravitate to $10$ million over time. The latest observation, $14$, sits *above* this anchor, so we expect future values to drift down toward 10.

### Step 5 — One-step-ahead forecast (Month 7)

Use the most recent actual value, $x_6 = 14$:

$$\hat{x}_7 = 4.0 + 0.60 \cdot 14 = 4.0 + 8.4 = 12.4$$

Inventory is forecast to drop from 14 to 12.4 next month — exactly the mean-reverting pull at work.

### Step 6 — Two-step-ahead forecast (Month 8) via the chain rule

Use the *forecast* $\hat{x}_7 = 12.4$ as the input:

$$\hat{x}_8 = 4.0 + 0.60 \cdot 12.4 = 4.0 + 7.44 = 11.44$$

Closer to 10. The series is converging.

### Step 7 — Three-step-ahead forecast (Month 9)

$$\hat{x}_9 = 4.0 + 0.60 \cdot 11.44 = 4.0 + 6.864 = 10.864$$

### Long-horizon convergence

Continuing the chain:

| Horizon $k$ | Forecast $\hat{x}_{6+k}$ |
|:-:|:-:|
| 1 | 12.40 |
| 2 | 11.44 |
| 3 | 10.864 |
| 4 | 10.518 |
| 5 | 10.311 |
| 10 | 10.024 |
| 20 | 10.0001 |
| ∞ | **10.000** (= $\mu$) |

Visually:

```
14 |●
   | \
12 |  ●
   |   \
   |    ●
10 |.....●..●..●——————————————————  ← μ = 10
   |
   +———————————————————————————————►  Months ahead
     6  7  8  9 10 11 ...
```

The forecast asymptotes to $\mu = 10$ — the mean-reverting level. Each step closes the gap by a factor of $b_1 = 0.60$. After 10 periods the gap to $\mu$ is $4 \cdot 0.6^{10} = 0.024$, vanishingly small.

### Interpreting the result

The model says: *given the current overstock at \$14M, expect inventory to slide back toward its long-run normal of \$10M, with the bulk of the adjustment happening in the first three or four months.* The decay rate is governed entirely by $b_1$ — a higher $b_1$ would mean slower convergence.

---

## Common Pitfalls

| Pitfall | Why it bites |
|---------|-------------|
| Running OLS on a non-stationary series | Estimates are unreliable; standard errors are wrong. **Always test stationarity first.** |
| Using Durbin-Watson on the residuals | DW is invalid because the regressor is the lagged dependent variable. Use t-tests on residual autocorrelations. |
| Stopping at AR(1) when residuals are autocorrelated | The model is misspecified; coefficients are biased. Add lags until residuals are white noise. |
| Forecasting far into the future | All long-horizon forecasts converge to $\mu$; precision degrades quickly. |
| Confusing $b_1 = 1$ with stationarity | $b_1 = 1$ is a *unit root*, the boundary of stationarity. Strictly $\lvert b_1 \rvert < 1$ is needed. |

---

## Connections

- [[Covariance stationary]] — the precondition for OLS to work on AR models
- [[Unit root]] — what happens when $b_1 = 1$; the bridge to random walks
- [[Dickey-Fuller Test]] — formal stationarity test built around the AR(1)
- [[First Differencing]] — the remedy when $\lvert b_1 \rvert \geq 1$
- [[Mean Reversion]] — the long-run behavior the AR(1) captures
- [[Random Walk]] — the limiting non-stationary case
- [[AIC and BIC]] — for choosing the order $p$ in AR(p)
- [[Durbin-Watson Test]] — what NOT to use here, and why
- [[Serial Correlation]] — what the residual autocorrelation tests detect
- [[Hypothesis Testing in Regression]] — general framework that the t-test on $\hat{\rho}_k$ inherits
- [[Level 2/Generated Notes/02 - Quantitative Methods/Spurious Correlation]] — the failure mode if you skip stationarity testing

---

## LOS Coverage

This note supports the Time-Series Analysis LOS:

- **Calculate** and **interpret** the predicted value of a time series using an AR(1) model.
- **Explain** mean reversion and **calculate** the mean-reverting level.
- **Contrast** in-sample and out-of-sample forecasts and use the chain rule of forecasting.
- **Explain** the requirement that a series be covariance stationary to use AR estimation.
- **Describe** how to test for serial correlation of errors in an AR model and how to correct it.
- **Compare** AR models with different lag specifications using AIC/BIC.
- **Explain** the relation between AR(1), unit roots, and random walks.
