---
title: "Private Company Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments]
aliases: []
---

# Private Company Valuation (CFA L2 — Module 6)

---

## The Big Picture

Imagine you want to buy a local restaurant chain that isn't listed on any stock exchange. You can't just look up a ticker symbol and see what "the market" thinks it's worth. There's no daily share price, no SEC filings, and the owner's mom is on the payroll at $300k/year for "consulting." Welcome to the world of [[Private Company Valuation]].

The core idea is **the same** as valuing a [[public company]] — you're still trying to figure out the [[present value]] of future [[cash flows]]. But the **inputs** are messier, the **discount rates]] need extra adjustments, and the final number may need **discounts** or **premiums** tacked on depending on who's buying what kind of stake.

Think of it like buying a used car with no Kelley Blue Book price. The engine is the same (DCF math), but you have to kick the tires a lot harder.

---

## 1. Public vs. Private Company Features

### Why This Matters

Before you value anything, you need to know **what makes private companies different**. These differences affect every number you plug into a model — the [[cash flows]] (numerator), the [[Discount rate]] (denominator), and any final adjustments (premiums/discounts).

### Company-Specific Factors

These are about the **business itself**:

| Factor | Public Company | Private Company | Why It Matters for [[Valuation|Valuation]] |
|---|---|---|---|
| **[[Life Cycle Stage]]** | Usually mature | Often early-stage or late-stage (near [[Liquidation]]) | Determines which [[Valuation|valuation]] model to use |
| **Size** | Larger, more resources | Smaller, fewer assets & employees | Smaller = riskier = higher [[Discount rate]] |
| **Management Depth** | Professional management, separated from owners | Owner often IS the manager | Reduces [[principal-agent conflict]], but limits talent pool |
| **Disclosure Quality** | [[Audited financial statements]], regulated | May be only "reviewed" or "compiled" — less reliable | More uncertainty = more adjustments needed |
| **Time Horizon** | Short-term pressure (quarterly earnings) | Longer-term focus (owners = managers) | Affects growth assumptions |
| **Tax Sensitivity** | Less direct impact on individuals | Owner's personal taxes tied to firm | May distort reported earnings |

### Stock-Specific Factors

These are about the **shares themselves** — and they're almost always **negative** for private companies:

| Factor | Effect | Why |
|---|---|---|
| **[[Illiquidity]]** | Decreases value | Can't easily sell your shares on a market — you're stuck |
| **Sale Restrictions** | Decreases value | [[Shareholder agreements]] may literally prevent you from selling |
| **[[Concentrated Control]]** | Can decrease value for minorities | A few shareholders call the shots; minority holders have little say |

> **Real-World Example:** Two partners each own 35% of a company, three others own 10% each. The two big partners can team up to form a 70% controlling block. The 10% holders? They'd need all three to coordinate just to reach 30%. On a **per-share basis**, the 35% stakes are worth more because of their potential to create [[control]].

---

## 2. Uses of Private Business Valuation

### Why Do We Value Private Companies?

There are three broad reasons, and they affect **how** you do the [[Valuation|valuation]]:

### Transaction-Related Valuations

These happen when **ownership or financing changes hands**:

- **[[Venture capital]] Financing:** Early-stage firms need cash. VC investors negotiate a value, often informally, because future [[cash flows]] are highly uncertain. Think of a startup pitching for Series A funding — the [[Valuation|valuation]] is more art than science at that stage.
- **[[IPO]] ([[Initial public offering|Initial Public Offering]]ng|Public Offering]]):** When a company goes public, [[Investment banks|investment banks]] value it using comparable public firms as benchmarks.
- **Sale / [[Acquisition]]:** A mature private firm being sold needs a [[Fair value|fair value]]. Both buyer and seller do [[Independent|independent]] valuations, then negotiate.
- **[[Bankruptcy]]:** Should the firm be liquidated or reorganized? Accurate valuation determines the path.
- **Share-Based Compensation:** If employees get [[stock options]] or [[restricted stock]], you need to know what they're worth for accounting and tax purposes.
- **Debt Financing:** Lenders want to know what they're lending against.

### Compliance-Related Valuations

These are legally or regulatorily required:

- **Financial Reporting:** [[Goodwill impairment]] testing requires valuing business units using private company methods.
- **Tax Purposes:** Transfer pricing, property taxes, estate & gift taxes all need valuations.

### Litigation-Related Valuations

Courts require valuations for:

- Shareholder disputes
- Damage claims
- Divorce settlements

> **Key Insight:** Most appraisers **specialize** in one area because the skill sets are so different. Investment bankers handle transactions. Accountants handle compliance. Lawyers handle litigation.

---

## 3. Three Areas of Focus for Analysts

