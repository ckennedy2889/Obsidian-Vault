---
title: Studentized Residuals
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics, influence-analysis, outliers]
aliases: [Studentized Deleted Residual, Externally Studentized Residual, Internally Studentized Residual, Deleted Studentized Residual]
---

# Studentized Residuals

## The Real-World Analogy First

Imagine you're a track coach timing runners, and one athlete finishes wildly slower than everyone else. A **raw residual** is just saying, "she was 20 seconds slower than the average." That's a start — but it hides an important question: *was her time really that bad, or does it just look bad because she was the only one running in a downpour while the others had clear skies?*

A **studentized residual** is the version of that comparison that **adjusts for her running conditions first**. It asks: given the specific weather, track, and time of day *she* ran in, how far did her actual time deviate from what we'd expect? A raw 20-second gap in perfect conditions is damning. A raw 20-second gap in a storm is expected. You can't treat the two the same.

In regression, "running in a storm" is analogous to being a **high-leverage point** — a data point whose $X$ value is so extreme it pulls the regression line toward itself. That pulling action *hides* the size of the residual. A studentized residual undoes the pull and reveals the observation's true "how-badly-does-the-model-miss-this-point" distance.

---

## The Problem With Raw Residuals: Why We Need to Studentize

The raw residual is just:

$$e_i = Y_i - \hat{Y}_i$$

Looks simple. Looks useful. And for most observations, it is. But raw residuals have two fatal weaknesses that make them **unreliable for outlier detection**.

### Weakness 1 — Different observations have different residual *scales*

A raw residual doesn't tell you whether a miss is "large relative to what we'd expect." In a regression with $\sigma = 2$, a residual of $e_i = 5$ is a 2.5-sigma miss — notable. In a regression with $\sigma = 50$, a residual of $e_i = 5$ is a 0.1-sigma miss — totally routine. You can't compare raw residuals across regressions, or even interpret them cleanly within one regression, without scaling.

### Weakness 2 — High-leverage points bend the line toward themselves

This is the bigger problem, and it's the reason studentization exists.

Here's the intuition. OLS chooses $\hat{b}$ to minimize $\sum e_i^2$. If one observation sits far from the crowd in $X$-space — a **high-leverage point** — the sum-of-squares objective pays a huge penalty for missing it, because a small error at a lever arm far from the mean translates into a big change in slope. So OLS bends the line **toward** that extreme point to reduce its residual.

The result: **the observation that could mess up your model the most ends up with an artificially small raw residual**, because the line has already been tilted to accommodate it. A raw-residual scan of the dataset will completely miss it.

```
       Y                                   Y
       │              × ← actual value     │              × ← actual
       │             ╱                     │           ╱
       │   ● ●    ╱    small residual      │    ●  ● ╱     large residual
       │ ●  ● ●╱       (OLS line tilted    │ ● ● ●╱        (line ignores X)
       │ ●●●╱╱             toward x)       │ ●●╱
       │ ●●╱                                │ ●╱
       └──────────────► X                   └──────────────► X
          "Full-sample" line                 "Line without x"
          (tilts to fit x)                   (reveals x's true miss)
```

Studentization fixes both problems by (a) dividing by the residual's own standard error and (b) using a variant that *excludes* the point being tested from the fit. That's the concept behind the **externally studentized** — or **deleted** — residual.

---

## The Machinery — Step by Step

Two quantities we need first.

### Leverage $h_{ii}$ — "How Far From the Crowd in $X$-Space?"

Leverage measures how extreme observation $i$'s regressors are compared to the sample average.

- **Range:** $0 \le h_{ii} \le 1$. Values near 0 mean "typical $X$ values, low influence"; values near 1 mean "far out in $X$-space, potentially huge pulling power."
- **Average leverage across the sample:** $\bar{h} = (k+1)/n$, where $k$ is the number of regressors (the $+1$ is for the intercept). So in a regression with $k = 2$ and $n = 15$, the average $h_{ii}$ is $3/15 = 0.20$.
- **Rule of thumb for flagging a high-leverage point:** $h_{ii} > 3(k+1)/n = 3\bar{h}$. Three times the average.

Leverage is a pure-$X$ concept — it doesn't know anything about $Y$. It's asking, "*if* this point turned out to have a weird $Y$, how much damage could it do?"

### The Residual Standard Error — "What Size Miss Counts as Normal?"

The residual standard error $s$ (sometimes called $s_e$ or the square root of MSE) measures the typical size of a raw residual across the whole regression. That's the benchmark we'll scale each individual residual against.

---

## The Two Flavors — Internal vs. External (Deleted)

There are two studentized-residual formulas, and the CFA curriculum cares about the **deleted** version. Know both so you don't get confused.

### Internally Studentized Residual

$$e_i^* = \frac{\hat{\varepsilon}_i}{s \sqrt{1 - h_{ii}}}$$

Where:

- $\hat{\varepsilon}_i$ = raw residual
- $s$ = residual standard error from the full-sample regression
- $h_{ii}$ = leverage of observation $i$
- $\sqrt{1 - h_{ii}}$ = the correction that accounts for the fact that a high-leverage point's raw residual is artificially shrunk

**The problem with this version:** the denominator still uses $s$, the full-sample residual standard error — which includes observation $i$ itself. If $i$ is a huge outlier, it inflates $s$, which *deflates* $e_i^*$, and the outlier hides itself in its own standard error. The fix: recompute $s$ with observation $i$ removed.

### Externally Studentized Residual (The Deleted / CFA Version)

This is the CFA exam's preferred outlier test statistic — sometimes called the **studentized deleted residual**.

$$\boxed{\, t_i^* = \frac{\hat{\varepsilon}_i}{\sqrt{\text{MSE}_{(i)}(1 - h_{ii})}} \,}$$

Where $\text{MSE}_{(i)}$ is the mean-squared-error from the regression **re-fit without observation $i$**. The name "deleted" comes from that step.

**The logic in plain English:**

1. Delete observation $i$ from the dataset.
2. Re-fit the regression on the remaining $n - 1$ observations.
3. Use that deleted-sample model to predict $\hat{Y}_i$ for the point you dropped.
4. Measure the gap between actual $Y_i$ and the deleted model's prediction.
5. Scale that gap by the deleted model's residual standard deviation.

If observation $i$ is truly an outlier, it can't hide in its own influence anymore — it's not there to tilt the line. Its true distance from what the rest of the data expects becomes visible.

**Computational note:** in practice you don't re-fit $n$ separate regressions. There's a closed-form shortcut that computes $t_i^*$ from full-sample quantities directly. The formula above is the result.

---

## Distribution and Decision Rule

Under the null hypothesis that observation $i$ is **not an outlier** (its error comes from the same distribution as all the others), the deleted studentized residual follows a Student's $t$-distribution:

$$t_i^* \sim t_{n - k - 2}$$

The degrees of freedom are **$n - k - 2$**:

- $-k$ for the $k$ slope coefficients estimated in the regression
- $-1$ for the intercept
- $-1$ for the observation you "deleted" in forming $t_i^*$

### Two Decision Rules You Should Know

**Rule of thumb (the quick sniff test):**

$$|t_i^*| > 3 \quad \Rightarrow \quad \text{flag as an outlier}$$

Because the $t$ distribution is nearly standard normal for reasonable $n$, $|t_i^*| > 3$ corresponds to a very low p-value (well below 1%). It's a blunt but effective rule.

**Formal test (compare to critical value):**

$$|t_i^*| > t_{\alpha/2,\,n-k-2} \quad \Rightarrow \quad \text{reject null — observation is an outlier}$$

Two-sided because outliers can be large in either direction. Use a small $\alpha$ (1% or 0.1%) if you're screening many observations, to avoid flagging random extreme points just by chance.

---

## Worked Numerical Example — Retailer Regression

An analyst studies 15 retailers, regressing a profitability metric on two independent variables: product count and online sales percentage.

- $n = 15$
- $k = 2$ (regressors, not counting the intercept)
- Significance level: $\alpha = 0.05$

### Step 1 — Degrees of Freedom

$$\text{df} = n - k - 2 = 15 - 2 - 2 = 11$$

### Step 2 — Critical Value

At $\alpha = 0.05$ two-sided, $t_{0.025,\,11} = \pm 2.201$.

### Step 3 — Read Observation #3's Studentized Residual

Suppose the software output reports for observation #3:

$$t_3^* = -4.033$$

### Step 4 — Apply Both Decision Rules

| Rule | Threshold | Comparison | Decision |
|---|---|---|---|
| Rule of thumb | $\|t_i^*\| > 3$ | $\|-4.033\| = 4.033 > 3$ | Flag |
| Critical value | $\|t_i^*\| > 2.201$ | $4.033 > 2.201$ | Reject null |

Both rules agree — observation #3 is an outlier at the 5% significance level.

### Step 5 — What to Do Next

Flagging is a **diagnostic**, not an automatic instruction to delete. The analyst should:

1. Investigate observation #3 manually — is it a data entry error? A firm in unusual financial distress? A recent acquisition that distorts its metrics?
2. If the data is legitimate, consider whether a **transformation** (log, square root) tames the extremity.
3. If the observation is a true data error, correct it.
4. Only as a last resort, re-run the regression with observation #3 excluded — and *always* report that you did so.

Deleting observations is a cardinal sin if undisclosed. An analyst who quietly drops outliers to boost $R^2$ is committing a [[Standards of Professional Conduct|Standards]] violation (V(A) — Diligence and Reasonable Basis).

---

## Studentized Residuals vs. Leverage vs. Cook's Distance

These three quantities are the **influence analysis triad**. They answer different questions.

