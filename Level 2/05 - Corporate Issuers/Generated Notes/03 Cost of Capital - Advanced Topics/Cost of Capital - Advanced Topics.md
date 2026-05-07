---
title: "Cost of Capital: Advanced Topics"
subject: "05 - Corporate Issuers"
tags: [CFA-L2, corporate-issuers, cost-of-capital, WACC, CAPM, ERP, beta, capital-structure]
aliases: ["Module 3 Cost of Capital", "Advanced WACC", "Cost of Capital Advanced"]
---

# Cost of Capital: Advanced Topics

> [!tldr] What This Module Is Really About
> Every firm "rents" money from two landlords — **bondholders** (debt) and **shareholders** (equity). The **rent** it pays, weighted by how much of each it uses, is its **[[WACC|Weighted Average Cost of Capital]]**. Level 1 taught you the textbook formula. Level 2 is about the *messy real world*: What if the bonds don't trade? What if the company is private? What if you're valuing a Brazilian steel mill with data from a US peer? What if the Equity Risk Premium you read in a textbook is 7% but your DDM says 4%? This module teaches you the *judgment calls*.

---

## The Anchoring Analogy: Apple, April 2026

Let's ground this in a real company before we touch a single formula. As of **April 16, 2026**, Apple's market data looks like this (pulled live from financialdatasets):

| Item | Value | Source |
|---|---|---|
| Share price | **$263.91** | Live quote (2026-04-16) |
| Shares outstanding | 14.776 B | FY2025 10-K (period ending 2025-09-27) |
| **Market cap (E)** | **≈ $3,900 B** | Price × shares |
| Total debt (D) | **$111.5 B** | FY2025 10-K |
| Cash & equivalents | $35.9 B | FY2025 10-K |
| Shareholders' equity (book) | $73.7 B | FY2025 10-K |

Notice something strange? Apple's **book equity** is only $73.7 B, but its **market equity** is $3.9 *trillion*. That gap — ~53× — is why CFA Level 2 hammers *market-value weights*, never book-value weights, in the WACC.

Apple's capital mix, by market value:

```
Total capital (V) = E + D = 3,900 + 111.5 = 4,011.5 B

w_e  = 3,900   / 4,011.5  =  97.2 %   ← equity finances almost everything
w_d  =   111.5 / 4,011.5  =   2.8 %   ← a whisper of debt
```

Hold onto this. We'll return to it at the end and actually compute Apple's WACC. The *reason* it's 97/3 and not 50/50 — why Tim Cook doesn't just crank up cheap tax-deductible debt and lower the WACC — is the whole capital-structure story in LOS 6.

> [!note] Mnemonic: The Landlord Metaphor
> - **Cost of debt** = what the bank landlord charges (contractual, senior, tax-deductible)
> - **Cost of equity** = what the shareholder landlord *demands* (residual, subordinated, not deductible)
> - **WACC** = blended rent, weighted by how much space each landlord owns
> - **Advanced topics** = everything that goes wrong when the rent isn't quoted on a signboard

---

## Module Map

![[Cost of Capital Map.png]]

---

## LOS 1 — Top-Down and Bottom-Up Factors

Imagine you're a coffee shop owner asking the bank for a loan. Two forces set your rate: **the weather outside the bank** (macro conditions — Fed policy, recession fears, inflation) and **how you run your shop** (cash flow stability, collateral, how leveraged you already are). CFA calls these **top-down** and **bottom-up** factors. They stack *additively* on top of the risk-free rate to produce the final cost of capital an investor demands.

### Top-Down (Macro) Factors — You Can't Control These

| Factor | What it does | Direction |
|---|---|---|
| **Capital availability** | Deep liquid markets (US, EU) mean lots of money chasing deals; shallow markets (EM) mean scarce capital and a reliance on expensive bank/shadow lending | Deep markets ↓ cost; shallow ↑ |
| **Interest rates & inflation** | Lenders demand compensation for purchasing-power loss. When inflation rises, nominal rates rise | Higher inflation ↑ cost |
| **Recession / risk appetite** | In downturns, investors demand wider spreads and bigger ERPs | Recession ↑ cost |
| **Legal & country risk** | Common-law jurisdictions with strong investor protections attract cheaper capital; politically unstable countries get charged a **Country Risk Premium (CRP)** | Weak rule of law ↑ cost |
| **Tax jurisdiction** | Interest is tax-deductible in most countries; higher corporate tax rates actually *lower* the after-tax cost of debt: $r_d(1-t)$ | Higher $t$ ↓ after-tax $r_d$ |
| **Capital flows** | Global "risk-on" flows into an emerging market strengthen its currency and compress local spreads | Inflows ↓ cost |

