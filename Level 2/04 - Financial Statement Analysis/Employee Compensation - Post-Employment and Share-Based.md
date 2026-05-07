---
title: "Employee Compensation: Post-Employment and Share-Based"
subject: "Financial Statement Analysis"
tags: [CFA-L2, financial-statement-analysis]
aliases: ["Post-Employment Benefits", "Share-Based Compensation", "Pension Accounting"]
---

# Employee Compensation: Post-Employment and Share-Based

> [!info] Module Overview
> Employee compensation often accounts for the **majority** of operating costs at most companies. At AstraZeneca, for example, wages and salaries alone represent 30% of total expenses. This module covers the two types of compensation that present the greatest analytical complexity: **share-based compensation** and **post-employment benefits**. Unlike salaries paid shortly after an employee works, these forms of compensation can be paid many years in the future at a cost that is uncertain, requiring significant assumptions and estimates by management.
>
> **Standards:** [[IAS 19]] *Employee Benefits* ([[IFRS]]) · [[IFRS 2]] *Share-based Payment* · Various ASC sections ([[US GAAP]])

---

## LOS 8.a: Contrast Types of Employee Compensation

### The Big Picture: Why Does This Matter?

Think of employee compensation as a spectrum. On the left, you have simple, immediate cash payments — a paycheck every two weeks. On the right, you have complex, deferred promises — a pension that won't be paid for 30 years. The further right you move, the more [[Estimation|estimation]] and judgment is required, and the more room there is for [[earnings management]].

```
COMPENSATION SPECTRUM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Simple / Immediate                                      Complex / Deferred
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

 Short-Term       Long-Term       Termination     Share-Based    Post-Employment
 Benefits         Benefits        Benefits        Compensation   Benefits
 ─────────        ──────────      ────────────    ────────────   ───────────────
 • Wages          • Long-term     • Severance     • RSUs         • Pensions
 • Bonuses          disability    • Career        • Stock        • Retiree
 • Health care    • Sabbatical      counseling      options        medical care
 • Social                         • Continued     • SARs         • Retiree life
   security                         benefits      • ESPPs          insurance
 • Paid leave

 ◄─── Cash ──►   ◄─── Cash ──►   ◄── Cash ──►   ◄── Shares ►   ◄─── Cash ──►
 Vest: Days       Vest: Months    Event-based     Vest: Years    Vest: Decades
 Measure: Known   Measure: Known  Measure: Known  Measure: FV    Measure: PV Est.
```

### The Core Accounting Principle

> [!important] One Principle Governs All Compensation
> Recognize the [[Fair value]] of compensation as an **expense** in the period the employee **provides services**, which is typically the same period the compensation **vests**.

Every type of compensation follows three key dates:

```
COMPENSATION TIMELINE
═══════════════════════════════════════════════════════════════════
  GRANT                    VESTING                   SETTLEMENT
  ─────                    ───────                   ──────────
  Employer communicates    Employee becomes           Employer pays
  terms; employee          unconditionally entitled   compensation
  accepts                  to compensation            (cash or shares)

  Example (wages):         Example (wages):           Example (wages):
  1 Jan — hired            1-14 Jan — works           14 Jan — paycheck

  Example (RSUs):          Example (RSUs):            Example (RSUs):
  1 Jan 20X1 — granted     31 Dec 20X3 — vests        31 Dec 20X3 — shares
                           after 3 years service       issued
═══════════════════════════════════════════════════════════════════
```

### Five Types Compared

| Feature | Short-Term | Long-Term | Termination | Share-Based | Post-Employment |
|---|---|---|---|---|---|
| **Typical vesting** | Days/weeks | Months | Event-based | Years | Years/decades |
| **Payment form** | Cash | Cash | Cash | Shares | Cash |
| **Measurement** | Undiscounted amount | Undiscounted amount | Undiscounted amount | [[Fair value]] at grant date | [[Present value]] of estimated future benefits |
| **B/S offset** | [[Current liabilities]] | [[Non-current liabilities]] | [[Current liabilities]] | [[Equity]] | [[Net pension liability]]/asset |
| **Cash flow impact** | [[CFO]] outflow | [[CFO]] outflow | [[CFO]] outflow | No cash impact (until exercise) | [[CFO]] outflow (contributions) |
| **Estimation complexity** | Low | Low | Low | High | Very high |

> [!example] Real World: Where Compensation Is Reported
> Compensation expense is **not** reported as a single line item. It is **embedded** within functional categories:
> - Factory worker wages → [[Cost of goods sold]]
> - R&D scientist salary + RSU grants → [[Research and development expense]]
> - CEO stock options + pension accrual → [[Selling, general and administrative expenses]]
> - Restructuring severance → Discrete "Restructuring Charges" line item
>
> This means you cannot simply look at one line to see total compensation — you have to dig into the notes.

---

## LOS 8.b: Share-Based Compensation and the Financial Statements

### Why Companies Pay in Shares: The Intuition

Imagine you're a startup founder. You have a brilliant engineer you want to hire, but your cash is limited. You offer them stock instead, telling them: "If we succeed together, you'll share in the upside." This is the essence of share-based compensation — it aligns interests, retains talent through multi-year vesting, and preserves [[Liquidity]].

