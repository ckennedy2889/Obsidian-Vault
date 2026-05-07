---
title: Hypothesis Testing in Regression
subject: Quantitative Methods
tags: [CFA-L2, QuantitativeMethods, Regression, MultipleRegression, HypothesisTesting, TTest, FTest, PValue, ConfidenceInterval, Significance, Multicollinearity, Heteroskedasticity, SerialCorrelation, RobustStandardErrors]
aliases: [Regression Hypothesis Testing, t-test in Regression, F-test in Regression, Significance Testing, Coefficient Significance]
---

# Hypothesis Testing in Regression

> [!abstract] The One-Sentence Version
> Regression hypothesis testing is the machinery that converts a coefficient estimate — a single number spit out by OLS — into a **defensible statement about whether that number is real or just noise**, using t-tests for individual coefficients and F-tests for groups of them.

## The Analogy — Is the Shoe Brand Actually Making You Faster?

Imagine you're a coach. You switch your runner from brand A sneakers to brand B and their 10K time drops by 45 seconds. Was it the shoes? Or was it just a good day — coffee, weather, sleep?

**OLS gave you the 45-second "estimate."** Hypothesis testing asks the harder question: **how confident are we that the true effect isn't zero?** If you ran the experiment 1,000 times with identical-but-useless shoes, would a 45-second drop show up by luck?

- The **t-test** answers: "Is *this one* change (brand B) making a real difference?"
- The **F-test** answers: "Is *anything in my whole coaching program* — shoes, diet, altitude training — making a real difference?"

Every coefficient OLS hands you needs to face this gauntlet before you trust it.

> [!tip] Memory Hook — **"Estimate ÷ Uncertainty"**
> Every test statistic in regression has the same DNA: **signal over noise**.
>
> $$t = \frac{\text{how far the estimate is from the null}}{\text{how much the estimate could jitter}}$$
>
> Big number → the signal dominates the noise → **reject** the null.

---

## 1. The Null and Alternative Hypotheses

Every hypothesis test in regression starts by writing down two mutually exclusive statements about the population (not the sample!):

| Hypothesis | Symbol | Plain English |
|---|---|---|
| **Null** ($H_0$) | $\beta_j = B_0$ | "The true coefficient equals the hypothesized value $B_0$" — usually the skeptic's position: the variable has no effect ($B_0 = 0$) |
| **Alternative** ($H_a$) | $\beta_j \neq B_0$ (two-tailed), or $\beta_j > B_0$ / $\beta_j < B_0$ (one-tailed) | "The true coefficient is different from $B_0$" — the claim you're trying to support |

> [!note] Jargon Decoded — **"Population" vs. "Sample"**
> $\beta_j$ (Greek letter) is the **true**, **unknown** population parameter. $\hat b_j$ (Roman letter with a hat) is your **estimate** from the sample. Hypothesis testing always asks questions about $\beta_j$, using $\hat b_j$ as evidence.

### Common Nulls You'll See on the Exam

| Context | Null Hypothesis | Why |
|---|---|---|
| Does variable matter at all? | $H_0: \beta_j = 0$ | The default — test statistical significance |
| Is the stock a market-tracker? | $H_0: \beta_{\text{MKT}} = 1$ | Test whether market beta equals exactly 1 |
| Is the currency-pair test passed? | $H_0: \beta_1 + \beta_2 = 1$ | Test a linear combination (unbiasedness) |
| Is the model useless? | $H_0: \beta_1 = \beta_2 = \dots = \beta_k = 0$ | Joint null — tested with F-test, not t-test |

---

## 2. The t-Test for a Single Coefficient

### 2.1 The Formula

$$
\boxed{\;t \;=\; \frac{\hat b_j - B_0}{s_{\hat b_j}}\;}
$$

| Symbol | Meaning |
|---|---|
| $\hat b_j$ | OLS-estimated slope on variable $j$ |
| $B_0$ | The hypothesized value under $H_0$ (almost always 0) |
| $s_{\hat b_j}$ | **Standard error** of the estimated coefficient — the jitter |

