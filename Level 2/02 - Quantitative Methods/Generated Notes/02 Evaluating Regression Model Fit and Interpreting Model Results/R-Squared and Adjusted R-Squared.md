---
title: R-Squared and Adjusted R-Squared
subject: Quantitative Methods
tags: [CFA-L2, QuantitativeMethods, Regression, MultipleRegression, GoodnessOfFit, RSquared, AdjustedRSquared, AIC, BIC, ModelSelection, CoefficientOfDetermination]
aliases: [R-Squared, R Squared, Adjusted R-Squared, Coefficient of Determination, R2, R^2, Adjusted R2]
---

# R-Squared and Adjusted R-Squared

> [!abstract] The One-Sentence Version
> **$R^2$** tells you the *fraction* of a dependent variable's wobble that your regression explains, and **$\bar{R}^2$ (adjusted $R^2$)** is the honest version that stops rewarding you for throwing in useless variables.

## The Analogy — The "Explained-Wobble" Scorecard

Imagine you're trying to predict how much a friend weighs on any given day. The daily weight bounces around — water retention, meals, workouts, you name it. That bouncing is the **total variation** in their weight.

Now you build a model: "weight = f(calories eaten, workout minutes)." How much of that daily bouncing does your model actually *capture*? If you nail 60% of the bouncing with your two predictors, $R^2 = 0.60$. If a total stranger's model hits 95%, they're explaining way more of the wobble.

But there's a catch. Suppose you add a silly variable — "number of socks they own." $R^2$ will *never go down*. It might even creep up by accident. That's the greedy behavior of plain $R^2$. **Adjusted $R^2$** is the same scorecard, but with a tax: every new variable has to justify its seat at the table, or adjusted $R^2$ will actually *fall*.

> [!tip] Memory Hook — **"Greedy vs. Honest"**
> $R^2$ is **greedy** (always grabs more when you add variables). $\bar{R}^2$ is **honest** (only goes up if the variable earns its keep).

---

## 1. The Foundation — Sum-of-Squares Decomposition

Before you can talk about $R^2$, you have to break apart the total variation of the dependent variable $Y$ into pieces. Given $n$ observations with mean $\bar Y$ and model predictions $\hat Y_i$:

| Component | Full name | Formula | Plain English |
|---|---|---|---|
| **SST** | Sum of Squares Total | $\displaystyle\sum_{i=1}^{n}(Y_i - \bar Y)^2$ | The **total wobble** — how much Y bounces around its own mean |
| **SSR** | Sum of Squares Regression (explained) | $\displaystyle\sum_{i=1}^{n}(\hat Y_i - \bar Y)^2$ | The **explained wobble** — variation the model accounts for |
| **SSE** | Sum of Squares Error (residual) | $\displaystyle\sum_{i=1}^{n}(Y_i - \hat Y_i)^2$ | The **unexplained wobble** — what the model missed |

> [!important] The Golden Identity
> $$\boxed{\;\mathrm{SST} \;=\; \mathrm{SSR} \;+\; \mathrm{SSE}\;}$$
>
> Total variation = Explained + Unexplained. This identity is what makes $R^2$ a meaningful *ratio*.

### Visual Layout

```
                ┌───────────────────────────────────────────┐
      SST   →   │ Total variation in Y around its mean      │
                └────────────────┬─────────────────┬────────┘
                                 │                 │
                                 ▼                 ▼
                       ┌──────────────┐   ┌──────────────────┐
                SSR →  │ Explained by │   │ Leftover / noise │ ← SSE
                       │ the model    │   │ (residuals²)     │
                       └──────────────┘   └──────────────────┘
```

> [!note] Jargon Decoded
> - **Residual** $e_i = Y_i - \hat Y_i$ — the vertical miss between actual and predicted.
> - **Degrees of freedom**: pieces of independent information available. SSE has $n - k - 1$ df (you burned $k+1$ df estimating the slopes and intercept). SST has $n-1$ df (one lost to the mean). SSR has $k$ df.

---

## 2. The $R^2$ Formula — Two Equivalent Forms