> [!tip] Advantages and Disadvantages
> **Advantages:**
> - Aligns employee and [[shareholder]] interests (reduces [[Agency costs]])
> - Multi-year vesting improves retention
> - No cash outlay required — preserves liquidity for younger companies
> - Can be combined with minimum share ownership requirements
>
> **Disadvantages:**
> - Individual employee may have limited influence on [[share price]] — so it doesn't necessarily reward individual effort
> - Excessive firm ownership may cause **risk aversion** (managers fear personal wealth loss)
> - Stock options may cause **excessive risk-taking** (asymmetric payoff — upside only)
> - Share price declines make compensation less valuable than cash would have been, damaging retention ("underwater options")

### The Four Instruments

| Instrument | Also Known As | Description | Voting? | Dividends? | Tradeable? |
|---|---|---|---|---|---|
| **[[Restricted stock]]** | RSAs, [[performance shares]], [[RSU\|RSUs]] | Shares or share-like units with sale restrictions lifted upon vesting | RS: Yes / RSU: No | RS: Yes / RSU: No | No (until vested) |
| **[[Stock options]]** | Share options | Non-tradeable [[call options]], typically issued [[At the money]] | No | No | No |
| **Stock appreciation-based** | [[Stock appreciation rights\|SARs]], phantom shares | Cash or shares based on share performance over a period | N/A | N/A | No |
| **Stock purchase-based** | [[ESPP]], [[ESOP]] | Employees purchase shares at a discount | Yes (after purchase) | Yes (after purchase) | Yes (after purchase) |

> [!warning] The Shift from Options to RSUs
> After the early 2000s tech bubble and the 2008 financial crisis, companies shifted heavily from stock options to RSUs. By 2021, options were used in fewer than 50% of S&P 500 CEO compensation packages. Reasons include:
> - RSUs always have *some* value (unless share price = $0), unlike options that can expire worthless
> - RSUs expose the holder to both downside *and* upside risk — better alignment than the asymmetric payoff of options
> - RSUs are simpler for tax calculations and require no exercise price payment

---

### Accounting for Restricted Stock Units (RSUs)

RSUs are the most common form of share-based compensation today. The accounting is straightforward once you grasp three key differences from salary accounting:

1. **Offset goes to [[Equity]]**, not a [[liability]], because you settle in shares, not cash
2. **Vesting takes years**, not weeks, so one grant affects multiple periods
3. **[[Fair value]]** is used as the measurement basis, measured **once** at the grant date — subsequent share price changes do **not** change the expense

> [!info] Grant-Date Fair Value for RSUs
> For RSUs, the fair value is simply the **market price** of the underlying shares on the grant date. If the RSU does not participate in dividends (which is typical), the share price is adjusted **downward** for expected dividends over the vesting period.

#### Worked Example: RSU Accounting

**Facts:** A company grants 25,000 shares to an R&D employee on 1 January 20X1. The award vests in 3 years. Fair value at grant = BRL 273,000.

Annual expense = BRL 273,000 ÷ 3 years = **BRL 91,000/year**

```
FINANCIAL STATEMENT IMPACT — RSU GRANT
═══════════════════════════════════════════════════════════════════════════
                        Y/E 31 Dec 20X1    Y/E 31 Dec 20X2    Y/E 31 Dec 20X3
─────────────────────────────────────────────────────────────────────────────
INCOME STATEMENT
  R&D Expense           (91,000)           (91,000)           (91,000)

BALANCE SHEET
  Share-Based Comp.
  Reserve (Equity)      +91,000            +91,000            +91,000
                                                              Then: Transfer
                                                              273,000 from
                                                              Reserve → Common
                                                              Stock & Paid-in
                                                              Capital

CASH FLOW STATEMENT
  Direct impact         None               None               None
  Indirect method:      Add back 91,000    Add back 91,000    Add back 91,000
  (NI → CFO reconcile)
═══════════════════════════════════════════════════════════════════════════
```

