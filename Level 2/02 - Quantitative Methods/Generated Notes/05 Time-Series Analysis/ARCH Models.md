---
title: ARCH Models
subject: 02 - Quantitative Methods
tags: [CFA-L2, time-series, volatility, ARCH, GARCH, heteroscedasticity, risk-management]
aliases: [ARCH, ARCH(1), ARCH(p), Autoregressive Conditional Heteroskedasticity, conditional volatility model]
---

# ARCH Models

## The Real-World Analogy

Think about the weather forecasts on the news. A meteorologist doesn't just tell you tomorrow's expected temperature — they also tell you the *uncertainty* around that forecast. On a calm summer day, the prediction is "78°F, give or take 2°." But on a day where a storm front is colliding with a heat wave, it's "78°F, give or take 15°." Same expected temperature; **wildly different risk**.

Now think about the stock market in 2008. The Lehman Brothers collapse on September 15 didn't just move prices — it announced *that markets had become much riskier*. The day's volatility was high, and crucially, the *next* day's volatility was also high, and so on for months. Storms in financial markets cluster, just like weather storms. Calm follows calm; turbulence follows turbulence.

That's the entire intuition of ARCH models. A regular regression assumes the size of random shocks ("how big is the typical wobble") is the same in every period — a constant. ARCH says: **No — the size of the wobble itself changes over time, in a predictable way.** Specifically, a big shock yesterday means we should expect a big wobble today. ARCH is a model not of the *level* of the data, but of the *risk* in the data.

---

## The Motivation — Why Constant Variance Fails for Returns

### The textbook assumption: homoscedasticity

Standard OLS regression — and the AR(1) you've already studied — assumes the error term has constant variance:

$$\text{Var}(\varepsilon_t) = \sigma^2 \quad \text{for all } t$$

This is **homoscedasticity** (see [[Homoscedasticity and Heteroscedasticity]]). Every t-statistic, p-value, and confidence interval the regression outputs depends on this assumption being approximately true.

### The reality: volatility clustering

In financial returns — stock prices, exchange rates, interest rates, commodity prices — this assumption fails dramatically. Plot daily returns of the S&P 500 over 30 years and you'll see:

- **Calm periods** of small daily moves clustered together (e.g., 2003–2007).
- **Turbulent periods** of huge swings clustered together (e.g., 2008–2009, March 2020).
- The transition between regimes is gradual, not random.

This phenomenon — large changes followed by more large changes, calm by more calm — is called **volatility clustering**, and it was first documented by Mandelbrot in 1963. It's one of the most robust empirical regularities in finance.

```
Daily returns of a typical equity index:

|   |||  | |||  ||||  |
| ||| | || |||| | |  ||||||| ← calm period (small bars)
|—————————————————————————|—— time
                          ↓
                        SHOCK
                          ↓
| ||| | ||| ||||| ||||||||| ← turbulent period (big bars)
|       large bars cluster after the shock
```

The bars don't have constant size. If you fit an OLS regression assuming they do, your standard errors are wrong, and every inference flowing from them is contaminated. **You cannot trust the t-stats.**

### Why this matters for an investor

A model that assumes constant variance reports a single risk number for every period — say, "this asset has a daily volatility of 1.2%." That's an *average*. In real markets, that average masks 0.4% volatility most of the time and 4% volatility during crises. A risk manager using the average will radically underestimate downside in turbulent regimes — exactly when accurate risk numbers matter most.

ARCH was designed to fix this. It produces a **time-varying variance** that responds to recent market conditions, so the risk number you report tomorrow reflects the risk environment we're actually in tomorrow.

---

## The Formal ARCH(1) Specification

ARCH stands for **A**uto**R**egressive **C**onditional **H**eteroskedasticity. Decoded:

| Word | Meaning |
|------|---------|
| **Autoregressive** | The variance depends on its own past (specifically, past squared shocks) |
| **Conditional** | "Conditional on the information up to time $t-1$" — i.e., a forecast variance, not a long-run average |
| **Heteroskedasticity** | Variance changes over time (the opposite of constant-variance) |

### The model

The ARCH(1) model is applied to the residuals $\varepsilon_t$ from some prior model — typically an AR(1) or other regression. The conditional variance of those residuals is modeled as:

$$\boxed{\sigma_t^2 = a_0 + a_1 \varepsilon_{t-1}^2}$$

Reading the equation:

| Term | Meaning |
|------|---------|
| $\sigma_t^2$ | Today's conditional variance — i.e., the *forecast* of how big the squared shock will be at time $t$, given what we knew at time $t-1$ |
| $a_0$ | Baseline (long-run-floor) variance — a constant; the variance you'd expect if no recent shocks had occurred |
| $a_1$ | Volatility persistence — how strongly yesterday's squared shock translates into today's variance |
| $\varepsilon_{t-1}^2$ | Yesterday's squared residual from the underlying mean model — the most recent observed "shock" |

The full system has two equations stacked:

1. **Mean equation** (typically an AR(1) or regression): $x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$
2. **Variance equation** (the ARCH part): $\sigma_t^2 = a_0 + a_1 \varepsilon_{t-1}^2$

The $\varepsilon_t$ that appears in the variance equation is the residual *from* the mean equation. So you fit ARCH in two stages: first estimate the mean equation, then model the variance of its residuals.

### Why squared residuals?

Variance is by definition the expected squared deviation from the mean. The residuals $\varepsilon_t$ already have mean zero (by construction of the regression), so $E[\varepsilon_t^2] = \text{Var}(\varepsilon_t)$. Squaring also strips off the sign — what matters for risk is *magnitude*, not direction. A −5% return and a +5% return contribute equally to volatility.

### Constraints on the parameters

For the ARCH(1) to be a valid, well-behaved model, three conditions must hold:

| Constraint | Why |
|------------|-----|
| $a_0 > 0$ | Variance must be positive. If $a_0 \le 0$ and yesterday was calm ($\varepsilon_{t-1}^2 \approx 0$), the model would predict zero or negative variance, which is nonsense. |
| $a_1 \geq 0$ | Past shocks must have a *non-negative* effect on current variance. A negative $a_1$ would mean "big shocks yesterday → smaller risk today," contradicting volatility clustering. |
| $a_1 < 1$ | Stationarity. If $a_1 \geq 1$, a single shock keeps amplifying — variance explodes toward infinity over time. This is the ARCH analog of a [[Unit root]]. |

The unconditional (long-run) variance, when $a_1 < 1$, is:

$$\bar{\sigma}^2 = \frac{a_0}{1 - a_1}$$

Notice the resemblance to the mean-reverting level $b_0/(1-b_1)$ in an AR(1). The same algebraic structure appears: a constant divided by one minus a "persistence" coefficient. This is the variance the model gravitates toward in the long run, when temporary shocks fade.

---

## ARCH vs. AR — Two Models, Two Jobs

This is the cleanest mental model: **AR** predicts the *level*, **ARCH** predicts the *risk*. They sit on top of each other.

| | AR Model | ARCH Model |
|---|----------|------------|
| What it forecasts | The next *value* of $x_t$ | The next *variance* of the residuals from the mean model |
| Equation | $x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$ | $\sigma_t^2 = a_0 + a_1 \varepsilon_{t-1}^2$ |
| Input | Past values of $x$ | Past squared residuals |
| Output | A point estimate (forecast value) | A variance forecast (risk) |
| Typical question answered | "What will inflation be next month?" | "How wide is the confidence band around that forecast?" |
| Stationarity condition | $\lvert b_1 \rvert < 1$ | $a_1 < 1$ (and $a_0 > 0$) |

Standard workflow:

1. Fit an AR(1) (or whatever mean model) to capture the dynamics in $x_t$.
2. Extract the residuals $\hat{\varepsilon}_t$.
3. Test whether those residuals show ARCH effects.
4. If yes, fit an ARCH model to them — and use the resulting $\sigma_t^2$ for risk forecasting.

---

## Testing for ARCH Effects — Three Steps

How do you know if your residuals have ARCH effects? You don't eyeball it; you test it formally with what's called the **Engle test** (after Robert Engle, who won the 2003 Nobel Prize in economics for inventing ARCH).

### Step 1 — Fit the mean model and save residuals

Run your AR(1) (or whatever) and store the residuals $\hat{\varepsilon}_t$.

### Step 2 — Run an auxiliary regression on squared residuals

Regress *squared* residuals on their own *one-period lag*:

$$\hat{\varepsilon}_t^2 = a_0 + a_1 \hat{\varepsilon}_{t-1}^2 + u_t$$

This is itself just an AR(1) — but on the squared residuals, not the original series. It asks: *does yesterday's squared shock predict today's squared shock?*

### Step 3 — t-test on $\hat{a}_1$

- $H_0: a_1 = 0$ — no ARCH effects; squared residuals are unrelated period to period; variance is constant.
- $H_a: a_1 \neq 0$ — ARCH effects exist; squared residuals are autocorrelated; variance changes over time.

Compute the t-statistic on $\hat{a}_1$ from the auxiliary regression output and compare to standard t critical values (typically ±1.96 at 5% in large samples).

| Decision | Conclusion |
|----------|------------|
| $\lvert t \rvert > 1.96$ → reject $H_0$ | ARCH effects present. Standard errors from the original mean model are unreliable. Use ARCH-aware methods. |
| $\lvert t \rvert \leq 1.96$ → fail to reject $H_0$ | No evidence of ARCH. The constant-variance assumption is okay; standard OLS results stand. |

The test is two-tailed because in principle $a_1$ could be negative (though in well-behaved financial data it's almost always positive — that's the whole point of volatility clustering).

---

## What Happens When ARCH Is Present

If you ignore ARCH effects and use standard OLS results from your mean model:

### The standard errors are wrong

OLS standard errors assume constant residual variance. With ARCH, that assumption fails — residuals have a smaller spread in calm periods and a larger spread in turbulent periods. The "average" standard error OLS computes is correct on average across the sample, but wrong for any specific period.

### Hypothesis tests become unreliable

Because t-statistics are coefficient divided by standard error, wrong standard errors mean wrong t-stats. You might:

- **Falsely reject** a true null — concluding a coefficient is "significant" when it isn't (a Type I error). The coefficient could be a "gold mine" you discovered that's actually just statistical noise.
- **Falsely fail to reject** a false null — missing a real effect because the inflated SE swamps a true coefficient.

### Forecast intervals are wrong

A 95% confidence interval for a forecast assumes a particular shape and width for the error distribution. If volatility is changing, the actual interval should be wider in turbulent periods and narrower in calm ones. OLS gives you one constant width — wrong in *both* regimes.

### The fix

Three options, in order of typical preference for the CFA curriculum:

1. **Use a generalized least squares (GLS) procedure** that explicitly weights observations by their estimated conditional variance. This produces correct standard errors when the variance structure is known.
2. **Use robust (heteroscedasticity-consistent) standard errors** — also called White or Huber-White errors. These give you correct standard errors without requiring you to model the variance structure. The point estimates from OLS are unchanged; only the SEs are.
3. **Model the variance directly with ARCH/GARCH** — and use the model's $\sigma_t^2$ to construct correct forecast intervals and risk numbers.

Which to pick depends on your goal: if you only need correct *inferences* on the regression coefficients, robust SEs are simplest. If you need a *forecast of risk itself*, you must build an ARCH model.

---

## Forecasting With ARCH