| Quantity | What It Measures | Axis of Concern | Detection Rule |
|---|---|---|---|
| **Leverage $h_{ii}$** | How extreme is this observation in $X$-space? | Pulling power (independent variables) | $h_{ii} > 3(k+1)/n$ |
| **Studentized residual $t_i^*$** | How badly does the model miss this observation's $Y$? | Vertical miss (dependent variable) | $\|t_i^*\| > 3$ or $t_{\alpha/2,\,n-k-2}$ |
| **Cook's Distance $D_i$** | Combined: leverage × residual → how much would the model change if this point were deleted? | Total influence (X and Y together) | $D_i > 1$ (serious); $D_i > 4/n$ (flag for review) |

### The 2×2 Matrix of Outlier Types

```
                          Large Residual?
                          No         Yes
                   ┌─────────────┬─────────────┐
    High           │             │  TRULY      │
    Leverage?  Yes │  Leverage   │  INFLUENTIAL│
                   │  only       │  (delete w/ │
                   │             │  caution)   │
                   ├─────────────┼─────────────┤
                   │             │  Outlier    │
                 No │  All good   │  on Y but   │
                   │             │  low pull   │
                   └─────────────┴─────────────┘
```

- **Top-left (high leverage, small residual):** the point sits far out in $X$-space, but the model fits it well. No damage — in fact, high-leverage points can *help* pin down slopes when they're on-trend.
- **Top-right (high leverage + large residual):** the nightmare. Data point is extreme in $X$ *and* the model's prediction is way off. This is where Cook's D will scream. Investigate immediately.
- **Bottom-right (large residual, low leverage):** an outlier in $Y$ but without much pull. Fixes your coefficient estimates less but is still worth investigating.
- **Bottom-left:** normal observations. Leave them alone.

A studentized residual alone can't distinguish top-right from bottom-right — you need leverage or Cook's D on top of it.

---

## Why the Deleted Version Is the CFA Answer

If the exam asks *"what is the preferred statistic for detecting outliers in a multiple regression?"*, the answer is **studentized deleted residuals** (externally studentized). Reason:

1. Raw residuals hide outliers that are high-leverage.
2. Internally studentized residuals partly fix this but let outliers inflate $s$.
3. Externally studentized (deleted) residuals remove the suspect observation from $s$ entirely — giving the cleanest possible "how unlikely was this point under the model fit without it" statistic.

It's the only version that has the right t-distribution under the null, and it's the only version whose rule of thumb ($|t_i^*| > 3$) maps cleanly onto a classical hypothesis test.

---

## Memory Hooks

- **"Residual adjusted for leverage"** — that's all a studentized residual is.
- **Deleted = don't let the outlier grade its own homework** — the refit-without-$i$ logic keeps the suspect from inflating its own SE.
- **df = $n - k - 2$** — the "extra minus one" is for the deletion.
- **$|t_i^*| > 3$ rule of thumb** — quick sniff test before running the formal comparison.
- **Raw residuals lie for high-leverage points** — the core reason the studentized version exists.
- **Triad:** Leverage (X extremity) + Studentized residual (Y miss) = Cook's D (total influence).

---

## CFA LOS Coverage

This note discharges:

| LOS | Verb | Covered By |
|---|---|---|
| **Quant LM4 LOS 4.a** — *describe influence analysis and methods of detecting influential data points* | **describe** | Full note — leverage, studentized residuals, Cook's D, the 2×2 matrix |
| **Quant LM4 LOS 4.b** — *formulate and interpret a multiple regression model that includes qualitative independent variables* | — | Adjacent LOS; studentized residuals also apply to dummy-variable regressions |

After reading, you should be able to **define** a studentized residual, **explain** why raw residuals fail for high-leverage points, **calculate** $t_i^*$ from given inputs, **interpret** it against critical $t$ or the rule of thumb, and **distinguish** outliers (Y-axis) from leverage (X-axis) from influence (combined).

---

## CFA Exam Focus

1. **Purpose:** detect outliers whose Y-values are poorly predicted by the regression — adjusted for each point's leverage.
2. **Formula (deleted):** $t_i^* = \hat{\varepsilon}_i \,/\, \sqrt{\text{MSE}_{(i)}(1-h_{ii})}$.
3. **Why deleted, not internal:** suspect observation can't pollute the SE it's being judged against.
4. **Distribution:** $t$ with $n-k-2$ degrees of freedom under the null of "not an outlier."
5. **Decision:** $|t_i^*| > 3$ (rule of thumb) or $|t_i^*| >$ critical $t$ (formal).
6. **Triad awareness:** studentized residual = outlier (Y); leverage = extreme X; Cook's D = combined influence.

---

## Related Notes

[[Extensions of Multiple Regression]] · [[Leverage]] · [[Cook's Distance]] · [[Influential Observation]] · [[Ordinary Least Squares]] · [[Residual Standard Error]] · [[Mean Squared Error]] · [[Hypothesis Testing in Regression]] · [[Degrees of Freedom]] · [[Regression Assumptions]]
