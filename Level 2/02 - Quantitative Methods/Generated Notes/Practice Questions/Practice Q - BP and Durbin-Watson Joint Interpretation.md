---
title: "Practice Q - Breusch-Pagan and Durbin-Watson Joint Interpretation"
subject: "Quantitative Methods"
tags: [CFA-L2, practice-question, regression-diagnostics, breusch-pagan, durbin-watson, heteroskedasticity, serial-correlation]
source: "unknown"
date: 2026-04-23
---

# Breusch-Pagan and Durbin-Watson Joint Interpretation

## Question

![[2026-04-23-bp-dw-joint-interpretation.png]]

Consider the following regression statistics:

| | Coefficients | Standard Error | t-statistic | p-value |
|---|---|---|---|---|
| Intercept | 2.12 | 0.08 | 26.50 | 0.0000 |
| $X_1$ | 0.67 | 0.19 | 3.53 | 0.0011 |
| $X_2$ | 0.75 | 0.13 | 5.77 | 0.0000 |
| $X_3$ | 0.13 | 0.89 | 0.15 | 0.8815 |

| Diagnostic | Value |
|---|---|
| Breusch-Pagan (BP) Test Statistic | **8.93** |
| Residual Standard Error | 1.31 |
| Multiple R-squared | 0.1786 |
| Adjusted R-squared | 0.1250 |
| Observations | **50** |
| Durbin-Watson Statistic | **1.51** |