This is where ARCH earns its keep. Once you've fit the model, the one-step-ahead variance forecast is straightforward — you know $\hat{\varepsilon}_t^2$ today, and the model gives you tomorrow's variance:

$$\hat{\sigma}_{t+1}^2 = \hat{a}_0 + \hat{a}_1 \hat{\varepsilon}_t^2$$

Applications:

### Value-at-Risk (VaR)

VaR asks: *what is the worst loss I can expect over the next day, with 95% confidence?* The standard formula assumes a return distribution with mean $\mu$ and standard deviation $\sigma$:

$$\text{VaR}_{95\%} = \mu - 1.645 \cdot \sigma$$

Plug in $\sigma_{t+1}$ from the ARCH forecast instead of a static historical $\sigma$, and you get a **time-varying VaR** that widens during turbulent periods and tightens during calm ones — much more useful for actual risk management.

### Option pricing

The Black-Scholes formula takes volatility as an input. In real markets, volatility isn't constant — option dealers use ARCH/GARCH-style forecasts to estimate the volatility input dynamically. Periods of high recent shocks → higher implied vol → more expensive options. ARCH formalizes this intuition.

### Capital allocation and stress testing

Banks compute regulatory capital requirements based on forecast risk exposure. ARCH-style models let them update those numbers daily based on recent market conditions, instead of relying on a single historical estimate.

### Multi-step variance forecasts

For an ARCH(1), iterating forward:

$$\hat{\sigma}_{t+k}^2 = \hat{a}_0 (1 + a_1 + a_1^2 + \cdots + a_1^{k-1}) + a_1^k \hat{\varepsilon}_t^2$$

As $k \to \infty$, the forecast converges to the unconditional variance $\bar{\sigma}^2 = a_0/(1-a_1)$ — assuming $a_1 < 1$. So long-horizon variance forecasts revert to the long-run mean, just like long-horizon AR forecasts revert to the mean-reverting level.

---

## Generalizations — ARCH(p) and GARCH

### ARCH(p)

The natural extension: include $p$ lagged squared residuals.

$$\sigma_t^2 = a_0 + a_1 \varepsilon_{t-1}^2 + a_2 \varepsilon_{t-2}^2 + \cdots + a_p \varepsilon_{t-p}^2$$

In practice, fitting ARCH(p) for moderate $p$ requires estimating many parameters and often suffers from instability. That motivated the next innovation.

### GARCH — Generalized ARCH

