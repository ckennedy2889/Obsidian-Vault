# Evaluating Quality of Financial Reports

> [!info] Module Overview
> This module teaches you to think like a **forensic analyst** — someone who can pick up a set of financial statements and ask: *"Can I trust these numbers, and are the [[Underlying|underlying]] economics any good?"* These are two distinct questions, and the entire module is built around separating them. Think of it like buying a used car: first, is the seller being honest about the condition (reporting quality)? Second, is the car actually a good car (results quality)?
>
> **CFA Institute 2025 Level II Curriculum — Volume 3, Learning Module 5**
> Supplemented by Mark Meldrum Notes

---

## 📋 Learning Outcome Statements

| LOS | Description |
|-----|-------------|
| **a** | Demonstrate the use of a conceptual framework for assessing the quality of a company's [[financial statements]] |
| **b** | Explain potential problems that affect the quality of financial reports |
| **c** | Describe how to evaluate the quality of a company's financial reports |
| **d** | Evaluate the quality of a company's financial reports |
| **e** | Describe indicators of [[earnings]] quality |
| **f** | Describe the concept of sustainable (persistent) earnings |
| **g** | Explain [[Mean reversion]] in earnings and how the [[accruals]] component affects the speed of [[Mean reversion|mean reversion]] |
| **h** | Evaluate the [[earnings]] quality of a company |
| **i** | Evaluate the [[cash flow]] quality of a company |
| **j** | Describe indicators of [[Balance sheet]] quality |
| **k** | Evaluate the [[Balance sheet]] quality of a company |
| **l** | Describe indicators of [[cash flow]] quality |
| **m** | Describe sources of information about risk |

---

## 1. The Two Dimensions of Quality (LOS a)

Before diving into ratios and models, you need to internalize the **foundational distinction** that structures this entire module: there are two separate but interrelated dimensions of quality.

### 1.1 Financial Reporting Quality vs. Earnings Quality

**[[Financial reporting quality]]** asks: *Is the information in the financial reports itself reliable and useful?* Does it meet the standard of being [[relevant]] (it affects decisions and is [[materiality|material]]) and a [[faithful representation]] (complete, neutral, free from error)?

