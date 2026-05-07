---
title: Variance Inflation Factor (VIF)
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics, multicollinearity]
aliases: [VIF, Variance Inflation Factor, Tolerance, 1/(1-R²) rule, Collinearity Diagnostic]
---

# Variance Inflation Factor (VIF)

## The Real-World Analogy First

Imagine you're on a hiring panel trying to decide which of three finalists contributed most to a group project. You interview two teammates and each one praises all three finalists interchangeably — "they were all great, they all worked on everything." You **know** the project succeeded, but you can't tell who drove which piece. Your uncertainty about any one finalist's contribution is huge, not because they did nothing, but because their contributions were tangled together.

Now swap "finalists" for regression variables. If your model uses **GDP growth**, **industrial production**, and **capacity utilization** — three macro cousins that essentially move together — the regression knows the macro cycle matters, but can't cleanly attribute the effect to any one of them. Each coefficient's standard error balloons because the information each variable carries is mostly redundant with the others.

**VIF is a single number per regressor that tells you exactly how badly that tangling has inflated the uncertainty around that regressor's coefficient.** A VIF of 10 means the variance of that slope estimate is **ten times larger** than it would be if the variable were cleanly independent of its neighbors.

**Memory hook:** *VIF = "Variance Inflated by Friends"* — how much your teammates are puffing up your standard error.

---

## One-Line Definition

The **Variance Inflation Factor** for an independent variable $X_j$ is:

$$\boxed{\,\text{VIF}_j = \frac{1}{1 - R_j^2}\,}$$

where $R_j^2$ is the R-squared from an **auxiliary regression** of $X_j$ on all the other independent variables in the model. It quantifies the degree to which [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity|multicollinearity]] has inflated the variance (and thus the standard error) of $\hat{b}_j$.

---

## The LOS This Note Fulfills

After reading this note you should be able to:

- **Define** the Variance Inflation Factor and the auxiliary regression behind it.
- **Calculate** VIF from an auxiliary regression's $R_j^2$.
- **Interpret** VIF values against the standard 1 / 5 / 10 thresholds.
- **Explain** how a high VIF inflates standard errors and deflates t-statistics.
- **Compare** VIF to a pairwise correlation matrix as a multicollinearity diagnostic.
- **Describe** corrective actions (drop, combine, increase $n$, regularize).
- **Identify** what VIF does *not* tell you (it does not bias coefficients, it does not pick which variable to drop).

---

## Derivation: Where the Formula Comes From

The formula isn't pulled from thin air — it drops directly out of the OLS variance formula. Writing the variance of a single slope coefficient in a multiple regression:

$$\text{Var}(\hat{b}_j) = \frac{\sigma^2}{(n-1) \cdot s_{X_j}^2 \cdot (1 - R_j^2)}$$

Break it down term by term:

| Symbol | Meaning | Effect on Var |
|---|---|---|
| $\sigma^2$ | True error variance of the regression | Bigger noise → bigger variance |
| $n - 1$ | Sample size (minus one) | More data → smaller variance |
| $s_{X_j}^2$ | Sample variance of $X_j$ itself | More spread in $X_j$ → smaller variance |
| $1 - R_j^2$ | "Unique" information in $X_j$ (tolerance) | Less unique info → variance **explodes** |

The last factor, $1 - R_j^2$, is the one multicollinearity attacks. Split the variance formula into two pieces:

$$\text{Var}(\hat{b}_j) = \underbrace{\frac{\sigma^2}{(n-1) \cdot s_{X_j}^2}}_{\text{baseline (no collinearity)}} \times \underbrace{\frac{1}{1 - R_j^2}}_{\text{inflation factor}}$$

The second factor **is** the VIF. It's literally the multiplicative penalty that multicollinearity imposes on the variance of $\hat{b}_j$ compared to the hypothetical case where $X_j$ was orthogonal to (uncorrelated with) all other regressors.

$$\boxed{\,\text{Var}(\hat{b}_j) = \text{Var}_{\text{ideal}}(\hat{b}_j) \times \text{VIF}_j\,}$$

So when you read "VIF = 10," the literal, precise statement is: **the variance of this slope estimate is 10 times larger than it would be if this regressor were uncorrelated with the others.** The standard error — the square root — is $\sqrt{10} \approx 3.16$ times larger.

