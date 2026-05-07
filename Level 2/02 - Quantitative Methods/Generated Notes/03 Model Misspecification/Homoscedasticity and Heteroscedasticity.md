---
title: Homoscedasticity and Heteroscedasticity
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics]
aliases: [Homoskedasticity, Heteroskedasticity, Constant Variance Assumption, Conditional Heteroskedasticity, Breusch-Pagan Test]
---

# Homoscedasticity and Heteroscedasticity

## One-Minute Version

[[Homoskedasticity]] means a regression's errors have the **same variance** across observations:

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma^2$$

[[Heteroskedasticity]] means the errors have **different variance** across observations:

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma_i^2$$

The CFA-relevant danger is **[[Conditional heteroskedasticity]]**, where the size of the error variance is related to the independent variables. It usually does **not** bias the regression coefficients, because the errors can still be centered around zero. But it makes the **standard errors wrong**, which makes [[t-statistic|t-stats]], [[F-statistic|F-tests]], [[P-Value|p-values]], and [[Confidence interval|confidence intervals]] unreliable.

The exam memory line is:

> [!tip] One-Line Rule
> Heteroskedasticity usually leaves the regression line alone but lies about how confident you should be in that line.

---

## LOS Coverage

| CFA task | What you must be able to do |
|---|---|
| Explain the types of heteroskedasticity | Distinguish [[Unconditional heteroskedasticity]] from [[Conditional heteroskedasticity]] |
| Explain the effect on inference | Know that coefficients are usually unbiased, but standard errors and test statistics are unreliable |
| Detect heteroskedasticity | Interpret fan-shaped residual plots and the [[Breusch–Pagan test]] |
| Correct heteroskedasticity | Use [[White-corrected standard errors]] / [[Robust standard errors]] |

---

## The Real-World Analogy First

Imagine you're an archer shooting at targets at different distances. At 10 meters, your arrows cluster tightly around the bullseye — you're off by an inch here, two inches there, but the **spread** is small and consistent. Now back up to 100 meters. Your average aim is still pointed at the bullseye, but the arrows spray out in a much wider cloud — sometimes close, sometimes wildly off.

If your shot-to-shot scatter is the **same size** regardless of distance, your shooting is **homoscedastic** ("same spread"). If the scatter **grows** as you back up, it's **heteroscedastic** ("different spread").

Now swap "distance" for an independent variable like company size, and "arrow scatter" for regression residuals. If your model predicts small-cap returns tightly but sprays wildly on large-caps, you've got heteroscedasticity. The model's *accuracy* (average aim) may be fine — but its *precision* depends on where you're aiming, and that breaks one of OLS's core assumptions.

---

## The Definitions

**Homoscedasticity** means the variance of the residuals is **constant** across all observations:

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma^2 \quad \text{for all } i$$

Every error term draws from the same-sized noise distribution, regardless of where you are in $X$-space. This is one of the **Gauss-Markov assumptions** that makes OLS the Best Linear Unbiased Estimator (BLUE).

**Heteroscedasticity** is the violation: residual variance *changes* across observations.

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma_i^2 \quad \text{(varies with } i \text{)}$$

The notation matters. The subscript in $\sigma_i^2$ is the warning light. It says each observation can have its own noise level. OLS can still draw a line through the middle of the data, but the usual uncertainty formula was built for one shared variance, not a different variance for every observation.

```
Homoscedastic residuals:           Heteroscedastic residuals:

 |  . . . . . . . . . .              |       . .   .   .
 | . . . . . . . . . . .             |    .  .  . . . . . .
─┼─────────────────────► X          ─┼─────────────────────► X
 | . . . . . . . . . . .             |  . . . .  . . . . . .
 |  . . . . . . . . . .              |       . .   .   .
                                             (fan / wedge shape)
```

The fan/wedge pattern is the classic visual tell.

---

## The Deep Why: What Exactly Breaks?

OLS does two separate jobs:

1. It estimates the coefficients: $\hat{b}_0, \hat{b}_1, \ldots, \hat{b}_k$.
2. It estimates how uncertain those coefficients are: $SE(\hat{b}_0), SE(\hat{b}_1), \ldots, SE(\hat{b}_k)$.