**[[Earnings quality]]** (also called "results quality") asks: *Given that the reporting is trustworthy, are the actual economic results any good?* High-quality earnings are **sustainable** (they recur) and **adequate** (they cover the company's [[Cost of capital]], i.e., [[ROIC]] > [[WACC]]).

> [!important] The Critical Dependency
> You **cannot** assess earnings quality without first having at least a baseline level of reporting quality. If the financial statements are fabricated, it doesn't matter how "good" the earnings look — they're meaningless. This is the module's single most important conceptual point.

Think of it as a 2×2 matrix:

```
                 Financial Reporting Quality
                    LOW              HIGH
                ┌────────────┬────────────────────┐
           HIGH │ IMPEDED    │ HIGH quality        │
Earnings        │ Can't even │ reporting ENABLES   │
Quality         │ assess     │ assessment →        │
                │ earnings   │ HIGH earnings =     │
                │ quality    │ INCREASES value     │
                ├────────────┼────────────────────┤
           LOW  │ IMPEDED    │ HIGH quality        │
                │ Worst case │ reporting ENABLES   │
                │            │ assessment →        │
                │            │ LOW earnings =      │
                │            │ DECREASES value     │
                └────────────┴────────────────────┘
```

> [!example] Real-World Illustration
> Consider a company whose only earnings for the year came from a one-time lawsuit settlement, without which it would have reported huge losses. If the company calculated its results correctly and provided decision-useful disclosures, it has **high reporting quality** but **low earnings quality** (non-recurring, unsustainable). An investor can at least *see* the problem and make informed decisions.
>
> Now consider [[Enron]] — it had earnings that *looked* spectacular, but the reporting quality was so low (off-balance-sheet entities, fabricated mark-to-market gains) that investors couldn't even assess what was real. That's the worst quadrant.

### 1.2 The Quality Spectrum

Quality isn't binary — it's a spectrum from best to worst. The CFA curriculum lays out six levels:

```
QUALITY SPECTRUM (Highest → Lowest)
═══════════════════════════════════════════════════════

① GAAP-Compliant, Decision-Useful, Sustainable, Adequate Returns
   → The gold standard. Faithful reporting of genuinely good economics.

② GAAP-Compliant, Decision-Useful, Sustainable...but is it Adequate?
   → Good reporting, recurring earnings, but ROIC may not cover WACC.

③ GAAP-Compliant, but Biased Accounting Choices
   → Within GAAP but aggressive or conservative to tell a "story."
   → Aggressive: ↑ Revenue, ↑ Earnings, ↑ CFO, ↓ Expenses, ↓ Debt today
   → Conservative: ↓ Revenue, ↓ Earnings today → ↑ future periods

④ GAAP-Compliant, but Active Earnings Management
   → Intentional choices to create biased reports.
   → Real actions: delaying R&D spending to boost current earnings
   → Accounting choices: extending useful lives to reduce depreciation

⑤ Non-Compliant Accounting
   → Incorrect treatment of transactions (violates GAAP/IFRS)

⑥ Fictitious Transactions
   → Pure fabrication. Making stuff up.
```

> [!warning] Aggressive vs. Conservative — Neither is Ideal
> **Aggressive accounting** pulls future revenues/earnings into the current period — it flatters today's results at the expense of tomorrow's. **Conservative accounting** does the opposite — it defers current earnings to future periods. Investors may prefer conservative choices (positive surprises are acceptable), while management may prefer aggressive choices (tied to compensation). **Unbiased** reporting — faithful representation that is **neutral** — is the ideal.
>
> **Earnings smoothing** is a common pattern: conservative choices today, aggressive choices in the future, to create the illusion of a steady earnings trajectory.

---

## 2. Potential Problems Affecting Quality (LOS b)

Problems that undermine financial reporting quality fall into two broad categories: **measurement/timing issues** and **classification issues**.

### 2.1 Measurement and Timing Issues

These affect **multiple** financial statement elements simultaneously because the accounting equation links everything together.

| Direction | Revenue Effect | Expense Effect | Impact on NI, Equity, Assets |
|-----------|---------------|----------------|------------------------------|
| **Aggressive** | Premature or fictitious [[revenue recognition]] | Omitted or delayed [[expense recognition]] | All ↑ overstated |
| **Conservative** | Delayed [[revenue recognition]] | Accelerated [[expense recognition]] | All ↓ understated |

> [!example] How This Cascades
> If a company aggressively recognizes $10M of revenue that should belong to next quarter:
> - [[Revenue]] ↑ $10M → [[Net income]] ↑ → [[Retained earnings]] ↑ → [[Equity]] ↑
> - [[Accounts receivable]] ↑ $10M (or [[Cash]] ↑ if collected) → [[Assets]] ↑
> - The [[Balance sheet]] equation still holds, but the numbers are misleading

### 2.2 Classification Issues

Classification issues involve how items are **categorized within** a single financial statement. Unlike measurement/timing issues, they typically affect **one** statement but not the total.

| Statement | Misclassification Example | Effect |
|-----------|--------------------------|--------|
| **[[Income statement]]** | Operating expenses classified as non-operating | [[Operating income]] overstated, [[Net income]] unchanged |
| **[[Income statement]]** | Non-operating revenue classified as operating | [[Operating income]] overstated |
| **[[Balance sheet]]** | Current [[Liabilities]] classified as non-current | [[Current ratio]] overstated, [[Leverage]] appears lower |
| **[[Cash flow statement]]** | Investing outflows classified as operating | [[CFO]] understated (or vice versa: investing classified as operating inflates CFO) |
| **[[OCI]]** | Routing losses through [[OCI]] and gains through [[Net income]] | [[Net income]] overstated, total comprehensive income unchanged |

> [!tip] Classification Shifting — A Subtle Trick
> **Classification shifting** leaves [[Net income]] unchanged but changes the composition. A company might reclassify ordinary operating expenses as "non-recurring restructuring charges" to make [[operating income]] look stronger. The red flag: does the company report income-decreasing special items regularly while operating income looks strong? If so, those "special" items may not be so special.

### 2.3 Business Combinations as a Quality Concern

[[Business combinations]] create unique opportunities to manipulate:
- **Maximizing [[Goodwill]]** by understating the [[Fair value]] of identifiable assets acquired → lower future [[amortization]]/[[Depreciation]] → higher future earnings
- Using [[acquisitions]] to conceal past operating mistakes (the "fresh start" effect)
- [[Impairment]] and [[restructuring charges]] provide management with discretion

---

## 3. Evaluating Financial Reporting Quality (LOS c, d)

The curriculum provides a **seven-step qualitative framework** followed by **quantitative tools**.

### 3.1 The Seven-Step Qualitative Framework

```
EVALUATING FINANCIAL REPORTING QUALITY
═══════════════════════════════════════

Step 1 ──→ Understand the COMPANY & INDUSTRY
            │ Basis for understanding which accounting principles
            │ are appropriate and which financial metrics are useful
            ▼
Step 2 ──→ Evaluate MANAGEMENT
            │ Compensation structure (tied to financial results?)
            │ Insider transactions
            │ Disclosures about motivation to misreport
            ▼
Step 3 ──→ Identify SIGNIFICANT ACCOUNTING AREAS
            │ Where is judgment used most?
            │ Revenue recognition policies, estimates, fair values
            ▼
Step 4 ──→ Make COMPARISONS
            │ Year-over-year (time series): major differences?
            │ Vs. competitors (cross-sectional): policy differences?
            │ Ratio analysis vs. peers
            ▼
Step 5 ──→ Check for WARNING SIGNS
            │ • Declining AR turnover
            │ • Declining inventory turnover
            │ • NI > CFO
            │ • Revenue growth higher than peers
            │ • Increasing DSO
            ▼
Step 6 ──→ SEGMENT ANALYSIS (multi-segment/multinational firms)
            │ Is a "desirable" segment showing positive performance
            │ while consolidated results are flat or negative?
            │ → May indicate shifting of profits/revenue
            ▼
Step 7 ──→ QUANTITATIVE TOOLS (Beneish Model, Altman Z-score)
```

> [!warning] Key Warning Signs — Commit These to Memory
> - **Declining [[Accounts receivable turnover]]** → Revenues may be fictitious or recorded prematurely, or the [[allowance for doubtful accounts]] is insufficient
> - **Declining [[Inventory turnover]]** → [[Obsolescence]] problems not being recognized
> - **[[Net income]] > [[CFO]]** → Aggressive [[accrual accounting]] may be shifting current expenses to later periods
> - **Revenue growth higher than peers** → Potential overstatement or non-sustainability
> - **Increases in discounts and returns** → Revenue quality deteriorating
> - **Large proportion of revenue in Q4** (for non-seasonal businesses) → Period-end "stuffing"
> - **Executive compensation largely tied to financial results** → Motivation to manipulate

### 3.2 The Beneish Model (M-Score)

The **Beneish model** is a [[probit regression]] model that estimates the **probability of [[earnings manipulation]]** using eight variables. The output is an **M-score**, which is a [[Standard normal distribution|standard normal variable]] (mean = 0, σ = 1).

$$M\text{-score} = -4.84 + 0.920(\text{DSR}) + 0.528(\text{GMI}) + 0.404(\text{AQI}) + 0.892(\text{SGI})$$
$$+ 0.115(\text{DEPI}) - 0.172(\text{SGAI}) + 4.679(\text{Accruals}) - 0.327(\text{LEVI})$$

**Cutoff:** M-score > **−1.78** → company is flagged as a potential manipulator (probability > 3.8%)

The higher (less negative) the M-score, the higher the probability of manipulation. The probability is the area in the **left tail** of the standard normal distribution.

| Variable | Formula | What It Captures | Value > 1 Means... |
|----------|---------|------------------|--------------------|
| **DSR** (Days Sales Receivable Index) | $\frac{\text{Receivables}_t / \text{Sales}_t}{\text{Receivables}_{t-1} / \text{Sales}_{t-1}}$ | Change in relationship between [[AR]] and [[Revenue]] | AR growing faster than sales → possible inappropriate [[revenue recognition]] |
| **GMI** (Gross Margin Index) | $\frac{\text{Gross Margin}_{t-1}}{\text{Gross Margin}_t}$ | Deterioration in [[Gross margin]] | Margins deteriorated → pressure to manipulate |
| **AQI** (Asset Quality Index) | $\frac{1 - (\text{PPE}_t + \text{CA}_t)/\text{TA}_t}{1 - (\text{PPE}_{t-1} + \text{CA}_{t-1})/\text{TA}_{t-1}}$ | Change in non-PPE, non-current asset proportion | ↑ "soft" assets → may indicate excessive [[capitalization]] of expenses |
| **SGI** (Sales Growth Index) | $\frac{\text{Sales}_t}{\text{Sales}_{t-1}}$ | [[Revenue]] growth rate | Growth companies face pressure to manipulate to maintain trajectory |
| **DEPI** (Depreciation Index) | $\frac{\text{Dep Rate}_{t-1}}{\text{Dep Rate}_t}$ | Change in [[Depreciation]] rate | Depreciation rate ↓ → may be extending [[useful lives]] or ↑ [[Salvage value]] |
| **SGAI** (SGA Index) | $\frac{\text{SGA}_t/\text{Sales}_t}{\text{SGA}_{t-1}/\text{Sales}_{t-1}}$ | Change in SG&A efficiency | Decreasing efficiency could predispose manipulation |
| **Accruals** | $\frac{\text{NI} - \text{CFO}}{\text{Total Assets}}$ | Overall [[accruals]] level | Higher accruals → more room for manipulation |
| **LEVI** (Leverage Index) | $\frac{\text{Leverage}_t}{\text{Leverage}_{t-1}}$ | Change in [[Leverage]] (debt/assets) | Increasing leverage → pressure to manipulate |

> [!tip] Exam Approach — Don't Memorize the Coefficients
> Per Mark Meldrum: *Don't memorize the model or coefficients — instead be able to interpret the model.* Know what each variable measures, what a value > 1 implies, and how to interpret an M-score relative to −1.78. The coefficients on SGAI and LEVI are **negative** (counterintuitive) — Beneish expected positive coefficients but actual regression results produced negative values.

> [!example] Beneish Model Application — XYZ Corporation
> Given: M-score = −1.231, Probability of manipulation = 10.93%
>
> Since −1.231 > −1.78, XYZ is flagged as a likely manipulator. The DSR, GMI, SGI, and DEPI values were all > 1, indicating:
> - Receivables growing faster than sales (possible inappropriate revenue recognition)
> - Gross margins deteriorating (pressure to manipulate)
> - Positive sales growth (pressure to maintain trajectory)
> - Declining depreciation rate (may be extending useful lives)

> [!danger] Limitations of the Beneish Model
> 1. **Accounting is only a partial representation of economic reality** — the model establishes associations, not cause and effect
> 2. **Managers learn to game it** — as awareness of the model spreads, manipulators can test their tactics against the model before deploying them
> 3. Research by Beneish et al. (2013) confirms the **predictive power is declining over time**
> 4. Qualitative analysis remains essential — quantitative tools supplement, they don't replace

### 3.3 The Altman Z-Score (Bankruptcy Prediction)

While not directly about earnings quality, the **[[Altman model]]** predicts the probability of [[Bankruptcy]] — an extreme outcome of poor financial results quality.

$$Z = 1.2\left(\frac{\text{NWC}}{\text{TA}}\right) + 1.4\left(\frac{\text{RE}}{\text{TA}}\right) + 3.3\left(\frac{\text{EBIT}}{\text{TA}}\right) + 0.6\left(\frac{\text{MV Equity}}{\text{BV Liabilities}}\right) + 1.0\left(\frac{\text{Sales}}{\text{TA}}\right)$$

| Component | What It Captures |
|-----------|-----------------|
| NWC / TA | [[Liquidity]] |
| RE / TA | Cumulative [[profitability]] |
| EBIT / TA | Current [[profitability]] |
| MV Equity / BV Liabilities | [[Leverage]] (market-based) |
| Sales / TA | Asset [[efficiency]] / activity |

**All five variables are positively related** to the Z-score → **higher Z = lower bankruptcy probability**.

| Z-Score | Interpretation |
|---------|---------------|
| > 3.00 | Safe zone — low probability of bankruptcy |
| 1.81 – 3.00 | Grey zone — moderate risk |
| < 1.81 | Distress zone — high probability of bankruptcy |

> [!warning] Limitations of Altman's Model
> - **Single-period static model** — doesn't capture changes in key variables over time
> - Relies mostly on **accounting data** (except MV Equity)
> - Like the Beneish model, it can be gamed once managers understand it

---

## 4. Earnings Quality (LOS e, f, g, h)

### 4.1 What Makes Earnings "High Quality"?

High-quality [[earnings]] must satisfy **two conditions**:

1. **Sustainable** — Expected to recur in future periods (derived from core, ongoing operations)
2. **Adequate** — Sufficient to cover the company's [[Cost of capital]] ([[ROIC]] > [[WACC]])

> [!info] The Value Connection
> High-quality earnings increase the value of a company more than low-quality earnings. This is directly relevant for [[Equity Valuation]] — if you're forecasting earnings for a [[DCF]] model, the persistence and quality of those earnings determines how much trust you can place in your forecast.

### 4.2 Indicators of Earnings Quality

The curriculum identifies several indicators:

**Recurring vs. Non-Recurring Earnings**

Earnings that are expected to continue are higher quality than one-off items. Analysts should evaluate non-recurring items carefully:
- Not all items classified as "non-recurring" truly are (management has discretion)
- Not all recurring items are classified as such
- **Pro-forma earnings** (non-GAAP) exclude non-recurring items — if used, companies must provide a [[reconciliation]] between pro-forma and [[Net income]]

> [!example] Classification Shifting in Practice
> A company reports strong [[operating income]] every quarter while simultaneously booking "non-recurring restructuring charges" every quarter. The restructuring charges depress [[Net income]] slightly, but [[operating income]] — the metric most analysts focus on — looks great. In reality, the "non-recurring" expenses are ordinary operating costs being relabeled. This is classification shifting — NI is unchanged, but [[operating income]] is inflated.

**Beating Benchmarks**

A company that **consistently** meets or barely beats [[consensus estimates]] raises suspicion. While not conclusive proof, it's a yellow flag — the probability of naturally landing just above the line quarter after quarter is low.

**External Indicators**

- [[SEC]] enforcement actions
- [[Restatements]] of previously issued financial statements

These are less useful to analysts because they're **after the fact** — by the time they're public, the damage is done. But an analyst should still be alert to them as confirmation of concerns.

### 4.3 Sustainable (Persistent) Earnings (LOS f)

The concept of **persistence** can be formalized with a simple regression:

$$\text{Earnings}_{t+1} = \alpha + \beta_1 \cdot \text{Earnings}_t + \varepsilon$$

A **higher $\beta_1$** indicates more persistent earnings — this period's earnings are a stronger predictor of next period's.

### 4.4 Decomposing Earnings: Cash vs. Accruals

Here's where the module gets powerful. You can decompose earnings into two components:

$$\text{Earnings} = \underbrace{\text{Cash Component}}_{\text{More persistent}} + \underbrace{\text{Accruals Component}}_{\text{Less persistent}}$$

The regression that captures this:

$$\text{Earnings}_{t+1} = \alpha + \beta_1 \cdot \text{Cash Flow}_t + \beta_2 \cdot \text{Accruals}_t + \varepsilon$$

**Research consistently shows $\beta_1 > \beta_2$** — the cash flow component of earnings is more persistent than the accruals component.

> [!tip] Why Cash Is More Persistent
> [[CFA_Glossary/Cash flow from operations]] represents actual money flowing in and out — it's hard to fake (though not impossible). [[Accruals]], by contrast, involve estimates, judgments, and assumptions about when to recognize revenues and expenses. The more judgment involved, the more room for manipulation and error, and the less reliable the signal about future performance.

**Types of Accruals:**

```
                    Accruals
                   ╱        ╲
        Non-Discretionary    Discretionary
        (Normal business)    (Non-normal transactions
                              or accounting choices)
        
        e.g., Depreciation   e.g., Changing useful
        on existing assets,  lives, adjusting bad
        normal AR growth     debt allowances,
        with sales           capitalizing expenses
        
        Less concerning      MORE LIKELY TO INDICATE
                              MANIPULATION
```

> [!important] Red Flag: NI > CFO
> When [[Net income]] **consistently exceeds** [[CFA_Glossary/Cash flow from operations]], it means a large portion of earnings is accrual-based rather than cash-based. This is one of the **strongest warning signs** of potential earnings manipulation. The gap between NI and CFO is essentially the accruals component.

### 4.5 Mean Reversion in Earnings (LOS g)

**Mean reversion** is the tendency for extreme levels of earnings — both high and low — to **revert to normal levels over time**. This is an economic phenomenon, not just an accounting one:

- **High earners attract competition** → new entrants drive down returns
- **Low earners shed losing operations** → abandon negative-value projects, replace management

> [!important] The Accruals Connection to Mean Reversion
> Earnings with a **high accruals component revert to the mean faster** than earnings driven primarily by cash flows. This is because accruals are inherently temporary — they involve estimates that eventually get corrected.
>
> The speed of mean reversion increases further when accruals are **discretionary** rather than non-discretionary. Discretionary accruals are more likely to be reversed or corrected in subsequent periods.

```
MEAN REVERSION SPEED
═══════════════════════════════════

Slowest ◄─────────────────────────────► Fastest
reversion                                reversion

Cash-based      Non-discretionary      Discretionary
earnings        accrual-based          accrual-based
                earnings               earnings

Most persistent ◄─────────────────────► Least persistent
```

> [!example] Mean Reversion in Practice
> A pharmaceutical company reports record earnings due to a patent-protected blockbuster drug. These earnings may persist for years (high cash component, sustainable). Compare this to a construction company that reports record earnings by capitalizing costs that should have been expensed and recognizing revenue on projects before completion (high discretionary accruals). The second company's earnings will revert — and likely overshoot to the downside — much faster.

### 4.6 Evaluating Earnings Quality — Revenue Recognition (LOS h)

[[Revenue recognition]] is the **#1 area** for earnings manipulation. In an SEC study of 227 enforcement cases (1997–2002), revenue recognition was the most common misrepresentation.

**Common Revenue Manipulation Techniques:**

| Technique | Description | Red Flags |
|-----------|-------------|-----------|
| **[[Channel stuffing]]** | Aggressively pushing product to distributors with generous terms (lax return policies) | ↑ Revenue growth vs. peers, ↑ returns, ↑ DSO |
| **[[Bill-and-hold]]** | Recognizing revenue at invoice while goods remain on seller's premises | Revenue note disclosures mentioning "bill and hold," ↑ AR |
| **Premature recognition** | Booking revenue before risks and rewards transfer | ↑ AR growth > Revenue growth |
| **Fictitious revenue** | Recording sales to non-existent customers | ↑ AR with no cash collections, NI >> CFO |

> [!example] Case Study: Sunbeam Corporation
> **Sunbeam** (1990s) is the curriculum's primary revenue manipulation case study. CEO "Chainsaw Al" Dunlap appeared to engineer a turnaround through cost-cutting and revenue growth. In reality:
> - Included **one-time disposals** in regular sales without disclosure
> - Booked revenue on **barbecue grills** shipped to a wholesaler who hadn't accepted ownership risks — all grills were returned next quarter
> - **Channel stuffing**: induced customers to order excess goods with return rights
> - **Bill-and-hold**: recognized revenue while goods stayed at Sunbeam's warehouse
>
> **The financial statement clues were there:**
>
> | Metric | 1995 | 1996 | 1997 |
> |--------|------|------|------|
> | Revenue growth | — | −3.2% | +18.7% |
> | AR growth | — | −1.3% | +38.5% |
> | Receivables/Revenue | 21.3% | 21.7% | 25.3% |
> | Days Sales Outstanding | 77.6 | 79.1 | 92.4 |
> | AR Turnover | 4.7 | 4.6 | 4.0 |
>
> The critical signal: **AR grew 38.5% while revenue only grew 18.7%**. Receivables/revenue jumped from 21.7% to 25.3%. DSO ballooned from 79 to 92 days — far worse than the industry median of 50 days.
>
> Even more revealing: Sunbeam had **securitized $59M of receivables** in December 1997, removing them from the balance sheet. Pro-forma (adding them back), AR growth was **66.1%** and DSO was **110.8 days**.

### 4.7 Evaluating Earnings Quality — Expense Recognition

The other major category of manipulation involves **capitalizing expenses** that should be expensed immediately.

> [!example] Case Study: WorldCom
> **[[WorldCom]]**'s most significant fraud was **capitalizing line costs** (expenses for using other companies' telecom networks) instead of expensing them. Because [[capital expenditures]] appear in [[Investing activities]] rather than [[Operating activities]] on the [[cash flow statement]], this had the double effect of:
> - **Inflating [[operating income]]** (lower expenses on the IS)
> - **Inflating [[CFO]]** (costs shifted from operating to investing outflows)
>
> The normal analyst check of "Is NI > CFO?" would have **missed this completely**:
>
> | Year | Net Income | CFO |
> |------|-----------|------|
> | 1999 | $4,013M | $11,005M |
> | 2000 | $4,153M | $7,666M |
> | 2001 | $1,501M | $7,994M |
>
> CFO exceeded NI every year — creating a **false sense of security**. This is why accrual measures can't be applied mechanically in isolation.

