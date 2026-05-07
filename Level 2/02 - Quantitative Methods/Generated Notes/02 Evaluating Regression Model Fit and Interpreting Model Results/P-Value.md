---
title: P-Value
subject: Quantitative Methods
tags: [CFA-L2, QuantitativeMethods, HypothesisTesting, PValue, Significance, Regression, TTest, FTest, StatisticalInference]
aliases: [p-value, p value, P-Value, Probability Value, Observed Significance Level]
---

# P-Value

> [!abstract] The One-Sentence Version
> The **p-value** is the probability of seeing a test statistic *at least as extreme* as the one you got, **if the null hypothesis were actually true** — so a small p-value means "the data I saw is too weird to be consistent with the null."

## The Analogy — The Courtroom Surprise Meter

Imagine you're on a jury. The defendant is presumed innocent ($H_0$). The prosecution shows you evidence. Your job isn't to decide whether the defendant is innocent or guilty — your job is to ask: **"How surprising is this evidence *if the defendant really were innocent?*"**

- If the evidence is unsurprising (high p-value), you acquit. The story hangs together.
- If the evidence is wildly improbable under innocence (low p-value), you convict. The "innocent" story no longer fits the facts.

That's the p-value. It's a **surprise meter** — a numeric answer to the question "*how weird is this data under the null?*" Small p = very weird = reject the null.

> [!tip] Memory Hook — **"p is the weird-o-meter"**
> p-value = P(data this extreme | $H_0$ true). The smaller the p-value, the weirder your result would be if the null were right — and the stronger your reason to reject.

---

## 1. The Formal Definition

$$
\boxed{\;p\text{-value} \;=\; P\bigl(\,\lvert T \rvert \ge \lvert t_{\text{obs}} \rvert \;\bigm|\; H_0 \text{ true}\,\bigr)\;}
$$

(for a two-tailed test with test statistic $T$ and observed value $t_{\text{obs}}$)

In words: **"Assume the null is true. Under that assumption, what fraction of possible test statistics would be as extreme as — or more extreme than — the one I just computed?"**

That fraction is your p-value.

### Three Equivalent Labels You'll See

| Label | What it emphasizes |
|---|---|
| "p-value" | The number itself |
| "Observed significance level" | The *smallest* $\alpha$ at which you'd still reject $H_0$ |
| "Prob." column in software output | Where you'll literally see it in regression tables |

---

## 2. What the P-Value Is **NOT** — Critical Misinterpretations

These misreadings appear on every exam and in every industry report. Commit them to memory.

| Wrong statement | Why it's wrong |
|---|---|
| "p = 0.03 means there's a 3% chance $H_0$ is true" | p-values are computed *assuming* $H_0$ is true; they can't tell you the probability of that assumption itself |
| "p = 0.03 means there's a 97% chance $H_a$ is true" | Same error, flipped side. Frequentist p-values say nothing about $H_a$'s probability |
| "p-value equals the probability of a Type I error" | The **Type I error rate is $\alpha$**, which *you* choose before the test. The p-value just tells you where you landed on that day's data |
| "A smaller p-value means a larger effect size" | Wrong. A p-value only measures *how inconsistent* data is with $H_0$ — not how *big* the effect is. Huge samples make tiny effects "significant" |
| "p > 0.05 means $H_0$ is true" | Failing to reject ≠ accepting. It just means you lack evidence to reject |

> [!warning] The Conditional Direction Matters
> p-value = $P(\text{data} \mid H_0)$, **not** $P(H_0 \mid \text{data})$. These two quantities are wildly different. To get the second (Bayesian posterior), you'd need a prior on $H_0$ and Bayes' theorem.

---

## 3. How the P-Value Is Computed

A p-value is always the **tail area** of the reference distribution beyond your observed test statistic.

### For a t-Statistic (Coefficient Test)