$$
\boxed{\;R^2 \;=\; \frac{\mathrm{SSR}}{\mathrm{SST}} \;=\; 1 - \frac{\mathrm{SSE}}{\mathrm{SST}}\;}
$$

Both forms are identical thanks to the golden identity. Use whichever matches the numbers you have.

| Form | When to use |
|---|---|
| $R^2 = \dfrac{\mathrm{SSR}}{\mathrm{SST}}$ | When the ANOVA table gives you the explained sum of squares directly |
| $R^2 = 1 - \dfrac{\mathrm{SSE}}{\mathrm{SST}}$ | When you have residuals (SSE) in hand — very common in software output |

### Properties

- **Bounded**: $0 \le R^2 \le 1$ in OLS with an intercept.
- $R^2 = 0$: your model explains *nothing* — you might as well predict $\bar Y$ for every observation.
- $R^2 = 1$: your model fits every data point *perfectly* (usually a red flag — look for overfitting or a deterministic relationship).

---

## 3. Interpretation — "Proportion of Variance Explained"

If a regression of a stock's return on three macro factors gives $R^2 = 0.6155$, the interpretation is:

> "**Roughly 61.6% of the variation in the stock's returns is explained by the three macro factors** in the model; the remaining 38.4% is unexplained — idiosyncratic noise, omitted variables, or measurement error."

Important caveats:

- $R^2$ measures **fit**, not **truth**. A biased model can still have high $R^2$.
- $R^2$ says nothing about whether any *individual* coefficient is significant. For that, use the **t-statistic**. For the *overall* model significance, use the **F-statistic**.
- A "good" $R^2$ is context-dependent. In controlled physical experiments, $R^2 > 0.95$ is routine. In asset-pricing regressions on individual stocks, $R^2 = 0.30$ might be excellent.

---

## 4. The Simple-Regression Link — Where "R-Squared" Gets Its Name

In **simple linear regression** (one predictor $X$), there's a beautiful identity:

$$R^2 = r_{XY}^2$$

where $r_{XY}$ is the **Pearson correlation coefficient** between $X$ and $Y$.

That's why it's called "R-squared" — it literally is the square of the correlation. In **multiple** regression, this identity breaks down: $R^2$ becomes the squared correlation between $Y$ and its fitted values $\hat Y$, but there's no single "r" between multiple predictors and Y.

See: [[Correlation]] · [[Simple Linear Regression]]

---

## 5. The Flaw — $R^2$ Is Greedy

Here's the punchline that every L2 candidate must internalize:

> [!warning] The Greed Problem
> **Adding a new independent variable to a regression can never *decrease* $R^2$** — it can only increase or stay exactly the same, *even if the new variable is pure noise.*

**Why?** OLS picks the slope coefficients to *minimize* SSE. If you add a new regressor and set its slope to zero, you've reproduced the old model — so SSE can't be worse. In practice, OLS will find *some* non-zero slope that fits random noise in the sample, so SSE falls a tiny bit and $R^2$ rises.

This creates a dangerous incentive:
1. Analyst wants a high $R^2$.
2. Analyst keeps tossing variables into the model until $R^2$ looks impressive.
3. Model has fit the **noise** in this specific sample — not the underlying economic relationship.
4. Out-of-sample predictions are garbage.

This disease has a name: [[Overfitting]].

---

## 6. Adjusted $R^2$ — The Honest Version

Adjusted $R^2$ (written $\bar R^2$ or $R^2_{\text{adj}}$) fixes the greed by penalizing the degrees of freedom you burn when you add more regressors.

$$
\boxed{\;\bar R^2 \;=\; 1 - \left[\frac{n-1}{n-k-1}\,(1 - R^2)\right]\;}
$$

| Symbol | Meaning |
|---|---|
| $n$ | Sample size |
| $k$ | Number of independent variables (not counting the intercept) |
| $n-1$ | Degrees of freedom for SST |
| $n-k-1$ | Degrees of freedom for SSE (residual df) |

### Why the Penalty Works

