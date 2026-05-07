---
title: "Practice Q - Overall F-Test for Model Significance (5-Variable)"
subject: "Quantitative Methods"
tags: [CFA-L2, practice-question, regression, F-test, ANOVA, hypothesis-testing]
source: "unknown"
date: 2026-04-21
---

# Overall F-Test for Model Significance (5-Variable Model)

## Question

![[attachments/2026-04-21-overall-f-test-5-variable-model.png]]

**Question (transcribed):**

An analyst developed the following multiple regression model.

$$Y_i = b_0 + b_1 X_{1i} + b_2 X_{2i} + b_3 X_{3i} + b_4 X_{4i} + b_5 X_{5i} + \varepsilon_i$$

After a brief review of the model, concern was formed regarding the model's overall significance. To explore this concern, they ran a statistical test; below are the partial ANOVA results.

| | Degrees of Freedom | Sum of Squares | Mean Squares |
|---|---:|---:|---:|
| Regression | 5 | 87.2462 | 17.4492 |
| Residual | 44 | 52.8261 | 1.2006 |
| Total | 49 | 140.0723 | |

$^1\,\text{F.INV.RT}(0.05, 5, 44) = 2.427$

**Given a 5% level of significance, the analyst should:**

- **A.** reject the null hypothesis that $b_1 \neq b_2 \neq \ldots \neq b_k \neq 0$
- **B.** reject the null hypothesis that $b_1 = b_2 = \ldots = b_k = 0$
- **C.** do not reject the null hypothesis that $b_1 \neq b_2 \neq \ldots \neq b_k \neq 0$

---

## Correct Answer: B — Reject the null hypothesis that $b_1 = b_2 = \ldots = b_k = 0$

### What Is This Testing?

This is the **overall F-test for model significance** — the "does my model do *anything* at all?" question. It asks whether *at least one* slope coefficient in the regression is different from zero, or whether the whole model is indistinguishable from just predicting the mean $\bar Y$ for every observation. For a detailed treatment, see [[Hypothesis Testing in Regression]] and [[F-Test vs t-Test]].

### The Correct Approach

**Step 1 — Write the hypotheses precisely.** This is where most students lose the point.

| | Statement |
|---|---|
| $H_0$ | $b_1 = b_2 = \ldots = b_k = 0$ (every slope is zero — the model explains nothing) |
| $H_a$ | **At least one** $b_j \neq 0$ (not "all $b_j \neq 0$") |

> [!warning] The Null is ALWAYS an "=" Statement
> A null hypothesis is a *single, specific* claim about parameters, so it must use equality (=). The statements in answers A and C — "$b_1 \neq b_2 \neq \ldots \neq 0$" — aren't valid nulls at all. They're nonsense as written.

**Step 2 — Compute the F-statistic.**

$$F = \frac{\mathrm{MSR}}{\mathrm{MSE}} = \frac{\mathrm{SSR}/k}{\mathrm{SSE}/(n-k-1)}$$

Plugging in the ANOVA table values directly:

$$F = \frac{17.4492}{1.2006} = \mathbf{14.534}$$

**Step 3 — Identify the critical value.**

The problem hands it to us: $F.\mathrm{INV.RT}(0.05, 5, 44) = 2.427$. That's the Excel function for the **right-tail** critical value of the F-distribution with:

- Numerator df $= k = 5$
- Denominator df $= n - k - 1 = 50 - 5 - 1 = 44$
- Significance level $\alpha = 5\%$

We can also verify the sample size from the ANOVA table: total df = $n - 1 = 49$, so $n = 50$.

**Step 4 — Apply the decision rule.**

The F-test is always **one-tailed (right-tail)** because the F-distribution is strictly non-negative and large values mean "lots of variation explained relative to noise."

$$F_{\text{stat}} = 14.534 \; > \; F_{\text{crit}} = 2.427 \;\; \Longrightarrow \;\; \textbf{Reject } H_0$$

### The Intuition

The F-statistic is a signal-to-noise ratio. **MSR** (mean square regression) is the variance explained *per regressor* — a per-variable "signal." **MSE** (mean square error) is the leftover residual variance *per degree of freedom* — the "noise floor." Here the signal is 14.5× the noise, which is light-years beyond what chance alone could produce. When $F \gg F_{\text{crit}}$, we have overwhelming evidence that at least one predictor is genuinely associated with $Y$.

The [[P-Value]] interpretation: under $H_0$, the chance of seeing an F-stat this extreme with $(5, 44)$ df is vanishingly small (well below 0.001), so rejecting is the only defensible call.

---

## The Trap — Most Tempting Wrong Answer: **A**

### Why It Looks Right

A student running on autopilot will:

1. Compute the F-stat and see it's huge.
2. Correctly conclude: *"I need to reject."*
3. Pick the first "reject" option they see — **A**.

The *direction* (reject) is right. But answer A states the null as "$b_1 \neq b_2 \neq \ldots \neq 0$" — which isn't a null at all. Rejecting a bogus hypothesis isn't a valid exam answer.

### The Specific Mistake

Confusing the structure of $H_0$ vs $H_a$:

- **$H_0$ (null)** must be a single equality statement: $b_1 = b_2 = \ldots = b_k = 0$.
- **$H_a$ (alternative)** is the complement: *at least one* $b_j \neq 0$ — **never** "all $b_j \neq 0$."

Answer A's phrasing — "reject the null that all betas are simultaneously non-zero" — describes nothing you'd ever actually test in a regression. It's a nonsense statement dressed up to look plausible.

### How to Avoid It on Exam Day

> [!tip] Two-Second Sanity Check
> Before picking any hypothesis-test answer, **scan for the equality sign in the null.** A null hypothesis in regression *always* contains "=". If the option's $H_0$ has "≠" in it, the option is wrong on its face, regardless of the reject/don't-reject direction.

Also: the overall F-test null is worth memorizing verbatim — **"all slope coefficients equal zero"** — so you recognize the correct phrasing instantly.

---

## Key Takeaway

> [!tip] Memory Hook
> **Big F → reject → every slope ≠ zero? No — "at least one" ≠ zero.** The null of the overall F-test is $b_1 = b_2 = \ldots = b_k = 0$. Reject it when $F > F_{\text{crit}}$, and conclude only that *somewhere* in the model lives a non-zero coefficient — you still need t-tests to pin down which one.

---

## Related Concepts

- [[Hypothesis Testing in Regression]] — parent note covering the full t-test and F-test workflow
- [[F-Test vs t-Test]] — when to reach for each
- [[F Distribution and F Tests]] — shape and properties of the F distribution
- [[R-Squared and Adjusted R-Squared]] — companion goodness-of-fit measure (same SSR/SSE breakdown)
- [[Multiple Regression - Basics and Assumptions]] — ANOVA decomposition and OLS setup
- [[Sum of Squares]] · [[Mean Square Error]] · [[Degrees of Freedom]]
- [[Type I and Type II Errors]] · [[P-Value]] · [[Critical Value]]
