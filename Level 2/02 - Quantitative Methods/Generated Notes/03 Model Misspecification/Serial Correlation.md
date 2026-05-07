---
title: Serial Correlation
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, time-series, diagnostics]
aliases: [Autocorrelation, Serial Correlation of Residuals]
---

# Serial Correlation

## The Real-World Analogy First

Imagine you're tracking your daily mood on a scale of 1–10. If you're in a great mood today, you're probably still in a decent mood tomorrow — yesterday's mood *bleeds into* today's. Your mood observations aren't independent; they carry memory from the past.

Now imagine you're an analyst tracking monthly corporate earnings surprises. If a company beats earnings one quarter, there's a decent chance it beats again next quarter — the underlying business conditions that drove the beat haven't fully reversed. The residuals in your regression model of that company's stock returns are doing the same thing: each one is correlated with the one before it.

That "bleeding over" of one period's value into the next is **serial correlation** — also called **autocorrelation**. Think of it as the **"echo" problem**: your model's errors echo each other through time, when they should be random static on a radio.

---

## What It Actually Means

In any regression or time-series model, you're fitting:

$$Y_t = b_0 + b_1 X_t + \varepsilon_t$$

The $\varepsilon_t$ terms are your **residuals** — the unexplained portion of $Y$ at each time $t$. A core assumption of [[Ordinary Least Squares]] (OLS) regression is that these residuals are **uncorrelated across time**. Formally:

$$\text{Cov}(\varepsilon_t, \varepsilon_{t-k}) = 0 \quad \text{for all } k \neq 0$$

Serial correlation is the violation of this assumption. The residual at time $t$ is systematically related to the residual at time $t-1$ (or $t-2$, etc.).

---

## Two Flavors: Positive and Negative

**Positive serial correlation** is the more common case — and especially common in financial data because markets, economies, and businesses have **momentum**. If the residual was positive last period (the model underestimated $Y$), it tends to be positive again this period. Plotted, residuals look like smooth waves — clustering on one side of zero for a while, then the other.

```
Residuals
  +  |  * * *
     |         * * *
  0  |---------------------> time
     |             * * *
  -  |  * * *
```

**Negative serial correlation** means last period's positive residual is followed by a negative one — residuals alternate signs like a bouncing ball. Rare in investment data, but it shows up if a model systematically overshoots then undershoots.

```
Residuals
  +  |  *   *   *
     |
  0  |---------------------> time
     |
  -  |    *   *   *
```

---

## Why OLS Breaks Down

Serial correlation acts like a **confidence trickster** on OLS. In a standard regression (no lagged dependent variable), it doesn't ruin your *coefficients* — but it severely messes up the "report card" attached to them.

| Consequence | What It Means Practically |
|---|---|
| Coefficients ($b_0$, $b_1$) are still **unbiased** | Your slope estimates aren't systematically wrong — just noisier than reported |
| Standard errors are **biased downward** | OLS *underestimates* the true uncertainty |
| t-statistics are **inflated** | Because SE is too small, t-stats look bigger than they should |
| p-values are **too small** | You reject $H_0$ too often — **Type I errors** explode |
| F-statistics are **unreliable** | Overall regression significance test is compromised |
| Confidence intervals are **too narrow** | False precision — more confident than you should be |

The dangerous practical effect: you think you've found a statistically significant relationship when you haven't. In portfolio work, you might trade on a phantom signal.

### The AR Model Exception

There's a critical wrinkle. If your model is an **autoregressive (AR)** model — where lagged $Y$ itself appears as a regressor (e.g., $Y_t = b_0 + b_1 Y_{t-1} + \varepsilon_t$) — serial correlation is *much* more dangerous. The coefficients themselves become **biased and inconsistent**, not just the standard errors. The lagged $Y_{t-1}$ is correlated with the lagged error $\varepsilon_{t-1}$, which is correlated with the current error $\varepsilon_t$, poisoning the whole estimation. Memorize this exception — it's a classic CFA trap.

---

## How to Detect It: The Durbin-Watson Test

The classic diagnostic is the **Durbin-Watson (DW) statistic**. It tests specifically for **first-order serial correlation** — correlation between adjacent residuals ($\varepsilon_t$ and $\varepsilon_{t-1}$).

### The Formula