![[Private-Company-Valuation-Framework.excalidraw]]

No matter why you're valuing a private company, you always need to address three things:

```
           VALUATION = Cash Flow (Numerator)
                        ─────────────────────
                        Discount Rate (Denominator)
                        
                        × Premiums/Discounts (Adjustments)
```

1. **[[Earnings Normalization]] / Cash Flow Issues** → Fixes the numerator
2. **[[Discount rate]] / Rate of Return Adjustments** → Fixes the denominator
3. **Valuation [[Discounts and Premiums]]** → Final adjustments for control and marketability

---

## 4. Earnings Normalization and Cash Flow Estimation

### What Are [[Normalized earnings]]?

**Definition:** [[Normalized earnings]] are what the company *would* earn if it were acquired and run efficiently by new, professional management. You're stripping away all the quirks of the current private ownership to get a clean baseline for forecasting.

This is different from the public-company concept of "normalized earnings" (which adjusts for [[Business cycle]] effects). Here, we're adjusting for **private company-specific distortions**.

### Why Normalize?

Private companies mix business and personal expenses all the time. The owner might:

- Pay themselves $1.5M when market compensation is $500K
- Run a ranch and a condo through the company books
- Lease a warehouse from a buddy at below-market rates
- Not pay themselves at all (making earnings look great when they shouldn't)

If you don't fix these, your [[DCF model]] will spit out garbage.

### Common Adjustments

| Issue | What to Do | Direction |
|---|---|---|
| **Above-market compensation** | Reduce to market rate | Increases earnings |
| **Below-market compensation** | Increase to market rate | Decreases earnings |
| **Personal assets** on company books (ranch, condo, jet) | Remove related expenses & depreciation | Increases earnings |
| **Non-arm's-length lease rates** | Adjust to market rates | Could go either way |
| **Related-party transactions** | Adjust to fair market value | Could go either way |
| **Nonrecurring items** | Remove them | Could go either way |
| **Real estate** owned by firm | Separate from operations; use market rental expense | Depends on situation |

### Worked Example: Normalizing Earnings for FLI

**Setup:** Fyt for Life, Inc. (FLI) is owned by Cheryl Xin. A private equity analyst, Dev Khan, is evaluating FLI for purchase.

**Reported Income Statement (SGD):**

| Line Item | As Reported |
|---|---|
| Revenue | 50,000,000 |
| COGS | 30,000,000 |
| Gross Profit | 20,000,000 |
| SG&A | 5,000,000 |
| EBITDA | 15,000,000 |
| D&A | 1,000,000 |
| EBIT | 14,000,000 |
| Pro Forma Tax (17%) | 2,380,000 |
| Operating Income After Tax | 11,620,000 |

**Issues Found:**

1. Xin's comp is SGD 1.5M; market rate is SGD 500K → **reduce SG&A by SGD 1,000,000**
2. Ranch & condo aren't needed for operations → **remove SGD 300K of operating expenses from SG&A** and **SGD 100K of depreciation**

**Normalized Income Statement (SGD):**

| Line Item | As Adjusted |
|---|---|
| Revenue | 50,000,000 |
| COGS | 30,000,000 |
| Gross Profit | 20,000,000 |
| SG&A | **3,700,000** ← (5M - 1M - 300K) |
| EBITDA | **16,300,000** |
| D&A | **900,000** ← (1M - 100K) |
| EBIT | **15,400,000** |
| Pro Forma Tax (17%) | 2,618,000 |
| Operating Income After Tax | **12,782,000** |

> **Step-by-step what happened:**
> - SG&A dropped by $1.3M total (1M excess comp + 300K non-operating expenses)
> - D&A dropped by $100K (depreciation on non-operating assets)
> - EBITDA rose from 15M → 16.3M
> - After-tax income rose from 11.62M → 12.78M — a **10% increase** just from cleaning up the books

### Strategic vs. Financial Transactions

When normalizing, ask: **Who is the buyer?**

- **[[Strategic Buyer]]** (same industry): Includes expected [[synergies]] — cost savings from eliminating redundancies, revenue from cross-selling. **Higher normalized EBITDA.**
- **[[Financial Buyer]]** (different industry): No synergies. **Lower normalized EBITDA.**

> **Example:** Target firm has EBITDA of $4.8M. Executive comp is $900K vs. market rate of $600K. Strategic buyer can also save $400K in redundant costs.
> - Financial buyer's normalized EBITDA: $4.8M + $300K = **$5.1M**
> - Strategic buyer's normalized EBITDA: $4.8M + $300K + $400K = **$5.5M**

### Cash Flow Estimation Issues

Beyond normalization, key issues when estimating [[FCFF]] or [[FCFE]]:

- **Controlling vs. non-controlling interest:** Cash flow assumptions may differ. A controlling interest holder can change [[Dividend policy|dividend policy]], capital structure, etc.
- **[[Scenario analysis]]:** Use multiple scenarios (optimistic, base, downside) and probability-weight them, especially for early-stage companies facing binary outcomes (e.g., drug approval).
- **Management Bias:** Management may overstate [[Goodwill]] or understate future capital needs. Be skeptical.
- **Use [[FCFF]] when capital structure will change:** [[WACC]] is less sensitive to leverage changes than [[Cost of equity]], so [[FCFF]] valuations are more stable.

### FCFF Formula

$$FCFF = EBITDA(1 - t) + Dep(t) - \Delta LT\ Assets - \Delta Working\ Capital$$

**In plain words:** Start with operating earnings before interest and non-cash charges. Tax them. Add back the [[tax shield]] from [[Depreciation]]. Subtract what you reinvested in long-term assets and working capital. What's left is cash available to ALL investors (debt + equity).

---

## 5. Discount Rate Adjustments for Private Companies

### Why Private Company Discount Rates Are Different

The [[Discount rate]] is what investors demand as compensation for risk. Private companies are generally **riskier** than public companies, so their discount rates are **higher**. But estimating exactly how much higher is tricky.

### Factors Requiring Adjustment

| Factor | Issue | Impact |
|---|---|---|
| **Size Premiums** | Small private firms are riskier. But be careful — some "small public firms" used as benchmarks are actually distressed former large firms, which biases the premium **upward**. | Higher discount rate |
| **Debt Availability & Cost** | Private firms have less access to debt, so they rely more on expensive [[Equity]]. Also, their debt costs more due to higher operating risk. | Higher [[WACC]] |
| **Acquirer vs. Target** | **Always use the target's WACC**, not the buyer's. Using the buyer's lower WACC overstates the target's value — you'd be paying the seller for value you bring to the deal. | Use target's rate |
| **Projection Risk** | Less information available = more uncertainty in forecasts. Management may also be inexperienced at forecasting. | Higher discount rate |
| **[[Life Cycle Stage]]** | Early-stage firms have high [[unsystematic risk]]. [[CAPM]] may be inappropriate since it only captures [[Systematic risk]]. | Model selection issue |

---

## 6. Required Rate of Return Models

### The Problem with Standard CAPM for Private Firms

The [[Capital asset pricing model]] (CAPM) says:

$$r_e = R_f + \[[Beta|beta]](R_m - R_f)$$

**In plain words:** The [[required return on equity]] equals the [[risk-free rate]] plus a premium for how much the stock moves with the overall market ([[Beta]] × [[Equity risk premium]]).

**Why it breaks down for private firms:**
- [[Beta]] is estimated from **public company** return data — but a small private firm may never go public
- [[CAPM]] only captures [[Systematic risk]] (market-wide risk), but private company investors are often **undiversified** — their whole wealth may be tied up in one business
- US tax courts have actually **rejected** CAPM for some private company valuations

### Solution 1: Expanded CAPM

$$r_e = R_f + \beta(R_m - R_f) + SP + CSP$$

| Variable | What It Is | Why It's Included |
|---|---|---|
| $R_f$ | [[Risk-free rate]] (e.g., Treasury yield) | Baseline: compensation for time value of money |
| $\beta(R_m - R_f)$ | Standard [[CAPM]] risk premium | Compensation for [[Systematic risk]] (market risk) |
| $SP$ | [[Small stock premium]] (size premium) | Private firms are smaller = riskier. Historically, small stocks earn higher returns |
| $CSP$ | [[Company-specific risk premium]] | Unique risks: key-person dependence, customer concentration, etc. Subjective. |

> Think of it like car insurance. [[CAPM]] prices your insurance based on how all drivers your age perform (systematic risk). Expanded CAPM also charges you extra for having a sports car (size) and three tickets on your record (company-specific risk).

### Solution 2: Build-Up Approach

$$r_e = R_f + ERP + SP + IRP + CSP$$

| Variable | What It Is | Why It's Included |
|---|---|---|
| $R_f$ | [[Risk-free rate]] | Same as above |
| $ERP$ | [[Equity risk premium]] ($R_m - R_f$, **no beta adjustment**) | Implicitly assumes $\beta = 1$ |
| $SP$ | [[Small stock premium]] | Same as Expanded CAPM |
| $IRP$ | [[Industry risk premium]] | Some industries are riskier than the broad market. This replaces the beta adjustment |
| $CSP$ | [[Company-specific risk premium]] | Same as above |

**When to use:** When you **can't find comparable public companies** to estimate [[Beta]]. Since beta is implicitly 1, the industry risk premium serves as a substitute.

### Key Differences Between the Three Models

| Feature | CAPM | Expanded CAPM | Build-Up |
|---|---|---|---|
| Uses [[Beta]]? | Yes | Yes | No (assumes β = 1) |
| Size premium? | No | Yes | Yes |
| Company-specific premium? | No | Yes | Yes |
| Industry risk premium? | No | No | Yes |
| Best when | Mature private firm similar to public comps | Private firm with good public comps but is smaller/riskier | No good public comps available |

### Worked Example: FLI's Required Return on Equity

**Given:**
- $R_f$ = 3.8%
- $ERP$ = 5.0%
- $\beta$ = 1.1 (from public comps)
- Small stock premium = 3.0%
- Company-specific premium = 1.0%
- Industry risk premium = 0.0%

**Step 1: CAPM**

$$r_e = 3.8\% + 1.1(5.0\%) = 3.8\% + 5.5\% = 9.3\%$$

**Step 2: Expanded CAPM**

$$r_e = 3.8\% + 1.1(5.0\%) + 3.0\% + 1.0\% = 9.3\% + 4.0\% = 13.3\%$$

**Step 3: Build-Up**

$$r_e = 3.8\% + 5.0\% + 3.0\% + 0.0\% + 1.0\% = 12.8\%$$

> **Why is Build-Up lower than Expanded CAPM here?** Two reasons:
> 1. The industry risk premium was assumed to be zero
> 2. Build-Up doesn't multiply the ERP by beta. Since beta = 1.1, the Expanded CAPM gets an extra 0.5% (= 5% × 0.1) from the beta adjustment

### Unlevering and Relevering Beta

When borrowing [[Beta]] from public comparables, you must adjust for differences in [[Leverage]] ([[Capital structure]]):

**Step 1: Unlever** the public company's beta (remove the effect of its debt):

$$\beta_{unlevered} = \frac{\beta_{levered}}{1 + (1 - t) \times \frac{Debt}{Equity}}$$

Where $t$ and $\frac{Debt}{Equity}$ are the **public company's** tax rate and leverage.

**Step 2: Relever** to match the private company's capital structure:

$$\beta_{levered}^{*} = \beta_{unlevered} \left[1 + (1 - t^{*}) \times \left(\frac{Debt}{Equity}\right)^{*}\right]$$

Where $t^{*}$ and $\left(\frac{Debt}{Equity}\right)^{*}$ are the **private company's** values.

> **Why?** [[Beta]] reflects both business risk AND financial risk (from leverage). Two identical businesses with different debt levels will have different betas. To compare apples-to-apples, you strip out the leverage effect, then add back the private firm's specific leverage.

### WACC Calculation

$$r_{WACC} = w_d \cdot r_d + w_e \cdot r_e$$

Where:
- $w_d$, $w_e$ = weights of debt and equity as % of total capital
- $r_d = r(1 - t)$ = [[after-tax cost of debt]]
- $r_e$ = [[Cost of equity]] (from CAPM, Expanded CAPM, or Build-Up)

**Which capital structure weights to use?**
- For an **acquisition**: use the **optimal** capital structure (the target will be restructured)
- Don't blindly copy public company debt ratios — public firms have **better debt access** and can carry more debt
- The private firm's **current** structure may reflect the owner's personal preferences (e.g., avoiding debt), not what's optimal

### Worked Example: FLI's WACC

**Given:** Pre-tax cost of debt = 7.5%, Tax rate = 17%, Cost of equity = 13.0%

**Using FLI's current capital structure (2% debt):**

$$r_{WACC} = 0.02 \times 7.5\%(1 - 0.17) + 0.98 \times 13.0\%$$
$$= 0.02 \times 6.225\% + 0.98 \times 13.0\%$$
$$= 0.1\% + 12.7\% = 12.9\%$$

**Using optimal capital structure (10% debt):**

$$r_{WACC} = 0.10 \times 6.225\% + 0.90 \times 13.0\%$$
$$= 0.62\% + 11.7\% = 12.3\%$$

> **Takeaway:** The optimal structure uses more cheap debt, lowering WACC from 12.9% → 12.3%. A buyer who restructures the capital will get more value — but should they pay the seller for this improvement they haven't made yet?

---

## 7. Valuation Discounts and Premiums

### The Control-Marketability Framework

After calculating a base value, you may need to adjust for two things:

```
Highest Value:   Strategic Control Premium
                     ↑ (synergies + control)
                 Financial Control Premium
                     ↑ (control, no synergies)
Base:            Comparable Public Company Value
                     ↓ (lack of control)
                 Non-controlling Interest
                     ↓ (lack of marketability)
Lowest Value:    Non-controlling, Non-marketable Interest
```

### Discount for Lack of Control ([[DLOC]])

**Definition:** A reduction in value because a minority shareholder **can't control** the company's decisions — can't hire/fire management, set dividends, sell assets, or change strategy.

**Why it exists:** Controlling shareholders can enjoy above-market compensation, perks, and other benefits that reduce returns to minority holders.

**Formula:**

$$DLOC = 1 - \frac{1}{1 + Control\ Premium}$$

**In plain words:** If controlling stakes trade at a 25% premium, then lacking control is worth a discount of $1 - \frac{1}{1.25} = 1 - 0.80 = 0.20 = 20\%$.

> **Important:** The DLOC is NOT the same as the [[Control premium|control premium]]! A 25% control premium translates to only a 20% DLOC.

**When to apply:**
- Apply DLOC when comparable values are for **controlling interests** but you're valuing a **minority interest**
- Don't apply if your DCF already used non-controlling assumptions (non-normalized earnings, non-optimal capital structure)

### Discount for Lack of Marketability ([[DLOM]])

**Definition:** A reduction in value because the shares **can't easily be sold**. There's no public market, and finding a buyer takes time and effort.

**Why it exists:** An [[illiquid]] investment involves opportunity cost — you can't redeploy your capital elsewhere when you want to.

**Factors affecting [[Discount for lack of marketability|DLOM]]:**

| Factor | Effect on DLOM |
|---|---|
| Impending [[IPO]] or sale | Decreases DLOM (liquidity is coming) |
| Contractual sale restrictions | Increases DLOM |
| Larger pool of potential buyers | Decreases DLOM |
| Greater ownership concentration | Increases DLOM |
| Higher asset risk / volatility | Increases DLOM |

**Three ways to estimate DLOM:**

1. **Restricted stock transactions:** Compare the price of restricted shares (can't trade for a period) to freely traded shares of the same company. The discount = DLOM estimate.
2. **Pre-IPO vs. Post-IPO prices:** Compare what shares sold for before the IPO to the IPO price. Caveat: the price increase may also reflect reduced business risk, not just improved marketability.
3. **Put option approach:** Price an [[at-the-money put option]] on a comparable public company. The put premium / stock price = DLOM. Advantage: directly captures the private firm's risk through [[Volatility]]. Drawback: a put gives price protection, not actual liquidity.

### Total Discount (Combining DLOC and DLOM)

**DLOC and DLOM are applied multiplicatively, NOT additively:**

$$Total\ Discount = 1 - (1 - DLOC)(1 - DLOM)$$

### Worked Example

**Given:** Control premium = 30%, DLOM = 20%

**Step 1: Calculate DLOC**

$$DLOC = 1 - \frac{1}{1 + 0.30} = 1 - \frac{1}{1.30} = 1 - 0.7692 = 23.1\%$$

> **Note:** The DLOC is 23.1%, NOT 30%. This is a common exam trap.

**Step 2: Calculate Total Discount**

$$Total\ Discount = 1 - (1 - 0.231)(1 - 0.20) = 1 - (0.769)(0.80) = 1 - 0.615 = 38.5\%$$

> If you had **added** them: 23.1% + 20% = 43.1% — that would be **wrong**.

---

## 8. Valuation Approaches Overview

### Three Main Approaches

| Approach | What It Does | Public Company Equivalent | Best For |
|---|---|---|---|
| **[[Income approach]]** | PV of expected future income | [[DCF]] / [[Present Value]] models | High-growth firms with forecastable cash flows |
| **[[Market approach]]** | Value based on comparable multiples | [[Method of comparables]] | Mature firms with good public comps |
| **[[Asset-based approach]]** | Assets minus liabilities | [[Liquidation value]] / [[Book value]] | Early-stage, distressed, or asset-heavy firms |

### Matching Approach to Life Cycle Stage

```
Early Stage ──────→ High Growth ──────→ Mature ──────→ Decline/Distress
Asset-Based          Income (FCF)        Market             Asset-Based
(too uncertain       (can forecast       (plenty of         (may be worth
 for cash flows)      cash flows)         comparables)       more dead
                                                             than alive)
```

---

## 9. Income Approach — Three Methods

### Method 1: Free Cash Flow (FCF) Method

This is the **two-stage model** you already know from public company valuation:

$$IV_t = \sum_{i=1}^{n} \frac{FCFF_{t+i}}{(1 + WACC)^i} + \frac{Terminal\ Value}{(1 + WACC)^n}$$

**In plain words:** Forecast cash flows for a discrete period (usually 5 years), then add a [[Terminal value]] representing everything after that period, all discounted back to today.

**[[Terminal value|Terminal value]]** can be estimated three ways:
1. **[[Capitalized Cash Flow]]** (growing [[Perpetuity|perpetuity]])
2. **Market-based multiple** (apply an [[EV/EBITDA]] multiple to terminal-year EBITDA)
3. **[[Excess earnings method]]** ([[Residual income|residual income]] approach)

### Method 2: Capitalized Cash Flow Method (CCM)

This is a **single-stage model** — a [[growing perpetuity]]:

$$Firm\ Value_t = \frac{FCFF_{t+1}}{WACC - g}$$

**In plain words:** If the business is expected to grow at a stable rate forever, just divide next year's cash flow by the spread between your [[Discount rate]] and the [[growth rate]].

**The [[Reinvestment Rate]] (RIR):**

$$RIR = \frac{g}{WACC}$$

This tells you what fraction of cash flow must be reinvested to sustain growth $g$.

**Using EBIT:**

$$Firm\ Value_t = \frac{EBIT_{t+1}(1 - t)(1 - RIR)}{WACC - g}$$

**When to use CCM:**
- Small private company
- No good [[Comparables|comparables]] available
- Stable growth is a reasonable assumption
- Projections are uncertain (simpler model = less room for error)

**To get [[equity value]]:** Subtract [[Market value|market value]] of debt from firm value.

### Worked Example: CCM

**Given:** FCFF₁ = $12,100,000 | WACC = 15% | g = 4% | Debt = $4,000,000

**Step 1: Firm Value**

$$Firm\ Value = \frac{\$12,100,000}{0.15 - 0.04} = \frac{\$12,100,000}{0.11} = \$110,000,000$$

**Step 2: Equity Value**

$$Equity\ Value = \$110,000,000 - \$4,000,000 = \$106,000,000$$

> **Warning:** This model is **extremely sensitive** to assumptions. A 3% drop in the assumed growth rate can reduce equity value by over 25%.

### Method 3: Excess Earnings Method (EEM)

The EEM separately values [[tangible assets]] and [[Intangible assets]]:

**Concept:** If a company earns more than what's needed to provide a fair return on its tangible assets, the excess belongs to the [[Intangible assets|intangible assets]] (brand, patents, relationships, etc.).

**Formula for [[Excess Earnings]] ([[Residual income|Residual Income]]):**

$$EE = Normalized\ Income - (WC \times r_{WC}) - (FA \times r_{FA})$$

Where:
- $EE$ = [[Excess Earnings]]
- $WC$ = [[Working capital]] ([[Current assets|current assets]] minus [[Current liabilities|current liabilities]]es|liabilities]])
- $r_{WC}$ = required return on [[Working capital]] (lowest, since most liquid)
- $FA$ = [[Fixed Assets]] (PP&E)
- $r_{FA}$ = required return on [[fixed assets]] (higher, less liquid)