**Red flags for expense capitalization:**
- Increasing [[fixed assets]] + stable/increasing [[operating margins]] may indicate capitalization of expenses
- Compare [[Capital expenditure]] patterns to peers
- Look for assets growing faster than revenue without corresponding operational justification

---

## 5. Cash Flow Quality (LOS i, l)

### 5.1 Why Cash Flow Matters

[[CFA_Glossary/Cash flow from operations]] is generally viewed as **less easily manipulated** than [[operating income]] or [[Net income]] because it's based on actual cash movements. However, it is **not** manipulation-proof.

### 5.2 Indicators of High-Quality Cash Flow

For **established companies**, high-quality cash flow has these characteristics:

| Indicator | Description |
|-----------|-------------|
| **Positive [[CFO]]** | The company generates cash from its core operations |
| **CFO from sustainable sources** | Not from one-off working capital liquidation or unusual items |
| **CFO > CapEx + Dividends + Debt Repayments** | Cash flow funds all obligations with room to spare |
| **Low CFO volatility** | Relative to industry peers — stable and predictable |

> [!warning] Life Cycle Matters
> Cash flow patterns depend on a company's **life cycle stage**. A start-up typically has:
> - **Negative CFO** (not yet generating cash from operations)
> - **Negative CFI** (investing heavily in assets)
> - **Positive CFF** (raising capital through debt or equity)
>
> It would be wrong to penalize a start-up for negative CFO — the question is whether the trajectory is improving.