Heteroscedasticity mostly attacks the second job.

### Why the coefficients can still be unbiased

The condition that protects unbiased coefficients is:

$$E(\varepsilon_i \mid X_i) = 0$$

That says: after you condition on the independent variables, the average error is zero. The model may be more precise for some observations and less precise for others, but the errors are not systematically above or below the regression line.

Think about the income-spending example. High-income households may have much more variable spending. Some spend far above the model's prediction, others far below it. But if those high-income errors still average to zero, the slope can still be centered correctly. The cloud is wider, not necessarily shifted upward or downward.

So heteroscedasticity does **not** automatically mean:

```text
The line is in the wrong place.
```

It means:

```text
The model is misreporting how precise the line is.
```

### Why the standard errors break

In simple regression, the usual slope variance formula has this structure:

$$\text{Var}(\hat{b}_1) = \frac{\sigma^2}{\sum (X_i - \bar{X})^2}$$

The numerator is one common $\sigma^2$. That formula assumes every observation is drawn from the same-sized error distribution.

But under heteroscedasticity, the true setup is closer to:

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma_i^2$$

There is no single shared noise level. Some observations are quiet; others are loud. If OLS pretends they all came from the same noise bucket, its standard errors are no longer honest.

That is the deepest mechanism. The coefficient can still be centered correctly because errors average to zero, but the uncertainty around that coefficient is measured with a formula that assumes constant variance. Once uncertainty is wrong, every inference statistic built on uncertainty becomes suspect:

```text
Wrong SE
  |
  v
Wrong t-stat
  |
  v
Wrong p-value
  |
  v
Wrong confidence interval
  |
  v
False confidence in a relationship
```

---

## Two Flavors: Unconditional vs. Conditional — The Full Story

Heteroscedasticity comes in two species, and the distinction is the single most important thing to internalize in this section. Both mean "residual variance isn't constant," but only one actually breaks your regression. CFA exam writers love this distinction because candidates who skim the definition will confuse them on exam day.

### The Mathematical Difference in One Line

**Unconditional:**

$$\text{Var}(\varepsilon_i) = \sigma_i^2, \quad \text{but } \text{Cov}(\sigma_i^2,\, X_i) = 0$$

The variance wobbles across observations — but *not* in any pattern tied to the regressors.

**Conditional:**

$$\text{Var}(\varepsilon_i \mid X_i) = \sigma_i^2 = f(X_i)$$

The variance is a **function of** $X$. Give me the value of the regressor, and I can predict roughly how big your residual will be.

That single difference — *is the variance pattern correlated with X or not* — is the whole game.

---

### Unconditional Heteroscedasticity — the Harmless Cousin

**Real-world analogy — "Market Mood Swings":** You're regressing tech-stock returns on R&D spending. During a 2020-style global crisis, the entire market's volatility spikes for everybody — small firms, big firms, heavy R&D spenders, penny-pinchers — all of their residuals get larger in that window. When the crisis passes, residuals calm down again, uniformly.

The variance of your errors really did change over time. But it changed because of a *market-wide shock*, not because of anything in your regressor. A company's R&D spend didn't cause the 2020 volatility; the virus did. The wobble was there; your $X$ didn't create it.

**Concrete example:** Suppose you have 10 years of data on 100 companies, and in Year 5 a geopolitical event makes *every* stock's residuals balloon — high-R&D firms and low-R&D firms alike. If you plotted $\hat{\varepsilon}_i^2$ against R&D spend, you'd see a random cloud. If you plotted residual variance against *year*, you'd see a Year-5 bulge. The variance is non-constant in time, but **not conditional on $X$**.

**Effect on OLS:**

| Quantity | Effect |
|---|---|
| Coefficients ($\hat{b}_j$) | Unbiased and consistent |
| Standard errors | Mostly OK — no systematic bias |
| t-stats, F-stats, p-values | Reasonably reliable |
| Overall inference | **Generally fine to proceed as-is** |

Unconditional heteroscedasticity is a *technical* violation of OLS's assumptions, but it doesn't poison statistical inference in practice. You can leave it alone.

---