**Value of [[Intangible assets]] (growing [[Perpetuity|perpetuity]]):**

$$V_{intg} = \frac{EE(1 + g)}{r_{intg} - g}$$

Where $r_{intg}$ = required return on [[Intangible assets]] (highest, least liquid and most risky).

**Total [[Firm Value]]:**

$$V_f = WC + FA + V_{intg}$$

### Worked Example: EEM

**Given:**
- [[Normalized earnings|Normalized earnings]] = $130,000
- [[Working capital|Working capital]] = $300,000, required return = 6%
- Fixed assets = $1,000,000, required return = 10%
- Intangible asset [[Discount rate|discount rate]] = 14%
- Excess earnings growth rate = 5%

**Step 1: Required returns on tangible assets**

$$Return\ on\ WC = \$300{,}000 \times 0.06 = \$18{,}000$$
$$Return\ on\ FA = \$1{,}000{,}000 \times 0.10 = \$100{,}000$$

**Step 2: Calculate [[Excess Earnings]]**

$$EE = \$130{,}000 - \$18{,}000 - \$100{,}000 = \$12{,}000$$

> This $12,000 is the income *above* what the tangible assets should be generating. It must be coming from intangibles like brand value or customer relationships.

**Step 3: Value [[Intangible assets]]**

$$V_{intg} = \frac{\$12{,}000 \times 1.05}{0.14 - 0.05} = \frac{\$12{,}600}{0.09} = \$140{,}000$$

