---
title: "CFA L2 - Time-Series Analysis"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, time-series, AR-model, unit-root, ARCH, cointegration, stationarity]
aliases: ["Module 2", "Time Series", "AR Model", "Unit Root", "ARCH Models"]
---

# Module 2 — Time-Series Analysis

## Data That Remembers Its Past

Most regression models treat each observation as [[Independent|independent]] — the return in January has nothing to do with the return in February. But financial data usually violates this assumption dramatically. Earnings this quarter are heavily influenced by earnings last quarter. Interest rates today depend on where rates were yesterday. [[Inflation|Inflation]] next month is related to [[Inflation|inflation]] this month.

**Time-series analysis** is a toolkit specifically built for data that is *ordered in time*, where the past carries information about the future. Instead of asking "what factors predict Y?" it asks "**what does Y's own history tell us about where Y is going?**"

---

## Part 1 — Trend Models

The simplest time-series models just look for a *direction* — a steady upward or downward drift over time.

### Linear Trend Model

$$y_t = b_0 + b_1 t + \epsilon_t$$

Where $t = 1, 2, 3, \ldots$ represents the time period.

**When to use it:** When you believe $y$ grows by a **constant dollar amount** each period. The trend is a straight line — like a company that adds exactly 1,000 new customers every quarter regardless of its current size.

```
y
│               ●
│          ●
│     ●
│●
└─────────────────── time
   Equal vertical jumps each period
```

**Finance example:** CPI inflation tracked in levels can sometimes appear linear over short horizons.

### Log-Linear Trend Model

$$\ln y_t = b_0 + b_1 t + \epsilon_t$$