### Bottom-Up (Firm-Specific) Factors — Management's Fingerprint

| Factor | Low-risk version | High-risk version |
|---|---|---|
| **Revenue / earnings volatility** | Utility, SaaS subscription | Luxury autos, semis, construction |
| **Asset nature / liquidity** | Tangible, fungible (real estate, aircraft) — serves as collateral | Intangible (code, brand) — hard to repossess |
| **Financial strength / leverage** | Low D/E, high interest coverage | "Maxed-out credit card" firm |
| **Security features** | Convertibles (investors accept lower yield for equity upside) | Subordinated, no covenants |
| **ESG risks** | Clean governance, no litigation | Environmental liabilities, scandals |

> [!tip] Intuition Check
> Two companies on the same block with identical products can face *very different* costs of capital if one has volatile sales and intangible assets, while the other has steady subscriptions and a warehouse full of machines.

---

## LOS 2 — Estimating the Cost of Debt

The cost of debt is **the yield a lender would demand *today* for new debt** with the same seniority, maturity, and features as the firm's existing debt. Crucially, it's **not** the historical coupon rate on old bonds sitting on the balance sheet — that was the rent negotiated years ago; we want today's rent.

### Method 1: Yield-to-Maturity on Publicly Traded Bonds

When a firm has **actively traded straight bonds**, just use the YTM of the longest-maturity issue. A "straight" bond means plain-vanilla — no embedded options. YTM is the IRR that discounts coupons and principal to the current bond price:

$$
P_0 = \sum_{t=1}^{N} \frac{C}{(1+\text{YTM})^t} + \frac{F}{(1+\text{YTM})^N}
$$

If the longest bond is thinly traded, step down to a shorter maturity with reliable pricing.

### Method 2: Matrix Pricing (Thinly-Traded Bonds)

If XYZ Corp's 6-year BBB bond doesn't trade, but you have yields on BBB bonds with 4-year and 7-year maturities, you **linearly interpolate**:

$$
\text{YTM}_{6yr} = \text{YTM}_{4yr} + \frac{6-4}{7-4} \times (\text{YTM}_{7yr} - \text{YTM}_{4yr})
$$

**Worked example.** Suppose:
- BBB 4-year YTM = 5.00%
- BBB 7-year YTM = 5.60%

Then:
$$
\text{YTM}_{6yr} = 5.00\% + \tfrac{2}{3} \times (5.60\% - 5.00\%) = 5.00\% + 0.40\% = 5.40\%
$$

### Method 3: Synthetic Credit Rating (No Rating / Private Firm)

When the firm has no agency rating, reverse-engineer one from financial ratios. The two workhorses:

$$
\text{Interest Coverage} = \frac{\text{EBIT}}{\text{Interest Expense}}, \qquad \text{D/E} = \frac{\text{Total Debt}}{\text{Equity}}
$$

You look up which rating bucket these ratios correspond to (Damodaran publishes free tables), then take today's **credit spread** for that rating and add it to the risk-free rate:

$$
r_d = R_f + \text{Credit Spread}_{\text{synthetic rating}}
$$

### Method 4: Floating-Rate Debt

Floating bonds reset coupons to a benchmark (e.g., **SOFR**) plus a fixed **quoted margin (QM)**. If the bond trades at par:

$$
r_d = \text{Benchmark} + \text{QM}
$$

If it trades at a discount or premium, compute the **discount margin (DM)** — the margin that, when added to expected benchmarks, discounts expected cash flows to the current price.

### Method 5: Adjustments for Embedded Options & Seniority

Bond features tilt the yield relative to a plain-vanilla bond of the same credit:

| Feature | Who benefits? | Effect on yield |
|---|---|---|
| **Callable** | Issuer (can refinance if rates fall) | ↑ yield (issuer pays for the option) |
| **Putable** | Investor (can sell back if rates rise) | ↓ yield (investor pays via lower rate) |
| **Convertible** | Investor (equity upside) | ↓ yield |
| **Secured / Senior** | Investor (lower default loss) | ↓ yield |
| **Subordinated** | Investor bears higher loss | ↑ yield |

### Method 6: Country Risk Premium (CRP) for EM Debt

