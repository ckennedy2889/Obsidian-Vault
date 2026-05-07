# 🏦 Analysis of Financial Institutions
## CFA Level II — Learning Module 4

> [!info] Module Overview
> This module teaches you how to analyze **banks** and **insurance companies** — two types of [[financial institutions]] that require a completely different analytical toolkit than what you'd use for a manufacturing or tech company. The centerpiece is the **CAMELS** framework for banks, plus specialized ratios for **P&C** and **L&H** insurers.
> 
> *Source: CFA Institute 2025 Curriculum Volume 3, LM4; Mark Meldrum Notes*

---

## 1 — What Makes Financial Institutions Different?

> **LOS a: Describe how financial institutions differ from other companies.**

Before diving into ratios and frameworks, you need to understand *why* we can't just run a normal [[DuPont analysis]] on JPMorgan the same way we would on Apple or Caterpillar. Three features make [[financial institutions]] fundamentally different.

### 1.1 Systemic Importance

Think of the financial system as the circulatory system of the economy. If Ford Motor Company fails, the economy takes a hit — but the blood keeps flowing. If a major bank fails, the entire circulatory system can seize up.

This is [[Systemic risk]]: the risk that the [[Impairment|impairment]] of one part of the financial system spreads throughout, dragging the real economy down with it. Banks are *intermediaries* — they sit between savers and borrowers, and they're deeply interconnected with one another through the interbank lending market, [[Level 2/08 - Derivatives/Derivatives]] exposures, and payment systems. When Lehman Brothers collapsed in September 2008, the contagion rippled through every major bank on the planet within days.

Because of this interconnectedness, governments typically insure [[deposits]] up to a certain limit (in the US, the [[FDIC]] insures up to $250,000 per depositor per institution). This prevents [[bank runs]] — the nightmare scenario where everyone tries to withdraw at once.

> [!example] Real-World: Silicon Valley Bank (2023)
> When SVB failed, it triggered panic among depositors at other regional banks — a textbook example of [[contagion effect]]. The FDIC stepped in immediately, illustrating why regulators consider banks "different." No one rushes to protect a failing retailer or software company with the same urgency.

### 1.2 The Nature of the Liabilities

For most companies, [[Liabilities]] are things like [[Accounts payable]], bonds issued, and [[long-term debt]] — obligations to suppliers and bondholders. For a bank, the dominant liability is **customer deposits**. Your checking account is an asset to you, but it's a liability to the bank.

This creates a unique vulnerability: depositors can demand their money at any time. The bank, meanwhile, has lent that money out in 30-year [[Mortgages|mortgages]]. This fundamental **maturity mismatch** — short-term [[Liabilities|liabilities]] funding long-term assets — is the defining feature of banking.

### 1.3 The Nature of the Assets

A manufacturing company's assets are mostly tangible: factories, equipment, [[Inventory]]. A bank's assets are predominantly **financial assets** — [[loans]], [[securities]], and [[Level 2/08 - Derivatives/Derivatives]].

This has two major consequences:

| Feature | Non-Financial Company | Bank |
|---|---|---|
| **Dominant assets** | [[PP&E]], [[Inventory]], [[Intangible assets]] | [[Loans]], [[securities]], [[Level 2/08 - Derivatives/Derivatives]] |
| **[[Valuation|Valuation]] basis** | Mostly [[Historical cost]] (depreciated) | Often at or near [[Fair value]] |
| **Primary risks** | Operational, competitive, technological | [[Credit risk]], [[Interest rate risk]], [[Liquidity risk]], [[Market risk]] |
| **Leverage** | Typically 2–4x | Often 10–15x or higher |

> [!tip] Exam Trap
> A common exam distractor says "banks' assets mostly consist of deposits." That's wrong — **deposits are [[Liabilities|liabilities]]**. Banks' assets are primarily loans and investment securities.

---

## 2 — Financial Regulation

> **LOS b: Describe key aspects of financial regulations of financial institutions.**

### 2.1 Why Regulate?

The goal of regulation is to **minimize [[Systemic risk]]**. Because financial institutions operate globally, a crisis in one jurisdiction can spread everywhere. This necessitates harmonized, global regulatory standards — without them, banks would migrate to the most loosely regulated countries (this is called [[Regulatory arbitrage]]).

### 2.2 The Basel Framework

The most important global regulatory body is the **Basel Committee on Banking Supervision**, a standing committee of the [[Bank for International Settlements]] (BIS). The Basel Committee developed **[[Basel III]]**, which rests on three pillars:

```
┌─────────────────────────────────────────────────────┐
│                    BASEL III                         │
│            Three Pillars of Stability               │
├─────────────────┬──────────────────┬────────────────┤
│   MINIMUM       │   MINIMUM        │   STABLE       │
│   CAPITAL       │   LIQUIDITY      │   FUNDING      │
├─────────────────┼──────────────────┼────────────────┤
│ Min % of risk-  │ Must hold enough │ Must have min. │
│ weighted assets │ high-quality     │ stable funding │
│ funded with     │ liquid assets to │ relative to    │
│ equity capital  │ cover a 30-day   │ liquidity      │
│                 │ stress scenario  │ needs over a   │
│ Prevents        │                  │ 1-year horizon │
│ excessive       │ Ensures survival │                │
│ leverage        │ if depositors    │ Longer-term    │
│                 │ start pulling    │ deposits > ST  │
│                 │ money out        │ deposits       │
│                 │                  │ Consumer       │
│                 │                  │ deposits >     │
│                 │                  │ interbank      │
│                 │                  │ funds          │
└─────────────────┴──────────────────┴────────────────┘
```

