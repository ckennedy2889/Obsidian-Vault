---
title: Using Multifactor Models
subject: Portfolio Management
tags: [CFA-L2, PortfolioManagement, Multifactor, APT, ArbitragePricingTheory, FactorModels, FamaFrench, Carhart, ActiveRisk, TrackingError, InformationRatio, ReturnAttribution, RiskAttribution]
aliases: [APT, Arbitrage Pricing Theory, Multifactor Models, L2 PM Module 4]
---

# Using Multifactor Models

> [!abstract] The One-Sentence Version
> A multifactor model says an asset's return is the sum of a baseline (like the risk-free rate) plus **sensitivities (betas) to a handful of systematic risks × the prices of those risks (lambdas)** plus noise — and once you have that structure, you can price assets, attribute performance, budget risk, and decompose active return into factor tilts vs stock picking.

The CAPM asks "how much market risk?" Multifactor models ask "how much of each kind of risk?" That shift unlocks **APT for pricing**, **Fama-French for style attribution**, **Barra for risk budgeting**, and the whole machinery of modern active management.

---

## 1. Arbitrage Pricing Theory (APT)

### 1.1 The Three Assumptions — Memorize These

APT rests on exactly **three** assumptions. CAPM is more restrictive; APT is more general.

| # | Assumption | What it buys us |
|---|---|---|
| 1 | A **factor model** describes asset returns | Gives us the linear structure $R_i = a_i + \beta_{i,1}F_1 + \dots + \beta_{i,K}F_K + \varepsilon_i$ |
| 2 | **Asset-specific (idiosyncratic) risk can be diversified away** in a well-diversified portfolio | Lets us ignore $\varepsilon_i$ at the portfolio level |
| 3 | **No arbitrage** opportunities exist | Forces the pricing equation below |

> [!tip] Memory Hook — **"F-D-A"**
> **F**actors explain returns → **D**iversification kills idio risk → no **A**rbitrage. If any one fails, APT breaks.

### 1.2 The APT Pricing Equation

$$
\boxed{\,E(R_p) \;=\; R_F \;+\; \lambda_1\,\beta_{p,1} \;+\; \lambda_2\,\beta_{p,2} \;+\; \dots \;+\; \lambda_K\,\beta_{p,K}\,}
$$

| Symbol | Meaning |
|---|---|
| $R_F$ | Risk-free rate |
| $\lambda_j$ | **Factor risk premium** — expected excess return on a portfolio with $\beta=1$ to factor $j$ and $\beta=0$ to all others |
| $\beta_{p,j}$ | **Factor sensitivity** of the portfolio to factor $j$ |
| $K$ | Number of factors (model-dependent) |

### 1.3 Relation to CAPM — Special Case

Set $K=1$ with the market factor, $\lambda_1 = E(R_M) - R_F$, and $\beta_{p,1} = \beta_p$:

$$
E(R_p) = R_F + \beta_p\,[E(R_M) - R_F] \quad \text{(CAPM)}
$$

> **CAPM is just APT with a single, named factor (the market).** Everything APT does generalizes this.

### 1.4 APT vs. CAPM — Key Differences

| Feature | CAPM | APT |
|---|---|---|
| Number of risk factors | 1 (market) | Unlimited |
| Equilibrium vs. no-arbitrage | **Equilibrium** (all investors optimize) | **No-arbitrage** (weaker, more realistic) |
| Market portfolio | Required | Not required |
| Utility-function assumptions | Yes (mean-variance) | **No** |
| Identifies factors? | Yes (the market) | **No** — theory is silent on which factors |

### 1.5 Worked Example — Two-Factor APT

> A portfolio has sensitivities to GDP growth ($\beta_1 = 1.2$) and inflation ($\beta_2 = 0.8$).
>
> **Inputs**
> - $R_F = 3\%$
> - $\lambda_{\text{GDP}} = 5\%$
> - $\lambda_{\text{INFL}} = -2\%$ (inflation-hedging assets command *lower* expected return — counterintuitive but correct)
>
> **Expected return**
> $$E(R_p) = 3\% + (1.2)(5\%) + (0.8)(-2\%) = 3\% + 6\% - 1.6\% = \mathbf{7.4\%}$$