When the issuer is in a developing market, add a CRP on top of the peer-country yield:

$$
r_{d, \text{local}} = r_{d, \text{developed peer}} + \text{CRP}
$$

CRP is typically the **sovereign yield spread** — the difference between the emerging country's USD-denominated sovereign bond yield and the US Treasury of the same maturity.

---

## LOS 3 — Estimating the Equity Risk Premium (ERP)

The **ERP** is the extra return investors demand for holding the market portfolio instead of a risk-free bond. It's the single most consequential — and most disputed — input in equity valuation. A 1% change in ERP can swing a DCF valuation by 20%+.

$$
\text{ERP} = E(R_m) - R_f
$$

### Historical Approach — "Rearview Mirror"

Take a long sample of index returns minus T-bill/bond returns, average them, call that ERP.

**Four key judgment calls:**

| Choice | Option A | Option B | Trade-off |
|---|---|---|---|
| Sample length | Short (20y) | Long (100y+) | Short = current regime; long = more data, less statistical noise |
| Frequency | Monthly | Annual | Monthly = more obs; annual = matches long-run holding periods |
| Risk-free proxy | T-bill (short) | T-bond (long) | Match to horizon of the valuation |
| Mean type | **Arithmetic** | **Geometric** | Arithmetic better for *one-period* forecasts; Geometric better for *multi-period compounding* |

**Arithmetic vs. Geometric — why the difference matters.** Suppose returns over three years are +50%, −50%, +50%.

- **Arithmetic mean** = (50 − 50 + 50)/3 = **+16.7%** per year
- **Geometric mean** = $\sqrt[3]{1.5 \times 0.5 \times 1.5} - 1 = \sqrt[3]{1.125} - 1 =$ **+4.0%** per year

A dollar at the start ends at $1 × 1.5 × 0.5 × 1.5 = \$1.125$, which is consistent with +4.0% compounded, **not** +16.7%. The arithmetic mean overstates terminal wealth whenever returns vary. For **multi-year** cost-of-capital inputs, use geometric (or a blend).

**Pitfalls of historical ERP:**
1. **Survivorship bias** — indexes quietly drop failing firms, so realized returns look better than what an investor actually earned. The classic Jorion-Goetzmann study found that US outperformance vs. other markets halves once you include countries whose markets collapsed (Russia 1917, China 1949).
2. **Non-stationarity** — the 1950s world (fixed-rate regime, post-war reconstruction) doesn't predict the 2020s (AI, QE, deglobalization).
3. **Series bias** — choice of start/end date can swing the estimate 200 bps.

### Forward-Looking Approach — "Windshield View"

#### (a) Survey-Based
Ask CFOs, academics, portfolio managers what ERP they expect. **Problem:** recency bias (respondents anchor on the last 6 months of returns) and selection (who answers surveys?).

#### (b) DDM-Implied ERP (Gordon Growth)
Solve the Gordon model for the market's implied required return, then subtract $R_f$:

$$
\text{ERP} = \underbrace{\frac{D_1}{P_0}}_{\text{forward div yield}} + \underbrace{g}_{\text{expected growth}} - R_f
$$

**Assumption landmine:** constant P/E forever. In reality, multiples mean-revert.

#### (c) Grinold-Kroner Macro Model — the "Deluxe" Forward Model

This decomposes the equity return into five observable pieces:

$$
E(R_e) = \underbrace{\frac{D}{P}}_{\text{div yield}} + \underbrace{i}_{\text{inflation}} + \underbrace{g}_{\text{real earnings growth}} + \underbrace{\Delta \text{PE}}_{\text{repricing}} - \underbrace{\Delta S}_{\text{dilution}}
$$

then subtract $R_f$ for the ERP.

**Worked example — US equity, April 2026 flavor:**

| Component | Estimate | Source logic |
|---|---|---|
| Dividend yield | 1.6% | S&P 500 trailing |
| Expected inflation | 2.3% | TIPS breakeven |
| Real earnings growth | 2.0% | Long-run real GDP proxy |
| Repricing ($\Delta$ PE) | 0.0% | Assume mean-revert → no change |
| Net buyback yield ($-\Delta S$) | +1.0% | Buybacks > issuance |
| **Expected market return** | **6.9%** | sum |
| Risk-free (10y T-note) | 4.2% | current |
| **Implied ERP** | **2.7%** | 6.9 − 4.2 |