### 5.3 Cash Flow Manipulation Techniques

Even though CFO is harder to manipulate, companies have several levers:

| Technique | Mechanism | Balance Sheet Footprint |
|-----------|-----------|----------------------|
| **Selling [[Accounts receivable]]** | Converts AR to cash, boosting CFO | AR ↓ abruptly on B/S |
| **Stretching [[Accounts payable]]** | Delays cash outflows, inflating CFO | AP ↑ on B/S |
| **Shifting CFF/CFI → CFO** | Reclassifying cash flow items | Changes in classification across periods |
| **Capitalizing operating costs** | Moves expenses from CFO to CFI (as in WorldCom) | ↑ Fixed assets disproportionate to revenue |

> [!tip] IFRS vs. US GAAP Classification Flexibility
> Under [[IFRS]], companies can classify [[interest paid]] as either operating or financing. [[Interest received]] and [[dividends received]] can be operating or investing. Under [[US GAAP]], all three must be classified as **operating**. When comparing an IFRS reporter to a US GAAP reporter, analysts must adjust for these classification differences. Also watch for **year-to-year changes** in classification by IFRS reporters — a switch from classifying interest paid as operating to financing would inflate CFO.

### 5.4 Evaluating Cash Flow Quality — What to Check

From the CFA curriculum (Mark Meldrum notes):
- **Unusual items** or items not seen in prior years' cash flow statements
- **Excessive outflows for [[receivables]] and [[Inventory]]** due to aggressive [[revenue recognition]]
- **Provisions for, and reversals of, [[restructuring charges]]** — are they legitimate?
- **Trends in CFO relative to [[Net income]]** — persistent divergence is a warning sign

