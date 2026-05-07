---
title: "CFA L2 - Model Misspecification"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, regression, heteroskedasticity, serial-correlation, multicollinearity, model-violations]
aliases: ["Module 1.3", "Regression Violations", "Heteroskedasticity", "Autocorrelation"]
---

# Module 1.3 — Model Misspecification

## When the Machine Breaks

Imagine a perfectly calibrated scale that works well for objects weighing between 1–10 lbs, but systematically under-reads anything heavier. You could use it all day and get results — they'd just be *wrong* in a predictable, hidden way.

That's what misspecification does to a regression model. The model runs. It produces numbers. The t-statistics look impressive. But the standard errors are lying to you, and the significance tests are misleading you into seeing patterns that aren't real (or missing ones that are).

This module covers three ways a regression model can be "broken":
1. **[[Heteroskedasticity]]** — the error variance isn't constant
2. **[[Serial Correlation]]** — the errors are correlated with each other over time
3. **[[CFA_Glossary/Multicollinearity]]** — the [[Independent|independent]] variables are too similar to each other

Each one corrupts your standard errors in a different way, leading to different types of false conclusions.

---

## Violation 1 — Heteroskedasticity

### What It Is

In a well-behaved regression, the residuals (the model's mistakes) should look like random static — a [[Consistent|consistent]] "cloud" of noise with no systematic pattern. This ideal state is called **[[Homoskedasticity|homoskedasticity]]** ("homo" = same, "skedasticity" = scatter).

**[[Heteroskedasticity|Heteroskedasticity]]** breaks this rule: the size of the errors *changes* depending on the value of the [[Independent|independent]] variables. The model is accurate in some regions of the data and wildly inaccurate in others.

There are two types:

| Type | Description | Problem? |
|------|-------------|---------|
| **Unconditional** | Error variance changes, but not related to $X$ | Minor — technically violates assumptions but doesn't break [[Hypothesis|hypothesis]] tests |
| **Conditional** | Error variance directly related to the $X$ variables | Serious — invalidates t-statistics and F-statistics |

[[Conditional heteroskedasticity|Conditional heteroskedasticity]] is the villain you need to know for the exam.

### Visualizing the Fan Shape

The clearest signal of [[Heteroskedasticity|heteroskedasticity]] is a **residual plot** (residuals on the y-axis, fitted values or an [[Independent variable|independent variable]] on the x-axis):

```
Residuals
    │
  + │    ·           ·  ·
    │  ·   ·       ·      ·
    │· · ·   · · ·          ·  ·
  0 │━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
    │· · ·   · · ·          ·  ·
    │  ·   ·       ·      ·
  - │    ·           ·  ·
    └──────────────────────────────→ X
          Heteroskedastic ("Fan")

Residuals
    │
  + │ · · · · · · · · · · · · · · ·
    │· · · · · · · · · · · · · · · ·
  0 │━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
    │· · · · · · · · · · · · · · · ·
  - │ · · · · · · · · · · · · · · ·
    └──────────────────────────────→ X
          Homoskedastic (Ideal — random cloud)
```

The fan shape is the classic signature: as X increases, the spread of residuals widens. The model becomes increasingly unreliable for larger values.

### What Causes It?

Heteroskedasticity typically emerges from:

- **Omitted variables** — you left out a factor that drives variance differently across the range
- **Inappropriate pooling** — mixing two fundamentally different groups (e.g., tech stocks and utility stocks) into one model
- **Wrong functional form** — trying to fit a straight line to a curved relationship
- **Natural variance scaling** — larger companies inherently have more volatile absolute earnings, even if percentage changes are stable

**Real-world finance example:** Modeling stock returns using ESG (carbon footprint) scores. For companies with moderate scores, the model is accurate (small residuals). For companies at the extremes — extremely green or extremely polluting — market reactions are unpredictable, creating a fan of large residuals at the edges.

### Consequences: Why It Matters

Conditional heteroskedasticity doesn't bias your slope coefficients — your $\hat{b}$ estimates remain "correct" on average. But it corrupts the **standard errors**:

- Standard errors become **too small** (underestimated)
- t-statistics become **inflated** (look more significant than they are)
- You commit **Type I errors** — concluding variables are significant when they're not
- F-statistics become unreliable

The model screams "significant!" at you while the signal is actually weak.

### Detection: The Breusch-Pagan Test

The **[[Breusch-Pagan test]]** provides a formal statistical test rather than relying on visual inspection:

**Step 1** — Run your original regression. Collect the residuals $\hat{\epsilon}_i$.

**Step 2** — Square the residuals ($\hat{\epsilon}_i^2$) to make them all positive. Regress these squared residuals on the original independent variables.

**Step 3** — Compute the test statistic:

$$\text{BP Statistic} = n \times R^2_{\text{auxiliary}}$$

This follows a **chi-square distribution** with $k$ degrees of freedom (where $k$ = number of predictors).

**Null hypothesis ($H_0$):** No conditional heteroskedasticity — variance of errors is constant.

If the BP statistic exceeds the critical chi-square value (or the p-value is small), **reject $H_0$**: you have a heteroskedasticity problem.

### The Fix: White's Robust Standard Errors

Once detected, you don't necessarily need to rebuild your model. Instead, **repair** it:

**[[White's robust standard errors]]** (also called heteroskedasticity-consistent or HC standard errors) recalculate the standard errors of your coefficients to be honest about the varying error variance.

The key effect:
- Robust standard errors are typically **larger** than the naive OLS standard errors
- Because $t = \frac{\text{coefficient}}{\text{standard error}}$, larger SE → smaller [[T-statistic|t-statistic]]
- This strips away the fake significance and gives you p-values you can trust

> [!tip] Exam Shortcut
> Question asks: "Heteroskedasticity is detected. What should the analyst do?" Answer: **Use robust (White-corrected) standard errors.** The coefficients don't change — only the standard errors are corrected.

---

## Violation 2 — Serial Correlation

### What It Is

**[[Serial Correlation]]** (also called [[Autocorrelation|autocorrelation]]) occurs when the error terms in your regression are not independent of each other — specifically, when a mistake in one period predicts the mistake in the next period.

In plain English: the model makes a similar type of error again and again, in a predictable sequence. Yesterday's miss gives you a clue about today's miss.

```
Ideal (No Serial Correlation):
  Error(t)    Error(t+1)   Error(t+2)   Error(t+3)
    +2           -1           +3           -2         (random, unpredictable)

Positive Serial Correlation:
  Error(t)    Error(t+1)   Error(t+2)   Error(t+3)
    +2           +3           +4           +2         (errors trend together)

Negative Serial Correlation:
  Error(t)    Error(t+1)   Error(t+2)   Error(t+3)
    +2           -3           +4           -2         (errors alternate signs)
```

**Positive** [[Serial Correlation|serial correlation]] is by far the most common in finance — errors cluster in the same direction.

### What Causes It in Finance?

Serial correlation almost always appears in **time-series data**:

- **Business cycles and macro trends** — a recession causes models to underestimate earnings for multiple quarters in a row
- **Omitted variables** — you left out a trending variable (e.g., interest rates), and its effect bleeds into the residuals as a trend
- **Mis-specified functional form** — you fit a straight line to a series that actually curves

### Consequences: Why It Matters

Like heteroskedasticity, serial correlation doesn't bias your coefficient estimates. But it destroys your inference:

- Standard errors become **too small** (underestimated)
- t-statistics become **inflated**
- Type I errors — you think variables are significant when they aren't
- F-statistics are also unreliable

The key difference from heteroskedasticity: serial correlation is specifically about the *time ordering* of errors, not their size across the range of X.

### Detection: The Durbin-Watson Test

The **[[Durbin-Watson statistic]]** is the classic detection tool:

$$\text{DW} \approx 2(1 - \hat{\rho})$$

Where $\hat{\rho}$ = estimated first-order autocorrelation of residuals.

```
DW Scale:
  0    ─────────────────── 2 ─────────────────── 4
  │                        │                     │
  Positive                 No serial           Negative
  serial                   correlation         serial
  correlation              (ideal)             correlation
```

| DW Value | Conclusion |
|----------|-----------|
| ≈ 2.0 | No serial correlation (ideal) |
| Significantly < 2.0 (e.g., 0.8–1.2) | Positive serial correlation |
| Significantly > 2.0 (e.g., 2.8–3.5) | Negative serial correlation |

> [!warning] DW Test Limitations
> The DW test only detects *first-order* (one-lag) serial correlation. For higher-order patterns, use the Breusch-Godfrey test. Also, DW is inappropriate for AR models (those with lagged dependent variables as predictors).

### The Fix: Newey-West Standard Errors

**[[Newey-West standard errors]]** (also called heteroskedasticity and autocorrelation consistent, or HAC, standard errors) correct for both serial correlation and heteroskedasticity simultaneously.

Like White's correction, they:
- Don't change the slope coefficients
- Inflate the standard errors to be more honest
- Make t-statistics smaller and more reliable

> [!tip] Exam Key
> "Analyst finds serial correlation. Appropriate correction?" → **Newey-West (HAC) standard errors.** Don't change the model; change the standard errors.

**Real-world example:** Predicting a country's quarterly GDP growth based on consumption spending. Because economic trends persist across quarters, a model that misses a downturn in Q1 will likely keep missing it in Q2 and Q3 — a classic positive serial correlation pattern.

---

## Violation 3 — Multicollinearity

### What It Is

**[[CFA_Glossary/Multicollinearity]]** occurs when two or more independent variables in your regression are so highly correlated with each other that the model can't distinguish their individual effects. They're mathematical "twins" — moving together so closely that you can't tell which one is actually driving Y.

```
Without Multicollinearity:
  X₁ → affects Y independently
  X₂ → affects Y independently
  Model can estimate both effects cleanly

With Multicollinearity:
  X₁ ←─── highly correlated ───→ X₂
  Both move together → model can't separate effects
  Coefficients become unreliable
```

### Why It's a Problem

Unlike the previous two violations, [[Multicollinearity|multicollinearity]] doesn't create small standard errors — it creates **enormous** ones:

- Standard errors become **massively inflated**
- t-statistics become **near zero** — every variable looks individually insignificant
- But the [[F-statistic]] and R² may still be high — the *team* of variables explains Y well, but each *individual* player looks useless

This creates the paradoxical situation:
- **High R²** → the model overall fits well
- **Low t-statistics** → no individual variable appears significant

That contradiction is the textbook signature of multicollinearity.

### The "Contradiction" in Action

```
Model predicts stock return using:
  • Growth Index (coeff = 0.8, SE = 2.1, t = 0.38)  ← "insignificant"
  • Value Index  (coeff = 1.2, SE = 1.9, t = 0.63)  ← "insignificant"
  • S&P 500 Index (coeff = 0.5, SE = 3.0, t = 0.17) ← "insignificant"

R² = 0.91  ←  But the model fits amazingly well?!

Explanation: The S&P 500 IS made of growth and value stocks.
All three variables are nearly identical. The model is confused.
```

### Detection

**Method 1 — [[Correlation|Correlation]] Matrix**

Check the pairwise correlations between all your [[Independent|independent]] variables. A [[Correlation|correlation]] above 0.60–0.70 is a warning sign. Above 0.90 is severe.

**Method 2 — [[Variance Inflation Factor (VIF)|Variance Inflation Factor (VIF)]]] Factor (VIF)**

The **[[VIF]]** is the [[Gold standard|gold standard]]. It measures how much the variance (standard error²) of a variable is "inflated" by its [[Correlation|correlation]] with the other variables:

$$\text{VIF}_j = \frac{1}{1 - R^2_j}$$

Where $R^2_j$ = R² from regressing $X_j$ on all other [[Independent|independent]] variables.

| VIF Value | Interpretation |
|-----------|---------------|
| 1.0 | No [[Multicollinearity|multicollinearity]] — completely independent |
| 1–5 | Mild — generally acceptable |
| 5–10 | Moderate — start worrying |
| > 10 | Severe — [[Multicollinearity|multicollinearity]] is a serious problem |

**Real-world example:** An analyst uses Growth Index, Value Index, and S&P 500 as regressors. Since the S&P 500 is literally composed of those growth and value stocks, all three are nearly identical. VIF scores would reach thousands, making individual coefficient estimates meaningless.

### The Fix

The cleanest fix is to **remove one of the highly correlated variables**. Since they contain nearly the same information, dropping one doesn't lose much — the remaining variable picks up all the credit, and standard errors shrink back to normal.

Other options:
- **Combine variables** (e.g., create a ratio or composite index)
- **Collect more data** — [[Multicollinearity|multicollinearity]] is less damaging with large samples
- **Accept it** — if the goal is prediction only (not interpretation of individual coefficients), [[Multicollinearity|multicollinearity]] is less harmful

> [!tip] Exam Shortcut
> The signature: **high R² + low t-stats on multiple variables = multicollinearity**. Detection: VIF > 10. Fix: drop a correlated variable.

---

## The Three Violations Side by Side

| Violation | Effect on Coefficients | Effect on Std. Errors | Key Symptom | Detection | Fix |
|-----------|----------------------|----------------------|-------------|-----------|-----|
| **[[Heteroskedasticity|Heteroskedasticity]]** | Unbiased | Too **small** | Fan-shaped residual plot | Breusch-Pagan test | White robust SEs |
| **[[Serial Correlation|Serial Correlation]]** | Unbiased | Too **small** | Patterns in residuals over time; DW ≠ 2 | [[Durbin-Watson Test|Durbin-Watson test]] | Newey-West SEs |
| **Multicollinearity** | Unreliable | Too **large** | High R², low t-stats | VIF > 10 | Drop a variable |

Notice the asymmetry: [[Heteroskedasticity|heteroskedasticity]] and [[Serial Correlation|serial correlation]] both make standard errors **too small** (leading to false confidence). Multicollinearity makes them **too large** (leading to false insignificance).

---

## Exam Traps

> [!danger] Common Mistakes
> - **Coefficients are still unbiased** with heteroskedasticity and [[Serial Correlation|serial correlation]] — only the inference is broken, not the estimates themselves
> - **Multicollinearity** doesn't bias coefficients either, but makes them unstable and unreliable
> - **DW ≈ 2 is good**, not bad — remember the direction
> - **VIF > 5 = worry; VIF > 10 = problem** — memorize both thresholds
> - **White's SE** fixes heteroskedasticity; **Newey-West SE** fixes both [[Serial Correlation|serial correlation]]on|correlation]] and heteroskedasticity

---

## Related Concepts

- [[Multiple Regression - Basics and Assumptions]] — the OLS assumptions these violations break
- [[Regression Model Fit and Interpretation]] — how violations affect F-tests and R²
- [[Breusch-Pagan Test]] — heteroskedasticity detection
- [[Durbin-Watson Test]] — serial correlation detection
- [[VIF]] — multicollinearity detection
- [[White's Standard Errors]] — heteroskedasticity correction
- [[Newey-West Standard Errors]] — serial correlation + heteroskedasticity correction
- [[Extensions of Multiple Regression]] — what to do when the model structure itself needs to change
