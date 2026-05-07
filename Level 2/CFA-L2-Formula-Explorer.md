# 📘 CFA Level II — Complete Formula Explorer

> **~165 formulas** · All sections · Worked examples · Obsidian-linked

---

## Table of Contents

- [[#📊 Quantitative Methods]]
  - [[#LM1-2 Regression & Model Fit]]
  - [[#LM3 Model Misspecification]]
  - [[#LM5 Time Series]]
  - [[#LM6-7 ML Metrics]]
- [[#🌍 Economics]]
  - [[#LM1 Currency Exchange Rates]]
  - [[#LM2 Economic Growth]]
- [[#📑 Financial Reporting]]
  - [[#Key Ratios]]
  - [[#Operating & Financial Leverage]]
  - [[#Intercorporate & Pensions]]
  - [[#Pension Accounting]]
  - [[#Accrual Ratios & Earnings Quality]]
  - [[#Earnings Quality & Insurance]]
- [[#🏢 Corporate Issuers]]
  - [[#Dividends & Repurchases]]
  - [[#Cost of Capital]]
  - [[#WACC]]
  - [[#MM Propositions & Beta Levering]]
- [[#📈 Equity Valuation]]
  - [[#Dividend Discount Models]]
    - [[#Two-Stage & Three-Stage DDM]]
  - [[#FCF Valuation]]
  - [[#Multiples & Residual Income]]
- [[#🏦 Fixed Income]]
  - [[#Term Structure]]
  - [[#Bond Pricing & Yield Measures]]
  - [[#Duration & Convexity]]
  - [[#Spreads & Credit Risk]]
  - [[#Embedded Options]]
  - [[#Credit & CDS]]
- [[#⚡ Derivatives]]
  - [[#Forwards & FRA]]
  - [[#Swaps]]
  - [[#Options]]
  - [[#Put-Call Parity]]
  - [[#Option Greeks]]
- [[#🏠 Alternatives]]
  - [[#Commodities]]
  - [[#Real Estate]]
  - [[#Hedge Funds]]
  - [[#Private Equity Multiples]]
- [[#🎯 Portfolio Management]]
  - [[#Factor Models]]
  - [[#Portfolio Mathematics]]
  - [[#Roy's Safety-First & Leverage]]
  - [[#VaR]]
  - [[#Economics & Investment Markets]]
  - [[#Active Management]]

---

# 📊 Quantitative Methods

## LM1-2 Regression & Model Fit

### General MR Equation

$$Y = b_0 + b_1 X_1 + b_2 X_2 + \ldots + b_n X_n$$

**In Plain English:** Y predicted by weighted sum of X's. Each b is a partial slope — effect of changing that X by 1, holding others constant.

| Variable | Meaning |
|----------|---------|
| $Y$ | Dependent variable |
| $b_0$ | Intercept |
| $b_1 \ldots b_n$ | Partial regression coefficients |
| $df$ | $n - k - 1$ |

> 💡 **Why / Analogy:** Like a recipe: Y is the dish, each X is an ingredient, each b tells how much to add. "Partial" isolates one ingredient's effect.

**📝 Worked Example:**
```
Ŷ = 2.5 + 1.8X₁ − 0.6X₂, X₁=3, X₂=4
Ŷ = 2.5 + 1.8(3) − 0.6(4) = 2.5 + 5.4 − 2.4 = 5.5
1-unit ↑ in X₁ → Ŷ ↑ by 1.8 holding X₂ constant
```

**Key Points & Exam Traps:**
- k slopes, k+1 total coefficients
- Dummies: use n−1 (0 or 1)
- Log-log: coefficients = elasticities

---

### R² and Adjusted R²

$$\bar{R}^2 = 1 - \frac{n-1}{n-k-1} \times (1 - R^2)$$

**In Plain English:** [[R²]] = fraction of variation explained. [[Adjusted R²]] penalizes for useless variables and can decrease.

| Variable | Meaning |
|----------|---------|
| $R^2$ | RSS/SST (0 to 1) |
| $\bar{R}^2$ | Penalized version |
| $n$ | Observations |
| $k$ | Variables |

> 💡 **Why / Analogy:** R² only goes up with more variables, even bad ones. Adjusted R² docks you for guessing.

**📝 Worked Example:**
```
R²=0.78, n=50, k=4
R̄² = 1 − [49/45] × 0.22
   = 1 − 1.089 × 0.22 = 0.760
```

**Key Points & Exam Traps:**
- Use $\bar{R}^2$ to compare models with different k
- $MSE = SSE/(n-k-1)$
- $R^2$ always ↑ with more variables

---

### AIC & BIC

$$AIC = n \cdot \ln(SSE/n) + 2(k+1)$$
$$BIC = n \cdot \ln(SSE/n) + \ln(n) \cdot (k+1)$$

**In Plain English:** Balance fit vs complexity. Lower = better. [[AIC]] for forecasting, [[BIC]] for goodness of fit.

| Variable | Meaning |
|----------|---------|
| $SSE$ | Sum of squared errors |
| $n$ | Observations |
| $k$ | Variables |

> 💡 **Why / Analogy:** Two judges: AIC lenient, BIC strict. BIC penalty > AIC when n ≥ 8.

**📝 Worked Example:**
```
SSE=200, n=100, k=3
AIC = 100·ln(2) + 2(4) = 69.31 + 8 = 77.31
BIC = 100·ln(2) + ln(100)·4 = 69.31 + 18.42 = 87.73
```

**Key Points & Exam Traps:**
- Lower always better
- BIC penalizes harder ($\ln(n)$ vs 2)
- AIC for prediction, BIC for parsimony

---

### F-Test (Joint Hypothesis)

$$F = \frac{(SSE_r - SSE_u) / q}{SSE_u / (n - k - 1)}$$

**In Plain English:** Tests whether a group of variables jointly matter. Compares restricted vs unrestricted model.

| Variable | Meaning |
|----------|---------|
| $SSE_r$ | Restricted model SSE |
| $SSE_u$ | Unrestricted SSE |
| $q$ | # restrictions |

> 💡 **Why / Analogy:** Remove ingredients, taste both. F asks: did removing them make it significantly worse?

**📝 Worked Example:**
```
SSEᵣ=500, SSEᵤ=400, q=2, n=60, k=4
F = [100/2] / [400/55] = 50/7.27 = 6.88
F-crit(2,55) at 5% ≈ 3.16 → Reject → variables matter
```

**Key Points & Exam Traps:**
- Overall fit: $F = (RSS/k)/(SSE/(n-k-1))$
- One-tailed right-tail
- Reject H₀ → jointly significant

---

## LM3 Model Misspecification

### Breusch-Pagan (Heteroskedasticity)

$$\text{Test stat} = nR^2 \sim \chi^2(k)$$
$$H_0: \text{No conditional heteroskedasticity}$$

**In Plain English:** Regress squared residuals on X's. High R² → error variance depends on X.

| Variable | Meaning |
|----------|---------|
| $\varepsilon^2$ | Squared residuals |
| $nR^2$ | Test statistic |
| $H_0$ | No hetero (don't want to reject) |

> 💡 **Why / Analogy:** Noise gets louder depending on X — like a speaker distorting at volume. Messes up standard errors.

**📝 Worked Example:**
```
n=100, R²(auxiliary)=0.12, k=3
nR² = 100 × 0.12 = 12
χ²(3) crit 5% = 7.815
12 > 7.815 → Reject → Heterosked present → Use White robust SE
```

**Key Points & Exam Traps:**
- Do NOT want to reject H₀
- One-tailed test
- Fix: [[White-corrected SE]]

---

### Durbin-Watson (Serial Correlation)

$$DW \approx 2(1 - r)$$

Reject if $DW < d_L$; Don't reject if $DW > d_U$

**In Plain English:** Tests [[Serial Correlation]] in residuals. DW~2 = no SC. ~0 = positive SC. ~4 = negative SC.

| Variable | Meaning |
|----------|---------|
| $DW$ | 0 to 4 |
| $r$ | $\text{Corr}(\varepsilon_t, \varepsilon_{t-1})$ |
| $d_L, d_U$ | Critical bounds |

> 💡 **Why / Analogy:** If today's error predicts tomorrow's, model is missing something systematic.

**📝 Worked Example:**
```
r=0.35, dL=1.46, dU=1.63
DW = 2(1−0.35) = 1.30
1.30 < 1.46(dL) → Reject → Positive SC → Newey-West SE
```

**Key Points & Exam Traps:**
- Can't use with lagged DV → [[Breusch-Godfrey]]
- Inconclusive between $d_L$ and $d_U$
- Fix: [[Newey-West SE|Newey-West robust SE]]

---

### Breusch-Godfrey (SC with Lagged DV)

$$H_0: \text{No serial correlation}$$
$$\chi^2 \text{ for lag=1; F-stat for lag>1}$$

**In Plain English:** Alternative to [[Durbin-Watson (Serial Correlation)|DW]] that works with lagged dependent variables.

| Variable | Meaning |
|----------|---------|
| $p$ | Lags tested |
| $df$ | $n - p - k - 1$ |

> 💡 **Why / Analogy:** DW breaks when lagged Y is an IV. BG handles this by regressing residuals on lagged residuals.

**📝 Worked Example:**
```
Model: Yₜ = b₀ + b₁Yₜ₋₁ + ε (can't use DW!)
BG: regress εₜ on εₜ₋₁ and original X's
χ² stat=8.2, crit(1df)=3.84 → Reject → SC present
```

**Key Points & Exam Traps:**
- Use when model has lagged DV
- χ² for lag=1, F for lag>1
- Fix: [[Newey-West SE]]

---

### VIF (Multicollinearity)

$$VIF_j = \frac{1}{1 - R_j^2}$$

**In Plain English:** How much coefficient variance is inflated by correlation among X's.

| Variable | Meaning |
|----------|---------|
| $VIF_j$ | Variance Inflation Factor |
| $R_j^2$ | R² from regressing $X_j$ on other X's |

> 💡 **Why / Analogy:** Two witnesses telling the same story — can't tell who really saw the crime.

**📝 Worked Example:**
```
R²(X₂ on X₁,X₃) = 0.88
VIF₂ = 1/(1−0.88) = 1/0.12 = 8.33
> 5 → Investigate multicollinearity!
```

**Key Points & Exam Traps:**
- VIF > 5 → investigate
- VIF > 10 → serious
- F sig but t-tests not = classic [[CFA_Glossary/Multicollinearity|MC]]

---

### Logistic Regression

$$\ln\left[\frac{p}{1-p}\right] = b_0 + b_1 X_1 + \ldots + b_n X_n$$
$$\text{odds} = e^{\hat{y}}; \quad P = \frac{\text{odds}}{1 + \text{odds}}$$

**In Plain English:** Predicts probability of binary event. Output forced between 0 and 1.

| Variable | Meaning |
|----------|---------|
| $p$ | Probability |
| $p/(1-p)$ | Odds |
| $\ln(p/(1-p))$ | Logit |

> 💡 **Why / Analogy:** Regular regression can predict outside 0–1 — nonsense for probabilities. Logistic forces valid output.

**📝 Worked Example:**
```
ln[p/(1−p)] = −3 + 0.05(Income $K)
Income=$80K: Logit = −3+4 = 1
odds = e¹ = 2.718
P = 2.718/3.718 = 73.1%
```

**Key Points & Exam Traps:**
- Use Likelihood Ratio test
- $P = 1/(1+e^{-\hat{y}})$
- Coefficients affect log-odds, not P directly

---

## LM5 Time Series

### Trend Models

$$\text{Linear: } y_t = b_0 + b_1 t + \varepsilon_t$$
$$\text{Log-linear: } \ln(y_t) = b_0 + b_1 t + \varepsilon_t$$

**In Plain English:** Linear = constant $ growth. Log-linear = constant % growth. Most economic data → log-linear.

| Variable | Meaning |
|----------|---------|
| $b_1$ | Trend coefficient |
| $t$ | Time |
| $\varepsilon_t$ | Error |

> 💡 **Why / Analogy:** Linear = adding $100/yr. Log-linear = growing 5%/yr.

**📝 Worked Example:**
```
ln(yₜ) = 3.2 + 0.04t → growth = 4%/period
t=20: ln(y₂₀) = 4.0 → y₂₀ = e⁴ = 54.60
```

**Key Points & Exam Traps:**
- If DW≠2 → [[Durbin-Watson (Serial Correlation)|SC]] → SE biased downward
- Log-linear $b_1$ ≈ growth rate

---

### AR(1) & Mean-Reverting Level

$$x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$$
$$\bar{x} = \frac{b_0}{1 - b_1}$$

**In Plain English:** Today depends on yesterday plus noise. If $b_1 < 1$, series gravitates to $\bar{x}$.

| Variable | Meaning |
|----------|---------|
| $b_1$ | < 1 for stationarity |
| $\bar{x}$ | Mean-reverting level |
| Cov. Stationary | Constant mean, variance, covariance |

> 💡 **Why / Analogy:** Rubber band tied to a post ($\bar{x}$). Can stretch but always snaps back. $b_1 \geq 1$ = band breaks.

**📝 Worked Example:**
```
xₜ = 5.2 + 0.68xₜ₋₁
x̄ = 5.2/(1−0.68) = 16.25
b₁=0.68<1 → Stationary ✓
If x=20 (above 16.25) → predicts drift down
```

**Key Points & Exam Traps:**
- Can't use [[Durbin-Watson (Serial Correlation)|DW]] with lagged DV
- $RMSE = \sqrt{\Sigma\varepsilon^2/n}$
- Not stationary → first-difference

---

### Random Walk & Dickey-Fuller

$$\text{RW: } x_t = x_{t-1} + \varepsilon_t \quad (b_0=0, b_1=1)$$
$$\text{DF: } g = b_1 - 1; \quad H_0: g=0, \quad H_a: g<0$$

**In Plain English:** RW has no [[AR(1) & Mean-Reverting Level|mean reversion]]. [[Dickey-Fuller]] tests if $b_1$ statistically = 1.

| Variable | Meaning |
|----------|---------|
| $g$ | $b_1 - 1$; $g = 0$ → unit root |
| $H_0$ | $g = 0$ (random walk) |
| $H_a$ | $g < 0$ (mean reverting) |

> 💡 **Why / Analogy:** Drunk walking — each step random, never finds home. DF asks: drunk or has a destination?

**📝 Worked Example:**
```
(xₜ−xₜ₋₁) = 0.3 − 0.05xₜ₋₁
g=−0.05, t-stat=−1.8, DF crit=−2.86
|1.8|<|2.86| → Fail to reject → Unit root → first-difference
```

**Key Points & Exam Traps:**
- RW with drift: $b_0 \neq 0$
- After differencing: stationary but no forecast power
- Can't estimate [[AR(1) & Mean-Reverting Level|AR(1)]] on a RW

---

### ARCH(1)

$$\hat{\varepsilon}^2_t = a_0 + a_1 \hat{\varepsilon}^2_{t-1} + \mu$$
$$H_0: a_1 = 0 \text{ (constant variance)}$$

**In Plain English:** Tests volatility clustering — big shock predicts future volatility?

| Variable | Meaning |
|----------|---------|
| $\hat{\varepsilon}^2$ | Squared residuals |
| $a_1$ | If ≠ 0 → ARCH effects |

> 💡 **Why / Analogy:** Market moods are contagious: stormy days follow stormy days.

**📝 Worked Example:**
```
ε̂²ₜ = 0.0004 + 0.35ε̂²ₜ₋₁, t=3.2>1.96
→ Reject → ARCH present
σ̂²ₜ₊₁ = 0.0004+0.35(0.0025) = 0.001275
```

**Key Points & Exam Traps:**
- Reject → ARCH effects
- $\hat{\sigma}^2_{t+1} = \hat{a}_0 + \hat{a}_1 \hat{\varepsilon}^2_t$

---

### Cointegration (Engle-Granger)

$$(\varepsilon_t - \varepsilon_{t-1}) = b_0 + g\varepsilon_{t-1} + \mu$$
$$H_0: g = 0 \text{ (no cointegration)}$$

**In Plain English:** Two unit-root series with stable long-run relationship if residuals are stationary.

| Variable | Meaning |
|----------|---------|
| $g$ | ≠ 0 → cointegrated |
| $H_0$ | $g = 0$ (not cointegrated) |

> 💡 **Why / Analogy:** Two drunks tied with rope — each wanders but can't get too far apart.

**📝 Worked Example:**
```
Residuals: (εₜ−εₜ₋₁) = 0.01 − 0.42εₜ₋₁
t=−3.8, crit=−3.37 → Reject → Cointegrated!
```

**Key Points & Exam Traps:**
- Both UR + cointegrated → OK
- Neither UR → OK
- One UR, one not → NOT OK

---

## LM6-7 ML Metrics

### Precision, Recall, F1, RMSE

$$P = \frac{TP}{TP+FP}; \quad R = \frac{TP}{TP+FN}$$
$$F_1 = \frac{2PR}{P+R}$$
$$\text{Accuracy} = \frac{TP+TN}{\text{All}}$$
$$RMSE = \sqrt{\frac{\Sigma(\text{pred}-\text{actual})^2}{n}}$$

**In Plain English:** P = how precise flags are. R = how many caught. F1 balances both. RMSE for continuous.

| Variable | Meaning |
|----------|---------|
| TP/FP/FN/TN | True/False Pos/Neg |
| $F_1$ | Harmonic mean of P, R |

> 💡 **Why / Analogy:** Accuracy misleading with imbalanced data. F1 forces catching events AND avoiding false alarms.

**📝 Worked Example:**
```
TP=40, FP=10, FN=20, TN=930
P=40/50=0.80; R=40/60=0.667
F1=2(.80)(.667)/1.467=0.727
Accuracy=970/1000=97% (misleading!)
```

**Key Points & Exam Traps:**
- ROC: TPR vs FPR
- RMSE for continuous targets
- Supervised = labeled; Unsupervised = unlabeled

---

# 🌍 Economics

## LM1 Currency Exchange Rates

### Bid-Ask & Inverting

$$P/B: \text{bid} \mid \text{offer}$$
$$B/P: 1/\text{offer} \mid 1/\text{bid}$$
$$\text{Cross: } (A/C)_{\text{bid}} = (A/B)_{\text{bid}} \times (B/C)_{\text{bid}}$$

**In Plain English:** Dealer buys base at bid, sells at offer. Invert: flip AND swap. Cross: bid×bid, offer×offer.

| Variable | Meaning |
|----------|---------|
| $P/B$ | Price per 1 Base |
| Bid | Dealer buys |
| Offer | Dealer sells |

> 💡 **Why / Analogy:** Dealer always buys low, sells high. Inverting: old offer → new bid.

**📝 Worked Example:**
```
USD/CAD: 1.3304/1.3309
CAD/USD: 1/1.3309=0.7514 | 1/1.3304=0.7517
```

**Key Points & Exam Traps:**
- Dealer bid < Interbank offer
- "Up the bid, down the ask"

---

### CIRP

$$F(P/B) = S(P/B) \times \frac{1 + i_P(d/360)}{1 + i_B(d/360)}$$
$$\text{Premium} = F - S$$

**In Plain English:** Forward rate = spot × interest rate ratio. No-arbitrage: can't profit from rate differentials.

| Variable | Meaning |
|----------|---------|
| $F$ | Forward |
| $S$ | Spot |
| $i_P / i_B$ | Price/Base currency rates |

> 💡 **Why / Analogy:** Borrow cheap, invest dear, lock FX → free money. CIRP prevents this by adjusting the forward.

**📝 Worked Example:**
```
S(USD/EUR)=1.10, iUSD=4%, iEUR=2%, 180d
F = 1.10×(1.02/1.01) = 1.10×1.00990 = 1.1109
Premium = +0.0109
```

**Key Points & Exam Traps:**
- $i_P > i_B$ → premium
- CIRP enforced by arbitrage
- MtM: calc $F_0$, $F_1$, discount difference → see [[Forward Mark-to-Market]]

---

### Forward Mark-to-Market

$$\text{Step 1: Calculate } F_0$$
$$\text{Step 2: Calculate } F_1 \text{ (new fwd for remaining time)}$$
$$V_t = \frac{(F_1 - F_0) \times \text{size}}{1 + r(d/360)}$$

**In Plain English:** Value of existing forward = PV of difference between current and original forward rates.

| Variable | Meaning |
|----------|---------|
| $F_0$ | Original forward |
| $F_1$ | Current forward |
| $r$ | Discount rate for remaining period |

> 💡 **Why / Analogy:** Comparing what you locked in vs what the market offers now. Discount the difference.

**📝 Worked Example:**
```
F₀=1.1109, 3mo later F₁=1.1200, 90d remain, r=4%
V = (1.12−1.1109)×€1M / [1+0.04(90/360)]
  = 0.0091M / 1.01 = $9,010 gain (long EUR)
```

**Key Points & Exam Traps:**
- Positive V → gain for long position
- Use remaining-period rate to discount

---

### UIRP, PPP & Intl Fisher

$$\text{UIRP: } \%\Delta S(f/d)^e = i_f - i_d$$
$$\text{PPP: } \%\Delta S \approx \pi_f - \pi_d$$
$$\text{Ex ante PPP: } \%\Delta S^e = \pi_f^e - \pi_d^e$$
$$\text{IFE: } i_f - i_d = \pi_f^e - \pi_d^e$$

**In Plain English:** [[UIRP]]: spot change = interest diff. [[PPP]]: spot change = inflation diff. [[IFE]]: combines both.

| Variable | Meaning |
|----------|---------|
| $\%\Delta S^e$ | Expected spot change |
| $i_f / i_d$ | Interest rates |
| $\pi_f / \pi_d$ | Inflation rates |

> 💡 **Why / Analogy:** High-rate currency expected to depreciate (UIRP). High-inflation depreciates (PPP). IFE: same coin.

**📝 Worked Example:**
```
iUK=5%, iUS=3%
UIRP: GBP depreciates 2%
πUK=4%, πUS=2% → PPP: same 2%
IFE: 5−3=4−2 → real rates equal (2%)
```

**Key Points & Exam Traps:**
- Fwd rate parity: $F = S^e$ ([[CIRP]] + [[UIRP]])
- PPP better long-term
- Carry trade profits when UIRP fails

---

## LM2 Economic Growth

### Cobb-Douglas

$$Y = AK^\alpha L^{1-\alpha}; \quad y = Ak^\alpha$$

**In Plain English:** Output = technology × capital × labor. Per-worker: productivity depends on capital per worker.

| Variable | Meaning |
|----------|---------|
| $A$ | TFP (Total Factor Productivity) |
| $\alpha$ | Capital share (~0.3) |
| $y$ | Output/worker |
| $k$ | Capital/worker |

> 💡 **Why / Analogy:** Three ways to grow: more workers, more machines/worker (deepening), better tech. Diminishing returns.

**📝 Worked Example:**
```
A=1.5, K=1000, L=500, α=0.3
Y = 1.5×1000⁰·³×500⁰·⁷ = 1.5×7.94×96.47 ≈ 1,149
y = 1149/500 = 2.30
```

**Key Points & Exam Traps:**
- ↑k = deepening; ↑A = tech progress
- $\alpha < 1$ → diminishing returns

---

### Growth Accounting

$$\frac{\Delta Y}{Y} \approx \frac{\Delta A}{A} + \alpha \frac{\Delta K}{K} + (1-\alpha)\frac{\Delta L}{L}$$
$$\frac{\Delta A}{A} \approx \frac{\Delta Y}{Y} - \alpha \frac{\Delta K}{K} - (1-\alpha)\frac{\Delta L}{L}$$
$$\frac{\Delta y}{y} \approx \frac{\Delta A}{A} + \alpha \frac{\Delta k}{k}$$
$$g_{Y^*} \approx g_L + g_{\text{labor productivity}}$$
$$\text{Steady state per capita} = \frac{\theta}{1-\alpha}$$
$$\text{Output growth} = \frac{\theta}{1-\alpha} + n$$

**In Plain English:** GDP growth decomposed into tech + capital + labor. $\Delta A / A$ = [[Solow Residual]]. [[Potential GDP]] growth can also be estimated as labor force growth + labor productivity growth.

| Variable | Meaning |
|----------|---------|
| $\Delta A / A$ | TFP growth (residual) |
| $y=Y/L$ | Output per worker |
| $k=K/L$ | Capital per worker |
| $\theta$ | Tech growth rate |
| $n$ | Labor force growth |

> 💡 **Why / Analogy:** Receipt showing where growth came from. What K and L can't explain = technology.

**📝 Worked Example:**
```
GDP grew 4%, K grew 5%, L grew 1%, α=0.3
ΔA/A = 4−0.3(5)−0.7(1) = 4−1.5−0.7 = 1.8%
```

**Key Points & Exam Traps:**
- Potential GDP = LF growth + productivity growth
- LF 1% + prod 2% → potential = 3%
- Per-worker growth uses $k$, not total $K$
- Solow residual = what K and L growth cannot explain

---

### Capital Stock, Output Gap & Steady State

$$K_t = K_{t-1} + I_t - D_t$$
$$\text{Net investment} = I_t - D_t$$
$$k = \frac{K}{L}; \quad \frac{\Delta k}{k} \approx \frac{\Delta K}{K} - \frac{\Delta L}{L}$$
$$\text{Output gap} = Y - Y^*; \quad \text{Output gap \%} = \frac{Y - Y^*}{Y^*}$$
$$s f(k^*) = \left(\delta + n + \frac{\theta}{1-\alpha}\right)k^*$$
$$MPK = \alpha\frac{Y}{K} \approx r_{\text{real}} \text{ in equilibrium}$$

**In Plain English:** [[CFA_Glossary/Capital stock]] rises when investment exceeds depreciation. [[CFA_Glossary/Output gap]] measures actual GDP vs sustainable GDP. Solow steady state occurs when actual investment just covers break-even investment.

| Variable | Meaning |
|----------|---------|
| $K_t$ | Ending capital stock |
| $I_t$ | Gross investment |
| $D_t$ | Depreciation |
| $Y^*$ | [[Potential GDP]] |
| $s$ | Saving rate |
| $\delta$ | Depreciation rate |
| $MPK$ | Marginal product of capital |

> 💡 **Why / Analogy:** Capital stock is the bathtub water level; investment is the faucet; depreciation is the drain. Output gap is the economy's speedometer versus its sustainable speed limit.

**📝 Worked Example:**
```
K₀=1,000, I=120, D=50
K₁ = 1,000 + 120 − 50 = 1,070

Actual GDP=22.0, Potential GDP=21.5
Output gap = (22.0−21.5)/21.5 = 2.33% positive
Positive gap → inflation pressure → rates likely ↑
```

**Key Points & Exam Traps:**
- Positive output gap: $Y>Y^*$ → overheating, inflation pressure, tighter policy
- Negative output gap: $Y<Y^*$ → slack, unemployment pressure, easier policy
- Higher saving raises the level of $y$, not the long-run Solow growth rate
- In steady state, $Y/K$ and $MPK$ are constant

---

### Stock Market & GDP

$$\frac{1}{T}\%\Delta P = \frac{1}{T}\%\Delta GDP + \frac{1}{T}\%\Delta(E/GDP) + \frac{1}{T}\%\Delta(P/E)$$
$$E(R_e) \approx DY + \Delta(P/E) + i + g - \Delta S$$
$$\Delta S = nbb + rd$$

**In Plain English:** Stock returns from GDP + earnings share + P/E expansion. Grinold-Kroner adds dividend yield, inflation, real growth, repricing, and dilution. Long-run: earnings growth is bounded by [[Potential GDP]] growth.

| Variable | Meaning |
|----------|---------|
| $P$ | Equity value |
| $E/GDP$ | Earnings share |
| $P/E$ | Multiple |
| $DY$ | Dividend yield |
| $i$ | Inflation |
| $g$ | Real economic growth |
| $\Delta S$ | Dilution / change in shares outstanding |
| $nbb$ | Net buybacks |
| $rd$ | Relative dynamism |

> 💡 **Why / Analogy:** Short-term: P/E swings. Long-term: E/GDP→0, P/E→0, stocks ≈ GDP.

**📝 Worked Example:**
```
GDP=3%, ΔE/GDP=0.5%, ΔP/E=2%
Short: 5.5%; Long-run: ≈ 3%
```

**Key Points & Exam Traps:**
- Long-run stock returns ≈ GDP growth
- P/E can't expand forever
- Earnings share of GDP cannot rise forever
- High GDP growth does not guarantee high equity returns if dilution is large

---

# 📑 Financial Reporting

## Key Ratios

### Liquidity & CCC

$$\text{Current} = CA/CL; \quad \text{Quick} = (Cash+STI+Recv)/CL$$
$$\text{Cash} = (Cash+STI)/CL$$
$$CCC = DOH + DSO - \text{Days Payable}$$
$$DOH = 365/\text{InvTO}; \quad DSO = 365/\text{RecvTO}$$

**In Plain English:** How fast cash moves through operations. Lower [[CCC]] = more efficient.

| Variable | Meaning |
|----------|---------|
| CCC | Days cash tied up |
| DOH | Inventory days |
| DSO | Collection days |

> 💡 **Why / Analogy:** Cash flowing through pipes. DOH/DSO = where it's stuck. Days Payable = borrowed time.

**📝 Worked Example:**
```
InvTO=8, RecvTO=12, PayTO=10
DOH=45.6, DSO=30.4, DaysPay=36.5
CCC = 45.6+30.4−36.5 = 39.5 days
```

**Key Points & Exam Traps:**
- Negative CCC = collect before paying (Amazon)
- Defensive Interval = liquid assets / daily expenses

---

### DuPont 5-Way & Sustainable Growth

$$ROE = \frac{NI}{EBT} \times \frac{EBT}{EBIT} \times \frac{EBIT}{Rev} \times \frac{Rev}{TA} \times \frac{TA}{Eq}$$
$$g = RR \times ROE$$
$$EPS = (NI - \text{PrefDiv}) / \text{WtdAvgShares}$$
$$BVPS = \text{CommonEq} / \text{SharesOut}$$

**In Plain English:** [[ROE]] decomposed into tax, interest, margin, turnover, leverage. Growth = what you keep × what you earn.

| Variable | Meaning |
|----------|---------|
| NI/EBT | Tax burden |
| EBT/EBIT | Interest burden |
| EBIT/Rev | Margin |
| Rev/TA | Turnover |
| TA/Eq | Leverage |

> 💡 **Why / Analogy:** ROE alone doesn't say WHY returns are high. DuPont peels back layers.

**📝 Worked Example:**
```
NI=100, EBT=133, EBIT=167, Rev=2000, TA=1500, Eq=600
ROE = .752×.796×.084×1.333×2.5 = 16.7%
RR=0.70 → g = 0.70×16.7% = 11.7%
```

**Key Points & Exam Traps:**
- Leverage ≠ Coverage ratios
- Payout + Retention = 1
- $FCFE = CFO - FCInv + \text{NetBorrowing}$

---

## Operating & Financial Leverage

### DOL, DFL & DCL

$$DOL = \frac{\%\Delta EBIT}{\%\Delta \text{Sales}} = \frac{S - VC}{S - VC - FC} = \frac{Q(P-V)}{Q(P-V)-FC}$$
$$DFL = \frac{\%\Delta EPS}{\%\Delta EBIT} = \frac{EBIT}{EBIT - \text{Interest}}$$
$$DCL = DOL \times DFL = \frac{Q(P-V)}{Q(P-V) - FC - \text{Interest}}$$
$$\text{Breakeven: } Q_{BE} = \frac{FC + \text{Interest}}{P - V}$$

**In Plain English:** DOL: how much does EBIT swing for a given sales swing — driven by fixed costs. DFL: how much does EPS swing for a given EBIT swing — driven by interest. DCL: both amplifications combined.

| Variable | Meaning |
|----------|---------|
| $S - VC$ | Contribution margin |
| $FC$ | Fixed costs (excludes interest) |
| $Q(P-V)$ | Total contribution |

> 💡 **Why / Analogy:** Fixed costs = operating leverage. Interest = financial leverage. Each is a multiplier on variability. Airlines (high DOL, high DFL) = very volatile EPS.

**📝 Worked Example:**
```
Q=1,000, P=$10, V=$6, FC=$2,000, Int=$500
DOL = 1,000×4 / (4,000−2,000) = 4,000/2,000 = 2.0x
DFL = 2,000 / (2,000−500) = 2,000/1,500 = 1.33x
DCL = 2.0 × 1.33 = 2.67x

Sales ↑10% → EBIT ↑20% → EPS ↑26.7%
```

**Key Points & Exam Traps:**
- DOL measured at current output level — changes as Q changes
- Higher fixed costs → higher DOL
- DOL > 1 always (unless FC=0)
- Operating breakeven: Q×(P−V) = FC
- Financial breakeven: EBIT = Interest

---

### Leverage & Coverage

$$D/E = Debt/Equity; \quad D/A = Debt/TA$$
$$\text{Interest Coverage} = EBIT / \text{Interest}$$
$$\text{Fixed Charge} = \frac{EBIT + Lease}{Int + Lease}$$

**In Plain English:** How much debt? Can the company cover fixed obligations?

| Variable | Meaning |
|----------|---------|
| Debt | Interest-bearing only |
| EBIT/Interest | Times interest earned |

> 💡 **Why / Analogy:** Leverage = caffeine. Great in moderation, dangerous in excess.

**📝 Worked Example:**
```
EBIT=200, Int=40, Lease=20
Int Coverage = 200/40 = 5.0x
Fixed Charge = 220/60 = 3.67x
```

**Key Points & Exam Traps:**
- Equity Multiplier = TA/Eq = 1 + D/E
- Higher coverage = more comfortable

---

## Intercorporate & Pensions

### Equity Method & Goodwill

$$\text{Investment} = \text{Purchase} + \%NI - \%Div - \text{AmortFV}$$
$$\text{Partial GW} = \text{FV consideration} - \%\text{FV net assets}$$
$$\text{Full GW} = \text{FV entity} - \text{FV net assets}$$
$$\text{Funded Status} = \text{FV Assets} - PV(DBO)$$
$$\text{Periodic Pension Cost} = \Delta\text{Funded Status} - \text{Contributions}$$

**In Plain English:** Equity method adjusts for income, dividends, amortization. GW = premium above identifiable assets.

| Variable | Meaning |
|----------|---------|
| + %NI | Share of investee income |
| − %Div | Reduces investment |
| − Amort | FV ÷ life |
| GW | Never amortized, tested annually |

> 💡 **Why / Analogy:** Own 30%: report 30% income, reduce by 30% dividends, amortize premium on identifiable assets.

**📝 Worked Example:**
```
30% for $600M. BV=$1500M, FV excess=$200M (10yr)
%BV=450; Excess=150; FV alloc=60(amort 6/yr); GW=90
Yr1: NI=200, Div=50
Inv = 600+60−15−6 = $639M

Pension: Assets=800, DBO=900 → FS=−100
```

**Key Points & Exam Traps:**
- IFRS impairment: 1 step; GAAP: 2 steps
- $NCI_{\text{full}} = \%\text{minority} \times \text{FV firm}$
- $NCI_{\text{partial}} = \%\text{minority} \times \text{FV net assets}$

---

## Pension Accounting

### PBO, Periodic Pension Cost & Funded Status

$$PBO_{end} = PBO_{beg} + \text{Service Cost} + \text{Interest Cost} + \text{Actuarial Gains/Losses} - \text{Benefits Paid}$$
$$\text{Interest Cost} = PBO_{beg} \times \text{Discount Rate}$$
$$\text{Periodic Pension Cost (P\&L)} = \text{Service Cost} + \text{Interest Cost} - \text{Expected Return on Assets} \pm \text{Amortisation}$$
$$\text{Funded Status} = \text{Plan Assets} - PBO$$
$$\text{Total Periodic Cost (economic)} = \text{Service Cost} + \text{Interest Cost} - \text{Actual Return on Assets}$$

**In Plain English:** PBO is the PV of all promised pension benefits. Funded status = assets minus obligations (positive = overfunded). P&L uses expected (not actual) asset returns; differences hit OCI.

| Variable | Meaning |
|----------|---------|
| Service Cost | PV of benefits earned this year |
| Interest Cost | PBO grows at the discount rate |
| Expected Return | Assumed long-run return on plan assets |
| OCI | Other comprehensive income (IFRS/GAAP differences) |

> 💡 **Why / Analogy:** Think of PBO as the company's pension "mortgage." Each year the mortgage grows (interest) and new obligations are added (service). Assets (savings account) offset it.

**📝 Worked Example:**
```
PBO_beg=$500M, discount=6%, service cost=$20M
Benefits paid=$15M, plan assets=$480M, exp return=7%
Interest cost = 500×6% = $30M
PBO_end = 500+20+30−15 = $535M
Funded status = 480−535 = −$55M (underfunded)
P&L charge = 20+30−0.07×480 = 50−33.6 = $16.4M
```

**Key Points & Exam Traps:**
- IFRS: uses net interest (discount rate × funded status); no expected return
- US GAAP: uses expected return separately
- Actuarial gains/losses go to OCI, amortised via corridor
- Analyst adjustment: use actual return; reclassify to get economic cost
- Underfunded pension = liability; overfunded = asset (but often restricted)

---

## Accrual Ratios & Earnings Quality

### Accrual Ratios (BS and CF Methods)

$$\text{NOA} = \text{Operating Assets} - \text{Operating Liabilities}$$
$$\text{Accrual Ratio (BS)} = \frac{NOA_{end} - NOA_{beg}}{(NOA_{end} + NOA_{beg})/2}$$
$$\text{Accrual Ratio (CF)} = \frac{NI - CFO - CFI}{(NOA_{end} + NOA_{beg})/2}$$
$$\text{CFO/NI Ratio} = CFO / NI$$
$$\text{CFO/Revenue} = CFO / \text{Revenue}$$

**In Plain English:** Accrual ratios measure how much of earnings is backed by cash. High accruals = low earnings quality (income recognised but cash not yet received). CFO/NI should be close to 1 for quality earnings.

| Variable | Meaning |
|----------|---------|
| NOA | Net Operating Assets (operating assets − operating liabilities) |
| Accrual ratio | Higher = more accruals, lower quality |
| CFO/NI | <1 = NI exceeds cash; >1 = quality |

> 💡 **Why / Analogy:** If revenue is booked but cash isn't collected, NOA swells (receivables rising). High accrual ratio = cash isn't following the reported earnings — a red flag.

**📝 Worked Example:**
```
NOA_beg=$200M, NOA_end=$260M, avg=$230M
NI=$50M, CFO=$30M, CFI=−$25M

Accrual(BS) = (260−200)/230 = 26.1% ← High! Red flag
Accrual(CF) = (50−30−(−25))/230 = 45/230 = 19.6%

CFO/NI = 30/50 = 0.60 ← Earnings not backed by cash
```

**Key Points & Exam Traps:**
- Lower accrual ratio = higher quality
- Rising DSO + rising accruals = revenue recognition concern
- Compare CFO/NI trend over time and vs peers
- Balance sheet method can be manipulated; CF method more robust

---

## Earnings Quality & Insurance

### Beneish M-Score

$$M = -4.84 + 0.920(DSR) + 0.528(GMI) + 0.404(AQI) + 0.892(SGI)$$
$$+ 0.115(DEPI) - 0.172(SGAI) + 4.679(\text{Accruals}) - 0.327(LEVI)$$

**In Plain English:** Manipulation detector. $M > -1.78$ → probable manipulation. Accruals coefficient highest (4.679).

| Variable | Meaning |
|----------|---------|
| DSR | Receivables vs Sales index |
| GMI | Gross Margin index |
| Accruals | $(NI - CFO) / TA$ |

> 💡 **Why / Analogy:** Each input is a red flag: receivables outpacing sales, margins falling, high accruals.

**📝 Worked Example:**
```
All 8 ratios → M = −1.62
−1.62 > −1.78 → ⚠️ Probable manipulation!
```

**Key Points & Exam Traps:**
- Accruals coefficient (4.679) = most important
- $b_1(CF) > b_2(\text{Accruals})$ → cash more persistent

---

### Earnings Persistence

$$E_{t+1} = a + b_1 E_t + \varepsilon$$
$$E_{t+1} = a + b_1 CF_t + b_2 \text{Accruals}_t + \varepsilon$$

**In Plain English:** First equation: higher $b_1$ = more persistent earnings. Second: if $b_1 > b_2$, cash flows are more persistent than accruals — a quality signal.

| Variable | Meaning |
|----------|---------|
| $b_1$ | Persistence coefficient (0–1) |
| $CF_t$ | Cash flow component |
| $\text{Accruals}_t$ | Accrual component |

> 💡 **Why / Analogy:** Cash is harder to manipulate than accruals. Companies with high accruals → earnings less repeatable.

**Key Points & Exam Traps:**
- High $b_1$ in eq 1 → earnings persistent, high quality
- $b_1 > b_2$ in eq 2 → cash beats accruals in persistence
- Accruals = $NI - CFO$; positive = potential red flag

---

### Altman Z-Score

$$Z = 1.2\frac{NWC}{TA} + 1.4\frac{RE}{TA} + 3.3\frac{EBIT}{TA} + 0.6\frac{MVE}{BVL} + 1.0\frac{Sales}{TA}$$

**In Plain English:** Bankruptcy prediction. > 2.99 safe, < 1.81 distress. EBIT/TA weighted most (3.3).

| Variable | Meaning |
|----------|---------|
| NWC/TA | Liquidity |
| EBIT/TA | Earning power (highest weight) |
| MVE/BVL | Market leverage |

> 💡 **Why / Analogy:** Five vital signs for corporate health.

**📝 Worked Example:**
```
NWC/TA=.15, RE/TA=.25, EBIT/TA=.12, MVE/BVL=1.5, S/TA=1.8
Z=0.18+0.35+0.396+0.90+1.80=3.63 → Safe ✓
```

**Key Points & Exam Traps:**
- > 2.99 safe
- 1.81–2.99 gray
- < 1.81 distress

---

### Insurance & CAMELS

$$\text{Combined} = \text{Loss Ratio} + \text{Expense Ratio}$$
$$CET1/RWA \geq 4.5\%; \quad Tier1 \geq 6\%; \quad Total \geq 8\%$$

**In Plain English:** Combined < 100% = profitable underwriting. [[CAMELS]] rates banks.

| Variable | Meaning |
|----------|---------|
| Loss Ratio | Claims / Net Premiums Earned |
| Expense Ratio | Expenses / Net Premiums Written |

> 💡 **Why / Analogy:** Combined under 100 = premiums exceed claims + expenses. Over 100 = underwriting loss.

**📝 Worked Example:**
```
Loss=68%, Expense=27%, Div=3%
Combined=95%; After div=98% → Profitable ✓
```

**Key Points & Exam Traps:**
- Loss ratio: premiums **EARNED**
- Expense ratio: premiums **WRITTEN**

---

# 🏢 Corporate Issuers

## Dividends & Repurchases

### Tax Rates & Payout Model

$$\text{DblTax: EffRate} = 1 - (1-T_c)(1-T_d)$$
$$\text{SplitRate: EffRate} = 1 - (1-T_{CL})(1-T_d)$$
$$\Delta D = (E \times \text{Target} - D_{\text{prev}}) \times \text{AdjFactor}$$
$$EPS_{\text{after}} = (\text{Earn} - \text{AT interest}) / \text{Shares}_{\text{after}}$$
$$BVPS_{\text{after}} = (Eq - \text{Buyback}) / (\text{Shares} - \text{Repurch})$$

**In Plain English:** Double tax hits corporate AND personal levels. [[Lintner model]] smooths dividends. Buyback accretive if E/P > AT borrowing cost.

| Variable | Meaning |
|----------|---------|
| $T_c$ | Corp tax on retained earnings |
| $T_{CL}$ | Corp tax on dividends (split-rate) |
| $T_d$ | Investor div tax |
| AdjFactor | 1 / years to adjust |

> 💡 **Why / Analogy:** Investors hate cuts → managers smooth dividends. Buyback: fewer shares (good) but less earnings (interest cost).

**📝 Worked Example:**
```
Tc=25%, Td=15%: 1−(.75)(.85) = 36.25%

E=$5, Target=40%, Dprev=$1.60, Adj=1/4
ΔD=(2.00−1.60)×.25=$0.10 → New D=$1.70

Buyback: Earn=$10M, P=$50, Borrow $5M@6%, T=30%
EPS_before=$5.00
EPS_after=(10M−210K)/1.9M=$5.15 → Accretive!
```

**Key Points & Exam Traps:**
- Accretive if $E/P > r_d(1-T)$
- BVPS ↓ if price > BVPS
- $\text{DivCoverage} = NI/Div$; $\text{FCFECov} = FCFE/(Div + Repurch)$

---

## Cost of Capital

### CAPM, FF5, Grinold-Kroner

$$\text{CAPM: } r_e = r_f + \beta(ERP)$$
$$\text{FF5: } r_e = r_f + \beta_1 ERP + \beta_2 SMB + \beta_3 HML + \beta_4 RMW + \beta_5 CMA$$
$$\text{Bond Yield+RP: } r_e = r_d + RP$$
$$\text{G-K: } ERP = DY + \text{Repricing} + \text{EPSgrowth} - E(r_f)$$

**In Plain English:** Single-factor, multi-factor, and supply-side approaches to [[Cost of Equity]].

| Variable | Meaning |
|----------|---------|
| SMB | Small − Big |
| HML | Value premium |
| RMW | Profitability |
| CMA | Investment |

> 💡 **Why / Analogy:** [[CAPM]] = one factor. [[Fama-French|FF5]] = five anomalies. [[Grinold-Kroner|G-K]] = observable market data.

**📝 Worked Example:**
```
CAPM: rf=3%, β=1.2, ERP=5% → rₑ=9%
FF5: +.3(2%)+.2(3%)+(−.1)(2.5%)+.15(2%)
   = 9+.6+.6−.25+.3=10.25%
```

**Key Points & Exam Traps:**
- Expanded CAPM: + size + specific premia
- Build-up: $r_f + ERP \pm$ premia

---

### WACC

$$WACC = w_d \cdot r_d(1-T) + w_p \cdot r_p + w_e \cdot r_e$$
$$w_d = \frac{MV_d}{MV_d + MV_p + MV_e}; \quad w_e = \frac{MV_e}{MV_d + MV_p + MV_e}$$

**In Plain English:** Weighted cost of all capital sources. After-tax because interest is deductible. Use market values, not book values, for weights.

| Variable | Meaning |
|----------|---------|
| $r_d(1-T)$ | After-tax cost of debt |
| $r_p$ | Cost of preferred: $D_p / P_p$ |
| $r_e$ | Cost of equity (CAPM/FF5/GK) |
| $w$ | Market value weights |

> 💡 **Why / Analogy:** The hurdle rate — any project must clear WACC to create value. Debt is cheaper than equity (tax shield) but too much debt → financial distress.

**📝 Worked Example:**
```
MV debt=$400M @6%, T=30%; MV pref=$100M @7%
MV equity=$500M, rₑ=12%
Total=$1,000M
WACC=.40×4.2% + .10×7% + .50×12%
    = 1.68% + 0.70% + 6.00% = 8.38%
```

**Key Points & Exam Traps:**
- Weights = market value (not book)
- Tax shield applies to debt only, not preferred
- If all equity: WACC = rₑ
- WACC = discount rate for FCFF models

---

### MM Propositions & Beta Levering

$$\text{MM I (no tax): } V_L = V_U$$
$$\text{MM I (with tax): } V_L = V_U + T \cdot D$$
$$\text{MM II (no tax): } r_e = r_0 + (r_0 - r_d)\frac{D}{E}$$
$$\text{MM II (with tax): } r_e = r_0 + (r_0 - r_d)(1-T)\frac{D}{E}$$
$$\beta_L = \beta_U \left[1 + (1-T)\frac{D}{E}\right]$$
$$\beta_U = \frac{\beta_L}{1 + (1-T)(D/E)}$$

**In Plain English:** With taxes, debt creates value via interest tax shield. As leverage rises, equity holders demand higher return (MM II). Beta levering adjusts for capital structure when using comparables.

| Variable | Meaning |
|----------|---------|
| $V_L / V_U$ | Levered / unlevered firm value |
| $T \cdot D$ | PV of tax shield |
| $r_0$ | Required return on unlevered equity |
| $\beta_L / \beta_U$ | Levered / unlevered beta |

> 💡 **Why / Analogy:** Adding debt = adding a gear. More gear = faster acceleration (returns) but also bigger crashes (risk). Tax shield is the government subsidising your debt.

**📝 Worked Example:**
```
VU=$500M, T=30%, D=$200M
VL = 500 + .30×200 = $560M

MM II: r₀=10%, rd=5%, D/E=1.0, T=30%
re = 10% + (10%−5%)(0.70)(1.0) = 13.5%

Beta levering:
βU=0.8, D/E=0.5, T=30%
βL = 0.8[1+0.70×0.5] = 0.8×1.35 = 1.08

Beta unlevering (using comp):
βL=1.2, D/E=0.6, T=25%
βU = 1.2/[1+0.75×0.6] = 1.2/1.45 = 0.828
```

**Key Points & Exam Traps:**
- Always unlever comp betas before relevering to target D/E
- MM with taxes: optimum = 100% debt (unrealistic; trade-off theory adds distress costs)
- Trade-off theory: optimal D/E where PV(tax shield) = PV(financial distress)
- Pecking order: internal → debt → equity (signals)

---

# 📈 Equity Valuation

## Dividend Discount Models

### GGM, H-Model, Perpetuity

$$\text{GGM: } V_0 = \frac{D_1}{r-g} = \frac{D_0(1+g)}{r-g}$$
$$\text{H: } V_0 = \frac{D_0(1+g_L) + D_0 H(g_S - g_L)}{r - g_L}$$
$$\text{Perpetuity: } V_0 = D/r$$
$$r = D_1/P_0 + g$$

**In Plain English:** [[GGM]] = constant growth forever. [[CFA_Glossary/H-model]] = declining growth shortcut. Perpetuity = no growth (preferred stock).

| Variable | Meaning |
|----------|---------|
| $D_1$ | Next dividend |
| $r$ | Required return |
| $g$ | Growth (must be < r) |
| $H$ | Half-life of high growth |

> 💡 **Why / Analogy:** If dividends grow at g forever, infinite sum simplifies to $D_1/(r-g)$. H-model shortcuts two-stage.

**📝 Worked Example:**
```
GGM: D₀=$2, g=5%, r=11%
V₀=2.10/0.06=$35 | r=2.10/35+.05=11% ✓

H: D₀=$1.50, gS=20%, gL=5%, r=12%, H=5
V₀=[1.575+1.125]/0.07=$38.57

Pref: D=$3.50, r=7% → V₀=$50
```

**Key Points & Exam Traps:**
- $g = RR \times ROE$ → see [[Sustainable Growth (PRAT)]]
- $g \leq$ GDP growth for GGM
- $g_S = g_L$ → H reduces to GGM

---

### Two-Stage & Three-Stage DDM

$$\text{2-stage: } V_0 = \sum_{t=1}^{n} \frac{D_0(1+g_S)^t}{(1+r)^t} + \frac{D_0(1+g_S)^n(1+g_L)}{(r-g_L)(1+r)^n}$$

$$\text{3-stage: } V_0 = \underbrace{\sum_{a=1}^{m} \frac{D_0(1+g_S)^a}{(1+r)^a}}_{\text{Stage 1}} + \underbrace{\sum_{b=m+1}^{n} \frac{D_0(1+g_S)^m(1+g_t)^{b-m}}{(1+r)^b}}_{\text{Stage 2}} + \underbrace{\frac{D_n(1+g_L)}{(r-g_L)(1+r)^n}}_{\text{Terminal}}$$

| Variable | Meaning |
|----------|---------|
| $g_S$ | Short-term (high) growth rate |
| $g_t$ | Transition growth rate |
| $g_L$ | Long-run stable growth rate |
| $n$ | End of forecast horizon |
| $m$ | End of stage 1 |

> 💡 **Why / Analogy:** Use when company growth > GDP in early years but must converge. H-Model approximates the declining-growth case; two-stage is exact.

**📝 Worked Example:**
```
2-stage: D₀=$2, gS=15%, gL=5%, r=10%, n=5
Stage1 PV = $2×1.15/1.10 + ... + $2×(1.15)⁵/(1.10)⁵ = $11.27
Terminal = $2×(1.15)⁵×1.05 / [(0.10−0.05)×(1.10)⁵] = $80.22
V₀ = 11.27 + 80.22 = $91.49
```

**Key Points & Exam Traps:**
- Use 2-stage when growth = 2 distinct phases; 3-stage when there's a transition
- $g > r$ in early stage is fine; GGM breaks only if $g \geq r$ forever
- Terminal value often dominates (80–90% of value)
- H-Model shortcuts the linear decline from $g_S$ to $g_L$

---

### PVGO & Justified Multiples

$$V_0 = E_1/r + PVGO$$
$$\text{Fwd P/E} = \frac{1-b}{r-g}$$
$$\text{Trail P/E} = \frac{(1-b)(1+g)}{r-g}$$
$$P/B = \frac{ROE - g}{r - g}$$
$$P/S = \frac{(E_0/S_0)(1-b)(1+g)}{r-g}$$
$$PEG = (P/E) / g$$

**In Plain English:** Value = no-growth + growth premium. Justified multiples from fundamentals.

| Variable | Meaning |
|----------|---------|
| $E_1/r$ | No-growth value |
| $PVGO$ | Growth premium |
| $1-b$ | Payout ratio |

> 💡 **Why / Analogy:** How much pays for growth? PVGO/V=80% → stock is 80% hope. PEG is quick & dirty.

**📝 Worked Example:**
```
E₁=$4, r=10%, g=6%, b=.40
D₁=4(.60)=$2.40; V₀=2.40/.04=$60
No-growth=4/.10=$40; PVGO=$20
Fwd P/E=.60/.04=15x
If B₀=$25: P/B=(16%−6%)/(10%−6%)=2.5x
```

**Key Points & Exam Traps:**
- PVGO < 0 → destroying value
- $ROE = r$ → $P/B = 1$
- Harmonic mean better for portfolio P/E

---

### Sustainable Growth (PRAT)

$$g = RR \times ROE$$
$$= \frac{NI-Div}{NI} \times \frac{NI}{Sales} \times \frac{Sales}{TA} \times \frac{TA}{Eq}$$

**In Plain English:** Growth from internal reinvestment. Combines retention with [[DuPont 5-Way & Sustainable Growth|DuPont ROE]].

| Variable | Meaning |
|----------|---------|
| $RR$ | Retention rate |
| $ROE$ | DuPont decomposition |

> 💡 **Why / Analogy:** How fast without new equity? Only as fast as you reinvest at your ROE.

**📝 Worked Example:**
```
NI=$100M, Div=$30M, Sales=$1000M, TA=$800M, Eq=$400M
RR=70%; ROE=.10×1.25×2.0=25%
g=.70×25%=17.5%
```

**Key Points & Exam Traps:**
- Higher retention → higher g (lower payout)
- If g > GDP → unsustainable

---

## FCF Valuation

### FCFF (4 Starting Points)

$$\text{NI: } FCFF = NI + NCC + Int(1-T) - FCInv - WCInv$$
$$\text{CFO: } FCFF = CFO + Int(1-T) - FCInv$$
$$\text{EBIT: } FCFF = EBIT(1-T) + Dep - FCInv - WCInv$$
$$\text{EBITDA: } FCFF = EBITDA(1-T) + Dep(T) - FCInv - WCInv$$
$$\text{Firm} = FCFF_1 / (WACC - g)$$

**In Plain English:** Cash for ALL investors. Add back after-tax interest. Subtract reinvestment.

| Variable | Meaning |
|----------|---------|
| NCC | Dep, amort |
| $Int(1-T)$ | Added back (FCFF is pre-financing) |
| FCInv | Capex |
| WCInv | ΔWC |

> 💡 **Why / Analogy:** Start anywhere on the IS, adjust to get cash for everyone. Add back interest because FCFF feeds debt + equity.

**📝 Worked Example:**
```
NI=$80M, Dep=$20M, Int=$15M, T=30%
FCInv=$35M, WCInv=$5M
FCFF=80+20+10.5−35−5=$70.5M
Firm(g=4%,WACC=9%)=70.5(1.04)/.05=$1,466M
```

**Key Points & Exam Traps:**
- Equity = Firm − MV Debt
- Two-stage: PV(explicit) + PV(terminal)
- Value = operating + non-operating assets

---

### FCFE (All Forms)

$$FCFE = NI + NCC - FCInv - WCInv + \text{NetBorr}$$
$$FCFE = CFO - FCInv + \text{NetBorr}$$
$$FCFE = EBIT(1-T) + Dep - FCInv - WCInv - Int(1-T) + \text{NetBorr}$$
$$FCFE = EBITDA(1-T) + Dep(T) - FCInv - WCInv - Int(1-T) + \text{NetBorr}$$
$$FCFE = NI - (1-DR)(FCInv - Dep) - (1-DR) \cdot WCInv$$
$$\text{Equity} = FCFE_1 / (r - g)$$

**In Plain English:** Cash for equity only. DR version assumes target capital structure.

| Variable | Meaning |
|----------|---------|
| $DR$ | Target debt ratio |
| $(1-DR)$ | Equity's share of financing |
| NetBorr | New debt − repayments |

> 💡 **Why / Analogy:** FCFE = take-home for shareholders. DR version great for forecasting.

**📝 Worked Example:**
```
NI=$80M, Dep=$20M, FCInv=$35M, WCInv=$5M, DR=40%
FCFE=80−.60(15)−.60(5)=$68M
Equity(r=11%,g=4%)=68(1.04)/.07=$1,010M
```

**Key Points & Exam Traps:**
- Discount at $r$ ([[Cost of Equity]]) not [[WACC]]
- If div = FCFE → [[GGM, H-Model, Perpetuity|DDM]] = FCFE model

---

## Multiples & Residual Income

### EV/EBITDA & Variants

$$EV = MV_e + MV_d + MV_{\text{pref}} - Cash$$
$$\text{EV/EBITDA, EV/EBIT, EV/Sales, EV/FCFF}$$
$$V_n = \text{benchmark P/E} \times E_n \text{ (terminal)}$$
$$SUE = \frac{EPS_t - E(EPS_t)}{\sigma}$$
$$\text{Norm EPS (avg)} = \frac{\sum EPS_i}{n}$$
$$\text{Norm EPS (ROE)} = \frac{\sum ROE_i}{n} \times BVPS_n$$
$$X_H = \frac{n}{\sum(1/X_i)}; \quad X_{WH} = \frac{1}{\sum(w_i/X_i)}$$

**In Plain English:** EV = total cost to buy business. EV multiples are capital-structure neutral. [[SUE]] = momentum indicator.

| Variable | Meaning |
|----------|---------|
| EV | Equity + debt − cash |
| SUE | Standardized unexpected earnings |
| $X_H$ | Harmonic mean |
| $X_{WH}$ | Weighted harmonic mean |

> 💡 **Why / Analogy:** EV captures what you pay (equity), assume (debt), and get back (cash). Better than P/S for cross-structure comparison.

**📝 Worked Example:**
```
MVe=$500M, MVd=$200M, Cash=$50M, EBITDA=$100M
EV=650M; EV/EBITDA=6.5x

Momentum: EPS=$2.10, E(EPS)=$1.90, σ=$0.15
SUE=(2.10−1.90)/0.15=1.33 (positive surprise)
```

**Key Points & Exam Traps:**
- EV/EBITDAR adds rent (airlines, retail)
- Use harmonic mean ($X_H$) for portfolio P/E — reduces large-multiple bias
- Norm EPS (avg ROE) adjusts for size changes; use only if BV makes sense
- Unexpected earnings: $UE_t = EPS_t - E(EPS_t)$

---

### Residual Income Model

$$V_0 = B_0 + \sum \frac{(ROE_t - r) \cdot B_{t-1}}{(1+r)^t}$$
$$\text{Single: } V_0 = B_0 + \frac{(ROE - r)}{r - g} \cdot B_0$$
$$EVA = NOPAT - WACC \times TC$$
$$MVA = MV - BV$$

**In Plain English:** Value = book + PV of excess returns. If ROE > r → premium. [[EVA]] = economic profit.

| Variable | Meaning |
|----------|---------|
| $B_0$ | Book value |
| $ROE - r$ | Spread |
| $\omega$ | Persistence (0 to 1) |
| $NOPAT$ | $EBIT(1-T)$ |

> 💡 **Why / Analogy:** Does company create value above cost of capital? ROE > r → premium over book. ROE < r → discount.

**📝 Worked Example:**
```
B₀=$25, ROE=18%, r=12%, g=4%
V₀=25+[.06/.08]×25=25+18.75=$43.75
P/B=43.75/25=1.75x ✓

EVA: NOPAT=$50M, TC=$400M, WACC=10%
EVA=50−40=$10M → creating value
```

**Key Points & Exam Traps:**
- $\omega = 1$ → RI forever; $\omega = 0$ → RI stops
- $B_t = B_{t-1} + E_t - D_t$
- Multi-stage: explicit RI + $(P_T - B_T)/(1+r)^T$

---

### Private Company

$$EE = \text{Earnings} - r_{WC}(WC) - r_{FA}(FA)$$
$$V_{\text{intg}} = \frac{EE(1+g)}{r_{\text{intg}} - g}$$
$$V_f = WC + FA + V_{\text{intg}}$$
$$DLOC = 1 - \frac{1}{1 + \text{Control Premium}}$$
$$\text{Expanded CAPM: } r_f + \beta \cdot ERP + \text{size} + \text{specific}$$

**In Plain English:** Excess earnings method for intangibles. [[DLOC]]/[[DLOM]] for minority/illiquidity discounts.

| Variable | Meaning |
|----------|---------|
| $EE$ | Excess earnings |
| $DLOC$ | Lack of control discount |
| $MVIC$ | $MV_e + MV_d$ |

> 💡 **Why / Analogy:** Strip away tangible asset returns. Whatever's left = intangible value. Discount for control/marketability.

**📝 Worked Example:**
```
Earn=$500K, WC=$200K@5%, FA=$800K@8%
EE=500−10−64=$426K
Vintg=426(1.03)/(15%−3%)=$3,657K
Vf=200+800+3657=$4,657K

Control prem=25%: DLOC=1−1/1.25=20%
```

**Key Points & Exam Traps:**
- MVIC/EBITDA key multiple
- Total disc = $1 - (1-DLOC)(1-DLOM)$
- Guideline: Comp MVIC/EBITDA × Norm EBITDA − Debt

---

# 🏦 Fixed Income

## Term Structure

### Discount Factors & Forward Rates

$$DF_N = \frac{1}{(1+z_N)^N}$$
$$(1+z_B)^B = (1+z_A)^A \cdot (1+f(A,B-A))^{B-A}$$
$$DF_B = DF_A \times F(A,B-A)$$
$$\text{Swap Spread} = \text{Corp} - \text{Treasury}$$

**In Plain English:** Spot rates price zeros. Forward rates link spots via no-arbitrage.

| Variable | Meaning |
|----------|---------|
| $z_N$ | N-year spot |
| $f(A,B-A)$ | Forward rate |
| $DF$ | PV of $1 |

> 💡 **Why / Analogy:** Investing 3yr directly must equal 1yr then 2yr forward. Otherwise free money.

**📝 Worked Example:**
```
z₁=3%, z₂=3.5% → f(1,1):
(1.035)²=(1.03)(1+f)
f=1.07123/1.03−1=4.003%
DF₁=0.9709; DF₂=0.9335
```

**Key Points & Exam Traps:**
- [[CFA_Glossary/Z-spread]]: added to curve to match price
- TED = 3mo MRR − 3mo T-bill
- SWAPS+ = Treasury + swap spread

---

## Bond Pricing & Yield Measures

### Bond Price, Accrued Interest & Yields

$$P = \sum_{t=1}^{N} \frac{C/m}{(1+y/m)^t} + \frac{FV}{(1+y/m)^N}$$
$$\text{Full Price} = \text{Flat Price} + AI; \quad AI = C \times \frac{t}{T}$$
$$\text{Current Yield} = \frac{\text{Annual Coupon}}{P}$$
$$\text{BEY} = 2 \times y_{\text{semi}}; \quad y_{\text{semi}} = \left(1 + y_{\text{annual}}\right)^{0.5} - 1$$
$$\text{YTM} = m \times \left[\left(\frac{FV + C/m}{P}\right)^{1/N} - 1\right] \text{ (approx)}$$

**In Plain English:** Bond price = PV of all coupons + PV of face. Full price is what you pay; flat price is quoted. BEY converts annual to semi-annual basis.

| Variable | Meaning |
|----------|---------|
| $C/m$ | Periodic coupon ($m$ = periods/year) |
| $y/m$ | Periodic yield |
| $t/T$ | Days since last coupon / days in period |
| $AI$ | Accrued interest |

> 💡 **Why / Analogy:** Flat price quoted to avoid jumps on coupon dates. Full price is actual cash exchanged. Premium bond: coupon > YTM. Discount bond: coupon < YTM.

**📝 Worked Example:**
```
$1,000 par, 6% semi, 3 yr, YTM=5%
P = 30/1.025 + 30/1.025² + ... + 1030/1.025⁶ = $1,027.59

AI (60 days into 180-day period):
AI = 30 × (60/180) = $10.00; Flat = $1,017.59
```

**Key Points & Exam Traps:**
- Coupon > YTM → price > par (premium)
- Coupon < YTM → price < par (discount)
- At maturity, price always pulls to par
- BEY not same as EAY: BEY assumes reinvestment at same rate

---

## Duration & Convexity

### MacD, ModD, Dollar Duration & DV01

$$MacD = \frac{\sum_{t=1}^{N} t \times PV(CF_t)}{P}$$
$$ModD = \frac{MacD}{1 + y/m}$$
$$\%\Delta P \approx -ModD \times \Delta y$$
$$\text{Dollar Dur} = ModD \times P \times 0.01$$
$$DV01 = ModD \times P \times 0.0001$$
$$\text{Money Dur} = ModD \times \text{Full Price}$$

**In Plain English:** MacD = weighted-average time to receive cash flows (in years). ModD = sensitivity: a 1% yield change → roughly ModD% price change. DV01 = price change per 1bp.

| Variable | Meaning |
|----------|---------|
| $MacD$ | Macaulay Duration (years) |
| $ModD$ | Modified Duration |
| $DV01$ | Dollar Value of 1 basis point |
| $\Delta y$ | Yield change (decimal) |

> 💡 **Why / Analogy:** Duration = average repayment time. A 5-year ModDur bond loses ~5% price for each 1% yield rise. DV01 = the dollar cost of being wrong by 1bp.

**📝 Worked Example:**
```
Bond: P=$1,027.59, ModD=2.78, y=5%
%ΔP ≈ −2.78 × 0.01 = −2.78%
ΔP ≈ −$28.57

DV01 = 2.78 × 1,027.59 × 0.0001 = $0.286/bp
Dollar Dur = 2.78 × 1,027.59 × 0.01 = $28.57/$1 move
```

**Key Points & Exam Traps:**
- Zero coupon: MacD = maturity exactly
- Higher coupon → lower duration (cash flows front-loaded)
- Higher yield → lower duration
- Callable: effective dur ≤ straight dur (call caps price upside)
- Portfolio duration = weighted avg of individual durations

---

### Convexity & Full Price Change

$$Cvx = \frac{P_- + P_+ - 2P_0}{P_0 \times (\Delta y)^2}$$
$$\%\Delta P \approx -ModD \times \Delta y + \frac{1}{2} \times Cvx \times (\Delta y)^2$$
$$\text{EffCvx} = \frac{PV_- + PV_+ - 2PV_0}{PV_0 \times (\Delta \text{curve})^2}$$

**In Plain English:** Duration is linear; convexity corrects for the curve. A bond with more convexity gains more than duration predicts when yields fall, and loses less than predicted when yields rise. Always a benefit.

| Variable | Meaning |
|----------|---------|
| $P_-/P_+$ | Price when yield falls/rises by $\Delta y$ |
| $Cvx$ | Convexity (positive for option-free) |
| Callable | Negative convexity at low yields |

> 💡 **Why / Analogy:** Duration is the speedometer; convexity is acceleration. Both give you a better picture of the ride.

**📝 Worked Example:**
```
P₀=$1,000, P₋=$1,085, P₊=$921, Δy=0.01
Cvx = (1,085 + 921 − 2,000) / (1,000 × 0.0001)
    = 6/0.1 = 60

ModD=8, Δy=−2%:
%ΔP ≈ −8×(−.02) + ½×60×(.02)² = 16% + 1.2% = 17.2%
```

**Key Points & Exam Traps:**
- Convexity always positive for option-free bonds
- Callable → negative convexity when rates low (call caps upside)
- Putable → more convexity than straight
- Larger convexity = better for any large rate move

---

## Spreads & Credit Risk

### Nominal, G, I, Z, OAS Spreads

$$\text{Nominal Spread} = YTM_{\text{corp}} - YTM_{\text{Treasury}}$$
$$\text{G-spread} = YTM - \text{interpolated Treasury yield}$$
$$\text{I-spread} = YTM - \text{swap rate (same maturity)}$$
$$\text{Z-spread: } P = \sum \frac{CF_t}{(1 + z_t + ZS)^t}$$
$$\text{OAS} = Z\text{-spread} - \text{option value (in bps)}$$
$$\text{Callable: } OAS = ZS - \text{call value}; \quad \text{Putable: } OAS = ZS + \text{put value}$$

**In Plain English:** Spreads measure extra yield above a benchmark for credit, liquidity, or optionality. OAS strips out the option to isolate pure credit + liquidity.

| Variable | Meaning |
|----------|---------|
| Z-spread | Constant spread over spot curve |
| OAS | Option-Adjusted Spread (pure credit) |
| Option value | In bps, embedded in bond price |

> 💡 **Why / Analogy:** If ZS=150bp and the call option = 30bp, OAS=120bp. That 120bp is the "true" spread for credit risk.

**📝 Worked Example:**
```
Callable bond: Z-spread = 180bp, call value = 40bp
OAS = 180 − 40 = 140bp

Putable bond: Z-spread = 100bp, put value = 25bp
OAS = 100 + 25 = 125bp

G-spread: Corp YTM=5.2%, 5yr Treasury=3.8%
G-spread = 140bp
```

**Key Points & Exam Traps:**
- Higher OAS → cheaper relative to model value
- OAS removes optionality → valid for cross-bond comparison
- Callable: ZS > OAS (option costs the investor)
- Putable: ZS < OAS (put benefits the investor)
- CVA = $\sum PD_t \times LGD_t \times DF_t$ (credit valuation adjustment)

---

## Embedded Options

### Callable/Putable/Convertible

$$V_{\text{call}} = V_{\text{straight}} - V_{\text{callable}}$$
$$V_{\text{put}} = V_{\text{putable}} - V_{\text{straight}}$$
$$\text{EffDur} = \frac{PV_- - PV_+}{2 \times \Delta\text{Curve} \times PV_0}$$
$$\text{ConvValue} = \text{Price} \times \text{ConvRatio}$$
$$\text{MinValue} = \max(\text{ConvValue}, \text{StraightValue})$$

**In Plain English:** Call → issuer benefit → lower price. Put → investor benefit → higher price. [[CFA_Glossary/Effective duration|EffDur]] handles optionality.

| Variable | Meaning |
|----------|---------|
| $PV_- / PV_+$ | Prices when curve shifts |
| ConvRatio | Par / ConvPrice |
| MktConvPrice | BondPrice / ConvRatio |

> 💡 **Why / Analogy:** Callable = landlord can evict (less rent). Putable = you can leave (more rent). Convertible = bond floor + stock upside.

**📝 Worked Example:**
```
PV₀=102, PV₋=105.5, PV₊=99, ΔCurve=50bp
EffDur=(105.5−99)/(2×.005×102)=6.37

Par=$1000, ConvP=$40, Share=$45, Bond=$1150
Ratio=25; ConvVal=$1125
MktConvP=$46; Premium=$1/sh
```

**Key Points & Exam Traps:**
- ↑ vol → ↑ call & put values
- $ED(\text{callable}) \leq ED(\text{straight})$
- Capped floater = straight − cap
- Floored floater = straight + floor

---

## Credit & CDS

### CDS & Credit Migration

$$\text{Upfront} \approx (\text{Spread} - \text{Coupon}) \times \text{Duration}$$
$$\text{Profit} \approx \Delta\text{Spread} \times \text{Duration} \times \text{Notional}$$
$$\text{ExpLoss} = PD \times LGD; \quad LGD = 1 - \text{Recovery}$$
$$\%\Delta P \approx -\text{ModDur} \times \Delta\text{Spread}$$

**In Plain English:** [[CDS]] buyer pays upfront if spread > coupon. Profits when spreads widen. Migration: ΔP ≈ −dur × Δspread.

| Variable | Meaning |
|----------|---------|
| Spread | Current CDS spread |
| Coupon | Fixed (100 or 500bp) |
| LGD | Loss Given Default |

> 💡 **Why / Analogy:** CDS = bond insurance. Standardized coupons; upfront adjusts for current risk.

**📝 Worked Example:**
```
Spread=350bp, Coupon=100bp, Dur=4.5, Not=$10M
Upfront=.025×4.5=11.25%=$1.125M

Spread→400bp: Profit=.005×4.5×10M=$225K

Migration BBB→BB: Δspread=80bp, dur=5
%ΔP≈−5×.008=−4.0%
```

**Key Points & Exam Traps:**
- Buyer profits when spreads widen
- Structural: equity ≈ call on assets
- $CVA = \Sigma PV(\text{expected losses})$

---

# ⚡ Derivatives

## Forwards & FRA

### Forward Price, Value & FRA

$$F_0 = FV[S_0 + CC - CB] = S_0 e^{(r+CC-CB)T}$$
$$V_t = \frac{F_t - F_0}{(1+r)^{T-t}}$$
$$\text{Equity: } F_0 = (S_0 - PVD)(1+r)^T \text{ or } S_0 e^{(r-\delta)T}$$
$$FRA_0 = \left\{\frac{(1+L_T \cdot t_T)}{(1+L_h \cdot t_h)} - 1\right\} / t_m$$
$$\text{Settle} = \frac{NA(\text{float} - \text{fixed})(d/360)}{1 + \text{float}(d/360)}$$

**In Plain English:** Forward = spot compounded + carry. [[FRA]] = implied forward rate. Settle at loan START (discount at floating).

| Variable | Meaning |
|----------|---------|
| CC/CB | Carry costs/benefits |
| PVD | PV dividends |
| $\delta$ | Continuous div yield |

> 💡 **Why / Analogy:** Forward price is cost-of-carry, NOT a forecast. FRA locks future borrowing rate.

**📝 Worked Example:**
```
S₀=$100, r=5%, δ=2%, T=0.5
F₀=100e^(.03)(.5)=$101.51

3×6 FRA: 90d=3%, 180d=3.5%
FRA={(1.0175/1.0075)−1}/.25=3.968%
Settle(rate=4.5%): $1,315
```

**Key Points & Exam Traps:**
- Value = 0 at initiation
- FI: $Q_0 = [(S_0 + AI)(1+r)^T - AI - FVC]/CF$
- CTD = $\min[S_T - Q_T \times CF]$

---

## Swaps

### IRS, Currency & Equity Swaps

$$PMT = \frac{1 - DF_n}{\Sigma DF}$$
$$\text{IRS: } V = (r_{\text{fix}_0} - r_{\text{fix}_t}) \times \Sigma DF \times NA$$
$$\text{Currency: } V = V_D - S(d/f) \times V_F$$
$$\text{Equity (rcvFix): } V = NA(r_{fx} \cdot \Sigma DF + DF_n) - (S_t/S_0) \cdot NA$$
$$\text{Currency (cont): } F = Se^{(r_f - r_d)T}$$

**In Plain English:** Swap rate makes fixed = floating at inception. Value after = rate difference × sum DFs × notional.

| Variable | Meaning |
|----------|---------|
| $DF_n$ | Final DF |
| $\Sigma DF$ | Sum all DFs |
| $r_{\text{fix}_0/t}$ | Original/current rate |

> 💡 **Why / Analogy:** At inception swap = 0. Fixed rate = par coupon. Rates move → one side gains.

**📝 Worked Example:**
```
Quarterly DFs: .9804, .9610, .9418, .9231
ΣDF=3.8063; PMT=(1−.9231)/3.8063=2.021%/qtr

New rate=2.2%/qtr, ΣDF'=1.92, NA=$10M
V_rcvFix=(2.021%−2.2%)×1.92×10M=−$34,368
```

**Key Points & Exam Traps:**
- EqSwap resets: $V = V_{FIX} - (S_t/S_{t-1}) \times NA_E$
- Currency: exchange notionals
- PayFixed = −ReceiveFixed

---

## Options

### Binomial Model

$$\pi = \frac{(1+r) - d}{u - d}$$
$$\Delta = \frac{c^+ - c^-}{S^+ - S^-}$$
$$c = \frac{\pi c^+ + (1-\pi)c^-}{1+r}$$
$$\text{2-pd: } c = \frac{\pi^2 c^{++} + 2\pi(1-\pi)c^{+-} + (1-\pi)^2 c^{--}}{(1+r)^2}$$

**In Plain English:** Risk-neutral pricing: find π, expected payoff, discount at rf. Δ = hedge ratio.

| Variable | Meaning |
|----------|---------|
| $\pi$ | Risk-neutral up prob |
| $u/d$ | Up/down factors |
| $\Delta$ | Shares per option |

> 💡 **Why / Analogy:** Hedge makes option riskless → discount at rf. π are math weights, not real probabilities.

**📝 Worked Example:**
```
S=100, u=1.15, d=.87, r=3%, X=105
c⁺=max(115−105,0)=10; c⁻=0
π=(.16/.28)=.5714
c=[.5714(10)]/1.03=$5.55
Δ=10/28=0.357
```

**Key Points & Exam Traps:**
- American: check early exercise each node
- Put Δ always negative
- 2-period expands the tree

---

### BSM, Black & Swaptions

$$\text{BSM: } c = SN(d_1) - e^{-rT}XN(d_2)$$
$$p = e^{-rT}XN(-d_2) - SN(-d_1)$$
$$\text{Black (futures): } c = e^{-rT}[F_0 N(d_1) - XN(d_2)]$$
$$\text{Black (IR): } c = NP[FRA \cdot N(d_1) - X_r \cdot N(d_2)]e^{-rT}$$
$$\text{PaySWN} = [R_{\text{fix}} \cdot N(d_1) - X_r \cdot N(d_2)] \times PVA$$
$$N_H = -\text{Portfolio}\Delta / \Delta_H$$

**In Plain English:** [[BSM]] = continuous-time. [[Black Model|Black]] = for futures/rates. [[Swaptions]] = options on swaps.

| Variable | Meaning |
|----------|---------|
| $N(d_1)$ | ≈ call delta |
| $N(d_2)$ | ≈ prob exercise |
| PVA | Annuity for swaptions |

> 💡 **Why / Analogy:** BSM = [[Binomial Model|binomial]] with infinitely small steps. Black adapts it for futures and interest rates.

**📝 Worked Example:**
```
BSM: S=42, X=40, r=5%, σ=30%, T=0.5
d₁=0.454, d₂=0.242
c=42(.675)−40e⁻·⁰²⁵(.596)=$5.10
p=40(.9753)(.404)−42(.325)=$2.11

Swaption: Rfix=3.5%, Xr=3%, PVA=4.2, NA=$10M
PaySWN=[.035(.802)−.03(.742)]×42M=$244K
```

**Key Points & Exam Traps:**
- Cap = series of caplets; Floor = floorlets
- Long floor + short cap = receive-fixed swap
- $\Delta C \approx \delta \times \Delta S + \frac{1}{2}\gamma \times \Delta S^2$

---

## Put-Call Parity

### Put-Call Parity & Synthetic Positions

$$c + PV(X) = p + S_0 \quad \text{(European, no dividends)}$$
$$c - p = S_0 - PV(X) = PV(F_0 - X) \quad \text{(forward-based)}$$
$$c + PV(X) = p + S_0 - PVD \quad \text{(with dividends)}$$
$$c = p + S_0 - PV(X) \quad \text{(solve for call)}$$
$$p = c - S_0 + PV(X) \quad \text{(solve for put)}$$

**In Plain English:** Long call + cash = long put + stock. If this breaks, arbitrage exists. Every position has a synthetic equivalent.

| Variable | Meaning |
|----------|---------|
| $PV(X)$ | PV of strike = $X \cdot e^{-rT}$ |
| $PVD$ | PV of dividends over life |
| $F_0$ | Forward price |

> 💡 **Why / Analogy:** Two ways to get "stock with downside protection": (1) own stock + put, or (2) own call + cash. Must cost the same.

**📝 Worked Example:**
```
S=$50, X=$50, r=5%, T=1, c=$5
PV(X) = 50/1.05 = $47.62
p = c − S + PV(X) = 5 − 50 + 47.62 = $2.62

If p quoted at $3.50: p too expensive
Arb: sell put, buy call, sell stock, invest PV(X)
```

**Key Points & Exam Traps:**
- Applies to European options only (American: $c \geq p + S - X$ for calls)
- Forward PCP: $c - p = PV(F_0 - X)$ → if $F_0 = X$, ATM call = ATM put
- Synthetics: long forward = long call + short put (same strike/expiry)

---

## Option Greeks

### Delta, Gamma, Theta, Vega, Rho

$$\Delta_c = N(d_1); \quad \Delta_p = N(d_1) - 1$$
$$\Gamma = \frac{\partial^2 C}{\partial S^2} > 0 \text{ (for long options)}$$
$$\text{Hedge ratio: } N_H = -\frac{\Delta_{\text{portfolio}}}{\Delta_{\text{option}}}$$
$$\%\Delta P \approx \delta \cdot \Delta S + \frac{1}{2}\gamma \cdot (\Delta S)^2$$
$$\text{Theta} < 0 \text{ (long options lose time value daily)}$$
$$\text{Vega} > 0 \text{ (long options gain from higher volatility)}$$
$$\text{Rho: calls positive, puts negative (higher } r \text{ → higher call)}$$

**In Plain English:** Delta = sensitivity to stock price. Gamma = how delta changes. Theta = time decay. Vega = volatility sensitivity. Rho = interest rate sensitivity.

| Greek | Call | Put | Notes |
|-------|------|-----|-------|
| Delta $\delta$ | 0 to 1 | −1 to 0 | = N(d₁) from BSM |
| Gamma $\gamma$ | Positive | Positive | Largest ATM |
| Theta | Negative | Negative | Decay accelerates near expiry |
| Vega | Positive | Positive | Largest ATM, long-dated |
| Rho | Positive | Negative | Small effect |

> 💡 **Why / Analogy:** Delta is speed, gamma is acceleration. A deep ITM call has Δ≈1 (moves like stock); deep OTM has Δ≈0. Gamma is highest at-the-money where delta is most uncertain.

**📝 Worked Example:**
```
BSM: S=50, X=50, δ=0.60, γ=0.04, Θ=−0.02/day
If S rises $1: ΔC ≈ 0.60×1 + ½×0.04×1 = $0.62
If S rises $5: ΔC ≈ 0.60×5 + ½×0.04×25 = $3.50

Delta hedge: Portfolio Δ=−500; option Δ=0.60
NΗ = −(−500)/0.60 = 833 calls to buy
```

**Key Points & Exam Traps:**
- Long call: Δ positive; long put: Δ negative
- Delta neutral ≠ gamma neutral — need different instruments
- Short option: negative gamma → exposure to large moves
- Vega is NOT a Greek letter mathematically but treated as one

---

# 🏠 Alternatives

## Commodities

### Total Return

$$\text{Total} = \text{Price} + \text{Roll} + \text{Collateral}$$
$$\text{Roll} = \frac{P_{\text{near}} - P_{\text{far}}}{P_{\text{near}}} \times \%\text{rolled}$$
$$\text{Futures} = \text{Spot} + \text{Storage} - \text{ConvYield}$$

**In Plain English:** Three sources: price change, rolling cost/benefit, interest on collateral.

| Variable | Meaning |
|----------|---------|
| Roll | Gain/loss from switching contracts |
| Collateral | T-bill rate on margin |

> 💡 **Why / Analogy:** [[Backwardation]] (far < near) = positive roll. [[Contango]] (far > near) = negative roll.

**📝 Worked Example:**
```
Near=$75, Far=$77 (contango)
Roll=(75−77)/75=−2.67%
Price: 73→75=+2.74%; Collateral=1%
Total=2.74−2.67+1.0=1.07%
```

**Key Points & Exam Traps:**
- Contango = negative roll
- Backwardation = positive roll

---

## Real Estate

### Direct Cap, DCF & Metrics

$$\text{Value} = NOI / \text{CapRate}; \quad \text{CapRate} = r - g$$
$$DSCR = NOI / \text{DebtService} \quad (\geq 1.2)$$
$$LTV = Loan / Value$$
$$\text{Terminal} = NOI_{\text{term}} / \text{TermCapRate}$$
$$\text{EqDivRate} = (NOI - DS) / Equity$$

**In Plain English:** Cap rate = yield minus growth. [[NOI]] excludes interest/taxes. DSCR measures debt coverage.

| Variable | Meaning |
|----------|---------|
| NOI | Rental income − OpEx |
| CapRate | $r - g$ or NOI/SalePrice |
| Terminal | Typically > going-in |

> 💡 **Why / Analogy:** [[GGM, H-Model, Perpetuity|GGM]] for real estate. Low cap = high growth. Terminal cap > going-in (older property).

**📝 Worked Example:**
```
NOI=$510K, r=9%, g=2%
Cap=7%; Value=510K/.07=$7.286M
Loan=$5M; DSCR=510K/400K=1.275 ✓
LTV=5M/7.286M=68.6%
Equity=$2.286M; CF=$110K
EqDiv=110K/2.286M=4.81%
```

**Key Points & Exam Traps:**
- Leveraged IRR: PV=−Eq, PMT=CF, FV=Sale−Mortgage
- Unleveraged: PV=−Price, PMT=NOI, FV=Sale

---

### REIT: NAV, FFO, AFFO

$$FFO = NI + Dep + \text{DefTax} + Losses - Gains$$
$$AFFO = FFO - \text{NonCashRent} - \text{MaintCapex}$$
$$NAVPS = \frac{\text{EstREValue} + \text{OtherAssets} - \text{Liab}}{Shares}$$

**In Plain English:** [[FFO]] adds back depreciation (RE appreciates). [[AFFO]] subtracts maintenance for truer cash flow.

| Variable | Meaning |
|----------|---------|
| FFO | NI adjusted for RE items |
| AFFO | More conservative |
| NAV | Liquidation value |

> 💡 **Why / Analogy:** RE depreciation is accounting fiction. FFO shows true cash generation. AFFO = what you need to maintain buildings.

**📝 Worked Example:**
```
NI=$50M, Dep=$30M, DefTax=$2M, Gain=$5M
FFO=50+30+2−5=$77M
NonCashRent=$3M, Maint=$8M
AFFO=$66M; Shares=20M
At P=$60: P/FFO=15.6x; P/AFFO=18.2x
```

**Key Points & Exam Traps:**
- NonCash rent = straight-line − cash
- NAV: NOI/cap + assets − liabilities

---

## Hedge Funds

### Conditional Factor Model

$$R_{HF,t} = \alpha + \beta(ERP)_t + D_t \beta'(ERP)_t$$

**In Plain English:** Dummy lets beta change in bear markets — captures asymmetric exposure.

| Variable | Meaning |
|----------|---------|
| $\alpha$ | Skill |
| $\beta$ | Normal beta |
| $D\beta'$ | Bear market shift |

> 💡 **Why / Analogy:** HFs may hedge only in downturns. This captures that asymmetry.

**📝 Worked Example:**
```
α=2%, β=0.4, Dβ'=0.3
Bear(D=1,ERP=−15%): R=2+.4(−15)+.3(−15)=−8.5%
Bull(D=0,ERP=12%): R=2+.4(12)=6.8%
Bear β=0.4+0.3=0.7
```

**Key Points & Exam Traps:**
- HF alloc: ↓σ, ↑Sharpe
- FoF: netting risk
- Multi-strat: better fees vs FoF

---

## Private Equity Multiples

### MOIC, DPI, RVPI, TVPI & Carried Interest

$$MOIC = \frac{\text{Total Value (Distributions + NAV)}}{\text{Invested Capital}}$$
$$DPI = \frac{\text{Cumulative Distributions}}{\text{Paid-In Capital}}$$
$$RVPI = \frac{\text{Residual NAV}}{\text{Paid-In Capital}}$$
$$TVPI = DPI + RVPI = \frac{\text{Distributions} + \text{NAV}}{\text{Paid-In Capital}}$$
$$\text{Carried Interest} = \text{Carry\%} \times (\text{Profits above hurdle})$$
$$\text{Management Fee} = \text{Fee\%} \times \text{Committed (or Invested) Capital}$$

**In Plain English:** TVPI measures total value created per dollar invested. DPI = realised; RVPI = unrealised. IRR is time-weighted; MOIC is not (ignores timing).

| Multiple | Meaning | >1 means |
|----------|---------|---------|
| DPI | Cash returned / invested | Has returned more than invested |
| RVPI | Remaining value / invested | Unrealised upside |
| TVPI | Total value / invested | Total return multiple |
| MOIC | Total value / cost basis | Same as TVPI (gross) |

> 💡 **Why / Analogy:** TVPI=2.5x means every $1 invested became $2.50. But 2.5x in 3 years is better than 2.5x in 10 years — that's where IRR adds the time dimension.

**📝 Worked Example:**
```
Committed=$100M, invested=$80M, carry=20%, hurdle=8%
Distributions to date=$60M, current NAV=$75M
Management fee (2% of committed) = $2M/yr

DPI = 60/80 = 0.75x (not yet returned capital)
RVPI = 75/80 = 0.94x
TVPI = 0.75 + 0.94 = 1.69x

Profit above hurdle = $35M
Carried interest = 20% × $35M = $7M to GP
```

**Key Points & Exam Traps:**
- Clawback provision: GP returns carry if losses materialise later
- Hurdle rate = preferred return to LPs before carry kicks in
- Vintage year = year fund makes first investment (used for benchmarking)
- IRR and MOIC can tell different stories: high MOIC + long hold = mediocre IRR
- J-curve: early negative IRR (fees + writedowns) before exits materialise

---

# 🎯 Portfolio Management

## Factor Models

### Carhart 4-Factor & Macro

$$E(R_p) = R_F + \beta_1 RMRF + \beta_2 SMB + \beta_3 HML + \beta_4 WML$$
$$\text{Macro: } E(R_i) = a_i + b_{i1} F_{INFL} + b_{i2} F_{GDP} + \varepsilon_i$$
$$\text{Factor return} = \Sigma(\beta_p - \beta_b) \times \lambda$$

**In Plain English:** Fundamental = premiums. Macro = surprises. Active return = factor + selection.

| Variable | Meaning |
|----------|---------|
| RMRF | Market premium |
| WML | Momentum |
| $F_{INFL}$ | Inflation surprise |
| $\lambda$ | Factor premium |

> 💡 **Why / Analogy:** [[CAPM, FF5, Grinold-Kroner|CAPM]] = 1 factor. Carhart = 4 anomalies. Macro = economic shocks.

**📝 Worked Example:**
```
RF=2%, RMRF=5%, SMB=2%, HML=3%, WML=1.5%
β: 1.1, .5, −.3, .2
E(Rp)=2+5.5+1.0−0.9+0.3=7.9%
```

**Key Points & Exam Traps:**
- Value ≠ momentum (diff signs)
- INFL surprise usually negative
- Active risk² = factor + specific risk

---

## Portfolio Mathematics

### Two-Asset Portfolio Variance & Correlation

$$\sigma_p^2 = w_A^2\sigma_A^2 + w_B^2\sigma_B^2 + 2w_Aw_B\sigma_A\sigma_B\rho_{AB}$$
$$\rho_{AB} = \frac{Cov(A,B)}{\sigma_A \sigma_B}; \quad Cov(A,B) = \rho_{AB}\sigma_A\sigma_B$$
$$\sigma_p = \sqrt{w_A^2\sigma_A^2 + w_B^2\sigma_B^2 + 2w_Aw_B Cov_{AB}}$$
$$\text{Min Var weight: } w_A^* = \frac{\sigma_B^2 - Cov_{AB}}{\sigma_A^2 + \sigma_B^2 - 2Cov_{AB}}$$

**In Plain English:** Portfolio variance depends on weights, individual variances, and correlation. Lower ρ = more diversification benefit. At ρ=−1, perfect hedging is possible.

| ρ value | Diversification benefit |
|---------|------------------------|
| +1.0 | None — no reduction |
| 0.0 | Partial — good diversification |
| −1.0 | Maximum — can reach zero risk |

> 💡 **Why / Analogy:** If two assets move together perfectly (ρ=1), combining them does nothing. If they move oppositely (ρ=−1), you can hedge all risk. Real correlations are between 0 and 1 — partial benefit.

**📝 Worked Example:**
```
wA=0.6, wB=0.4, σA=15%, σB=10%, ρ=0.3
Cov = 0.3×15×10 = 45
σ²p = .36×225 + .16×100 + 2×.6×.4×45
    = 81 + 16 + 21.6 = 118.6
σp = √118.6 = 10.89%

vs. ρ=1: σp = .6×15+.4×10 = 13% (no diversification)
```

**Key Points & Exam Traps:**
- Covariance matrix: $n(n-1)/2$ unique covariances for n assets
- Diversification eliminates specific risk; systematic risk remains
- Correlation ≠ causation; can change in crises (correlations rise)

---

## Roy's Safety-First & Leverage

### Safety-First Criterion & Leveraged Returns

$$\text{SFR} = \frac{E(R_p) - R_L}{\sigma_p}$$
$$\text{Choose portfolio with highest SFR (like Sharpe with threshold)}$$
$$\text{Leveraged Return: } R_L = R_p + \frac{B}{E}(R_p - r_b)$$
$$\text{Leveraged } \sigma: \sigma_L = \frac{V}{E} \times \sigma_p$$
$$V = E + B; \quad \frac{V}{E} = 1 + \frac{B}{E}$$

**In Plain English:** SFR: minimise probability of falling below a threshold return $R_L$ — pick highest (E(R)−RL)/σ. Leverage amplifies both returns AND volatility by the leverage ratio V/E.

| Variable | Meaning |
|----------|---------|
| $R_L$ | Minimum acceptable return |
| $B/E$ | Borrowing / equity (leverage ratio) |
| $r_b$ | Borrowing cost |
| $V/E$ | Leverage factor for volatility |

> 💡 **Why / Analogy:** SFR is Sharpe Ratio with $R_f$ replaced by your minimum survival threshold. Roy: "the client can't fall below X — maximise the odds of staying above it."

**📝 Worked Example:**
```
Portfolio A: E(R)=12%, σ=15%, RL=5%
Portfolio B: E(R)=9%, σ=8%, RL=5%
SFR_A = (12−5)/15 = 0.47
SFR_B = (9−5)/8 = 0.50 → Choose B (higher SFR)

Leverage: E=$1M, B=$500K@3%, Rp=10%, σp=12%
RL = 10% + 0.5(10%−3%) = 13.5%
σL = 1.5 × 12% = 18%
```

**Key Points & Exam Traps:**
- When RL = Rf, SFR = Sharpe Ratio
- Leverage amplifies losses equally — borrowed returns come at borrowing cost
- Margin call risk: leveraged positions can be unwound at worst times
- σ scales with V/E; E(R) excess above borrowing scales with B/E

---

## VaR

### Value at Risk

$$VaR = [E(R_p) - z \cdot \sigma_p] \times (-1) \times NA$$
$$\text{Daily } \sigma = \sigma / \sqrt{250}; \quad \text{Daily } E(R) = E(R)/250$$

| z-score | Confidence |
|---------|------------|
| 2.33 | 1% |
| 1.65 | 5% |
| 1.00 | 16% |

**In Plain English:** Min loss exceeded at given probability. Scale: ÷ periods for E(R), ÷ √periods for σ.

| Variable | Meaning |
|----------|---------|
| $z$ | Confidence z-score |
| $NA$ | Portfolio value |
| [[CVaR]] | Expected loss given loss > VaR |

> 💡 **Why / Analogy:** One downside number. Doesn't say HOW BAD worst cases get (that's CVaR).

**📝 Worked Example:**
```
E(Rp)=10%, σ=18%, NA=$50M, 5% annual
VaR=[.10−1.65(.18)]×(−1)×50M
   =[−.197]×(−50M)=$9.85M

Daily: E(R)=.04%, σ=1.138%
VaR=[−.01838]×(−50M)=$919K/day
```

**Key Points & Exam Traps:**
- CVaR = expected loss given VaR exceeded
- $\sigma_{\text{weekly}} = \sigma/\sqrt{52}$; $\sigma_{\text{monthly}} = \sigma/\sqrt{12}$
- $\sigma^2_{\text{port}} = w_A^2 \sigma_A^2 + w_B^2 \sigma_B^2 + 2w_A w_B Cov_{AB}$

---

## Economics & Investment Markets

### Asset Pricing Layers

$$P = \sum \frac{E[CF]}{(1 + I + \theta + \pi + \gamma + \kappa + \phi)^s}$$
$$\text{Short rate: } r = R + \pi$$
$$\text{Long rate: } R + \pi + \theta$$
$$1+i \approx (1+r)(1+\pi^e); \quad i \approx r + \pi^e$$
$$BEI_{t,s} = y_{\text{nominal},t,s} - y_{\text{real},t,s} = \theta_{t,s} + \pi_{t,s}$$
$$\text{Credit: } +\gamma; \quad \text{Equity: } +\kappa; \quad \text{RE: } +\phi$$
$$\text{Taylor: } r = R_n + \pi + 0.5(\pi - \pi^*) + 0.5(y - y^*)$$
$$\text{Output gap \%} \approx y - y^*$$

**In Plain English:** Discount rate = stacked risk premia. [[Taylor Rule]] sets policy rate from inflation & output gaps.

| Variable | Meaning |
|----------|---------|
| $I / R$ | Real rate |
| $\pi$ | Expected inflation in this sheet's rate shorthand |
| $\theta$ | Inflation uncertainty in this sheet's rate shorthand |
| $\theta_{t,s}$ | Expected inflation in CFA BEI notation |
| $\pi_{t,s}$ | Inflation risk premium in CFA BEI notation |
| $\gamma$ | Credit |
| $\kappa$ | Equity premium |
| $\phi$ | Illiquidity |
| $y-y^*$ | [[CFA_Glossary/Output gap]] |

> 💡 **Why / Analogy:** Stacking Lego: real + inflation + credit + equity + illiquidity. Each block adds required return.

**📝 Worked Example:**
```
R=2%, π=2.5%, θ=.5%
Bond: +γ(1%)=6.0%
Equity: +κ(4%)=10.0%
RE: +φ(1.5%)=11.5%

Taylor: Rn=2%, π=3%, π*=2%, y−y*=1%
r=2+3+.5+.5=6.0%
```

**Key Points & Exam Traps:**
- $BEI = \text{nominal} - \text{TIPS yield}$
- BEI = expected inflation + inflation risk premium
- Real rate = $1/E(m_1) - 1$
- Fisher approximation: nominal ≈ real + expected inflation
- Taylor rule output gap is usually log actual GDP minus log potential GDP, so it reads like a percentage gap

---

## Active Management

### Active Return Decomposition

$$R_A = \sum \Delta w_j \cdot R_{B,j} + \sum w_{p,j} \cdot R_{A,j}$$
$$\quad\quad\text{(allocation)} \quad\quad\quad \text{(selection)}$$

**In Plain English:** Active return = sector bets (allocation) + stock picking (selection).

| Variable | Meaning |
|----------|---------|
| $\Delta w_j$ | Active weight (port − bench) |
| $R_{B,j}$ | Benchmark return |
| $R_{A,j}$ | Active return in class j |

> 💡 **Why / Analogy:** Two ways to beat benchmark: right sectors or better stocks within each.

**📝 Worked Example:**
```
Stocks: wp=65%, wb=60%, RB=12%, Rp=14%
Bonds:  wp=35%, wb=40%, RB=4%,  Rp=3%
Alloc:  5%(12%)+(−5%)(4%)=0.4%
Select: 65%(2%)+35%(−1%)=0.95%
Total=1.35%
```

**Key Points & Exam Traps:**
- Active return = $R_p - R_B$
- Active risk = $\sigma(\text{active return})$

---

### SR, IR & Fundamental Law

$$SR = \frac{R_p - R_f}{\sigma_p}; \quad IR = \frac{R_A}{\sigma_A}$$
$$SR_p^2 = SR_B^2 + IR^2$$
$$\sigma_A^* = \frac{IR}{SR_B} \times \sigma_B$$
$$IR = TC \times IC \times \sqrt{BR}$$
$$E(R_A) = TC \times IC \times \sqrt{BR} \times \sigma_A$$

**In Plain English:** [[Sharpe Ratio|SR]] = total reward/risk. [[Information Ratio|IR]] = active reward/risk. [[Fundamental Law|FLAM]]: IR = skill × breadth × freedom.

| Variable | Meaning |
|----------|---------|
| $TC$ | Transfer coeff (1 unconstrained) |
| $IC$ | Forecast accuracy |
| $BR$ | # independent decisions/yr |
| $\sigma_A$ | Active risk |

> 💡 **Why / Analogy:** Recipe for alpha: skill × opportunities × freedom. Low IC + high BR can beat high IC + few bets.

**📝 Worked Example:**
```
IC=.05, BR=500, TC=.8, σA=4%
IR=.8×.05×22.36=0.894
E(RA)=.894×4%=3.58%

Constrained TC=.5: IR=.559
E(RA)=2.24% (lost 1.34%)

SR²p=.33²+.894²=.908; SRp=.953
```

**Key Points & Exam Traps:**
- SR unaffected by cash/leverage
- IR affected by cash but NOT active weight aggressiveness
- Highest IR → highest SR
- Doubling BR → $IR \times \sqrt{2} \approx 1.41\times$

---

## Quick Cross-Reference Index

| Concept | Links To |
|---------|----------|
| [[R² and Adjusted R²]] | [[AIC & BIC]], [[F-Test (Joint Hypothesis)]] |
| [[Breusch-Pagan (Heteroskedasticity)]] | [[White-corrected SE]], [[Durbin-Watson (Serial Correlation)]] |
| [[Durbin-Watson (Serial Correlation)]] | [[Breusch-Godfrey (SC with Lagged DV)]], [[Newey-West SE]] |
| [[AR(1) & Mean-Reverting Level]] | [[Random Walk & Dickey-Fuller]], [[ARCH(1)]] |
| [[CIRP]] | [[Forward Mark-to-Market]], [[UIRP, PPP & Intl Fisher]] |
| [[Cobb-Douglas]] | [[Growth Accounting]] |
| [[GGM, H-Model, Perpetuity]] | [[Sustainable Growth (PRAT)]], [[PVGO & Justified Multiples]] |
| [[FCFF (4 Starting Points)]] | [[FCFE (All Forms)]], [[WACC]] |
| [[Residual Income Model]] | [[DuPont 5-Way & Sustainable Growth]], [[EVA]] |
| [[Binomial Model]] | [[BSM, Black & Swaptions]] |
| [[CAPM, FF5, Grinold-Kroner]] | [[Carhart 4-Factor & Macro]], [[Cost of Equity]] |
| [[SR, IR & Fundamental Law]] | [[Value at Risk]], [[Active Return Decomposition]] |
| [[Direct Cap, DCF & Metrics]] | [[REIT: NAV, FFO, AFFO]] |
| [[Forward Price, Value & FRA]] | [[IRS, Currency & Equity Swaps]] |
| [[Bond Price, Accrued Interest & Yields]] | [[MacD, ModD, Dollar Duration & DV01]], [[Convexity & Full Price Change]] |
| [[MacD, ModD, Dollar Duration & DV01]] | [[Convexity & Full Price Change]], [[Callable/Putable/Convertible]] |
| [[Nominal, G, I, Z, OAS Spreads]] | [[CDS & Credit Migration]], [[Callable/Putable/Convertible]] |
| [[Put-Call Parity & Synthetic Positions]] | [[BSM, Black & Swaptions]], [[Delta, Gamma, Theta, Vega, Rho]] |
| [[Delta, Gamma, Theta, Vega, Rho]] | [[Binomial Model]], [[BSM, Black & Swaptions]] |
| [[WACC]] | [[CAPM, FF5, Grinold-Kroner]], [[FCFF (4 Starting Points)]], [[MM Propositions & Beta Levering]] |
| [[MM Propositions & Beta Levering]] | [[WACC]], [[CAPM, FF5, Grinold-Kroner]], [[Cost of Capital]] |
| [[DOL, DFL & DCL]] | [[Leverage & Coverage]], [[SR, IR & Fundamental Law]] |
| [[PBO, Periodic Pension Cost & Funded Status]] | [[Equity Method & Goodwill]], [[DuPont 5-Way & Sustainable Growth]] |
| [[Accrual Ratios (BS and CF Methods)]] | [[Beneish M-Score]], [[Earnings Persistence]] |
| [[MOIC, DPI, RVPI, TVPI & Carried Interest]] | [[Direct Cap, DCF & Metrics]], [[Conditional Factor Model]] |
| [[Two-Asset Portfolio Variance & Correlation]] | [[Value at Risk]], [[SR, IR & Fundamental Law]] |
| [[Safety-First Criterion & Leveraged Returns]] | [[SR, IR & Fundamental Law]], [[Value at Risk]] |
