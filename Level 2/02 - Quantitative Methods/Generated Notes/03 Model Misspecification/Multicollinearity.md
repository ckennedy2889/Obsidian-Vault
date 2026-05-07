---
title: Multicollinearity
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics]
aliases: [Collinearity, Near Multicollinearity, Perfect Multicollinearity]
---

# Multicollinearity

## The Real-World Analogy First

Imagine you're trying to figure out which of two nearly identical twins ate the last cookie. They dress the same, talk the same, and were both in the kitchen at the same time. Witnesses say "one of the twins did it" — but ask them *which* twin, and they shrug. Information is there in aggregate ("a twin did it"), but you can't cleanly assign blame to *one* specific twin because the two are so hard to tell apart.

Now picture a regression where you're explaining a stock's return using both **GDP growth** and **industrial production growth**. These two macro variables move together almost in lockstep — when one rises, so does the other. Your regression knows the macro cycle matters, but it can't cleanly assign *how much* of the effect belongs to GDP vs. industrial production. The coefficients become unstable, standard errors balloon, and t-stats collapse.

That's **multicollinearity**: when two or more independent variables in your regression are so highly correlated that the model can't separate their individual contributions. Think of them as **mathematical twins** — the math gets confused about which one is actually driving the result.

---

## What It Actually Means

In a multiple regression:

$$Y = b_0 + b_1 X_1 + b_2 X_2 + \cdots + b_k X_k + \varepsilon$$

The slopes $b_1, b_2, \ldots$ are meant to capture the **independent** effect of each $X_j$ — what happens to $Y$ when $X_j$ changes *holding the others constant*. That interpretation only works if the $X$'s can, in fact, move independently.

### Perfect vs. Near Multicollinearity

| Type | What It Is | Consequence |
|---|---|---|
| **Perfect** | Exact linear relationship, e.g. $X_3 = 2X_1 + 5X_2$ | $(X^\top X)$ is singular — OLS literally cannot be computed. Software drops a variable or errors out |
| **Near** | Regressors highly but not perfectly correlated | OLS runs fine — but the output becomes untrustworthy in specific ways |

Near multicollinearity is the common and insidious case in finance. The computer gives you an answer; the answer just can't be trusted.

---

## Why OLS Gets Wobbly — Four Ways to See It

The exam wants you to *recite* that multicollinearity inflates SEs. A good analyst wants to know **why**. Here are four complementary mental models — each lights up a different facet of the same phenomenon. They all point to the same answer: when regressors carry near-identical information, OLS has almost nothing *unique* to each one to work with, and that shortage of unique information becomes uncertainty in the coefficient.

### View 1 — The Formula

The variance of an individual slope coefficient in a multiple regression is:

$$\text{Var}(\hat{b}_j) = \frac{\sigma^2}{(n-1) \cdot s_{X_j}^2 \cdot (1 - R_j^2)}$$

where $R_j^2$ is the $R^2$ from the **auxiliary regression of $X_j$ on all the other regressors**. Three things can shrink the denominator and thereby *inflate* the variance of $\hat{b}_j$:

- **$\sigma^2$ (error variance) large** — noisy data always widens SEs.
- **$s_{X_j}^2$ (regressor variance) small** — a variable that barely moves carries little information.
- **$R_j^2 \to 1$** — this is the multicollinearity channel. As the other $X$'s get better at predicting $X_j$, $(1 - R_j^2)$ collapses toward zero, and dividing by a tiny number blows up the variance.

$R_j^2 = 0.90 \Rightarrow (1 - R_j^2) = 0.10 \Rightarrow$ variance is 10× what it would be without multicollinearity. $R_j^2 = 0.99 \Rightarrow$ variance is 100× inflated. This factor $1/(1 - R_j^2)$ *is* the [[Variance Inflation Factor (VIF)|Variance Inflation Factor]] — the name is literal.

### View 2 — The "Unique Variation" View

OLS estimates $b_j$ by asking: *when $X_j$ moves and the other regressors don't, how does $Y$ respond?*

It answers that question using only the portion of $X_j$ that is **not explained by the other regressors** — because only that portion represents "$X_j$ moving while the others stay still." The rest of $X_j$'s variation is entangled with the others and can't be cleanly attributed.

That unique portion is exactly $X_j - \hat{X}_j$, where $\hat{X}_j$ is the fitted value from regressing $X_j$ on the other regressors. The *size* of that unique piece is:

$$s_{X_j}^2 \cdot (1 - R_j^2) \quad = \quad \underbrace{\text{total variation in } X_j}_{s_{X_j}^2} \;\times\; \underbrace{\text{fraction that's unique}}_{1 - R_j^2}$$

If the others explain 90% of $X_j$, only 10% of $X_j$'s variation is left to estimate $b_j$ from. It's as if your "effective sample" shrank to 10% of $n$. With ten times less usable data, your coefficient SE is correspondingly larger.

**This is the core intuition.** Multicollinearity isn't a weird pathology — it's a **data shortage problem in disguise**. The regressor has plenty of raw variation, but almost all of it is redundant with the other regressors. OLS works with what's unique; when little is unique, little can be estimated precisely.

### View 3 — The Seesaw (Identification) View

Imagine $X_1$ and $X_2$ are nearly identical — say $X_2 \approx X_1$. Then in the regression $Y = b_0 + b_1 X_1 + b_2 X_2 + \varepsilon$, the fitted values are:

$$\hat{Y} = b_0 + b_1 X_1 + b_2 X_2 \;\approx\; b_0 + (b_1 + b_2) X_1$$

The data pin down the **sum** $b_1 + b_2$ fairly well — that's what drives $\hat{Y}$. But the individual values of $b_1$ and $b_2$ are **not pinned down**. You could have $(b_1, b_2) = (10, -5)$, $(5, 0)$, or $(-2, 7)$, all producing nearly the same fit with nearly the same sum.

This is the **seesaw**: if you raise $b_1$ a little, the estimator happily drops $b_2$ to compensate, and the overall fit barely changes. Many different $(b_1, b_2)$ combinations fit the data about equally well. That *is* what "high variance of $\hat{b}_j$" means. The SE is literally the formal measurement of how much $\hat{b}_j$ could plausibly wiggle without worsening the fit.

```
Fit surface with nearly-collinear X1, X2:

    b2 ▲
       │     ╲
       │      ╲     ← all (b1, b2) pairs on this ridge
       │       ╲       fit Y roughly equally well
       │        ╲
       │         ╲
       └─────────────► b1

     The ridge is LONG, so b1 and b2 individually
     have enormous uncertainty — but their SUM
     along the ridge direction is well-determined.
```

With uncorrelated regressors, the fit surface would be a clean bowl with a single sharp minimum → tight SEs. With near-collinear regressors, the bowl stretches into a canyon → SEs explode along the ridge direction.

### View 4 — The Geometric View

Think of the regressors as vectors in $n$-dimensional "data space" (one dimension per observation). Regression projects $Y$ onto the subspace spanned by the $X$ vectors. The coefficients $(b_1, b_2, \ldots)$ are the coordinates of that projection in the basis of $X$'s.

- When the $X$ vectors are **perpendicular** (uncorrelated), each coordinate is cleanly defined — small shifts in $Y$ produce small, well-defined shifts in each $b_j$.
- When the $X$ vectors are **nearly parallel** (collinear), the basis is "skewed" — a tiny shift in $Y$ requires a large, compensating swing in the individual coordinates to represent it. The coordinates are hypersensitive.

A concrete thought experiment: try to describe a point on a whiteboard using two arrows that are perpendicular. Easy — the $(x, y)$ coordinates are unique and stable. Now try to describe the same point using two arrows that are almost parallel. You can still do it — but any small measurement error in the point's location swings the coordinates wildly. Parallel-ish arrows are a bad coordinate system, and multicollinear regressors are a bad basis for the regression.

---

### The Bottom-Line "Why"

Pick your favorite view — **formula**, **unique variation**, **seesaw**, or **geometry** — they're all the same fact. Multicollinearity inflates standard errors because OLS only has *unique* information about each regressor to work with, and when two regressors are near-duplicates, almost none of their variation is unique. Less unique information → less precision → bigger SEs. The coefficients remain unbiased (the estimator still, on average, hits the right value), but the range of plausible estimates around that average widens dramatically.

---

## The Classic Symptom Pattern

| Symptom | What You Observe |
|---|---|
| **High overall $R^2$** | The regression as a whole fits well |
| **Significant F-statistic** | The joint hypothesis that all slopes are zero is rejected |
| **Insignificant individual t-stats** | But *none* of the coefficients look individually significant |
| **Inflated standard errors** | SEs much larger than expected |
| **Unstable coefficients** | Adding/removing a variable causes wild swings |
| **Counter-intuitive signs** | Coefficients may flip the "wrong" direction |

### The F-vs-t Paradox

The giveaway is the **F-vs-t paradox**: the F-test says "the regressors jointly matter a lot," but the t-tests say "no single regressor matters." It's like a sports team winning every game while every individual player seems to have a terrible season — collectively they did it, individually you can't tell who.

```
Without multicollinearity:     With multicollinearity:

  X1 ───┐                        X1 ──╲
        ├──► Y                         ╲
  X2 ───┘                         X2 ──►── Y
                                        ╱
  Each lane contributes          X1 & X2 merge — can't tell
  separately and cleanly.        which lane did what.
```

---

## How to Detect It

### Method 1: Correlation Matrix

A simple table showing pairwise correlations among all regressors. Any pair with $|r| > 0.7$ is suspect. **Limitation**: only catches pairwise relationships. Three variables can be collectively collinear (e.g., $X_3 \approx X_1 + X_2$) without any pair crossing the threshold.

### Method 2: Variance Inflation Factor (VIF) — the Gold Standard

VIF catches multi-way collinearity and is the CFA exam's preferred diagnostic.

$$\boxed{\text{VIF}_j = \frac{1}{1 - R_j^2}}$$

where $R_j^2$ is from the auxiliary regression of $X_j$ on all other regressors. VIF tells you *how much the variance of $\hat{b}_j$ is inflated* by its correlation with the others.

| VIF | $R_j^2$ | Interpretation |
|---|---|---|
| **1** | 0 | Ideal — no multicollinearity |
| **> 5** | > 0.80 | Warning sign — investigate |
| **> 10** | > 0.90 | Serious multicollinearity — **must act** |

### Method 3: The F/t Paradox Itself

Significant F-stat + no significant t-stats = multicollinearity is the prime suspect. No formal test needed to raise the alarm.

---

## Worked Numerical Example

You run a regression of monthly stock returns on two macro factors:

$$R_t = b_0 + b_1 \cdot \text{GDP}_t + b_2 \cdot \text{IndProd}_t + \varepsilon_t$$

with $n = 60$ observations. Output:

| Coefficient | Estimate | Std. Error | t-stat |
|---|---|---|---|
| $b_0$ | 0.5 | 0.3 | 1.67 |
| $b_1$ (GDP) | 1.8 | 2.1 | 0.86 |
| $b_2$ (IndProd) | 1.4 | 1.9 | 0.74 |

Regression $R^2 = 0.62$; F-statistic = 46.5 (p < 0.001).

**Step 1 — Spot the paradox.** F-stat massively significant, $R^2 = 0.62$, yet neither t-stat clears 2.0. Red flag.

**Step 2 — Auxiliary regression** of GDP on IndProd yields $R_1^2 = 0.92$.

**Step 3 — Compute VIF:**

$$\text{VIF}_1 = \frac{1}{1 - 0.92} = \frac{1}{0.08} = 12.5$$

VIF > 10 → **serious multicollinearity** confirmed.

**Step 4 — Interpret the damage.** The "true" standard error (if GDP and IndProd were uncorrelated) would be roughly:

$$\text{SE}_{\text{true}} \approx \frac{2.1}{\sqrt{12.5}} = \frac{2.1}{3.54} \approx 0.59$$

That would give $t \approx 1.8 / 0.59 \approx 3.05$ — highly significant. Multicollinearity is hiding a real effect behind inflated standard errors.

**Step 5 — Fix.** Drop one variable, or combine them (e.g., a macro composite index). Re-estimate.

---

## How to Fix It

| Remedy | How It Works | When to Use |
|---|---|---|
| **Drop a redundant variable** | Remove the regressor with highest VIF (or least theoretical importance) | The simplest fix — usually right |
| **Use a proxy** | Replace a variable with a less-correlated version of the same concept | When theory demands both stay represented |
| **Combine correlated variables** | Replace GDP and IndProd with a single "macro factor" (average or PCA) | When both matter conceptually |
| **Collect more data** | Larger $n$ shrinks standard errors directly | Only if feasible |
| **Do nothing** | If the goal is *prediction* (not coefficient interpretation), multicollinearity doesn't hurt forecasts | Pure forecasting use cases |

CFA-preferred answer is almost always: **drop the offending variable or combine correlated variables**.

---

## Multicollinearity vs. Its Siblings

| Problem | What's Wrong | Coefficients? | Std. Errors? | Primary Fix |
|---|---|---|---|---|
| **Multicollinearity** | $X$'s correlated with each other | Unbiased but imprecise | **Too large** (inflated) | Drop/combine variables |
| **[[Serial Correlation]]** | Residuals correlated across time | Unbiased* | **Too small** (deflated) | Newey-West SEs |
| **[[Heteroskedasticity]]** | Residual variance not constant | Unbiased | Biased (direction varies) | White (robust) SEs |

\* Except in autoregressive models.

Notice the mirror image: **multicollinearity *inflates* SEs** (too-wide CIs, too-few rejections), while **serial correlation *deflates* SEs** (too-narrow CIs, too-many false rejections). One makes you timid, the other makes you reckless.

---

## Memory Hooks

- **The twins problem** — two variables so alike the model can't tell them apart
- **F says yes, t says no** — the signature paradox
- **VIF > 10 = fix it** — the bright-line rule
- **$\text{VIF} = 1/(1 - R_j^2)$** — "one over one minus $R^2$ of the side regression"
- **Inflated SEs, unbiased coefficients** — precision suffers, not accuracy
- **Mirror vs. serial correlation** — multicollinearity puffs SEs up, serial correlation squishes them down

---

## CFA Exam Focus

1. **Definition**: high linear correlation among independent variables
2. **Effect**: coefficients unbiased but standard errors inflated → t-stats shrink → individual variables look insignificant even when jointly they matter
3. **Classic tell**: high $R^2$ and significant F-stat, but no significant t-stats
4. **Detection**: Variance Inflation Factor (VIF > 10 = serious)
5. **Fix**: drop a redundant variable or combine correlated variables
6. **Contrast with heteroskedasticity & serial correlation** — know which problem inflates SEs vs. deflates them

## Related Notes

[[Serial Correlation]] · [[Heteroskedasticity]] · [[Ordinary Least Squares]] · [[Regression Assumptions]] · [[Variance Inflation Factor]] · [[Multiple Regression]] · [[F Distribution and F Tests]]

---