### Conditional Heteroscedasticity — the Villain

**Real-world analogy — "The Income-Spending Fan":** You're predicting household spending from household income. People earning $20k/yr have very little flexibility — they spend on rent and groceries, and the model predicts them well. Residuals stay tight. People earning $2M/yr have enormous variety: some are penny-pinchers who keep their old Honda; others buy yachts. The same $X$ (income) produces a massive range of $Y$ (spending). Your residuals **fan out** as income rises.

The residual variance is now a **function of the regressor**: $\text{Var}(\varepsilon_i) = f(\text{income}_i)$. Given a value of $X$, you can predict how spread out the residual will be. This is the defining feature.

**Concrete example:** Regress monthly stock return on market beta across a panel of stocks. Low-beta stocks (utilities, consumer staples) have tight residuals — the model nails them. High-beta stocks (early-stage biotech, crypto-adjacent names) have enormous residuals. The squared residuals $\hat{\varepsilon}_i^2$ are strongly *positively correlated* with $\beta_i$. That's conditional heteroscedasticity.

**Effect on OLS:**

| Quantity | Effect |
|---|---|
| Coefficients ($\hat{b}_j$) | Still unbiased and consistent |
| Standard errors | **Biased — typically downward** (too small) |
| t-stats | **Inflated** (because $t = \hat{b}/SE$ with SE too small) |
| F-stat | Unreliable |
| p-values | Too small — Type I errors explode |
| Confidence intervals | Too narrow — false precision |

This is why it's the villain. The *predictions* from your model are fine — the coefficients aren't systematically wrong. But the "report card" attached to the predictions (t-stats, p-values, confidence intervals) is a **lie**. You'll see $X_2$ at $t = 4.5$ with $p = 0.0000$ and trade on it, when the honest t-stat is $2.1$ and the relationship is borderline at best.

---

### Why the Exam Only Cares About Conditional

On the CFA exam, *heteroscedasticity* — used unqualified — almost always means **conditional** heteroscedasticity. The logic:

1. Unconditional hetero is technically a violation, but inference still works — no action required, nothing to test.
2. Conditional hetero silently corrupts t-stats → fake "significant" alpha → bad portfolio decisions → direct relevance to the analyst's job.

That direct line — *bad test statistic → bad investment decision* — is why the curriculum and the exam focus on conditional.

---

### How the Breusch-Pagan Test Distinguishes Them

Here's the elegant part: the [[Breusch–Pagan Test]] is designed specifically to pick out the **conditional** flavor and ignore the unconditional one. The mechanics force this result:

1. Original regression → save residuals $\hat{u}_i$.
2. Square them: $\hat{u}_i^2$ is your observable proxy for **local variance**.
3. Regress $\hat{u}_i^2$ **on the original $X$'s**.
4. Test statistic: $BP = n \cdot R^2_{\text{aux}} \sim \chi^2_k$.

Now think about what that auxiliary regression is asking: *can my $X$'s predict the size of the squared residuals?*

- If the heteroscedasticity is **unconditional**, squared residuals wobble across observations but have **no relationship with $X$** → auxiliary $R^2$ is near zero → $BP$ is small → fail to reject → test correctly says "no dangerous heteroscedasticity."
- If the heteroscedasticity is **conditional**, squared residuals are systematically tied to $X$ → auxiliary $R^2$ is high → $BP$ is large → reject → test correctly flags the problem.

The auxiliary regression's $R^2$ is essentially a direct measurement of "how conditional is the wobble." That's why BP tests *conditional* heteroscedasticity by design, not just "any non-constant variance."

---

### Is Unconditional Heteroscedasticity Ever Worth Correcting?

Generally **no**. Three reasons:

1. **Inference still works** — t-stats, F-stats, and p-values are not systematically corrupted.
2. **Correcting it introduces risk** — applying White SEs or GLS to a model that doesn't need it adds noise and can make results *worse* if the "fix" assumes a structure that isn't there.
3. **The BP test will tell you** — if BP fails to reject, you don't need to do anything. If BP rejects, the problem is conditional, and White SEs are the fix.

**The practical flowchart:**

