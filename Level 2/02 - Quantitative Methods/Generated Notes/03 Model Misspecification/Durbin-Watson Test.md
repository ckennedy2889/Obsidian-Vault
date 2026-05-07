---
title: Durbin-Watson Test
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, time-series, diagnostics, serial-correlation]
aliases: [DW Test, Durbin Watson, DW Statistic, Durbin-Watson Statistic, First-Order Serial Correlation Test]
---

# Durbin-Watson Test

## The Real-World Analogy That Anchors Everything

Imagine you're a weather forecaster posting a daily temperature prediction. Each day, you compare what you guessed to what actually happened, and the difference is your *forecast error* for that day. If your forecasting method is working properly, those daily errors should look like random static — some days you're high, some days you're low, no pattern.

But suppose you notice something unsettling: when you underpredicted yesterday's temperature, you *also* tend to underpredict today's. When you overshot yesterday, you overshoot again today. Your errors are not random — they're carrying **memory** from one day to the next. Something about the weather system (an unaccounted-for ridge of high pressure, say) is causing your errors to cluster in streaks.

This "memory" in your errors is **serial correlation**, and it's precisely what the Durbin-Watson test is built to detect. The test answers one sharp question: *"Are my regression's errors today predictable from yesterday's errors?"* If yes, your regression's standard errors are lying to you, and every statistical claim downstream — t-stats, p-values, confidence intervals — is compromised.

**Memory hook:** *Durbin-Watson catches "echo errors" — residuals that echo the last one.*

---

## LOS This Note Fulfills

After reading, you should be able to:

- **Describe** what serial correlation is and why it breaks OLS inference.
- **Calculate** the Durbin-Watson statistic from a series of residuals.
- **Derive** the approximation $DW \approx 2(1 - \hat{\rho})$ and explain why it holds.
- **Interpret** DW values of 0, near 0, 2, near 2, near 4, and 4.
- **Apply** the DW decision rule using $d_L$ and $d_U$ critical values, including the inconclusive zone — for both positive and negative serial correlation.
- **Identify** when DW is *invalid* (lagged dependent variables) and its limitations (first-order only).
- **Choose** between DW, Breusch-Godfrey, and Newey-West corrections in context.

---

# Part 1 — Why the Test Exists: The Problem of Serial Correlation

## 1.1 The OLS assumption this test protects

One of the core [[Regression Assumptions|classical OLS assumptions]] is:

$$\text{Cov}(\varepsilon_t, \varepsilon_{t-k}) = 0 \quad \text{for all } k \neq 0$$

In plain English: *"any two different error terms are uncorrelated."* The residuals should be drawn as if from an urn with replacement — each one independent of all the others.

**Why does OLS need this?** Because OLS's standard-error formulas assume each observation contributes *independent* information about the slope. If two residuals are positively correlated, they partially duplicate each other's information, and you have less *effective* data than your $n$ suggests. The formulas don't know this and happily divide by the original $n$ — producing standard errors that are too small.

## 1.2 Why financial data breaks the assumption constantly

Time-series data in finance is the natural habitat of serial correlation:

- **Economic momentum:** if GDP shocks this quarter are positive, next quarter's usually are too (the economy doesn't flip on a dime).
- **Earnings persistence:** companies that beat earnings one quarter tend to beat again.
- **Regime behavior:** bull markets cluster, bear markets cluster.
- **Slow adjustment:** prices don't fully react to news instantly; the residual correction bleeds across multiple periods.
- **Missing variables:** if you omit a slow-moving factor (say, monetary policy stance), its influence ends up smeared across consecutive residuals.

For any of these reasons, real-world time-series regressions are *much* more likely to violate the no-autocorrelation assumption than they are to satisfy it.

## 1.3 Why serial correlation is dangerous (the damage chain)

Unlike [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity|multicollinearity]] (which inflates SEs and makes you too *timid*), positive serial correlation **deflates** standard errors — it makes you too *reckless*. Here's the chain of damage:

```
   Positive serial correlation in residuals
                 │
                 ▼
      OLS treats repeated info as independent
                 │
                 ▼
     Standard errors come out TOO SMALL
                 │
                 ▼
    t-statistic = b_hat / SE  ← SE deflated
                 │
                 ▼
              t-stats INFLATED
                 │
                 ▼
  p-values look much smaller than they should
                 │
                 ▼
   Reject H₀ when you shouldn't → Type I error
   "False positive" predictors everywhere
```

**Why this specific direction (deflation) for the common case of positive correlation?** Because positively correlated residuals mean that when one is high, the next is high too — they move together. OLS interprets "these residuals are small *deviations from each other*" as "my model is doing great" and shrinks its uncertainty estimate. The opposite happens for negative serial correlation, but it's much rarer in finance.

**Crucial point that often surprises students:** serial correlation does **not** bias the estimated slope coefficients themselves (they remain consistent). It only breaks the inference — the standard errors and every test that depends on them. The point estimates are still the same; their precision is just mis-reported.

---

# Part 2 — The Test Statistic

## 2.1 The formula

$$\boxed{\,DW = \frac{\displaystyle\sum_{t=2}^{n}(\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2}{\displaystyle\sum_{t=1}^{n} \hat{\varepsilon}_t^2}\,}$$

Break it apart piece by piece:

| Piece | What it is | Why it's there |
|---|---|---|
| **Numerator:** $\sum_{t=2}^{n}(\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2$ | Sum of squared **changes** between adjacent residuals | Measures how much residuals "jump around" from period to period. If residuals are **highly correlated**, they change little between adjacent periods → small numerator. If they're **anti-correlated**, they flip sign constantly → huge numerator. |
| **Denominator:** $\sum_{t=1}^{n} \hat{\varepsilon}_t^2$ | Sum of squared residuals (the usual [[Regression Statistics - Complete Reference\|SSE]]) | Normalizes the numerator by the overall scale of residuals, making DW unit-free. |
| **Start index 2 on top, 1 on bottom** | Numerator needs pairs $(\varepsilon_t, \varepsilon_{t-1})$, so it starts at $t=2$ | You can't compare $\varepsilon_1$ to a nonexistent $\varepsilon_0$. |

**Why squared differences in the numerator and not absolute differences?** Three reasons (same as everywhere in OLS): (1) squares are differentiable and mathematically tractable, (2) they let the clean approximation $DW \approx 2(1-\hat{\rho})$ pop out, and (3) they align with the squared-residual structure of the denominator, making the ratio unit-free.

## 2.2 Deriving the key approximation $DW \approx 2(1 - \hat{\rho})$

This derivation is worth doing slowly because it's the source of every interpretation rule below.

Expand the numerator:

$$\sum_{t=2}^{n}(\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2 = \sum_{t=2}^{n}\hat{\varepsilon}_t^2 - 2\sum_{t=2}^{n}\hat{\varepsilon}_t\hat{\varepsilon}_{t-1} + \sum_{t=2}^{n}\hat{\varepsilon}_{t-1}^2$$

For large $n$, the first and third sums are each approximately equal to $\sum \hat{\varepsilon}_t^2$ (you're just missing one boundary term). So the numerator is approximately:

$$\approx 2\sum \hat{\varepsilon}_t^2 - 2\sum \hat{\varepsilon}_t\hat{\varepsilon}_{t-1}$$

Divide by the denominator $\sum \hat{\varepsilon}_t^2$:

$$DW \approx 2 - 2\cdot\frac{\sum \hat{\varepsilon}_t\hat{\varepsilon}_{t-1}}{\sum \hat{\varepsilon}_t^2}$$

The fraction on the right is precisely the **sample first-order autocorrelation** of the residuals:

$$\hat{\rho} = \frac{\sum \hat{\varepsilon}_t\hat{\varepsilon}_{t-1}}{\sum \hat{\varepsilon}_t^2}$$

Therefore:

$$\boxed{\,DW \approx 2(1 - \hat{\rho})\,}$$

**Why this approximation matters:** it converts an unintuitive-looking sum-of-squared-differences formula into something directly interpretable. You stop thinking about "squared differences of residuals" and start thinking about "correlation between adjacent residuals."

## 2.3 Building intuition — what each DW value means

Since $\hat{\rho} \in [-1, +1]$, and $DW \approx 2(1-\hat{\rho})$:

| $\hat{\rho}$ | $DW$ | What the residuals look like |
|---|---|---|
| $-1$ | $4$ | Perfect anti-correlation — each residual is the exact opposite of the prior one |
| $-0.5$ | $3$ | Moderate negative — zig-zag pattern |
| $0$ | $2$ | **Independent** — random static. The model passes. |
| $+0.5$ | $1$ | Moderate positive — streaks on one side of zero |
| $+1$ | $0$ | Perfect positive — residuals are clones of the prior one |

```
        DW axis
        
      0 ─────────── 2 ─────────── 4
      │                           │
    ρ = +1       ρ = 0         ρ = −1
   perfect       random       perfect
   positive    (no problem)    negative
  correlation               correlation
   
   ◄──── problem ────►  ◄───── problem ─────►
```

**So: if the reported DW is much less than 2, suspect positive serial correlation. If much greater than 2, suspect negative. Right at 2, you're clean.**

---

# Part 3 — The Decision Rule (This Is Where Most Students Slip Up)

## 3.1 Why DW needs two critical values, not one

Most tests you've seen (t-test, F-test, chi-square) have a single critical value: above it → reject, below it → fail to reject. The DW test has **two**: a lower bound $d_L$ and an upper bound $d_U$. Why?

Because the DW statistic's exact sampling distribution under $H_0$ **depends on the specific values of the regressors $X$** — not just on $n$ and $k$. Different $X$-matrices yield slightly different null distributions, so a single universal critical value doesn't exist. What statisticians *can* prove is a **range** that contains the true critical value regardless of the $X$'s:

- **$d_L$** is the worst-case lower bound (most "demanding" critical value).
- **$d_U$** is the best-case upper bound (most "lenient" critical value).

Between $d_L$ and $d_U$, the true cutoff *could* be anywhere — which is why that region is called **inconclusive**: you genuinely don't have enough information to decide.

**Why there's an inconclusive zone at all:** it's an honesty tax. Rather than pretend a test has sharper discriminating power than it really does, the DW procedure tells you "your answer falls in the fuzzy band — I can't confidently say yes or no."

## 3.2 Hypotheses

You can run the DW test as:

| Test type | Null ($H_0$) | Alternative ($H_a$) |
|---|---|---|
| **Positive serial correlation** (most common) | $\rho = 0$ | $\rho > 0$ |
| **Negative serial correlation** | $\rho = 0$ | $\rho < 0$ |
| **Two-sided** | $\rho = 0$ | $\rho \neq 0$ |

Almost all exam questions test the positive-correlation case, because that's what actually happens in financial time series.

## 3.3 Decision rule — positive serial correlation test

Given your sample $DW$ and table values $d_L, d_U$ (which depend on $n$ and $k$):

```
                        d_L         d_U           2
                         │           │            │
  DW axis:   0 ──────────┼───────────┼────────────┼────────── 2
                         │           │            │
              Reject H₀  │ inconclusive │  Fail to Reject H₀
             (positive   │            │      (no evidence of
          serial correl. │            │    positive serial corr.)
            exists)      │            │
```

In words:

| If your DW is… | Decision | Interpretation |
|---|---|---|
| $DW < d_L$ | **Reject $H_0$** | Strong evidence of positive serial correlation |
| $d_L \leq DW \leq d_U$ | **Inconclusive** | Can't tell — treat cautiously, consider a better test |
| $DW > d_U$ | **Fail to reject $H_0$** | No evidence of positive serial correlation |

## 3.4 Decision rule — negative serial correlation test

The critical values are mirrored around 2: use $4 - d_U$ and $4 - d_L$.

| If your DW is… | Decision |
|---|---|
| $DW > 4 - d_L$ | **Reject $H_0$** (negative serial correlation exists) |
| $4 - d_U \leq DW \leq 4 - d_L$ | **Inconclusive** |
| $DW < 4 - d_U$ | **Fail to reject $H_0$** |

**Why the "4 minus" flip?** Because the DW distribution is symmetric around 2. A DW of 3.2 is "as extreme" from 2 as a DW of 0.8 — they're mirror images. So the decision regions for negative correlation are literally the mirror image of those for positive correlation, reflected across 2.

## 3.5 The "positive + negative" combined picture

```
  0 ─── d_L ─── d_U ──────── 2 ──────── 4−d_U ─── 4−d_L ─── 4
  │     │       │            │            │       │         │
  ├─────┤       │            │            │       ├─────────┤
  REJECT  INCONCLUSIVE   FAIL TO REJECT  INCONCLUSIVE  REJECT
  (positive               (no correlation)             (negative
   serial                                                serial
   correlation)                                          correlation)
```

**Memory trick:** DW far from 2 in *either* direction is trouble. Close to 2 is clean. The closer to 0, the worse the positive autocorrelation; the closer to 4, the worse the negative.

## 3.6 How $n$ and $k$ change the critical values

The DW table is indexed by:

- **$n$** — sample size (more rows = more rigid test)
- **$k$** — number of **slope** regressors (not counting the intercept)

As $n$ grows, $d_L$ and $d_U$ both rise and squeeze toward 2 — the test gets more powerful (smaller "inconclusive" band).

---

# Part 4 — Limitations (Exam Traps)

## 4.1 DW detects only **first-order** serial correlation

The test only looks at correlations between adjacent observations ($t$ and $t-1$). If your residuals have **seasonal** correlation — say, errors every 4 quarters (yearly seasonality) or every 12 months — DW will happily report a value near 2 and miss the pattern entirely.

**Why?** Because the formula pairs each residual only with its *immediate* predecessor. If $\hat{\varepsilon}_1$ and $\hat{\varepsilon}_5$ are highly correlated but adjacent residuals are uncorrelated, nothing in the DW formula catches it.

**Fix:** use the **Breusch-Godfrey (BG) test**, which can test autocorrelation at any lag (or several lags simultaneously).

## 4.2 DW is **invalid** when a lagged dependent variable is on the right-hand side

This is the most dangerous gotcha. Suppose your regression is:

$$Y_t = b_0 + b_1 Y_{t-1} + b_2 X_t + \varepsilon_t$$

(This is called an [[Autoregressive Models|autoregressive]] or "dynamic" specification.) In models like this, DW is **biased toward 2** — it systematically reports values close to 2 even when serial correlation is severe.

**Why?** Intuitively: because $Y_{t-1}$ is a regressor, OLS fits coefficients that force the residuals to be approximately uncorrelated with $Y_{t-1}$, which mechanically pushes DW toward 2 regardless of the true autocorrelation.

**Fix:** when you have lagged dependent variables, **do not use DW**. Use the Breusch-Godfrey test or the **Durbin h-test** (a modified DW for this specific case).

## 4.3 DW requires a constant (intercept) in the model

Without an intercept, the DW critical-value tables don't apply. Most regressions have an intercept, but this can trip up the rare specification without one.

## 4.4 DW requires the residuals to be ordered by time

If observations aren't in a meaningful time sequence (e.g., cross-sectional data on companies), DW is nonsense — you'd be measuring "correlation between residuals listed alphabetically by ticker," which has no economic meaning.

---

# Part 5 — Corrections (What to Do When You Reject H₀)

## 5.1 Newey-West (Hansen) standard errors

The most common fix. Newey-West recomputes the standard errors using a variance estimator that allows for autocorrelation *and* heteroskedasticity. Your coefficient estimates don't change — only their standard errors.

| Quantity | Before Newey-West | After Newey-West |
|---|---|---|
| $\hat{b}_j$ | unchanged | unchanged |
| $SE(\hat{b}_j)$ | deflated | **corrected upward** |
| $t$-stat | inflated | **deflated** (honest) |
| $p$-value | understated | **corrected** |

Result: fewer variables look significant, but the ones that survive are trustworthy.

## 5.2 Model re-specification

Sometimes serial correlation is a symptom of a **misspecified model**, not a fact about the error process. Common fixes:

- **Add missing variables** — especially slow-moving ones. If you omitted a variable whose influence drifts slowly, its effect ends up lumped into consecutive residuals.
- **Add lagged $Y$** — if the true process has dynamics, include $Y_{t-1}$. (But remember this invalidates DW itself — use BG for testing.)
- **Change the functional form** — e.g., difference the data if it's non-stationary.

## 5.3 Generalized Least Squares (GLS)

If you have a specific model for the autocorrelation structure (e.g., AR(1) with known $\rho$), you can re-weight observations to undo it. Less common in practice than Newey-West because it requires structural assumptions.

---

# Part 6 — Contrast with Breusch-Godfrey

| Feature | **Durbin-Watson (DW)** | **Breusch-Godfrey (BG)** |
|---|---|---|
| Lags tested | First-order only ($t-1$) | Any order, simultaneously |
| Works with lagged $Y$? | **No** (biased toward 2) | **Yes** |
| Requires intercept? | Yes | Yes |
| Test statistic distribution | Custom DW tables ($d_L$, $d_U$) | $\chi^2_p$ (where $p$ = number of lags) |
| Inconclusive zone? | **Yes** | No |
| Ease of use | Simple, shows on most outputs | Requires auxiliary regression |
| When to use | Classic time-series, no lagged $Y$ | Higher-order suspected, or lagged $Y$ present |

**BG is strictly more flexible; DW is the simpler default.** Expect the CFA exam to ask about DW; expect practitioners to prefer BG.

**Mnemonic:** *"DW for the simple case; BG when DW breaks."*

---

# Part 7 — Worked Numerical Example

**Setup:** An analyst fits a linear trend model for U.S. inflation:

$$\text{Inflation}_t = b_0 + b_1 \cdot \text{Time}_t + \varepsilon_t$$

with **$n = 228$ monthly observations** and **$k = 1$ slope regressor**.

### Step 1 — Observe the reported DW

Software output reports: $DW = 1.2145$.

First glance: $1.21$ is quite a bit below $2$. The $DW \approx 2(1-\hat{\rho})$ approximation gives:

$$\hat{\rho} \approx 1 - \frac{DW}{2} = 1 - \frac{1.2145}{2} \approx 1 - 0.607 = 0.393$$

So the sample first-order autocorrelation of residuals is roughly $+0.39$ — a substantial positive correlation. Red flag.

### Step 2 — Look up critical values

For $n = 228, k = 1$, the DW table (at $\alpha = 0.05$, positive-correlation test) gives approximately:

- $d_L \approx 1.77$
- $d_U \approx 1.78$

(Note: at this large $n$, $d_L$ and $d_U$ are squeezed tightly toward 2 — the inconclusive band is tiny.)

### Step 3 — Apply the decision rule

Compare: is $DW = 1.2145 < d_L = 1.77$?

Yes — **$1.2145 < 1.77$**. We are firmly in the "reject $H_0$" region, far from even the inconclusive band.

### Step 4 — Conclusion

**Reject $H_0$** (no positive serial correlation). Strong evidence of positive first-order serial correlation in the residuals.

### Step 5 — What the analyst must do next

- The reported standard errors are deflated.
- The reported t-statistics are inflated.
- The reported p-values are too small.
- **Do not trust any significance claim** from this regression until the standard errors are recomputed with Newey-West.

---

# Part 8 — Everything-in-One Summary Table

| Quantity | Formula / Rule | Meaning |
|---|---|---|
| DW statistic | $\dfrac{\sum_{t=2}^{n}(\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2}{\sum_{t=1}^{n}\hat{\varepsilon}_t^2}$ | Test statistic |
| Approximation | $DW \approx 2(1 - \hat{\rho})$ | Connects DW to the first-order autocorrelation of residuals |
| DW range | $0 \leq DW \leq 4$ | Always bounded |
| $DW = 2$ | $\hat{\rho} = 0$ | No serial correlation (good) |
| $DW < 2$ | $\hat{\rho} > 0$ | Positive serial correlation (common in finance) |
| $DW > 2$ | $\hat{\rho} < 0$ | Negative serial correlation (rare) |
| Positive-corr test | Reject $H_0$ if $DW < d_L$ | Serial correlation exists |
| | Inconclusive if $d_L \leq DW \leq d_U$ | Ambiguous |
| | Fail to reject if $DW > d_U$ | Clean |
| Negative-corr test | Mirror rule: $(4-d_U), (4-d_L)$ | Same logic, reflected around 2 |
| Critical values | Depend on $n$ and $k$ | From the DW table |
| Limitation 1 | First-order only | Use BG for higher-order |
| Limitation 2 | Invalid with lagged $Y$ | Use BG or Durbin h |
| Fix when reject | **Newey-West / Hansen SEs** | Keeps $\hat{b}_j$, corrects $SE(\hat{b}_j)$ |

---

# Part 9 — Common Exam Traps

1. **"DW = 2 means great model"** — it means no *first-order* serial correlation. Higher-order correlation could still exist. Don't over-claim.
2. **Confusing $d_L$ and $d_U$** — the tighter boundary ($d_L$) is the rejection cutoff for *positive* serial correlation. Think: "DW has to beat the *lower* bar to be *rejected* as clean."
3. **Forgetting the inconclusive zone** — it's a real outcome, not "probably fine." If your answer lands there, say "inconclusive" and switch to BG.
4. **Applying DW to a model with lagged $Y$** — invalid. The CFA loves testing this trap. If you see $Y_{t-1}$ on the right-hand side, *never* use DW.
5. **Using $k$ including the intercept** — the $k$ in the DW table is the number of *slopes*, not slopes plus intercept.
6. **Forgetting which direction deflates SEs** — **positive** serial correlation deflates SEs (inflated t-stats, Type I errors). Negative is the reverse and less common.
7. **DW doesn't bias coefficients** — the slopes $\hat{b}_j$ remain consistent. Only the inference breaks. (Same as [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity|multicollinearity]] and [[Homoscedasticity and Heteroscedasticity|heteroskedasticity]] in this respect.)
8. **Confusing DW with Breusch-Pagan** — BP tests heteroskedasticity (variance), DW tests serial correlation (autocorrelation). They are **different problems** with **different tests**. See [[Breusch–Pagan test]].

---

# Part 10 — Memory Hooks

- **"Two is true"** — DW near 2 means no first-order correlation. Anywhere else is trouble.
- **"Low DW = high $\hat{\rho}$"** — the further below 2, the more positive the autocorrelation.
- **"Squash or zigzag"** — positive correlation squashes residuals on one side (DW low); negative correlation zigzags them (DW high).
- **"Left of $d_L$ = Liar"** — if $DW < d_L$, your regression's standard errors are lying.
- **"DW fails when lag is on the line"** — lagged $Y$ as a regressor kills DW's validity.
- **"DW catches echoes at lag 1; BG catches them at any lag"** — when to upgrade tests.
- **"DW → Newey-West"** — reject DW, reach for Newey-West corrections.

---

# Part 11 — The Diagnostic Triangle

| OLS violation | Primary test | Effect on SEs | Primary fix |
|---|---|---|---|
| [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]] | [[Variance Inflation Factor (VIF)\|VIF]] | **Inflated** | Drop/combine variables |
| [[Homoscedasticity and Heteroscedasticity\|Heteroskedasticity]] | [[Breusch–Pagan test\|BP test]] | Biased (often deflated) | White/robust SEs |
| **Serial correlation** | **Durbin-Watson / Breusch-Godfrey** | **Deflated (if positive)** | **Newey-West SEs** |

**Mirror image mnemonic:** multicollinearity *inflates* SEs (you get too timid); positive serial correlation *deflates* SEs (you get too reckless). Two opposite failure modes.

---

# Related Notes

- [[Serial Correlation]] — the umbrella concept this test diagnoses
- [[Breusch–Pagan test]] — the parallel test for heteroskedasticity
- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- [[Variance Inflation Factor (VIF)]]
- [[Homoscedasticity and Heteroscedasticity]]
- [[Regression Statistics - Complete Reference]] — full regression output reference
- [[Hypothesis Testing in Regression]]
- [[Autoregressive Models]]
- [[F Distribution and F Tests]]
- [[Ordinary Least Squares]]
- [[Regression Assumptions]]

---