> [!important] Impact of Basel III
> Basel III has forced banks to:
> - Focus on [[asset quality]]
> - Hold capital against operational risk (not just credit risk)
> - Develop improved risk assessment processes
> - Improve the quality and composition of their capital base

### 2.3 Other Global Regulatory Bodies

| Organization | Primary Focus |
|---|---|
| **[[Financial Stability Board]]** (FSB) | Coordinate actions to identify and manage [[Systemic risk]] |
| **[[IOSCO]]** (International Organization of Securities Commissions) | Promote fair, efficient securities markets |
| **[[IAIS]]** (International Association of Insurance Supervisors) | Improve supervision of the insurance industry |
| **[[IADI]]** (International Association of Deposit Insurers) | Improve effectiveness of deposit insurance systems |

At the individual country level, regulators enforce these frameworks. In the US, the [[FDIC]], [[Federal Reserve]], and [[OCC]] oversee banking; the [[NAIC]] oversees insurance. In some countries like Japan, a single body (the Financial Services Agency) oversees both.

> [!example] Real-World: HSBC's Regulatory Complexity
> HSBC Holdings, as one of the most global banks, discloses that it is "regulated and supervised by approximately 400 different central banks and other regulatory authorities." As a bank's global operations expand, compliance requirements multiply enormously.

---

## 3 — The CAMELS Approach to Bank Analysis

> **LOS c: Explain the CAMELS approach to analyzing a bank, including key ratios and its limitations.**
> **LOS d: Analyze a bank based on financial statements and other factors.**

### 3.0 What is CAMELS?

**CAMELS** is a six-component bank rating system originally developed by US bank regulators. An examiner assigns each component a score from **1** (best — strong risk management, minimal concern) to **5** (worst — immediate supervisory attention needed). The overall composite rating summarizes the bank's health.

```
    ╔═══════════════════════════════════════════════╗
    ║              C A M E L S                      ║
    ╠═══════════════════════════════════════════════╣
    ║  C — Capital Adequacy                        ║
    ║  A — Asset Quality                           ║
    ║  M — Management Capabilities                 ║
    ║  E — Earnings Sufficiency                    ║
    ║  L — Liquidity Position                      ║
    ║  S — Sensitivity to Market Risk              ║
    ╚═══════════════════════════════════════════════╝
    
    Rating Scale: 1 (best) ────────────► 5 (worst)
    
    Composite score = Sum of component ratings
    Best possible: 6 (all 1s)
    Worst possible: 30 (all 5s)
    Composite rating = Composite score ÷ 6
```

> [!warning] Ordering ≠ Importance
> The fact that "C" comes first doesn't mean capital is most important. The order is just a mnemonic. Under Basel III, strong capital **and** strong liquidity are equally important.

---

### 3.1 C — Capital Adequacy

**The big question:** Does the bank have enough capital to absorb losses without going under?

#### The Intuition

Imagine you buy a house for $500,000. You put $50,000 down (equity) and borrow $450,000 (mortgage). Your leverage is 10:1. If the house drops 10% in value to $450,000, your equity is wiped out. A bank works the same way — its capital is the equity cushion protecting depositors and creditors from losses on the asset side.

#### Risk-Weighted Assets (RWA)

Not all assets carry the same risk, so Basel III doesn't require the same capital cushion for every dollar of assets. Instead, assets are **risk-weighted**:

| Asset Type | Risk Weight | Rationale |
|---|---|---|
| Cash, sovereign bonds | **0%** | Essentially riskless |
| Residential mortgages | **35–50%** | Secured by property |
| Performing corporate loans | **100%** | Standard credit risk |
| Non-performing loans (90+ days past due) | **>100%** (e.g., 150%) | Elevated loss risk |

> [!example] Calculating RWA
> Suppose a bank has:
> - $10M in cash → $10M × 0% = **$0**
> - $1,000M in performing loans → $1,000M × 100% = **$1,000M**
> - $10M in non-performing loans → $10M × 150% = **$15M**
> 
> **Total RWA = $1,015M**
> 
> Notice: $1,020M in total assets produces only $1,015M in RWA, because cash carries zero weight.

#### Capital Tiers

[[Basel III]] classifies capital into a hierarchy based on loss-absorbing capacity:

```
┌───────────────────────────────────────────────────────────┐
│              CAPITAL HIERARCHY                            │
├───────────────────────────────────────────────────────────┤
│                                                           │
│  COMMON EQUITY TIER 1 (CET1)         ≥ 4.5% of RWA      │
│  ─────────────────────────────                            │
│  Most loss-absorbing form of capital                      │
│  Includes:                                                │
│    • Common stock                                         │
│    • Additional paid-in capital (surplus)                  │
│    • Retained earnings                                    │
│    • Accumulated other comprehensive income (AOCI)        │
│    Less: deduction of intangibles & DTAs                  │
│                                                           │
│  + OTHER TIER 1 CAPITAL                                   │
│  ─────────────────────                                    │
│  Subordinated instruments with:                           │
│    • No fixed maturity                                    │
│    • Discretionary dividends (e.g., some preferred stock) │
│                                                           │
│  TOTAL TIER 1 CAPITAL                 ≥ 6.0% of RWA      │
│                                                           │
│  + TIER 2 CAPITAL                                         │
│  ────────────────                                         │
│  Instruments subordinate to depositors/general creditors  │
│    • Original maturity ≥ 5 years                          │
│                                                           │
│  TOTAL CAPITAL (Tier 1 + Tier 2)      ≥ 8.0% of RWA      │
│                                                           │
└───────────────────────────────────────────────────────────┘
```

> [!example] Real-World: HSBC Capital Ratios (2016)
> 
> | Ratio | 2015 | 2016 | Basel III Min |
> |---|---|---|---|
> | CET1 Ratio | 11.9% | 13.6% | 4.5% |
> | Tier 1 Ratio | 13.9% | 16.1% | 6.0% |
> | Total Capital Ratio | 17.2% | 20.1% | 8.0% |
> 
> HSBC's ratios are well above Basel III minimums and **strengthened** year-over-year, as RWA declined while capital was maintained. This would warrant a strong CAMELS rating on capital adequacy.

---

### 3.2 A — Asset Quality

**The big question:** How risky are the bank's assets, and how well is credit risk managed?

#### Loans: The Core Asset

[[Loans]] are the largest component of a bank's assets. Evaluating loan quality involves:

- **Creditworthiness of borrowers** — What's the default probability?
- **Adequacy of the [[allowance for loan losses]]** — Has the bank set aside enough to cover expected defaults?
- **Concentration risk** — Is the portfolio diversified, or heavily exposed to one sector/geography?

Loans are carried at [[amortized cost]], shown net of allowances for loan losses. Watch for changes in the allowance: a steadily declining allowance relative to total loans might indicate the bank is becoming overconfident about credit quality.

#### Investment Securities

Banks also hold investment portfolios. The accounting treatment differs:

| Classification | IFRS | US GAAP | B/S Treatment | Unrealized G/L |
|---|---|---|---|---|
| Amortized cost | [[Amortized cost]] | [[Held-to-maturity]] (debt only) | [[Amortized cost]] | Not recognized |
| [[FVOCI]] | [[Fair value through OCI]] | [[Available-for-sale]] (debt only) | [[Fair value]] | Through [[OCI]] |
| [[FVPL]] | [[Fair value through P&L]] | [[Held-for-trading]] (debt & equity) | [[Fair value]] | Through [[Income statement]] |

Under current US GAAP, **equity securities** are carried at [[Fair value]] with unrealized gains/losses flowing through the [[Income statement]], regardless of intent.

> [!tip] Key Exam Point
> A large proportion of assets classified as Level 3 in the [[fair value hierarchy]] (unobservable inputs, model-based) is a red flag for [[asset quality]]. Level 1 (quoted prices) is most reliable and most liquid; Level 2 (observable but not quoted) is intermediate.

> [!example] Real-World: Citigroup Asset Quality
> An analyst examining Citigroup would look at the trend in non-performing loans as a percentage of total loans, the adequacy of the [[loan loss provision]], geographic and sector concentration, and the proportion of Level 3 assets. If non-performing loans are rising while the allowance is flat or declining, the bank may be under-reserving — a serious warning sign.

---

### 3.3 M — Management Capabilities

**The big question:** Can management identify profitable opportunities while effectively managing risk?

This is the most **qualitative** component of CAMELS. You can't compute a single ratio for management quality, but you can look for evidence:

- **Governance structure** — Is there an independent board? Separation of CEO/Chairman?
- **Internal controls** — Does the bank have robust risk management systems? Has it had any material weaknesses?
- **Financial reporting quality** — Any restatements? Audit qualifications?
- **Risk appetite** — Is the bank prudently managing credit, market, operating, and legal risk?
- **Track record** — Has management delivered consistent results, or are there boom-bust swings suggesting excessive risk-taking?

> [!example] Real-World: Wells Fargo Fake Accounts Scandal (2016)
> Wells Fargo employees opened millions of unauthorized accounts to meet aggressive sales targets. This was a catastrophic management failure — the governance structure, internal controls, and corporate culture all failed simultaneously. An analyst using CAMELS would have assigned a very poor management rating, even though the bank's financial ratios looked strong on the surface.

---

### 3.4 E — Earnings

**The big question:** Are earnings high quality, sustainable, and adequate relative to the bank's cost of capital?

#### Revenue Components

A bank's revenue comes from three primary sources, each with different quality characteristics:

```
┌──────────────────────────────────────────────────────┐
│              BANK REVENUE SOURCES                    │
├────────────────────┬─────────────────────────────────┤
│ Net Interest       │ Interest earned on loans/        │
│ Income (NII)       │ securities MINUS interest paid   │
│                    │ on deposits/borrowings            │
│                    │ ► MOST STABLE, core business     │
├────────────────────┼─────────────────────────────────┤
│ Service/Fee        │ Transaction fees, advisory,      │
│ Income             │ wealth management, etc.           │
│                    │ ► MODERATELY STABLE              │
├────────────────────┼─────────────────────────────────┤
│ Trading            │ Gains/losses from proprietary    │
│ Income             │ trading activities                │
│                    │ ► MOST VOLATILE                  │
└────────────────────┴─────────────────────────────────┘
```

#### Earnings Quality Concerns

Bank earnings are heavily influenced by estimates:

- **[[Loan loss provisions]]** — Too low = overstated earnings now, big write-downs later. Too high = "cookie jar" reserves that can be released to inflate future earnings.
- **[[Fair value]] estimates** — Level 3 assets require model-based valuations. Management has enormous discretion.
- **[[Goodwill]] impairment** — Banks that grew through acquisitions may carry large goodwill balances vulnerable to write-down.

High-quality bank earnings are **sustainable** (driven by NII and fee income, not one-time trading gains), based on **reliable estimates**, and **trending upward** over time.

> [!example] Real-World: Citigroup Earnings Analysis
> From the curriculum's Citigroup case study, the analyst examines:
> - Revenue mix (NII vs. fees vs. trading) and whether it's shifting
> - [[Net interest margin]] trends over time
> - The ratio of Level 3 assets to total assets (higher = more estimation risk)
> - Whether [[loan loss provisions]] are consistent with actual loss experience
> 
> Citigroup's earnings showed a revenue mix shift toward fee income and some reliance on trading — the analyst might rate this a 3 (satisfactory with some concerns) rather than a 1 or 2.

---

### 3.5 L — Liquidity

**The big question:** Can the bank meet its short-term obligations if depositors or creditors suddenly demand cash?

Liquidity is existential for a bank. A bank can be **solvent** (assets > liabilities) but still fail if it can't meet immediate cash demands. This is exactly what happened in many bank failures historically — the bank had enough assets overall, but couldn't convert them to cash fast enough.

#### Basel III Liquidity Standards

Basel III establishes two minimum liquidity standards:

**1. Liquidity Coverage Ratio (LCR):**

$$LCR = \frac{\text{High-Quality Liquid Assets (HQLA)}}{\text{Expected Net Cash Outflows over 30 days}} \geq 100\%$$

This measures whether the bank can survive a **30-day liquidity stress scenario** — a sudden, severe loss of funding. HQLA includes things like government bonds and central bank reserves that can be quickly converted to cash.

**2. Net Stable Funding Ratio (NSFR):**

$$NSFR = \frac{\text{Available Stable Funding (ASF)}}{\text{Required Stable Funding (RSF)}} \geq 100\%$$

The NSFR takes a longer view (**one-year horizon**). Each funding source is assigned a stability factor:

| Funding Source | Stability Factor | Rationale |
|---|---|---|
| Consumer deposits (long-term) | High | "Sticky" — people rarely move their bank |
| Consumer deposits (short-term) | Moderate | Less committed |
| Interbank market funds | Low | Can evaporate overnight in a crisis |

Similarly, assets are assigned required stable funding factors based on their liquidity profile — long-dated, illiquid loans require more stable funding than short-term government bonds.

#### Other Liquidity Metrics

Beyond LCR and NSFR, analysts also examine:

- **Concentration of funding** — How dependent is the bank on a single source? If 40% of funding comes from one large institutional depositor, that's dangerous.
- **Contractual maturity mismatch** — The gap between when assets mature and when liabilities come due. A bank with 30-year mortgage assets funded by overnight borrowings has an extreme mismatch.

> [!example] Real-World: Northern Rock (2007)
> The UK bank Northern Rock relied heavily on wholesale funding markets (low stability) rather than retail deposits (high stability). When wholesale markets froze during the 2007 credit crisis, Northern Rock couldn't roll over its short-term borrowings, leading to the first UK bank run in 150 years. Had the NSFR been in effect, it would have flagged this exact vulnerability.

---

### 3.6 S — Sensitivity to Market Risk

**The big question:** How much would adverse market movements hurt the bank's earnings and capital?

Banks face multiple market risks:

| Risk Type | Description | Example |
|---|---|---|
| **[[Interest rate risk]]** | Mismatch between asset/liability repricing | Rising rates hurt if assets reprice slower than liabilities |
| **[[Currency risk]]** | Foreign exchange exposure from global ops | USD strengthening reduces value of foreign subsidiaries |
| **[[Credit spread risk]]** | Widening spreads reduce bond portfolio value | Investment portfolio losses during credit crisis |
| **[[Equity risk]]** | Market declines in equity holdings | Trading portfolio losses |

**[[Interest rate risk]]** is the most important for traditional banks. A bank earns the **spread** between what it charges borrowers and what it pays depositors. If the bank's assets reprice at different speeds or frequencies than its liabilities, interest rate changes can compress or expand that spread unpredictably.