The ratio $\dfrac{n-1}{n-k-1}$ is **always $\ge 1$** when you have at least one regressor ($k \ge 1$). As $k$ grows, the ratio grows, which *inflates* the "$1 - R^2$" term, which *lowers* the adjusted $R^2$. So for $\bar R^2$ to rise when you add a variable, the new variable must improve $R^2$ enough to **outweigh** that inflating penalty.

### The t-Stat Rule of Thumb (MEMORIZE)

> [!tip] The 1.0 Threshold
> When you add a single new regressor:
> - **$|t| > 1.0$** on the new variable → $\bar R^2$ **increases**
> - **$|t| < 1.0$** on the new variable → $\bar R^2$ **decreases**
> - **$|t| = 1.0$** exactly → $\bar R^2$ unchanged
>
> This is *much* weaker than the usual 1.96 significance threshold — so adjusted $R^2$ rising does **not** mean the new variable is statistically significant at the 5% level. It just means the variable carried *some* information.

### Properties (vs. plain $R^2$)

| Property | $R^2$ | $\bar R^2$ |
|---|---|---|
| Upper bound | 1 | 1 (usually lower in practice) |
| Lower bound | 0 | **Can be negative** (very bad fit with many regressors) |
| Behavior when adding a noisy variable | Weakly increases | Typically decreases |
| Good for comparing models with different $k$? | **No** — biased toward larger models | **Yes** — the intended use |

---

## 7. Worked Example — The "Useless Advertising Variable"

An analyst studies Return on Assets (ROA) for a company and compares two models.

### Inputs

Sample size: $n = 40$.

| Model | Regressors | $k$ | $R^2$ | $\bar R^2$ | New variable's t-stat |
|---|---|---|---|---|---|
| **1** | Capital Spending only | 1 | 0.8799 | 0.8768 | — |
| **2** | Capital Spending + Advertising | 2 | 0.8805 | 0.8740 | $-0.33$ |

### Step-by-Step Verification of Model 2

$$
\bar R^2_{\text{Model 2}} = 1 - \left[\frac{40-1}{40-2-1}\,(1-0.8805)\right] = 1 - \left[\frac{39}{37}\,(0.1195)\right]
$$

$$
= 1 - (1.0541)(0.1195) = 1 - 0.1260 = \mathbf{0.8740}
$$

### Interpretation

- Plain $R^2$ rose **0.8799 → 0.8805**: looks like progress, right? Wrong.
- Adjusted $R^2$ *fell* **0.8768 → 0.8740**: the advertising variable added less explanatory juice than the penalty for burning another degree of freedom.
- The advertising t-statistic is only $-0.33$, well below the **1.0 threshold**. That's exactly why $\bar R^2$ fell.

**Bottom line.** Plain $R^2$ said Model 2 was better. Adjusted $R^2$ correctly said **Model 1 is the better model** — fewer variables, comparable explanatory power, more parsimonious.

---

## 8. When to Use Which

| Situation | Use |
|---|---|
| Reporting how much variation a single model explains | $R^2$ |
| Interpretability for a lay reader | $R^2$ |
| Simple linear regression (1 predictor) with the correlation already known | $R^2 = r_{XY}^2$ |
| **Comparing two models with the same Y but different numbers of predictors** | $\bar R^2$ |
| Checking whether a new variable earned its place | $\bar R^2$ |
| Variable selection / stepwise regression decisions | $\bar R^2$ (or better: AIC/BIC) |