---

## 6. Balance Sheet Quality (LOS j, k)

### 6.1 Two Dimensions: Results Quality and Reporting Quality

**Results quality** for the balance sheet means:
- Optimal [[Leverage]]
- Adequate [[Liquidity]]
- Economically successful asset allocation
- Evaluated through [[ratio analysis]] and [[common-size financial statements]]

**Reporting quality** for the balance sheet is assessed across three dimensions:

```
BALANCE SHEET REPORTING QUALITY
═══════════════════════════════

         ┌──────────────┐
    ┌────│ COMPLETENESS │────┐
    │    └──────────────┘    │
    │                        │
    │    Are all relevant    │
    │    items ON the B/S?   │
    │                        │
    ▼                        ▼
┌──────────────┐    ┌──────────────────┐
│   UNBIASED   │    │     CLEAR        │
│ MEASUREMENT  │    │  PRESENTATION    │
└──────────────┘    └──────────────────┘
Are asset/liability          Are disclosures
values fair and              adequate? Is language
neutral?                     clear? Appropriate
                             level of detail?
```

### 6.2 Completeness

[[Completeness]] is compromised by **off-balance-sheet obligations**:

- **[[Take-or-pay contracts]]** — purchase obligations structured so the buyer must either take delivery or pay a penalty. Analysts should [[constructive capitalization|constructively capitalize]] the PV of future obligations.
- **[[Unconsolidated joint ventures]] / [[equity method]] investees** — the parent reports its share of NI but **not** its share of sales, assets, or liabilities. This can:
  - **Overstate [[Profitability ratios]]** (e.g., [[Net profit margin]], [[ROA]]) because the numerator includes investee profits but the denominator excludes investee assets/sales
  - **Understate [[Leverage]]** because investee debt is off-balance-sheet

