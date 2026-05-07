---
title: Degrees of Freedom
subject: Quantitative Methods
tags: [CFA-L2, QuantitativeMethods, Statistics, Regression, DegreesOfFreedom, df, TDistribution, FDistribution, ANOVA, HypothesisTesting]
aliases: [df, Degrees of Freedom, DoF, Residual df, Regression df]
---

# Degrees of Freedom

> [!abstract] The One-Sentence Version
> **Degrees of freedom** count how many pieces of *independent* information you have left in your data after you've spent some of it estimating parameters — and in regression, every coefficient you estimate costs you exactly one piece.

## The Analogy — The Dinner Bill

You and three friends go out to dinner. The total bill is *exactly* $100 — that's fixed. The waiter asks each person individually what they owe.

- **Friend 1** can say anything — "I had $38." ✓ Freedom.
- **Friend 2** can also say anything — "I had $22." ✓ Freedom.
- **Friend 3** can also say anything — "I had $31." ✓ Freedom.
- **Friend 4** is *stuck*. Their amount is forced: whatever makes the four numbers sum to $100. In this case, $100 − 38 − 22 − 31 = $9. ✗ No freedom.

You have **four data points** (the four amounts) but only **three degrees of freedom**, because the constraint "must sum to $100" locked down one value. The moment you fix a total (or a mean, or any other summary), you give up one piece of independent information.

> [!tip] Memory Hook — **"Every constraint costs one df"**
> df = (number of observations) − (number of constraints already imposed on the data). If you've computed anything *from* the data and are using that quantity downstream, you've spent a degree of freedom.

---

## 1. The Formal Definition

$$
\boxed{\;\text{df} \;=\; n \;-\; (\text{number of parameters estimated from the data})\;}
$$

| Symbol | Meaning |
|---|---|
| $n$ | Sample size — how many observations you have |
| Parameters estimated | Means, slopes, intercepts, anything you computed from the sample and are now treating as "known" |

Degrees of freedom are the pieces of *independent* information remaining — the wiggle room left in your dataset after you've already "spent" some of it to estimate summary statistics.

---

## 2. The Simplest Example — Why Sample Variance Divides by $n-1$

You've seen this formula a hundred times:

$$s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar x)^2$$

**Why $n-1$ and not $n$?** Because you had to compute $\bar x$ from the same data first. That single act imposes one constraint: the deviations $(x_i - \bar x)$ must sum to exactly zero. Once you know $n-1$ of the deviations, the last one is *determined* — just like friend #4 at dinner.

| Step | What happens to df |
|---|---|
| Start with raw data | $n$ degrees of freedom |
| Compute $\bar x$ | Burns 1 df (one constraint imposed) |
| Left to estimate variance | $n - 1$ df |

This isn't a quirk — it's the pattern. **Every estimated parameter burns exactly one degree of freedom.**

---

## 3. The Parameter Cost Principle

> [!important] The Core Rule
> **Each parameter you estimate from the data costs one degree of freedom.**
> - Estimate one mean → lose 1 df.
> - Estimate one slope → lose 1 df.
> - Estimate 5 slopes + 1 intercept → lose 6 df.

Think of df as a *budget*. You start with $n$ units of information. You spend one for every quantity you compute from the data. What's left pays for inference — t-tests, F-tests, confidence intervals, everything.

If you try to estimate more parameters than you have observations ($k \ge n$), you literally run out of information. The regression won't even run.

---

## 4. Applying This to Multiple Regression

In a multiple regression with $k$ independent variables:

$$\hat Y_i = b_0 + b_1 X_{1i} + b_2 X_{2i} + \dots + b_k X_{ki}$$

you estimate:
- **1** intercept ($b_0$)
- **$k$** slope coefficients ($b_1, b_2, \ldots, b_k$)

Total parameters estimated: $k + 1$.

### Residual Degrees of Freedom

$$\boxed{\;\mathrm{df}_{\text{residual}} \;=\; n - k - 1\;}$$

This is the df left over for the *residuals* (the unexplained errors) after the regression has "spent" $k + 1$ pieces of information on fitting the coefficients.

```
Start:          n pieces of information
Burn:           1 for the intercept (b₀)
Burn:           k for the slopes    (b₁, b₂, …, bₖ)
─────────────────────────────────────────────────
Remaining:      n − k − 1  → residual df
```

**Why is this the number everyone keeps repeating?** Because virtually every hypothesis test, every t-critical-value lookup, every F-test in regression uses $n - k - 1$ as the "denominator df" — it's the amount of genuine error information your model has left to work with.

---

## 5. The ANOVA Table — Where the df Pieces Add Up

The ANOVA (Analysis of Variance) table that software spits out for every regression has a df column. The df for the three sums of squares **always add up**:

| Row | Sum of Squares | Degrees of Freedom | Why |
|---|---|---:|---|
| **Regression (SSR)** | $\sum(\hat Y_i - \bar Y)^2$ | **$k$** | One df per slope |
| **Residual (SSE)** | $\sum(Y_i - \hat Y_i)^2$ | **$n - k - 1$** | What's left after fitting intercept + $k$ slopes |
| **Total (SST)** | $\sum(Y_i - \bar Y)^2$ | **$n - 1$** | One df burned to compute $\bar Y$ |

> [!tip] The Additivity Identity
> $$\underbrace{k}_{\text{SSR df}} \;+\; \underbrace{(n-k-1)}_{\text{SSE df}} \;=\; \underbrace{n-1}_{\text{SST df}}$$
>
> If your numbers don't add up this way in an ANOVA table, you've miscounted $k$ or $n$.

Every **mean square** in the ANOVA table is formed by dividing a sum of squares by its df:

$$\mathrm{MSR} = \frac{\mathrm{SSR}}{k}, \qquad \mathrm{MSE} = \frac{\mathrm{SSE}}{n-k-1}$$

That's why df matters for the F-test: $F = \mathrm{MSR}/\mathrm{MSE}$ uses both df values to compute the statistic itself.

---

## 6. Why Degrees of Freedom Matter for t-Tests

The Student's **t-distribution** is shaped by its degrees of freedom.

| df | Shape | Critical value (two-tail, $\alpha = 0.05$) |
|---|---|---|
| **5** | Very fat tails — extreme values are common | **2.571** |
| **10** | Still fat-tailed | **2.228** |
| **25** | Noticeably tighter | **2.060** |
| **50** | Close to normal | **2.009** |
| **100** | Nearly standard normal | **1.984** |
| **∞** | Exact standard normal | **1.960** |

```
Low df (5):   ───╱╲──────╱╲───    ← long, fat tails
                 ╱  ╲    ╱  ╲
                ╱    ╲  ╱    ╲

High df (100):  ──╱‾╲──────╱‾╲──   ← tight, almost normal
                  ╱  ╲    ╱  ╲
                 ╱    ╲  ╱    ╲
```

**What this means practically:**

- **Low df** → fat tails → big random excursions are common → **higher** critical values → **harder to reject $H_0$**.
- **High df** → tight distribution → the same t-statistic looks more extreme → **easier to reject $H_0$**.

**Implication for model building:** every extra regressor you add shrinks your residual df, which raises your t-critical values, which makes it *harder* to prove any individual variable is significant. Parsimony isn't just aesthetic — it's a statistical necessity.

---

## 7. Why Degrees of Freedom Matter for F-Tests

The **F-distribution** takes **two** df parameters:

$$F \sim F_{\;k,\; n-k-1}$$

| df piece | Role |
|---|---|
| **Numerator df $= k$** | Number of regression parameters being tested |
| **Denominator df $= n-k-1$** | Residual df (your noise-floor information) |

The critical value $F_{\text{crit}}$ depends on *both*. Large residual df → tight F-distribution → lower critical value → easier to detect a significant overall model. Tiny residual df (lots of regressors, few observations) → blown-up critical values → almost nothing passes.

See: [[F Distribution and F Tests]] · [[Hypothesis Testing in Regression]]

---

## 8. Practical Consequences — The Hidden Cost of "Kitchen Sink" Models

Consider a naive analyst who keeps tossing variables into a regression:

| Model size ($k$) | Sample $n$ | Residual df | t-crit (5%, two-tail) | Relative difficulty |
|---|---|---|---|---|
| 2 predictors | 30 | 27 | 2.052 | Baseline |
| 10 predictors | 30 | 19 | 2.093 | Slightly harder |
| 20 predictors | 30 | 9 | **2.262** | Noticeably harder |
| 25 predictors | 30 | 4 | **2.776** | Very hard |
| 29 predictors | 30 | 0 | ∞ (no inference possible) | Degenerate |

> [!warning] The Overfitting Tax
> Adding useless variables doesn't just dilute the model — it *actively shrinks the df budget*, penalizing every hypothesis test. You pay twice for greedy specifications: once in inflated standard errors (multicollinearity), once in shriveled residual df (tighter critical-value hurdles).

This is also why [[AIC and BIC]] and [[R-Squared and Adjusted R-Squared]] exist — to penalize complexity explicitly.

---

## 9. Fully Worked Example

**Setup.** You study $n = 50$ companies and regress returns on $k = 4$ factors — Size, Value, Momentum, and Profitability.

### Compute Every df in Sight

| Quantity | Formula | Value |
|---|---|---|
| Total df (SST) | $n - 1$ | $50 - 1 = \mathbf{49}$ |
| Regression df (SSR) | $k$ | $\mathbf{4}$ |
| Residual df (SSE) | $n - k - 1$ | $50 - 4 - 1 = \mathbf{45}$ |
| Check additivity | $k + (n-k-1) = n-1$ | $4 + 45 = 49$ ✓ |