When $B_0 = 0$ (the usual case), this simplifies to the familiar:

$$t = \frac{\hat b_j}{s_{\hat b_j}}$$

That's the "t-stat" you see in every regression output.

### 2.2 Degrees of Freedom — The Hurdle Height

$$\boxed{\;\mathrm{df} \;=\; n - k - 1\;}$$

| Symbol | Meaning |
|---|---|
| $n$ | Sample size |
| $k$ | Number of independent variables (excluding the intercept) |
| $+1$ | The intercept itself |

Every coefficient you estimate "costs" one degree of freedom. More regressors → fewer df → *larger* critical values → **harder** to achieve significance. That's the intuition for why kitchen-sink models get punished.

### 2.3 Standard Error — Where Uncertainty Comes From

The standard error of $\hat b_j$ depends on three things:

1. **How noisy the residuals are** — captured by the residual standard error $s_e = \sqrt{\mathrm{SSE}/(n-k-1)}$. Noisier errors → larger $s_{\hat b_j}$.
2. **How much $X_j$ varies** in the sample — more variation in $X_j$ → more precision → **smaller** $s_{\hat b_j}$.
3. **How correlated $X_j$ is with other regressors** — higher correlation (multicollinearity) → *larger* $s_{\hat b_j}$.

The [[Variance Inflation Factor]] (VIF) quantifies #3:

$$\mathrm{VIF}_j = \frac{1}{1 - R_j^2}$$

where $R_j^2$ is the $R^2$ from regressing $X_j$ on all the *other* regressors. Rule of thumb: **VIF > 10** flags a multicollinearity problem.

---

## 3. One-Tailed vs. Two-Tailed Tests

Choose before peeking at the data — post-hoc choices invalidate the test.

| Test type | $H_0$ | $H_a$ | When to use | Critical region |
|---|---|---|---|---|
| **Two-tailed** | $\beta_j = B_0$ | $\beta_j \neq B_0$ | No directional prior; default test | Both tails |
| **Right-tailed** (one-tail) | $\beta_j \le B_0$ | $\beta_j > B_0$ | Theory says effect is positive (e.g., education → wages) | Right tail only |
| **Left-tailed** (one-tail) | $\beta_j \ge B_0$ | $\beta_j < B_0$ | Theory says effect is negative (e.g., price → demand) | Left tail only |

```
Two-tailed                 One-tailed (right)
   ─────────                 ─────────
   │   ∧   │                 │    ∧  │
   │  ╱ ╲  │                 │   ╱ ╲ │
   │ ╱   ╲ │                 │  ╱   ╲│
   │╱     ╲│                 │ ╱    ╲░░ ← reject region
   ░░     ░░                 │╱      ░░
   ↑      ↑                        ↑
 α/2     α/2                       α
```

**Rule of thumb:** For the same $\alpha$, one-tailed critical values are *smaller* (easier to reject) — but only valid if you committed to the direction in advance.

---

## 4. Decision Rules — Two Equivalent Paths

### 4.1 Critical-Value Approach

1. Choose $\alpha$ (usually 0.05 or 0.01).
2. Look up $t_{\text{crit}}$ in the t-table at df $= n-k-1$ and the chosen $\alpha$ (halve it for two-tailed).
3. Compute your $t$-statistic.
4. **Reject $H_0$ if $|t| > t_{\text{crit}}$** (two-tailed) or $t$ lies in the appropriate one-tailed rejection region.

### 4.2 P-Value Approach

The **p-value** is the probability, *assuming $H_0$ is true*, of seeing a test statistic at least as extreme as yours.

- **Reject $H_0$ if $p < \alpha$.**
- Small p-value = strong evidence against $H_0$.

| p-value | Common language |
|---|---|
| p < 0.01 | "Highly significant" |
| 0.01 ≤ p < 0.05 | "Significant" |
| 0.05 ≤ p < 0.10 | "Marginally significant" |
| p ≥ 0.10 | "Not significant" |