---

## The Auxiliary Regression, Step by Step

The $R_j^2$ inside the VIF formula is **not** the $R^2$ of your main regression. It's from a side calculation.

### Step 1 — Pick the regressor you're evaluating

Say you have a model:

$$Y = b_0 + b_1 X_1 + b_2 X_2 + b_3 X_3 + \varepsilon$$

You want $\text{VIF}_2$.

### Step 2 — Run an auxiliary regression

**Ignore $Y$ entirely.** Instead, regress $X_2$ on all the *other* regressors:

$$X_2 = c_0 + c_1 X_1 + c_3 X_3 + w$$

### Step 3 — Extract $R_j^2$

The $R^2$ from this auxiliary regression is $R_2^2$ — the proportion of the variation in $X_2$ that the other regressors can already explain.

### Step 4 — Plug in

$$\text{VIF}_2 = \frac{1}{1 - R_2^2}$$

**Repeat for every regressor** ($X_1$, $X_3$, …) to get a VIF for each. Software reports them as a column.

### Intuition for the auxiliary regression

- $R_j^2 \approx 0$: $X_j$ is essentially uncorrelated with the other regressors → it brings genuinely new information → $\text{VIF}_j \approx 1$.
- $R_j^2 \approx 1$: $X_j$ is almost perfectly predictable from the others → it's a "duplicate" → $\text{VIF}_j \to \infty$.

```
R_j² = 0.0  →  VIF = 1/1.00  =  1.00     ◄── ideal
R_j² = 0.50 →  VIF = 1/0.50  =  2.00
R_j² = 0.80 →  VIF = 1/0.20  =  5.00     ◄── WARNING threshold
R_j² = 0.90 →  VIF = 1/0.10  =  10.0     ◄── SERIOUS threshold
R_j² = 0.95 →  VIF = 1/0.05  =  20.0
R_j² = 0.99 →  VIF = 1/0.01  =  100
R_j² = 1.00 →  VIF = 1/0.00  =  ∞        ◄── perfect collinearity
```

---

## VIF and Tolerance: Two Sides of the Same Coin

**Tolerance** is simply the denominator of VIF:

$$\text{Tolerance}_j = 1 - R_j^2 = \frac{1}{\text{VIF}_j}$$

Tolerance answers: *"What fraction of $X_j$'s variation is unique — not already explained by the other regressors?"*

| Quantity | Formula | Direction of alarm | Alarm threshold |
|---|---|---|---|
| **Tolerance** | $1 - R_j^2$ | Small values are bad | < 0.20 warning, < 0.10 serious |
| **VIF** | $1 / (1 - R_j^2)$ | Large values are bad | > 5 warning, > 10 serious |

They are exact reciprocals. Output from statistical packages often reports both. Either alone is sufficient.

---

## The Rule-of-Thumb Thresholds

| $\text{VIF}_j$ | $R_j^2$ | Interpretation | Action |
|---|---|---|---|
| **1** | 0 | No correlation with other regressors — ideal | None |
| **1 – 5** | 0 – 0.80 | Mild, acceptable collinearity | None |
| **> 5** | > 0.80 | Warning — investigate further | Consider action |
| **> 10** | > 0.90 | **Serious** multicollinearity | **Must correct** |

These thresholds are conventions, not derived from a distribution. They are widely used by CFA curriculum and in practice. The cutoff VIF > 10 corresponds exactly to $R_j^2 > 0.90$, which is a very tight linear relationship among regressors.

---

## The Mechanical Chain: VIF → SE → t-stat → Significance

Here is the step-by-step damage path when VIF is elevated:

```
            ┌────────────────────────────────┐
            │   High correlation among X's   │
            └────────────────────────────────┘
                          │
                          ▼
               R_j² in auxiliary regression
                          │
                          ▼
                 VIF_j = 1 / (1 - R_j²)
                          │
                          ▼
      Var(b_hat_j) = baseline × VIF_j  ← inflated
                          │
                          ▼
             SE(b_hat_j) = baseline × √VIF_j
                          │
                          ▼
      t-stat = b_hat_j / SE(b_hat_j)  ← deflated
                          │
                          ▼
         p-value too large → fail to reject H₀
                          │
                          ▼
     "Insignificance Paradox":  b is real but
     looks statistically insignificant
```