### Which df Do You Use Where?

| Test | df used | Why |
|---|---|---|
| t-test on any single slope coefficient | **45** | Residual df = $n-k-1$ |
| 95% CI on any single coefficient | **45** | Same as t-test |
| Overall F-test for model significance | **(4, 45)** | Numerator $k$, denominator $n-k-1$ |
| Nested F-test dropping 2 variables (testing $\beta_3 = \beta_4 = 0$) | **(2, 45)** | Numerator $q$ (restrictions), denominator $n-k-1$ from the *unrestricted* model |

### Critical Values

- $t_{0.025,\, 45} \approx \mathbf{2.014}$ (two-tail, 5%)
- $F_{0.05,\, 4,\, 45} \approx \mathbf{2.579}$

If your computed t-stat on any coefficient exceeds 2.014 in absolute value, reject $H_0: \beta_j = 0$ at 5%. If your F-stat exceeds 2.579, reject the joint "all slopes zero" null.

---

## 10. Rules of Thumb for Sample Size vs. Regressors

### The Hard Rule

$$n > k + 1 \quad \text{(strictly — otherwise the regression is under-identified)}$$

You need at least one more observation than parameters, or OLS literally has no unique solution.

### The Practical Rules

| Guidance | When it applies |
|---|---|
| **$n \ge 10 \times k$** ("10 observations per regressor") | Classical minimum for reasonably stable OLS coefficients |
| **$n \ge 20 \times k$** | Preferred in finance where noise is high |
| **$n \gg k$** | Machine-learning-adjacent work; the more, the better for avoiding overfitting |
| **$n - k - 1 \ge 30$** | Residual df large enough that t-distribution is nearly normal — safer inference |

> [!tip] Quick Sanity Check on Exam Day
> Before trusting any regression-based inference on the exam, compute $n - k - 1$. If it's below ~10, the t-distribution has fat tails and critical values are much larger than the "~2" rule of thumb — reading off the t-table is non-negotiable.

---

## 11. Quick-Reference Cheat Sheet

| Context | df formula | What it represents |
|---|---|---|
| Sample mean | $n$ | No constraints yet |
| Sample variance / std dev | $n - 1$ | One constraint from the computed mean |
| Simple linear regression (1 predictor) | $n - 2$ | 1 intercept + 1 slope |
| Multiple regression — residual df | $n - k - 1$ | 1 intercept + $k$ slopes |
| Multiple regression — SSR df | $k$ | One per slope |
| Multiple regression — SST df | $n - 1$ | One per sample minus mean |
| t-test on a coefficient | $n - k - 1$ | Residual df |
| F-test, overall significance | $(k,\; n - k - 1)$ | Both numerator and denominator |
| General F-test, joint restrictions | $(q,\; n - k - 1)$ | $q$ = number of restrictions |

### The Three-Sentence Summary

1. You start with $n$ pieces of information.
2. Every parameter you estimate from the data burns exactly one degree of freedom.
3. What's left ($n - k - 1$ in multiple regression) is the fuel for t-tests, F-tests, and confidence intervals — and the smaller that fuel tank, the harder it is to prove anything.

---

## 12. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Define** degrees of freedom intuitively (constraints on independent information) and formally.
- [x] **Explain** why sample variance divides by $n-1$ and not $n$.
- [x] **State** the parameter-cost principle: each estimated parameter costs one df.
- [x] **Calculate** the residual df $n - k - 1$ for a multiple regression.
- [x] **Reproduce** the three df rows of an ANOVA table ($k$, $n-k-1$, $n-1$) and verify their additivity.
- [x] **Describe** how df affects the shape of the t-distribution and the magnitude of critical values.
- [x] **Identify** both df parameters for an F-test (numerator $k$, denominator $n-k-1$).
- [x] **Explain** the practical consequence of adding too many regressors — shrinking residual df, higher critical values, harder inference.
- [x] **Apply** the df framework to a fully worked example and identify the correct df for each test.
- [x] **State** the minimum $n > k+1$ rule and common rules-of-thumb for adequate sample size.

---

## Related Notes

- [[Hypothesis Testing in Regression]] — where df shows up in every t-test and F-test
- [[R-Squared and Adjusted R-Squared]] — adjusted $R^2$ uses $n-1$ and $n-k-1$ directly
- [[AIC and BIC]] — model-selection criteria that penalize complexity $(k+1)$
- [[F Distribution and F Tests]] · [[F-Test vs t-Test]]
- [[Multiple Regression - Basics and Assumptions]] — setup that creates the df budget
- [[Sum of Squares]] · [[ANOVA]] · [[Mean Square Error]]
- [[t-Statistic]] · [[Confidence Interval]] · [[P-Value]]