> [!tip] The Two Paths Always Agree
> $|t| > t_{\text{crit}}$ ⟺ $p < \alpha$. They're the same test, just framed differently. Pick whichever your software gives you.

---

## 5. Type I and Type II Errors

| | $H_0$ True | $H_0$ False |
|---|---|---|
| **Reject $H_0$** | **Type I error** ("false positive") — probability $\alpha$ | ✔ Correct ("power" = $1 - \beta$) |
| **Fail to reject $H_0$** | ✔ Correct | **Type II error** ("false negative") — probability $\beta$ |

| Symbol | Name | Plain English |
|---|---|---|
| $\alpha$ | Significance level | The risk of a false alarm you're willing to tolerate |
| $\beta$ (not the regression beta!) | Type II error rate | The risk of missing a real effect |
| $1 - \beta$ | **Power** of the test | The chance of correctly rejecting a false null |

> [!warning] The $\alpha$-$\beta$ Trade-Off
> Lowering $\alpha$ (being stricter about false alarms) **raises $\beta$** (you miss more real effects). The only way to improve both simultaneously is a **bigger sample**.

---

## 6. Confidence Intervals — The Flip Side of the Same Coin

A $(1-\alpha)$ confidence interval for $\beta_j$:

$$\boxed{\;\hat b_j \;\pm\; t_{\text{crit}} \times s_{\hat b_j}\;}$$

where $t_{\text{crit}}$ uses $\alpha/2$ in each tail and df $= n-k-1$.

**The deep link to hypothesis testing:**

> If $B_0$ lies **inside** the $(1-\alpha)$ CI → **fail to reject** $H_0: \beta_j = B_0$.
> If $B_0$ lies **outside** the $(1-\alpha)$ CI → **reject** $H_0: \beta_j = B_0$.

That's why if a **95% CI for a slope excludes zero**, the coefficient is significant at the 5% level (two-tailed) — the test and the CI are algebraically identical.

---

## 7. The F-Test for Overall Model Significance

The t-test asks one variable at a time. The **F-test** asks the whole model at once.

### 7.1 Hypotheses

| | Statement |
|---|---|
| $H_0$ | $\beta_1 = \beta_2 = \dots = \beta_k = 0$ (the model as a whole explains nothing) |
| $H_a$ | **At least one** $\beta_j \neq 0$ |

### 7.2 The Statistic

$$
\boxed{\;F \;=\; \frac{\mathrm{MSR}}{\mathrm{MSE}} \;=\; \frac{\mathrm{SSR}/k}{\mathrm{SSE}/(n-k-1)}\;}
$$

| Term | Full name | What it is |
|---|---|---|
| **MSR** | Mean Square Regression | Explained variation *per regressor* |
| **MSE** | Mean Square Error | Leftover unexplained variation *per residual df* |

Distribution under $H_0$: $F \sim F_{k,\; n-k-1}$ (numerator df, denominator df).

### 7.3 Decision Rule

- **One-tailed** (F is always non-negative). Reject $H_0$ if $F > F_{\text{crit}}$ or if p-value $< \alpha$.

### 7.4 Why Not Just Run k Separate t-Tests?

Because running many tests inflates the family-wise Type I error. With 20 regressors at $\alpha = 0.05$, you'd expect roughly one "significant" t-stat by pure chance even if *all* true $\beta$'s were zero. The overall F-test guards against that.

See: [[F-Statistic]] · [[Sum of Squares]] · [[R-Squared and Adjusted R-Squared]]

---

## 8. The General (Nested) F-Test — Testing a Subset of Coefficients

Often you want to test whether a *group* of variables matters jointly: "Do factors 4, 5, 6 collectively add anything?"

### 8.1 The Setup

Two models, same dependent variable:

| Model | Name | Details |
|---|---|---|
| **Unrestricted** | The full model | $k$ regressors, residual sum of squares $\mathrm{SSE}_U$ |
| **Restricted** | Drop the $q$ variables you're testing | $k - q$ regressors, residual sum of squares $\mathrm{SSE}_R$ |

