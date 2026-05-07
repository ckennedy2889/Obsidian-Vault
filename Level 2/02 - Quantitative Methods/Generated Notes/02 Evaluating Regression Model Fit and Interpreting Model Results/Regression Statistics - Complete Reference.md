---
title: Regression Statistics — Complete Reference
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, ANOVA, statistics, master-reference]
aliases: [Regression Output Statistics, ANOVA Table, Regression Statistics, SST SSR SSE, Regression Output Explained]
---

# Regression Statistics — Complete Reference

## The Real-World Analogy That Anchors Everything

Imagine you're a sports analyst trying to explain a basketball team's season-long point totals using three inputs: **minutes played**, **shot attempts**, and **average opponent defensive rating**. You build a formula that predicts points, then check: how close are my predictions to what actually happened?

You'll discover quickly that there are *many different questions* you want to ask about your model, each one requiring its own number:

- "Overall, how well does my recipe work?" → needs **R²** and **SEE**
- "Did the recipe beat 'no recipe at all' (just guessing the average)?" → needs the **F-statistic**
- "Is *this one specific ingredient* actually doing anything?" → needs **t-stats** and **p-values**
- "Am I being fooled into thinking I've got a great model just because I added more ingredients?" → needs **Adjusted R²**, **AIC**, **BIC**
- "How wrong is my model, on average, in points?" → needs **SEE / RMSE**
- "How much could the true effect of minutes-played realistically be?" → needs **confidence intervals**
- "Are my errors doing something suspicious, like getting bigger for high-scoring teams?" → needs **residual diagnostics**

A regression output table is exactly this — a dashboard of answers to all those questions. Every number on the printout is answering one specific question about trust. Learn to read each number as the answer to a specific question, and the whole table stops looking like noise.

**The spine that holds it all together:** the **sum-of-squares decomposition**. Master that one idea and every other statistic in the output falls out of it as a consequence. We'll build up from there.

---

## LOS This Note Fulfills

You should finish this note able to:

- **Describe** the regression equation and every symbol in it.
- **Decompose** total variation into explained (SSR) and unexplained (SSE) pieces.
- **Calculate and interpret** R², Adjusted R², and SEE/RMSE.
- **Construct and read** the ANOVA table (SS, df, MS, F).
- **Test** the overall significance of a regression via the F-statistic.
- **Test** individual coefficients via t-statistics, p-values, and confidence intervals.
- **Compare** competing models using AIC and BIC.
- **Identify** what each line of a standard regression-output printout represents and which question it answers.
- **Link** every diagnostic back to the deeper OLS assumption it protects.

---

# Part 1 — The Regression Equation

Every regression statistic exists to answer a question about *this one equation*:

$$Y_i = b_0 + b_1 X_{1i} + b_2 X_{2i} + \dots + b_k X_{ki} + \varepsilon_i$$

Why is this the starting point? Because the claim the regression is making is: "the dependent variable $Y$ can be written as a weighted sum of the independent variables plus a leftover wobble." Every statistic we'll meet either (a) measures how true that claim is, or (b) measures how trustworthy one of the weights is.

### Every symbol, explained

| Symbol | Name | What it represents | Why you care |
|---|---|---|---|
| $Y_i$ | **Dependent variable** (target, response, regressand) | The thing you're trying to explain or predict for observation $i$ | This is the outcome the whole exercise is about |
| $X_{ji}$ | **Independent variable** (regressor, predictor, feature) for regressor $j$, observation $i$ | An input factor you think drives $Y$ | These are the "ingredients" |
| $b_0$ | **Intercept** | Predicted value of $Y$ when every $X_j = 0$ | Anchors the regression line; sometimes meaningless (extrapolation), sometimes critical (baseline) |
| $b_1, \dots, b_k$ | **Slope coefficients** (partial regression coefficients) | How much $\hat{Y}$ changes for a one-unit change in $X_j$, **holding all other $X$'s fixed** | The heart of causal/economic interpretation |
| $\varepsilon_i$ | **Error term** (disturbance, true noise) | The part of $Y_i$ that no $X$ in your model explains | Unobservable. We can only *estimate* it via residuals. |
| $k$ | Number of independent variables | Model complexity | Shows up in every degrees-of-freedom formula |
| $n$ | Number of observations | Sample size | Shows up in every degrees-of-freedom formula |

