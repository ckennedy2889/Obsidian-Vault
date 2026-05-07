---
title: "CFA L2 - Regression Model Fit and Interpretation"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, regression, ANOVA, R-squared, F-statistic, AIC, BIC]
aliases: ["Module 1.2", "ANOVA Regression", "R-squared", "Model Fit"]
---

# Module 1.2 — Evaluating Regression Model Fit

## The Report Card Problem

Imagine you hired a financial analyst to predict your portfolio's monthly returns. After three months, they show you their model. But how do you know if it's actually *good*? The analyst could just be getting lucky. This is exactly the problem that regression diagnostics solve — they're the **report card** for your prediction machine, telling you not just what it predicted but *how well* it actually worked.

The tools in this module answer three questions:
1. **Is my model doing anything at all?** (F-[[Statistic|statistic]])
2. **How much of the real variation did I explain?** (R² and Adjusted R²)
3. **Is this the best version of my model?** (AIC, BIC)

---

## ANOVA Decomposition: Slicing the Variation Pie

Every [[Multiple Regression]] model starts with a simple but profound idea: the total variation in your outcome variable ($Y$) can be sliced into two pieces — the part your model explains and the part it doesn't.

This slicing is called **ANOVA (Analysis of Variance)** decomposition.

```
TOTAL VARIATION IN Y (SST)
         │
    ┌────┴────┐
    │         │
  SSR        SSE
(Explained) (Unexplained)
```

The relationship is always exact:

$$\text{SST} = \text{SSR} + \text{SSE}$$

### The Three Pieces

**SST — Sum of Squares Total**

This is the "Total Variation Pie." It measures how much the individual data points for $Y$ spread out from their overall average $\bar{Y}$:

$$\text{SST} = \sum_{i=1}^{n}(Y_i - \bar{Y})^2$$

SST represents the entire puzzle you're trying to solve. If SST is large, returns are all over the place. If SST is small, returns cluster tightly around the mean.

**SSR — Sum of Squares Regression**

This is the "Explained Variation." It measures how much of that total spread your model's predicted values capture:

$$\text{SSR} = \sum_{i=1}^{n}(\hat{Y}_i - \bar{Y})^2$$

If you have a great model, SSR will be a large share of SST — your predictions scatter around the mean almost as much as the actual data does.

**SSE — Sum of Squares Error**

This is the "Mystery Part." It's the total of your model's squared mistakes — the gap between what happened and what the model predicted:

$$\text{SSE} = \sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2$$

A perfect model would have SSE = 0. In the real world, SSE is always positive — there's always some variation you can't explain.