> [!warning] Watch for ~50% Ownership Stakes
> A company operating with **numerous or material unconsolidated subsidiaries** where ownership approaches 50% is a warning sign. At 50%+ it would typically need to consolidate, bringing all assets and liabilities on-balance-sheet. Structuring ownership at just below 50% to avoid consolidation suggests potential manipulation.

### 6.3 Unbiased Measurement

Unbiased measurement is especially important for assets and liabilities where **valuation is subjective**:

| Area | Potential Bias | Red Flag |
|------|---------------|----------|
| **[[Goodwill]]** | Understating impairment | Market value of equity < book value of shareholders' equity but no [[Impairment]] taken |
| **[[Inventory]]** | Not recognizing obsolescence | [[Inventory turnover]] declining; NRV write-downs absent despite market signals |
| **[[PP&E]] and other [[long-term assets]]** | Understating [[Impairment]] charges | ↑ Asset values with ↓ returns on those assets |
| **[[Deferred tax assets]]** | Under/overstating [[Valuation allowance]] | Significant, unexplainable variations in the allowance account |
| **Investments (Level 3)** | Non-observable inputs for [[Fair value]] | Large % of assets valued using management estimates with no market data |
| **[[Pension]] liabilities** | Discount rate assumptions | Unusually low discount rate to reduce PBO, or inadequate updates |