**Step 4: Total [[Firm Value]]**

$$V_f = \$300{,}000 + \$1{,}000{,}000 + \$140{,}000 = \$1{,}440{,}000$$

> **When to use EEM:** Small firms where [[Intangible assets|intangible assets]] are significant. The drawback is that the required returns for WC, FA, and intangibles are subjective and hard to estimate reliably.

---

## 10. Market Approach — Three Methods

The [[Market approach]] values companies by comparing them to real transactions. Practitioners often **prefer** this approach because it uses actual market data.

### Key Multiple for Private Companies

$$\frac{MVIC}{EBITDA}$$

Where:
- $MVIC$ = [[Market value of invested capital]] = $MV_{equity} + MV_{debt}$
- $EBITDA$ = [[Earnings Before Interest, Taxes, Depreciation, and Amortization]]

> **Why MVIC/EBITDA instead of P/E?** Because private companies often have changing [[capital structures]], and [[Enterprise value]] multiples are more flexible — they value the whole firm regardless of how it's financed.

### Method 1: Guideline Public Company Method ([[GPCM]])

**What it does:** Uses [[EV/EBITDA]] (or other) multiples from **publicly traded** comparable companies.

**Equity Value from GPCM:**

$$EV = (Guideline\ MVIC/EBITDA) \times Normalized\ EBITDA$$
$$Equity\ Value = EV - Debt\ Capital$$

