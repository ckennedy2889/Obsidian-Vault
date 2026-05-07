---
title: "Practice Q - F-Statistic Calculation (Canadian Inflation)"
subject: "Quantitative Methods"
tags: [CFA-L2, practice-question, regression, F-test, ANOVA, hypothesis-testing, degrees-of-freedom]
source: "unknown"
date: 2026-04-21
---

# F-Statistic Calculation — Canadian Inflation Model

## Question

![[attachments/2026-04-21-f-statistic-canadian-inflation.png]]

**Question (transcribed):**

Jenny Hamilton is a financial economist who is studying the Canadian inflation rate. She runs a regression with inflation as the dependent variable and unemployment, the total money supply, and the difference between real GDP and potential GDP (the output gap) as a percentage of total GDP as the independent variables. Using annual data from 1961–2016, she obtains the following equation:

$$\hat Y_i = 10.4 + 0.76 X_{1i} + 0.65 X_{2i} + 0.35 X_{3i}$$

Where $X_1$ is the unemployment rate, $X_2$ is the money supply, and $X_3$ is the output gap.

If the regression sum of squares = 86.5, and the sum of squared errors = 76, **what is the value of the F-statistic?**

- **A.** 1.15
- **B.** 3.25
- **C.** 19.73

---

## Correct Answer: C — 19.73

### What Is This Testing?

A mechanical calculation of the **overall F-statistic** for a multiple regression, using only the two sums of squares and the sample size / regressor count. The exam writers want to confirm you can assemble the degrees of freedom correctly and apply the $F = \mathrm{MSR}/\mathrm{MSE}$ formula without the safety net of a pre-filled ANOVA table. See [[Hypothesis Testing in Regression]] and [[F Distribution and F Tests]].

### The Correct Approach

The formula for the overall F-statistic:

$$
\boxed{\;F \;=\; \frac{\mathrm{MSR}}{\mathrm{MSE}} \;=\; \frac{\mathrm{RSS}/k}{\mathrm{SSE}/(n - k - 1)}\;}
$$

| Symbol | Meaning | Value in this problem |
|---|---|---|
| RSS | Regression sum of squares (explained variation) | 86.5 |
| SSE | Sum of squared errors (residual variation) | 76 |
| $k$ | Number of independent variables | **3** (unemployment, money supply, output gap) |
| $n$ | Sample size | **56** (annual data 1961 through 2016 inclusive = $2016 - 1961 + 1$) |
| $n - k - 1$ | Residual degrees of freedom | $56 - 3 - 1 = \mathbf{52}$ |

> [!note] Watch the Sample-Size Count
> Annual data from 1961 **to** 2016 gives $2016 - 1961 + 1 = 56$ observations, **not** 55. Inclusive date ranges are a quiet exam trap — off-by-one errors here propagate straight into your denominator df.

### Step-by-Step Computation

**Step 1 — Mean Square Regression (numerator).**

$$\mathrm{MSR} = \frac{\mathrm{RSS}}{k} = \frac{86.5}{3} = 28.8333$$

**Step 2 — Mean Square Error (denominator).**

$$\mathrm{MSE} = \frac{\mathrm{SSE}}{n - k - 1} = \frac{76}{56 - 3 - 1} = \frac{76}{52} = 1.4615$$

**Step 3 — Ratio.**

$$F = \frac{28.8333}{1.4615} = \mathbf{19.73}$$

### The Intuition

Each "mean square" is a **variance-per-degree-of-freedom** figure. MSR measures how much explained variation you're getting *per regressor you spent* — the payoff of each variable. MSE measures the leftover noise *per residual degree of freedom* — the floor. The ratio tells you how many times larger your signal is than your noise.

Here signal is ~19.7× noise. With $F_{0.05, 3, 52} \approx 2.78$, this is far above any reasonable critical value — the model is overwhelmingly significant. The same number would be reported as p < 0.001 in software output.

See: [[F-Test vs t-Test]] · [[R-Squared and Adjusted R-Squared]] (which uses the exact same sums of squares).

---

## The Trap — Most Tempting Wrong Answer: **A (1.15)**

### Why It Looks Right

The student sees two sums of squares, divides them directly, and gets:

$$\frac{\mathrm{RSS}}{\mathrm{SSE}} = \frac{86.5}{76} \approx 1.138 \;\; \longrightarrow \;\; \text{rounds to } 1.15$$

It *feels* like you've done the right thing — you combined the two variation quantities in the right direction (explained over unexplained). But you skipped the critical step: **converting each into a mean square by dividing by its degrees of freedom.**

### The Specific Mistake

Forgetting that F is a **ratio of mean squares**, not a ratio of sums of squares. A sum of squares grows with both sample size and parameter count; only after normalizing by df does the ratio become a proper signal-to-noise statistic with a known F-distribution.

### The Other Wrong Answer: **B (3.25)**

Option B typically reflects a **degrees-of-freedom miscount** — most commonly using the wrong $n$ (e.g., counting the year range exclusively as 55 and then a further df slip) or attaching df to only one of numerator or denominator. Either way, the cure is the same: write out $n$, $k$, and $n - k - 1$ **before** you touch the calculator.

### How to Avoid It on Exam Day

> [!tip] The Three-Line Setup Ritual
> Before computing any F-statistic, write down on scratch paper:
> 1. $n = \underline{\;\;\;\;\;}$ (watch for inclusive year ranges!)
> 2. $k = \underline{\;\;\;\;\;}$ (independent variables only — *not* counting the intercept)
> 3. $n - k - 1 = \underline{\;\;\;\;\;}$
>
> With those three numbers locked in, the formula $F = (\mathrm{RSS}/k) / (\mathrm{SSE}/(n-k-1))$ is impossible to botch.

---

## Key Takeaway

> [!tip] Memory Hook
> **F is mean-square-over-mean-square, not sum-over-sum.** Every sum of squares gets divided by its own degrees of freedom *first* — RSS by $k$, SSE by $n-k-1$ — and only then do you take the ratio.

---

## Related Concepts

- [[Hypothesis Testing in Regression]] — parent workflow with full F-test treatment
- [[F Distribution and F Tests]] — shape of the reference distribution and df rules
- [[F-Test vs t-Test]] — when to use each
- [[R-Squared and Adjusted R-Squared]] — uses identical RSS/SSE building blocks
- [[Multiple Regression - Basics and Assumptions]] — OLS and ANOVA decomposition
- [[Sum of Squares]] · [[Mean Square Error]] · [[Degrees of Freedom]]
