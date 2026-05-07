---
title: Dickey-Fuller Test
subject: 02 - Quantitative Methods
tags: [CFA-L2, time-series, stationarity, unit-root, hypothesis-testing, AR-models]
aliases: [DF test, Dickey Fuller test, Augmented Dickey-Fuller, ADF test, unit root test]
---

# Dickey-Fuller Test

## The Real-World Analogy

Imagine you're a quality inspector at a factory, and you have to decide whether a manufacturing process is "in control" (stable, predictable, anchored to a target) or "drifting" (slowly wandering off-spec). You have a regular thermometer that works perfectly under normal conditions, but breaks down when temperatures get extreme — *exactly the conditions you most need to detect.*

That's the situation with testing for non-stationarity. The thing you most want to detect — a series whose statistical "rules" are breaking down — is the very thing that breaks the standard tools (the t-test) you'd normally use to detect it. So Dickey and Fuller built a *special-purpose* thermometer with its own calibration. That's the Dickey-Fuller test: a test for non-stationarity that *works precisely because it's designed for non-stationary conditions.*

You use it whenever you've got a time series and you're about to fit an AR model. Before you can trust any forecast, you have to clear this hurdle: does the series have a [[Unit root]] or not?

---

## Why a Standard t-Test Fails — The Core Motivation

Suppose you fit an AR(1) by OLS and want to test whether $b_1 = 1$ (the unit-root condition). The naive approach:

$$t = \frac{\hat{b}_1 - 1}{\text{SE}(\hat{b}_1)}$$

Compare to standard t-table values. **This is wrong.** Two reasons, layered on each other:

### Reason 1 — The OLS standard error formula assumes a stationary regressor

In an AR(1), the regressor is $x_{t-1}$. The standard error formula for $\hat{b}_1$ uses the variance of that regressor in its denominator. Under the null hypothesis $b_1 = 1$, however, $x_{t-1}$ is a random walk — its variance grows with $t$ rather than being constant. So the formula is built on an assumption that breaks under the very hypothesis you're testing.

### Reason 2 — The sampling distribution of the t-statistic is not Student's t

Even if you ignore reason 1, mathematical statisticians showed in the 1970s that under $H_0: b_1 = 1$, the limiting distribution of the t-statistic is **non-standard**:

- It is **skewed** (asymmetric) toward more negative values.
- It has **fatter left tails** than the Student's t.
- The 5% critical value is around **−2.86**, not −1.96.

If you used standard t-table values, you'd reject the null too easily — flagging series as "stationary" when they actually have a unit root. That false confidence then leads to [[Level 2/Generated Notes/02 - Quantitative Methods/Spurious Correlation|spurious regressions]], misleading forecasts, and broken portfolio decisions.

So Dickey and Fuller (1979) did two things: (i) reformulated the regression to avoid the most awkward part of the math, and (ii) **simulated the correct sampling distribution under the null and tabulated new critical values**. The combination is what we call the Dickey-Fuller test.

---

## The Algebraic Transformation — The "Subtraction Trick"

The DF test is built around a clever rewrite of the AR(1).

### Step 1 — Start with the AR(1)

$$x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$$

### Step 2 — Subtract $x_{t-1}$ from both sides

$$x_t - x_{t-1} = b_0 + (b_1 - 1) x_{t-1} + \varepsilon_t$$

### Step 3 — Define new symbols

Let $\Delta x_t = x_t - x_{t-1}$ (the first difference) and $g_1 = b_1 - 1$ (the **transformed slope**). The equation becomes:

$$\boxed{\Delta x_t = b_0 + g_1 x_{t-1} + \varepsilon_t}$$

This is the **Dickey-Fuller regression**. Why is this rewrite useful?

### Why the transformation matters

