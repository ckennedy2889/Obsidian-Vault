---
title: Fama-French Model
subject: Portfolio Management
tags: [CFA-L2, PortfolioManagement, Equity, FactorModels, FamaFrench, Carhart, SMB, HML, Momentum, CostOfEquity, StyleAnalysis, APT, CAPM]
aliases: [Fama-French, Fama-French 3-Factor, FF3, FF5, Fama-French Factor Models, Fama-French Three-Factor Model, Fama-French Five-Factor Model]
---

# Fama-French Model

> [!abstract] The One-Sentence Version
> The Fama-French model says a stock's expected return isn't just compensation for **market risk** — it's also compensation for being **small** and for being **cheap** (and in the 5-factor extension, for being **profitable** and **investment-disciplined**) — giving us a richer, empirically-grounded alternative to CAPM.

## The Analogy — Why One Ingredient Isn't Enough

Imagine you're a chef trying to predict how tasty a dish will be. [[CAPM]] says "the only thing that matters is how spicy it is" — one ingredient, one prediction. But any real cook knows that **saltiness**, **fat content**, and **acid balance** all independently shape how the dish tastes. Ignore them, and your predictions systematically miss.

Eugene **Fama** and Kenneth **French** looked at 30 years of stock-market data and discovered the same thing: **CAPM was missing ingredients.** Two groups of stocks kept beating CAPM's forecasts over and over:

1. **Small companies** outperformed big ones.
2. **"Cheap" companies** (high book-to-market) outperformed "expensive" growth ones.

CAPM had no explanation for either pattern — they were **anomalies**. Fama-French's insight: stop treating them as anomalies. **Treat them as risk factors.** If investors persistently demand extra return for holding small or cheap stocks, those traits must carry real, priced risk. Add them to the model.

> [!tip] Memory Hook — **"Market, Mini, Marked-down"**
> CAPM gives you **Market** risk. Fama-French adds **Mini** (size/SMB) and **Marked-down** (value/HML). Carhart tacks on **Momentum**. Fama-French-5 adds **Moneymaking** (profitability/RMW) and **Modest investment** (investment discipline/CMA). All M's.

---

## 1. Origin and Motivation — What CAPM Failed to Explain

For decades, the **Capital Asset Pricing Model** reigned:

$$E(R_i) = R_F + \beta_i\,[E(R_M) - R_F]$$

One factor. One beta. The *only* compensated risk is how much the stock wiggles with the market.

Then the anomalies arrived. Academics ran thousands of regressions and kept finding the same two patterns:

| Anomaly | What researchers saw | Why CAPM choked |
|---|---|---|
| **Size effect** | Small-cap stocks earned ~3% per year *above* what CAPM predicted | CAPM's β didn't differentiate by firm size |
| **Value effect** | Stocks with high book-to-market (B/M) earned persistent excess returns | CAPM's β didn't pick up "cheapness" |

Fama and French (1992, 1993) published the canonical papers. Their fix wasn't to replace CAPM — it was to **generalize** it. Keep the market factor; add **Size** and **Value** as additional systematic risks. The three-factor model was born.

---

## 2. The Three-Factor Model — Equation and Variables

$$
\boxed{\;E(R_i) \;=\; R_F \;+\; \beta_{i,\mathrm{MKT}}\,(R_M - R_F) \;+\; \beta_{i,\mathrm{SMB}}\,\mathrm{SMB} \;+\; \beta_{i,\mathrm{HML}}\,\mathrm{HML}\;}
$$

Or, in the CFA-text cost-of-equity form:

$$r_e = R_F + \beta_1\,\mathrm{ERP} + \beta_2\,\mathrm{SMB} + \beta_3\,\mathrm{HML}$$

| Symbol | Full name | What it is | Sign intuition |
|---|---|---|---|
| $R_F$ | Risk-free rate | Government T-bill / T-bond yield | Baseline — always positive |
| $R_M - R_F$ or $\mathrm{ERP}$ | Market / equity risk premium | Excess return of the market over cash | Positive (stocks > cash over long run) |
| $\mathrm{SMB}$ | **S**mall **M**inus **B**ig | Return on small-cap portfolio *minus* return on large-cap portfolio | Positive historically (small-cap premium ~2–3%) |
| $\mathrm{HML}$ | **H**igh **M**inus **L**ow | Return on high-B/M (value) portfolio *minus* return on low-B/M (growth) portfolio | Positive historically (value premium ~4–5%) |
| $\beta_{i,k}$ | Factor loading (sensitivity) of stock $i$ to factor $k$ | Estimated by multivariate regression | Can be positive or negative |

