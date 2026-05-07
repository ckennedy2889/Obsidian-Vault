---
title: F Distribution and F Tests
subject: Quantitative Methods
tags:
  - CFA-L2
  - quantitative-methods
  - statistics
  - hypothesis-testing
  - regression
aliases:
  - F-test
  - F distribution
  - variance ratio test
  - ANOVA F-test
---

# F Distribution and F Tests

## The Core Intuition: A Competition Between Two Variances

Picture two archers shooting at targets. Archer A's arrows are scattered widely — high variance. Archer B's arrows cluster tightly — low variance. You want to know: is Archer A's variance *genuinely* higher, or could the difference just be random noise from a small sample?

That's exactly the question the F-test answers. At its heart, an F-test is always a **ratio of two variances** — it asks whether the variance in the numerator is meaningfully larger than the variance in the denominator, or whether they're plausibly equal. Everything else is just context for what those two variances represent.

---

## Building the F Distribution from First Principles

To understand where the F distribution comes from, you need to know one thing about the [[Chi-Squared Distribution]]: if you take a random sample of $n$ observations from a normal population and compute the sample variance $s^2$, then the quantity

$$\frac{(n-1)s^2}{\sigma^2} \sim \chi^2(n-1)$$

is chi-squared distributed with $n-1$ degrees of freedom. In plain English: scaled sample variances follow a chi-squared distribution.

Now suppose you have **two independent** chi-squared random variables:

$$X \sim \chi^2(m) \qquad Y \sim \chi^2(n)$$

The ratio of these two variables, each divided by their own degrees of freedom, defines the F distribution:

$$F = \frac{X/m}{Y/n} \sim F(m,\ n)$$

The two parameters — $m$ (numerator degrees of freedom) and $n$ (denominator degrees of freedom) — fully characterize the shape. Since both chi-squared variables are always non-negative, $F$ is always $\geq 0$. The distribution is **right-skewed**, with the bulk of probability mass near 1 (when the two variances are equal) and a long right tail (when the numerator variance is much larger).

```
F Distribution Shape (right-skewed, always ≥ 0)

Probability
│
│  ████
│ ██████
│ ████████
│ ██████████
│ █████████████
│ ████████████████████
│ ██████████████████████████████████████████
└─────────────────────────────────────────────── F value
0    1    2    3    4    5    6
        ↑
   Most mass near 1
   (when variances are equal)
```

As both degrees of freedom grow large, the F distribution approaches a normal shape and becomes approximately symmetric. For small degrees of freedom (common in practice), it's heavily skewed.

> [!tip] Memory Hook: F = Fight between Two Variances
> The F statistic always pits two variances against each other. **Numerator on top = the thing you're testing**. Denominator = the baseline or error. If F is much greater than 1, the numerator variance is suspiciously large relative to the baseline.

---

## The Two Main Uses in CFA Level 2

The F-test appears in two distinct but related contexts in the curriculum:

| Use Case | What's Being Tested | Numerator Variance | Denominator Variance |
|---|---|---|---|
| **Equality of Two Variances** | Are two population variances equal? | Larger sample variance $s_1^2$ | Smaller sample variance $s_2^2$ |
| **Overall Regression Significance** | Do any of the regressors explain $Y$? | Mean Square Regression (MSR) | Mean Square Error (MSE) |

---

## Use Case 1: Testing Equality of Two Variances

### Setup

You have two independent samples from two normal populations. You want to test whether the populations have the same variance.

$$H_0: \sigma_1^2 = \sigma_2^2 \qquad H_a: \sigma_1^2 \neq \sigma_2^2$$

(Or a one-tailed version if you have a directional hypothesis.)

### The F Statistic

By convention, **always place the larger sample variance in the numerator** to push the test statistic into the right tail:

$$F = \frac{s_1^2}{s_2^2}, \quad \text{where } s_1^2 \geq s_2^2$$

$$df_1 = n_1 - 1 \qquad df_2 = n_2 - 1$$

Under $H_0$, both $s_1^2$ and $s_2^2$ are estimating the same $\sigma^2$, so their ratio should be close to 1. A large F value is evidence against $H_0$.

### Decision Rule

Because we always put the larger variance on top, we only look at the **right tail** — even for a two-tailed test. To account for this, use $\alpha/2$ as your significance level when looking up the critical value in an F-table.