#### Value at Risk (VaR)

Banks commonly use **[[Value at risk]]** (VaR) to quantify market risk exposure. For example, HSBC estimates its VaR using:
- 99% confidence level
- One-day holding period
- Two prior years of pricing data

A declining VaR trend is positive — it indicates the bank is reducing its market risk exposure.

> [!example] Real-World: Interest Rate Sensitivity
> HSBC publishes interest rate sensitivity tables showing how a parallel shift in rates would affect earnings. But these are **static** presentations — they assume the current asset/liability structure remains unchanged. In reality, banks actively manage their interest rate exposure.
> 
> **Why did central banks lower rates after 2008 if lower rates hurt bank earnings?** Because while banks' interest sensitivity tables show negative impacts from rate cuts, central banks' actions also lowered banks' *borrowing costs* to near zero, while lending rates remained positive. The net effect was supportive of bank profitability.

---

### 3.7 Putting CAMELS Together

An analyst can compute an overall CAMELS score by simply averaging the six component ratings, or by applying weights to reflect which components matter most for a particular analysis.

> [!example] Citigroup CAMELS Assessment (from Curriculum)
> 
> | Component | Rating | Weight (Equity Analyst) | Weighted Rating |
> |---|---|---|---|
> | Capital adequacy | 1.0 | 1 | 1.00 |
> | Asset quality | 2.5 | **2** | 5.00 |
> | Management | 2.0 | 1 | 2.00 |
> | Earnings | 3.0 | **2** | 6.00 |
> | Liquidity | 1.0 | 1 | 1.00 |
> | Sensitivity | 1.0 | 1 | 1.00 |
> | **Total** | **10.5** | **8** | **16.00** |
> | **Unweighted CAMELS** | **1.75** | | |
> | **Weighted CAMELS** | | | **2.00** |
> 
> The equity analyst weights asset quality and earnings at **2x** because these drive equity value most directly. The unweighted score of 1.75 looks strong, but the weighted score of 2.00 highlights more concern — indicating flaws that management may need to address.

### 3.8 Limitations of CAMELS

> [!danger] Key Limitations
> - **Not comprehensive** — Misses important factors like government support, corporate culture, competitive position
> - **Backward-looking** — Based on current/past data, may not capture emerging risks
> - **Subjective** — Component ratings involve judgment, different analysts may disagree
> - **Weighting is arbitrary** — No universally agreed-upon weights
> - **Static snapshot** — Doesn't capture dynamic interactions between components

---

## 4 — Non-CAMELS Factors in Bank Analysis

> **LOS e: Describe other factors to consider in analyzing a bank.**

### 4.1 Banking-Specific Factors

**Government Support:** Unlike other industries, governments often rescue failing banks because of [[Systemic risk]]. "[[Too big to fail]]" institutions (called [[Systemically Important Financial Institutions]] or SIFIs) carry an implicit government guarantee, which affects their risk profile and cost of funding.

**Government Ownership:** In some countries, governments own banks to promote economic development. A government-owned bank is more likely to receive intervention during economic distress.

**Mission of the Banking Entity:** A community bank serving a single region is fundamentally different from a global bank like HSBC. The community bank is concentrated in one economy; the global bank is more diversified but faces greater complexity. This is a qualitative assessment not captured by CAMELS.

**Corporate Culture:** Is the bank risk-averse or risk-seeking? Warning signs of a problematic culture include:
- Recent losses from concentrated, outsized bets
- Financial statement restatements
- Above-average equity-based compensation (incentivizing short-termism)
- History of slow loss recognition followed by large write-downs

### 4.2 General Factors (Apply to All Companies)

| Factor | Why It Matters for Banks |
|---|---|
| **Competitive environment** | Affects capital allocation decisions and risk-taking behavior |
| **Off-balance-sheet items** | [[VIEs]], [[pension]] shortfalls, [[assets under management]] — can create hidden exposures |
| **Segment information** | Shows how capital is allocated across consumer, commercial, investment banking, etc. |
| **Currency exposure** | Global banks face [[translation risk]] and transaction risk across multiple currencies |
| **Risk factors** | Annual filing disclosures often reveal legal/regulatory risks not visible elsewhere |
| **Basel III disclosures** | Extensive required disclosures complement the minimum capital ratios |

> [!example] Real-World: Deutsche Bank's Culture Problem
> Deutsche Bank's aggressive trading culture led to billions in fines for manipulating benchmark rates (LIBOR scandal), mortgage securities fraud, and sanctions violations. The bank's CAMELS financial ratios didn't fully capture the cultural rot that was generating massive legal liabilities. An analyst relying solely on CAMELS would have missed this.

---

## 5 — Analyzing Insurance Companies

> **LOS f: Describe key ratios and other factors to consider in analyzing an insurance company.**

### 5.0 Two Types of Insurance

[[Insurance companies]] earn revenue from two sources: **[[premiums]]** (what policyholders pay for coverage) and **[[investment income]]** earned on the **[[Float]]** (premiums collected but not yet paid out as claims).

Insurance companies split into two categories with very different characteristics:

| Feature | P&C (Property & Casualty) | L&H (Life & Health) |
|---|---|---|
| **Contract duration** | Usually **short-term** (annual) | Usually **long-term** (decades) |
| **Claim variability** | **High** — "lumpy," driven by unpredictable events (fires, hurricanes, lawsuits) | **Low** — predictable, based on actuarial mortality tables applied to large populations |
| **Examples** | Auto, homeowners, commercial liability, workers' comp | Term life, whole life, annuities, health insurance |
| **Capital requirements** | **Higher** — need bigger equity cushion due to claim unpredictability | **Lower** — more predictable claims allow thinner cushion |
| **Investment style** | **Conservative** — low-risk, high-liquidity | Can take **more risk** — longer float allows riskier investments |
| **Key additional risk** | [[Underwriting risk]], catastrophe risk | [[Interest rate risk]] (duration mismatch between assets and liabilities) |

---

### 5.1 Property & Casualty (P&C) Insurance

#### 5.1.1 Business Profile

P&C insurers protect against loss or damage to property (buildings, autos) and liability to third parties (casualty/liability insurance). A single event like a car accident can trigger both property and casualty claims — these are called **multiple peril policies**.

**Distribution methods:**
- **Direct writers** — Own sales staff (higher fixed costs, lower variable costs)
- **Agency writers** — Independent agents/brokers (lower fixed costs, higher variable commissions)

#### 5.1.2 The Underwriting Cycle

P&C insurance is inherently **cyclical**. Understanding this cycle is critical:

```
   ┌──── HARD MARKET ◄───────────────────── SOFT MARKET ◄────┐
   │                                                          │
   │  • Fewer competitors         • Many competitors          │
   │  • Tight underwriting        • Loose underwriting        │
   │  • Higher premiums           • Price cutting              │
   │  • Strong profitability      • Slim/negative margins     │
   │  • Low combined ratio        • High combined ratio       │
   │                                                          │
   │  Attracts new entrants ──►   Drives out weak players ──► │
   │                                                          │
   └──────────────────────────────────────────────────────────┘
```

The cycle is driven by the industry's **[[combined ratio]]** — total insurance expenses divided by net premiums earned. When the combined ratio is **low** (meaning the industry is profitable), it's a **hard market** that attracts new entrants who cut prices. The resulting price war pushes the combined ratio up (soft market), eventually driving out unprofitable participants and resetting the cycle.

#### 5.1.3 Key P&C Profitability Ratios

> [!important] Premium Terminology
> - **Net premiums written** = Direct premiums written − premiums ceded to reinsurers
> - **Net premiums earned** = The portion of net premiums written that corresponds to coverage provided during the reporting period (accrual basis)
> 
> Premiums are billed in advance (e.g., semi-annually), so they're *earned* over the coverage period.

**The Five Key Ratios:**

**① Loss and Loss Adjustment Expense Ratio**

$$\text{Loss Ratio} = \frac{\text{Loss Expense} + \text{Loss Adjustment Expense}}{\text{Net Premiums Earned}}$$

Measures the quality of underwriting — **lower is better**. Are policies priced appropriately for the risk?

**② Underwriting Expense Ratio**

$$\text{Expense Ratio} = \frac{\text{Underwriting Expenses}}{\text{Net Premiums Written}}$$

Measures efficiency of acquiring new business — **lower is better**. Note: denominator is premiums *written*, not *earned*.

> [!warning] US GAAP Variation
> Some companies report the expense ratio using net premiums **earned** in the denominator instead of written, [[Consistent|consistent]] with US GAAP. Travelers, for example, reports this way. Always check which denominator is being used.

**③ Combined Ratio**

$$\text{Combined Ratio} = \text{Loss Ratio} + \text{Expense Ratio}$$

The master metric of underwriting profitability:
- **< 100%** = Underwriting profit (efficient)
- **> 100%** = Underwriting loss

**④ Dividends to Policyholders (Shareholders) Ratio**

$$\text{Dividends Ratio} = \frac{\text{Dividends to Policyholders/Shareholders}}{\text{Net Premiums Earned}}$$

A **[[Liquidity|liquidity]] measure** — relates cash outflows to premium income.

**⑤ Combined Ratio After Dividends**

$$\text{CRAD} = \text{Combined Ratio} + \text{Dividends Ratio}$$

A stricter, more comprehensive measure of overall efficiency after accounting for all cash distributions.

> [!example] Real-World: P&C Ratio Comparison (2016 Data from Curriculum)
> 
> | Metric | Travelers | Hartford | W.R. Berkley | CNA Financial | Markel |
> |---|---|---|---|---|---|
> | Loss & LAE Ratio | 61.4% | 82.2% | 61.1% | 76.1% | **53.1%** |
> | Expense Ratio | 32.6% | 48.8% | 37.3% | 39.9% | 35.9% |
> | **Combined Ratio** | **94.0%** | **131.0%** | **98.4%** | **116.0%** | **89.0%** |
> | Dividends Ratio | 3.1% | 2.4% | 2.9% | 11.7% | 0.0% |
> | **CRAD** | **97.1%** | **133.4%** | **101.3%** | **127.7%** | **89.0%** |
> 
> **Markel** (combined ratio 89%) was the most profitable [[Underwriter|underwriter]]. **Hartford** (131%) was generating significant underwriting losses — its high loss ratio (82.2%) AND high expense ratio (48.8%) suggest both poor risk selection and operational inefficiency.

