---
title: Breusch–Pagan Test
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics, heteroskedasticity, glossary]
aliases: [Breusch-Pagan Test, BP Test, BP Statistic, Test for Conditional Heteroskedasticity]
---

# Breusch–Pagan Test

**Program:** CFA® Program
**Level:** Level II

## Quick Definition

A formal, three-step hypothesis test that checks whether the variance of a regression's error terms changes systematically with the independent variables — i.e., whether [[Conditional heteroskedasticity|conditional heteroskedasticity]] is present. The test statistic is $BP = n \cdot R^2$ from an auxiliary regression of squared residuals on the $X$'s, and it follows a chi-square distribution with $k$ degrees of freedom.

---

## The Real-World Analogy

Imagine you run a bakery and forecast each day's muffin sales from the weather forecast. You fit a simple line: hotter day → more lemonade, fewer muffins. But you suspect something's off. On cool days, your forecasts are nearly perfect — you're off by three or four muffins at most. On hot days, your forecasts are wildly unreliable — sometimes off by fifty, sometimes dead on.

Your *average* prediction isn't biased (hot-day errors still center near zero), but the *spread* of your errors explodes as temperature rises. Traditional statistics assume your forecast errors wobble the same amount every day; they don't. If you ignore this, your confidence intervals around "expected muffin sales" will look much tighter than they really are.

The Breusch–Pagan test is the formal instrument that **proves** the size of your errors is tied to temperature — not just noise, but a systematic relationship between your inputs and your error variance. Once proved, you know your standard errors lie, your t-stats are inflated, and you need to fix the machinery before trusting any significance claims.

**Memory hook:** *BP = "Big-Predictor, Big-error"* — the test catches errors that grow (or shrink) with the $X$'s.

---

## Why This Test Exists: The Problem It Solves

[[Heteroskedasticity|Heteroskedasticity]] means "different scatter" (Greek *hetero-* = different, *skedastikos* = scattering). Its opposite, homoskedasticity, is one of the [[Classical linear regression model|classical OLS assumptions]]: the variance of the error term must be constant across all observations.

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma^2 \quad \text{(homoskedasticity — the assumption we want)}$$

When this fails, OLS still produces **unbiased and consistent** slope coefficients — the point estimates are fine — but it produces **wrong standard errors**, and everything downstream (t-stats, p-values, F-tests, confidence intervals) becomes untrustworthy.

### Two flavors — and only one is dangerous

| Type | Definition | Does it matter? |
|---|---|---|
| **[[Unconditional heteroskedasticity]]** | Error variance differs across observations but is **unrelated** to the independent variables | No — does not bias inference materially |
| **[[Conditional heteroskedasticity]]** | Error variance is **correlated with** (conditional on) the values of the $X$'s | **Yes — this is what breaks inference** |

The Breusch–Pagan test is specifically designed to detect the dangerous kind: **conditional** heteroskedasticity. It asks, "Are the squared residuals predictable from the regressors?" If yes → conditional heteroskedasticity.

### What exactly goes wrong under conditional heteroskedasticity?

```
          ┌─────────────────────────────────────────┐
          │  Conditional heteroskedasticity present │
          └─────────────────────────────────────────┘
                            │
                            ▼
       ┌────────────────────────────────────────┐
       │ OLS *underestimates* the standard error│
       │ of slope coefficients (in most cases). │
       └────────────────────────────────────────┘
                            │
                            ▼
        t-stat = coefficient / SE(coefficient)
                     (SE too small)
                            │
                            ▼
              ┌──────────────────────────┐
              │  t-stats are INFLATED    │
              └──────────────────────────┘
                            │
                            ▼
       ┌────────────────────────────────────────┐
       │  Too many rejections of H₀ → Type I    │
       │  errors → "significant" predictors     │
       │  that aren't really significant        │
       └────────────────────────────────────────┘
                            │
                            ▼
      F-test on overall model also unreliable
      (MSE no longer estimates true σ² properly)
```

So the *why* of the BP test: before you trust any t-stat, p-value, or F-stat from your regression output, you need to rule out conditional heteroskedasticity. The BP test is the rigorous, quantitative ruling.

---

## The LOS This Note Fulfills

**Quantitative Methods, LOS 3.b** — *explain the types of heteroskedasticity and how heteroskedasticity and serial correlation affect statistical inference.*

After reading this note you should be able to:

- **Describe** the concept of heteroskedasticity (conditional vs. unconditional) and its effect on regression inference.
- **Explain** why conditional heteroskedasticity matters and how it biases standard errors.
- **Formulate** the null and alternative hypotheses of the Breusch–Pagan test.
- **Calculate** the BP test statistic from $n$ and $R^2$ of the auxiliary regression.
- **Interpret** the BP statistic against a chi-square critical value.
- **Identify** appropriate corrections (robust standard errors, GLS, model revision).
- **Compare** the BP test to other regression diagnostics (visual inspection, Durbin–Watson, Breusch–Godfrey).

---

## The Mechanics: Three Steps, in Detail

The BP test is a *regression on the residuals of a regression*. That recursive structure is what trips people up, so walk through it carefully.

### Step 1 — Run the original regression