> [!important] Key Point: No Impact on Total Equity or Cash
> Each year, the journal entry is:
> - **DR** Compensation Expense (I/S) → reduces [[Net income]]
> - **CR** Share-Based Compensation Reserve (Equity) → increases equity component
>
> Net effect on total [[shareholders' equity]]: **zero** (expense reduces [[retained earnings]], but the reserve increases by the same amount). There is **no cash impact** at any point.

#### Multiple Overlapping Grants: The Real World

In practice, companies make grants every year, so multiple vintages of RSUs are being expensed simultaneously.

> [!example] Workflow Corporation — Multi-Year RSU Grants
>
> | Date | RSUs Granted | Share Price (JPY) | Aggregate FV (¥M) | Annual Expense (¥M) |
> |---|---|---|---|---|
> | 1 Jan 20X1 | 4,542,000 | 4,360 | 19,803 | 6,601 |
> | 1 Jan 20X2 | 3,521,000 | 3,270 | 11,514 | 3,838 |
> | 1 Jan 20X3 | 5,198,000 | 3,333 | 17,325 | 5,775 |
>
> *All RSUs vest in 3 years. Company does not pay dividends.*
>
> **Total compensation expense by year:**
> - 20X1: ¥6,601M (only 20X1 grant)
> - 20X2: ¥6,601 + ¥3,838 = **¥10,439M** (two grants overlapping)
> - 20X3: ¥6,601 + ¥3,838 + ¥5,775 = **¥16,214M** (three grants overlapping)
>
> If share prices had been 25% higher at the 20X2 and 20X3 grant dates, the 20X3 expense would have been ¥18,617M instead — a **¥2,403M difference** from the same number of RSUs granted. This illustrates why share-based compensation is sensitive to grant-date share prices.

---

### Accounting for Stock Options

[[Stock options]] are non-tradeable [[call options]] on the employer's stock, typically granted [[At the money]] (strike price = current share price).

The key difference from RSUs: the **fair value of the option must be estimated using a pricing model** because options have no observable market price.

> [!info] Option Valuation Requirements
> The model must be:
> 1. Consistent with [[Fair value]] measurement principles
> 2. Based on established principles of financial economic theory
> 3. Reflective of all substantive characteristics of the award
>
> Classic models: [[Black-Scholes-Merton model]], [[Binomial option pricing model]]
>
> **Key valuation inputs (and their effect on option value):**
>
> | Input | Effect if Increased |
> |---|---|
> | Stock price [[Volatility]] | Increases option value |
> | Estimated life of award | Increases option value |
> | [[Risk-free rate]] | Increases option value |
> | [[Dividend yield]] | **Decreases** option value |
> | [[Exercise price]] | **Decreases** option value |
>
> **Volatility is the most subjective input** — typically based on implied volatility from exchange-traded options or historical volatility of the share price. A company using a lower volatility assumption will produce a lower option value and therefore lower compensation expense — a potential lever for [[earnings management]].

#### Worked Example: Stock Option Accounting

**Facts:** On 1 Jan 20X1, a company grants 25 million at-the-money stock options. Share price = JPY 4,360, so strike price = JPY 4,360. Fair value per option = JPY 1,288 (from option pricing model). Options vest 31 Dec 20X3 and expire 1 Jan 20X8.

Total fair value at grant = 25M × ¥1,288 = **¥32,200M**
Annual expense = ¥32,200M ÷ 3 years = **¥10,733M/year**

```
STOCK OPTION LIFECYCLE
═══════════════════════════════════════════════════════════════════════════
                                                    SETTLEMENT SCENARIOS
DURING VESTING (20X1-20X3)                 ┌─────────────────────────────────
Each year:                                 │
  I/S: Compensation expense  (10,733)      │  IF price stays below ¥4,360:
  B/S: SBC Reserve (equity)  +10,733       │    Options remain unexercised
  CFS: No cash impact                      │    No further F/S impact
  Total equity: No change                  │
                                           │  IF price rises to ¥5,400 and
                                           │  6M options exercised:
                                           │    I/S: No impact (already expensed)
                                           │    B/S: SBC Reserve    (7,728)
                                           │         Cash           +26,160
                                           │         Paid-in Cap.   +33,888
                                           │    CFS: CFF inflow     +26,160
                                           │         (6M × ¥4,360 exercise)
                                           └─────────────────────────────────
```

> [!warning] Critical Difference: Options vs RSUs at Settlement
> When options are **exercised**, the company receives **cash** equal to the exercise price × number of options exercised. This is classified as a **[[cash flow from financing activities]]** inflow. RSU vesting, by contrast, involves **no cash** at all.

---

### Vesting Conditions

Vesting determines *when* the employee earns the right to compensation. There are three types:

| Condition | Description | Example | Treatment if Not Met |
|---|---|---|---|
| **Service condition** | Employee must remain employed for a specified period | "RSUs vest after 3 years of continuous service" | Awards are forfeit; previously recognized expense is reversed |
| **Performance condition** | Company must meet a non-market target | "RSUs vest if cumulative [[EPS]] exceeds $5.00 over 3 years" | Awards may be excluded from [[Diluted EPS]] if target appears unlikely |
| **Market condition** | Company must meet a share-price-related target | "RSUs vest if stock outperforms the S&P 500 over 3 years" | Reflected in grant-date fair value; expense is **not** reversed even if condition is not met |

---

### Tax Effects of Share-Based Compensation

Share-based compensation creates a **timing difference** between [[financial reporting]] expense and [[tax deduction]]:

```
TAX TREATMENT: FINANCIAL STATEMENTS vs. TAX RETURN
═══════════════════════════════════════════════════════════════════
           FINANCIAL REPORTING             TAX RETURN
           ────────────────────            ──────────────
Timing:    Spread over vesting period      At settlement
Amount:    Fair value at grant date        Share price at settlement (RSU)
                                           Intrinsic value at exercise (options)
═══════════════════════════════════════════════════════════════════
```

This creates a **windfall** or **shortfall** depending on what happened to the share price between grant and settlement:

| Scenario | IFRS Treatment | US GAAP Treatment |
|---|---|---|
| Settlement price **>** grant price → tax deduction **>** book expense | Gain goes directly to [[Equity]] | **Decrease** in [[income tax expense]] on I/S |
| Settlement price **<** grant price → tax deduction **<** book expense | Loss goes directly to [[Equity]] | **Increase** in [[income tax expense]] on I/S |

> [!example] Real World: Meta Platforms and Tax Windfalls
> Meta Platforms' share price was rising rapidly through 2021, creating large tax windfalls from RSU vesting. The company guided that its effective tax rate would remain below the statutory 21% rate "if stock price remains constant." When Meta's share price declined 72% from January through October 2022, the tax windfalls evaporated and the effective tax rate jumped sharply to the 21% statutory rate — an 8 percentage-point increase vs. the prior year.
>
> **Analyst takeaway under US GAAP:** Do not assume that a historically low [[effective tax rate]] driven by share-based compensation windfalls will persist. Under IFRS, this is less of an issue because windfalls/shortfalls go directly to equity, resulting in more stable effective tax rates.

---

### Shares Outstanding and the Treasury Stock Method

[[Share-based compensation]] is one of the primary drivers of [[shares outstanding]] over time. For example, Meta Platforms' shares increased ~1% per year over the decade since its 2012 IPO, primarily from RSU settlements.

**Basic shares outstanding** increases when awards settle (RSUs vest, options are exercised). Unvested awards are included in **[[diluted shares outstanding]]** using the [[Treasury stock method]] (TSM).

```
TREASURY STOCK METHOD
═══════════════════════════════════════════════════════════════════
  Basic shares outstanding                                  X
  PLUS:  Shares from conversion/exercise of awards          X
  MINUS: Assumed proceeds / Average share price             (X)
  ──────────────────────────────────────────────────────────────
  Diluted shares outstanding                                X
═══════════════════════════════════════════════════════════════════

  Where assumed proceeds = Cash from exercise
                         + Average unrecognized SBC expense
```

> [!example] Worked Example: Diluted EPS Calculation
> **Workflow Corp.** — Year ended 31 Dec 20X1
> - Basic shares outstanding: 176,401,000
> - Outstanding options: 25,000,000 (strike = JPY 4,360)
> - Outstanding RSUs: 3,028,000
> - Unrecognized SBC expense (options): ¥21,467M (¥0 prior year-end)
> - Unrecognized SBC expense (RSUs): ¥13,202M (¥0 prior year-end)
> - Average share price: ¥4,200
>
> **Options (strike ¥4,360 > avg price ¥4,200 → OUT-OF-THE-MONEY → ANTI-DILUTIVE):**
> - Assumed proceeds = (25M × ¥4,360) + (¥21,467M / 2) = ¥119,734M
> - Assumed repurchases = ¥119,734M / ¥4,200 = 28.51M shares
> - Net dilution = 25M − 28.51M = **negative** → anti-dilutive, **excluded**
>
> **RSUs:**
> - Assumed proceeds = ¥0 + (¥13,202M / 2) = ¥6,601M
> - Assumed repurchases = ¥6,601M / ¥4,200 = 1,571,667 shares
> - Net dilution = 3,028,000 − 1,571,667 = **1,456,333** dilutive shares
>
> **Diluted shares = 176,401,000 + 1,456,333 = 177,857,333**
>
> *The 25M anti-dilutive options would be disclosed in footnotes. A conservative analyst may add them back anyway, especially if the share price is volatile.*

**General rules from the TSM:**
- [[In-the-money]] options → dilutive
- [[Out-of-the-money]] / [[At-the-money]] options → anti-dilutive
- RSUs → almost always dilutive (unless share price has dropped well below grant-date price)
- If company reports a **net loss**, all potentially dilutive securities are treated as anti-dilutive (diluted EPS cannot exceed basic EPS)

---

### Real-World Disclosures

> [!example] Meta Platforms 2021 RSU Disclosure (10-K)
>
> | | Shares (thousands) | Wtd-Avg Grant Date FV |
> |---|---|---|
> | Unvested, 31 Dec 2020 | 96,733 | $181.88 |
> | Granted | 59,127 | $305.40 |
> | Vested | (44,574) | $198.95 |
> | Forfeited | (12,438) | $211.58 |
> | **Unvested, 31 Dec 2021** | **98,848** | **$244.58** |
>
> - Unrecognized SBC expense: **$22.77 billion** — expected to be recognized over ~3 years
> - FV of RSUs vested in 2021: **$14.42 billion** (vs $9.38B in 2020, $6.01B in 2019)
> - Income tax benefit from vested awards: **$3.08 billion**
>
> These numbers reveal that Meta's annual SBC run-rate was approaching $8B/year and growing — a material "real cost" despite being non-cash.

---

## LOS 8.c: Forecasting SBC and Shares Outstanding in a Model

### Forecasting Share-Based Compensation Expense

Share-based compensation is typically **not** reported as a discrete [[Income statement]] line item — it's embedded within [[COGS]], [[R&D expense]], and [[SG&A]]. The common forecasting approach:

```
FORECASTING WORKFLOW
═══════════════════════════════════════════════════════════════════
Step 1: ISOLATE SBC from each expense line item
        (using note disclosures)

Step 2: FORECAST each adjusted expense line as % of revenues
        (based on historical trends)

Step 3: FORECAST SBC separately as % of revenues
        Methods:  • Historical average
                  • Management guidance
                  • Reversion to industry/sector average

Step 4: RECOMBINE to get reported expense lines

Step 5: On CFS (indirect method), ADD BACK SBC expense
        in reconciliation of NI → CFO

Step 6: On B/S, ADD SBC expense to equity
        (share-based compensation reserve)
═══════════════════════════════════════════════════════════════════
```

> [!warning] When to Forecast SBC Separately
> For **mature companies**, forecasting operating expenses implicitly (as a % of sales) may be fine because SBC moves proportionally with other expenses. For **early-stage companies**, SBC is often a much higher % of revenues than other operating expenses, so it should be modeled discretely to avoid distortions.

### Forecasting Shares Outstanding

```
SHARES OUTSTANDING FRAMEWORK
═══════════════════════════════════════════════════════════════════
  Basic shares outstanding, beginning of period            X
  + RSUs vested / stock options exercised                  X
  + Other share issuances (secondaries, acquisitions)      X
  − Share repurchases                                     (X)
  ──────────────────────────────────────────────────────────
  Basic shares outstanding, end of period                  X

  + Potentially dilutive securities (% of unvested)        X
  ──────────────────────────────────────────────────────────
  Diluted shares outstanding                               X
═══════════════════════════════════════════════════════════════════
```

Grants net of forfeitures and settlements are typically forecast using growth rates off historical disclosure data.

### Valuation Considerations: SBC Is a Real Cost

> [!danger] The "Non-Cash" Trap
> Some analysts argue SBC is irrelevant to value because it's not a cash expense. **This is flawed.** Share-based compensation is a transfer of value from an issuer to its employees and dilutes existing shareholders. A company cannot increase its value simply by replacing cash compensation with shares.
>
> In fact, many companies repurchase shares on the open market to offset dilution from SBC — effectively converting the "non-cash" expense into a cash one.

**Accounting for SBC in [[DCF valuation]]:**

| Impact | Method |
|---|---|
| **Dilution from outstanding/unvested awards** | Use [[diluted shares outstanding]] as the share count. Conservative analysts use basic shares + gross amount of potentially dilutive securities (bypassing the TSM assumption of repurchases). |
| **Dilution from future awards** | **Deduct SBC expense from [[Free cash flow]]** in the DCF model (treat it as if it were a cash expense). This is the most pragmatic approach. |

> [!example] Why Free Cash Flow Comparisons Can Be Misleading
>
> | | Company A | Company B |
> |---|---|---|
> | Market capitalization | 10,000 | 10,000 |
> | Revenues | 1,000 | 1,000 |
> | Net income | 120 | 120 |
> | SBC expense | 0 | 150 |
> | CFO | 420 | 570 |
> | Capex | 300 | 300 |
> | **Net margin** | **12%** | **12%** |
> | **FCF margin** | **12%** | **27%** |
> | **P/E** | **83x** | **83x** |
> | **P/FCF** | **83x** | **37x** |
>
> Company B *appears* cheaper on P/FCF because it chose to pay with shares instead of cash. But this is misleading — the dilution is real. Analysts should either deduct SBC from FCF or adjust multiples to ensure consistency.

**For multiples-based valuation:** Ensure all companies in a peer comparison use the same measure (all GAAP or all non-GAAP). [[GAAP]] and [[non-GAAP]] multiples are not comparable.

---

## LOS 8.d: Post-Employment Benefits and the Financial Statements

### The Two Structures: DC vs DB

Post-employment benefits include [[pension]] payments and non-monetary benefits (life insurance, medical care) for retired employees.

```
POST-EMPLOYMENT BENEFIT STRUCTURES
═══════════════════════════════════════════════════════════════════

  DEFINED CONTRIBUTION (DC)                DEFINED BENEFIT (DB)
  ─────────────────────────                ────────────────────────
  Employer's obligation:                   Employer's obligation:
  Make agreed-upon contributions           Pay a DEFINED BENEFIT in
  to the plan. Period.                     retirement (e.g., 2% × yrs
                                           service × final salary)

  Investment risk borne by:                Investment risk borne by:
  EMPLOYEE                                 EMPLOYER

  Accounting complexity:                   Accounting complexity:
  SIMPLE                                   VERY COMPLEX
  Expense = Contribution                   Expense ≠ Contribution

  Trend:                                   Trend:
  Growing — most companies                 Declining in private sector
  have shifted to DC                       Still common in public sector
                                           Legacy obligations can be huge

  Real-world example:                      Real-world example:
  401(k) match in the US                   Traditional pension at GM, GE,
                                           UK public sector
═══════════════════════════════════════════════════════════════════
```

> [!tip] Analogy: DC vs DB
> Think of DC like giving your employee a **gift card** — you've fulfilled your obligation the moment you hand it over. What they buy with it is their problem.
>
> DB is like giving your employee a **standing dinner reservation** — you've promised them a specific meal every night for the rest of their life. You'd better hope you've saved enough to cover the bill.

---

### Defined Contribution Plans

Accounting is simple and mirrors short-term benefits:

- **I/S:** Expense = Employer contribution for the period
- **B/S:** Any unpaid contribution → [[current liability]]
- **CFS:** Cash outflow in [[Operating activities]]

No further obligation exists. Nothing more to model.

---

### Defined Benefit Plans: The Balance Sheet

DB plans create an obligation that must be estimated and funded over decades. The company sets up a **separate legal entity** (pension trust fund) that holds [[plan assets]].

```
DB PLAN STRUCTURE
═══════════════════════════════════════════════════════════════════

     EMPLOYER                 PENSION TRUST               RETIREES
     (Sponsor)                FUND (Separate              (Beneficiaries)
                              Legal Entity)
      │                        │                            │
      │── Contributions ──────►│                            │
      │                        │── Pension Payments ───────►│
      │                        │                            │
      │   Cannot withdraw      │   Invested in bonds,      │
      │   contributions        │   stocks, etc.             │
      │                        │   Bankruptcy-remote        │
      │                        │                            │
═══════════════════════════════════════════════════════════════════
```

**The Balance Sheet equation:**

$$\text{Funded Status} = \text{Fair Value of Plan Assets} - \text{Pension Obligation (PBO)}$$

| Funded Status | Meaning | B/S Presentation |
|---|---|---|
| **Positive** (assets > obligation) | [[Overfunded plan]] | [[Net pension asset]] |
| **Negative** (obligation > assets) | [[Underfunded plan]] | [[Net pension liability]] |

> [!important] Key Details
> - The [[Discount rate]] used for the pension obligation = yield on investment-grade [[corporate bonds]] (or government bonds if no liquid corporate market)
> - [[Plan assets]] are the property of the trust, not the company — once contributed, they **cannot be withdrawn**
> - Plan assets are **bankruptcy-remote** — protected from the sponsor's creditors
> - Different plans' funded statuses **cannot be netted** against each other

---

### Defined Benefit Plans: The Income Statement (IFRS)

Under [[IFRS]], pension cost has three components — two in the [[Income statement]] and one in [[OCI]]:

```
IFRS DB PENSION COST
═══════════════════════════════════════════════════════════════════
INCOME STATEMENT:
┌─────────────────────────────────────────────────────────────────┐
│  Service Costs (Operating Expenses):                           │
│    Current service cost: PV of benefits earned this period     │
│    Past service cost: PV of retroactive benefit amendments     │
│                                                                │
│  Net Interest Expense/Income (Below Operating Income):         │
│    = Beginning Funded Status × Discount Rate                   │
│    (Negative funded status → expense; positive → income)       │
└─────────────────────────────────────────────────────────────────┘

OTHER COMPREHENSIVE INCOME:
┌─────────────────────────────────────────────────────────────────┐
│  Remeasurements:                                               │
│    (1) Actuarial gains/losses from changes in assumptions      │
│        (e.g., mortality, salary growth, discount rate)         │
│    (2) Difference between actual return on plan assets         │
│        and the return implied by the discount rate             │
│                                                                │
│  Under IFRS: Remeasurements stay in OCI permanently            │
│              (never recycled to I/S)                           │
└─────────────────────────────────────────────────────────────────┘
```

> [!info] Understanding Net Interest Under IFRS
> IFRS uses a **single discount rate** for both the obligation and the assets. The net interest figure captures the passage of time on the **net funded status**:
>
> - If the plan is underfunded by $1,500 and the discount rate is 6%, net interest expense = $1,500 × 6% = **$90**
> - This implicitly assumes that plan assets earn the same rate as the discount rate. Any difference between the actual return and this assumed return goes to OCI as a remeasurement.

#### Worked Example: IFRS DB Plan

> [!example] Full Numerical Walkthrough
>
> **Beginning of year (31 Dec 20X3):**
> - Benefit obligation: 24,000
> - Plan assets: 22,500
> - Funded status: **(1,500)** (underfunded)
> - Discount rate: 6%
>
> **During the year (20X4):**
> - Current service cost: 4,000
> - Actuarial loss (obligation increased): 2,000
> - Interest cost (6% × 24,000): 1,440
> - Benefits paid: (1,000)
> - Employer contributions: 6,000
> - Actual return on plan assets: 1,200
>
> **End of year (31 Dec 20X4):**
> - Ending obligation: 24,000 + 4,000 + 2,000 + 1,440 − 1,000 = **30,440**
> - Ending plan assets: 22,500 + 6,000 + 1,200 − 1,000 = **28,700**
> - Funded status: **(1,740)** (still underfunded)
>
> **IFRS Income Statement:**
>
> | Component | Amount | Location |
> |---|---|---|
> | Service cost | 4,000 | Operating expenses |
> | Net interest expense (6% × 1,500) | 90 | Below operating income |
> | **Total pension expense (I/S)** | **4,090** | |
>
> **IFRS OCI:**
>
> | Component | Amount | Calculation |
> |---|---|---|
> | Return difference | 150 | Expected return (6% × 22,500 = 1,350) − actual (1,200) |
> | Actuarial loss | 2,000 | Change in obligation assumptions |
> | **Total remeasurement (OCI)** | **2,150** | |
>
> **Total periodic pension cost = 4,090 + 2,150 = 6,240**
>
> **Cash flow statement:** CFO outflow = employer contribution = **6,000**

---

### US GAAP vs IFRS: The Critical Differences

> [!danger] This Is Heavily Tested — Know the Differences Cold

**Balance sheet and cash flow statement:** Identical under both frameworks.

**Income statement and OCI:** Significantly different.

| Component | IFRS | US GAAP |
|---|---|---|
| **Current service cost** | I/S — operating expenses | I/S — operating expenses |
| **Past service cost** | I/S — **immediately** in operating expenses | **OCI** — then amortized to I/S over remaining service lives |
| **Interest on obligation** | Netted: Funded status × discount rate | **Gross:** Discount rate × beginning obligation |
| **Return on plan assets** | Netted (uses discount rate) | **Expected return** on plan assets (management's assumed rate) |
| **Actuarial gains/losses** | OCI — **never** amortized to I/S | OCI — **amortized** to I/S using the [[corridor approach]] |

```
SIDE-BY-SIDE: SAME FACTS, DIFFERENT RESULTS
═══════════════════════════════════════════════════════════════════
Using the example above (disc. rate = 6%, expected return = 8%):

              IFRS                          US GAAP
              ────                          ───────
I/S:                                I/S:
  Service cost      4,000             Service cost       4,000
  Net interest         90             Interest expense   1,440
                                        (6% × 24,000)
                                      Expected return  (1,800)
                                        (8% × 22,500)
  ─────────────────────               ─────────────────────
  Total I/S         4,090             Total I/S          3,640

OCI:                                OCI:
  Return diff.        150             Return diff.         600
    (1,350 − 1,200)                     (1,800 − 1,200)
  Actuarial loss    2,000             Actuarial loss     2,000
  ─────────────────────               ─────────────────────
  Total OCI         2,150             Total OCI          2,600

TOTAL COST:         6,240             TOTAL COST:        6,240
═══════════════════════════════════════════════════════════════════
```

> [!warning] The Total Is Always the Same
> Both frameworks produce the **same total periodic pension cost** — the difference is only in how it's split between the income statement and OCI. Under US GAAP, more items flow through OCI and are amortized to I/S over time, which **smooths** reported earnings.

#### The Corridor Approach (US GAAP Only)

Under US GAAP, cumulative unrecognized actuarial gains/losses sitting in [[AOCI]] are amortized to the income statement **only if** they exceed the "corridor":

$$\text{Corridor} = 10\% \times \max(\text{Beginning PBO}, \text{Beginning Plan Assets})$$

Only the **excess** above the corridor is amortized, spread over the remaining average working lives of employees.

---

### Key Assumptions and Earnings Quality

Pension cost and funded status depend on several assumptions. Analysts must compare these over time and across peers:

| Assumption | Aggressive Choice (↓ expense, ↓ PBO) | Conservative Choice (↑ expense, ↑ PBO) |
|---|---|---|
| Discount rate | Higher | Lower |
| Salary growth rate | Lower | Higher |
| Life expectancy | Lower | Higher |
| Inflation rate | Lower | Higher |
| Expected return on assets (US GAAP only) | Higher (↓ expense only, no PBO effect) | Lower |

> [!tip] Internal Consistency Check
> A company that simultaneously assumes **low inflation** but **high salary growth** has internally inconsistent assumptions — a red flag for [[earnings quality]].

> [!example] Real World: General Electric's Pension Crisis
> At the end of 2007, GE reported a DB plan **surplus** of $4 billion. Over the next decade, low interest rates, passage of time, and increasing lifespan assumptions caused the surplus to become a **deficit exceeding $35 billion** — representing over **40% of GE's market capitalization** by end of 2018.
>
> Unlike companies with high debt that benefit from falling rates, companies with large DB plans **suffer** from falling rates because a lower discount rate increases the PBO. This can overwhelm even strong investment returns on plan assets.

---

## LOS 8.e: Financial Modeling and Valuation for Post-Employment Benefits

### Modeling DB Plans

For material DB plans, the analyst should separately forecast:
- **Service cost** — grows with headcount and salary levels
- **Net interest expense/income** — driven by funded status × discount rate
- **Remeasurements** — typically assumed to be zero in forward projections (unpredictable)
- **Employer contributions** — based on funding policies and regulatory requirements

> [!tip] When Detailed Forecasting Isn't Necessary
> If the DB plan is **small** (net pension liability < 5% of equity market cap), **well-funded**, and/or **closed/frozen** (not accruing new benefits), a simplified approach is acceptable because the plan is not material to the investment case.

### Valuation: The Asymmetric Treatment

```
VALUATION TREATMENT OF DB PLANS
═══════════════════════════════════════════════════════════════════

  ENTERPRISE VALUE CALCULATION:
  ─────────────────────────────
  PV of Free Cash Flows
  − Net Debt
  − Underfunded pension liability  ◄── DEDUCT (it's like debt)
  − Other claims
  ──────────────────────────────────
  = Equity Value

  KEY RULES:
  ┌─────────────────────────────────────────────────────────────┐
  │  Underfunded plan → DEDUCT from enterprise value            │
  │                     (company is obligated to pay regardless) │
  │                                                             │
  │  Overfunded plan  → IGNORE                                  │
  │                     (assets cannot be withdrawn/distributed  │
  │                      to shareholders — they're solely for    │
  │                      paying benefits)                        │
  └─────────────────────────────────────────────────────────────┘
```

**Treatment of future service costs in DCF:**

| Item | Treatment in DCF | Rationale |
|---|---|---|
| **Service cost** | **Leave as an expense** in FCF (do not add back) | Real compensation cost earned by employees — analogous to SBC |
| **Net interest expense/income** | **Exclude** from FCF | Represents unwinding of the discount on the PBO, which is already accounted for by deducting the net pension liability at present value from enterprise value |
| **Contributions** | Report as actual cash outflow in CFS | The cash cost of funding the plan |

> [!important] Summary: Pension [[Valuation|Valuation]] Approach
> 1. Deduct net pension liability from [[Enterprise value]]
> 2. Keep service cost as an expense in [[Free cash flow]]
> 3. Remove net interest expense from FCF (double-counting)
> 4. Ignore overfunded plans
> 5. If company reports under US GAAP with a high expected return assumption, consider adjusting to the [[Discount rate|discount rate]] for a more conservative analysis

---

## IFRS vs US GAAP Summary Table

| Area | IFRS | US GAAP |
|---|---|---|
| **SBC: Grant-date measurement** | Same | Same |
| **SBC: Expense over vesting** | Same | Same |
| **SBC: Tax windfall/shortfall** | Directly to [[Equity]] | Through [[income tax expense]] on I/S |
| **DB: [[Balance sheet|Balance sheet]]** | [[Funded status|Funded status]] | [[Funded status|Funded status]] (same) |
| **DB: Service cost** | I/S immediately | Current: I/S immediately; Past: OCI then amortize |
| **DB: Interest** | Net interest on [[Funded status|funded status]] | Gross interest on PBO |
| **DB: Return on assets** | [[Discount rate|Discount rate]] (implicit) | Expected return (management's estimate) |
| **DB: Actuarial G/L** | OCI — **never** amortized | OCI — amortized via [[corridor approach]] |
| **DB: Past service cost** | I/S immediately | OCI then amortize over service lives |
| **DB: Cash flows** | Contributions in [[CFO]] | Contributions in [[CFO]] (same) |

---

## Key Formulas

$$\text{Funded Status} = \text{Fair Value of Plan Assets} - \text{Pension Obligation}$$

$$\text{Net Interest (IFRS)} = \text{Beginning Funded Status} \times \text{Discount Rate}$$

$$\text{Interest Cost (US GAAP)} = \text{Beginning PBO} \times \text{Discount Rate}$$

$$\text{Expected Return (US GAAP)} = \text{Beginning Plan Assets} \times \text{Expected Rate of Return}$$

$$\text{Annual SBC Expense} = \frac{\text{Grant-Date Fair Value} \times \text{Number of Awards Expected to Vest}}{\text{Vesting Period}}$$

$$\text{Assumed Proceeds (TSM)} = \text{Cash from Exercise} + \text{Avg. Unrecognized SBC Expense}$$

$$\text{Dilutive Securities} = \text{Awards Outstanding} - \frac{\text{Assumed Proceeds}}{\text{Average Share Price}}$$

$$\text{Corridor (US GAAP)} = 10\% \times \max(\text{Beginning PBO}, \text{Beginning Plan Assets})$$

---

## Practice Checks

> [!question] Quick Concept Checks
>
> **Q1:** A company grants RSUs when its share price is $50 and the price rises to $80 by vesting. What is the total compensation expense recognized?
> **A:** The total expense is based on the **$50 grant-date price**, not the $80 [[Settlement|settlement]]nt price|[[Settlement|settlement]] price]]. Share price changes after the [[Grant date|grant date]] do not affect the expense.
>
> **Q2:** Under IFRS, if a DB plan has beginning plan assets of $100M, a beginning obligation of $120M, and a [[Discount rate|discount rate]] of 5%, what is the net interest expense?
> **A:** Net interest expense = ($100M − $120M) × 5% = −$20M × 5% = **$1M expense** (since [[Funded status|funded status]] is negative).
>
> **Q3:** Under US GAAP with the same facts and an expected return of 7%, what are the interest cost and expected return components?
> **A:** Interest cost = $120M × 5% = **$6M**. Expected return = $100M × 7% = **$7M**. Net effect on I/S = $6M − $7M = **−$1M** ([[Net income|net income]] benefit).
>
> **Q4:** A company reports higher [[FCF]] than a peer despite the same [[Net income]]. Investigation shows the difference is entirely due to SBC. Is the company truly more profitable?
> **A:** No. SBC is a real cost that dilutes shareholders. FCF-based profitability measures are inflated for companies with heavy SBC usage. Adjust by deducting SBC from FCF.
>
> **Q5:** In a DCF [[Valuation|valuation]], should an underfunded pension liability be deducted from [[Enterprise value|enterprise value]]?
> **A:** **Yes.** An underfunded pension is treated like [[debt]] — it's an obligation the company must satisfy. An overfunded plan, however, is **ignored** because plan assets cannot be distributed to shareholders.

---

*Sources: CFA Institute 2025 Level II Curriculum, Volume 3, Learning Module 2; Mark Meldrum CFA Level II Notes*