#### 5.1.4 Loss Reserves — The Critical Estimate

**[[Loss reserves]]** are an insurer's estimated liability for unpaid claims. This is the single most important estimate on a P&C insurer's [[Balance sheet]], and it's subject to enormous management discretion.

Key things to watch:

- **Underestimation** → Undercharging for risks → eventual insolvency risk
- **Downward revisions of prior-year reserves** → Company was initially conservative (generally positive), BUT large revisions can also signal earnings manipulation
- **Upward revisions of prior-year reserves** → Company initially underestimated losses (warning sign of aggressive profit booking)
- **Long-tail [[Liabilities|liabilities]]** → Some claims (e.g., asbestos, environmental) emerge years after policies were written, making [[Estimation|estimation]] extremely difficult

> [!example] Real-World: Travelers Loss Reserve Development
> From the curriculum: Travelers' 2016 downward revisions of prior-year estimates ($680M) contributed **16.8% of income before taxes**. This means a significant portion of reported profit came not from current business but from releasing old reserves. An analyst must ask: Is this conservative [[Estimation|estimation]], or is the company using "cookie jar" reserves to smooth earnings?

#### 5.1.5 Investment Returns

P&C insurers invest conservatively — mostly in **fixed-income securities** with low risk and high [[Liquidity|liquidity]]. At Travelers, approximately **86% of investments** were fixed-maturity securities, with equities comprising only 1%.

$$\text{Total Investment Return Ratio} = \frac{\text{Total Investment Income}}{\text{Invested Assets}}$$

Analysts often calculate this ratio both **with** and **without unrealized gains** to understand how much of the return depends on market appreciation versus actual income.

#### 5.1.6 Liquidity

P&C insurers need a **high degree of [[Liquidity|liquidity]]** because claims can arise suddenly and unpredictably (natural disasters, mass torts). The [[fair value hierarchy]] is useful here — a portfolio concentrated in Level 1 assets is more liquid than one heavy in Level 2 or 3.

#### 5.1.7 Capitalization

No global risk-based capital standard exists for insurers (unlike banking's [[Basel III]]). However, regional standards do exist:

- **EU:** [[Solvency II]] regime — establishes minimum capital requirements with supervisory intervention below thresholds
- **US:** [[NAIC]] risk-based capital requirements — minimum capital based on size and risk profile, incorporating asset risk, [[Credit risk|credit risk]], and underwriting risk

---

### 5.2 Life & Health (L&H) Insurance

#### 5.2.1 Business Profile

L&H insurers generate revenue from:
- **[[Life insurance|Life insurance]] premiums** — Term life (pays benefit only if death occurs during the term), whole life (combines insurance with a savings vehicle), universal life, variable life
- **[[Health insurance|Health insurance]] premiums** — Coverage for medical expenses and disability income
- **Investment products** — Annuities (fixed or variable), retirement savings
- **Fee income** — From managing investment products

Diversification across revenue sources, products, geographies, and distribution channels reduces risk.

#### 5.2.2 Earnings Characteristics

L&H earnings are heavily influenced by **[[Accounting estimates|accounting estimates]] and judgment**:

- **[[Actuarial assumptions]]** about life expectancy, morbidity, and lapse rates drive the value of future [[Liabilities|liabilities]]
- **Current-period claims expense** includes both actual payments AND interest on estimated future obligations
- **Deferred [[Acquisition|acquisition]] costs (DAC)** — Costs of acquiring new policies are capitalized and amortized based on expected future profits. Changes in estimates affect amortization.
- **Asset/liability [[Valuation|valuation]] mismatches** — Assets may be at [[Fair value]] while liabilities are at [[Historical cost|historical cost]], creating [[Volatility|volatility]] when interest rates change

**L&H [[Profitability ratios|Profitability Ratios]]:**

$$\text{Benefits Ratio} = \frac{\text{Total Benefits Paid}}{\text{Net Premiums Written + Deposits}}$$

$$\text{Expense Ratio} = \frac{\text{Commissions + Expenses}}{\text{Net Premiums Written + Deposits}}$$

Plus standard measures: [[ROA]], [[ROE]], pre/post-tax operating margins, and [[Book value|book value]]ue per share|[[Book value|book value]] per share]].

> [!example] Real-World: MetLife ROE vs. Industry
> 
> | Year | US L&H Sector ROE | MetLife ROE |
> |---|---|---|
> | 2011 | 4.70% | 12.20% |
> | 2012 | 12.60% | 2.00% |
> | 2013 | 12.90% | 5.40% |
> | 2014 | 11.00% | 9.40% |
> | 2015 | 11.20% | 7.50% |
> | 2016 | n/a | 1.00% |
> 
> MetLife outperformed the industry in 2011 but underperformed significantly in subsequent years. The [[Volatility|volatility]] (12.2% to 1.0%) suggests sensitivity to [[Accounting estimates|accounting estimates]] and market conditions, warranting further investigation into what's driving the swings.