### 8.2 The Statistic

$$
\boxed{\;F \;=\; \frac{(\mathrm{SSE}_R - \mathrm{SSE}_U)/q}{\mathrm{SSE}_U / (n - k - 1)}\;}
$$

| Term | Meaning |
|---|---|
| $q$ | Number of coefficients restricted to zero (number of variables dropped) |
| $\mathrm{SSE}_R - \mathrm{SSE}_U$ | How much *worse* the restricted model's fit got |
| $n - k - 1$ | df of the *unrestricted* model |

**Intuition.** If dropping the $q$ variables only slightly worsens the fit, those variables weren't doing much — F will be small. If dropping them blows up the SSE, F will be large → reject $H_0$ and keep the variables.

Distribution: $F \sim F_{q,\; n-k-1}$.

### 8.3 Special Case

The **overall F-test** (§7) is a general F-test where the restricted model has only the intercept ($q = k$, $\mathrm{SSE}_R = \mathrm{SST}$).

---

## 9. Testing a Single Linear Restriction

Example: "Do $X_1$ and $X_2$ together fully capture the effect — i.e., $\beta_1 + \beta_2 = 1$?"

### Two Equivalent Paths

**Path A — t-test on the combination:**

$$t = \frac{(\hat b_1 + \hat b_2) - 1}{s_{\hat b_1 + \hat b_2}}$$

where $s_{\hat b_1 + \hat b_2} = \sqrt{\mathrm{Var}(\hat b_1) + \mathrm{Var}(\hat b_2) + 2\,\mathrm{Cov}(\hat b_1, \hat b_2)}$.

**Path B — Restricted/unrestricted F-test** with the restriction substituted into the unrestricted model. Works for any linear restriction, including multiple restrictions simultaneously.

---

## 10. Economic vs. Statistical Significance

> [!warning] Don't Confuse Them
> A coefficient can be **statistically significant** (p < 0.01) yet **economically trivial**. Example: a 1% rise in marketing spend *reliably* increases sales by 0.0001%. Statistically real. Business-wise irrelevant.

| | Statistical significance | Economic significance |
|---|---|---|
| Measures | Is the effect reliably different from zero? | Is the effect **big enough** to matter? |
| Depends on | Sample size, noise, estimation precision | Context, costs, decision thresholds |
| Test | t-stat, p-value | Judgment — is $\hat b_j$ large relative to the practical scale? |

Huge samples make *everything* statistically significant. Always report the estimated magnitude, not just the p-value.

---

## 11. Common Pitfalls That Break Hypothesis Tests

| Problem | What it is | Effect on t-stats | Diagnosis | Fix |
|---|---|---|---|---|
| **Multicollinearity** | Regressors highly correlated with each other | **Inflates** standard errors → t-stats look small, **joint F significant but individual t's not** | High VIF (>10); significant F with no significant t's | Drop redundant variables; use PCA; pool into an index |
| **Heteroskedasticity** | Error variance changes with X | t-stats **unreliable** (usually overstated); Type I error rate wrong | Breusch-Pagan, White test; residual plot shows fanning | **White-corrected (robust) SE** |
| **Serial correlation (autocorrelation)** | Errors correlated over time | Inflates t-stats → too many false positives; F-tests invalid | Durbin-Watson; Breusch-Godfrey; correlogram | **Newey-West** (HAC) SE; add lagged terms |
| **Omitted variable bias** | Relevant regressor left out, correlated with included X | Biases the coefficient (and its SE) itself | Economic reasoning; look for structural breaks | Add the omitted variable or instrument it |
| **Model misspecification** | Wrong functional form | t-tests test the wrong thing | Ramsey RESET; residual patterns | Transform variables (logs, squares) or respecify |

> [!tip] The Robust-SE Reflex
> Both heteroskedasticity and serial correlation have the same remedy structure: **don't change the point estimates, just fix the standard errors.**
> - **White** → cross-sectional data (heteroskedasticity only)
> - **Newey-West** → time-series data (heteroskedasticity **and** autocorrelation)