> [!note] Jargon Decoded — **Book-to-Market (B/M)**
> B/M = (Book value of equity) / (Market value of equity). A **high** B/M means the market is pricing the firm cheaply relative to its accounting net worth — the classic definition of a **value stock**. A **low** B/M means the market is willing to pay a premium over book — a **growth stock**.

---

## 3. How the Factor Portfolios Are Constructed (2×3 Sort)

This is the part most texts skip — but if you don't see how SMB and HML are *built*, the factors feel like black magic. Fama and French use a **double sort**:

```
                        Book-to-Market (value dimension)
                   Low (Growth)  |  Medium  |  High (Value)
                  ─────────────────────────────────────────
Size:  Small  →  [ S/L ]         [ S/M ]   [ S/H ]
       Big    →  [ B/L ]         [ B/M ]   [ B/H ]
```

Every NYSE/AMEX/NASDAQ stock is sorted into one of these **six portfolios** each year. Then:

$$\mathrm{SMB} \;=\; \frac{1}{3}\,(S/L + S/M + S/H) \;-\; \frac{1}{3}\,(B/L + B/M + B/H)$$

$$\mathrm{HML} \;=\; \frac{1}{2}\,(S/H + B/H) \;-\; \frac{1}{2}\,(S/L + B/L)$$

**Plain English:**
- **SMB** = average return of the three *small* portfolios − average return of the three *big* portfolios. It isolates the pure **size** effect (value mix is held constant across both sides).
- **HML** = average return of the two *high-B/M* (value) portfolios − average return of the two *low-B/M* (growth) portfolios. It isolates the pure **value** effect (size is held constant across both sides).

> [!tip] Why "minus"?
> SMB and HML are constructed as **long-short spread portfolios** (also called zero-cost portfolios). You're long small, short big — so SMB *measures the premium*, not a raw return. That's why its sign can legitimately be positive or negative in any given year, and why $\beta_{\mathrm{SMB}}$ is a **tilt**, not a level.

---

## 4. Interpreting Factor Loadings — The Stock's "Personality"

The betas ($\beta_1, \beta_2, \beta_3$) are estimated by running a **time-series regression** of the stock's excess returns on the three factor returns:

$$R_{i,t} - R_{F,t} = \alpha_i + \beta_{i,1}(R_{M,t} - R_{F,t}) + \beta_{i,2}\mathrm{SMB}_t + \beta_{i,3}\mathrm{HML}_t + \varepsilon_{i,t}$$

The estimated $\hat\beta$'s tell you what the stock **behaves like**:

| Factor | Loading value | Stock personality |
|---|---|---|
| $\beta_1$ (Market) | Near 1.0 | Average market exposure |
| $\beta_1$ | > 1.0 | Cyclical / aggressive |
| $\beta_2$ (SMB) | **Positive** | Behaves like a **small-cap** (even if formally mid- or large-cap) |
| $\beta_2$ | **Negative** | Behaves like a **large-cap**, mega-cap tilt |
| $\beta_3$ (HML) | **Positive** | **Value** orientation (cheap, high B/M) |
| $\beta_3$ | **Negative** | **Growth** orientation (expensive, low B/M) |
| $\alpha_i$ (intercept) | Significantly > 0 | Genuine outperformance *after* controlling for size/value — a skilled manager (or a missing risk factor) |

> [!warning] Market Beta Changes Between Models
> The same stock will typically have a **different $\beta_1$ under Fama-French than under CAPM.** In CAPM, $\beta$ soaks up all systematic variation; in FF3, the size and value factors peel off part of that variation first, so the remaining market beta is cleaner (and usually smaller in magnitude).

See: [[CAPM]] · [[Multiple Regression - Basics and Assumptions]] · [[Factor Risk Premium]]

---

## 5. Worked Example — Three-Factor Cost of Equity

> **Scenario.** You're valuing **Acme Small Industrials, Inc.**, a small-cap value manufacturer. You've run a regression and estimated the factor loadings. Compute the required return.
>
> **Inputs**
> - Risk-free rate: $R_F = 4.0\%$
> - Equity risk premium: $\mathrm{ERP} = 5.5\%$, with $\beta_1 = 1.10$
> - Size premium: $\mathrm{SMB} = 2.5\%$, with $\beta_2 = 0.85$  *(strong small-cap tilt)*
> - Value premium: $\mathrm{HML} = 4.0\%$, with $\beta_3 = 0.60$  *(clear value tilt)*
>
> **Calculation**
> $$r_e = 4.0\% + (1.10)(5.5\%) + (0.85)(2.5\%) + (0.60)(4.0\%)$$
> $$r_e = 4.0\% + 6.05\% + 2.125\% + 2.40\% = \mathbf{14.58\%}$$
>
> **Interpretation.** A pure-CAPM version would have given $r_e = 4\% + 1.10(5.5\%) = 10.05\%$. The extra **4.5 percentage points** is the *risk compensation* investors demand because Acme carries both small-cap and value risk that CAPM simply ignores.