> [!tip] Memory Hook
> SST = SSR + SSE reads as: "Total = Explained + Unexplained." Think of it as a budget: your total budget (SST) splits between what you spend wisely (SSR, the part your model accounts for) and what slips through the cracks (SSE, the residual mess you can't explain).

---

## The ANOVA Table

The ANOVA table organizes the three pieces into a structured "report card." Every regression software produces one automatically.

| Source | Degrees of Freedom | Sum of Squares | Mean Squares | F-Statistic |
|--------|-------------------|----------------|-------------|-------------|
| **Regression** | $k$ | SSR | MSR = SSR / $k$ | **MSR / MSE** |
| **Error (Residual)** | $n - k - 1$ | SSE | MSE = SSE / $(n-k-1)$ | |
| **Total** | $n - 1$ | SST | | |

Where:
- $n$ = number of observations
- $k$ = number of independent variables (predictors)
- **Degrees of freedom** = how many "free" data points are left after the model uses up parameters

### Why Divide by Degrees of Freedom?

Raw sums of squares get bigger just by adding more observations. Dividing by degrees of freedom converts them to **Mean Squares (MS)** — an "average" variation per degree of freedom — which allows fair comparison across models of different sizes.

---

## The F-Statistic: The "Overall Usefulness" Test

The **F-statistic** answers one focused question: *Does my model, as a whole, explain anything?*

$$F = \frac{\text{MSR}}{\text{MSE}} = \frac{\text{SSR}/k}{\text{SSE}/(n-k-1)}$$

Think of it as a ratio of signal to noise. MSR is the "average explained variation per variable" — your signal. MSE is the "average unexplained variation per residual degree" — your noise.

### What It Tests

The F-test tests the [[Null Hypothesis]] that **all slope coefficients are simultaneously zero**:

$$H_0: b_1 = b_2 = \dots = b_k = 0$$

In plain English: "Your model is completely useless — none of your inputs matter at all."

The **alternative hypothesis** is that *at least one* coefficient is non-zero — meaning at least one variable has some explanatory power.

### Interpreting the Result

```
Large F-statistic  →  Small p-value  →  Reject H₀
                   →  At least one variable matters
                   →  Model has overall statistical significance

Small F-statistic  →  Large p-value  →  Fail to reject H₀
                   →  Model appears no better than random guessing
```

> [!warning] F-Test vs. t-Tests
> The F-test is an **omnibus test** — it tests all coefficients jointly. Individual **t-tests** test each variable separately. You can have a significant F-statistic (model overall is useful) but some individual variables with insignificant t-stats (certain variables don't independently contribute). Both tests are needed.

---

## R² — The Fit Score

The **[[Coefficient of Determination]] (R²)** is the most popular single measure of how well your model fits the data. It answers: *What percentage of the total variation in Y did my model explain?*

$$R^2 = \frac{\text{SSR}}{\text{SST}} = 1 - \frac{\text{SSE}}{\text{SST}}$$

### Interpretation

| R² Value | Meaning |
|----------|---------|
| 0.00 | Model explains nothing — pure noise |
| 0.50 | Model explains 50% of Y's variation |
| 1.00 | Perfect fit — model explains everything |

R² is bounded between 0 and 1.

```
R² = SSR / SST

Low R²:   SSR tiny, SSE huge   → model misses most of the variation
High R²:  SSR large, SSE tiny  → model captures most of the variation
```

### The Fatal Flaw of R²

R² has a dangerous property in [[Multiple Regression]]: **it always increases (or stays the same) when you add more variables**, even if those variables are completely random garbage.

This is because adding a variable, even a useless one, lets the model soak up a tiny bit of SSE by sheer luck. The equation $\text{SST} = \text{SSR} + \text{SSE}$ means SSR can only go up as SSE shrinks — never down.

This creates an incentive to "pad" your model with variables to artificially inflate R², a form of [[overfitting]].

---

## Adjusted R² — The Filter

**[[Adjusted R-squared]] ($\bar{R}^2$)** solves R²'s inflation problem by penalizing model complexity. It incorporates both the number of observations ($n$) and the number of variables ($k$):

$$\bar{R}^2 = 1 - \left[\frac{n-1}{n-k-1}\right](1 - R^2)$$

The adjustment factor $\frac{n-1}{n-k-1}$ is always $\geq 1$, which means the penalty makes $(1 - R^2)$ larger — shrinking $\bar{R}^2$ below $R^2$.

### When Does Adjusted R² Go Up vs. Down?

- **Goes up** when you add a variable whose t-statistic has absolute value $> 1.0$ — the variable earns its spot
- **Goes down** when you add a variable with $|t| < 1.0$ — the variable's noise outweighs its signal

> [!tip] Rule of Thumb
> If adding a variable *decreases* Adjusted R², drop it. The simpler model is better.

**Real-world example:** A manager predicting a company's Return on Assets using capital expenditure (CAPEX). If they add the advertising budget and it has no real relationship to ROA, Adjusted R² drops, signaling the simpler model was better.

---

## AIC and BIC — Choosing Between Competing Models

When you have several different candidate models (different combinations of variables), you need a systematic way to pick the best one. **AIC (Akaike's Information Criterion)** and **BIC (Schwarz's Bayesian Information Criterion)** are that system.

Both start from the model's unexplained error (SSE) and add a **complexity penalty** for each additional variable:

$$\text{AIC} = n\ln\!\left(\frac{\text{SSE}}{n}\right) + 2(k+1)$$

$$\text{BIC} = n\ln\!\left(\frac{\text{SSE}}{n}\right) + \ln(n)(k+1)$$

### The Key Difference

The AIC penalty for each variable is a flat $2$. The BIC penalty is $\ln(n)$, which grows with sample size. For any dataset with $n > 7.4$ (i.e., practically always), $\ln(n) > 2$, so **BIC penalizes complexity more harshly than AIC**.

```
AIC penalty:  2 per variable   (constant, mild)
BIC penalty:  ln(n) per variable (grows with sample size, strict)
```

### Which to Use?

| Criterion | Lower Is Better | Use When |
|-----------|----------------|----------|
| **AIC** | Yes | Goal is accurate **prediction** — you want the most predictive model |
| **BIC** | Yes | Goal is **explanatory parsimony** — you want the simplest model that fits |

**Real-world example:** A portfolio manager comparing 31 factor combinations to explain fund returns. The 4-factor model might have the lowest AIC (best for forecasting next month), while the 1-factor model has the lowest BIC (the most conservative, reliable explanation of the past).

> [!danger] Direction of Preference
> Unlike R² and Adjusted R² (where higher is better), **lower AIC and lower BIC are always preferred**. Don't flip the direction on the exam.

---

## Predictions and Prediction Intervals

Once you have a model, you can plug in new values to forecast $Y$. But a single-point forecast without any measure of uncertainty is dangerously misleading. The honest answer is a **prediction interval**.

### Point Forecast

Plug your chosen values of $X$ into the fitted regression equation:

$$\hat{Y}_f = \hat{b}_0 + \hat{b}_1X_{1f} + \hat{b}_2X_{2f} + \cdots$$

### Prediction Interval

The interval accounts for two layers of uncertainty:

$$\text{Prediction Interval} = \hat{Y}_f \pm (t_c \times s_f)$$

Where:
- $t_c$ = critical t-value for your confidence level (e.g., 1.96 for 95%, large $n$)
- $s_f$ = **standard error of the forecast** — a measure of total uncertainty

The standard error of the forecast is *wider* than the standard error of the model itself because it must account for:
1. **Model error** — the model isn't perfect
2. **Sampling error** — the input values you're forecasting with are themselves uncertain

```
True value
    │
    ├── Upper bound: Ŷf + (tc × sf)
    │
   [Ŷf]  ← Point estimate
    │
    └── Lower bound: Ŷf - (tc × sf)
```

**Real-world example:** A model predicts a bond index will return −2.10% next month. The 95% prediction interval runs from −4.41% to +0.21%. This tells the client: "We expect a loss, but there's still a small chance the return could be positive."

> [!warning] Confidence Interval vs. Prediction Interval
> A **confidence interval** bounds the *mean response* — the average $Y$ for all observations with those inputs. A **prediction interval** bounds a *single future observation* — it is always wider. On the exam, when they ask about forecasting a specific value, use the prediction interval.

---

## Putting It All Together: A Portfolio Manager Example

A portfolio manager wants to explain monthly returns of a 50-stock fund using five factors (market return, size, value, momentum, quality) over 50 months.

**ANOVA results:**
- SST = 147.24 (total wobble in returns)
- SSR = 90.62 (what the five factors explained)
- SSE = 56.62 (what's still a mystery)

**Calculations:**
$$R^2 = \frac{90.62}{147.24} = 0.6155$$

The five factors explain **61.55%** of the fund's monthly return variation.

$$F = \frac{90.62/5}{56.62/(50-5-1)} = \frac{18.12}{1.285} = 14.10$$

With an F-[[Statistic|statistic]] of 14.10 far exceeding the critical value (~2.4 for this sample size), the manager can confidently conclude the factors are driving returns — not luck.

**If they add a sixth "junk" variable** (say, average monthly rainfall):
- R² goes up slightly (it always does)
- Adjusted R² likely drops (the variable's t-stat is near zero)
- [[AIC and BIC|AIC and BIC]] both increase (model is more complex but not more accurate)

The diagnostics correctly signal: **keep the 5-factor model**.

---

## Exam Traps

> [!danger] Watch Out For
> - **F-test vs. t-tests**: F tests *all* coefficients jointly; t tests each *individually*. You need both.
> - **R² always rises**: Adding junk variables never decreases R². Only Adjusted R² can fall.
> - **Lower AIC/BIC is better**: Direction is opposite to R².
> - **Prediction interval > Confidence interval**: Forecasting a *single* observation is always more uncertain than estimating the *mean* response.
> - **[[Degrees of Freedom|Degrees of freedom]]**: Regression df = $k$, Error df = $n - k - 1$, Total df = $n - 1$.

---

## Related Concepts

- [[Multiple Regression - Basics and Assumptions]] — the model this module evaluates
- [[Model Misspecification]] — what happens when the model structure is wrong
- [[F-Statistic]] — the formal [[Hypothesis|hypothesis]] test covered here
- [[Adjusted R-Squared]] — the corrected fit measure
- [[AIC]] / [[BIC]] — model selection criteria
- [[Overfitting]] — the problem Adjusted R², AIC, and BIC all guard against
