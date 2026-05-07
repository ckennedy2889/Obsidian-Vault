---
title: AIC and BIC
subject: Quantitative Methods
tags: [CFA-L2, QuantitativeMethods, Regression, ModelSelection, AIC, BIC, InformationCriteria, Parsimony, Overfitting]
aliases: [AIC, BIC, Akaike Information Criterion, Bayesian Information Criterion, Schwarz Criterion, Information Criteria, Schwarz Information Criterion, SIC]
---

# AIC and BIC

> [!abstract] The One-Sentence Version
> **AIC** and **BIC** are two scorecards for picking the best regression model from a lineup — both reward fit and punish complexity, but **AIC** is the lenient judge built for prediction, while **BIC** is the stricter judge built for finding the true underlying model.

## The Analogy — Two Judges, One Model Lineup

Imagine you're comparing five different regression models and you need a rule to pick the best one. You hire two judges.

- **AIC** is the **prediction-minded** judge: "Give me the model that'll forecast best on next year's data. If a variable even *slightly* helps the fit, I'll tolerate it." Cost of each extra variable: a flat fine of 2.
- **BIC** is the **truth-seeking** judge: "I want the most parsimonious description of reality. If a variable isn't pulling serious weight, I'm cutting it." Cost of each extra variable: a fine of $\ln(n)$ — and once your sample exceeds ~7 observations, that fine is *always* steeper than AIC's.

Give both judges the same lineup and BIC will almost always hand back a smaller, simpler model. Neither is "right" in isolation — the choice depends on whether you want to **predict** or **explain**.

> [!tip] Memory Hook — **"A before B, prediction before belief"**
> **A**IC → **A**ccuracy of prediction. **B**IC → **B**elief about the true model. BIC's $\ln(n)$ penalty is heavier, so BIC picks smaller models.

---

## 1. Motivation — Why R² and Adjusted R² Aren't Enough

You already know the two fit metrics from [[R-Squared and Adjusted R-Squared]]:

| Metric | Problem it has |
|---|---|
| **$R^2$** | "Greedy" — never decreases when a variable is added, even pure noise. Using it to compare models of different sizes is a trap. |
| **Adjusted $R^2$** | Honest about complexity but sets a **very low bar**: it rises whenever an added variable's $\lvert t \rvert > 1$, which is well below the 5% significance threshold (1.96). Plenty of non-significant variables still "pass." |

**Information criteria raise the bar.** They apply stronger penalties for complexity than adjusted $R^2$ and give you a defensible, single-number ranking across candidate models.

Both criteria attack the same enemy: **[[Overfitting]]** — the model that memorizes today's noise and fails on tomorrow's data.

---

## 2. The Formulas

Both AIC and BIC share the *same* goodness-of-fit term and differ only in how harshly they penalize complexity.

$$
\boxed{\;\mathrm{AIC} \;=\; n \ln\!\left(\frac{\mathrm{SSE}}{n}\right) \;+\; 2(k+1)\;}
$$

$$
\boxed{\;\mathrm{BIC} \;=\; n \ln\!\left(\frac{\mathrm{SSE}}{n}\right) \;+\; \ln(n)\,(k+1)\;}
$$

| Symbol | Meaning |
|---|---|
| $n$ | Sample size |
| $k$ | Number of independent variables (not counting the intercept) |
| $k+1$ | Total parameters estimated (includes intercept) |
| $\mathrm{SSE}$ | Sum of squared errors — unexplained variation |
| $n\ln(\mathrm{SSE}/n)$ | Goodness-of-fit term — shrinks as fit improves |

### The Anatomy — Two Tug-of-War Terms

```
┌─────────────────────────────────┐    ┌────────────────────────┐
│   n · ln(SSE/n)                 │    │   penalty × (k+1)      │
│   ← falls as SSE shrinks        │ +  │   ↑ grows with k       │
│   (rewarding fit)               │    │   (fining complexity)  │
└─────────────────────────────────┘    └────────────────────────┘
          GOODNESS OF FIT                    COMPLEXITY PENALTY
```