Estimate the model you actually care about:

$$Y_i = b_0 + b_1 X_{1i} + b_2 X_{2i} + \dots + b_k X_{ki} + \varepsilon_i$$

and save the fitted residuals:

$$\hat{u}_i = Y_i - \hat{Y}_i$$

These $\hat{u}_i$ are your **estimates of the unobservable errors**. You can't observe $\varepsilon_i$ directly, but $\hat{u}_i$ is the best proxy OLS gives you.

### Step 2 — Auxiliary regression of squared residuals

Now run a **second** regression, using the *squared* residuals as the dependent variable and the **same independent variables** as before:

$$\hat{u}_i^2 = a_0 + a_1 X_{1i} + a_2 X_{2i} + \dots + a_k X_{ki} + v_i$$

**Why squared residuals?** Because variance is by definition the expected value of the squared deviation from the mean — and OLS residuals have zero mean. So $\hat{u}_i^2$ is a direct, observable proxy for the local error **variance**. If that variance is being driven by the $X$'s, the auxiliary $R^2$ will be large. If it isn't, the auxiliary $R^2$ will be near zero.

Call the R-squared from this auxiliary regression $R^2_{\text{aux}}$.

### Step 3 — Compute the BP statistic

$$\boxed{\,BP = n \cdot R^2_{\text{aux}}\,}$$

- $n$ = number of observations in the original regression.
- $R^2_{\text{aux}}$ = coefficient of determination from the Step 2 auxiliary regression.

That's it. No separate software output needed — you just need the sample size and the auxiliary $R^2$.

**Intuition behind $n \cdot R^2$:** The auxiliary $R^2$ measures the proportion of variation in $\hat{u}^2$ explained by the regressors. Multiplying by $n$ rescales it into a chi-square-distributed quantity (a standard trick in Lagrange Multiplier tests — the BP test is in fact an **LM test**).

---

## The Hypotheses

| | Statement | Practical meaning |
|---|---|---|
| **$H_0$** (null) | $a_1 = a_2 = \dots = a_k = 0$ in the auxiliary regression | The $X$'s do **not** explain the squared residuals → residuals are homoskedastic |
| **$H_a$** (alt) | At least one $a_j \neq 0$ | The $X$'s **do** explain the squared residuals → conditional heteroskedasticity |

Under $H_0$, the BP statistic follows:

$$BP \sim \chi^2_k$$

where $k$ = number of independent variables in the original regression.

---

## The Decision Rule

The BP test is a **one-tailed, right-sided chi-square test**. Why right-sided? Because large values of $n \cdot R^2_{\text{aux}}$ mean the $X$'s explain a lot of the squared-residual variation → strong evidence **against** homoskedasticity. Small values mean the $X$'s explain nothing → no evidence of heteroskedasticity.

$$\text{Reject } H_0 \quad \text{if} \quad BP > \chi^2_{k,\,\alpha}$$

```
          χ² distribution with k df
                                 
     ╱╲                          
    ╱  ╲___                      
   ╱       ╲____                 
  ╱             ╲_____           
 ╱                   ╲_____      
                           ╲_____
─┼──────────────────────┼────────►
 0                  χ²_critical   
                         │  REJECT H₀ →
                         │  heteroskedasticity
                         ▼
                (right tail only)
```

**Memory hook for direction:** *"Big BP → Break the assumption."* A large statistic rejects homoskedasticity.

---

## Worked Numerical Example

An analyst is building a two-factor model to explain monthly returns on a small-cap equity fund. The independent variables are:

- $X_1$ = market excess return
- $X_2$ = a value-vs-growth factor

Sample size: $n = 96$ months. So the original regression has $k = 2$ independent variables.

### Step 1 — Original regression

$$R_{\text{fund}, i} = b_0 + b_1 \cdot R_{\text{mkt}, i} + b_2 \cdot \text{VMG}_i + \varepsilon_i$$

The analyst fits this via OLS and saves the 96 residuals $\hat{u}_i$.

### Step 2 — Auxiliary regression

The analyst squares each residual and regresses:

$$\hat{u}_i^2 = a_0 + a_1 \cdot R_{\text{mkt}, i} + a_2 \cdot \text{VMG}_i + v_i$$

Output: $R^2_{\text{aux}} = 0.06511$.

### Step 3 — Compute BP

$$BP = n \cdot R^2_{\text{aux}} = 96 \times 0.06511 = 6.251$$

### Decision

Degrees of freedom: $k = 2$ (two regressors in the *original* model).
Significance level: $\alpha = 0.05$.
Critical value: $\chi^2_{2,\,0.05} = 5.991$.

Since $6.251 > 5.991$, **reject $H_0$**. There is statistically significant evidence of conditional heteroskedasticity. The analyst's t-stats on $b_1$ and $b_2$ are not trustworthy as reported — they need to be corrected before any factor is called "significant."

| Quantity | Value |
|---|---|
| $n$ | 96 |
| $k$ (df) | 2 |
| $R^2_{\text{aux}}$ | 0.06511 |
| $BP$ statistic | 6.251 |
| $\chi^2_{2,\,0.05}$ critical | 5.991 |
| Decision | **Reject $H_0$** |
| Conclusion | Conditional heteroskedasticity present |