**Key adjustments:**
- Match [[Comparables|comparables]] on industry, size, leverage, life cycle
- Adjust multiples for risk differences (sometimes deflate by a % to account for private firm risk)
- For multi-industry private firms, use a **weighted average** of industry multiples

**Advantage:** Usually lots of publicly traded data available.
**Disadvantage:** Public firms may not be truly comparable. Adjustments are subjective.

**[[Control premium|Control premium]] considerations** (if valuing a controlling interest):
- Consider transaction type (financial vs. strategic)
- Industry conditions ("in play" industries may already have control premiums baked into prices)
- Form of consideration (stock vs. cash)
- Reasonableness check

### Method 2: Guideline Transactions Method ([[GTM]])

**What it does:** Uses multiples from **actual acquisitions** of entire companies (public or private).

**Key difference from GPCM:** Transaction prices **already include [[control premiums]]**, so no additional [[Control premium|control premium]] adjustment is needed.

**Factors to watch:**
- **Synergies:** Strategic acquisitions include synergy payments — may not apply to your deal
- **[[Contingent consideration|Contingent consideration]]:** Part of the price may depend on future milestones (e.g., FDA approval). Adds risk for the seller
- **Non-cash consideration:** Stock payments may be hard to value accurately
- **Data availability:** Private [[Acquisition|acquisition]] data is limited and may not be reliable
- **Date relevance:** Old transactions may not reflect current market conditions