> [!example] Real-World: Goodwill Overstated
> In August 2012, the Wall Street Journal identified six companies carrying more [[Goodwill]] on their balance sheets than the companies' entire **market values**. If the market is valuing the whole company at less than just its goodwill, that strongly suggests goodwill impairment charges are overdue. This is a failure of unbiased measurement.

### 6.4 Clear Presentation

- Separate vs. aggregate [[line items]] — are important items buried in catch-all categories?
- Clear language in disclosures
- Adequate disclosure in [[notes to financial statements]]
- Appropriate level of detail

---

## 7. Sources of Information About Risk (LOS m)

Evaluating risk is a critical part of the analyst's job. The curriculum identifies five sources:

### 7.1 Auditor's Report

| Aspect | Details |
|--------|---------|
| **Usefulness** | **Limited** — focuses on historical information, provides opinion on GAAP compliance |
| **Clean opinion** | Necessary but not sufficient; unlikely to provide timely warning of potential risks |
| **Key signal** | A **change in auditor** is an important risk indicator — may suggest disagreements with the previous auditor over accounting treatments |
| **Another concern** | An audit firm with **inadequate resources** for the complexity of the engagement |

### 7.2 Notes to Financial Statements

[[IFRS]] and [[US GAAP]] require specific disclosures about:
- [[Contingent obligations]]
- [[Pension]] and [[post-employment benefits]]
- [[Financial instrument]] risks (credit risk, market risk, liquidity risk)
- [[Related party transactions]]
- [[Accounting policies]] and significant estimates

### 7.3 Management Discussion & Analysis (MD&A)

The [[MD&A]] covers:
- Nature of the business
- Objectives and strategies
- Resources, risks, and relationships
- Results and prospects
- Performance measures and indicators

Under US GAAP (Item 7 of [[10-K]]):
- [[Liquidity]]
- [[Capital resources]]
- [[Results of operations]]
- [[Off-balance-sheet arrangements]]
- [[Contractual obligations]]

Risk disclosures in the MD&A focus on items that **significantly affect the entity's strategies and the progress of the entity's value**: interest rate risk, foreign exchange risk, commodity price fluctuations.

### 7.4 Other Required Disclosures

**[[Form 8-K]]** (US) — filed for material events including:
- Capital raising
- Change of management
- Non-timely filings (a warning sign in itself)
- Legal disputes
- Change of control ([[M&A]])

### 7.5 Financial Press

The financial press can be a useful source when reporters uncover financial reporting issues not previously recognized. However, any issue identified in the press **requires independent follow-up and investigation** by the analyst — don't take media reports at face value.

---

## 8. Putting It All Together — The Analyst's Decision Framework

```
START HERE
    │
    ▼
Is reporting quality at least baseline acceptable?
    │                    │
   YES                  NO → STOP. Cannot assess earnings quality.
    │                        Reporting impedes valuation.
    ▼
Are earnings sustainable (recurring)?
    │                    │
   YES                  NO → Low quality. One-off items, 
    │                        non-recurring sources.
    ▼
Are earnings adequate (ROIC > WACC)?
    │                    │
   YES                  NO → Sustainable but insufficient
    │                        returns → may still be low quality
    ▼
✓ HIGH-QUALITY EARNINGS
  → Increases company value
  → Reliable basis for forecasting
```