**Key consequence:** the coefficient estimate itself is still **unbiased and consistent**. You are not getting a "wrong answer." You are getting the *right answer with too much uncertainty attached* — so wide that you can't reject the null when you should.

---

## Worked Numerical Example

An analyst studies **Return on Assets (ROA)** explained by three corporate-spending intensities:

$$\text{ROA}_i = b_0 + b_1 \cdot \text{CAPEX}_i + b_2 \cdot \text{ADV}_i + b_3 \cdot \text{R\&D}_i + \varepsilon_i$$

### Auxiliary regressions

The software runs three auxiliary regressions and reports:

| Regressor | Auxiliary $R_j^2$ | Tolerance ($1 - R_j^2$) | $\text{VIF}_j$ |
|---|---|---|---|
| CAPEX | 0.141 | 0.859 | $1 / 0.859 = \mathbf{1.164}$ |
| ADV | 0.220 | 0.780 | $1 / 0.780 = 1.282$ |
| R&D | 0.185 | 0.815 | $1 / 0.815 = 1.227$ |

**Verification for CAPEX:**
$$\text{VIF}_{\text{CAPEX}} = \frac{1}{1 - 0.141} = \frac{1}{0.859} \approx 1.164$$

### Interpretation

All three VIFs are well below 5 → multicollinearity is **not a problem** here. The three spending categories move somewhat together (as one would expect — big firms spend more on everything), but not enough to compromise inference. Each variable contributes substantial unique information.

### Contrast: what a *problem* case would look like

Suppose instead the model used **GDP growth** and **Industrial Production growth**, with auxiliary $R_1^2 = 0.92$:

$$\text{VIF}_{\text{GDP}} = \frac{1}{1 - 0.92} = \frac{1}{0.08} = 12.5$$

VIF > 10 → serious collinearity. The standard error of $\hat{b}_{\text{GDP}}$ is $\sqrt{12.5} \approx 3.54$ times larger than it would be in a clean model. If reported SE is 2.1, the "true" (deflated) SE would be closer to $2.1 / 3.54 \approx 0.59$ — converting an insignificant $t = 0.86$ into a highly significant $t \approx 3.05$.

---

## VIF vs. Pairwise Correlation Matrix

The cheapest multicollinearity diagnostic is a correlation table showing $\text{corr}(X_i, X_j)$ for every pair. It's fast and visual. But it has a **critical blind spot**: it only sees pairs.

Consider three regressors satisfying approximately:

$$X_3 \approx X_1 + X_2$$

Each pairwise correlation — $\text{corr}(X_1, X_2)$, $\text{corr}(X_1, X_3)$, $\text{corr}(X_2, X_3)$ — could be modest (say 0.5 each), not tripping any alarm. Yet the *combined* linear dependence is severe: the auxiliary regression of $X_3$ on $X_1$ and $X_2$ will yield $R_3^2 \approx 1$, producing an enormous $\text{VIF}_3$.

| Diagnostic | Detects pairwise collinearity? | Detects multi-way collinearity? | Typical threshold |
|---|---|---|---|
| **Correlation matrix** | Yes | **No** | $|r| > 0.7$ |
| **VIF** | Yes | **Yes** | VIF > 5 or 10 |

**Bottom line:** correlation matrix is a useful first glance; **VIF is the authoritative diagnostic** because it captures how each variable relates to *all* others simultaneously — via the auxiliary regression.

---

## How to Fix High VIF

If a regressor has $\text{VIF}_j > 10$, you cannot leave it alone if you want to interpret individual coefficients. Choices:

| Fix | How it works | When to use |
|---|---|---|
| **Drop a variable** | Remove the regressor with the highest VIF (or the one with weakest theoretical justification) | Simplest, most common — usually right |
| **Combine variables** | Replace correlated group with a composite (average, sum, PCA score, index) | Both variables are theoretically essential |
| **Use a proxy** | Substitute a less-correlated measure of the same concept | When a cleaner proxy is available |
| **Collect more data** | Larger $n$ shrinks every variance directly — even the inflated ones | Feasible only sometimes |
| **Ridge regression / LASSO** | Add a penalty on coefficient magnitudes to stabilize estimates in the presence of collinearity | Advanced; not in the CFA core but worth knowing |
| **Do nothing** | If the model is for *prediction only* and no one interprets coefficients, multicollinearity doesn't hurt forecasts | Pure forecasting use cases |