Notice the Grinold-Kroner ERP (≈2.7%) is much lower than the historical long-run ERP (≈5%). That gap is the *entire debate* in practitioner equity research: is the world structurally lower-return now, or are we underestimating growth?

---

## LOS 4 — Required Return on Equity: The Model Zoo

No single model dominates. Each makes different assumptions about what drives expected return. Here's the full lineup:

### Comparison Table

| Model | Formula | Best for | Key weakness |
|---|---|---|---|
| **CAPM** | $r_e = R_f + \beta (\text{ERP})$ | Large, diversified public firms | Single-factor; misses size/value |
| **Fama-French 3F** | $r_e = R_f + \beta_1 \text{ERP} + \beta_2 \text{SMB} + \beta_3 \text{HML}$ | Small-cap, value tilts | Factors not stable across decades |
| **Fama-French 5F** | adds $\beta_4 \text{RMW} + \beta_5 \text{CMA}$ | Profitability/investment-style analysis | Over-fitting risk; data-hungry |
| **Build-up** | $r_e = R_f + \text{ERP} + \text{SP} + \text{IP} + \text{SCRP}$ | Private firms, no peer beta | Subjective premium sizing |
| **Bond Yield + Risk Premium (BYPRP)** | $r_e = r_d + \text{RP}$ (RP typically 3–5%) | Sanity check when firm has traded bonds | Crude; RP is a plug |
| **CAPM + CRP** | $r_e = R_f + \beta(\text{ERP}_{DM} + \lambda \cdot \text{CRP})$ | Emerging-market firms | Choosing $\lambda$ (exposure) is judgment |

### CAPM — Still the Workhorse

$$
r_e = R_f + \beta \cdot (\text{ERP})
$$

- $R_f$: match maturity to valuation horizon (10y or 20y government).
- $\beta$: regression slope of stock returns on market returns (raw β), often **Blume-adjusted** toward 1:
$$\beta_{\text{adj}} = \tfrac{2}{3}\beta_{\text{raw}} + \tfrac{1}{3}(1.0)$$
- **ERP**: forward or historical per LOS 3.

### Fama-French Factors Explained

| Factor | What it captures | Why it's a risk |
|---|---|---|
| **SMB** (Small Minus Big) | Return of small-cap − large-cap | Small firms are more prone to distress |
| **HML** (High Minus Low) | Value − growth (high B/M minus low B/M) | Value stocks are often distressed, recover unevenly |
| **RMW** (Robust Minus Weak) | Profitable − unprofitable | Profitability predicts return |
| **CMA** (Conservative Minus Aggressive) | Low-investment − high-investment | Firms that invest aggressively tend to underperform |

### Build-Up for Private Firms

$$
r_e = R_f + \text{ERP} + \underbrace{\text{SP}}_{\text{size}} + \underbrace{\text{IP}}_{\text{industry}} + \underbrace{\text{SCRP}}_{\text{specific-company}}
$$

No β, because no traded price series. You "build up" the return by adding each identifiable risk premium.

### Country-Risk-Adjusted CAPM

$$
r_e = R_f + \beta [\text{ERP}_{\text{mature}} + \lambda \cdot \text{CRP}]
$$

where $\lambda \in [0, 1]$ measures the firm's exposure to the local country (1.0 = fully local, 0 = fully international). **Refined CRP** (Damodaran):

$$
\text{CRP} = \text{Sovereign Yield Spread} \times \frac{\sigma_{\text{equity index}}}{\sigma_{\text{sovereign bond}}}
$$

The volatility ratio scales the bond-market risk premium up to equity-market units.

---

## LOS 5 — Public vs. Private: The Beta Problem

Private companies have **no traded stock** → no β → can't run CAPM directly. The workaround is the **pure-play method** (a.k.a. guideline public company method):

> [!abstract] Pure-Play Method — The Five Steps
> 1. Identify a publicly traded peer (or several) in the same business.
> 2. Pull the peer's **levered** β from its stock returns.
> 3. **Unlever** to strip out peer's capital structure → get pure *business* risk.
> 4. **Relever** using the *private firm's* capital structure.
> 5. Plug the new β into CAPM.

### Unlever / Relever Formulas

**Unlever the peer:**
$$
\beta_{U} = \frac{\beta_{L, \text{peer}}}{1 + (1-t_{\text{peer}}) \cdot (D/E)_{\text{peer}}}
$$

**Relever for the private firm:**
$$
\beta_{L, \text{private}} = \beta_{U} \cdot \left[1 + (1 - t_{\text{private}}) \cdot (D/E)_{\text{private}}\right]
$$