$$\text{Reject } H_0 \text{ if } F > F_{\text{critical}}(df_1,\ df_2,\ \alpha/2)$$

### Worked Example

A portfolio manager claims that Fund A and Fund B have the same return variance. You gather 25 monthly returns for Fund A ($s_A^2 = 36\%^2$) and 31 monthly returns for Fund B ($s_B^2 = 20\%^2$). Test at the 5% significance level.

**Step 1 — State hypotheses:**
$$H_0: \sigma_A^2 = \sigma_B^2 \qquad H_a: \sigma_A^2 \neq \sigma_B^2$$

**Step 2 — Compute the F statistic** (larger variance in numerator):
$$F = \frac{s_A^2}{s_B^2} = \frac{36}{20} = 1.80$$

**Step 3 — Degrees of freedom:**
$$df_1 = 25 - 1 = 24 \qquad df_2 = 31 - 1 = 30$$

**Step 4 — Critical value** at $\alpha/2 = 0.025$:

From F-tables, $F_{0.025}(24, 30) \approx 2.14$

**Step 5 — Decision:**
$$1.80 < 2.14 \implies \text{Fail to reject } H_0$$

The evidence does not support a difference in variances at the 5% level.

---

## Use Case 2: Testing Overall Regression Significance

This is the F-test you'll see in regression output — the "ANOVA F-test." It answers the question: **does the regression model as a whole explain a statistically significant portion of the variation in $Y$?**

### The Setup: Decomposing Total Variation

In [[Simple and Multiple Linear Regression]], we decompose the total variation in $Y$ (measured as the Total Sum of Squares, SST) into two pieces:

$$\underbrace{SST}_{\text{Total variation in }Y} = \underbrace{RSS}_{\text{Explained by regression}} + \underbrace{SSE}_{\text{Unexplained (errors)}}$$

Where:
- **SST** (Total Sum of Squares) $= \sum(Y_i - \bar{Y})^2$ — how much $Y$ varies around its mean
- **RSS** (Regression Sum of Squares) $= \sum(\hat{Y}_i - \bar{Y})^2$ — how much of that variation the model accounts for
- **SSE** (Sum of Squared Errors) $= \sum(Y_i - \hat{Y}_i)^2$ — how much is left over (residuals)

> [!note] Notation Alert
> Some textbooks call RSS the "Explained Sum of Squares" (ESS). The CFA curriculum uses RSS. Don't confuse RSS here with "Residual Sum of Squares" used elsewhere — in CFA, **RSS = explained variation**, **SSE = residual/error variation**.

### The ANOVA Table

The regression output typically presents this as an ANOVA (Analysis of Variance) table. With $k$ independent variables and $n$ observations:

| Source | Sum of Squares | Degrees of Freedom | Mean Square | F |
|---|---|---|---|---|
| Regression | RSS | $k$ | $MSR = RSS/k$ | $MSR/MSE$ |
| Error | SSE | $n - k - 1$ | $MSE = SSE/(n-k-1)$ | — |
| Total | SST | $n - 1$ | — | — |

The **Mean Square** is simply the sum of squares divided by its degrees of freedom — it converts a total into a per-degree-of-freedom average, so the two can be fairly compared regardless of model size.

### The F Statistic

$$\boxed{F = \frac{MSR}{MSE} = \frac{RSS/k}{SSE/(n-k-1)}}$$

**Degrees of freedom:** $df_1 = k$ (numerator), $df_2 = n - k - 1$ (denominator)

**Hypotheses being tested:**

$$H_0: \beta_1 = \beta_2 = \cdots = \beta_k = 0 \qquad H_a: \text{at least one } \beta_j \neq 0$$

This is a **joint hypothesis** — you're testing all slope coefficients simultaneously. Under $H_0$, the regression explains nothing, so RSS should be small and $F$ should be close to zero. A large $F$ means the model is explaining more than you'd expect by chance.