---

## How to Correct for Heteroskedasticity

Rejecting $H_0$ isn't the end of the analysis — it's the start. Three standard fixes:

### 1. Robust standard errors (the go-to fix)

Also called **[[White-corrected standard errors]]** or **heteroskedasticity-consistent standard errors**. These recompute the standard errors using a formula that doesn't assume constant variance. Your slope coefficients don't change — only their standard errors (and therefore t-stats and p-values).

- **When to use:** almost always the default. Easy, requires no structural assumptions about the form of heteroskedasticity.
- **Effect:** standard errors typically *increase* → t-stats *decrease* → fewer predictors look significant, but the ones that survive are more credible.

### 2. Generalized Least Squares (GLS) / Weighted Least Squares (WLS)

Re-weight each observation by the inverse of its estimated error variance so that the transformed regression has homoskedastic errors.

- **When to use:** when you have a specific model for how the variance changes (e.g., $\sigma_i^2 \propto X_i$).
- **Tradeoff:** more efficient than OLS with White-corrected SEs *if* you've got the variance structure right — and worse than OLS if you've got it wrong.

### 3. Model respecification

Sometimes heteroskedasticity is a **symptom** of a misspecified model:

- Omitted variable → residual variance picks up the missing factor's influence.
- Wrong functional form → a log transformation of $Y$ (or $X$) can tame variance that grows with the level.
- Outliers clustered at extreme $X$ values.

Fixing the underlying model is the most principled solution, but often hardest to find.

---

## Comparison to Other Regression Diagnostics

| Test | What it detects | Test statistic | Distribution | Key hypothesis |
|---|---|---|---|---|
| **Breusch–Pagan** | Conditional heteroskedasticity | $n \cdot R^2_{\text{aux}}$ | $\chi^2_k$ | $H_0$: homoskedastic errors |
| **Visual scatterplot** of residuals | Any heteroskedasticity (informal) | — (eyeball) | — | — |
| **[[Durbin-Watson Test\|Durbin–Watson]]** | First-order serial correlation (AR(1)) | $d \approx 2(1-\hat{\rho})$ | Special DW tables | $H_0$: no serial correlation |
| **Breusch–Godfrey** | Serial correlation of any order | $n \cdot R^2$ (different auxiliary regression) | $\chi^2_p$ | $H_0$: no serial correlation |
| **[[Variance inflation factor\|VIF]]** | [[CFA_Glossary/Multicollinearity]] | $\text{VIF}_j = 1/(1-R^2_j)$ | rule of thumb: >5 or >10 | — |

**Key distinction:** Breusch–Pagan and Breusch–Godfrey look deceptively similar — both are "run an auxiliary regression, take $n \cdot R^2$, compare to $\chi^2$." But:

- **BP** regresses **squared residuals** on the $X$'s → tests for heteroskedasticity.
- **BG** regresses **residuals** on the $X$'s **and lagged residuals** → tests for serial correlation.

**Mnemonic:** *Pagan squares; Godfrey lags.*

---

## Common Pitfalls and Exam Traps

1. **Degrees of freedom = $k$, not $n - k - 1$.** The BP df is the number of regressors in the *original* model. Don't confuse it with the residual df from the original regression.
2. **The test is right-tailed.** A small BP statistic is good news (consistent with homoskedasticity). A large one rejects.
3. **BP detects — it does not fix.** After rejecting $H_0$, you still have to apply robust SEs, GLS, or respecify. The test by itself changes nothing.
4. **Coefficients are not biased.** Conditional heteroskedasticity breaks **inference**, not **estimation**. The slope estimates remain consistent and unbiased; only their standard errors are wrong.
5. **BP does not detect serial correlation.** If residuals are autocorrelated but have constant variance, BP will miss it — use [[Breusch-Godfrey Test|Breusch–Godfrey]] or [[Durbin-Watson Test|Durbin–Watson]].
6. **Don't confuse "auxiliary $R^2$" with "original $R^2$."** The $R^2$ in $BP = n \cdot R^2$ is from the Step 2 regression on squared residuals, **not** from the original model.

---

## One-Line Summary

> The Breusch–Pagan test regresses the squared residuals of your model on the same $X$'s, computes $BP = n \cdot R^2$, and compares it to a $\chi^2_k$ critical value — a large statistic means your error variance is tied to the regressors (conditional heteroskedasticity), and you should correct your standard errors before trusting any t-stat.

---

## Related Notes

- [[Heteroskedasticity]]
- [[Homoscedasticity and Heteroscedasticity]]
- [[Conditional heteroskedasticity]]
- [[Unconditional heteroskedasticity]]
- [[Heteroskedasticity-consistent standard errors]]
- [[White-corrected standard errors]]
- [[Robust standard errors]]
- [[Serial Correlation]]
- [[CFA_Glossary/Multicollinearity]]
- [[Hypothesis Testing in Regression]]
- [[F Distribution and F Tests]]
- [[Degrees of Freedom]]

**Tags:** #CFA #CFA-L2 #quantitative-methods #regression #diagnostics #glossary
