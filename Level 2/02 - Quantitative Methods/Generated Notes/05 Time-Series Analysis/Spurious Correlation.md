---
title: Spurious Correlation
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, time-series, diagnostics, stationarity]
aliases: [Spurious Regression, Nonsense Correlation, Granger-Newbold Problem]
---

# Spurious Correlation

## The Real-World Analogy First

Two people, Alice and Bob, live in different cities and have never met. Alice leaves her house at 8:00 AM every weekday to catch her bus. Bob leaves his house at 8:00 AM every weekday to walk his dog. If you recorded a year of their departure times and ran a correlation, you'd get something close to **+1.0**.

A naïve analyst might conclude Alice's movements *cause* Bob's — maybe they're sending secret signals. In reality, they're both responding to the same **lurking third factor**: the workday starts at 9:00, and the sun rises on a schedule. The correlation is real in the data, but the causal story is empty. The number on the screen is telling you absolutely nothing about Alice and Bob's actual relationship.

That's **spurious correlation** — a numerically high, statistically "significant" relationship between two variables that are, in reality, unrelated in any meaningful or causal way. The math isn't broken; it's just being *tricked*. And in finance — where we make portfolio decisions based on reported t-stats and $R^2$'s — getting fooled by spurious correlation is how real money gets lost.

---

## Precise Definition

A correlation (or regression coefficient) is **spurious** when it is numerically large and statistically significant by OLS's usual criteria, yet does not reflect a genuine economic or causal relationship between the variables. The "significance" is a statistical artifact — not a real signal.

Three common sources produce spurious results:

1. **Pure chance (data mining)** — test enough variable pairs and some will look strongly correlated by coincidence.
2. **A confounding lurking variable** — both variables are driven by a hidden third factor.
3. **Non-stationary time series (the CFA-favorite case)** — two random walks regressed on each other will produce misleadingly high $R^2$ and inflated t-stats even when totally unrelated.

The CFA exam focuses heavily on source (3). It's the one where a careful analyst with the right tools can systematically detect and avoid the trap — which makes it testable.

---

## The Three Classic Flavors

### Flavor A — Pure Chance (Data Mining)

If you mine a dataset of 10,000 random variables against each other, pure probability guarantees some pairs will show $|r| > 0.9$. The web is full of infamous examples: the U.S. per-capita consumption of cheese is highly correlated with the number of people who die tangled in bedsheets. The math is correct. The relationship is nonsense.

**The lesson:** statistical significance is *cheap* when the researcher gets many tries. This is why CFA coursework emphasizes **pre-specifying hypotheses** based on economic theory before testing.

### Flavor B — Confounding Variable

Two variables $X$ and $Y$ look correlated because a hidden third variable $Z$ drives both.

- Ice-cream sales and drowning deaths both spike in July. Neither causes the other — *summer heat* causes both.
- A firm's advertising spend correlates with its stock return — but both are driven by *overall revenue growth*.

Formally: $\text{Corr}(X, Y) > 0$ because $\text{Corr}(X, Z) > 0$ and $\text{Corr}(Y, Z) > 0$. Control for $Z$ in a multiple regression and the apparent $X \leftrightarrow Y$ link collapses.

**The lesson:** univariate correlations are dangerous. Multivariate regression with carefully chosen controls is the proper tool.

### Flavor C — Spurious Regression Between Non-Stationary Time Series

This is **the** CFA case. It has a precise name, a precise mechanism, and a precise fix. It deserves its own section.

---

## The CFA Headline Case — Spurious Regression Between Unit-Root Series

In 1974, Clive Granger and Paul Newbold published a result that shook econometrics. They simulated pairs of **independent random walks** — series with unit roots, drawn from completely unrelated data-generating processes — and regressed one on the other. The results were disturbing:

- $R^2$ routinely exceeded 0.7 — often 0.9+.
- t-statistics on the slope routinely exceeded the usual 95% critical value.
- A naïve analyst running the standard OLS output would declare a "strong, significant relationship" — when by construction there was none.

This is the **Granger–Newbold spurious regression problem**, and it's the mechanical reason every time-series regression in the CFA curriculum starts with a stationarity check.

### Why Mechanically Does This Happen?

OLS is only a valid procedure when one of its core assumptions holds: the residuals $\varepsilon_t$ are **covariance stationary** — mean zero, constant variance, no trend. That assumption implicitly requires $Y_t$ and $X_t$ to *not* be trending in ways the errors can't absorb.

A **[[Random Walk|random walk]]** is the canonical non-stationary process:

$$Y_t = Y_{t-1} + \epsilon_t$$

It has a unit root ($b_1 = 1$ when you regress $Y_t$ on $Y_{t-1}$), no mean-reversion, and a variance that **grows without bound** as $t$ increases. When you regress one random walk on another:

$$Y_t = b_0 + b_1 X_t + \varepsilon_t$$

the residual $\varepsilon_t = Y_t - b_0 - b_1 X_t$ is itself non-stationary — it inherits the unbounded-variance behavior of $Y_t$ and $X_t$. The classical OLS formulas for standard errors assume a stationary residual, so:

- The SE formula is applied to the wrong object → SEs are drastically **underestimated**.
- t-stats become wildly inflated.
- $R^2$ is also inflated because two trending series will share whatever their trends happened to do, boosting explained variation mechanically.

The regression output *looks* beautiful. It is beautiful in the same way a mirage looks like water — the signal you think you see is a geometric coincidence of two wandering paths, not a real relationship.

### The Output Trap Visualized

What a spurious regression report looks like vs. what it actually is:

| Diagnostic | What the OLS Output Shows | What's Really True |
|---|---|---|
| $R^2$ | 0.92 — "nearly deterministic" | Inflated; two independent walks "looked" related by accident |
| t-stat on $b_1$ | 7.3 — "highly significant" | SE underestimated → t bloated |
| p-value | 0.0000 — "overwhelming evidence" | Meaningless; based on a wrong null distribution |
| Durbin-Watson | ~0.2 — ⚠️ red flag | Residuals are non-stationary, *not* just autocorrelated |
| True economic link | — | **None** |

The **Durbin-Watson is the canary**: in a spurious regression between two random walks, DW is near zero because the residuals themselves wander like a random walk. A classic diagnostic check: **if $R^2 > DW$, suspect spurious regression.**

---

## How to Detect and Prevent Spurious Regression

The CFA curriculum lays out a specific detection-and-correction workflow. Learn it cold — it is testable verbatim.

### Step 1 — Test each series for a unit root using the Dickey–Fuller (DF) test

Rewrite the autoregression of $X_t$ on $X_{t-1}$ in difference form:

$$X_t - X_{t-1} = b_0 + (b_1 - 1) X_{t-1} + \varepsilon_t$$

Define $g_1 = b_1 - 1$. The hypotheses are:

- $H_0$: $g_1 = 0$ (i.e., $b_1 = 1$, unit root present, non-stationary)
- $H_a$: $g_1 < 0$ (i.e., $b_1 < 1$, no unit root, stationary)