See: [[Multiple Regression - Basics and Assumptions]] · [[Model Misspecification]]

---

## 12. The Individual-vs-Joint Significance Paradox

Classic exam-bait symptom:

> Overall F-stat huge (p < 0.001). Model $R^2 = 0.85$. But **none** of the individual t-stats are significant.

**Diagnosis: Multicollinearity, almost always.**

**Why it happens:** The regressors are telling the *same story*. As a group they explain 85% of the variation (F knows this). But OLS can't attribute the effect to any *one* variable, so every standard error is inflated, every t-stat is small.

**What to do:**
1. Check the correlation matrix and VIFs.
2. Drop or combine correlated regressors.
3. Re-estimate and retest.

---

## 13. Fully Worked Numerical Example

**Setup.** An analyst regresses a firm's Return on Assets (ROA) on Capital Expenditures (CAPEX), Advertising (ADV), and R&D spending.

- Sample size: $n = 26$
- Regressors: $k = 3$
- Degrees of freedom for residuals: $n - k - 1 = 26 - 3 - 1 = 22$

**Estimated model:**

$$\widehat{\mathrm{ROA}} = 4.7022 + 1.2302\,\mathrm{CAPEX} - 0.0371\,\mathrm{ADV} + 0.1029\,\mathrm{R\&D}$$

### Part A — Overall F-Test (at $\alpha = 1\%$)

- $H_0: \beta_{\mathrm{CAPEX}} = \beta_{\mathrm{ADV}} = \beta_{\mathrm{R\&D}} = 0$
- $H_a$: at least one $\beta_j \neq 0$
- $F_{\text{stat}} = 54.4039$ (from software)
- $F_{\text{crit}}$ at $(k, n-k-1) = (3, 22)$, $\alpha = 0.01$ → **4.8166**

**Decision:** $54.4039 > 4.8166$ → **reject $H_0$.** The model is significant overall.

### Part B — t-Test on CAPEX (two-tailed, $\alpha = 1\%$)

- $H_0: \beta_{\mathrm{CAPEX}} = 0$; $H_a: \beta_{\mathrm{CAPEX}} \neq 0$
- $\hat b_{\mathrm{CAPEX}} = 1.2302$, $s_{\hat b_{\mathrm{CAPEX}}} = 0.1056$
- $t = \dfrac{1.2302 - 0}{0.1056} = \mathbf{11.649}$
- $t_{\text{crit}}$ at df = 22, two-tail $\alpha/2 = 0.005$ → $\pm 2.8188$

**Decision:** $11.649 > 2.8188$ → **reject $H_0$.** CAPEX is highly significant.

### Part C — t-Test on ADV (two-tailed, $\alpha = 1\%$)

- $H_0: \beta_{\mathrm{ADV}} = 0$
- $\hat b_{\mathrm{ADV}} = -0.0371$, $s_{\hat b_{\mathrm{ADV}}} = 0.1062$
- $t = \dfrac{-0.0371}{0.1062} = \mathbf{-0.3493}$

**Decision:** $|-0.3493| < 2.8188$ → **fail to reject $H_0$.** Advertising is *not* a significant predictor of ROA in this model.

### Part D — 95% Confidence Interval for CAPEX

For a 95% CI with df = 22, $t_{\text{crit, 0.025}} = 2.0739$.

$$\mathrm{CI}_{95\%} = 1.2302 \pm (2.0739)(0.1056) = 1.2302 \pm 0.2190 = (1.0112,\; 1.4492)$$

Zero is **nowhere near** this interval → consistent with rejecting $H_0$ at 5% (and at 1%).

### Part E — Testing a Non-Zero Hypothesis: Does CAPEX have a unit elasticity?

Suppose theory predicts $\beta_{\mathrm{CAPEX}} = 1$.