Adding a new variable can only help if the drop in the fit term **exceeds** the increase in the penalty term. Otherwise the criterion gets worse.

---

## 3. The Key Difference — Penalty Strength

This is the entire exam point.

| Criterion | Penalty per parameter | Numerical example at $n = 50$ |
|---|---|---|
| **AIC** | **2** | $2$ |
| **BIC** | **$\ln(n)$** | $\ln(50) \approx 3.91$ |

BIC's penalty *grows with sample size* while AIC's stays flat. In any realistic sample, BIC is the strict judge.

### The Crossover Point

BIC is stricter than AIC whenever $\ln(n) > 2$, which solves to:

$$n > e^2 \approx \mathbf{7.39}$$

> [!tip] Practical Rule
> For any sample size $n \ge 8$ — essentially *every* real financial dataset — **BIC penalizes extra variables more harshly than AIC** and therefore tends to pick smaller models.

---

## 4. Interpretation — Lower is Better, and Only Relative

| Rule | Detail |
|---|---|
| **Lower is better** | Both AIC and BIC are "cost" functions — the minimum wins |
| **Relative only** | An AIC of 25.8 is meaningless alone. Meaningful only as "Model A's AIC < Model B's AIC" |
| **Apples-to-apples** | Compared models must use the **same dependent variable** and the **same sample** |
| **Not a significance test** | No p-value is attached. AIC/BIC rank models but don't tell you whether the winner is "real" |

---

## 5. When to Use Which

| Goal | Preferred criterion | Why |
|---|---|---|
| **Forecasting** / out-of-sample prediction | **AIC** | Keeps variables that help prediction even if they're not strictly "true" drivers — tolerates a little extra complexity for better forecasts |
| **Identifying the true model** / parsimonious description | **BIC** | Asymptotically consistent: as $n \to \infty$, BIC converges on the true model; AIC tends to keep a few too many variables |
| Comparing nested models | Either (paired with F-test) | F-test for binary reject/keep; AIC/BIC for ranking across multiple candidates |

---

## 6. Worked Numerical Example — Selecting Between Two Models

**Setup.** An analyst predicts Return on Assets (ROA) with $n = 26$. She compares two nested models.

| Metric | Model 1 (CAPEX only) | Model 2 (CAPEX + ADV) |
|---|---|---|
| Independent variables $k$ | 1 | 2 |
| Adjusted $R^2$ | 0.875 | 0.870 |
| **AIC** | **23.899** | 25.804 |
| **BIC** | **26.523** | 28.792 |

### Reading the Numbers

- **AIC:** Model 1's 23.899 < Model 2's 25.804 → **Model 1 wins.**
- **BIC:** Model 1's 26.523 < Model 2's 28.792 → **Model 1 wins.**
- **Adjusted $R^2$:** 0.875 > 0.870 → **Model 1 wins.**

All three criteria agree: the advertising variable doesn't earn its seat. The drop in SSE from adding ADV is too small to offset the complexity penalty.

### Verifying the BIC Penalty Is Heavier

At $n = 26$:
- AIC penalty per parameter: $2$
- BIC penalty per parameter: $\ln(26) = 3.258$

BIC's per-parameter fine is ~63% steeper than AIC's. That's why BIC's gap between models (28.792 − 26.523 = 2.269) is larger than AIC's (25.804 − 23.899 = 1.905).

> [!note] When Criteria Disagree
> If AIC prefers the bigger model while BIC prefers the smaller one, you've found exactly the boundary case where the extra variable is "useful for prediction but not structurally true." Your research goal decides the tiebreaker.

---

## 7. The Strictness Ladder — How AIC/BIC Relate to Other Tools

From least strict to most strict on complexity:

```
R²            →  Adjusted R²          →  AIC                 →  BIC
(no penalty)     (|t| > 1 threshold)     (penalty = 2 each)     (penalty = ln n each)
greedy           lenient                 moderate               strict
```