Run OLS and use the **Dickey–Fuller** critical values (not the standard t-table — under the null, the statistic isn't t-distributed). If you fail to reject, the series has a unit root.

### Step 2 — First-difference to induce stationarity

If $X_t$ has a unit root, work with:

$$\Delta X_t = X_t - X_{t-1}$$

For a random walk, $\Delta X_t = \epsilon_t$ — white noise, which is covariance stationary by definition. Regress **changes on changes**, not levels on levels:

$$\Delta Y_t = b_0 + b_1 \Delta X_t + \varepsilon_t$$

This regression is statistically valid because both sides are stationary. The Granger–Newbold trap is disarmed.

### Step 3 — If both series have unit roots, test for cointegration

Sometimes two unit-root series are truly linked by a long-run equilibrium relationship (e.g., short-term and long-term interest rates; two stocks in a pairs trade). They're each random walks, but the **difference** between them is stationary. That's called **[[Cointegration|cointegration]]**, and it's detected with the **Engle–Granger test**:

1. Regress $Y_t$ on $X_t$ in levels.
2. Take the residuals $\hat{\varepsilon}_t$.
3. Run a Dickey–Fuller test on the residuals.
4. If DF rejects (residuals are stationary), the two series are cointegrated, and the level regression is **not spurious** — it's capturing a real long-run relationship.

So the decision tree is:

```
Both series have unit roots?
        │
        ▼
  Are they cointegrated (Engle–Granger DF on residuals rejects)?
        │
   ┌────┴────┐
   ▼         ▼
  YES       NO
   │         │
   ▼         ▼
Level      First-difference
regression both series and
is valid   regress Δ on Δ
```

---

## Worked Conceptual Example — The JPY/USD Exchange Rate

An analyst wants to forecast the JPY/USD exchange rate using an AR(1) model:

$$\text{JPY/USD}_t = b_0 + b_1 \cdot \text{JPY/USD}_{t-1} + \varepsilon_t$$

### The Tempting Output

OLS on monthly levels over a 10-year sample gives:

- $R^2 = 0.9897$
- $b_1 = 0.9985$, with $t = 120.4$, $p < 0.0001$
- Durbin-Watson $\approx$ 2.0

The analyst writes up a report claiming to explain 99% of JPY/USD movement. The compliance officer should fire them.

### The Problem

The JPY/USD rate is a **random walk** — it has a unit root. The Dickey–Fuller test on the series fails to reject the null of a unit root. The apparent model fit is a classic Granger–Newbold artifact: $b_1$ is close to 1 *because the process is a random walk*. The $R^2 = 0.99$ just means today's exchange rate is close to yesterday's — which is tautologically true for any near-random-walk series.

### The Fix — First Difference

Re-run the regression on the **change** in the exchange rate:

$$\Delta (\text{JPY/USD})_t = b_0 + b_1 \cdot \Delta (\text{JPY/USD})_{t-1} + \varepsilon_t$$

The new output:

- $R^2 = 0.0008$
- $b_1$ not statistically different from 0
- Residuals are stationary → model is valid

### The Conclusion

The **real** economic content is in the second regression: month-to-month *changes* in JPY/USD are essentially **unpredictable from past changes**. The original 0.9897 $R^2$ was purely spurious — a statistical mirage caused by regressing one non-stationary series on another. The honest answer — "we can't predict it" — is less marketable but correct.

**Lesson:** high $R^2$ on time-series levels is *prima facie* suspicious. Always run DF on each series before trusting the fit.

---

## The $R^2$ vs. DW Quick Check

One of the most practical red-flag heuristics on the exam:

> If you see $R^2 > DW$ in a time-series regression, suspect spurious regression.

Why? Because in a genuine regression with white-noise residuals, DW should be near 2 and $R^2$ rarely exceeds 0.9. When two random walks are regressed, residuals wander (DW near 0) and the mechanical fit is absurdly high (R² near 1). The inequality $R^2 > DW$ is a fingerprint of the pathology.

---

## Spurious Correlation vs. Other Regression Problems

Easy to confuse spurious correlation with other regression diagnostics. The distinction:

| Problem | Source | Effect on OLS | Primary Fix |
|---|---|---|---|
| **Spurious regression** | Non-stationary series | Inflated $R^2$, inflated t-stats, coefficients meaningless | First-difference; test cointegration |
| **[[Serial Correlation]]** | Correlated residuals | Coefficients unbiased*, SEs too small | Newey-West HAC SEs |
| **[[Homoscedasticity and Heteroscedasticity\|Conditional heteroskedasticity]]** | Variance depends on $X$ | Coefficients unbiased, SEs too small | White (robust) SEs |
| **[[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]** | $X$'s correlated with each other | Coefficients unstable, SEs too **large** | Drop/combine variables |
| **Confounding bias** | Omitted common cause of $X$ and $Y$ | Coefficients *biased* | Include the confounder |

\* Except in AR models, where serial correlation biases coefficients.

**The signature of spurious regression** is the *combination* of high $R^2$, inflated t-stats, and a low Durbin-Watson on time-series levels data. The other diagnostics leave coefficients unbiased; spurious regression produces coefficients that are fundamentally meaningless.

---

## Memory Hooks

- **Alice & Bob leaving at 8 AM** — spurious correlation is a relationship created by an unmodeled common driver, not by a causal link between the two variables.
- **"Random walks tell tall tales"** — two independent unit-root series will fake a significant relationship nearly every time.
- **$R^2 > DW$** — if you see this, suspect spurious regression first, debug second.
- **DF then difference** — always test for unit roots (Dickey–Fuller) before regressing levels. If non-stationary, first-difference.
- **Cointegration = real leash** — two random walks can have a genuine relationship if their *difference* is stationary.
- **Granger–Newbold name-drop** — the 1974 result that formalized the spurious regression trap.

---

## CFA LOS Coverage

This note discharges the following CFA Level 2 Learning Outcome Statements:

| LOS | Verb | Covered By |
|---|---|---|
| **Quant LOS 5.g** — *describe random walk processes and contrast them to covariance stationary processes* | **describe** | "Why Mechanically Does This Happen?" and "Worked Example" sections |
| **Quant LOS 5.h** — *describe implications of unit roots for time-series analysis, explain when unit roots are likely to occur and how to test for them* | **describe / explain** | "How to Detect and Prevent" — Dickey–Fuller procedure |
| **Quant LOS 5.k** — *explain how time-series variables should be analyzed for nonstationarity and/or cointegration before use in a linear regression* | **explain** | "Step 3 — Cointegration" and decision tree |

After reading, you should be able to **define** spurious correlation, **explain** the Granger–Newbold mechanism, **describe** the Dickey–Fuller and Engle–Granger tests, **identify** the $R^2 > DW$ red flag, and **recommend** first-differencing or cointegration analysis as the appropriate fix.

---

## CFA Exam Focus

1. **Definition**: statistically significant relationship without a real economic link.
2. **Three sources**: chance, confounding variable, non-stationary time series.
3. **Granger–Newbold**: two independent random walks produce inflated $R^2$ and t-stats.
4. **Mechanism**: OLS SEs assume stationary residuals; when residuals are non-stationary, SEs are wildly underestimated.
5. **Detection**: Dickey–Fuller test for unit roots on each series; also watch for $R^2 > DW$.
6. **Fix**: first-difference both series, or test for cointegration (Engle–Granger) if both have unit roots.

---

## Related Notes

[[Serial Correlation]] · [[Homoscedasticity and Heteroscedasticity]] · [[Durbin-Watson Test]] · [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] · [[Time-Series Analysis]] · [[Covariance Stationarity]] · [[Random Walk]] · [[Unit Root]] · [[Dickey-Fuller Test]] · [[Cointegration]] · [[Engle-Granger Test]] · [[R-Squared and Adjusted R-Squared]] · [[Ordinary Least Squares]]