- $H_0: \beta_{\mathrm{CAPEX}} = 1$; $H_a: \beta_{\mathrm{CAPEX}} \neq 1$
- $t = \dfrac{1.2302 - 1}{0.1056} = \dfrac{0.2302}{0.1056} = \mathbf{2.180}$
- $t_{\text{crit}}$ at df = 22, two-tail $\alpha = 0.05$ → $\pm 2.0739$

**Decision:** $2.180 > 2.0739$ → **reject $H_0$ at 5%.** The effect is statistically larger than 1 at 5% (though *not* at 1%, where the critical value is 2.8188).

---

## 14. Quick-Reference Cheat Sheet

### Which Test When

| Question | Test | Statistic | df |
|---|---|---|---|
| Is *this one* variable significant? | Single-coefficient t-test | $t = (\hat b_j - B_0)/s_{\hat b_j}$ | $n-k-1$ |
| Is the *whole model* significant? | Overall F-test | $F = \mathrm{MSR}/\mathrm{MSE}$ | $k,\; n-k-1$ |
| Do *these q variables jointly* matter? | Nested F-test | $F = \dfrac{(\mathrm{SSE}_R-\mathrm{SSE}_U)/q}{\mathrm{SSE}_U/(n-k-1)}$ | $q,\; n-k-1$ |
| Does a *linear combination* of coefficients equal some value? | t-test on the combo (or restricted F) | $t = \dfrac{(\hat b_1 + \hat b_2 - c)}{s_{\hat b_1+\hat b_2}}$ | $n-k-1$ |

### Common Critical Values (Two-Tailed t, Large Sample)

| $\alpha$ | $t_{\text{crit}}$ (df large) |
|---|---|
| 0.10 | 1.645 |
| 0.05 | 1.960 |
| 0.01 | 2.576 |

### Red-Flag Table

| Symptom | Likely cause | Fix |
|---|---|---|
| Big F, small t's everywhere | Multicollinearity | Drop/combine regressors, check VIF |
| t-stats suspiciously large | Heteroskedasticity in cross-section | White SE |
| t-stats suspiciously large, time-series data | Serial correlation | Newey-West SE |
| Coefficient's sign flips when a variable is added | Omitted-variable bias or collinearity | Revisit specification |

---

## 15. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Formulate** null and alternative hypotheses for a single regression coefficient (two-tailed, right-tailed, left-tailed, against non-zero targets).
- [x] **Calculate** a t-statistic and **determine** the correct degrees of freedom.
- [x] **Describe** how the standard error of a coefficient is affected by noise, variation in X, and multicollinearity.
- [x] **Apply** both the critical-value and p-value decision rules.
- [x] **Distinguish** Type I from Type II errors, and explain the $\alpha$-$\beta$-power trade-off.
- [x] **Construct** a confidence interval for a coefficient and **explain** its link to hypothesis testing.
- [x] **Calculate** and **interpret** the overall F-test for model significance.
- [x] **Apply** the general (nested) F-test to a subset of coefficients and state the correct $q$ and df.
- [x] **Distinguish** statistical significance from economic significance.
- [x] **Diagnose** multicollinearity, heteroskedasticity, and serial correlation as threats to valid inference, and **name** the standard remedy (White, Newey-West, drop regressors).
- [x] **Explain** the individual-vs-joint-significance paradox and its diagnosis.
- [x] **Execute** a full regression hypothesis-testing workflow end-to-end on a multi-variable problem.

---

## Related Notes

- [[Multiple Regression - Basics and Assumptions]] — OLS setup, Gauss-Markov assumptions
- [[Regression Model Fit and Interpretation]] — companion note on goodness-of-fit
- [[R-Squared and Adjusted R-Squared]] — complementary metrics, non-test-based
- [[Model Misspecification]] — omitted variables, wrong functional form
- [[F-Statistic]] · [[t-Statistic]] · [[P-Value]] · [[Confidence Interval]]
- [[Variance Inflation Factor]] · [[Heteroskedasticity]] · [[Serial Correlation]]
- [[White-Corrected Standard Errors]] · [[Newey-West Standard Errors]]
- [[Type I and Type II Errors]] · [[Statistical Power]]