```
         Residual plot shows non-constant scatter
                         │
                         ▼
                Run Breusch-Pagan test
                         │
             ┌───────────┴────────────┐
             ▼                        ▼
       BP large → reject          BP small → fail to reject
             │                        │
             ▼                        ▼
    Conditional hetero         Unconditional hetero (or none)
             │                        │
             ▼                        ▼
    APPLY White (robust) SEs       Do nothing — inference OK
```

---

### Side-by-Side Summary

| Feature | Unconditional | Conditional |
|---|---|---|
| Variance related to $X$? | **No** | **Yes** |
| Coefficients biased? | No | No |
| Standard errors biased? | No (practically) | **Yes — usually downward** |
| t-stats / F-stats / p-values | Reliable | **Inflated → Type I errors** |
| BP test result | Small $BP$ → fail to reject | Large $BP$ → reject |
| Needs correcting? | No | **Yes — White / robust SEs** |
| CFA exam weight | Defined, but rarely the "answer" | The entire focus of the section |

---

## Consequences: Why It's Dangerous

Heteroscedasticity is a close cousin of [[Serial Correlation]] — same flavor of damage, different cause.

| Component | Effect |
|---|---|
| **Coefficients** ($\hat{b}_j$) | Still **unbiased** and consistent — the "prediction line" sits in the right place |
| **Standard errors** | Typically **biased downward** (too small) |
| **t-statistics** | **Inflated** — look larger than they should |
| **F-statistic** | Unreliable |
| **p-values** | Too small → excess **Type I errors** (false positives) |
| **Confidence intervals** | Too narrow — false precision |

The practical danger: you declare variables significant when they're not, then trade on phantom signals. The coefficients are right; their *report card* is a lie.

---

## Detection

### Method 1 — Residual Plots (Eyeball Test)

Plot residuals $\hat{\varepsilon}_i$ against fitted values $\hat{Y}_i$ or against each regressor $X_j$.

- **Random cloud** → homoscedastic, no issue
- **Fan / wedge / cone shape** → heteroscedasticity (variance grows with $X$)
- **Bowtie** → variance smallest in the middle, larger at both ends

Fast, intuitive, but subjective. Formal tests are better.

### Method 2 — The Breusch-Pagan (BP) Test

The gold-standard formal test on the CFA exam.

**Procedure:**

1. Run your original regression and save the residuals $\hat{\varepsilon}_i$.
2. Square them: $\hat{\varepsilon}_i^2$.
3. Run a **second (auxiliary) regression** of $\hat{\varepsilon}_i^2$ on the original $X$ variables.
4. Record the $R^2$ from that auxiliary regression — call it $R^2_{\text{aux}}$.
5. Compute the test statistic:

$$\boxed{\text{BP} = n \cdot R^2_{\text{aux}} \ \sim \ \chi^2(k)}$$

where $n$ is the sample size and $k$ is the number of regressors in the auxiliary regression.

**Decision rule:** compare BP to the critical value from a $\chi^2$ table with $k$ degrees of freedom. If $\text{BP} > \chi^2_{\text{crit}}$, reject $H_0$: homoscedasticity → you have conditional heteroscedasticity.