#### 5.2.3 Investment Returns

L&H insurers have a **longer float period** than P&C (decades vs. a year), so investment returns are a **key** profitability driver. The longer, more predictable nature of claims allows L&H companies to invest in slightly riskier, higher-yielding assets than P&C insurers.

$$\text{Total Investment Return Ratio} = \frac{\text{Investment Income}}{\text{Invested Assets}}$$

**Key concern:** **Duration mismatch** between assets and liabilities. If an L&H insurer holds 10-year bonds but has 30-year policy obligations, a sustained rise in interest rates could impair the value of their bond portfolio while liabilities (at [[Historical cost|historical cost]]) remain unchanged. Conversely, falling rates make it harder to earn adequate returns on new investments to cover guaranteed policy obligations.

> [!example] Real-World: AIA Group Investment Portfolio (2016)
> 
> | [[Asset class|Asset Class]] | % of Total |
> |---|---|
> | Debt securities | 73.3% |
> | Equity securities | 19.5% |
> | Loans and deposits | 4.6% |
> | [[Investment property|Investment property]] | 2.5% |
> | Other | 0.1% |
> 
> AIA's portfolio is dominated by debt securities, typical for an L&H insurer. The estimated return on fixed-income assets was approximately **4.7%** ($5,417M income on $116,266M average fixed-income assets). Year-over-year, a small shift from loans to equities occurred, reflecting a modest reach for yield.

#### 5.2.4 Liquidity

L&H [[Liquidity|liquidity]] is driven by the **liability structure** — primarily policyholder obligations and policy surrenders. Historically less critical than for P&C (because claims are more predictable), but increasingly important as new investment-linked products can create unpredictable surrender patterns.

One approach (used by S&P): Compare adjusted assets (weighted by convertibility to cash) to adjusted obligations (weighted by withdrawal [[Probability|probability]]), under both normal and stress conditions.

> [!tip] Key Difference
> The standard [[Current ratio]] doesn't apply to L&H companies because their balance sheets often don't separate current vs. non-current classifications.

#### 5.2.5 Capitalization

Like P&C, no global standard exists. Key differences from P&C:
- L&H claims are more predictable → **lower capital requirements** (less equity cushion needed)
- Material exposure to [[Interest rate risk]] → risk-based capital formulas **incorporate [[Interest rate|interest rate]]te risk|[[Interest rate|interest rate]] risk]]** (unlike P&C, where underwriting risk dominates)

---

## 6 — Summary Comparison: Banks vs. P&C vs. L&H

| Dimension | Banks | P&C Insurers | L&H Insurers |
|---|---|---|---|
| **Framework** | CAMELS | Combined ratio + 5 areas | 5 areas of analysis |
| **Revenue drivers** | NII, fees, trading | Premiums, investment income | Premiums, investment income, fees |
| **Key risk** | Credit, [[Interest rate|interest rate]], liquidity | Underwriting, catastrophe | [[Interest rate|Interest rate]], longevity |
| **Earnings concern** | Loan loss provisions, FV estimates | Loss reserves, combined ratio | Actuarial assumptions, DAC amortization |
| **Regulation** | Basel III (global) | Solvency II (EU), NAIC (US) | Solvency II (EU), NAIC (US) |
| **Capital standard** | Global (Basel III) | Regional/jurisdictional | Regional/jurisdictional |
| **[[Investment style|Investment style]]** | Varies (loans are the "investment") | Conservative, high liquidity | Can take more risk, longer duration |
| **Liquidity concern** | Bank runs, wholesale funding | Sudden catastrophe claims | Policy surrenders |

---

## 7 — Exam Strategy

> [!danger] High-Yield Exam Points
> 
> **Must-Know Ratios:**
> - Basel III minimums: CET1 ≥ 4.5%, Tier 1 ≥ 6.0%, Total Capital ≥ 8.0% of RWA
> - LCR ≥ 100%, NSFR ≥ 100%
> - Combined ratio < 100% = underwriting profit
> - CRAD = Combined ratio + Dividends ratio
> 
> **Common Traps:**
> - Deposits are **liabilities** (not assets) for a bank
> - CAMELS ordering ≠ importance
> - CAMELS doesn't cover competitive environment, government support, or corporate culture
> - P&C expense ratio uses net premiums **written** (not earned) in denominator
> - L&H claims are **more predictable** than P&C → lower capital requirements
> - Difference 3 from the practice problem: P&C insurers have **higher** capital requirements (not lower) and invest more conservatively (not in riskier investments) — it's L&H that can seek higher returns
> 
> **Qualitative Points to Remember:**
> - Hard market = low combined ratio → attracts new entrants → soft market cycle
> - Downward reserve revisions = initially conservative (but can mask earnings manipulation)
> - Level 3 assets = red flag for both banks and insurers
> - Government support ("too big to fail") is a factor CAMELS doesn't capture

---

*Module complete. CFA Institute 2025 Level II Curriculum, Volume 3, Learning Module 4. Supplemented by Mark Meldrum lecture notes.*