> [!warning] F-test vs. t-tests in Regression
> The overall F-test and the individual [[t-test]]s for each coefficient answer different questions. You could have a significant overall F (the model works) but an insignificant individual t (that specific variable isn't contributing much after accounting for others) — this happens with [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]. Always look at both.

### The Connection to R²

There's a beautiful algebraic link between the F-statistic and $R^2$ (the coefficient of determination):

$$R^2 = \frac{RSS}{SST} \implies 1 - R^2 = \frac{SSE}{SST}$$

You can rewrite F entirely in terms of $R^2$:

$$F = \frac{R^2/k}{(1-R^2)/(n-k-1)}$$

This formula reveals the three forces that drive F upward:
1. **Higher $R^2$** — model explains more
2. **Fewer regressors $k$** — model is more parsimonious
3. **More observations $n$** — more data to pin down the relationships

### Worked Example

A researcher runs a regression of stock excess returns on three factors (market, size, value) using 60 monthly observations. The regression output shows:

$$RSS = 420 \qquad SSE = 580 \qquad n = 60 \qquad k = 3$$

**Step 1 — Compute means squares:**
$$MSR = \frac{RSS}{k} = \frac{420}{3} = 140$$
$$MSE = \frac{SSE}{n-k-1} = \frac{580}{60-3-1} = \frac{580}{56} = 10.36$$

**Step 2 — Compute F:**
$$F = \frac{MSR}{MSE} = \frac{140}{10.36} = 13.51$$

**Step 3 — Degrees of freedom and critical value** at $\alpha = 0.05$:
$$df_1 = 3 \qquad df_2 = 56$$
$$F_{\text{critical}}(3, 56, 0.05) \approx 2.76$$

**Step 4 — Decision:**
$$13.51 \gg 2.76 \implies \text{Reject } H_0$$

At least one of the three factor loadings is significantly different from zero — the model has real explanatory power.

**Cross-check with $R^2$:**
$$R^2 = \frac{RSS}{SST} = \frac{420}{420+580} = \frac{420}{1000} = 0.42$$
$$F = \frac{0.42/3}{0.58/56} = \frac{0.14}{0.01036} = 13.51 \checkmark$$

---

## Key Properties to Remember

```
F Distribution Properties
──────────────────────────────────────────
  Always ≥ 0           (ratio of variances)
  Right-skewed          (especially small df)
  Two parameters       (df₁, df₂)
  Mean ≈ df₂/(df₂-2)  (slightly > 1 for large df₂)
  As df → ∞: F → normal
──────────────────────────────────────────
  F(df₁, df₂) ≠ F(df₂, df₁)  ← ORDER MATTERS
  Critical values are NOT symmetric
```

> [!danger] Common Mistake: Swapping Degrees of Freedom
> $F(3, 56)$ and $F(56, 3)$ have completely different critical values. The numerator df always corresponds to the *numerator* variance. In the equality-of-variances test, the larger variance goes in the numerator, so its sample size drives $df_1$.

---

## The F–t Relationship

For a regression with a **single** independent variable ($k = 1$), the F-test and the t-test for the slope coefficient are algebraically equivalent:

$$F = t^2$$

That is, $F(1, n-2) = [t(n-2)]^2$. The F-test is simply a generalization of the t-test to multiple simultaneous hypotheses. When you only have one restriction to test, both say the same thing.

---

## Summary Table

| Feature | Equality of Variances Test | Overall Regression F-Test |
|---|---|---|
| $H_0$ | $\sigma_1^2 = \sigma_2^2$ | All $\beta_j = 0$ |
| Numerator | Larger $s^2$ | MSR = RSS/k |
| Denominator | Smaller $s^2$ | MSE = SSE/(n–k–1) |
| $df_1$ | $n_1 - 1$ | $k$ |
| $df_2$ | $n_2 - 1$ | $n - k - 1$ |
| Tail | Right only (put larger on top) | Right only (large F = bad fit under H₀) |
| Related concept | [[Hypothesis Testing]], [[Chi-Squared Distribution]] | [[Multiple Regression]], [[R-Squared]] |

---

## Related Notes

- [[Chi-Squared Distribution]] — F is built from two chi-squared variables
- [[t-test and t-distribution]] — F = t² for single-variable regression
- [[Simple and Multiple Linear Regression]] — where the ANOVA F-test lives
- [[Hypothesis Testing Framework]] — the broader structure of test statistics
- [[R-Squared and Adjusted R-Squared]] — algebraically linked to the regression F-statistic
- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] — why F can be significant while individual t-tests are not