$$DW = \frac{\sum_{t=2}^{T} (\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2}{\sum_{t=1}^{T} \hat{\varepsilon}_t^2}$$

You're dividing the sum of squared *differences* in consecutive residuals by the total sum of squared residuals.

### Derivation to the Handy Form

Expand the numerator:

$$\sum (\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2 = \sum \hat{\varepsilon}_t^2 + \sum \hat{\varepsilon}_{t-1}^2 - 2\sum \hat{\varepsilon}_t \hat{\varepsilon}_{t-1}$$

For large $T$, $\sum \hat{\varepsilon}_t^2 \approx \sum \hat{\varepsilon}_{t-1}^2 \approx \sum \hat{\varepsilon}^2$, so:

$$DW \approx \frac{2\sum \hat{\varepsilon}^2 - 2\sum \hat{\varepsilon}_t \hat{\varepsilon}_{t-1}}{\sum \hat{\varepsilon}^2} = 2\left(1 - \frac{\sum \hat{\varepsilon}_t \hat{\varepsilon}_{t-1}}{\sum \hat{\varepsilon}^2}\right)$$

The fraction inside the parentheses is exactly the estimated first-order autocorrelation $\hat{\rho}$, giving the clean formula:

$$\boxed{DW \approx 2(1 - \hat{\rho})}$$

### Intuition

If residuals are positively correlated, consecutive ones are similar — their *differences* are small → numerator small → **DW small**. If uncorrelated, consecutive differences are about as big as the residuals themselves → **DW ≈ 2**. If negatively correlated, residuals flip signs, so differences are large → **DW large**.

| DW Value | $\hat{\rho}$ | Interpretation |
|---|---|---|
| Close to **0** | $\approx +1$ | Strong **positive** serial correlation |
| Close to **2** | $\approx 0$ | **No** serial correlation (ideal) |
| Close to **4** | $\approx -1$ | Strong **negative** serial correlation |

### The Decision Rule

Compare your DW to critical values $d_L$ and $d_U$ from the DW table (they depend on sample size $n$ and number of regressors $k$):

```
0 ----[dL]----[dU]--------2--------[4-dU]----[4-dL]---- 4
  Positive   Incon-   No serial   Incon-   Negative
  serial    clusive  correlation  clusive   serial
  correl.                                  correl.
```

### The Critical DW Trap

The DW test is **invalid** when a lagged dependent variable appears as a regressor (as in AR models). The test statistic is biased toward 2, so you'll falsely conclude "no serial correlation" when there actually is some. For AR models, use Breusch-Godfrey (or the related **t-test on residual autocorrelations**) instead.

---

## Alternative Detection: The Breusch-Godfrey Test

The **Breusch-Godfrey (BG) test** is more general — it can detect serial correlation up to any order $p$ and works fine with lagged dependent variables.

**Procedure**: Run your original regression, save residuals $\hat{\varepsilon}_t$, then regress those residuals on the original regressors *plus* lagged residuals $\hat{\varepsilon}_{t-1}, \ldots, \hat{\varepsilon}_{t-p}$. Test statistic is $n \cdot R^2$ from this auxiliary regression, distributed as $\chi^2(p)$ under $H_0$: no serial correlation.

If the test statistic is high, you reject — serial correlation is present.

---

## Worked Numerical Example

You're regressing monthly stock returns $Y_t$ on a market factor $X_t$ using $T = 100$ observations. After estimation, you save the residuals and compute:

$$\sum_{t=2}^{100} (\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2 = 4.8 \qquad \sum_{t=1}^{100} \hat{\varepsilon}_t^2 = 12.0$$

**Step 1 — Compute DW:**

$$DW = \frac{4.8}{12.0} = 0.40$$

**Step 2 — Interpret:** DW = 0.40 is very close to zero. From the DW table with $n = 100$, $k = 1$: $d_L \approx 1.65$, $d_U \approx 1.69$. Since $0.40 < d_L$, **reject the null** — strong positive serial correlation.

**Step 3 — Back out $\hat{\rho}$:**

$$0.40 \approx 2(1 - \hat{\rho}) \implies \hat{\rho} = 1 - \frac{0.40}{2} = 0.80$$

An autocorrelation of **0.80** means ~80% of last period's residual bleeds into this period's. Your reported standard errors are badly underestimated, and any "significant" t-stats from this regression are suspect.

**Step 4 — Fix it:** Re-estimate with Newey-West standard errors. Coefficients stay the same; standard errors rise; t-stats shrink to honest levels.

---

## Second Worked Example — Inflation Trend Regression

A more realistic CFA-flavored scenario. An analyst tests a linear time trend for monthly U.S. inflation using $n = 228$ months and one independent variable ($k = 1$):

$$\text{Inflation}_t = b_0 + b_1 \cdot t + \varepsilon_t$$

The software output reports **DW = 1.2145**.

**Step 1 — Look up critical values:** For $n = 228$, $k = 1$, the DW table gives $d_L \approx 1.77$ (and $d_U$ just above it).

**Step 2 — Compare:**

$$1.2145 < d_L = 1.77$$

So DW is in the **reject region** for positive serial correlation.

**Step 3 — Back out $\hat{\rho}$:**

$$\hat{\rho} \approx 1 - \frac{DW}{2} = 1 - \frac{1.2145}{2} \approx 0.393$$

About 39% of last month's residual carries into this month's — a meaningful echo.

**Step 4 — Interpret:** Reject $H_0$: no serial correlation. The reported t-statistics on the trend coefficient are inflated and cannot be trusted. Before drawing any conclusion about whether inflation has a true linear trend, the model must be re-estimated with Newey-West (HAC) standard errors — or respecified to capture the missing dynamic (e.g., add a lagged inflation term, or first-difference the series).

**The lesson**: a headline-significant trend from OLS on time-series data is never trustworthy until you've checked DW.

---

## How to Fix It

| Remedy | How It Works | When to Use |
|---|---|---|
| **Newey-West SEs** | Adjusts standard errors for both serial correlation *and* heteroskedasticity; coefficients unchanged | Default CFA fix; keeps model intact |
| **Generalized Least Squares (GLS)** | Transforms data to "whiten" residuals (e.g., Cochrane-Orcutt) | More powerful but more involved |
| **Add lagged variables** | If serial correlation stems from misspecification, adding $Y_{t-1}$ or $\Delta X_t$ fixes the root cause | Leftover dynamic process |
| **First-difference the data** | Regress $\Delta Y_t$ on $\Delta X_t$ instead of levels | Non-stationary / trending variables |

**Newey-West** is the go-to. It produces **heteroskedasticity and autocorrelation consistent (HAC)** standard errors — coefficients don't change, standard errors are corrected upward. Think of it as **noise-canceling headphones**: same signal, honest volume.

---

## Serial Correlation vs. Heteroskedasticity

Easy to confuse — here's the distinction:

| Feature | Serial Correlation | [[Heteroskedasticity]] |
|---|---|---|
| What's correlated | Residuals *across time* | Residual *variance* across observations |
| Classic symptom | Residuals show time patterns | Residuals fan out vs. fitted values |
| Primary test | Durbin-Watson, Breusch-Godfrey | Breusch-Pagan, White test |
| Fix | Newey-West HAC SEs | White (robust) SEs |
| Coefficients biased? | No* | No |
| SEs biased? | Yes (usually downward) | Yes (direction varies) |

\* Except in AR models, where coefficients *are* biased.

Newey-West handles **both** simultaneously — why it's the preferred default in financial time series.

---

## Memory Hooks

- **Echo problem**: errors echo through time
  - **DW ≈ 0** → loud echo (positive serial correlation)
  - **DW ≈ 2** → no echo (clean white noise — ideal)
  - **DW ≈ 4** → anti-echo (negative serial correlation)
- **"Two minus rho doubled"** — $DW \approx 2(1 - \hat{\rho})$
- **Newey-West = noise-canceling headphones** — same signal, honest volume
- **AR trap** — Durbin-Watson breaks when lagged $Y$ is a regressor; use Breusch-Godfrey instead
- **"Type I explosion"** — underestimated SEs → inflated t-stats → false significance

---

## CFA LOS Coverage

This note discharges the following CFA Level 2 Learning Outcome Statements:

| LOS | Verb | Covered By |
|---|---|---|
| **Quant LOS 3.c** — *explain serial correlation and how it affects statistical inference* | **explain** | "What It Actually Means", "Two Flavors", "Why OLS Breaks Down" sections |
| **Quant LOS 3.d** — *describe tests for detecting serial correlation (Durbin-Watson, Breusch-Godfrey)* | **describe** | "How to Detect It" and "Alternative Detection" sections |
| **Quant LOS 3.e** — *describe methods for correcting serial correlation* | **describe** | "How to Fix It" section (Newey-West, GLS, respecification, differencing) |
| **Quant LOS 5.e** — *explain how autocorrelations of the residuals can be used to test whether the autoregressive model fits the time series* | **explain** | "The AR Model Exception" subsection — extends to [[Autoregressive Models]] note |

After reading, you should be able to **describe** both tests, **calculate** DW from residual sums, **interpret** a DW value against critical bounds, **explain** the consequences for inference, and **identify** the Newey-West remedy.

## CFA Exam Focus

1. **Definition**: correlation between residuals across time
2. **Effect on OLS**: coefficients unbiased (except AR models), SEs underestimated → inflated t-stats → spurious significance
3. **Detection**: Durbin-Watson (DW near 0 = positive, near 4 = negative, near 2 = none)
4. **Fix**: Newey-West HAC standard errors
5. **DW limitation**: unreliable with lagged dependent variables — use Breusch-Godfrey
6. **AR model exception**: serial correlation biases coefficients themselves, not just SEs

## Related Notes

[[Heteroskedasticity]] · [[Autoregressive Models]] · [[Time Series Analysis]] · [[Regression Assumptions]] · [[Durbin-Watson Test]] · [[Newey-West Standard Errors]] · [[Covariance Stationarity]] · [[Ordinary Least Squares]] · [[F Distribution and F Tests]]
