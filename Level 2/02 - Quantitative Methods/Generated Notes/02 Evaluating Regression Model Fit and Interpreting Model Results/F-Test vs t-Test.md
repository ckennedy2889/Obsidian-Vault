---
title: F-Test vs t-Test
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, hypothesis-testing]
aliases: [t-Test vs F-Test, F vs t, Joint Significance Test, Individual Significance Test]
---

# F-Test vs t-Test

## The Real-World Analogy First

Picture a soccer team after a season. You can ask two very different questions about them:

1. **"Is striker #9 pulling her weight?"** — a question about *one* player's individual contribution.
2. **"Is this team actually any good?"** — a question about the *entire squad* working together.

The two questions need different answers, different evidence, and different statistical tools. In regression, the **t-test** answers the first kind of question (one player / one coefficient), while the **F-test** answers the second (the whole squad / all coefficients together, or a subset of them).

Both are "report cards" you use to judge whether the variables in your regression are actually doing useful work, or just producing random noise.

---

## The One-Line Distinction

> **t-test** = "Does *this specific variable* matter?"
> **F-test** = "Does this *group* of variables explain anything?"

The t-test is a scalpel — surgical, one coefficient at a time. The F-test is a net — it scoops up several coefficients and tests them jointly.

---

## Hypotheses: What Each Test Is Actually Proving

| Feature | t-Test (Single Coefficient) | F-Test (Overall Model) | F-Test (Joint / Subset) |
|---|---|---|---|
| **Null $H_0$** | $b_j = 0$ | $b_1 = b_2 = \cdots = b_k = 0$ | $b_{j+1} = \cdots = b_{j+q} = 0$ |
| **Alternative $H_a$** | $b_j \neq 0$ | At least one $b_j \neq 0$ | At least one of the $q$ is $\neq 0$ |
| **Plain English** | "This variable is useless" | "The entire model is useless" | "This *subset* of variables adds nothing" |

Key nuance: the F-test's alternative is "at least one works" — it does **not** tell you *which* one. That's why you always follow a rejected F-test with individual t-tests to isolate the drivers.

---

## Test Statistic Formulas

### t-statistic (single coefficient)

$$t = \frac{\hat{b}_j - B_j}{s_{\hat{b}_j}}$$

In plain English: **(Estimated Slope – Hypothesized Slope) / Standard Error**. For the usual "is it zero?" test, $B_j = 0$, so the t-stat simplifies to the estimate divided by its standard error.

### F-statistic (overall model significance)

$$F = \frac{\text{MSR}}{\text{MSE}} = \frac{\text{RSS} / k}{\text{SSE} / (n - k - 1)}$$

In plain English: **Average variation the model explains / Average variation left as a mystery**. When the model explains far more than residual noise, F is large and the model is significant.

### F-statistic (joint / nested test of $q$ restrictions)

$$F = \frac{(SSE_R - SSE_U) / q}{SSE_U / (n - k - 1)}$$

where:
- $SSE_R$ = sum of squared errors from the **restricted** model (variables you want to test are dropped)
- $SSE_U$ = sum of squared errors from the **unrestricted** (full) model
- $q$ = number of restrictions (variables dropped)
- $n - k - 1$ = degrees of freedom of the *unrestricted* model

Intuition: how much does error *drop* when you add the $q$ variables back? If adding them barely helps (numerator small), they're not worth keeping.

---

## Degrees of Freedom & Tail Direction

| Feature | t-test | F-test |
|---|---|---|
| **Degrees of freedom** | $n - k - 1$ | $(k, \ n - k - 1)$ — two values |
| **Distribution shape** | Symmetric bell (like normal, heavier tails) | Right-skewed, only positive values |
| **Tails used** | **Two-tailed** (testing $\neq 0$) or one-tailed (testing $>$ or $<$) | **Always one-tailed (right tail)** |
| **Critical value** | $\pm t_{\alpha/2}$ for two-tailed | $F_{\alpha}$ at right tail only |

Why is the F-test always one-tailed? The F-stat is a *ratio of variances*, which can't be negative. We only ever ask "is explained variance *bigger* than unexplained?" — never the reverse. Rejection always happens in the right tail.

```
   t-distribution                   F-distribution
   (symmetric)                     (right-skewed, ≥ 0)

       ___                           __
      /   \                         |  \__
  ___/     \___                     |     \___
 /             \                    |         \___
-t            +t                    0           F_crit
(reject)    (reject)                         (reject)
 two-tailed rejection               one-tailed, right tail only
```

---

## When to Use Which