**Why "partial" slope coefficient?** Because in multiple regression, $b_1$ is *not* the slope you'd get from regressing $Y$ on $X_1$ alone. It's what remains of $X_1$'s relationship to $Y$ **after controlling for $X_2, \ldots, X_k$**. This distinction is why [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity|multicollinearity]] matters so much — if $X_1$ and $X_2$ are tangled, "controlling for" becomes impossible.

### Fitted values and residuals

When OLS finishes fitting, you get two derived quantities for every observation:

$$\hat{Y}_i = \hat{b}_0 + \hat{b}_1 X_{1i} + \dots + \hat{b}_k X_{ki} \qquad \text{(fitted value, prediction)}$$

$$e_i = Y_i - \hat{Y}_i \qquad \text{(residual — our estimate of } \varepsilon_i\text{)}$$

**Why the hat?** The hat ($\hat{\phantom{Y}}$) means "estimated from the sample." $b_0$ is the unknowable true parameter; $\hat{b}_0$ is what OLS produces from your data.

**Why is the residual only an *estimate* of the error?** Because the true error $\varepsilon_i$ requires knowing the true population parameters $b_0, b_1, \ldots, b_k$ — which we never observe. We only observe their sample estimates, and therefore only observe the residual $e_i$, not the true error. This is the single most under-emphasized point in introductory regression: **residuals ≠ errors; residuals are our best sample proxy for errors.**

---

# Part 2 — The Sum-of-Squares Decomposition (The Spine)

Why does sum-of-squares get its own whole section? Because *every* fit statistic you'll meet is either a sum of squares, a ratio of sums of squares, or a ratio of transformed sums of squares. Learn this one idea and the rest is bookkeeping.

### The core identity

Take any observation $Y_i$. Its distance from the sample mean $\bar{Y}$ can be split perfectly into two pieces:

$$\underbrace{(Y_i - \bar{Y})}_{\text{total deviation}} = \underbrace{(\hat{Y}_i - \bar{Y})}_{\text{explained by model}} + \underbrace{(Y_i - \hat{Y}_i)}_{\text{residual, unexplained}}$$

**Why does this decomposition hold?** Just add and subtract $\hat{Y}_i$:
$$Y_i - \bar{Y} = (Y_i - \hat{Y}_i) + (\hat{Y}_i - \bar{Y})$$

Now square both sides and sum across all observations. A beautiful OLS property makes the cross-product term zero (because OLS chooses coefficients that make residuals orthogonal to fitted values). The result:

$$\boxed{\underbrace{\sum (Y_i - \bar{Y})^2}_{\text{SST}} = \underbrace{\sum (\hat{Y}_i - \bar{Y})^2}_{\text{SSR}} + \underbrace{\sum (Y_i - \hat{Y}_i)^2}_{\text{SSE}}}$$