1. Compute $t_{\text{obs}} = (\hat b_j - B_0)/s_{\hat b_j}$.
2. Find $\mathrm{df} = n - k - 1$.
3. Locate $t_{\text{obs}}$ on the t-distribution with those df.
4. **Two-tailed p-value** $= 2 \times P(T > \lvert t_{\text{obs}} \rvert)$ — area in both tails.
5. **One-tailed p-value** $= P(T > t_{\text{obs}})$ (right-tail) or $P(T < t_{\text{obs}})$ (left-tail).

```
Two-Tailed P-Value (t-distribution, df = 25)
                      ∧
                     ╱ ╲
                    ╱   ╲
                   ╱     ╲
                  ╱       ╲
              ░░░╱         ╲░░░
              ↑             ↑
         −t_obs          +t_obs
         (shaded tail + shaded tail = p)
```

### For an F-Statistic (Joint / Overall Test)

F is always positive and we only care about extreme-large values (tons of explained variation), so F-tests are **always right-tailed**:

$$p\text{-value}_F = P(F_{\text{num df, den df}} > F_{\text{obs}})$$

### Software vs. Table Lookup

| Context | How you get p |
|---|---|
| Excel / Python / R / Stata output | Reported to 4+ decimal places next to each coefficient |
| CFA exam (no software) | Bracket it with a t-table — find the two t-table values your $t_{\text{obs}}$ falls between, and your p is between those column probabilities |

---

## 4. The Decision Rule — Two Paths, One Conclusion

$$
\boxed{\;\text{Reject } H_0 \;\Longleftrightarrow\; p\text{-value} < \alpha\;}
$$

| Approach | What you compare |
|---|---|
| **Critical-value path** | $\lvert t_{\text{obs}} \rvert$ vs $t_{\text{crit}}$ |
| **P-value path** | $p$ vs $\alpha$ |

These are **algebraically equivalent**: $\lvert t_{\text{obs}} \rvert > t_{\text{crit}}$ if and only if $p < \alpha$. Pick the one that matches the information you have.

### The P-Value's Edge

P-values communicate *gradation*. Two researchers both at $\alpha = 0.05$ may reach the same conclusion, but their strength of evidence is different:

- p = 0.048 — marginal rejection
- p = 0.0003 — overwhelming rejection

Critical-value-only reporting hides that distinction.

---

## 5. One-Tailed vs. Two-Tailed P-Values

| | Two-tailed | One-tailed |
|---|---|---|
| Alternative | $\beta_j \neq B_0$ | $\beta_j > B_0$ or $\beta_j < B_0$ |
| Default output | Yes — software defaults | Requires manual manipulation |
| Relationship | p-one-tail $= \tfrac{1}{2}\,$p-two-tail (when $t_{\text{obs}}$ is on the hypothesized side) | — |

> [!warning] Don't Halve After the Fact
> Commit to one-tailed or two-tailed *before* running the test. Halving a two-tailed p-value *because it's inconvenient* is a well-documented form of **p-hacking**.

---

## 6. Common Thresholds and Significance Language

| p-value range | Exam / industry language | Starred-notation shorthand |
|---|---|---|
| $p < 0.01$ | "Highly significant" | *** |
| $0.01 \le p < 0.05$ | "Significant at the 5% level" / "Statistically significant" (default standard) | ** |
| $0.05 \le p < 0.10$ | "Weakly significant" / "Marginally significant" | * |
| $p \ge 0.10$ | "Not statistically significant" | (blank) |

These thresholds are **conventions**, not laws of nature. A p = 0.051 result isn't meaningfully different from p = 0.049 — yet exam questions and industry practice treat them as opposite verdicts. Report the p-value itself, not just the binary verdict.

---

## 7. Worked Example — Step by Step

**Setup.** You test a size-factor coefficient in a regression. You get $t_{\text{obs}} = 2.5$ with $\mathrm{df} = 25$. Two-tailed test. $\alpha = 0.05$.

**Step 1 — Hypotheses.**

