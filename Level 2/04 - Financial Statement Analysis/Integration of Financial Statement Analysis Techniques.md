# 🔗 Integration of Financial Statement Analysis Techniques

> **CFA Level II — Financial Statement Analysis, Learning Module 6**
> *CFA Institute 2025 Curriculum, Volume 3 | Schweser Reading 12 | Mark Meldrum Notes*

---

## Why This Module Matters

Think of the earlier FSA modules as learning individual instruments. This module is the concert — where you play them all together. Every technique you've studied — [[DuPont analysis]], [[accruals]], [[common-size statements]], [[segment reporting]], [[cash flow analysis]] — gets woven into a single, structured investigation of a real company.

The curriculum uses **Nestlé** (CFA Institute textbook) and **Thunderbird [[Corporation|Corporation]]** (Schweser) as extended case studies. The exam loves this material because it tests whether you can *think like an analyst*, not just calculate ratios.

> [!important] Exam Focus
> This is arguably the most important FSA reading. You must be able to: (1) apply the six-phase analysis framework, (2) strip out equity income from associates to isolate core performance, (3) calculate and interpret accruals ratios using both approaches, (4) evaluate capital allocation with segment data, and (5) decompose [[Market value|market value]] to compute an implied [[P/E ratio]].

---

## LOS 12.a: The Financial Analysis Framework

> *Demonstrate the use of a framework for the analysis of financial statements, given a particular problem, question, or purpose.*

### 🏗️ The Intuition — Every Investigation Needs a Map

Imagine you're a detective. You don't start dusting for fingerprints before you even know what crime was committed. Financial analysis works the same way: you start with the *question*, then gather evidence, then interpret it.

The CFA Institute framework is a six-phase process that applies whether you're evaluating a [[long-term equity investment]], critiquing a [[credit rating]], or assessing [[Financial leverage]].

### The Six-Phase Framework

```
┌─────────────────────────────────────────────────────────────┐
│                FINANCIAL ANALYSIS FRAMEWORK                  │
├──────┬──────────────────────────┬────────────────────────────┤
│ Phase│ Action                   │ Output                     │
├──────┼──────────────────────────┼────────────────────────────┤
│  1   │ Define purpose & context │ List of questions to       │
│      │                          │ answer; nature of report   │
├──────┼──────────────────────────┼────────────────────────────┤
│  2   │ Collect input data       │ Financial statements,      │
│      │ - FS, news, industry     │ questionnaires, organized  │
│      │ - Mgmt/supplier talks    │ data tables                │
│      │ - Site visits             │                            │
├──────┼──────────────────────────┼────────────────────────────┤
│  3   │ Process data             │ Adjusted statements,       │
│      │                          │ common-size, ratios,       │
│      │                          │ graphs, forecasts          │
├──────┼──────────────────────────┼────────────────────────────┤
│  4   │ Analyze/interpret        │ Analytical results         │
├──────┼──────────────────────────┼────────────────────────────┤
│  5   │ Communicate conclusions  │ Analyst report with        │
│      │ & recommendations        │ recommendation             │
├──────┼──────────────────────────┼────────────────────────────┤
│  6   │ Follow-up                │ Updated reports,           │
│      │                          │ monitoring triggers        │
└──────┴──────────────────────────┴────────────────────────────┘
```

> [!example] Real-World Application: Nestlé Case Study
> A pension fund portfolio manager wants to evaluate Nestlé for a **long-term core equity holding**. She asks her analyst to answer:
> 1. What are the sources of earnings growth? Are they sustainable over a 5–10 year [[investment horizon]]?
> 2. What is the quality of earnings — do reported earnings represent economic reality ([[CFO]] vs. [[Net income]])?
> 3. Can the [[Capital structure]] support future operations? Are there [[asset]] write-downs or hidden [[Liabilities]] pending?
> 4. What is the relationship of [[earnings]] to [[cash flow]]?
>
> The analyst follows the framework: defines purpose (Phase 1), gathers Nestlé's [[annual report]]s (Phase 2), then spends Phases 3 & 4 doing [[DuPont analysis]], [[segment analysis]], [[accruals]] testing, and [[cash flow]] analysis.

> [!tip] Exam Tip
> Phase 2 (Collect Data) includes talking to management, suppliers, customers, and competitors. Phase 3 (Process Data) is where you create [[common-size statements]] and ratios — don't confuse the two. A classic exam question: "Communicating with company suppliers is an input during which phase?" → **Phase 2: Collecting data.**