| Situation | Use | Why |
|---|---|---|
| Test if *one* variable matters | **t-test** | Surgical — isolates a single coefficient |
| Test if the *entire model* has explanatory power | **F-test (overall)** | Validates the model before trusting individual coefficients |
| Test if a *subset* of variables jointly matters | **F-test (joint / nested)** | Lets you test "should we keep these three together?" |
| Compare a restricted vs. unrestricted model | **F-test (nested)** | Measures the improvement from adding variables |
| Test a coefficient against a non-zero value (e.g., $b_1 = 1$) | **t-test** | Only the t-test lets you plug in a custom $B_j$ |
| Diagnose **multicollinearity** | Both together | The F-vs-t paradox (F significant, t's not) is the signature |

### The Workflow

1. **Run the overall F-test first.** If you can't reject $H_0$ for the whole model, there's no point inspecting individual coefficients — nothing is working.
2. **If F is significant, move to individual t-tests** to find which variables are actually doing the work.
3. **If F is significant but no t-test is** — suspect [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]. This is the classic F-vs-t paradox.

---

## The $F = t^2$ Relationship

For a single restriction (testing just *one* coefficient), the F-test and the two-tailed t-test are mathematically equivalent:

$$F = t^2 \qquad \text{(when } q = 1 \text{)}$$

This holds in any of these cases:
- Simple (one-regressor) regression: testing overall model significance
- Multiple regression: testing a single coefficient via a joint-test machinery ($q = 1$)

Intuitively, squaring the t-stat throws away the sign (positive vs. negative deviation) and keeps only the magnitude — which is exactly what the one-tailed F-test cares about. The p-values from the two tests will match exactly.

**Exam shortcut:** If you're given a t-stat of 3.0 on a single coefficient, the equivalent F-stat is $3.0^2 = 9.0$.

---

## Worked Context Example

**Scenario:** An analyst models a company's **Return on Assets (ROA)** using three variables: Capital Investment (**CAPEX**), Advertising (**ADV**), and **R&D**.

$$\text{ROA} = b_0 + b_1 \text{CAPEX} + b_2 \text{ADV} + b_3 \text{R\&D} + \varepsilon$$

### Step 1 — Overall F-test

Compute $F = 54.40$ with critical value $F_{0.05, (3, n-4)} = 4.82$.

Since $54.40 > 4.82$, **reject $H_0$**. At least one variable matters; the model as a whole is useful.

### Step 2 — Individual t-tests

| Variable | t-stat | Verdict |
|---|---|---|
| CAPEX | **11.65** | Reject $H_0$ — star predictor |
| ADV | $-0.35$ | Fail to reject — not useful on its own |
| R&D | (small) | Fail to reject — not useful on its own |

### Step 3 — Joint F-test: can we drop ADV and R&D together?

Test $H_0$: $b_2 = b_3 = 0$ (two restrictions, $q = 2$).

Compute joint $F = 0.1188$. Compare to critical value $\approx 3.00$ at $\alpha = 0.05$.

Since $0.1188 < 3.00$, **fail to reject**. ADV and R&D add no joint value — a simpler model with just CAPEX is preferred. This is a classic use of the F-test that **no pair of t-tests could replicate** — maybe ADV and R&D each look weak individually but together capture a marketing-innovation factor. The joint F-test answers "do they matter *together*?" definitively.

---

## Comparison Cheat Sheet

| Dimension | t-Test | F-Test |
|---|---|---|
| **Scope** | One coefficient | Multiple coefficients (including the whole model) |
| **Question** | "Does $X_j$ matter?" | "Does this group of $X$'s matter?" |
| **Statistic** | $(\hat{b}_j - B_j) / s_{\hat{b}_j}$ | MSR/MSE or $\Delta SSE$-based |
| **Distribution** | Student's t, symmetric | F-distribution, right-skewed |
| **DoF** | $n - k - 1$ | $(q, \ n - k - 1)$ |
| **Tails** | Two-tailed (usually), optionally one | Always one-tailed (right) |
| **Custom hypothesis ($B_j \neq 0$)?** | ✅ Yes | ❌ No (only restriction = 0) |
| **Can identify *which* variable?** | ✅ Yes | ❌ No — only "at least one" |
| **Special relationship** | $t^2 = F$ when $q = 1$ | Same equivalence, squared |

---

## Memory Hooks

- **t = individual, F = team** — t-test asks about one player, F-test about the squad
- **F is always right-tailed** — it's a variance ratio, can't be negative
- **$F = t^2$ for one restriction** — squaring the t-stat erases sign, keeps magnitude
- **"F first, then t"** — validate the model overall, then diagnose individuals
- **F-vs-t paradox** — F significant + all t's insignificant → suspect [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- **Joint F-test for subsets** — the only tool for "do these $q$ variables matter *together*?"

---

## CFA Exam Focus

1. **Use t-test for single coefficient; F-test for joint or overall significance**
2. **Know the hypotheses cold** — especially that the F-test's $H_a$ is "at least one $b_j \neq 0$," not "all are nonzero"
3. **F is always one-tailed (right)**; t is usually two-tailed
4. **Nested F-test formula** — know $SSE_R$, $SSE_U$, $q$, and what each represents
5. **$F = t^2$** when testing a single restriction
6. **F-vs-t paradox** = multicollinearity red flag
7. **Degrees of freedom**: t uses $n - k - 1$; F uses $(k, n - k - 1)$ for overall, $(q, n - k - 1)$ for joint

## Related Notes

[[F Distribution and F Tests]] · [[Multiple Regression]] · [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] · [[Serial Correlation]] · [[Heteroskedasticity]] · [[Hypothesis Testing]] · [[Ordinary Least Squares]] · [[Regression Assumptions]] · [[Coefficient of Determination]]

---