---

## 6. The Five-Factor Extension — Adding Quality

Fama and French (2015) kept finding that FF3 *still* left return patterns unexplained. Two new factors joined the lineup — both capturing **profitability and investment "quality."**

$$r_e = R_F + \beta_1\,\mathrm{ERP} + \beta_2\,\mathrm{SMB} + \beta_3\,\mathrm{HML} + \beta_4\,\mathrm{RMW} + \beta_5\,\mathrm{CMA}$$

| New factor | Full name | Construction | Economic story |
|---|---|---|---|
| **RMW** | **R**obust **M**inus **W**eak | High-operating-profitability firms *minus* low-profitability firms | Profitable firms earn persistent premia — "quality pays" |
| **CMA** | **C**onservative **M**inus **A**ggressive | Low-asset-growth (conservative) firms *minus* high-asset-growth (aggressive investment) firms | Firms that grow their asset base slowly tend to outperform empire-builders |

**Worked five-factor example:**

| Component | β | Premium | Contribution |
|---|---|---|---|
| Risk-free rate | — | 3.82% | 3.82% |
| ERP (market) | 1.20 | 6.50% | 7.80% |
| SMB (size) | 0.10 | 1.80% | 0.18% |
| HML (value) | −0.20 | 4.00% | −0.80% |
| RMW (profitability) | 0.50 | 2.00% | 1.00% |
| CMA (investment) | 0.20 | 1.00% | 0.20% |
| **Total $r_e$** | | | **12.20%** |

Notice the **negative HML loading** — this firm behaves like a growth stock, so the 4% value premium works *against* its expected return.

---

## 7. The Carhart Four-Factor Model — Adding Momentum

Before FF5 arrived, Mark Carhart (1997) noticed that **momentum** — the tendency of winners to keep winning over 3–12 month horizons — explained even more fund performance than FF3 alone.

$$r_e = R_F + \beta_1\,\mathrm{ERP} + \beta_2\,\mathrm{SMB} + \beta_3\,\mathrm{HML} + \beta_4\,\mathrm{WML}$$

| Factor | Name | Construction |
|---|---|---|
| **WML** (a.k.a. **UMD** — Up Minus Down) | **W**inners **M**inus **L**osers | Top-decile past-12-month return stocks *minus* bottom-decile past-12-month return stocks (typically skipping the most recent month to avoid reversal) |

The Carhart model is the **canonical benchmark for mutual fund evaluation** in L2 — it's what academics use when asking "did this manager genuinely beat the market, or were they just riding momentum?"

See: [[Using Multifactor Models]] · [[Carhart Four-Factor Model]]

---

## 8. Applications — Where Fama-French Actually Gets Used

### 8.1 Cost of Equity (Corporate Issuers context)

Private-company and small-cap valuations especially benefit from Fama-French, because CAPM systematically **under**-estimates required returns for exactly the stocks these models target. Analysts plug Fama-French $r_e$ into [[WACC]] and [[Discounted Cash Flow]] valuations.

### 8.2 Performance Attribution

Given a manager's monthly returns, run the Carhart-4 regression. The **intercept $\alpha$** is the manager's genuine skill. The **betas** reveal style tilts. A "stock picker" with high $\alpha$ and near-zero style betas is actually adding value. A manager with zero $\alpha$ but large positive $\beta_{\mathrm{SMB}}$ and $\beta_{\mathrm{HML}}$ is just **tilting into well-known premia** — you could replicate them with ETFs for ten basis points.

$$\underbrace{R_p - R_F}_{\text{active return}} = \alpha + \underbrace{\sum_k \beta_k f_k}_{\text{factor tilts}} + \varepsilon$$

### 8.3 Style Analysis

Does a "Large-Cap Value" fund actually hold large-cap value stocks? Check the loadings:
- $\beta_{\mathrm{SMB}}$ should be *negative* (large-cap tilt)
- $\beta_{\mathrm{HML}}$ should be *positive* (value tilt)

If the loadings disagree with the name, that's **style drift** — a red flag for institutional allocators.

### 8.4 Risk Budgeting

Decompose portfolio variance into factor-attributed pieces. A portfolio that looks diversified by sector may actually have 80% of its active risk in the **value** factor alone — FF exposes that.

---

## 9. Comparison — CAPM vs. APT vs. Fama-French