**When to use it:** When you believe $y$ grows at a **constant percentage rate** — i.e., exponential growth. In this case, the *dollar* amount added each period keeps getting bigger (because you're growing a percentage of an ever-larger base), so the series curves upward.

```
y (in levels)               ln(y) (after log transformation)
│               ●           │               ●
│          ●                │          ●
│      ●                    │     ●
│   ●                       │●
│ ●                         │
└──────────── time          └──────────── time
   Exponential curve           Straight line
```

**Finance example:** Starbucks' quarterly sales grew so rapidly in its expansion phase that a linear model couldn't keep up. A log-linear model was needed to fit the curved growth pattern. The key test: **plot your data first** — if it curves upward like a hockey stick, use log-linear.

### The Decision Rule

| Plot of Raw Data | Model to Use |
|-----------------|-------------|
| Straight ramp up/down | Linear trend |
| Hockey-stick curve (accelerating) | Log-linear trend |
| Irregular — neither | Consider AR or differencing |

---

## Part 2 — Autoregressive (AR) Models

### The Core Idea

A **trend model** uses *time* as its only predictor. An **[[Autoregressive model]]** goes further: it uses the *past values of Y itself* as predictors.

The logic: if stock returns exhibit momentum, today's return might be partially explained by yesterday's return. If earnings are sticky, this quarter's earnings will partially reflect last quarter's earnings. AR models formalize this self-referential structure.

### AR(1) — First-Order Autoregressive

$$x_t = b_0 + b_1 x_{t-1} + \epsilon_t$$

"Today's value = intercept + (coefficient × yesterday's value) + random noise"

The coefficient $b_1$ is the key:

| $b_1$ Value | Interpretation |
|------------|----------------|
| $b_1 > 0$ | Positive momentum — above-average values tend to be followed by above-average values |
| $b_1 < 0$ | Mean-reverting oscillation — above-average values tend to flip to below-average |
| $b_1 = 0$ | No predictability from past — white noise |
| $b_1 = 1$ | Random walk — no [[Mean reversion|mean reversion]] (see [[Unit root|unit root]] section) |
| $\|b_1\| < 1$ | Mean-reverting — series eventually returns to its long-run level |

**The long-run mean:** For a stationary AR(1) model, the series converges toward:

$$\bar{x} = \frac{b_0}{1 - b_1}$$

If $b_1$ is close to 1, mean reversion is very slow. If $b_1$ is close to 0, mean reversion is very fast.

### AR(p) — Higher-Order Models

An AR($p$) model uses $p$ past periods as predictors:

$$x_t = b_0 + b_1 x_{t-1} + b_2 x_{t-2} + \cdots + b_p x_{t-p} + \epsilon_t$$

The challenge: how many lags ($p$) should you include? Too few: the model misses real patterns. Too many: [[Overfitting|overfitting]]. The answer comes from examining the [[Autocorrelation|autocorrelation]] structure of the residuals.

### Autocorrelations and the Correlogram

**[[Autocorrelation]]** measures how much a time series correlates with its own past values. The autocorrelation at lag $k$ is:

$$\rho_k = \text{Corr}(x_t, x_{t-k})$$

A **correlogram** is a bar chart showing autocorrelations at each lag:

```
Autocorrelation
  1.0│
     │●
  0.5│ ●
     │   ●
  0  │━━━━●━━●━━●━━●━━●━━ ← "significance band"
     │               ● ●
 -0.5│
     └─────────────────────── Lag (1, 2, 3, 4, 5, 6...)

AR model residuals should look like this (no bars sticking out above/below the band)
```

If the residual correlogram shows **significant spikes** at some lags, the model is misspecified — you need to add more lags.

> [!tip] Model Selection Rule
> - **AR model**: Autocorrelations decay gradually (geometric decline)
> - **MA (Moving Average) model**: Autocorrelations cut off sharply after lag $q$
> - **Well-specified model's residuals**: No significant autocorrelations at any lag

### The Chain Rule of Forecasting

When forecasting more than one period ahead, you use your own predictions as inputs — **the chain rule**:

**Forecast 1 period ahead:**
$$\hat{x}_{t+1} = \hat{b}_0 + \hat{b}_1 x_t$$

**Forecast 2 periods ahead** (you don't have $x_{t+1}$ yet, so plug in $\hat{x}_{t+1}$):
$$\hat{x}_{t+2} = \hat{b}_0 + \hat{b}_1 \hat{x}_{t+1}$$

**And so on:** Each step uses the previous step's forecast.

The key insight: for a mean-reverting AR model, **multi-period forecasts converge toward the long-run mean $\bar{x}$**. Each step of the chain rule nudges the forecast closer to $b_0/(1-b_1)$ until, far enough in the future, every forecast simply equals the mean.

```
Forecast converging to mean:
y
│ ×
│   ×
│     ×  ×
│          × × × ×━━━━━━━━ (long-run mean)
│
└──────────────────────────── Forecast horizon
   Each step: forecast drifts toward mean
```

**Finance example:** An analyst forecasting Intel's gross margins. If current margins are above the historical average and the AR(1) coefficient is 0.7, each step of the chain rule pulls the forecast 30% closer to the mean. After several periods, the forecast essentially converges to the long-run average.

---

## Part 3 — Stationarity and Unit Roots

### Why Stationarity Matters

For AR models (and most time-series forecasting) to work, the data must be **covariance stationary** — its statistical properties must stay roughly constant over time:

1. **Constant mean** — the series doesn't trend upward or downward permanently
2. **Constant variance** — the "wobbliness" doesn't change over time
3. **Constant autocorrelation structure** — the relationship with past values stays stable

If a series isn't stationary, forecasts become meaningless. The model is calibrated on one "regime" but applied to another. Results become **spurious** — random coincidences masquerading as relationships.

### The Unit Root Problem

In an AR(1) model $x_t = b_0 + b_1 x_{t-1} + \epsilon_t$, a **[[Unit root]]** occurs when $b_1 = 1$ exactly.

This creates a **random walk**:

$$x_t = b_0 + x_{t-1} + \epsilon_t$$

"Today = yesterday + a random shock."

```
Random Walk (unit root — b₁ = 1):
y
│        ●
│      ●   ●
│    ●       ●
│●               ●
│                  ●
└──────────────────── time
  Wanders without bound — no mean to return to

Stationary AR (|b₁| < 1):
y
│         ●
│  ●   ●     ●   ●
│──●───────────●───── long-run mean
│                  ●
│  ●
└──────────────────── time
  Fluctuates but reverts to mean
```

**Why random walks are a forecasting disaster:** Stock prices famously follow (approximately) a random walk. If a stock is at $100 today, the best AR forecast for tomorrow is $100 (plus drift). For next year: still $100 (plus accumulated drift). But the *uncertainty* grows without bound — the 95% prediction interval keeps widening as the forecast horizon extends.

### The Dickey-Fuller Test

The **[[Dickey-Fuller Test]]** formally tests for a unit root:

$$H_0: b_1 = 1 \quad (\text{unit root — non-stationary})$$
$$H_A: b_1 < 1 \quad (\text{stationary})$$

**Key exam point:** The null hypothesis is *non-stationarity*. Rejecting $H_0$ means your series IS stationary (good). Failing to reject $H_0$ means you have a unit root (bad — need to transform the data).

> [!warning] Direction of the Test
> The DF test is unusual: you *want* to reject the null (stationarity is the alternative). On the exam, watch for trick questions asking what "rejection" means.

### The Fix: First-Differencing

If a series has a unit root, **first-differencing** usually fixes it. Instead of modeling $x_t$, model the *change* $\Delta x_t = x_t - x_{t-1}$:

$$\Delta x_t = b_0 + b_1 \Delta x_{t-1} + \epsilon_t$$

Stock prices may be non-stationary, but **returns** ($\Delta \text{price}/\text{price}$) are approximately stationary. The level wanders; the change bounces around a roughly constant mean.

---

## Part 4 — ARCH Models: When Volatility Clusters

### The Observation That Changed Finance

In 1982, Robert Engle noticed something about financial markets: **large price swings tend to cluster together**. After a crash, there's more volatility. During calm bull markets, volatility is low for months. This is **volatility clustering**:

```
Return
  │
 +│    ████  ████             ████
  │   █  █ █  █             █  █
  │
  0 ──────────────────────────────── time
  │
 -│         ████          ████████
  │        █   █         █       █

Calm periods:  small bars
Crisis periods: large bars in clusters
```

Standard regression models assume the *variance* of errors is constant over time. Volatility clustering means this assumption is catastrophically wrong for financial data.

### ARCH(1) — The Model

**[[ARCH]] (Autoregressive Conditional [[Heteroskedasticity|heteroskedasticity]])** models the variance of the error term as a function of its own past:

$$\hat{\epsilon}_t^2 = a_0 + a_1 \hat{\epsilon}_{t-1}^2 + \nu_t$$

"Today's variance = constant + (coefficient × yesterday's squared error)"

If $a_1$ is large and positive: a big shock yesterday (large $\hat{\epsilon}_{t-1}^2$) predicts a large variance today. This is volatility clustering, captured mathematically.

### Why ARCH Matters for Risk Management

1. **Better [[Value at risk|VaR]] estimates:** Value-at-Risk calculations that ignore ARCH will underestimate risk in volatile periods and overestimate it in calm periods. ARCH-based VaR adapts dynamically.

2. **Honest standard errors:** If ARCH errors are present, standard OLS standard errors are wrong — typically understating risk. An ARCH-corrected model gives you standard errors you can trust.

3. **Options pricing:** Implied volatility in options markets reflects the market's expectation of future volatility. ARCH models help explain this time-varying structure.

**Real-world example:** A risk manager running daily VaR for a trading desk. After the 2020 COVID crash (massive volatility), the ARCH model immediately inflates the estimated variance, signaling that risk limits should be tightened. As markets calm over the next months, the model gradually lowers the risk estimate. A static model would miss both the spike and the recovery.

> [!tip] ARCH Detection
> To test for ARCH effects: regress the squared residuals ($\hat{\epsilon}_t^2$) from your primary regression on lagged squared residuals. If the coefficients are significant, you have ARCH.

---

## Part 5 — Cointegration: Long-Run Relationships Between Non-Stationary Series

### The Problem

You can't just run a [[Linear regression]] between two time series that both have unit roots. The results would be **spurious** — the math finds a "relationship" simply because both series are trending, even if they have nothing to do with each other.

Classic example: ice cream sales and drowning deaths both rise in summer and fall in winter. A regression finds a "strong relationship" — but it's a coincidence driven by a common trend (temperature), not a real causal link.

### The Exception: Cointegration

However, there is one case where regression *is* valid between two non-stationary series: when they are **[[Cointegrated]]**.

Two I(1) series (series with a unit root) are cointegrated if there exists a linear combination of them that is stationary — i.e., they share a long-run equilibrium relationship that prevents them from drifting too far apart.

**The dog-leash analogy:**

```
A person walking a dog on a leash:

Both the person (Y₁) and the dog (Y₂) wander non-stationarily.
But the leash keeps them connected — they can't drift more than
the length of the leash apart.

The "leash" = the cointegrating relationship.
The gap between them = Y₁ - βY₂ = stationary error.
```

### Why Regression is Valid

When two series are cointegrated, the **error term** from regressing $Y_1$ on $Y_2$ is stationary — it doesn't wander off forever. This means:
- The OLS estimates are meaningful and consistent
- The residuals have a well-behaved, bounded distribution
- You can make valid inferences about the long-run relationship

### Testing for Cointegration

**Engle-Granger two-step approach:**
1. Regress $Y_1$ on $Y_2$ and save the residuals
2. Test if those residuals have a unit root (using Dickey-Fuller)
   - If residuals are **stationary**: the series ARE cointegrated — regression is valid
   - If residuals have a **unit root**: not cointegrated — regression is spurious

**Real-world finance example:** A company's quarterly sales and national GDP — both grow over decades (unit roots), but they're tied together by the economy. If cointegrated, you can build a valid model showing how GDP drives that company's long-term growth trajectory, even though both series independently wander.

Another classic: **pairs trading** — two stocks in the same industry may both have unit roots individually, but their *spread* (price ratio) is stationary. Traders exploit deviations from this equilibrium.

---

## Time-Series Model Selection: The Decision Tree

```
Start: New time series to model
          │
          ▼
    Is the series stationary?
    (Visual test + Dickey-Fuller)
          │
    ┌─────┴──────┐
    │ Yes        │ No (unit root)
    │            ▼
    │    First-difference the series
    │    (Then proceed with stationary series)
    │
    ▼
Does the series have a clear trend?
          │
    ┌─────┴──────┐
    │ Yes        │ No
    ▼            ▼
Trend model   Does it correlate with its own past?
(linear or    (Check autocorrelations)
log-linear)         │
                    ▼
              AR(p) model
              (Choose p based on residual autocorrelations)
                    │
                    ▼
              Check residuals for ARCH
              (If volatility clustering → use ARCH model)
```

---

## Exam Traps

> [!danger] Common Mistakes
> - **[[Stationary|Stationary]] vs. non-[[Stationary|stationary]]**: Know the three conditions (constant mean, variance, [[Autocorrelation|autocorrelation]])
> - **[[Unit root|Unit root]] null [[Hypothesis|hypothesis]]**: $H_0$ is non-stationarity — *rejecting* $H_0$ means the series IS [[Stationary|stationary]]
> - **Spurious regression**: Two unit-root series can have high R² without any real relationship — must test for [[Cointegration|cointegration]] first
> - **Chain rule**: Multi-period AR forecasts converge toward the long-run mean — not toward infinity
> - **ARCH vs. [[Heteroskedasticity|heteroskedasticity]]**: ARCH is *time-conditional* (today's variance depends on past errors); regular [[Heteroskedasticity|heteroskedasticity]] is *cross-sectional* (variance depends on X values)
> - **Log-linear vs. [[Linear trend|linear trend]]**: Choose based on whether growth is in absolute amounts (linear) or percentage rates (log-linear)

---

## Related Concepts

- [[Multiple Regression - Basics and Assumptions]] — the cross-sectional counterpart
- [[Model Misspecification]] — [[Serial Correlation|serial correlation]] and [[Heteroskedasticity|heteroskedasticity]] in OLS
- [[Stationarity]] — the key requirement for AR models
- [[Dickey-Fuller Test]] — testing for unit roots
- [[Random walk]] — the [[Unit root|unit root]] special case
- [[Cointegration]] — valid regression between non-[[Stationary|stationary]] series
- [[ARCH]] — time-varying [[Volatility|volatility]] models
- [[Machine Learning]] — modern alternatives to classical time-series models