> [!tip] Integration with Other FSA Topics
> This module connects directly to several other CFA Level II topics:
> - **[[FSA Integration]]** — The DuPont decomposition and accruals ratios you learned in the integration module are tools used here to assess quality
> - **[[Income Statement Analysis]]** — Revenue and expense recognition policies are the primary manipulation levers
> - **[[Cash Flow Statement Analysis]]** — CFO vs. NI comparison is a core diagnostic
> - **[[Balance Sheet Analysis]]** — Off-balance-sheet items and [[Fair value|fair value]] subjectivity
> - **[[Equity Valuation]]** — Earnings quality directly affects your confidence in [[DCF]] and [[multiples]]-based models
> - **[[Intercorporate Investments]]** — Equity method investees can hide [[Liabilities|liabilities]]; [[Consolidation|consolidation]] can bury problems

---

## 9. Quick-Reference Summary Tables

### Earnings Quality Checklist

| Dimension | High Quality | Low Quality / Red Flag |
|-----------|-------------|----------------------|
| **Source** | Core, recurring operations | One-off settlements, asset sales, non-recurring gains |
| **Composition** | Cash-dominated | Accrual-dominated (especially discretionary) |
| **Returns** | [[ROIC]] > [[WACC]] | ROIC < WACC |
| **Revenue** | AR growth ≤ Revenue growth | AR growth >> Revenue growth; ↑ DSO |
| **Expenses** | [[Consistent|Consistent]] capitalization policies | ↑ Fixed assets without ↑ revenue; changing [[Depreciation|depreciation]] policies |
| **Benchmarks** | Results vary naturally | Consistently meet/barely beat consensus |
| **Accruals** | NI ≈ CFO | NI >> CFO persistently |

### Cash Flow Quality Checklist

| Dimension | High Quality | Low Quality / Red Flag |
|-----------|-------------|----------------------|
| **Sign** | Positive CFO | Negative CFO (unless early-stage company) |
| **Source** | Sustainable operations | AR sales, AP stretching, cash flow reclassification |
| **Coverage** | CFO > CapEx + Dividends + Debt Repayment | CFO insufficient for obligations |
| **[[Volatility|Volatility]]** | Low relative to peers | High [[Volatility|volatility]] |
| **Classification** | [[Consistent|Consistent]] classification | Shifts between CFO/CFI/CFF across periods |

### Balance Sheet Quality Checklist

| Dimension | High Quality | Low Quality / Red Flag |
|-----------|-------------|----------------------|
| **Completeness** | All obligations on B/S | Significant off-balance-sheet debt; ~50% stakes avoiding [[Consolidation|consolidation]] |
| **Measurement** | Unbiased fair values | MV Equity < BV Goodwill; unexplained valuation allowance changes |
| **Presentation** | Clear, adequate disclosure | Vague language; important items aggregated into catch-all lines |

---

## 10. Practice Application

> [!example] Comprehensive Example
> You are analyzing **Acme Corp.** and observe the following:
> - Revenue grew 22% last year while the industry averaged 5%
> - [[Accounts receivable]] grew 45% over the same period
> - [[DSO]] increased from 40 days to 58 days (industry median: 35 days)
> - [[Net income]] = $200M; [[CFO]] = $95M
> - Beneish M-score = −1.45
> - Company recently switched auditors
> - [[Goodwill]] = $3.2B; Market cap = $2.8B
> - 48% ownership stake in a subsidiary accounted for under the [[equity method]]
>
> **Assessment:**
> 1. **Revenue quality is poor**: AR growth (45%) far exceeds revenue growth (22%), and DSO is ballooning vs. both its own history and industry norms → possible [[channel stuffing]] or premature recognition
> 2. **Accruals-based earnings**: NI ($200M) >> CFO ($95M) → large accruals gap → low persistence expected
> 3. **M-score signals manipulation**: −1.45 > −1.78 cutoff → flagged as potential manipulator
> 4. **Auditor change**: Warning sign of potential disagreement over accounting treatments
> 5. **[[Goodwill]] overstated**: Market values the whole company at less than its goodwill → [[Impairment|impairment]] likely overdue
> 6. **Off-balance-sheet risk**: 48% equity method investment keeps investee's debts off Acme's [[Balance sheet|balance sheet]], likely understating leverage and overstating [[Profitability ratios|profitability ratios]]
>
> **Conclusion**: Multiple red flags across reporting quality (auditor change, off-balance-sheet structuring) and earnings quality (unsustainable revenue growth, high accruals, potential manipulation). Treat reported earnings with extreme skepticism for [[Valuation|valuation]] purposes.

---

> [!info] Sources
> - CFA Institute 2025 Level II Curriculum, Volume 3, Learning Module 5: *Evaluating Quality of Financial Reports*
> - Mark Meldrum CFA Level II Notes: *Evaluating Quality of Financial Reports*
> - Mark Meldrum CFA Level II Formula Sheet (Revised 01/30/2025)
> - CFA Level II Quick Reference Sheet