### Purposes of Analysis

The framework adapts to different objectives:

| Purpose | Key Focus Areas |
|---------|----------------|
| **Long-term [[Equity]] investment** | [[ROE]] drivers, earnings sustainability, [[cash flow]] adequacy, [[Valuation]] |
| **[[Credit rating]] evaluation** | [[Leverage]], [[Liquidity]], [[debt]] coverage, [[cash flow]] stability |
| **[[Comparable]] [[Valuation]]** | Adjustments for accounting differences, [[earnings normalization]] |
| **Assessing management claims** | Verify [[MD&A]] assertions against actual financial data |

---

## LOS 12.b: Financial Reporting Choices and Biases

> *Identify financial reporting choices and biases that affect the quality and comparability of companies' financial statements.*

### 🎭 The Intuition — Financial Statements Are Not Photographs

A photograph captures reality. Financial statements are more like *paintings* — the artist (management) makes hundreds of choices about what to emphasize, what colors to use, and what to leave out. These choices create **biases** that affect both quality and [[comparability]].

### Sources of Bias in Reporting

> [!warning] Key Reporting Choices That Introduce Bias
> **Revenue:** Aggressive recognition policies (e.g., [[bill-and-hold]], [[FOB shipping]], [[barter transactions]], [[multiple deliverables]]) make it easier to manipulate timing of [[revenue recognition]].
>
> **Expenses:** Capitalizing vs. expensing decisions (e.g., [[software development costs]], [[R&D]]) shift expenses from the [[Income statement]] to the [[Balance sheet]], inflating current [[earnings]].
>
> **Classification:** Reclassifying normal [[operating expenses]] as "special items" or [[restructuring charges]] inflates [[Core earnings]] (called **[[classification shifting]]**).
>
> **Cash Flow:** Management can maximize [[CFO]] by stretching [[Accounts payable]], capitalizing operating expenditures (shifting to [[CFI]]), or selling [[receivables]].

### Extended DuPont: Where Bias Shows Up

The **five-way [[DuPont decomposition]]** is the primary tool for identifying where reporting choices affect [[ROE]]:

$$ROE = \underbrace{\frac{NI}{EBT}}_{\text{Tax Burden}} \times \underbrace{\frac{EBT}{EBIT}}_{\text{Interest Burden}} \times \underbrace{\frac{EBIT}{Revenue}}_{\text{EBIT Margin}} \times \underbrace{\frac{Revenue}{Avg. Assets}}_{\text{Asset Turnover}} \times \underbrace{\frac{Avg. Assets}{Avg. Equity}}_{\text{Leverage}}$$

Each component can be distorted by reporting choices:

| Component | Bias Risk | What to Watch |
|-----------|-----------|---------------|
| **Tax Burden** (NI/EBT) | [[Deferred tax]] assumptions, valuation allowances | Trend in [[effective tax rate]] vs. [[statutory rate]] |
| **Interest Burden** (EBT/EBIT) | Off-balance-sheet [[debt]], [[operating leases]] | Hidden interest in [[lease]] payments |
| **[[EBIT]] Margin** | Expense capitalization, [[revenue recognition]] | Margins vs. peers and trend |
| **[[Asset turnover]]** | [[Impairment]] timing, [[revaluation]] | [[Goodwill]] as % of [[total assets]] |
| **[[Leverage]]** | Off-BS [[Liabilities]], [[SPE]]s, [[operating leases]] | [[Debt-to-equity]] with adjustments |

> [!info] Interpretation of Tax and Interest Burden Ratios
> These ratios work in **reverse**: a *higher* tax burden ratio (NI/EBT closer to 1.0) means a *lower* effective tax rate — less tax burden. Similarly, a higher interest burden ratio means less of EBIT is consumed by interest. Think of them as "what percentage of earnings *survives*" through each layer.

### 🏭 Real-World Example: Isolating Equity Income from Associates

When a company owns 20–50% of another entity, [[equity method]] income flows into [[Net income]] but does NOT pass through [[Revenue]] or [[EBIT]]. This creates a critical distortion in the [[DuPont analysis]].