**Critical values** ($\chi^2$ with df = 3, Student's $t$ with df = 46, $F$ with df = 3, 46):

| Significance | $\chi^2_3$ | $t_{46}$ | $F_{3,46}$ |
|---|---|---|---|
| 0.05 | 7.81 | 2.01 | 2.81 |
| 0.01 | 11.34 | 2.69 | 4.24 |

**Durbin-Watson critical values** (n = 50):

| α | K=3 $d_L$ | K=3 $d_U$ |
|---|---|---|
| 0.05 | 1.42 | 1.67 |
| 0.01 | 1.25 | 1.49 |

Consider the following statements:

- **Statement 1:** We can be 95% confident that there is no positive serial correlation in this model.
- **Statement 2:** We can be 99% confident that there is conditional heteroskedasticity in this model.

Which of these statements is correct?

- **A.** Only Statement 1
- **B.** Only Statement 2
- **C.** Neither statement

---

## Correct Answer: C — Neither statement is correct

This question is doing something subtle and **very CFA-like**: it gives you two plausible-sounding claims, each dressed up in the language of a formal diagnostic test, and asks whether the evidence *actually* supports them at the stated confidence level. Both claims fail — but for different reasons, and each failure teaches a different lesson about how these tests are read.

### What is this testing?

The question tests whether you can execute the full decision procedure for two different regression diagnostics:

1. The **[[Durbin-Watson Test|Durbin–Watson test]]** for first-order positive [[Serial Correlation]] — which has the unusual quirk of an **inconclusive zone** sandwiched between the reject and fail-to-reject regions.
2. The **[[Breusch–Pagan Test]]** for [[Conditional heteroskedasticity]] — a straightforward right-tailed $\chi^2$ test where you must match the statistic against the correct critical value for the stated confidence level.

The trap in both statements is that the numeric results sit *close* to the critical bounds, so a fresh learner who eyeballs them instead of running the comparison rigorously will get fooled.

---

### Evaluating Statement 1 — the Durbin-Watson reasoning

The Durbin-Watson statistic is **DW = 1.51**. The regression has $k = 3$ regressors and $n = 50$. For a 95% confidence test of positive serial correlation, the table gives:

$$d_L = 1.42, \qquad d_U = 1.67$$

Recall the Durbin-Watson decision map for **positive serial correlation**:

```
0 ─────[ d_L = 1.42 ]─────[ d_U = 1.67 ]─────2
   REJECT H₀          INCONCLUSIVE          FAIL TO REJECT
   (positive SC)         zone                (no positive SC)
```

Now locate DW = 1.51:

$$1.42 \; < \; 1.51 \; < \; 1.67$$

That places us **squarely in the inconclusive region**. The test gives us no answer — we can neither conclude there *is* positive serial correlation nor that there *isn't*. So the claim "we can be 95% confident that there is no positive serial correlation" is **unsupported**. To reach that conclusion, DW would have needed to exceed $d_U = 1.67$. It didn't.

This is the classic Durbin-Watson trap: the test has **three outcomes, not two**. A value near — but below — $d_U$ is not the same as "no serial correlation."

**Statement 1 is incorrect.**

---

### Evaluating Statement 2 — the Breusch-Pagan reasoning

The Breusch-Pagan statistic is **BP = 8.93**, distributed as $\chi^2$ with $df = k = 3$ (the number of regressors in the original model — see [[Breusch–Pagan Test]] for why).

For the claim to hold at **99% confidence**, BP must exceed the $\chi^2_3$ critical value at $\alpha = 0.01$:

$$\chi^2_{3,\,0.01} = 11.34$$

Compare:

$$BP = 8.93 \; < \; 11.34 = \chi^2_{3,\,0.01}$$

BP falls **below** the 99% critical value, so we **fail to reject** $H_0$: homoskedasticity at the 1% significance level. We cannot be 99% confident that conditional heteroskedasticity is present.

Note the subtlety: at the **95%** level, the critical value is only 7.81, and $BP = 8.93 > 7.81$ — so we *could* reject homoskedasticity at 95% confidence. But Statement 2 specifically claims **99%** confidence, and at that more demanding threshold the evidence isn't strong enough.

**Statement 2 is incorrect.**

---

### Putting it together

| Statement | Claim | Test | Stat | Critical | Verdict |
|---|---|---|---|---|---|
| 1 | 95% confident: no positive SC | DW | 1.51 | $d_U = 1.67$ | Inconclusive — can't conclude no SC |
| 2 | 99% confident: conditional hetero. | BP | 8.93 | $\chi^2_{3,\,0.01} = 11.34$ | Fail to reject — can't conclude hetero. |

Because both fail, the answer is **C — Neither statement is correct.**

---

### The intuition — why this is a favorite CFA trap

Both statements tempt you to *round* — to treat "close to the critical value" as "past the critical value." CFA loves this pattern because in real analyst work, getting the confidence level and decision rule exactly right is what separates a disciplined quantitative analyst from one who trades on phantom signals.

Two habits from this problem that carry through the curriculum:

1. **Always write down which confidence level a claim demands.** 95% and 99% use *different* critical values, and a statistic can be "significant" at one and not the other.
2. **For Durbin-Watson, memorize the three-zone decision map.** Most other tests you know (t, F, $\chi^2$) are binary — reject or don't. DW is the rare test where "inconclusive" is a legitimate verdict, and forgetting that is the standard trap.

---

## The Trap — Most Tempting Wrong Answer

**B — Only Statement 2.**

This is the seductive option because $BP = 8.93$ *looks* comfortably above the $\chi^2_3$ critical value — which it is, at the 95% level (7.81). A student who checks the 95% column and forgets that Statement 2 demands 99% will happily endorse it. The test writers specifically picked a BP value that is significant at 5% but not at 1% to punish this exact mistake.

**How to avoid it:** When a statement specifies a confidence level, underline it and go hunt for *that* column in the critical value table — not the default α = 0.05. The p-value mindset — "small is significant" — has to be anchored to the specific α the problem asks about.

A secondary trap is option **A — Only Statement 1.** A student who remembers the DW rule of thumb "close to 2 ≈ no serial correlation" and sees 1.51 not-too-far-from-2 might wave Statement 1 through. But 1.51 is well below 2 *and* below $d_U = 1.67$ — it is not a clean fail-to-reject. The formal rule wins over the rule of thumb.

---

## Key Takeaway

> [!tip] Memory Hook
> **Confidence matters as much as the statistic.** A diagnostic value that crosses the 95% bar may still sit below the 99% bar — a statement demanding "99% confident" is a different question. And for **Durbin-Watson, remember the three zones** — *inconclusive* is a real answer, not a rounding error.

---

## Related Concepts

- [[Serial Correlation]] — full treatment of the serial correlation problem and DW test
- [[Durbin-Watson Test]] — the test's mechanics and three-zone decision rule
- [[Breusch–Pagan Test]] — glossary-level deep dive on the BP procedure
- [[Homoscedasticity and Heteroscedasticity]] — why conditional heteroskedasticity breaks inference
- [[Conditional heteroskedasticity]] — the specific flavor BP detects
- [[Hypothesis Testing in Regression]] — general framework for these decision rules
- [[F Distribution and F Tests]] — cousin test; different statistic, same "reject-if-exceeds-critical" logic