- $H_0$: $\beta_{\text{size}} = 0$
- $H_a$: $\beta_{\text{size}} \neq 0$

**Step 2 — Bracket the p-value using a t-table (df = 25).**

| Table entry | One-tail area | Two-tail area | Corresponding t (df = 25) |
|---|---|---|---|
| 0.025 | 0.025 | 0.050 | 2.060 |
| 0.010 | 0.010 | 0.020 | 2.485 |
| 0.005 | 0.005 | 0.010 | 2.787 |

Our $t_{\text{obs}} = 2.500$ sits *just above* 2.485, so:

- One-tail p is *just under* 0.010 — call it **≈ 0.009**
- Two-tail p is *just under* 0.020 — call it **≈ 0.018**

**Step 3 — Decision.**

$$p \approx 0.018 \;<\; \alpha = 0.05 \;\; \Longrightarrow \;\; \textbf{Reject } H_0$$

**Step 4 — Interpretation.** "The size-factor coefficient is statistically significant at the 5% level (p ≈ 0.018). The probability of observing a t-stat this extreme, *if the true coefficient were zero*, is only about 1.8%."

> [!tip] Exam Shortcut
> On the exam, you don't need exact p-values. Bracket the t-stat between two t-table values and state "p is between X% and Y%." That's sufficient to make any $\alpha = 0.01, 0.05, 0.10$ decision.

---

## 8. The Confidence Interval Link

P-values and [[Confidence Interval|confidence intervals]] are algebraic twins. For any $\alpha$:

> If $p < \alpha$, then $B_0$ (the hypothesized value) lies **outside** the $(1 - \alpha)$ confidence interval.
> If $p \ge \alpha$, then $B_0$ lies **inside** the $(1 - \alpha)$ confidence interval.

**Why this matters.** You can answer a hypothesis test by checking whether the CI includes the hypothesized value — no separate p-value calculation needed. A 95% CI that excludes zero *is* a 5%-level rejection of $H_0: \beta = 0$.

---

## 9. Warnings and Pitfalls

### 9.1 P-Hacking (Data Snooping)

Run 100 independent tests with $\alpha = 0.05$. *Even if every null is true*, you expect 5 "significant" findings by pure chance. Analysts who silently run many models and report only the "significant" one are **p-hacking** — producing spurious strategies that vanish out of sample.

**Defenses:**
- Pre-register the hypothesis before looking at the data
- Apply **Bonferroni correction** (divide $\alpha$ by the number of tests) for families of tests
- Validate on hold-out samples

### 9.2 Sample Size Distorts Both Ways

| Sample | Effect on p |
|---|---|
| **Huge** | Trivially small effects become "significant" — p-values approach 0 even for economically meaningless $\hat b$ |
| **Tiny** | Real effects fail to clear $\alpha$ — "failure to reject" just means you lack statistical power, not that $H_0$ is true |

### 9.3 Statistical vs. Economic Significance

A p-value of 0.0001 tells you the coefficient is *reliably* non-zero. It does **not** tell you whether the coefficient is *big enough to matter*. Always pair a p-value with the **magnitude** of $\hat b_j$ and a practical benchmark.

### 9.4 Assumption Violations Invalidate P-Values

The p-value is only correct if the test-statistic's reference distribution is accurate. That depends on the regression assumptions:

- [[Heteroskedasticity]] makes standard errors wrong → p-values wrong → fix with **White-corrected SE**
- [[Serial Correlation]] in time series makes SE too small → p-values too small → fix with **Newey-West SE**
- Non-normal residuals in small samples inflate tail probabilities

A p-value from a misspecified model is a **false precision** — it looks trustworthy and isn't.

---

## 10. P-Values in Regression Output

Every regression table you'll see has a p-value per coefficient. Here's how to read one:

| Variable | Coefficient $\hat b_j$ | Std. Error $s_{\hat b_j}$ | t-stat | **P-value** |
|---|---:|---:|---:|---:|
| Intercept | 4.7022 | 0.5821 | 8.08 | < 0.001 |
| CAPEX | 1.2302 | 0.1056 | 11.65 | < 0.001 |
| ADV | −0.0371 | 0.1062 | −0.35 | 0.7296 |
| R&D | 0.1029 | 0.0444 | 2.32 | 0.0302 |

**Reading at a glance:**

- **CAPEX** — p < 0.001 → highly significant. Real driver of the dependent variable.
- **ADV** — p = 0.7296 → not close to any threshold. Advertising carries no explanatory signal here.
- **R&D** — p = 0.0302 → significant at 5% but not at 1%. Include it if your cutoff is $\alpha = 0.05$.

> [!tip] The Scan Pattern
> Jump straight to the **P-value column**. Anything < 0.05 is earning its seat in the model (at the 5% standard). Anything > 0.10 is deadweight — a candidate for removal when chasing parsimony (confirm with adjusted $R^2$ and AIC/BIC).

---

## 11. Quick-Reference Cheat Sheet

| Concept | Formula / Rule |
|---|---|
| Definition | $p = P(\lvert T\rvert \ge \lvert t_{\text{obs}}\rvert \mid H_0)$ |
| Two-tail p (from t-stat) | $2 \times P(T > \lvert t_{\text{obs}}\rvert)$ |
| One-tail p | $P(T > t_{\text{obs}})$ (or left-tail analog) |
| F-test p | $P(F > F_{\text{obs}})$, right-tail only |
| Decision rule | Reject $H_0$ iff $p < \alpha$ |
| CI link | $p < \alpha \Leftrightarrow B_0 \notin$ $(1{-}\alpha)$ CI |
| Exam thresholds | 0.01 → highly sig · 0.05 → sig · 0.10 → weakly sig |

### Three-Bullet Anti-Misinterpretation Drill

> [!warning] Say This Three Times Before the Exam
> 1. A p-value is $P(\text{data} \mid H_0)$, **not** $P(H_0 \mid \text{data})$.
> 2. "p > 0.05" means *insufficient evidence*, **not** "the null is true."
> 3. A small p-value means *reliable*, **not** *important* — always also check effect size.

---

## 12. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Define** a p-value in precise conditional-probability terms.
- [x] **Identify** and **reject** the common misinterpretations (it is not $P(H_0)$, not the Type I error rate, not effect size).
- [x] **Compute** a p-value from a t-statistic and df using a t-table (bracket method).
- [x] **Distinguish** one-tailed from two-tailed p-values and their numerical relationship.
- [x] **Apply** the $p < \alpha$ decision rule and demonstrate its equivalence to the critical-value approach.
- [x] **Interpret** the conventional thresholds (0.01 / 0.05 / 0.10) and the significance language paired with each.
- [x] **Link** p-values to confidence intervals — any $H_0: \beta = B_0$ with $p < \alpha$ has $B_0$ outside the $(1-\alpha)$ CI.
- [x] **Diagnose** p-hacking, sample-size distortions, and statistical-vs-economic-significance traps.
- [x] **Read** a regression output's p-value column and decide which coefficients are significant at a stated $\alpha$.
- [x] **Explain** why heteroskedasticity or serial correlation can invalidate reported p-values, and how robust standard errors fix them.

---

## Related Notes

- [[Hypothesis Testing in Regression]] — the parent workflow where p-values live
- [[F-Test vs t-Test]] · [[F Distribution and F Tests]] — the reference distributions
- [[R-Squared and Adjusted R-Squared]] — goodness-of-fit, complement to p-value
- [[Confidence Interval]] — the CI↔p-value algebraic twin
- [[Type I and Type II Errors]] · [[Statistical Power]]
- [[Heteroskedasticity]] · [[Serial Correlation]] · [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] — assumption threats to valid p-values
- [[White-Corrected Standard Errors]] · [[Newey-West Standard Errors]] — robust remedies
- [[Multiple Regression - Basics and Assumptions]] — upstream regression setup