See: [[Arbitrage Pricing Theory]] · [[CAPM]] · [[Factor Risk Premium]]

---

## 2. Arbitrage — Definition and Detection

### 2.1 What Is an Arbitrage?

An **arbitrage** is a trade with:
1. **Zero net investment** (no money of your own down),
2. **Zero risk** (payoffs are certain or fully hedged),
3. **Positive expected profit** (strictly better than cash).

> If all three hold, rational traders pile in until prices move and the opportunity vanishes. APT *assumes* this happens instantly.

### 2.2 The Law of One Price

> **Two assets (or portfolios) with identical cash flows must have identical prices.** If not, buy the cheap one, short the expensive one, pocket the spread — riskless profit.

In a factor-model world, "identical cash flows" becomes "identical factor exposures." Two well-diversified portfolios with the same β to every factor must offer the same expected return.

### 2.3 Detecting Arbitrage in a Single-Factor World

**Procedure**
1. Run the pricing equation: $E(R) = R_F + \lambda\,\beta$ using two correctly-priced portfolios to pin down $R_F$ and $\lambda$.
2. Test any third portfolio: does its return fall on the line?
3. If **above** the line → portfolio is **underpriced** (offers too much return for its risk). **Buy** it, fund by shorting a same-β mix of the reference portfolios.
4. If **below** the line → **overpriced**. **Short** it, buy the reference mix.

### 2.4 Worked Example — Arbitrage Detection

> The market implies a single-factor equation $E(R) = 5\% + 4\%(\beta)$.
>
> | Portfolio | Expected return | β |
> |---|---|---|
> | A | 9% | 1.0 |
> | B | 13% | 2.0 |
> | C | 12% | 1.5 |
>
> **Check each**:
> - A: model says $5 + 4(1) = 9$ ✓ fair
> - B: model says $5 + 4(2) = 13$ ✓ fair
> - C: model says $5 + 4(1.5) = 11$; actual = **12% > 11%** → **C is underpriced**
>
> **Arbitrage trade** (zero net investment, zero net β):
>
> | Action | Portfolio | Weight | Cash flow | β contribution |
> |---|---|---|---|---|
> | **Buy** | C | +1.0 | –$100 | +1.5 |
> | **Short** | A | –0.5 | +$50 | –0.5 |
> | **Short** | B | –0.5 | +$50 | –1.0 |
> | **Net** | | 0 | **$0** | **0** |
>
> **Net expected return**: $(1.0)(12\%) + (-0.5)(9\%) + (-0.5)(13\%) = 12\% - 4.5\% - 6.5\% = \mathbf{+1\%}$ of riskless profit.

> [!tip] Mnemonic — **"Above the line = Buy"**
> Plot expected return vs. β. Points *above* the security-market line are cheap (buy); points *below* are rich (short). The arbitrage opportunity is measured vertically.

See: [[Arbitrage]] · [[Law of One Price]] · [[Well-Diversified Portfolio]]

---

## 3. Computing Expected Return from Factor Sensitivities

The equation $E(R_p) = R_F + \sum \lambda_j \beta_{p,j}$ is the workhorse. Show it with a real model.

### 3.1 Carhart 4-Factor Model — Worked Example

The **Carhart four-factor model** extends Fama-French 3-factor by adding momentum:

$$
R_i - R_F \;=\; \alpha_i \;+\; \beta_{i,\text{MKT}}(R_M - R_F) \;+\; \beta_{i,\text{SMB}}\,R_{\text{SMB}} \;+\; \beta_{i,\text{HML}}\,R_{\text{HML}} \;+\; \beta_{i,\text{WML}}\,R_{\text{WML}} \;+\; \varepsilon_i
$$