In 1986, Tim Bollerslev (Engle's student) introduced the **G**eneralized **ARCH** model. The most common form is GARCH(1,1):

$$\sigma_t^2 = a_0 + a_1 \varepsilon_{t-1}^2 + \beta \sigma_{t-1}^2$$

Reading: today's variance depends on yesterday's *shock* (the ARCH term) **plus** yesterday's *variance itself* (the GARCH term). This is a much more parsimonious way of capturing long memory in volatility. With just three parameters ($a_0, a_1, \beta$), GARCH(1,1) often fits financial data better than an ARCH(p) with $p = 5$ or more.

The stationarity condition becomes $a_1 + \beta < 1$, and the unconditional variance is $a_0 / (1 - a_1 - \beta)$.

GARCH is the workhorse model used by professional risk managers, but for CFA Level 2 you only need to know:

- It exists and generalizes ARCH.
- It adds a lagged variance term.
- It's preferred in practice for being more compact and stable.

---

## Why This Connects to Real Market Behavior

ARCH explains two famous empirical features of financial markets that the standard normal distribution cannot:

### Fat tails (excess kurtosis)

Daily stock returns have far more "extreme" days than a normal distribution predicts. A normal model says a 5-sigma down day should occur once every several million years. In practice, equity markets see one every few decades — roughly a million times more often than the normal predicts.

ARCH partially explains this. Even if shocks $\varepsilon_t$ are conditionally normal *given* the current variance $\sigma_t^2$, the *unconditional* distribution (mixing over all the different $\sigma_t^2$ values that occur over time) has fatter tails. Periods of high variance produce extreme observations far more often than a single-volatility model would predict.

### Volatility persistence

Once a market gets "scared" (think March 2020, October 2008), the fear doesn't dissipate overnight. Volatility stays elevated for weeks or months. ARCH parameters $a_1$ (and $\beta$ in GARCH) measure exactly how persistent the fear is. Empirically, $a_1 + \beta$ is often close to 0.99 in financial data — meaning shocks decay extremely slowly.

### What ARCH does NOT explain

- **Asymmetry (leverage effect):** Negative shocks raise volatility more than positive shocks of equal size. Plain ARCH treats $\varepsilon_{t-1}^2$ symmetrically — it doesn't care about the sign. Variants like EGARCH and GJR-GARCH add asymmetry.
- **Long memory beyond what ARCH(p) or GARCH can capture.** Some series show even slower volatility decay than GARCH allows; FIGARCH and similar models address this.

These extensions are out of CFA scope but worth knowing exist.

---

## Worked Numerical Example

An analyst is modeling monthly inflation rates. They have already fit an AR(1) to the inflation series and saved the residuals. Now they want to know: do these residuals show ARCH effects?

### Step 1 — The setup

The analyst has 100+ months of inflation residuals. From the auxiliary regression of squared residuals on lagged squared residuals:

$$\hat{\varepsilon}_t^2 = a_0 + a_1 \hat{\varepsilon}_{t-1}^2 + u_t$$

The OLS output gives:

| Coefficient | Estimate | Standard Error | t-statistic |
|-------------|----------|----------------|-------------|
| $\hat{a}_0$ | 6.3626 | 1.40 | 4.54 |
| $\hat{a}_1$ | 0.2754 | 0.057 | **4.83** |

### Step 2 — Test for ARCH effects

| Hypothesis | Statement |
|-----------|-----------|
| $H_0$ | $a_1 = 0$ (no ARCH; constant variance) |
| $H_a$ | $a_1 \neq 0$ (ARCH effects present) |

The t-statistic on $\hat{a}_1$ is 4.83. Compare to the two-tailed 5% critical value of ±1.96.

$$|4.83| > 1.96 \quad \Rightarrow \quad \text{Reject } H_0$$

**Conclusion:** ARCH effects are clearly present. The variance of the residuals is not constant — it depends systematically on the size of the previous month's shock.

### Step 3 — What the result means

- The original AR(1) model's standard errors are unreliable. Any t-tests on the slope coefficient $b_1$ in that AR(1) need to be recomputed with robust standard errors before they can be trusted.
- The analyst can use the fitted ARCH(1) parameters to forecast next-month variance.

### Step 4 — Forecast next-period variance

Suppose the most recent observed squared residual is $\hat{\varepsilon}_t^2 = 1.0$ (a small shock). The variance forecast for next month is:

$$\hat{\sigma}_{t+1}^2 = 6.3626 + 0.2754 \cdot 1.0 = \mathbf{6.6380}$$

### Step 5 — What if the latest shock had been large?

Suppose instead $\hat{\varepsilon}_t^2 = 9.0$ (a 3-unit shock):

$$\hat{\sigma}_{t+1}^2 = 6.3626 + 0.2754 \cdot 9.0 = 6.3626 + 2.479 = \mathbf{8.8413}$$

The forecast variance jumps by about 33%. **That's volatility clustering in action** — the same model, but a bigger recent shock translates into a bigger forecast risk.

### Step 6 — Long-run variance

The unconditional variance, the level the model gravitates to in calm conditions:

$$\bar{\sigma}^2 = \frac{a_0}{1 - a_1} = \frac{6.3626}{1 - 0.2754} = \frac{6.3626}{0.7246} = \mathbf{8.78}$$

So in the long run, expect monthly squared residuals to average around 8.78. After any shock, the variance forecast decays geometrically (factor $a_1 = 0.2754$ each period) back toward this 8.78 floor.

### Step 7 — Two-period-ahead forecast

Using the chain rule of forecasting:

$$\hat{\sigma}_{t+2}^2 = a_0 + a_1 \hat{\sigma}_{t+1}^2$$

(After the next period, we don't have an actual residual to plug in; we use the forecast variance instead, since $E[\varepsilon_{t+1}^2] = \sigma_{t+1}^2$.)

Starting from $\hat{\sigma}_{t+1}^2 = 6.6380$ (low-shock scenario):

$$\hat{\sigma}_{t+2}^2 = 6.3626 + 0.2754 \cdot 6.6380 = 6.3626 + 1.828 = 8.191$$

Already moving back toward the long-run 8.78.

### Visual summary

```
σ²
 |     ●  ← post-shock spike (ε² = 9 → forecast 8.84)
8|________________________●═══════════════════ ← long-run var = 8.78
 |       \                ↑
 |        \              decay back to 8.78
7|_________●─────────────────────── (post-small-shock forecast = 6.64)
 |          \
 |           \____ slow upward drift toward 8.78
 |
 +─────────────────────────────────────► time
   t   t+1   t+2  ...
```

---

## Common Pitfalls

| Pitfall | Why It Bites |
|---------|--------------|
| Skipping the ARCH test before reporting standard errors | If ARCH is present, all your t-stats and p-values are wrong. The test takes one regression — always run it. |
| Forgetting to use **squared** residuals | Regressing $\hat{\varepsilon}_t$ on $\hat{\varepsilon}_{t-1}$ tests serial correlation, not ARCH. The squaring is the whole point — it strips off sign and detects volatility clustering. |
| Confusing ARCH with serial correlation | Serial correlation is autocorrelation in the *levels* of residuals; ARCH is autocorrelation in the *squared* residuals. Different tests, different remedies. |
| Ignoring stationarity constraint $a_1 < 1$ | If your fit gives $\hat{a}_1 > 1$, the model is explosive — you can't use it for forecasting. Re-specify (often switching to GARCH solves it). |
| Reporting a single VaR in turbulent markets | Without ARCH, VaR is a constant. Real markets vary risk by an order of magnitude across regimes. Time-varying $\sigma_t^2$ matters most exactly when risk is highest. |
| Applying ARCH directly to non-stationary returns | ARCH assumes a stationary mean equation; if the underlying series has a [[Unit root]], difference it first. |

---

## Connections

- [[Homoscedasticity and Heteroscedasticity]] — the constant-variance assumption ARCH relaxes
- [[AR(1) Model]] — the typical mean model whose residuals get fed into ARCH
- [[Covariance stationary]] — ARCH stationarity ($a_1 < 1$) is the variance-equation analog
- [[Unit root]] — the level-equation analog of $a_1 = 1$
- [[Serial Correlation]] — autocorrelation in residuals (compare with autocorrelation in *squared* residuals = ARCH)
- [[Hypothesis Testing in Regression]] — the framework for the t-test on $\hat{a}_1$
- [[Level 2/Generated Notes/02 - Quantitative Methods/Spurious Correlation]] — what wrong standard errors can produce
- [[P-Value]] — used to interpret ARCH test output
- [[Studentized Residuals]] — diagnostics on regression residuals

---

## LOS Coverage

This note supports the Time-Series Analysis LOS:

- **Explain** how to test and correct for heteroscedasticity in time-series regression residuals.
- **Describe** the structure of an ARCH(1) model and its parameters.
- **Test** whether a time series has ARCH errors using an auxiliary regression on squared residuals.
- **Calculate** and **interpret** a one-period-ahead variance forecast using ARCH(1).
- **Discuss** the practical consequences of ARCH effects (unreliable standard errors, fat tails, volatility persistence) and the appropriate fixes (GLS, robust SEs, GARCH).