**Why squares and not absolute deviations?** Three reasons: (1) squaring makes big errors hurt *disproportionately* (which matches most analysts' preferences — a $100 miss is more than 10× worse than a $10 miss), (2) squares are differentiable, which makes the optimization calculus tractable, (3) under normally distributed errors, OLS with squared deviations is the **Maximum Likelihood Estimator** — a deep statistical justification.

### The three sums, one by one

| Term | Name(s) | Formula | What it is |
|---|---|---|---|
| **SST** | Sum of Squares Total (also TSS) | $\sum (Y_i - \bar{Y})^2$ | The **total variation** in $Y$. The "pie" we want to divide up. Equals $(n-1) \cdot s_Y^2$ where $s_Y^2$ is the sample variance of $Y$. |
| **SSR** | Sum of Squares Regression (also ESS = Explained Sum of Squares; sometimes "RSS = Regression SS" in some texts) | $\sum (\hat{Y}_i - \bar{Y})^2$ | The **explained** piece — how much of $Y$'s variation is captured by the model |
| **SSE** | Sum of Squares Error (also SSR = Sum of Squared Residuals in some texts; sometimes "RSS = Residual SS") | $\sum (Y_i - \hat{Y}_i)^2 = \sum e_i^2$ | The **unexplained** piece — the leftover wobble, the penalty OLS minimized |

### The notation-conflict landmine

This is a genuine source of confusion on the exam:

> Some textbooks write **RSS** meaning **R**egression SS (= our SSR, the explained piece).
> Other textbooks write **RSS** meaning **R**esidual SS (= our SSE, the unexplained piece).
> These mean **opposite things.**

**CFA curriculum convention** (the one to memorize):

- **SSR = Sum of Squares Regression** = **E**xplained
- **SSE = Sum of Squares Error** = Residual / Unexplained
- **SST = Sum of Squares Total** = the whole pie

Mnemonic to avoid flipping: **"R is what the Regression explains; E is the Error that's left over; T is the Total pie."** If you see "RSS" in a foreign text, stop and check which of the two it means by context (is it in the numerator of R²? Then it's the explained one).

### The fundamental identity

$$\boxed{SST = SSR + SSE}$$

"The total pie = the slice I explained + the slice I didn't." Every fit statistic rides on this identity.

### Visualizing the pie

```
  SST  =  SSR  +  SSE
 ┌─────────────────────────────┐
 │                             │
 │   [  SSR (explained)  ]     │ ← Bigger SSR = model works
 │                             │
 │   [  SSE (residual)  ]      │ ← Bigger SSE = model missed
 │                             │
 └─────────────────────────────┘
        Total variation
```

---

# Part 3 — Model-Fit Statistics (Overall Goodness)

These answer: "how good is my recipe overall?"

## 3.1 Coefficient of Determination — R²

$$\boxed{R^2 = \frac{SSR}{SST} = 1 - \frac{SSE}{SST}}$$

**Why two formulas?** They are algebraically identical (since $SSR = SST - SSE$). Use whichever your output table gives you directly.

**Interpretation:** the **proportion of variation in $Y$ explained by the model**. If $R^2 = 0.82$, the model explains 82% of the variation in $Y$; 18% is noise the model can't capture.

**Range:** $0 \leq R^2 \leq 1$ (in a regression with an intercept).

**Why is R² always ≥ 0 when there's an intercept?** Because the intercept guarantees the model is at least as good as predicting the sample mean, which has $SSR = 0$ and $R^2 = 0$.

**Why is R² ≤ 1?** Because $SSR \leq SST$ — you can't explain more variation than exists.

### The problem with R² alone

**Why we can't trust R² as a standalone quality score:** $R^2$ mechanically **never decreases** when you add an independent variable to the model — even a garbage variable. Add a variable of pure random noise and $R^2$ will rise (or stay exactly the same); it can *never* fall.

**Why?** Because OLS is free to set the new coefficient to 0 if the variable is useless, recovering the original $R^2$ exactly. But usually it finds some tiny non-zero value that fits the noise a hair better, bumping $R^2$ up. So comparing $R^2$ across models with different numbers of regressors is unfair — the bigger model will always win on $R^2$ even when it shouldn't.

That's why we need Adjusted R².

## 3.2 Adjusted R² (R̄² or "R-bar squared")

$$\boxed{\bar{R}^2 = 1 - \left(\frac{n-1}{n-k-1}\right)(1 - R^2)}$$

**Why this formula?** It penalizes the model for each additional regressor ($k$) by shrinking the fraction of "available degrees of freedom" relative to the denominator. Adding a useless regressor raises $R^2$ a tiny bit but raises the penalty more — so $\bar{R}^2$ actually **falls**.

**Interpretation:** the R² that "would have been" fair if you'd accounted for how many variables you used.

**Key facts:**
- $\bar{R}^2 \leq R^2$ always (equality only when $k = 0$).
- $\bar{R}^2$ can be **negative** (if the model fits worse than predicting the mean, after penalty).
- $\bar{R}^2$ rises when you add a variable *only if* the t-stat on that variable exceeds about 1 in absolute value — a very low bar, so $\bar{R}^2$ is a weak penalty.

**Why use it:** for comparing models with different numbers of regressors.

→ Full treatment: [[R-Squared and Adjusted R-Squared]].

## 3.3 Standard Error of the Estimate (SEE / SER / RMSE)

Three names, one statistic:

| Name | Where you'll see it |
|---|---|
| **Standard Error of the Estimate (SEE)** | CFA curriculum |
| **Standard Error of Regression (SER)** | Some econometrics texts |
| **Root Mean Squared Error (RMSE)** | Statistics / data-science output |

All the same number:

$$\boxed{\text{SEE} = \sqrt{\frac{SSE}{n-k-1}} = \sqrt{\text{MSE}}}$$

**What it is:** the standard deviation of the residuals, corrected for degrees of freedom.

**Why divide by $n - k - 1$ and not $n$?** Because you burned $k+1$ degrees of freedom estimating $b_0, b_1, \ldots, b_k$. With $k+1$ parameters estimated from $n$ points, only $n - k - 1$ independent "pieces of residual information" remain. Dividing by $n - k - 1$ produces an **unbiased** estimate of the true error variance $\sigma^2$. Dividing by $n$ would systematically understate it.

**Interpretation:** "on average, my predictions are off by SEE units of $Y$." If $Y$ is measured in dollars and SEE = $3.44, then typical prediction error is about $3.44.

**Why it matters:** unlike $R^2$, SEE is in the **same units** as $Y$, so it's directly interpretable. SEE = $0.10 tells you more about whether the model is economically useful than $R^2 = 0.82$ ever could.

**Relationship to confidence intervals:** SEE feeds directly into the standard errors of each coefficient, which in turn drive confidence intervals and t-stats. SEE is the "noise" that OLS has to fight through.

---

# Part 4 — The ANOVA Table and the F-Statistic

The ANOVA (Analysis of Variance) table is a structured presentation of the sum-of-squares decomposition, with everything needed to run the overall F-test.

## 4.1 Mean squares

The "mean" in Mean Squares is the "variance per degree of freedom" interpretation:

| Statistic | Formula | Degrees of freedom | Meaning |
|---|---|---|---|
| **MSR** (Mean Square Regression) | $SSR / k$ | $k$ | Explained variation per regressor |
| **MSE** (Mean Square Error) | $SSE / (n - k - 1)$ | $n - k - 1$ | Unexplained variation per residual df. Equals $\text{SEE}^2$. |

**Why divide SSR by $k$ and not by something else?** Because SSR "used up" $k$ degrees of freedom — one for each of the $k$ slope coefficients. The intercept $b_0$ doesn't count here because SSR is measured relative to $\bar{Y}$, which already absorbs the intercept.

**Why divide SSE by $n - k - 1$?** You have $n$ data points; you consumed $k + 1$ degrees of freedom fitting intercept + $k$ slopes; what's left is $n - k - 1$.

## 4.2 The F-statistic

$$\boxed{F = \frac{MSR}{MSE} = \frac{SSR / k}{SSE / (n - k - 1)}}$$

**What it tests:** the **joint significance** of the entire model — "do *all* my independent variables, together, explain any of $Y$, or are they all useless?"

**Hypotheses:**

- $H_0$: $b_1 = b_2 = \cdots = b_k = 0$ (all slopes zero → model explains nothing)
- $H_a$: at least one $b_j \neq 0$

**Distribution under $H_0$:** $F \sim F_{k,\,n-k-1}$ — an F-distribution with $k$ numerator degrees of freedom and $n-k-1$ denominator degrees of freedom.

**Decision rule:** one-tailed right-side test. Reject $H_0$ if $F > F_{\text{critical}}$.

**Why right-tailed?** Because $F$ is a ratio of positive quantities; large $F$ means "explained variance >> unexplained variance" — exactly the evidence against $H_0$.

**Why not just check the individual t-stats?** Because individual t-tests each risk a Type I error; running $k$ of them inflates the overall false-positive rate. The F-test tests the *joint* null with a single, clean statistic.

**Classic "F/t paradox":** significant F-stat but no significant t-stats → the F says "as a group you matter" but no individual variable looks important → prime suspect: [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity|multicollinearity]]. See also [[Variance Inflation Factor (VIF)]].

## 4.3 The canonical ANOVA table

```
+-------------+--------------+----------------+----------------+---------------------+
| Source      |    df        |       SS       |      MS        |        F            |
+-------------+--------------+----------------+----------------+---------------------+
| Regression  |    k         |      SSR       |  MSR = SSR/k   |                     |
| Error       |  n - k - 1   |      SSE       | MSE = SSE/df   |  F = MSR / MSE      |
| Total       |   n - 1      |      SST       |                |                     |
+-------------+--------------+----------------+----------------+---------------------+
```

**Why do the df columns always add up ($k + (n - k - 1) = n - 1$)?** Because SST has $n - 1$ df (you only lose one to estimating $\bar{Y}$), and SST = SSR + SSE, so the df must split the same way.

---

# Part 5 — Individual Coefficient Statistics

These answer: "is *this one specific variable* doing anything?"

## 5.1 Standard error of a coefficient, $SE(\hat{b}_j)$

$$SE(\hat{b}_j) = \sqrt{\frac{\text{MSE}}{(n-1) \cdot s_{X_j}^2 \cdot (1 - R_j^2)}}$$

**What it measures:** the uncertainty (standard deviation of the sampling distribution) around the estimated coefficient $\hat{b}_j$.

**Why each piece is there (asking "why" to each term):**

- **MSE in numerator:** more residual noise → more uncertainty about coefficients. Obvious.
- **$n - 1$ in denominator:** more data → less uncertainty. Obvious.
- **$s_{X_j}^2$ in denominator:** more variation in $X_j$ → regression has more leverage to pin down its slope. If every $X_j$ were the same value, you'd have *no* slope information at all.
- **$(1 - R_j^2)$ in denominator:** this is the [[Variance Inflation Factor (VIF)|VIF]] term. $R_j^2$ is from an auxiliary regression of $X_j$ on the other $X$'s. If $X_j$ is collinear with the other regressors, $R_j^2 \to 1$, the term vanishes, and the standard error **explodes**.

## 5.2 The t-statistic for each coefficient

$$\boxed{t_j = \frac{\hat{b}_j - b_j^{\text{hypothesized}}}{SE(\hat{b}_j)}}$$

Almost always the hypothesized value is 0 (testing "does this variable matter at all?"), so:

$$t_j = \frac{\hat{b}_j}{SE(\hat{b}_j)}$$

**Degrees of freedom:** $n - k - 1$.

**Decision rule:** two-tailed test at significance level $\alpha$. Reject $H_0: b_j = 0$ if $|t_j| > t_{\alpha/2,\,n-k-1}$.

**Rule of thumb for quick eyeballing:** with $n$ reasonably large (say $n > 30$), $t \geq 2$ in absolute value is roughly significant at the 5% level.

**Why the hypothesized value is in the formula:** so you can test *any* null, not just zero. If you want to test whether a stock's CAPM beta equals 1, plug $b_j^{\text{hyp}} = 1$ and ask "is the estimate far from 1 relative to its uncertainty?"

## 5.3 p-value

**Definition:** the probability, assuming $H_0$ is true, of observing a test statistic at least as extreme as the one computed.

**Interpretation:** the "surprise meter." A small p-value means "if the null were true, getting this result would be very surprising, so the null is probably wrong."

**Decision rule:** reject $H_0$ if $p < \alpha$.

**Common thresholds:**

| p-value | Conventional interpretation |
|---|---|
| $< 0.01$ | Very strong evidence against $H_0$ |
| $< 0.05$ | Strong evidence (standard exam threshold) |
| $< 0.10$ | Marginal evidence |
| $\geq 0.10$ | Insufficient evidence |

**Why p-value is the preferred reporting format:** it lets every reader apply their own $\alpha$, rather than being locked into the analyst's choice.

→ Full treatment: [[P-Value]].

## 5.4 Confidence interval for a coefficient

$$\boxed{\hat{b}_j \pm t_{\alpha/2,\,n-k-1} \cdot SE(\hat{b}_j)}$$

**Interpretation:** a range that, if we repeated the sampling procedure many times, would contain the true $b_j$ roughly $(1 - \alpha) \cdot 100\%$ of the time.

**Decision-rule equivalent:** if zero is *outside* the CI, the coefficient is statistically significant at level $\alpha$. **The CI and the t-test are mathematically the same test, expressed two different ways.**

**Why analysts prefer CIs over just p-values:** a CI tells you *how big* the effect could plausibly be, not just whether it's statistically nonzero. "Significant" could mean "huge" or "microscopic"; the CI disambiguates.

---

# Part 6 — Information Criteria: AIC and BIC

Answer the question: "I'm comparing several models. Which is best — accounting for the fact that a more complex model always fits the sample better?"

## 6.1 The formulas

$$\text{AIC} = n \ln\!\left(\frac{SSE}{n}\right) + 2(k + 1)$$

$$\text{BIC} = n \ln\!\left(\frac{SSE}{n}\right) + \ln(n) \cdot (k + 1)$$

**Why these specific forms?** Both have the same "fit" term $n \ln(SSE/n)$ — which gets smaller as SSE gets smaller (better fit → smaller AIC/BIC). The differences live entirely in the **penalty term** for complexity:

- AIC's penalty is $2(k+1)$ — constant per parameter.
- BIC's penalty is $\ln(n) \cdot (k+1)$ — grows with sample size.

**Why ln(n) for BIC?** Because BIC is derived from Bayesian posterior-probability arguments, and the $\ln(n)$ factor drops out of the mathematics. Once $n > e^2 \approx 7.4$, BIC's penalty exceeds AIC's — so for any realistic sample size, BIC is *harsher* on complexity than AIC.

## 6.2 When to use which

| Criterion | Use when your goal is… | Why |
|---|---|---|
| **AIC** | **Prediction** — finding the model that forecasts best on new data | Lighter penalty → keeps more borderline-useful variables, which helps out-of-sample fit |
| **BIC** | **Explanation / parsimony** — finding the *true* model | Heavier penalty → favors simpler models, more consistent in recovering the correct sparse model as $n \to \infty$ |

## 6.3 Decision rule

**Lower is better for both.** Pick the model with the smallest AIC (for forecasting) or smallest BIC (for parsimony).

→ Full treatment: [[AIC and BIC]].

---

# Part 7 — Residuals and Diagnostic Stats

Regression output usually includes at least one residual diagnostic. The big three:

## 7.1 Durbin–Watson statistic (DW)

$$DW = \frac{\sum_{i=2}^{n}(e_i - e_{i-1})^2}{\sum_{i=1}^{n} e_i^2} \approx 2(1 - \hat{\rho})$$

where $\hat{\rho}$ is the estimated first-order autocorrelation of residuals.

| DW value | Meaning |
|---|---|
| $\approx 2$ | No first-order serial correlation (good) |
| $< 2$ | Positive serial correlation (common in time-series regressions) |
| $> 2$ | Negative serial correlation (rarer) |
| $\approx 0$ | Strong positive autocorrelation |
| $\approx 4$ | Strong negative autocorrelation |

**Why you see this on every regression output:** positive serial correlation *deflates* standard errors and *inflates* t-stats, producing false positives — it's the most common inference-breaking flaw in time-series regressions.

→ Full treatment: [[Serial Correlation]].

## 7.2 Breusch–Pagan (BP) test

Tests for conditional heteroskedasticity. Computes $BP = n \cdot R^2_{\text{aux}}$ from a regression of squared residuals on the $X$'s; compares to $\chi^2_k$.

→ Full treatment: [[Breusch–Pagan test]].

## 7.3 Residuals themselves

Always worth plotting. A well-behaved residual plot looks like uniform random noise around zero. Patterns (fan shape, systematic drift, clumps) are each symptoms of a specific OLS violation — see [[Homoscedasticity and Heteroscedasticity]].

---

# Part 8 — An Annotated Regression Output Table

Here is what a typical regression output looks like, with every number labeled.

### Block 1: Regression Statistics (the summary box)

| Line | Example value | What it is | Formula |
|---|---|---|---|
| Multiple R | 0.907 | Correlation between $\hat{Y}$ and $Y$ | $\sqrt{R^2}$ |
| **R-Squared** | 0.823 | Proportion of $Y$'s variation explained | $SSR/SST$ |
| **Adjusted R-Squared** | 0.817 | R² penalized for $k$ | $1 - \frac{n-1}{n-k-1}(1-R^2)$ |
| **Standard Error** | 3.438 | SEE — typical prediction error in $Y$ units | $\sqrt{SSE/(n-k-1)}$ |
| Observations | 96 | Sample size $n$ | — |

### Block 2: ANOVA

| Source | df | SS | MS | F | Signif. F |
|---|---|---|---|---|---|
| Regression | $k = 3$ | 5058.43 | $MSR = 1686.1$ | 142.63 | 0.000 |
| Residual | $n - k - 1 = 92$ | 1087.62 | $MSE = 11.82$ | | |
| Total | $n - 1 = 95$ | 6146.05 | | | |

"Significance F" = the p-value of the overall F-test. "0.000" means < 0.001 — the model is jointly highly significant.

### Block 3: Coefficients table

| Variable | Coefficient | Std Error | t-stat | p-value | Lower 95% | Upper 95% |
|---|---|---|---|---|---|---|
| Intercept | 2.15 | 0.87 | 2.47 | 0.015 | 0.42 | 3.88 |
| $X_1$ (GDP) | 1.42 | 0.38 | 3.74 | 0.000 | 0.67 | 2.17 |
| $X_2$ (Rates) | -0.88 | 0.29 | -3.03 | 0.003 | -1.46 | -0.30 |
| $X_3$ (Infl) | 0.04 | 0.15 | 0.27 | 0.788 | -0.26 | 0.34 |

Reading it:
- Intercept significant at 5% (p = 0.015).
- GDP and Rates highly significant (p < 0.01).
- Inflation is **not** significant (p = 0.788, CI crosses zero) — it's consistent with having no effect on $Y$ in this model.

---

# Part 9 — Worked Numerical Example: Computing the Whole ANOVA Table

**Setup:** an analyst regresses portfolio returns on $k = 5$ factors, with $n = 50$ observations. The software reports: $SSR = 90.6234$, $SSE = 56.6182$.

### Step 1 — SST from the identity

$$SST = SSR + SSE = 90.6234 + 56.6182 = 147.2416$$

### Step 2 — Degrees of freedom

| Source | df |
|---|---|
| Regression | $k = 5$ |
| Error | $n - k - 1 = 50 - 5 - 1 = 44$ |
| Total | $n - 1 = 49$ |

**Check:** $5 + 44 = 49$. ✓

### Step 3 — Mean squares

$$MSR = \frac{SSR}{k} = \frac{90.6234}{5} = 18.1247$$

$$MSE = \frac{SSE}{n - k - 1} = \frac{56.6182}{44} = 1.2868$$

### Step 4 — F-statistic

$$F = \frac{MSR}{MSE} = \frac{18.1247}{1.2868} = 14.0853$$

**Critical value:** $F_{0.05, 5, 44} \approx 2.43$. Since $14.09 \gg 2.43$, **reject $H_0$**. The model is jointly highly significant.

### Step 5 — R²

$$R^2 = \frac{SSR}{SST} = \frac{90.6234}{147.2416} = 0.6155 \;\;(61.55\%)$$

### Step 6 — Adjusted R²

$$\bar{R}^2 = 1 - \frac{n-1}{n-k-1}(1-R^2) = 1 - \frac{49}{44}(1 - 0.6155)$$
$$= 1 - 1.1136 \times 0.3845 = 1 - 0.4282 = 0.5718 \;\;(57.18\%)$$

### Step 7 — SEE

$$\text{SEE} = \sqrt{MSE} = \sqrt{1.2868} = 1.1344$$

### Compiled ANOVA table

| Source | df | SS | MS | F |
|---|---|---|---|---|
| Regression | 5 | 90.6234 | 18.1247 | 14.0853 |
| Error | 44 | 56.6182 | 1.2868 | |
| Total | 49 | 147.2416 | | |

**Summary:** $R^2 = 0.6155$, $\bar{R}^2 = 0.5718$, SEE = 1.1344. Model jointly significant at p < 0.001.

---

# Part 10 — The Everything-in-One-Place Reference

| Statistic | Formula | What it answers | Rule of thumb |
|---|---|---|---|
| **SST** | $\sum (Y_i - \bar{Y})^2$ | Total variation in $Y$ | — |
| **SSR** | $\sum (\hat{Y}_i - \bar{Y})^2$ | Explained variation | — |
| **SSE** | $\sum (Y_i - \hat{Y}_i)^2$ | Unexplained variation | Smaller = better fit |
| **R²** | $SSR/SST$ | % of variation explained | Higher = better, but beware greediness |
| **Adj. R²** | $1 - \frac{n-1}{n-k-1}(1-R^2)$ | R² fair across models with different $k$ | Higher = better, penalizes complexity |
| **SEE / RMSE** | $\sqrt{SSE/(n-k-1)}$ | Typical error in $Y$-units | Smaller = better |
| **MSR** | $SSR/k$ | Explained variance per df | Numerator of F |
| **MSE** | $SSE/(n-k-1)$ | Unexplained variance per df | Denominator of F; = SEE² |
| **F** | $MSR/MSE$ | Joint significance of all slopes | Reject $H_0$ if $F > F_{\text{crit}}$ |
| **t-stat (coefficient)** | $\hat{b}_j / SE(\hat{b}_j)$ | Significance of one coefficient | $|t| > 2$ ≈ significant at 5% |
| **SE(b̂_j)** | $\sqrt{\frac{MSE}{(n-1)s_{X_j}^2(1-R_j^2)}}$ | Uncertainty in $\hat{b}_j$ | Small = precise estimate |
| **p-value** | $P(\text{data or more extreme} \mid H_0)$ | Probability the null could produce this | Reject if $p < \alpha$ |
| **95% CI for b_j** | $\hat{b}_j \pm t_{0.025,\,n-k-1} \cdot SE(\hat{b}_j)$ | Range of plausible true values | If 0 outside → significant |
| **AIC** | $n\ln(SSE/n) + 2(k+1)$ | Model-comparison for prediction | Lower = better |
| **BIC** | $n\ln(SSE/n) + \ln(n)(k+1)$ | Model-comparison for parsimony | Lower = better |
| **DW** | $\sum (e_i - e_{i-1})^2 / \sum e_i^2$ | First-order serial correlation | ≈ 2 = clean |
| **VIF** | $1/(1 - R_j^2)$ | Multicollinearity penalty | > 10 = serious |
| **BP** | $n \cdot R^2_{\text{aux}}$ | Heteroskedasticity test | > $\chi^2_{k,\alpha}$ → reject homosked. |

---

# Part 11 — The Diagnostic Triangle: Which Statistic Tells You About Which Violation

| OLS Violation | Primary diagnostic | Effect on SEs | Primary fix |
|---|---|---|---|
| [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] | [[Variance Inflation Factor (VIF)\|VIF]] | **Inflated** | Drop/combine variables |
| [[Homoscedasticity and Heteroscedasticity\|Heteroskedasticity]] | [[Breusch–Pagan test\|BP test]] | Often **deflated** (under conditional) | White/robust SEs |
| [[Serial Correlation]] | Durbin–Watson / Breusch–Godfrey | **Deflated** | Newey–West SEs |

**Memory hook for direction of SE bias:**

- Multicollinearity **puffs up** SEs → you become too timid (miss real effects).
- Serial correlation **squashes** SEs → you become too reckless (false positives).

---

# Part 12 — Memory Hooks & Exam Tips

### Memory hooks

- **"SST = SSR + SSE"** — the master identity. Every fit statistic is built from these three.
- **"R is Regression, E is Error, T is Total"** — disambiguates SSR from SSE from SST.
- **"R² is greedy, Adjusted R² is fair"** — explains why you need both.
- **"F says yes, t says no → check VIF"** — multicollinearity paradox.
- **"df is the rent you pay for each parameter"** — you always lose $k+1$ df fitting intercept + slopes.
- **"Same units as Y"** — SEE is in Y-units; $R^2$ is unitless. Both tell different stories.
- **"AIC predicts, BIC parsimonizes"** — which criterion for which goal.
- **"DW near 2 is serene"** — rhymes, sticks.

### Common exam traps

1. **SSR vs SSE confusion.** Know CFA convention: **S**S**R** = **R**egression (explained); **SSE** = **E**rror (residual).
2. **Degrees of freedom.** Error df is $n - k - 1$, not $n - k$ (intercept counts!).
3. **R² "can only go up."** True mechanically; that's why we need Adjusted R².
4. **"Significant F, insignificant t's" is multicollinearity.** Not heteroskedasticity.
5. **t-test vs F-test.** t tests one coefficient; F tests all slopes jointly.
6. **SEE is in units of Y.** Don't confuse with R² (unitless).
7. **p-value ≠ probability the null is true.** It's the probability of the data given the null.
8. **CI contains 0 ⟺ coefficient is insignificant** at the corresponding level.

---

# Part 13 — Related Notes

**Core companions (expand any statistic above):**
- [[R-Squared and Adjusted R-Squared]] — R², $\bar{R}^2$ in depth
- [[Hypothesis Testing in Regression]] — t-tests, F-tests, p-values
- [[F Distribution and F Tests]] — F-test theory and mechanics
- [[F-Test vs t-Test]] — when to use each
- [[P-Value]]
- [[Degrees of Freedom]]
- [[AIC and BIC]]

**Diagnostics and violations:**
- [[Homoscedasticity and Heteroscedasticity]]
- [[Breusch–Pagan test]]
- [[Serial Correlation]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- [[Variance Inflation Factor (VIF)]]

**Related concepts:**
- [[Ordinary Least Squares]]
- [[Regression Assumptions]]
- [[Homoskedasticity]]
- [[Heteroskedasticity-consistent standard errors]]

---