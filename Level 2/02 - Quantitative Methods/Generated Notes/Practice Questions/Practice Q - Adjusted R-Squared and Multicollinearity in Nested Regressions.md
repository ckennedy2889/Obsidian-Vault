---
title: "Practice Q - Adjusted R² and Multicollinearity in Nested Regressions"
subject: "Quantitative Methods"
tags: [CFA-L2, practice-question, regression, adjusted-r-squared, multicollinearity]
source: "unknown"
date: 2026-04-22
---

# Adjusted R² and Multicollinearity — Nested Regression Comparison

## Question

> *(Screenshot was captured from a temp location that has since been cleared — transcription below.)*

Consider the following results for two regressions:

**Regression 1**

| | Coefficients | Standard Error | t-statistic | p-value |
|---|---|---|---|---|
| Intercept | 2.12 | 0.08 | 26.50 | 0.0000 |
| X₁ | 0.77 | 0.16 | 4.81 | 0.0000 |
| X₂ | 0.86 | 0.09 | 9.56 | 0.0000 |

**Regression 2**

| | Coefficients | Standard Error | t-statistic | p-value |
|---|---|---|---|---|
| Intercept | 2.12 | 0.08 | 26.50 | 0.0000 |
| X₁ | 0.67 | 0.19 | 3.53 | 0.0011 |
| X₂ | 0.75 | 0.13 | 5.77 | 0.0000 |
| X₃ | 0.13 | 0.89 | 0.15 | 0.8815 |

Where the number of observations, dependent variable, X₁, and X₂ are the same for both regressions.

**Statement 1:** X₂ is correlated with X₃.
**Statement 2:** R̄² will likely be higher for the second regression.

**Which of these statements is correct?**

---

## Correct Answer: Only Statement 1 is correct.

### What is this testing?

This is a **nested-model comparison**. Regression 1 has two regressors; Regression 2 adds a third ($X_3$) while keeping the same dataset, same dependent variable, and the same $X_1, X_2$. When you nest one regression inside another and compare the output line-by-line, two specific diagnostic stories emerge:

1. **The fingerprint of [[CFA_Glossary/Multicollinearity]]** — adding a correlated variable inflates the standard errors of the *existing* coefficients without necessarily changing the point estimates by a huge amount.
2. **Adjusted R²'s asymmetric behavior** — [[R-Squared and Adjusted R-Squared|$\bar{R}^2$]] only rises when the newly added variable earns its keep. Adding a "dead weight" regressor makes $\bar{R}^2$ *fall*, even though plain R² mechanically rises.

Both statements hand you the evidence to solve this on a 10-second inspection, once you know what to look for. No formulas or chi-square tables needed — just read the output.

### Statement 1 — *"X₂ is correlated with X₃"* → **TRUE**

The tell is hidden in plain sight across two lines of the output.

When we move from Regression 1 to Regression 2, here's what happens to the *existing* coefficients' standard errors:

| | SE in Reg 1 | SE in Reg 2 | Change |
|---|---|---|---|
| X₁ | 0.16 | 0.19 | ↑ 19% larger |
| X₂ | 0.09 | 0.13 | **↑ 44% larger** |

And look at X₃'s own standard error in Regression 2: **0.89** — enormous relative to the coefficient 0.13. That's why X₃'s t-stat is a humiliating 0.15 and its p-value 0.88.

This pattern — where **adding a new regressor inflates the SEs of the regressors already in the model** — is the textbook fingerprint of multicollinearity. Recall the formula for the standard error of a coefficient:

$$SE(\hat{b}_j) = \sqrt{\frac{\text{MSE}}{(n-1) \cdot s_{X_j}^2 \cdot (1 - R_j^2)}}$$

The term $(1 - R_j^2)$ in the denominator is the tolerance — the slice of $X_j$'s variation that's *unique*, not already explained by the other regressors. When $X_3$ enters and happens to be correlated with $X_2$, the auxiliary $R_2^2$ (from regressing $X_2$ on $X_1$ and the new $X_3$) **rises**, so $(1 - R_2^2)$ shrinks, and $SE(\hat{b}_2)$ gets bigger — which is exactly what we see (0.09 → 0.13).

The same story explains X₃'s own gigantic SE of 0.89: if $X_3$ is nearly predictable from $X_1$ and $X_2$, its auxiliary $R_3^2$ approaches 1, its [[Variance Inflation Factor (VIF)|VIF]] explodes, and its coefficient has almost no unique information to lean on.

**Why X₂ specifically and not X₁?** Both SEs went up, so technically we can't be sure *only* X₂ is the correlated one — X₁ might be implicated too. But X₂'s SE blew up by 44% vs. X₁'s 19%, making X₂ the more obviously correlated with X₃. The statement "X₂ is correlated with X₃" is consistent with — and the most natural reading of — the evidence.