**Hypotheses:**
- $H_0$: homoscedasticity (residual variance unrelated to $X$'s)
- $H_a$: conditional heteroscedasticity present

The BP test is **one-tailed right** (like all $\chi^2$ and F tests): a large BP statistic means the $X$'s *do* explain residual size, which is exactly the problem.

---

## When You See This, Do This

| If the question gives you... | Think... | Do this... |
|---|---|---|
| A residual plot with a fan, cone, or wedge | Error variance changes with fitted values or $X$ | Suspect [[Heteroskedasticity]] |
| Residual variance tied to the independent variables | [[Conditional heteroskedasticity]] | Ordinary OLS standard errors are unreliable |
| A large [[Breusch–Pagan test]] statistic | Squared residuals are explained by $X$ | Reject homoskedasticity |
| A small BP p-value | Evidence against $H_0$ | Conclude conditional heteroskedasticity is present |
| Heteroskedasticity is detected | Inference problem, not usually coefficient bias | Use [[White-corrected standard errors]] |
| The question asks whether $\hat{b}_j$ is biased | Check whether $E(\varepsilon_i \mid X_i)=0$ is violated | Heteroskedasticity alone usually does **not** bias coefficients |

---

## Worked Numerical Example

**Scenario:** You're predicting stock returns ($Y$) from advertising spend ($X$) for $n = 100$ companies.

**Step 1 — Fit the model.** OLS regression gives $R^2 = 0.88$. Looks great.

**Step 2 — Plot residuals.** Errors are tiny for small advertisers ($1M spend), but fan out to huge misses for giant advertisers ($100M spend). Classic wedge.

**Step 3 — Run Breusch-Pagan.**

- Square residuals.
- Regress $\hat{\varepsilon}_i^2$ on ad spend.
- Auxiliary regression returns $R^2_{\text{aux}} = 0.10$.

**Step 4 — Test statistic:**

$$\text{BP} = n \cdot R^2_{\text{aux}} = 100 \times 0.10 = 10.0$$

**Step 5 — Compare to critical value.** With $k = 1$ regressor in the auxiliary regression, at $\alpha = 0.05$: $\chi^2_{\text{crit}} = 3.84$.

Since $10.0 > 3.84$, **reject $H_0$**. Conditional heteroscedasticity confirmed.

**Step 6 — Fix.** Re-estimate with White standard errors. Originally, ad spend had a t-stat of 4.5. After White correction, the t-stat drops to 2.1. Ad spend is still significant, but much less spectacularly than OLS pretended.

---

## Worked Example — Exam-Speed Version

You run a regression with $n = 80$. The auxiliary Breusch-Pagan regression of squared residuals on the three independent variables has $R^2_{\text{aux}} = 0.12$. The 5% critical value for $\chi^2_3$ is 7.815.

Compute:

$$BP = nR^2_{\text{aux}} = 80(0.12) = 9.60$$

Compare:

$$9.60 > 7.815$$

Decision: reject $H_0$ of homoskedasticity. Conditional heteroskedasticity is present.

Exam implication: do **not** trust the reported OLS standard errors, t-stats, p-values, or confidence intervals. Use [[White-corrected standard errors]].

---

## Remedies

| Remedy | How It Works | When to Use |
|---|---|---|
| **White (robust) standard errors** | Recalculates SEs using a formula that doesn't assume constant variance. Coefficients unchanged, SEs typically rise, t-stats shrink | The default CFA fix — works without changing the model |
| **Generalized Least Squares (GLS)** | Transforms the data so variance becomes constant in the transformed scale. More efficient than White if you know the variance structure | When you have a specific model for how variance scales with $X$ |
| **Weighted Least Squares (WLS)** | A special case of GLS — down-weights high-variance observations | When variance is proportional to a known quantity (e.g., firm size) |
| **Transform $Y$** | Take logs or square roots — often stabilizes variance | When variance grows with the *level* of $Y$ |

**White standard errors** are the go-to answer on exams. They produce **heteroscedasticity-consistent (HC) standard errors** — same coefficients, honest uncertainty.

---

## Heteroscedasticity vs. Its Siblings

| Problem | What's Wrong | Coefficients? | Standard Errors? | Primary Fix |
|---|---|---|---|---|
| **Heteroscedasticity** | Residual variance not constant | Unbiased | Biased (usually **too small**) | White (robust) SEs |
| **[[Serial Correlation]]** | Residuals correlated across time | Unbiased* | **Too small** (deflated) | Newey-West HAC SEs |
| **[[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]** | $X$'s correlated with each other | Unbiased but imprecise | **Too large** (inflated) | Drop/combine variables |

\* Except in autoregressive models.

**Key distinction:** serial correlation and heteroscedasticity both *deflate* SEs (inflate t-stats → false positives). Multicollinearity *inflates* SEs (deflates t-stats → false negatives). Newey-West handles both heteroscedasticity *and* serial correlation; White handles only heteroscedasticity.

---

## Common Wrong Reasoning

### Wrong Reasoning 1 — "Heteroskedasticity biases the slope."

Why it feels right: heteroskedasticity is an OLS assumption violation, and "assumption violation" sounds like the model must be wrong.

Why it fails: the slope is protected by the zero conditional mean assumption:

$$E(\varepsilon_i \mid X_i)=0$$

If the errors still average to zero at each value of $X$, the line can remain centered correctly even if the residual spread changes. Heteroskedasticity changes the **variance** of the errors, not necessarily their **expected value**.

Exam correction: heteroskedasticity usually breaks **inference**, not **estimation**.

### Wrong Reasoning 2 — "A high $R^2$ means heteroskedasticity is not a problem."

Why it feels right: if the regression explains a lot of $Y$, it feels like the model must be statistically reliable.

Why it fails: the main regression $R^2$ measures fit, not whether residual variance is constant. A model can fit the average relationship well and still have residuals that fan out. In fact, heteroskedasticity often appears in useful models because some parts of the data are naturally harder to predict than others.

Exam correction: judge heteroskedasticity from residual plots or the BP test, not from the main model's $R^2$.

### Wrong Reasoning 3 — "White standard errors fix the coefficients."

Why it feels right: the word "correction" sounds like the regression coefficients are being repaired.

Why it fails: White standard errors leave $\hat{b}_j$ unchanged. They repair the standard errors, which then repair the t-stats, p-values, and confidence intervals.

Exam correction:

```text
White changes the report card, not the fitted line.
```

---

## Memory Hooks

- **"Homo" = same, "hetero" = different** — same spread vs. different spread
- **Fan shape** = heteroscedasticity's fingerprint on a residual plot
- **Conditional = dangerous, unconditional = harmless** — only the $X$-linked kind breaks inference
- **$BP = n \cdot R^2_{\text{aux}} \sim \chi^2(k)$** — "n-R-squared" is the test statistic
- **White headphones** — White standard errors: same signal (coefficients), honest volume (SEs)
- **Coefficients fine, SEs lying** — the damage is on the report card, not the predictions
- **Mirror of multicollinearity** — heteroscedasticity shrinks SEs, multicollinearity blows them up

---

## CFA Exam Focus

1. **Definition**: constant residual variance is an OLS assumption; heteroscedasticity violates it
2. **Only conditional heteroscedasticity matters** — unconditional doesn't hurt inference
3. **Consequences**: coefficients unbiased, SEs underestimated → inflated t-stats → Type I errors
4. **Detection**: residual plot (fan shape) + Breusch-Pagan test with $n \cdot R^2 \sim \chi^2(k)$
5. **Fix**: White (robust) standard errors — the default answer
6. **Know the sibling comparison**: heteroscedasticity vs. serial correlation vs. multicollinearity — which inflates vs. deflates SEs

---

## Minimum Memorization

1. Homoskedasticity:

$$\text{Var}(\varepsilon_i \mid X_i)=\sigma^2$$

2. Heteroskedasticity:

$$\text{Var}(\varepsilon_i \mid X_i)=\sigma_i^2$$

3. Conditional heteroskedasticity means error variance is related to $X$.

4. Coefficients are usually unbiased and consistent.

5. Standard errors are biased, often too small, so t-stats can be inflated.

6. Detection: residual plot or [[Breusch–Pagan test]].

7. Fix: [[White-corrected standard errors]] / [[Robust standard errors]].

---

## Can I Solve This?

- [ ] I can tell homoskedasticity from heteroskedasticity on a residual plot.
- [ ] I can distinguish unconditional from conditional heteroskedasticity.
- [ ] I can explain why heteroskedasticity usually does not bias coefficients.
- [ ] I can explain why it does bias standard errors.
- [ ] I can compute $BP = nR^2_{\text{aux}}$.
- [ ] I can compare BP to a $\chi^2_k$ critical value.
- [ ] I can name the correct fix: White / robust standard errors.
- [ ] I can avoid confusing heteroskedasticity with [[Serial Correlation]] or [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]].

## Related Notes

[[Serial Correlation]] · [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] · [[Ordinary Least Squares]] · [[Regression Assumptions]] · [[Breusch-Pagan Test]] · [[White Standard Errors]] · [[Generalized Least Squares]] · [[Chi-Square Distribution]] · [[F-Test vs t-Test]] · [[F Distribution and F Tests]]

---