> [!example] Nestlé's Associates (Textbook Case)
> In 2014, Nestlé reported [[Net income]] of CHF 14,904 million. Of this, CHF 8,003 million (53.7%!) came from [[income from associates]] — primarily its 23.4% stake in L'Oréal. Much of this included a one-time gain of CHF 4,569 million from selling L'Oréal shares and a CHF 2,817 million revaluation gain from acquiring full ownership of Galderma.
>
> **The problem:** Including this associate income, Nestlé's [[Net profit margin]] was 16.27%. Excluding it, Nestlé's *own* margin was only 7.53%. The associates were masking a **declining trend** in core profitability (10.50% → 9.96% → 7.53% over three years).

**How to adjust the DuPont for associates:**

```
ADJUSTED NET PROFIT MARGIN:
   Numerator:  Net Income − Income from Associates
   Denominator: Revenue (unchanged — associates don't contribute revenue)

ADJUSTED ASSET TURNOVER:
   Numerator:  Revenue (unchanged)
   Denominator: Avg. Total Assets − Avg. Investment in Associates

LEVERAGE:
   Do NOT adjust (absent specific info on how the investment was financed)
   → Implicitly assumes same debt/equity mix finances the associate investment
```

> [!example] Worked Example: Thunderbird Corporation (Schweser)
> Thunderbird owns 30% of Eagle Corporation. Selected data:
>
> | | 2023 | 2022 | 2021 |
> |---|---|---|---|
> | Revenue | $848,000 | $813,600 | $774,000 |
> | EBIT | $99,500 | $85,300 | $78,100 |
> | Equity income from Eagle | $15,900 | $12,200 | $10,500 |
> | EBT | $104,300 | $89,700 | $80,100 |
> | Net Income | $73,600 | $62,600 | $55,100 |
> | Avg. Total Assets | $468,000 | $420,000 | $390,000 |
> | Avg. Equity | $346,200 | $322,600 | $282,300 |
> | Avg. Investment in Eagle | $56,400 | $49,250 | $42,100 |
>
> **As-Reported ROE (2023):** $73,600 / $346,200 = **21.26%**
>
> **Adjusted (excl. Eagle):**
> - Net profit margin = ($73,600 − $15,900) / $848,000 = **6.81%**
> - Asset turnover = $848,000 / ($468,000 − $56,400) = **2.06**
> - Leverage = $468,000 / $346,200 = **1.35** (not adjusted)
> - Adjusted ROE = 6.81% × 2.06 × 1.35 = **18.93%**
>
> The equity investment in Eagle adds ~2.3 percentage points to ROE. Without Eagle, the core business has lower margins but higher asset turnover (assets are smaller).

> [!tip] Professor's Note (Schweser)
> Don't adjust [[Leverage]] for the equity investment unless the question *specifically* tells you how the investment was financed. You're implicitly assuming the investment uses the same mix of [[debt]] and [[Equity]] as the rest of the company.

---

## LOS 12.c: Adjustments for Quality and Comparability

> *Evaluate the quality of a company's financial data and recommend appropriate adjustments.*

### 🔧 The Intuition — Before You Compare, You Must Adjust

You wouldn't compare the fuel efficiency of a car measured in miles-per-gallon to one measured in liters-per-100km without converting. Similarly, you can't compare companies without adjusting for differences in [[accounting standards]], methods, and assumptions.

### Key Adjustments

#### 1. Balance Sheet: Off-Balance-Sheet Liabilities

> [!warning] Constructive Capitalization
> Some [[Liabilities]] don't appear on the [[Balance sheet]] but represent real obligations. The analyst should **constructively capitalize** these by estimating the [[present value]] of future payments and adding them to both [[Assets]] and [[Liabilities]].
>
> Common examples:
> - **Take-or-pay contracts** — purchase agreements where the buyer must either take delivery or pay a penalty
> - **Unconsolidated [[joint ventures]]** or [[equity method]] investees that carry significant [[debt]]
> - **Operating commitments** not captured under [[IFRS 16]] / [[ASC 842]]

#### 2. Balance Sheet: Asset Composition Over Time

Present [[Balance sheet]] items as a percentage of [[total assets]] ([[common-size balance sheet]]) and track changes over time:

```
ASSET COMPOSITION ANALYSIS
┌────────────────────────────────────────────────┐
│                                                │
│  Operating Assets = Current Assets + PP&E      │
│  ──────────────────                            │
│  → Generated through CFO activity              │
│  → Revenue-producing core of the business      │
│                                                │
│  Acquisition Assets = Goodwill + Intangibles   │
│  ────────────────────                          │
│  → Generated through CFI activity              │
│  → If growing as % of total assets, company    │
│    is becoming more acquisition-dependent      │
│  → Watch for impairment risk                   │
│                                                │
└────────────────────────────────────────────────┘
```