| Factor | Abbrev. | Long leg | Short leg | Risk premium (the "price") |
|---|---|---|---|---|
| Market | RMRF / MKT | Market portfolio | Risk-free | $R_M - R_F$ |
| Size | SMB | Small-cap | Large-cap | "Small minus Big" |
| Value | HML | High B/P (value) | Low B/P (growth) | "High minus Low" |
| Momentum | WML or UMD | Winners (past 12-2 month) | Losers | "Winners minus Losers" / "Up minus Down" |

> **Why these four?** Empirically, SMB, HML, and WML portfolios have produced persistent premia that market β alone can't explain. Fama-French added a 5th factor in 2015 — profitability (RMW) and investment (CMA) — but Carhart-4 is the canonical L2 benchmark.

### 3.2 Worked Example — Carhart Expected Return

> | Input | Value |
> |---|---|
> | $R_F$ | 2% |
> | $R_M - R_F$ | 6% |
> | $R_{\text{SMB}}$ | 2% |
> | $R_{\text{HML}}$ | 3% |
> | $R_{\text{WML}}$ | 8% |
> | $\beta_{\text{MKT}}$ | 1.1 |
> | $\beta_{\text{SMB}}$ | 0.5 |
> | $\beta_{\text{HML}}$ | –0.2 |
> | $\beta_{\text{WML}}$ | 0.3 |
>
> $$E(R) = 2\% + (1.1)(6\%) + (0.5)(2\%) + (-0.2)(3\%) + (0.3)(8\%)$$
> $$= 2\% + 6.6\% + 1.0\% - 0.6\% + 2.4\% = \mathbf{11.4\%}$$
>
> **Interpretation**: This stock has a market-beating β, tilts **small** (positive SMB), tilts **growth** (negative HML), and **rides momentum** — and these four exposures alone explain an 11.4% expected return.

See: [[Fama-French Model]] · [[Carhart Four-Factor Model]] · [[SMB]] · [[HML]] · [[Momentum]]

---

## 4. The Three Factor-Model Families

All multifactor models share the same equation structure — they differ only in **how the factors are defined**.

![[factor-model-families.png]]

### 4.1 Macroeconomic Factor Models

Factors are **surprises** to macro variables — the component of each data release that wasn't already priced in.

$$
R_i \;=\; a_i \;+\; \beta_{i,\text{GDP}}(F_{\text{GDP}}) \;+\; \beta_{i,\text{INFL}}(F_{\text{INFL}}) \;+\; \dots \;+\; \varepsilon_i
$$

where $F_{\text{GDP}} = \text{actual GDP} - \text{expected GDP}$ (the surprise).

- **Typical factors**: GDP growth surprise, inflation surprise, term spread change, credit spread change, oil-price surprise.
- **Beta estimation**: time-series regression of asset returns on factor surprises.
- **Best for**: investors who want to express specific macroeconomic views, or hedge macro exposures (e.g., pension funds matching liabilities).

### 4.2 Fundamental Factor Models

Factors are **firm attributes** — observable company or security characteristics.

- **Typical factors**: Market, Size, Value, Momentum, Profitability, Investment, Quality, Low-Volatility.
- **Beta estimation**: Betas are the asset's **observed attributes**, standardized (z-scored). Factor returns are then estimated by cross-sectional regression for each period.
- **Key flip**: Unlike macro models, the *betas are the data* and the *factor returns are estimated* — the opposite direction.
- **Best for**: style analysis, return attribution, smart-beta product design.

> [!tip] Macro vs Fundamental — The Flip
> **Macro**: observe factor returns (surprises), estimate betas (time-series regression).
> **Fundamental**: observe betas (attributes), estimate factor returns (cross-sectional regression).

### 4.3 Statistical Factor Models

Factors are **unlabeled mathematical constructs** extracted from the return covariance matrix.

- **Two sub-types**:
  - **Factor analysis** — chooses factors that best explain the **covariance** of asset returns.
  - **Principal components analysis (PCA)** — chooses factors that best explain the **variance** of asset returns.