### Worked Example: GTM

**Given:** Average public company EV/EBITDA multiple = 7.2x. Analyst deflates by 30% for higher private firm risk. Normalized EBITDA = $18,200,000.

**Step 1: Adjust the multiple**

$$Adjusted\ Multiple = 7.2 \times (1 - 0.30) = 5.0\times$$

**Step 2: Calculate [[Enterprise value|Enterprise Value]]**

$$EV = 5.0 \times \$18{,}200{,}000 = \$91{,}000{,}000$$

### Method 3: Prior Transaction Method ([[PTM]])

**What it does:** Uses prices from **past sales of the subject company's own stock**.

**Best when:** Transactions are recent, arm's-length, and of similar motivation to the current valuation.

**Limitations:** Prior transactions may be stale, not arm's-length (e.g., between family members), or done under different motivations.

---

## 11. Asset-Based Approach

**What it does:** Values the company as [[Assets]] minus [[Liabilities]], with each asset marked to [[Fair market value]].

**Best for:**
- Companies in **[[Financial distress|financial distress]]** (may be worth more dead than alive)
- **Early-stage** companies with minimal or unpredictable cash flows
- **Asset-heavy** businesses ([[Real estate|real estate]], natural resources)
- When the company is being [[liquidated]]

**Limitations:** Doesn't capture [[going concern]] value, synergies, or intangible asset value very well.