| Original AR(1) | DF regression |
|----------------|---------------|
| Test $H_0: b_1 = 1$ vs $H_a: b_1 < 1$ | Test $H_0: g_1 = 0$ vs $H_a: g_1 < 0$ |
| Dependent variable $x_t$ — non-stationary under $H_0$ | Dependent variable $\Delta x_t$ — *stationary* under $H_0$ (it's white noise plus a constant) |
| t-stat distribution badly behaved | t-stat distribution still non-standard but tractable; critical values can be tabulated |

The trick converts a "is this slope equal to 1?" problem into a "is this slope equal to 0?" problem — and zero is a much friendlier boundary because OLS regression output already gives you the t-stat for "slope = 0" automatically.

### What you actually do in practice

1. Compute $\Delta x_t$ for $t = 2, \ldots, T$ — that's your dependent variable.
2. Use $x_{t-1}$ as the regressor.
3. Run OLS.
4. Read off the t-statistic on $\hat{g}_1$ from the regression output.
5. Compare it to **Dickey-Fuller** critical values (NOT standard t-table values).

---

## Hypotheses — One-Tailed and Why

| | Statement | What It Means |
|---|-----------|---------------|
| **$H_0$** | $g_1 = 0$ (equivalently $b_1 = 1$) | The series **has a unit root** — non-stationary, random walk |
| **$H_a$** | $g_1 < 0$ (equivalently $b_1 < 1$) | The series is **stationary**, mean-reverting |

### Why one-tailed (lower tail only)

You only reject the null toward $g_1 < 0$. The other direction ($g_1 > 0$, i.e., $b_1 > 1$) corresponds to an **explosive process** — variance grows exponentially, prices double every day forever. That's economically implausible (markets crash, regulators intervene), so we don't entertain it as an alternative. The test is built to distinguish "stationary" from "unit root," ignoring "explosive."

### What the alternative does NOT include

Importantly, the DF test does *not* test for trend-stationarity by default. A series that is stationary around a deterministic linear trend (rising at a steady rate plus stationary noise) will fail the basic DF test. To handle that, you use a variant — see "Variations" below.

---

## Dickey-Fuller Critical Values

The most important practical fact about the DF test: **you must use DF-specific critical values, not the standard t-table.** They are *larger in absolute value*, meaning the bar to reject the null is *higher*.

Approximate critical values for the DF regression *with a constant only* (the most common form), for moderate sample sizes ($T \approx 100$):

| Significance | Standard t (one-tail) | **Dickey-Fuller** |
|:------------:|:----------------------:|:------------------:|
| 10% | −1.28 | **≈ −2.57** |
| 5% | −1.65 | **≈ −2.86** |
| 1% | −2.33 | **≈ −3.43** |

Notice: at the 5% level, you need a t-stat more negative than **−2.86** to reject the unit-root null. With ordinary t-tables you'd only need −1.65. The DF hurdle is much higher.

### Why higher?

Because under $H_0$ (unit root), the OLS estimator $\hat{g}_1$ is biased downward in finite samples — it tends to come in negative even when the truth is $g_1 = 0$. If we used standard critical values, we'd reject the unit root far more often than 5% of the time when it's actually true. Tabulated DF critical values correct for this bias.

### How critical values vary

DF critical values depend on:
- **Sample size** — they get slightly smaller in absolute value as $T$ grows.
- **Specification** — the constant-only form has different values than the constant-plus-trend form.

For exam purposes, the values above (constant-only, moderate sample) are the ones to memorize.

---

## Decision Rule

After running the DF regression, you have a computed t-statistic $t_\text{calc}$ on $\hat{g}_1$ and a critical value $t_\text{crit}$ (negative number from the DF table).

| Condition | Conclusion |
|-----------|------------|
| $t_\text{calc} < t_\text{crit}$ (more negative than the cutoff) | **Reject $H_0$.** Series is stationary; an AR(1) on raw levels is appropriate. |
| $t_\text{calc} > t_\text{crit}$ (not negative enough) | **Fail to reject $H_0$.** Series has a unit root; you must transform (first-difference) before modeling. |

**Mnemonic:** "more negative than the critical value → kill the null." Failure to clear the hurdle leaves the unit root standing, and you should treat the series as non-stationary.

---

## Variations — Three Flavors of the DF Test

Real-world series come in different shapes, and Dickey-Fuller comes in three main forms. The right choice depends on what you see when you plot the data.

### 1. No constant, no trend

$$\Delta x_t = g_1 x_{t-1} + \varepsilon_t$$

Used only if the series is known to fluctuate around zero with no drift. Rare in finance.

### 2. Constant only (the standard form)

$$\Delta x_t = b_0 + g_1 x_{t-1} + \varepsilon_t$$

This is the form covered above. Use when the series appears to fluctuate around a non-zero mean but has no visible trend. **This is the default CFA Level 2 form.**

### 3. Constant and trend

$$\Delta x_t = b_0 + b_1 t + g_1 x_{t-1} + \varepsilon_t$$

Adds a deterministic time trend $b_1 t$. Use when the series shows visible upward (or downward) drift over time — e.g., GDP, price levels. Rejecting $H_0$ here means the series is **trend-stationary** — stable around a deterministic trend, not a unit root.

The critical values for this version are *even more negative* (e.g., ≈ −3.45 at 5%) because a trend term gives the model extra flexibility to explain non-stationary-looking data without invoking a unit root.

### 4. Augmented Dickey-Fuller (ADF)

The basic DF assumes the residuals $\varepsilon_t$ are white noise — no serial correlation. In practice, real series often have richer dynamics that the simple DF regression doesn't capture, leaving residuals correlated. That violates the test's assumptions.

The **Augmented Dickey-Fuller (ADF)** test fixes this by adding extra lagged differences as regressors:

$$\Delta x_t = b_0 + g_1 x_{t-1} + \delta_1 \Delta x_{t-1} + \delta_2 \Delta x_{t-2} + \cdots + \delta_p \Delta x_{t-p} + \varepsilon_t$$

The extra lags soak up any residual autocorrelation. The test is still on $g_1$ — same null, same alternative, same critical values. The $\delta_i$ coefficients aren't of interest; they're "nuisance" terms.

For CFA purposes you should know:
- **ADF exists and is preferred when residuals from basic DF are autocorrelated.**
- It is the form most software (R's `adf.test()`, Python's `statsmodels.tsa.stattools.adfuller()`) uses by default.
- The interpretation of the $\hat{g}_1$ t-statistic is identical to basic DF.

---

## What to Do After the Test

### If you reject $H_0$ — series is stationary

You're free to model the levels directly with an AR(p), use the mean-reverting level $b_0/(1-b_1)$, and forecast normally. See [[AR(1) Model]].

### If you fail to reject $H_0$ — series has a unit root

You cannot model the raw series. Two paths:

**1. First-differencing.** Build $y_t = \Delta x_t = x_t - x_{t-1}$. Run a DF test on $\{y_t\}$ to confirm *it* is now stationary. If yes, the original series is **integrated of order 1**, written $I(1)$, and you fit AR models to $\{y_t\}$.

**2. Cointegration check (multivariate).** If you have *two* unit-root series and you want to model their relationship, test whether they are [[Cointegration|cointegrated]] using the Engle-Granger procedure. If yes, you can run a regression on the levels meaningfully. If no, only differences are usable. See [[Unit root]] for the cointegration discussion.

---

## Common Pitfalls

| Pitfall | Why It Bites |
|---------|--------------|
| Using standard t-table critical values | The single most common exam trap. The t-distribution doesn't apply under $H_0$. Always use DF tables. |
| Choosing the wrong DF variant | A trending series tested with constant-only DF can falsely fail to reject. Pick the variant that matches the visual shape of the data. |
| Small samples | DF has low *power* in small samples — it may fail to detect a stationary alternative even when one exists. With $T < 50$, results are unreliable. |
| Structural breaks | A policy change or regime shift creates the appearance of non-stationarity. The DF test will incorrectly conclude "unit root" when the series is actually two stationary regimes glued together. |
| Ignoring residual autocorrelation | Basic DF assumes white-noise errors. If they're autocorrelated, use ADF instead. |
| Reporting $\hat{b}_1$ instead of $\hat{g}_1$ | They differ by exactly 1. The t-stat in the DF output is for $\hat{g}_1$ — that's the one to compare to DF critical values. |

---

## Worked Numerical Example

An analyst has 10 monthly observations of an exchange rate and wants to know whether AR-style modeling is appropriate.

| Month $t$ | $x_t$ |
|:-:|:-:|
| 1 | 1.10 |
| 2 | 1.12 |
| 3 | 1.11 |
| 4 | 1.13 |
| 5 | 1.15 |
| 6 | 1.14 |
| 7 | 1.16 |
| 8 | 1.18 |
| 9 | 1.17 |
| 10 | 1.19 |

### Step 1 — Visual inspection

The series drifts upward from 1.10 to 1.19 over 10 months. Suspicious — looks like it might be non-stationary, but could also be stationary around a slowly rising trend. Run the DF test to settle it.

### Step 2 — Build the DF regression columns

We need $\Delta x_t$ as the dependent variable and $x_{t-1}$ as the regressor. We lose the first observation.

| $t$ | $x_t$ | $x_{t-1}$ | $\Delta x_t$ |
|:-:|:-:|:-:|:-:|
| 2 | 1.12 | 1.10 | +0.02 |
| 3 | 1.11 | 1.12 | −0.01 |
| 4 | 1.13 | 1.11 | +0.02 |
| 5 | 1.15 | 1.13 | +0.02 |
| 6 | 1.14 | 1.15 | −0.01 |
| 7 | 1.16 | 1.14 | +0.02 |
| 8 | 1.18 | 1.16 | +0.02 |
| 9 | 1.17 | 1.18 | −0.01 |
| 10 | 1.19 | 1.17 | +0.02 |

Nine observation pairs from the original ten data points.

### Step 3 — Run OLS for $\Delta x_t = b_0 + g_1 x_{t-1} + \varepsilon_t$

Suppose the OLS output (computed via software or by hand) gives:

- $\hat{b}_0 = 0.075$
- $\hat{g}_1 = -0.05$
- $\text{SE}(\hat{g}_1) = 0.04$

### Step 4 — Compute the test statistic

$$t_\text{calc} = \frac{\hat{g}_1 - 0}{\text{SE}(\hat{g}_1)} = \frac{-0.05}{0.04} = -1.25$$

### Step 5 — Compare against the DF critical value

At the 5% significance level (one-tailed lower), the DF critical value is approximately **−2.86** for moderate sample sizes. The exact value for $T = 10$ is more negative still (smaller samples need larger absolute critical values), but for illustration we'll use −2.86.

| Quantity | Value |
|----------|-------|
| Calculated t-statistic | **−1.25** |
| DF critical value (5%, constant only) | **−2.86** |
| Is $t_\text{calc} < t_\text{crit}$? | $-1.25 < -2.86$? → **No** |

### Step 6 — Conclusion

We **fail to reject $H_0$**. The series has a unit root and is non-stationary.

### Step 7 — What the analyst does next

Don't run an AR(1) on the raw exchange-rate levels. Instead:

1. **First-difference** the series: $y_t = x_t - x_{t-1}$. The differenced series is the $\Delta x_t$ column above: {+0.02, −0.01, +0.02, +0.02, −0.01, +0.02, +0.02, −0.01, +0.02}.
2. **Re-run a DF test** on $\{y_t\}$ to confirm stationarity.
3. If the differenced series is stationary, fit an AR model on the differences and report forecasts in change-of-rate terms.

### Compare to the wrong conclusion

If the analyst had used the *standard* t-table at 5% (critical value ≈ −1.65), they would have computed:

$$-1.25 < -1.65? \text{ → No}$$

…and *also* failed to reject. In this particular case, both tests give the same answer. But for a borderline case — say $t_\text{calc} = -2.20$:

| Test | Critical value | Decision |
|------|----------------|----------|
| Standard t-table | −1.65 | $-2.20 < -1.65$? Yes → **Reject** ($H_0$: stationary) |
| Dickey-Fuller table | −2.86 | $-2.20 < -2.86$? No → **Fail to reject** (unit root) |

Two opposite conclusions from the same number. The DF result is the correct one, and this is precisely why the test exists.

---

## Connections

- [[Unit root]] — the property the test checks for
- [[Covariance stationary]] — what stationarity means and why we need it
- [[AR(1) Model]] — the model whose lag coefficient is being tested
- [[First Differencing]] — the standard remedy when the test fails
- [[Random Walk]] — the canonical unit-root process
- [[Cointegration]] — the multivariate extension; the Engle-Granger test reuses DF on residuals
- [[Level 2/Generated Notes/02 - Quantitative Methods/Spurious Correlation]] — what happens if you skip the DF test and run regressions on non-stationary series
- [[Hypothesis Testing in Regression]] — the general framework this test inherits from
- [[P-Value]] — interpretation of the DF p-value, which most software reports automatically

---

## LOS Coverage

This note supports the Time-Series Analysis LOS:

- **Explain** the requirement that a series be covariance stationary to use AR estimation.
- **Describe** how to test for and correct non-stationarity, including the use of the Dickey-Fuller test for unit roots.
- **Calculate** and **interpret** the test statistic from a Dickey-Fuller regression and reach the appropriate conclusion.
- **Describe** the steps to take if a unit root is detected (first-differencing, re-testing, integration order).