- **Betas**: loadings from the eigen-decomposition.
- **Best for**: risk modeling (Barra's E-model and similar), when no theory exists or when theoretical factors fail to explain data.
- **Weakness**: factors have no economic interpretation — they're just mathematical directions.

### 4.4 Comparison Table

| Feature | Macroeconomic | Fundamental | Statistical |
|---|---|---|---|
| Factor = | Macro surprise | Firm attribute | Math construct |
| Interpretable? | **Yes** (intuitive) | **Yes** (style) | **No** (numbers only) |
| Data need | Economic forecasts + actual | Company financials | Historical prices only |
| Estimation | Time-series regression | Cross-sectional regression | Eigen-decomposition |
| Canonical example | BIRR 5-factor | Fama-French / Carhart | Barra E-model, APT-PCA |
| Primary use | Economic views; liability matching | Style attribution; smart beta | Risk modeling; covariance |

See: [[Macroeconomic Factor Model]] · [[Fundamental Factor Model]] · [[Statistical Factor Model]] · [[Principal Components Analysis]]

---

## 5. What Multifactor Models Are Actually Used For

Five major use cases, each relevant to a CFA exam question.

### 5.1 Return Attribution

Decompose a portfolio's active return ($R_P - R_B$) into:

$$
R_A \;=\; \underbrace{\sum_j (\beta_{P,j} - \beta_{B,j})\,F_j}_{\text{Factor-tilt return}} \;+\; \underbrace{\text{Security selection}}_{\text{Residual / alpha}}
$$

#### Worked Example — Return Attribution

> | Item | Portfolio β | Benchmark β | Factor return |
> |---|---|---|---|
> | Market (RMRF) | 1.10 | 1.00 | 6% |
> | Value (HML) | 0.40 | 0.00 | 5% |
> | Security selection | — | — | 0.50% |
>
> **Market tilt contribution**: $(1.10 - 1.00) \times 6\% = 0.60\%$
> **Value tilt contribution**: $(0.40 - 0.00) \times 5\% = 2.00\%$
> **Factor-tilt total**: 2.60%
> **Security selection**: 0.50%
> **Total active return**: $\mathbf{3.10\%}$

### 5.2 Risk Attribution

Decompose total active risk (variance) into factor-bet risk and stock-pick risk — see Section 7.

### 5.3 Portfolio Construction

| Approach | How models help |
|---|---|
| **Passive indexing** | Replicate a benchmark's factor exposures using a small subset of securities (index-sampling) |
| **Active management** | Build portfolios with intentional factor tilts where the manager has forecasted skill |
| **Rules-based / smart beta** | Capture factor premia mechanically — value/size/momentum ETFs at low fees |
| **Risk-parity** | Equal **risk** contributions across factors, not equal dollar weights |

### 5.4 Strategic / Liability-Driven Decisions

Pension funds match the factor exposures of their **liabilities** (e.g., long-duration interest-rate sensitivity) with corresponding asset exposures — immunization done at the factor level, not just the duration level.

### 5.5 Active Risk Budgeting

Set bounds on permissible factor tilts (e.g., "tracking error ≤ 3%, with factor-tilt contribution ≤ 60% of that") to enforce discipline and prevent single-factor concentration.

See: [[Return Attribution]] · [[Smart Beta]] · [[Liability-Driven Investing]] · [[Risk Budgeting]]

---

## 6. Benefits of Considering Multiple Risk Dimensions

### 6.1 Diversification Across Factors, Not Just Stocks

Two equity portfolios can look diversified (500 names each) yet be identically exposed to a single factor (say, value). Factor thinking exposes this hidden concentration.

### 6.2 Matching Investor-Specific Exposures

| Investor type | Should underweight... | Reason |
|---|---|---|
| Oil-industry employee | Energy factor / oil-price beta | Human capital already loaded |
| Tech-heavy executive (RSUs) | Growth / technology factor | Diversification |
| Long-horizon university endowment | Can *overweight* recession-risk factors | 50-year horizon; can ride drawdowns |
| DB pension plan | Match interest-rate and inflation sensitivities | Liabilities have those exposures |

> [!tip] Mnemonic — **"Underweight what you're already long"**
> The single biggest benefit of factor thinking is recognizing exposures outside your investment portfolio — jobs, homes, businesses — and sizing the portfolio to complement them, not amplify them.

### 6.3 Comparative-Advantage Risk Taking

Different investors have different tolerances for different factors:
- **Long-horizon investors** can bear **business-cycle risk** (equity beta) because they won't be forced to sell in a downturn.
- **Short-horizon investors** must avoid illiquidity and drawdown risk but can bear short-term volatility.
- **Tax-exempt investors** can embrace high-yield (tax-inefficient) exposures that retail investors should avoid.

Factor models let you pick up premia specifically in your risk dimensions — where you have a comparative advantage — rather than blindly loading the market factor.

### 6.4 Better Risk-Adjusted Returns

Historically, diversified factor tilts (e.g., value + momentum + profitability) have delivered higher Sharpe ratios than the market alone because factor premia are imperfectly correlated.

See: [[Factor Investing]] · [[Comparative Advantage]] · [[Human Capital]]

---

## 7. Sources of Active Risk, Tracking Error, and the Information Ratio

### 7.1 The Decomposition of Active Risk

Active risk (tracking error) squared breaks cleanly into two orthogonal pieces:

$$
\boxed{\,\sigma_A^{\,2} \;=\; \underbrace{\text{Active Factor Risk}}_{\text{variance from factor tilts}} \;+\; \underbrace{\text{Active Specific Risk}}_{\text{variance from individual stock picks}}\,}
$$

| Source | Definition | Example |
|---|---|---|
| **Active factor risk** | Variance of active returns due to systematic factor tilts vs benchmark | Overweight small-cap relative to index |
| **Active specific risk** | Variance from idiosyncratic stock-specific bets | Overweight Apple by 3% when benchmark is 2% |

#### Worked Example — Active Risk Decomposition

> | Component | Variance (%²) |
> |---|---|
> | Active factor risk | 18 |
> | Active specific risk | 7 |
> | **Total active variance** | **25** |
>
> **Tracking error** = $\sqrt{25} = \mathbf{5\%}$
>
> **Proportions**:
> - Factor tilts: $18/25 = 72\%$
> - Stock picking: $7/25 = 28\%$
>
> **Interpretation**: This manager's active risk is dominated by **factor bets**, not name selection. If the client only wanted stock-picking alpha, the manager is off-mandate.

### 7.2 Tracking Risk (a.k.a. Tracking Error)

$$
\sigma_A \;=\; \text{stddev}(R_P - R_B)
$$

A measure of how closely a portfolio follows its benchmark. Typical values:

| Strategy | Typical TE |
|---|---|
| Index fund | < 0.25% |
| Enhanced index | 0.5 – 1.5% |
| Active core equity | 3 – 5% |
| Concentrated active / hedge | 5 – 10%+ |

### 7.3 Information Ratio (Re-cap from Module 2)

$$
\text{IR} \;=\; \frac{\bar{R}_A}{\sigma_A}
$$

In multifactor world, $\bar{R}_A$ can come from factor tilts, security selection, or both — but IR still measures **active return per unit of tracking error**, regardless of source.

#### Worked Example — Full Chain

> From Section 5.1: active return = 3.10%.
> From Section 7.1: tracking error = 5.00%.
>
> $$\text{IR} \;=\; \frac{3.10\%}{5.00\%} \;=\; \mathbf{0.62}$$
>
> **Interpretation**: 0.62 units of active return per unit of tracking error — "quite good" in quant/equity land. The manager earns 0.62% for every 1% of active risk taken.

See: [[Active Risk]] · [[Tracking Error]] · [[Information Ratio]] · [[Active Factor Risk]] · [[Active Specific Risk]]

---

## 8. Putting It All Together

### 8.1 Master Summary Table

| LOS | Key idea / formula |
|---|---|
| **APT** | Three assumptions: factor model, diversifiable idio risk, no arbitrage |
| **APT equation** | $E(R_p) = R_F + \sum \lambda_j \beta_{p,j}$ |
| **APT vs CAPM** | CAPM is APT with K=1, market factor, $\lambda = E(R_M) - R_F$ |
| **Arbitrage** | Zero investment, zero risk, positive return |
| **Detection** | Point above the SML → underpriced → buy; below → overpriced → short |
| **Factor families** | Macro (surprises), Fundamental (attributes), Statistical (PCA) |
| **Return attribution** | $R_A = \sum(\beta_P - \beta_B)F + \text{selection}$ |
| **Active risk decomp** | $\sigma_A^2 = \text{Factor risk} + \text{Specific risk}$ |
| **IR** | $\bar{R}_A / \sigma_A$ |

### 8.2 Exam Danger Zones

| Trap | Fix |
|---|---|
| Confusing CAPM with APT | APT is multi-factor, no utility assumptions, no market portfolio |
| Forgetting macro factors are **surprises**, not raw data | $F_{\text{GDP}}$ = actual − expected |
| Confusing direction in fundamental models | Betas are observed (attributes); factor returns are estimated |
| Missing a factor when computing expected return | Include all factors; unused ones have β = 0 |
| Conflating tracking error with Sharpe denominator | Sharpe uses total σ; IR uses active σ |
| Adding active variances without subtracting covariances | **Active factor and specific risks are orthogonal by construction** — you can add variances directly |
| Ignoring the sign of λ | Hedge assets can have negative λ (e.g., inflation-hedge) |

### 8.3 Decision Framework for a Multifactor Question

1. **Identify the model** — macro / fundamental / statistical? This tells you what betas mean.
2. **Write the APT equation** with the factors in the question.
3. **Compute expected return** → $R_F + \sum \lambda \beta$.
4. **Check for arbitrage** → compare actual return to equation's prediction.
5. **Attribute active return** → tilt + selection.
6. **Decompose risk** → factor variance + specific variance → tracking error.
7. **Compute IR** → divide active return by tracking error.

---

## 9. Formula Cheat Sheet

| Formula | Gives |
|---|---|
| $R_i = a_i + \sum_j \beta_{i,j}F_j + \varepsilon_i$ | General factor model |
| $E(R_p) = R_F + \sum_j \lambda_j \beta_{p,j}$ | APT pricing equation |
| $E(R_p) = R_F + \beta_p[E(R_M) - R_F]$ | CAPM (APT special case, K=1) |
| $R_i - R_F = \alpha + \beta_M(R_M-R_F) + \beta_{\text{SMB}}\text{SMB} + \beta_{\text{HML}}\text{HML} + \beta_{\text{WML}}\text{WML}$ | Carhart 4-factor |
| $R_A = \sum_j(\beta_{P,j}-\beta_{B,j})F_j + \text{selection}$ | Return attribution |
| $\sigma_A^2 = \text{Active factor risk} + \text{Active specific risk}$ | Risk decomposition |
| $\text{IR} = \bar{R}_A / \sigma_A$ | Information ratio |
| Arbitrage test: actual return > $R_F + \lambda\beta$ | Underpriced → buy |

---

## 10. Related Notes

- [[Arbitrage Pricing Theory]] · [[CAPM]] · [[Law of One Price]]
- [[Fama-French Model]] · [[Carhart Four-Factor Model]] · [[SMB]] · [[HML]] · [[Momentum]]
- [[Macroeconomic Factor Model]] · [[Fundamental Factor Model]] · [[Statistical Factor Model]]
- [[Return Attribution]] · [[Brinson Fachler Attribution]]
- [[Active Risk]] · [[Tracking Error]] · [[Information Ratio]]
- [[Smart Beta]] · [[Factor Investing]] · [[Risk Budgeting]]
- [[Liability-Driven Investing]] · [[Risk Parity]]
- Connected reading: [[Analysis of Active Portfolio Management]] — same IR framework, different angle
- Practice: `Practice Questions/10 - Portfolio Management/Using Multifactor Models/`

---

> [!quote] Final Frame
> APT gave us the equation. Fama-French gave us useful factors. The three factor-model families gave us three ways to *name* those factors. Put them together and the same structure **prices assets, attributes returns, budgets risk, and yields the information ratio** — one framework, many jobs.