> [!example] Real-World: Merck's Inventory Reclassification
> In its 2003 [[Annual Report]], Merck reclassified $447.5 million of [[Inventory]] from [[Current assets]] to "Other assets" (a [[non-current asset]]). This was inventory held for product launches not expected to be sold within one year.
>
> **Impact on ratios:**
> - [[Days of inventory on hand]] → **Decreased** (lower inventory numerator relative to [[COGS]])
> - [[Current ratio]] → **Decreased** (current assets fell, current liabilities unchanged)
> - [[Quick ratio]] → **No change** (inventory excluded from quick ratio anyway)
>
> The lesson: always check the notes for reclassifications between reporting periods.

#### 3. Capital Structure Analysis

Examine the composition of [[long-term capital]] over time:

| Component | What to Watch |
|-----------|---------------|
| [[Long-term debt]] | Absolute level, trend, maturity profile |
| [[Deferred tax liabilities]] | May not result in actual cash outflow if the firm keeps growing |
| [[Minority interests]] | Non-controlling claims on subsidiary earnings |
| [[Shareholders' equity]] | Changes from [[retained earnings]] vs. [[share issuances]] vs. [[OCI]] |

> [!info] Key Insight
> Not all [[Liabilities]] necessarily result in an outflow of cash. [[Deferred tax liabilities]] from [[accelerated depreciation]] may persist indefinitely if a firm continuously replaces assets. Similarly, [[pension liabilities]] under [[defined benefit plans]] are based on actuarial assumptions that may overstate the true obligation.

---

## LOS 12.d: Effects of Changes in Accounting Standards

> *Evaluate how a given change in accounting standards, methods, or assumptions affects financial statements and ratios.*

### 📋 The Intuition — New Rules Change the Score

When accounting standards change, the same economic reality gets reported differently. An analyst must understand these effects to avoid confusing an accounting change with a fundamental change in the business.

### Framework for Evaluating Accounting Changes

```
ACCOUNTING CHANGE IMPACT ANALYSIS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Step 1: Identify what changed
         ↓
Step 2: Determine which financial statements are affected
         (Balance Sheet? Income Statement? Cash Flow Statement?)
         ↓
Step 3: Determine the direction of impact on key line items
         (↑ Assets? ↓ Equity? ↑ Expenses?)
         ↓
Step 4: Recalculate affected ratios
         ↓
Step 5: Assess whether the change improves or impairs
         comparability across time and across firms
```

> [!example] Real-World: IFRS 16 Lease Accounting
> Before [[IFRS 16]], firms classified leases as either [[finance leases]] (on-balance-sheet) or [[operating leases]] (off-balance-sheet). IFRS 16 requires lessees to capitalize virtually all leases.
>
> **Balance Sheet:** [[Right-of-use asset]] ↑, [[Lease liability]] ↑ → [[Total assets]] ↑, [[Total liabilities]] ↑
>
> **Income Statement:** [[Rent expense]] → replaced by [[Depreciation]] + [[interest expense]]. Front-loaded interest means **higher total expense in early years**, lower in later years.
>
> **Cash Flow:** [[CFO]] ↑ (principal portion now classified as [[CFF]]), [[CFF]] ↓
>
> **Ratios affected:**
> - [[Debt-to-equity]] ↑ (more liabilities)
> - [[Asset turnover]] ↓ (more assets)
> - [[EBITDA]] ↑ (rent removed, depreciation added back)
> - [[Interest coverage]] ↓ (new interest expense in denominator)
> - [[CFO]] ↑ (looks like better operating cash generation — but it's just reclassification)

> [!warning] Exam Alert
> Users must be aware of **proposed** changes in accounting standards because of financial statement effects and potential impact on [[Valuation]]. The exam may present a scenario where a new standard is being adopted and ask you to assess the impact on [[ratios]] and [[financial statements]].

---

## LOS 12.e: Balance Sheet Modifications, Earnings Normalization, and Cash Flow Adjustments

> *Analyze and interpret how balance sheet modifications, earnings normalization, and cash flow statement related modifications affect a company's financial statements, financial ratios, and overall financial condition.*

This is the most formula-heavy and analytically rich LOS. It covers three major areas.

---

### Part 1: Segment Analysis and Capital Allocation

#### 🏢 The Intuition — Where Is the Company Spending Its Money?

[[Consolidated financial statements]] combine everything into one set of numbers, hiding the performance of individual business units. [[Segment reporting]] requirements force companies to disaggregate this information.

The key question: **Is the company allocating capital to its most profitable segments?**

#### The Capital Allocation Ratio

$$\text{CapEx Allocation Ratio} = \frac{\text{Segment's \% of Total CapEx}}{\text{Segment's \% of Total Assets}}$$

| Ratio | Interpretation |
|-------|---------------|
| **= 1.0** | Segment receives proportional capital spending |
| **> 1.0** | Segment is receiving a "**growth allocation**" — company is growing this segment |
| **< 1.0** | Segment is being **under-invested** — will shrink as a proportion of the company over time |

Compare this ratio to each segment's [[EBIT]] margin to see if capital is going to the *right* places.

> [!example] Thunderbird Corporation: Capital Misallocation
> Thunderbird operates four divisions. Here's the 2023 data:
>
> | Division | EBIT Margin | % of Assets | % of CapEx | CapEx/Asset Ratio |
> |----------|-------------|-------------|------------|-------------------|
> | Aircraft | 22.0% | 18.5% | 12.3% | 0.66 |
> | Automotive | 12.5% | 42.1% | 43.7% | 1.04 |
> | Marine | 10.8% | 26.2% | 24.8% | 0.95 |
> | Specialty Products | 5.2% | 13.2% | 19.2% | 1.45 |
>
> **Red flag:** The **specialty products** division has the *lowest* EBIT margin (5.2%) but the *highest* CapEx allocation ratio (1.45). The company is pouring capital into its worst-performing segment. Meanwhile, the **aircraft** division — with the highest margin — is being starved of capital (ratio of 0.66).
>
> **Conclusion:** Thunderbird may be **overallocating** resources to specialty products. If this continues, company-wide returns will suffer.

> [!tip] Cash Return vs. EBIT Return
> [[EBIT]] margins can be misleading because of [[accrual accounting]] choices. A better measure is **[[cash operating return on assets]]**:
>
> $$\text{Cash Return on Assets} = \frac{EBIT + \text{Depreciation \& Amortization}}{\text{Average Total Assets}}$$
>
> The Nestlé case study showed that the Nutrition & Health Science segment had the *highest* EBIT margin but the *lowest* cash return on assets — because its massive [[Goodwill]] and [[Intangible assets]] (from acquisitions) inflated the asset base.

---

### Part 2: Accruals Analysis and Earnings Quality

#### 📊 The Intuition — Are Earnings Backed by Cash?

[[Earnings]] = [[Cash flow]] + [[Accruals]]. The cash component is more persistent and harder to manipulate. The accruals component is based on estimates and judgments — and is where manipulation hides.

**The lower the accruals ratio, the higher the [[earnings quality]].**

#### Two Approaches to Measuring Accruals

##### Balance Sheet Approach

$$\text{Accruals}_{BS} = NOA_{END} - NOA_{BEG}$$

Where [[Net Operating Assets]] (NOA):
$$NOA = \underbrace{(\text{Total Assets} - \text{Cash} - \text{Marketable Securities})}_{\text{Operating Assets}} - \underbrace{(\text{Total Liabilities} - \text{Total Debt})}_{\text{Operating Liabilities}}$$

$$\boxed{\text{Accruals Ratio}_{BS} = \frac{NOA_{END} - NOA_{BEG}}{(NOA_{END} + NOA_{BEG}) / 2}}$$

##### Cash Flow Statement Approach

$$\text{Accruals}_{CF} = NI - CFO - CFI$$

$$\boxed{\text{Accruals Ratio}_{CF} = \frac{NI - CFO - CFI}{(NOA_{END} + NOA_{BEG}) / 2}}$$

> [!info] Why No CFF in the Cash Flow Approach?
> The purpose is to evaluate the persistence of [[earnings]]. [[Net income]] arises from transactions associated with [[CFO]] (normal operations) and [[CFI]] (investment income). [[CFF]] arises from *financing decisions* — how the company funds itself — which is separate from the question of whether earnings are real.
>
> Note: Under [[IFRS]], interest and dividends can be classified in [[CFO]] or [[CFF]]. For comparison with [[US GAAP]] firms, you may need to reclassify interest paid from [[CFO]] to [[CFF]].

> [!example] Worked Example: Bickchip Enterprises (Practice Problem)
> Given data for 2020:
> - Net Income: €4,038
> - CFO: €9,822
> - CFI: −€10,068
> - Average NOA: €43,192
>
> **Cash-flow-based accruals ratio:**
> $$\frac{4{,}038 - 9{,}822 - (-10{,}068)}{43{,}192} = \frac{4{,}038 - 9{,}822 + 10{,}068}{43{,}192} = \frac{4{,}284}{43{,}192} = 9.9\%$$
>
> The accruals ratio fell from 11.0% in 2018 to 5.9% in 2019, then rose to 9.9% in 2020. The overall net decline indicates a **slight improvement** in earnings quality.

> [!warning] Interpreting Accruals Ratios
> - **Low and stable** → High-quality earnings (Nestlé: 6.6%, −2.4%, 10.6% — relatively contained)
> - **High and rising** → Possible earnings manipulation
> - **Wide fluctuations** → Could indicate manipulation OR legitimate acquisition activity (acquisitions create large swings in NOA)
> - The two approaches can give **different results** because of acquisitions/divestitures, exchange rate effects, and inconsistent treatment of items between the BS and CFS

---

### Part 3: Cash Flow Confirmation of Earnings

#### Cash Generated from Operations (CGO)

To compare [[cash flow]] to [[operating income]], you must put them on the same basis. [[CFO]] deducts cash paid for interest and taxes, but [[EBIT]] does not. So we add them back:

$$\boxed{CGO = CFO + \text{Cash Interest Paid} + \text{Cash Taxes Paid}}$$

Or equivalently:

$$CGO = EBIT + \text{Non-cash Charges} - \Delta \text{Working Capital}$$

Then compute:

$$\text{CGO to Operating Income} = \frac{CGO}{EBIT}$$

| Ratio | Interpretation |
|-------|---------------|
| **> 1.0** | Cash flow *exceeds* accrual earnings → Earnings confirmed by cash ✅ |
| **< 1.0** | Cash flow *trails* accrual earnings → Potential quality concern ⚠️ |
| **Declining trend** | Even if > 1.0, a falling ratio suggests deterioration |

> [!tip] IFRS vs. US GAAP Adjustment
> Under [[IFRS]], a firm may classify cash interest paid as [[CFF]] instead of [[CFO]]. If it does, **no interest adjustment is needed** when computing CGO — the interest is already excluded from CFO. Under [[US GAAP]], interest paid is *always* in [[CFO]], so you must add it back.

> [!example] Nestlé: Cash Flow Confirms Earnings
>
> | | 2014 | 2013 | 2012 |
> |---|---|---|---|
> | Cash generated from operations (CHF M) | 17,199 | 18,206 | 18,525 |
> | Operating profit (CHF M) | 10,905 | 13,068 | 13,388 |
> | **CGO / Operating Profit** | **1.58** | **1.39** | **1.38** |
>
> Cash substantially exceeded operating profit in all three years — a strong sign that earnings are supported by real cash flows. However, the *trend* in cash return on total assets was declining (15.5% → 14.8% → 13.5%), suggesting management's asset allocation may be becoming less effective.

#### Additional Cash Flow Ratios

| Ratio | Formula | What It Tells You |
|-------|---------|-------------------|
| **Cash flow to reinvestment** | CFO / [[Capital expenditures]] | Can the firm fund its CapEx internally? (>1.0 is healthy) |
| **Cash flow to total debt** | CFO / Total [[debt]] | How quickly could CF retire all debt? |
| **Cash flow interest coverage** | (CFO + Interest + Taxes) / Interest paid | Cash-based [[Interest coverage]] |
| **Cash return on total assets** | Cash from operations / Avg. [[total assets]] | Cash-based [[ROA]] — unaffected by accrual choices |

---

### Part 4: Market Value Decomposition

#### 💰 The Intuition — What's the Company Worth *On Its Own*?

When a company owns a significant stake in a publicly traded [[associate]], part of the parent's [[market capitalization]] reflects the value of that investment. To assess whether the parent's *own* operations are fairly valued, strip out the associate.

#### Steps

```
MARKET VALUE DECOMPOSITION
━━━━━━━━━━━━━━━━━━━━━━━━

1. Parent's Market Cap                       $137.0 B
2. − Pro rata share of associate's market cap
     (Associate Mkt Cap × Ownership %)
     (€60B × 30% × $1.40/€ exchange rate)   −$25.2 B
                                             ─────────
3. = Implied standalone value of parent      $111.8 B

4. Implied P/E of parent (excl. associate):
   Parent NI − Equity income from associate
   ($8.0B − $0.896B = $7.104B)

   Implied P/E = $111.8B / $7.104B = 15.7×

5. Compare to benchmark (S&P 500 at 20.1×)
   → 22% discount to market — possible undervaluation
```

> [!warning] Currency Conversion
> - **Market value** of a foreign associate: convert at the **spot (current) exchange rate**
> - **Earnings** of a foreign associate: convert at the **average exchange rate** for the period (earnings accrue throughout the year)

> [!example] Nestlé's L'Oréal Holding
> At year-end 2014:
> - Nestlé market cap: CHF 231,135 million
> - L'Oréal holding value: CHF 21,747 million (9.4% of Nestlé's market cap)
> - Nestlé standalone value: CHF 209,388 million
>
> L'Oréal contributed CHF 934 million to Nestlé's earnings. Removing this:
> - Nestlé consolidated P/E: 16.0× (vs. S&P 500 at 19.9× → 20% discount)
> - Nestlé standalone P/E: **15.5×** → an even steeper **22% discount**
>
> The analyst found this discount surprising given Nestlé's low leverage and strong cash flows. He concluded the market may be pricing in concern about Nestlé's **slipping core profitability**.

---

## Putting It All Together: The Analyst's Workflow

```
START: Define Purpose (e.g., long-term equity investment)
  │
  ▼
COLLECT: Annual reports, industry data, MD&A, peer comparisons
  │
  ▼
PROCESS & ANALYZE:
  │
  ├──→ DuPont Decomposition
  │      ├── 5-way ROE breakdown
  │      ├── Isolate equity income from associates
  │      └── Adjust for unusual charges (impairments, restructuring)
  │
  ├──→ Asset Base Composition
  │      ├── Common-size balance sheet over time
  │      ├── Operating assets vs. acquisition assets trend
  │      └── Constructively capitalize off-BS obligations
  │
  ├──→ Capital Structure Analysis
  │      ├── Long-term capital components
  │      ├── Working capital ratios (current, quick, defensive interval)
  │      └── Cash conversion cycle
  │
  ├──→ Segment / Capital Allocation
  │      ├── Revenue and EBIT by segment
  │      ├── CapEx % to Asset % ratio
  │      ├── Compare to EBIT margins
  │      └── Cash operating return on segment assets
  │
  ├──→ Accruals & Earnings Quality
  │      ├── BS-based accruals ratio
  │      ├── CF-based accruals ratio
  │      └── CGO / Operating Income ratio
  │
  ├──→ Cash Flow Analysis
  │      ├── CFO to total assets trend
  │      ├── CF to reinvestment, debt, interest coverage
  │      └── Free cash flow adequacy
  │
  └──→ Market Value Decomposition
         ├── Implied standalone value
         ├── Implied P/E (excl. associates)
         └── Compare to market/sector multiples
  │
  ▼
CONCLUDE: Investment recommendation with specific concerns/triggers
  │
  ▼
FOLLOW-UP: Monitor accruals quality, capital allocation, cash returns
```

---

## Key Formulas Summary

| Formula | Purpose |
|---------|---------|
| $ROE = \frac{NI}{EBT} \times \frac{EBT}{EBIT} \times \frac{EBIT}{Rev} \times \frac{Rev}{Avg.Assets} \times \frac{Avg.Assets}{Avg.Equity}$ | Extended [[DuPont]] decomposition |
| $\text{Adjusted NPM} = \frac{NI - \text{Equity Income}}{Revenue}$ | [[Net profit margin]] excluding [[associates]] |
| $\text{Adjusted AT} = \frac{Revenue}{Avg.Assets - Avg.Investment_{assoc}}$ | [[Asset turnover]] excluding associates |
| $NOA = (\text{Assets} - \text{Cash} - \text{Mkt.Sec.}) - (\text{Liab.} - \text{Debt})$ | [[Net operating assets]] |
| $\text{Accruals}_{BS} = \frac{\Delta NOA}{Avg.NOA}$ | BS-based [[accruals ratio]] |
| $\text{Accruals}_{CF} = \frac{NI - CFO - CFI}{Avg.NOA}$ | CF-based [[accruals ratio]] |
| $CGO = CFO + \text{Cash Int.} + \text{Cash Tax}$ | [[Cash generated from operations]] |
| $\frac{\text{Segment CapEx \%}}{\text{Segment Asset \%}}$ | [[Capital allocation]] ratio |
| $\text{Implied Value} = \text{Mkt Cap} - \text{Pro Rata Assoc. Value}$ | [[Market value decomposition]] |
| $\text{Implied P/E} = \frac{\text{Implied Value}}{NI - \text{Equity Income}}$ | Standalone [[P/E multiple]] |

---

## Common Exam Traps

> [!danger] Watch Out For These
> 1. **Adjusting leverage for associates** — Don't do it unless the question tells you how the investment was financed.
> 2. **Tax/interest burden direction** — Higher ratio = less burden (more earnings survive). A tax burden of 0.70 means 30% tax rate, not 70%.
> 3. **IFRS interest classification** — Under IFRS, if interest paid is in CFF, don't add it back when computing CGO.
> 4. **Accruals ratio sign** — CFI is typically negative (cash outflow). In the formula $NI - CFO - CFI$, subtracting a negative CFI *adds* it. Watch your signs carefully.
> 5. **CapEx/Asset ratio interpretation** — Ratio > 1 means "growth allocation" (investing more than proportional), not necessarily that it's *good* allocation.
> 6. **Common-size outputs are Phase 3** — not Phase 2. Phase 2 is collecting raw data; Phase 3 is processing it into ratios and standardized formats.
> 7. **[[Market value|Market value]] decomposition currency** — Use [[Spot rate|spot rate]] for market values, average rate for earnings.

---

## Practice Questions

> [!question] Q1: Framework Phase Identification
> When applying the financial analysis framework, creating [[common-size financial statements]] is best classified as output from which phase?
>
> A. Defining the purpose and context
> B. Collecting input data
> C. Processing input data
>
> > [!tip]- Answer
> > **C.** Common-size statements are created by *processing* raw data into analytically useful formats. This is Phase 3, not Phase 2 (data collection).

> [!question] Q2: DuPont with Associates
> Lorenzo Company reports EBIT margin of 11%, total asset turnover of 1.2, [[Financial leverage|financial leverage]] of 1.5, interest burden of 70%, and tax rate of 35%. Lorenzo's ROE is closest to:
>
> A. 9%
> B. 10%
> C. 11%
>
> > [!tip]- Answer
> > **A.** ROE = Tax burden × Interest burden × EBIT margin × Asset turnover × Leverage
> > = (1 − 0.35) × 0.70 × 0.11 × 1.2 × 1.5 = 0.65 × 0.70 × 0.11 × 1.2 × 1.5 = **9.0%**
> > Note: Tax burden = NI/EBT = 1 − tax rate = 0.65

> [!question] Q3: Cash Flow Accruals Ratio
> MegaCo reports: NI = $12,000; CFO = $33,000; CFI = −$30,000; Average NOA = $180,000. The cash flow accruals ratio is closest to:
>
> A. 5.0%
> B. 7.5%
> C. 10.0%
>
> > [!tip]- Answer
> > **A.** Accruals = NI − CFO − CFI = $12,000 − $33,000 − (−$30,000) = $12,000 − $33,000 + $30,000 = $9,000
> > Accruals ratio = $9,000 / $180,000 = **5.0%**

> [!question] Q4: [[Market value|Market Value]] Decomposition
> Big Company owns 25% of Small Company. Big's market cap is £275,000. Small's market cap is €150,000. The current $/€ exchange rate is £0.85/€. Big's [[Net income|net income]] is £16,000, of which £1,200 is equity income from Small (already translated at the average rate of £0.80/€).
>
> Big's implied P/E without Small is closest to:
>
> A. 16.1
> B. 16.4
> C. 17.2
>
> > [!tip]- Answer
> > **B.** Pro rata share of Small's [[Market value|market value]] = €150,000 × 25% × £0.85 = £31,875
> > Implied value of Big = £275,000 − £31,875 = £243,125
> > Big's NI without Small = £16,000 − £1,200 = £14,800
> > Implied P/E = £243,125 / £14,800 = **16.4×**

---

*Sources: CFA Institute 2025 Level II Curriculum, Volume 3, Learning Module 6; Schweser Reading 12; Mark Meldrum 2025 L2 FSA Notes.*