| Tool | Threshold a new variable must clear |
|---|---|
| Plain $R^2$ | Nothing — any contribution keeps it |
| Adjusted $R^2$ | $\lvert t \rvert > 1$ on the new variable |
| AIC | SSE must fall enough to beat a penalty of 2 |
| BIC | SSE must fall enough to beat a penalty of $\ln(n)$ |
| F-test / p-value | $\lvert t \rvert > t_{\text{crit}}$ (e.g., 1.96 at 5%) — sharpest and most conventional |

Information criteria and the F-test answer slightly different questions — the F-test is a **statistical significance test**, while AIC/BIC are **model comparison scorecards**. They can and often do agree, but when they diverge, use the tool that matches your goal.

See: [[Hypothesis Testing in Regression]] · [[F-Test vs t-Test]]

---

## 8. Limitations and Pitfalls

| Pitfall | What can go wrong | How to protect yourself |
|---|---|---|
| **Comparing across different Y** | AIC/BIC are meaningless if the dependent variable changes (e.g., ROA vs. log(ROA)) | Compare only models with identical response variable |
| **Different samples** | Dropping rows due to missing data changes $n$ and shifts the goodness-of-fit term | Use the same observation set across all candidate models |
| **Non-nested models** | AIC/BIC *do* work across non-nested models (unlike the F-test) — but you still need identical Y and sample | Explicit check on the data |
| **Model instability in time series** | In ARMA/ARIMA specification, parameters can be unstable and AIC/BIC surfaces can be flat across nearby orders | Pair with diagnostic plots, cross-validation |
| **Not a significance test** | AIC-best model isn't necessarily statistically "significant" | Follow up with t-tests and F-tests on the chosen model |
| **Penalty assumes Gaussian-like errors** | Derivation assumes normal residuals | Check residual normality; use transformations if violated |

---

## 9. Quick-Reference Cheat Sheet

### Formulas

$$\mathrm{AIC} = n\ln(\mathrm{SSE}/n) + 2(k+1)$$

$$\mathrm{BIC} = n\ln(\mathrm{SSE}/n) + \ln(n)(k+1)$$

### Decision Logic

| Scenario | Choose |
|---|---|
| Need to forecast → pick the lower **AIC** |
| Need the "true" parsimonious model → pick the lower **BIC** |
| Both agree → you're done |
| They disagree → your goal breaks the tie |

### The Numbers to Know

| Fact | Value |
|---|---|
| AIC penalty per parameter | 2 |
| BIC penalty per parameter | $\ln(n)$ |
| Crossover sample size where BIC > AIC penalty | $n > e^2 \approx 7.39$ |
| Verdict for any realistic sample | BIC is always stricter |

---

## 10. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Describe** why $R^2$ and adjusted $R^2$ are insufficient for model selection across different-sized models.
- [x] **State** the formulas for AIC and BIC and identify the goodness-of-fit and complexity-penalty terms.
- [x] **Calculate** AIC and BIC given $n$, $k$, and SSE.
- [x] **Compare** AIC's and BIC's penalty factors and identify the $n > 7.39$ crossover.
- [x] **Choose** AIC for prediction tasks and BIC for identifying the true model, with justification.
- [x] **Interpret** AIC/BIC as relative, minimization metrics (lower is better; not interpretable in isolation).
- [x] **Apply** AIC and BIC to a head-to-head model comparison and state the verdict.
- [x] **Explain** the strictness ladder: $R^2$ → Adjusted $R^2$ → AIC → BIC → F-test.
- [x] **Recognize** the apples-to-apples requirement (same Y, same sample) and other limitations.

---

## Related Notes

- [[R-Squared and Adjusted R-Squared]] — the less-strict siblings in the goodness-of-fit family
- [[Hypothesis Testing in Regression]] — the F-test and t-tests that complement information criteria
- [[Multiple Regression - Basics and Assumptions]] — where SSE, $k$, and $n$ come from
- [[Overfitting]] · [[Parsimony]] — the concepts AIC/BIC operationalize
- [[F-Test vs t-Test]] · [[F Distribution and F Tests]]
- [[P-Value]] — significance-based alternative approach to model choice