### Worked Example — Valuing "PrivateCo"

PrivateCo is a private software firm. Peer is SaaSCo (public).

| Input | SaaSCo (peer) | PrivateCo |
|---|---|---|
| Levered β | 1.40 | — |
| D/E | 0.25 | 0.80 |
| Tax rate | 21% | 21% |

**Step 1 — Unlever SaaSCo:**
$$
\beta_U = \frac{1.40}{1 + (1 - 0.21)(0.25)} = \frac{1.40}{1 + 0.1975} = \frac{1.40}{1.1975} = 1.169
$$

**Step 2 — Relever for PrivateCo:**
$$
\beta_{L, \text{Priv}} = 1.169 \times [1 + (1 - 0.21)(0.80)] = 1.169 \times [1 + 0.632] = 1.169 \times 1.632 = 1.908
$$

**Step 3 — CAPM with $R_f$ = 4.2%, ERP = 5%:**
$$
r_e = 4.2\% + 1.908 \times 5.0\% = 4.2\% + 9.54\% = 13.74\%
$$

PrivateCo's higher D/E drives β from 1.17 to 1.91 — a 360-bp jump in required return, purely from capital structure.

### Illiquidity & Control Discounts

Once you've valued PrivateCo as if it were liquid, you apply two further discounts:

| Discount | Meaning | Typical size |
|---|---|---|
| **DLOM** — Discount for Lack of Marketability | Can't sell quickly; private shares are "stuck" | 15–35% |
| **DLOC** — Discount for Lack of Control | Minority stake with no board seats | 10–25% |

**Combined (multiplicative, not additive):**
$$
\text{Total Discount} = 1 - (1 - \text{DLOC})(1 - \text{DLOM})
$$

**Example:** DLOC = 20%, DLOM = 25%.
$$
1 - (1 - 0.20)(1 - 0.25) = 1 - 0.80 \times 0.75 = 1 - 0.60 = 40\%
$$

---

## LOS 6 — Benchmarking a Firm's Capital Structure

WACC without context is just a number. An 8% WACC is cheap for a biotech and expensive for a utility. You have to compare.

### Two Competing Theories of Capital Structure

| | **Trade-off Theory** | **Pecking Order Theory** |
|---|---|---|
| **Core idea** | Firms balance the **tax shield** of debt vs. **cost of financial distress** | Firms prefer the cheapest, least-informative financing source first |
| **Optimal point?** | Yes — where marginal tax benefit = marginal distress cost | No single optimum; just a preference order |
| **Order of funding** | Mix to minimize WACC | 1. Retained earnings → 2. Debt → 3. New equity |
| **Equity issuance signal** | Neutral | **Negative** (stock is likely overvalued) |

### The Optimal Capital Structure (Trade-Off View)

![[Optimal Capital Structure.png]]

At the **minimum** of the WACC curve, the marginal tax benefit of adding one more dollar of debt exactly equals the marginal cost of increased financial distress. Left of that point, the tax shield is still winning — the firm is *under-levered*. Right of it, distress costs dominate — the firm is *over-levered*. The Apple dot sits way out on the left, far from the theoretical optimum — yet management stays there deliberately, trading some WACC-efficiency for strategic flexibility and near-zero distress risk.

### Signals from Peer Comparison

| If firm's WACC < peers | If firm's WACC > peers |
|---|---|
| Stable, predictable revenue | Cyclical / high operating leverage |
| Tangible, liquid collateral | Intangible assets, hard to repossess |
| Strong ESG standing | ESG controversies or liabilities |
| Diversified customer base | Customer concentration |
| Investment-grade rating | Speculative-grade, wide spreads |
| Key person / succession plan | Founder-dependent, no succession |
| Near-optimal D/V | Under-levered (wasting tax shield) or over-levered (distress risk) |

### Common Capital-Structure Red Flags

1. **Under-leveraged cash-cow** (e.g., Apple!): could issue more debt to buy back stock and lower WACC, but may be constrained by international cash tax frictions or optionality value of flexibility.
2. **Over-leveraged cyclical**: WACC looks low today but blows up in a downturn.
3. **Mismatched maturities**: short-term debt funding long-term assets → refinancing risk.
4. **Currency mismatch**: borrowing USD to fund local-currency cash flows in an EM.

---

## Returning to Apple: A Full WACC Walkthrough