> [!tip] The Rule of Parsimony (Occam's Razor for regressions)
> Prefer the **simplest model that adequately explains the data.** Adjusted $R^2$ is the first tool you reach for when enforcing parsimony — but it's a weak penalty compared to AIC/BIC.

---

## 9. Limitations of Both $R^2$ and $\bar R^2$

| Limitation | What it means | What to do instead |
|---|---|---|
| Neither tests **individual coefficient significance** | High $R^2$ doesn't mean any single $\beta$ is reliably different from zero | Use **t-statistics** on each coefficient |
| Neither tests **overall model significance** | Adjusted $R^2$ can be high by chance in small samples | Use the **F-statistic** on the whole model |
| **Biased models can have high $R^2$** | Omitted-variable bias, wrong functional form — both can still produce impressive fit | Residual diagnostics; economic reasoning |
| **Low $R^2$ ≠ useless model** | In asset pricing, monthly-return regressions often have $R^2 < 0.05$ yet the coefficients are meaningful | Judge significance, not fit, for hypothesis testing |
| Adjusted $R^2$'s penalty is **weak** | The $|t|>1$ threshold lets in variables that are not significant at any conventional level | Use **AIC / BIC** for stricter selection |

---

## 10. AIC and BIC — The Stricter Alternatives

When adjusted $R^2$ isn't tough enough, analysts use information criteria. Both penalize complexity more aggressively than $\bar R^2$.

| Criterion | Formula (conceptual) | When preferred | Rule |
|---|---|---|---|
| **AIC** — Akaike Information Criterion | $n\ln(\mathrm{SSE}/n) + 2(k+1)$ | **Prediction / forecasting** — picks models that predict well out-of-sample | Lower AIC = better |
| **BIC** — Bayesian Information Criterion / Schwarz | $n\ln(\mathrm{SSE}/n) + \ln(n)\,(k+1)$ | **Description / best fit** — picks the most likely "true" model | Lower BIC = better |

**Key distinction to memorize:**
- BIC's penalty $\ln(n)$ exceeds AIC's penalty of 2 whenever $n > 7.39$ — i.e., **for any realistic sample, BIC penalizes extra variables more harshly than AIC.**
- **AIC** → better for **prediction**.
- **BIC** → better for identifying the **true underlying model**.

> [!tip] Memory Hook — **"A before B, prediction before belief"**
> **A**IC for **A**ccuracy of prediction. **B**IC for **B**elief about the true model. BIC's stiffer penalty ($\ln n > 2$) means it picks smaller models.

---

## 11. Quick-Reference Cheat Sheet

| Metric | Formula | Rises when you add noise? | Good for comparing models of different size? |
|---|---|---|---|
| $R^2$ | $1 - \mathrm{SSE}/\mathrm{SST}$ | **Yes — always** | ❌ No |
| $\bar R^2$ | $1 - \dfrac{n-1}{n-k-1}(1-R^2)$ | No — falls if $|t|<1$ | ✅ Yes (weak) |
| AIC | $n\ln(\mathrm{SSE}/n) + 2(k+1)$ | No | ✅ Yes (stronger) — prediction |
| BIC | $n\ln(\mathrm{SSE}/n) + \ln(n)(k+1)$ | No | ✅ Yes (strongest) — truth |

---

## 12. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Describe** the sum-of-squares decomposition $\mathrm{SST} = \mathrm{SSR} + \mathrm{SSE}$.
- [x] **Calculate** and **interpret** $R^2$ using both equivalent forms.
- [x] **Explain** why $R^2$ never decreases when a variable is added to a multiple regression.
- [x] **Calculate** adjusted $R^2$ given $n$, $k$, and $R^2$.
- [x] **Interpret** why adjusted $R^2$ can decrease when a useless regressor is added, and apply the $|t|>1$ rule.
- [x] **Compare** $R^2$ and adjusted $R^2$ for competing models and decide which is more parsimonious.
- [x] **Describe** the limitations of both $R^2$ and adjusted $R^2$ as goodness-of-fit measures.
- [x] **Distinguish** AIC from BIC, including when each is preferred.

---

## Related Notes

- [[Multiple Regression - Basics and Assumptions]] — setup, OLS estimation, assumptions
- [[Regression Model Fit and Interpretation]] — parent note on goodness-of-fit
- [[F-Statistic]] — tests overall model significance
- [[t-Statistic]] — tests individual coefficient significance
- [[AIC and BIC]] · [[Overfitting]] · [[Parsimony]]
- [[Sum of Squares]] · [[Residuals]] · [[Degrees of Freedom]]
- [[Correlation]] — link to simple-regression $R^2$