CFA exam preferred answers: **drop a redundant variable** or **combine correlated variables**.

---

## What VIF Does *Not* Tell You

1. **VIF does not bias your coefficients.** Multicollinearity makes slopes imprecise, not wrong. $\hat{b}_j$ remains an unbiased, consistent estimate of $b_j$.
2. **VIF does not tell you *which* variable to drop.** If $X_1$ and $X_2$ both have VIF = 12, the math cannot distinguish them. You must use **theory** (which one actually belongs in the model?) or **parsimony** (which one is harder to measure?) to decide.
3. **VIF does not detect heteroskedasticity or serial correlation.** Those are different OLS violations, each with their own tests ([[Breusch–Pagan test]] and [[Durbin-Watson Test|Durbin–Watson]]/[[Breusch-Godfrey Test|Breusch–Godfrey]] respectively).
4. **VIF does not work on categorical variables in a simple way.** Dummy variables from a single categorical feature will naturally have pairwise overlap; specialized variants (generalized VIF, GVIF) exist but are beyond the CFA scope.
5. **VIF is not a statistical test.** There's no p-value, no distribution under a null — it's a diagnostic number interpreted against conventions.

---

## VIF in Context: The Diagnostic Triangle

VIF is one corner of a three-sided toolkit for OLS assumption-checking:

| Assumption violated | Primary diagnostic | Effect on SEs | Typical fix |
|---|---|---|---|
| **Multicollinearity** | **VIF** ($1/(1-R_j^2)$) | **Inflated** | Drop/combine vars |
| **[[Heteroskedasticity]]** | [[Breusch–Pagan test]] | Biased (direction varies, often deflated) | White/robust SEs |
| **[[Serial Correlation]]** | [[Durbin-Watson Test\|Durbin–Watson]] / [[Breusch-Godfrey Test\|Breusch–Godfrey]] | **Deflated** | Newey–West SEs |

**Mnemonic for direction of the bias:**
- Multicollinearity *puffs up* standard errors (you become too timid — miss real effects).
- Serial correlation *squashes* standard errors (you become too reckless — call random effects significant).
- Heteroskedasticity can do either depending on which observations have the extra variance.

---

## Memory Hooks and Mnemonics

- **"One over one minus R squared of the side regression"** — the formula in one breath.
- **VIF = "Variance Inflated by Friends"** — teammates redundancy puffs up your SE.
- **"VIF > 10 → fix it, VIF > 5 → watch it, VIF = 1 → clean"** — the three thresholds.
- **Tolerance = 1 / VIF** — the flipped view; small tolerance = big VIF.
- **"F says yes, t says no → check VIF"** — the F/t paradox is the classic prompt to compute VIF.
- **Square root for SEs:** a VIF of 9 means standard errors are 3× too large; VIF of 100 means 10× too large. Take $\sqrt{\text{VIF}}$ for SE inflation.

---

## CFA Exam Focus

1. **Know the formula cold:** $\text{VIF}_j = 1 / (1 - R_j^2)$ where $R_j^2$ is the auxiliary regression of $X_j$ on all other regressors.
2. **Thresholds:** VIF > 5 warning; VIF > 10 serious.
3. **Symptom of a VIF problem:** high model $R^2$, significant F, but insignificant individual t-stats.
4. **Effect on coefficients:** unbiased but imprecise (large SE, small t).
5. **Fix:** drop a variable or combine variables.
6. **Contrast with pairwise correlation:** VIF catches multi-way collinearity; a correlation matrix does not.
7. **Contrast with other OLS violations:** multicollinearity inflates SEs; heteroskedasticity biases them (often deflated); serial correlation deflates them.

---

## Related Notes

- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- [[Breusch–Pagan test]]
- [[Heteroskedasticity]]
- [[Homoscedasticity and Heteroscedasticity]]
- [[Serial Correlation]]
- [[Hypothesis Testing in Regression]]
- [[R-Squared and Adjusted R-Squared]]
- [[F Distribution and F Tests]]
- [[Degrees of Freedom]]

---