Let's compute Apple's WACC with plausible April 2026 inputs.

### Step 1 — Weights (market values)

```
E = $3,900 B         w_e = 97.22%
D = $111.5 B         w_d =  2.78%
V = $4,011.5 B
```

### Step 2 — Cost of Debt

Apple is rated **AA+** (S&P). Its long-dated bonds yield roughly **T + 80 bps**. With 10y UST at 4.2%:
$$
r_d = 4.2\% + 0.80\% = 5.0\%
$$
Apple's US effective tax rate ≈ 16% (mixed domestic/foreign), so:
$$
r_d (1 - t) = 5.0\% \times (1 - 0.16) = 4.20\%
$$

### Step 3 — Cost of Equity (CAPM)

- $R_f$ = 4.2% (10y UST)
- β ≈ 1.20 (regression estimate)
- ERP: historical says 5%, Grinold-Kroner says ~3%. Call it **4.5%** as a blend.

$$
r_e = 4.2\% + 1.20 \times 4.5\% = 4.2\% + 5.4\% = 9.60\%
$$

### Step 4 — Cross-Check with BYPRP

Apple's bond yield = 5.0%; add a 4% equity risk premium:
$$
r_e \approx 5.0\% + 4.0\% = 9.0\%
$$

The BYPRP ≈ 9.0% is close to CAPM's 9.6%. ✓

### Step 5 — Blend

$$
\text{WACC} = w_e \cdot r_e + w_d \cdot r_d(1-t)
$$
$$
\text{WACC} = 0.9722 \times 9.60\% + 0.0278 \times 4.20\% = 9.332\% + 0.117\% = \boxed{9.45\%}
$$

### The Teaching Moment

At Apple's 97/3 mix, **WACC ≈ cost of equity**. The tax-shield benefit of debt is almost invisible. Why doesn't Apple lever up to, say, 40/60 debt/equity and slash its WACC?

- **Cash flow volatility is low, but asset collateral quality is mostly intangible** (brand, IP).
- **Trade-off theory answer**: the PV of financial distress for a firm whose brand could be damaged by any whiff of trouble is huge. Management keeps a war chest.
- **Pecking-order answer**: Apple generates ~$100 B/year of free cash flow — it never *needs* external capital, so why issue?
- **Signaling**: issuing debt to buy back stock *does* happen (Apple has issued ~$120 B of bonds over the past decade), but calibrated to keep ratings AA+.

This is exactly the peer-benchmarking exercise LOS 6 asks you to do — and the answer is that Apple's capital structure, though it *looks* inefficient on a pure textbook WACC-minimization basis, is optimal once you price in distress costs, strategic optionality, and market signaling.

---

## Memory Hooks

> [!tip] The Four "Too"s of Cost of Capital
> 1. **Too small** (size premium → build-up)
> 2. **Too private** (no β → pure-play method)
> 3. **Too foreign** (country risk → CRP adjustment)
> 4. **Too weird** (embedded options → feature-specific adjustment)

> [!tip] The Order of the Pecking Order (mnemonic: "RICH DIE SILENT")
> **RICH**: Retained earnings first (cheapest)
> **DIE**: Debt next
> **SILENT**: Stock last (issuing is a Signal — market assumes overvaluation)

> [!tip] Beta Unlever / Relever — Remember the Tax Term
> "(1 − t) lives with every D/E." The tax shield makes debt look like less leverage, so unlevering β divides by more when $t$ is lower.

> [!tip] Arithmetic vs. Geometric — Holding Period Match
> One-year forecast → **arithmetic** mean. Multi-year compounding → **geometric** mean. Arithmetic always ≥ geometric (with equality only when returns have zero variance).

---

## Related Notes

- [[WACC|Weighted Average Cost of Capital]] — the base-case formula
- [[CAPM]] — single-factor model foundations
- [[Equity Risk Premium]] — deeper ERP dive
- [[Beta|Beta & Systematic Risk]]
- [[Capital Structure Theory]] — Modigliani-Miller through Trade-off
- [[Country Risk Premium]]
- [[Dividend Discount Model]]
- [[Gordon Growth Model]]
- [[Fama-French Factor Models]]
- [[Free Cash Flow Valuation]] — where WACC is used

---

## Practice

See `Practice Questions/05 - Corporate Issuers/Cost of Capital Advanced/` for drills on: synthetic ratings, unlever/relever β, Grinold-Kroner ERP, peer WACC benchmarking, and build-up method.