---

## 12. Comprehensive Worked Example: FLI Full Income Approach Valuation

This pulls everything together — normalization, [[Discount rate|discount rate]], DCF, and discounts:

### Step 1: Estimate WACC

From earlier calculations, Khan uses a blended 13.0% [[Cost of equity|cost of equity]] and averages different [[Capital structure|capital structure]] assumptions to arrive at **WACC = 12.55%**.

### Step 2: Calculate Base-Year FCFF

From normalized financials:

$$FCFF = EBITDA(1-t) + Dep(t) - \Delta LT\ Assets - \Delta WC$$
$$= 16{,}300{,}000(0.83) + 900{,}000(0.17) - 1{,}200{,}000 - 500{,}000$$
$$= 13{,}529{,}000 + 153{,}000 - 1{,}200{,}000 - 500{,}000$$
$$= SGD\ 11{,}982{,}000$$

### Step 3: Forecast FCFF and Terminal Value

Three scenarios over 5 years with 3% perpetual terminal growth:

| Year | Downside (2%) | Base (5%) | Optimistic (8%) |
|---|---|---|---|
| Base | 11,982 | 11,982 | 11,982 |
| 1 | 12,222 | 12,581 | 12,941 |
| 2 | 12,466 | 13,210 | 13,976 |
| 3 | 12,715 | 13,871 | 15,094 |
| 4 | 12,970 | 14,564 | 16,301 |
| 5 | 13,229 | 15,292 | 17,605 |
| **[[Terminal value|Terminal Value]]** | **142,680** | **164,934** | **189,881** |