| Dimension | CAPM | [[Arbitrage Pricing Theory\|APT]] | Fama-French / Carhart |
|---|---|---|---|
| **# of factors** | Exactly 1 (market) | Unspecified ($K$) | FF3 = 3, FF5 = 5, Carhart = 4 |
| **Foundation** | Equilibrium (mean-variance) | No-arbitrage | **Empirical** — found in the data |
| **Factor identity** | Theory-specified (market) | Silent — researcher chooses | Specific: market, SMB, HML, (RMW, CMA, WML) |
| **Factor nature** | Market return | Macro shocks / surprises | Fundamental attributes (size, B/M, profitability, investment) |
| **Utility assumptions** | Yes (mean-variance) | None | None |
| **Market portfolio required** | Yes | No | Used but not required to be "the" MKT |
| **Primary use case** | Simple benchmark; teaching | Flexible academic research | **Manager evaluation, style analysis, cost of equity** |

> [!tip] The Family Tree
> **APT** is the theoretical scaffold (general $K$-factor pricing). **Fama-French** is the most successful *empirical* filling-in of APT's blanks — specific factors, specific construction, industrial-strength datasets (Ken French's data library is the de-facto standard).

---

## 10. Limitations and Critiques

| Critique | The argument | Why it matters for L2 |
|---|---|---|
| **Data mining / snooping** | Factors were *discovered* by regressing returns on firm attributes — no ex-ante economic theory predicted SMB or HML | You should always be skeptical of purely empirical factors; ask whether they survive out-of-sample |
| **Model disagreement** | CAPM, FF3, FF5, and Carhart-4 give **different** $r_e$ for the same stock | Cost-of-equity estimates carry genuine model-choice uncertainty |
| **Beta instability** | Market β in FF3 ≠ CAPM β because other factors absorb return variation | Never mix a CAPM β with FF premia or vice versa |
| **Factor decay** | Premia (esp. SMB) have shrunk post-publication as investors arbitraged them | A back-tested factor premium overstates what you'll actually earn going forward |
| **Data-hungry** | Needs long time series and reliable accounting data (book value, profitability) | Hard to apply to emerging-market or very young firms |
| **Correlated factors** | HML and CMA are empirically correlated — multicollinearity inflates standard errors | Interpret individual loadings with caution in FF5 |

---

## 11. Quick-Reference Cheat Sheet

| Model | # Factors | Equation (after $R_F$) |
|---|---|---|
| **CAPM** | 1 | $\beta_M(R_M - R_F)$ |
| **Fama-French 3F** | 3 | $\beta_1\mathrm{ERP} + \beta_2\mathrm{SMB} + \beta_3\mathrm{HML}$ |
| **Carhart 4F** | 4 | FF3 + $\beta_4\mathrm{WML}$ |
| **Fama-French 5F** | 5 | FF3 + $\beta_4\mathrm{RMW} + \beta_5\mathrm{CMA}$ |

> [!tip] Sign Conventions to Memorize
> | Factor | Positive loading means… |
> |---|---|
> | SMB | Small-cap tilt |
> | HML | Value tilt |
> | WML / UMD | Momentum / trend-chaser |
> | RMW | Quality / high-profitability tilt |
> | CMA | Low-investment, disciplined-capital tilt |

---

## 12. LOS Discharge Checklist

After reading this note, you should be able to:

- [x] **Describe** the Fama-French three-factor model and its motivation.
- [x] **Explain** the construction of the SMB and HML factor portfolios via the 2×3 double sort.
- [x] **Compare** Fama-French with CAPM and APT (factors, foundations, use cases).
- [x] **Interpret** factor loadings as style tilts (small/large, value/growth, momentum, quality).
- [x] **Calculate** a cost of equity using FF3, FF5, or Carhart-4 given betas and factor premia.
- [x] **Describe** the Carhart four-factor model and the role of WML / momentum.
- [x] **Describe** the five-factor model and the role of RMW and CMA.
- [x] **Apply** Fama-French in three canonical contexts: cost of equity, performance attribution, style analysis.
- [x] **Critique** the Fama-French framework (data mining, factor decay, multicollinearity).

---

## Related Notes

- [[Using Multifactor Models]] — parent note covering APT, risk/return attribution, information ratio
- [[Cost of Capital - Advanced Topics]] — cost of equity model comparisons
- [[CAPM]] · [[Arbitrage Pricing Theory]] · [[Carhart Four-Factor Model]]
- [[SMB]] · [[HML]] · [[Momentum]] · [[Factor Risk Premium]]
- [[Multiple Regression - Basics and Assumptions]] — estimation technique for factor loadings
- [[Active Risk]] · [[Tracking Error]] · [[Information Ratio]]