**Why the coefficients on X₁ and X₂ also shifted slightly** (X₁: 0.77 → 0.67; X₂: 0.86 → 0.75): this is another multicollinearity signature. When regressors are correlated, their fitted coefficients become **unstable** — small changes to the model (like adding or removing a correlated variable) cause noticeable shifts in the partial slopes. If $X_3$ were truly orthogonal (uncorrelated) to $X_1$ and $X_2$, the coefficients on $X_1$ and $X_2$ in Regression 2 would match Regression 1 almost exactly, and their standard errors would be essentially unchanged.

### Statement 2 — *"R̄² will likely be higher for Regression 2"* → **FALSE**

This is the classic [[R-Squared and Adjusted R-Squared|Adjusted R²]] trap. The rule to memorize:

> [!info] The Adjusted R² Rule
> Adjusted R² rises when you add a variable **only if the absolute t-statistic on that variable exceeds 1**.

**X₃'s t-statistic is 0.15.** That's nowhere near 1 — it's not even a whisper of significance. Adding X₃ contributes *some* tiny explanatory power (plain R² will tick up, because it always does when you add a variable), but the added complexity penalty in the $\bar{R}^2$ formula swamps the gain. Net result: **$\bar{R}^2$ will fall**, not rise, when moving from Regression 1 to Regression 2.

### The underlying formula, so you see why |t| > 1 is the threshold

Adjusted R² is defined:

$$\bar{R}^2 = 1 - \left(\frac{n - 1}{n - k - 1}\right)(1 - R^2)$$

When you add a variable, $R^2$ rises by some amount $\Delta R^2$ and $k$ increases by 1. The algebra of whether $\bar{R}^2$ rises or falls reduces to: **does the gain in $R^2$ beat the penalty for one more parameter?** That break-even point is algebraically equivalent to $|t_j| > 1$ on the newly added variable. A variable with $|t| \leq 1$ is *dead weight* for adjusted-R² purposes.

X₃'s t-stat of 0.15 is so far below 1 that Regression 2's $\bar{R}^2$ will be *meaningfully lower* than Regression 1's, not higher.

### Putting the two statements together

- **Statement 1 correct:** the standard errors of X₁ and X₂ both inflated when X₃ was added, and X₃'s own SE is enormous — multicollinearity fingerprint. Correlation between X₂ and X₃ is the natural read.
- **Statement 2 incorrect:** X₃'s t-stat of 0.15 is far below 1, so adding it *lowers* Adjusted R² rather than raising it. Plain R² rises (mechanically), but the penalized version does not.

**Only Statement 1 is correct.**

---

## The Trap — Most Tempting Wrong Answer

The seductive wrong answer here is **"Both statements are correct"** — the student sees Regression 2 with one more variable and assumes "more variables = better fit = higher R-squared of any kind."

### Why it looks right

It conflates two different R-squared concepts:

- **Plain R²** *always* rises (or stays flat) when you add a variable, because OLS can always set the new coefficient to zero and recover the original fit. So it's true that R² of Regression 2 > R² of Regression 1.
- **Adjusted R²** is *specifically engineered* to punish this behavior. It penalizes per-parameter complexity precisely so that you're not tricked into thinking a fatter model is a better model.

Students who don't internalize that $\bar{R}^2$ can *decrease* when a weak variable is added will fall for Statement 2.

### The specific mistake

Forgetting (or never learning) the **"|t| > 1" shortcut** for Adjusted R². If you see the newly added variable's t-stat, you get the answer for free — no algebra, no formulas, just a two-second glance.

### How to avoid it

On exam day, whenever a question asks about Adjusted R² behavior when adding or removing a regressor, immediately look at the absolute t-statistic on the variable being added or removed:

- $|t| > 1$: the move improves $\bar{R}^2$ (variable earns its keep).
- $|t| < 1$: the move hurts $\bar{R}^2$ (variable is dead weight).
- $|t| = 1$ (exactly): $\bar{R}^2$ unchanged.

X₃ has $|t| = 0.15$ — dead weight → Adjusted R² falls.

---

## Key Takeaway

> [!tip] Memory Hook
> **Inflated SEs across the board = multicollinearity; |t| ≤ 1 on a new variable = Adjusted R² falls.** Read those two signals off the output table and you've solved any "compare two nested regressions" question in under thirty seconds.

---

## Related Concepts

- [[CFA_Glossary/Multicollinearity]] — the underlying violation detected by inflated SEs when regressors are added
- [[Variance Inflation Factor (VIF)]] — the quantitative measure of the collinearity being diagnosed here
- [[R-Squared and Adjusted R-Squared]] — formula, derivation of the |t| > 1 rule, and when to trust each statistic
- [[Regression Statistics - Complete Reference]] — master reference for every number on a regression output table
- [[Hypothesis Testing in Regression]] — t-tests, p-values, and joint-vs-individual significance
- [[P-Value]] — interpretation of the 0.8815 on X₃ (consistent with "no relationship")