*(All figures in SGD thousands)*

[[Terminal value|Terminal Value]] (downside example):

$$TV = \frac{FCFF_5 \times (1+g)}{WACC - g} = \frac{13{,}229 \times 1.02}{0.1255 - 0.03} = \frac{13{,}494}{0.0955} \approx 141{,}295$$

### Step 4: Discount to Present Value

Discounting at WACC = 12.55%:

| Case | EV (SGD millions) | Equity Value (EV - 2.5M debt) |
|---|---|---|
| Downside | 124.0 | 121.5 |
| Base | 140.2 | 137.7 |
| Optimistic | 158.2 | 155.7 |

### Step 5: Apply Discounts

Khan applies an 18% [[DLOM]] (no DLOC since Xin has a controlling stake):

| Case | Equity Value × (1 - 0.18) |
|---|---|
| Downside | SGD 99.7M |
| Base | SGD 112.9M |
| Optimistic | SGD 127.6M |

> **Final answer:** FLI's equity is worth approximately **SGD 100M – 128M** depending on growth assumptions, after accounting for its status as a private, illiquid investment.

---

## 13. Summary: Key Formulas at a Glance

### Discount Rate Models

| Model | Formula |
|---|---|
| **[[CAPM]]** | $r_e = R_f + \beta(R_m - R_f)$ |
| **[[Expanded CAPM]]** | $r_e = R_f + \beta \cdot ERP + SP + CSP$ |
| **[[Build-up approach]]** | $r_e = R_f + ERP + SP + IRP + CSP$ |
| **[[WACC]]** | $r_{WACC} = w_d \cdot r_d + w_e \cdot r_e$ |
| **[[After-Tax Cost of Debt]]** | $r_d = r(1-t)$ |

### Valuation Models

| Model | Formula |
|---|---|
| **[[FCFF]] DCF** | $IV_t = \sum \frac{FCFF_{t+i}}{(1+WACC)^i} + \frac{TV}{(1+WACC)^n}$ |
| **[[CCM]]** | $Firm\ Value = \frac{FCFF_1}{WACC - g}$ |
| **[[Reinvestment Rate]]** | $RIR = \frac{g}{WACC}$ |
| **[[Excess Earnings]]** | $EE = Income - r_{WC}(WC) - r_{FA}(FA)$ |
| **[[Intangible Asset Value]]** | $V_{intg} = \frac{EE(1+g)}{r_{intg} - g}$ |
| **[[Firm Value]] (EEM)** | $V_f = WC + FA + V_{intg}$ |

### Discounts and Premiums

| Item | Formula |
|---|---|
| **[[DLOC]]** | $DLOC = 1 - \frac{1}{1 + Control\ Premium}$ |
| **Total Discount** | $1 - (1 - DLOC)(1 - DLOM)$ |
| **[[GPCM]] Equity** | $(MVIC/EBITDA) \times EBITDA - Debt$ |

### Beta Adjustments

| Step | Formula |
|---|---|
| **Unlever** | $\beta_U = \frac{\beta_L}{1 + (1-t) \times D/E}$ |
| **Relever** | $\beta_L^{*} = \beta_U[1 + (1-t^{*}) \times (D/E)^{*}]$ |

---

## 14. Common Exam Traps

1. **DLOC ≠ [[Control premium|Control Premium]].** A 25% [[Control premium|control premium]] → DLOC = 20%, not 25%.
2. **Total discount is multiplicative, not additive.** Don't just add DLOC + DLOM.
3. **Use the target's WACC**, not the acquirer's.
4. **Build-up method assumes β = 1**, not β = 0.
5. **Strategic vs. financial buyer** changes [[Normalized earnings|normalized earnings]] (synergies).
6. **[[Normalized earnings|Normalized earnings]]** in private company context ≠ cycle-adjusted earnings for public companies. Here it means adjusting for owner quirks.
7. **CCM is extremely sensitive** to growth rate and WACC assumptions.
8. **GTM multiples already include control premiums** — don't add one again.
9. **When to use FCFF vs. FCFE:** Use FCFF when [[Capital structure|capital structure]] is expected to change (it almost always is in private company deals).
10. **[[Optimal capital structure|Optimal capital structure]]** for WACC ≠ public company [[Capital structure|capital structure]]. Private firms have less debt access.
