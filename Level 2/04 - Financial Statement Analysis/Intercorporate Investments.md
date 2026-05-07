# 🏢 Intercorporate Investments — Complete Study Guide

> [!info] **CFA Level II — Financial Statement Analysis | Learning Module 1**
> *Source: 2025 CFA Program Curriculum, Volume 3 — Financial Statement Analysis (CFA Institute) & MarkMeldrum Study Notes*
>
> This is the single most testable topic in FSA at Level II. There are **no shortcuts**. You must understand how and when to use each accounting method, and be able to trace the effects through the financial statements and into ratios.

---

## 📋 Learning Outcomes (LOS 7.a, 7.b, 7.c)

After mastering this material, you should be able to:

1. **Describe** the classification, measurement, and disclosure under [[IFRS]] for:
   - Investments in financial assets
   - Investments in associates
   - Joint ventures
   - Business combinations
   - Special purpose and variable interest entities
2. **Compare and contrast** [[IFRS]] and [[US GAAP]] across all five categories
3. **Analyze** how different accounting methods affect financial statements and ratios

---

# Part 1: The Big Picture — Why This Matters

## 🌍 What Are Intercorporate Investments?

Intercorporate investments are simply **investments that one company makes in another company**. Think of it this way: when Apple buys a small percentage of a chip supplier's stock, or when Google acquires YouTube entirely, or when two automakers form a 50/50 joint venture — these are all intercorporate investments. The accounting, however, is wildly different for each.

Companies make these investments to:
- **Diversify** their asset base (don't put all eggs in one basket)
- **Enter new markets** (buying a local company is faster than building from scratch)
- **Obtain competitive advantages** (lock in a supplier, gain [[Technology|technology]])
- **Deploy excess cash** (earn returns on idle capital)
- **Achieve additional profitability** (expand the revenue base)

These investments can be in **debt securities** (corporate bonds, [[Commercial paper|commercial paper]], redeemable [[Preferred stock|preferred stock]], [[Asset-backed securities]]) or **equity securities** ([[Common stock|common stock]], non-redeemable [[Preferred stock|preferred stock]]).

> [!example] **Real-World Analogy: The Apartment Building**
> Think of intercorporate investing like buying into an apartment building:
> - **< 20% ownership** → You're just a passive investor. You get dividend checks (rent) but have no say in how the building is run. This is an **investment in financial assets**.
> - **20%–50% ownership** → You're a significant partner. You sit on the condo board, influence decisions about renovations and tenants, but you can't unilaterally decide to sell the building. This is an **investment in an associate**.
> - **> 50% ownership** → You control the building. You hire the property manager, set rents, decide on capital improvements. You call the shots. This is a **business [[Combination|combination]]**.
> - **Joint Venture** → You and another investor each own 50% and must agree on every decision. Neither of you can act alone.
> - **SPE/VIE** → You create a separate LLC to hold the building. Technically, you don't "own" it in the voting sense, but you bear all the risk and get all the upside. You're the economic owner even without voting control.

---

## 🗺️ The Classification Framework

> [!important] **The Golden Rule**
> The accounting treatment is determined by the investor's **degree of influence or control** over the investee — not just the percentage of ownership. The percentages are *guidelines*, not hard rules. A company with 15% ownership might have significant influence (if they have a board seat), while a company with 25% might have none (if another shareholder has a controlling block).

The textbook (CFA Institute, Exhibit 1) provides this master summary:

| Category | Typical % | Influence | Accounting Method | IFRS Standard | US GAAP Standard |
|---|---|---|---|---|---|
| **Financial Assets** | $< 20\%$ | Not significant | FVPL, FVOCI, or [[Amortised cost]] | IFRS 9 | FASB ASC 320 |
| **Associates** | $20\% - 50\%$ | Significant | [[Equity Method]] | IAS 28 | FASB ASC 323 |
| **Joint Ventures** | Varies | Shared control | [[Equity Method]] (IFRS) | IAS 28, IFRS 11, IFRS 12 | FASB ASC 323 |
| **Business Combinations** | $> 50\%$ | Control | [[Acquisition method]] + [[Consolidation|Consolidation]] | IFRS 3, IFRS 10, IAS 27 | FASB ASC 805, 810 |
| **SPE / VIE** | Varies | Economic control | [[Consolidation|Consolidation]] (if criteria met) | IFRS 10 | FASB ASC 810 |

---

# Part 2: Investments in Financial Assets (Passive, < 20%)

## 🏦 The Concept: You're Just Along for the Ride

When a company owns less than about 20% of another company's equity — or holds its debt securities — and has no significant influence over the investee's operations, the investment is classified as a **financial asset**. The investor is essentially a passive holder. They receive dividends or interest, and they hope the [[Fair value]] goes up, but they don't get to influence the company's decisions.

> [!example] **Real-World Example**
> Imagine you buy 100 shares of Microsoft. You technically "own" part of Microsoft, but you have zero influence on Satya Nadella's decisions. You get dividends when declared, and you can sell your shares whenever you want. That's a financial asset. Now imagine a large [[Corporation|corporation]] doing the same thing — buying a small stake in another company's stock or bonds. Same idea, different scale.

## 📐 The IFRS 9 Classification System

Prior to IFRS 9 (which replaced IAS 39, effective January 1, 2018), financial assets were classified using a portfolio-based approach with categories like "[[Held-to-maturity|held-to-maturity]]," "[[Available-for-sale|available-for-sale]]," and "held-for-trading." Those terms no longer exist under IFRS (though [[US GAAP]] still uses similar terminology).

Under **IFRS 9**, classification is based on **two tests** applied to the financial asset:

### Test 1: The Business Model Test
*"What is management's objective for holding this financial asset?"*

Are they holding it to **collect contractual cash flows** (like holding a bond to maturity)? Or are they holding it to potentially **sell** it? Or both?

### Test 2: The Cash Flow Characteristics Test (the "SPPI" test)
*"Are the contractual cash flows **S**olely **P**ayments of **P**rincipal and **I**nterest?"*

If the cash flows consist only of [[Principal|principal]] repayment and interest on that [[Principal|principal]] — nothing exotic like equity conversion features — then the asset passes the SPPI test.

> [!tip] **Think of it This Way**
> The SPPI test asks: "Is this a plain-vanilla debt instrument?" If yes, it can potentially be held at [[Amortised cost|amortised cost]]. If no (e.g., [[Convertible Bonds|convertible bonds]], equity instruments), it gets pushed toward [[Fair value|fair value]] treatment.

## 📘 The Three Categories

### <span style="color:#2980b9">Category 1: Amortised Cost</span>

**Who qualifies?** Debt instruments ONLY that pass BOTH tests:
1. ✅ Business model = hold to collect contractual cash flows
2. ✅ Cash flows are SPPI (solely [[Principal|principal]] and interest)

**How it works:**
- Initially recorded at [[Fair value]] (which equals cost at [[Acquisition|acquisition]])
- Subsequently reported at [[Amortised cost]] on the [[Balance sheet]]
   - [[Amortised cost]] = original cost + amortized discount (or − amortized premium)
- **Interest income** is recognized in the [[Income statement]] using the effective interest method
- **Changes in [[Fair value]]** are IGNORED — you don't mark it to market
- **[[Impairment|Impairment]]**: Under IFRS 9's expected credit loss model, companies must evaluate both historical and **forward-looking** information to recognize [[Impairment|impairment]] earlier than under the old "incurred loss" model

> [!example] **Textbook Example: Midland [[Corporation|Corporation]] (CFA Institute Curriculum)**
> Midland purchases a 9% coupon bond, [[Face value|face value]] \$100,000, for \$96,209 (to yield 10%). Coupons paid annually. FV at year-end = \$98,500.
>
> **Under [[Amortised cost|Amortised Cost]]:**
> - Interest revenue = $\$96{,}209 \times 10\% = \$9{,}621$
> - This includes the coupon payment (\$9,000) plus amortized discount (\$621)
> - Year-end [[Balance sheet]] value = $\$96{,}209 + \$621 = \$96{,}830$
> - The \$98,500 [[Fair value]]? **Completely ignored.**
>
> The [[Income statement]] shows \$9,621 of interest income. Nothing else. The market could love this bond or hate it — the financial statements don't care until the bond is sold or impaired.

### <span style="color:#27ae60">Category 2: Fair Value Through Profit or Loss (FVPL)</span>

**Who qualifies?**
- **All equity instruments** that are [[Held for trading|held for trading]] (mandatory)
- **All equity instruments** not designated as FVOCI (default)
- **Debt instruments** that fail the SPPI test (e.g., [[Convertible Bonds|convertible bonds]])
- **Debt instruments** [[Held for trading|held for trading]]
- **Debt instruments** where management elects FVPL to avoid an "accounting mismatch" (when related [[Liabilities|liabilities]] are measured at [[Fair value|fair value]])
- **[[Level 2/08 - Derivatives/Derivatives]]** that are NOT hedging instruments
- Assets with **embedded [[Derivatives|derivatives]]** (e.g., [[Convertible Bonds|convertible bonds]]) — the whole hybrid instrument goes to FVPL

**How it works:**
- Initially recorded at [[Fair value]]
- Subsequently measured at [[Fair value]] on the [[Balance sheet]]
- **ALL changes in [[Fair value|fair value]]** (both realized and unrealized gains/losses) are recognized **directly in the [[Income statement]]** (P&L)
- Interest income and dividend income also recognized in P&L
- This is the **most volatile** classification — every market fluctuation hits your reported earnings

> [!example] **Continuing the Midland Example:**
> **Under FVPL:**
> - Interest revenue = \$9,621 (same calculation)
> - [[Balance sheet]] value = \$98,500 (the [[Fair value]], not [[Amortised cost|amortised cost]])
> - Unrealized gain = $\$98{,}500 - \$96{,}209 - \$621 = \$1{,}670$
> - **[[Income statement]] impact** = \$9,621 (interest) + \$1,670 (unrealized gain) = **\$11,291** total P&L impact
>
> Compare this to [[Amortised cost|amortised cost]] (\$9,621 income). The FVPL method produced \$1,670 *more* income this year. But if the bond's value drops next year, it could produce *less* income. That's the [[Volatility|volatility]] trade-off.

### <span style="color:#e67e22">Category 3: Fair Value Through Other Comprehensive Income (FVOCI)</span>

**Who qualifies?**
- **Debt instruments** with a "hold-to-collect AND sell" business model (i.e., management may collect cash flows but also sell the asset if needed) — AND the cash flows pass the SPPI test
- **Equity instruments** — by **irrevocable election** at initial recognition (IFRS only). Once you choose FVOCI for an equity investment, you **cannot change your mind**

**How it works:**
- Initially recorded at [[Fair value]]
- Subsequently measured at [[Fair value]] on the [[Balance sheet]]
- **Unrealized gains/losses** → recognized in **[[Other comprehensive income]]** (OCI) — this bypasses the [[Income statement]] and goes directly to equity
- **Interest income** (for debt) and **dividend income** (for equity) → recognized in P&L
- When the asset is **sold**, the cumulative unrealized gain/loss is **recycled** from OCI to P&L (for debt instruments). For equity instruments designated as FVOCI, the gains/losses are **never** recycled — they stay in equity permanently.

> [!example] **Continuing the Midland Example:**
> **Under FVOCI:**
> - Interest revenue = \$9,621 (recognized in P&L — same as always)
> - [[Balance sheet]] value = \$98,500 (the [[Fair value]])
> - Unrealized gain = \$1,670
> - But this gain goes to **OCI**, not the [[Income statement]]
> - **P&L impact** = only \$9,621 (interest income)
> - **OCI impact** = +\$1,670
>
> See the difference? The [[Balance sheet]] looks the same as FVPL (\$98,500), but the [[Income statement]] is less volatile because unrealized gains/losses are parked in OCI.

## 📊 Visual Summary: Where Does Everything Go?

```
                           ┌─────────────────┐
                           │ Financial Asset  │
                           │   Acquired at FV │
                           └────────┬────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
     ┌────────▼────────┐  ┌────────▼────────┐  ┌────────▼────────┐
     │  AMORTISED COST │  │      FVPL       │  │     FVOCI       │
     │  (Debt only)    │  │ (Debt & Equity) │  │ (Debt & Equity) │
     └────────┬────────┘  └────────┬────────┘  └────────┬────────┘
              │                     │                     │
   B/S: Amortised cost    B/S: Fair value       B/S: Fair value
              │                     │                     │
   I/S: Interest income   I/S: Interest/Div     I/S: Interest/Div
              │                  + ALL FV changes         │
   FV changes: IGNORED           │              OCI: Unrealized G/L
              │                     │                     │
   Impairment: Expected    No separate            Impairment: Expected
   credit loss model       impairment needed      credit loss model
```

## 🔄 Reclassifications Under IFRS 9

This is an area the curriculum emphasizes heavily:

| Instrument Type | Reclassification Allowed? | When? |
|---|---|---|
| **Equity** instruments | ❌ **Never** | The initial choice (FVPL or FVOCI) is **irrevocable** |
| **Debt** instruments | ✅ **Only** when the business model changes | Must be significant and affect operations; expected to be **very infrequent** |

**What happens on reclassification of debt:**
- The asset is measured at [[Fair value]] on the reclassification date
- If moving from amortised cost → FVPL: any gain/loss is immediately recognized in P&L
- If moving from FVPL → amortised cost: the [[Fair value]] at reclassification date becomes the new [[Carrying value]]
- **No restatement of prior periods** is required

> [!warning] **Exam Trap**
> Students often forget: equity reclassification = NEVER. If you chose FVOCI for an equity investment, you're stuck with it forever. The textbook states this is because "an entity's initial classification of FVPL and FVOCI is irrevocable."

## 🇺🇸 vs. 🌐 IFRS vs. US GAAP — Financial Assets

| Feature | IFRS (IFRS 9) | US GAAP (ASC 320/825) |
|---|---|---|
| **Classification basis** | Business model + SPPI test | Management intent and ability |
| **Debt categories** | Amortised cost, FVPL, FVOCI | Held-to-maturity, Trading, [[Available-for-sale]] |
| **Equity — default** | FVPL | FVPL |
| **Equity — FVOCI option** | Yes (irrevocable election; dividends → P&L; gains never recycled) | Generally not available for equity |
| **Reclassification** | Debt only, when business model changes | Generally not permitted |
| **Impairment model** | Expected credit loss (forward-looking) | Current expected credit loss (CECL) — also forward-looking |
| **Old terminology** | ~~Held-to-maturity~~, ~~Available-for-sale~~ **no longer exist** | Still uses HTM, Trading, AFS |

## 🔍 What Analysts Should Do

The CFA curriculum (and the MarkMeldrum notes) emphasizes this analytical point:

> [!tip] **Analytical Best Practice**
> Evaluate company performance **separately** for operating and investing activities:
> - **Exclude** from operating analysis: interest income, dividend income, realized and unrealized gains/losses on investments
> - **Exclude** non-operating assets from the calculation of return on net operating assets
> - Use market values to adjust pro forma financial statements for consistency when comparing across companies
>
> *Source: CFA Institute Curriculum, LM1, p.10*

---

# Part 3: Investments in Associates & Joint Ventures (20%–50%)

## 🤝 The Concept: You Have a Seat at the Table

When a company holds between **20% and 50%** of the voting rights of another company (either directly or through subsidiaries), it is *presumed* to have **significant influence** — the power to participate in the financial and operating policy decisions of the investee, but **not control** them.

The textbook (CFA Institute Curriculum) lists evidence of significant influence:
- **Board of directors representation**
- **Involvement in policy making**
- **Material intercompany transactions**
- **Interchange of managerial personnel**
- **Dependence on technology**

> [!note] **The Presumption Works Both Ways**
> - Below 20%: Presumed NO significant influence — unless you can demonstrate it (e.g., you have a board seat despite holding only 15%)
> - 20%–50%: Presumed significant influence — unless rebutted (e.g., another shareholder has a controlling block and freezes you out)
>
> The Deutsche Bank annual report, quoted in the textbook, notes that they use the equity method for some investments under 20% because they have representation on boards of directors.

> [!example] **Real-World Analogy: The Business Partnership**
> Imagine you own 30% of a restaurant chain. You don't run the day-to-day operations, but you're on the board. You influence decisions about menu changes, expansion plans, and the hiring of the CEO. You receive your share of profits, but you can't force the company to do anything on your own. That's significant influence — and the accounting method is the **[[Equity Method]]**.

## 📐 The Equity Method — How It Really Works

The [[Equity Method]] is sometimes called **"one-line consolidation"** because the entire investment appears as a **single line item** on the [[Balance sheet]] ("Investment in Associate") and a **single line item** on the [[Income statement]] ("Equity Income" or "Investment Income").

### Initial Recognition

The investment is recorded at **cost** — whatever the investor paid to acquire the shares.

$$\text{Investment in Associate (Day 1)} = \text{Purchase Price}$$

### Subsequent Measurement — The Core Mechanics

Each period, the investment balance is adjusted for three things:

$$\boxed{\text{Inv. in Assoc.}_{\text{end}} = \text{Inv. in Assoc.}_{\text{begin}} + (\% \times \text{NI}) - (\% \times \text{Dividends}) - \text{Amort. of Excess}}$$

Let's break each piece down:

**1. Add: Proportionate share of investee's [[Net income]]**
- This is recognized on the investor's [[Income statement]] as "Investment Income" or "Equity Income"
- It increases the [[Balance sheet]] investment balance
- It represents the investor's claim on the investee's earnings

**2. Subtract: Proportionate share of dividends received**
- Dividends **reduce** the investment balance on the [[Balance sheet]]
- Dividends are **NOT income** under the equity method — they are a **return OF capital**, not a return ON capital
- Cash increases, investment decreases — it's just a reclassification on the [[Balance sheet]]

**3. Subtract: Amortization of excess purchase price** (explained in detail below)

> [!warning] **The #1 Equity Method Mistake on Exams**
> Under the equity method, **dividends are NOT income**. They reduce the investment account. Also, **changes in [[Fair value]]** of the associate's stock are **completely ignored**. This is the opposite of financial assets classified at FVPL.
>
> Think of it this way: under the equity method, you're recording your share of the associate's **actual economic performance** (its net income), not the market's opinion of its value. If the associate earns money, your investment goes up. If it pays you a dividend, your investment goes down (because cash left the associate's coffers).

### 📝 Textbook Example: ABC and XYZ (MarkMeldrum Notes)

> ABC purchases a **20% interest** in XYZ for **\$480,000** on Jan. 2, 2013 (48,000 shares @ \$10/share).

**Step 1: Initial Recording**

| Date | Account | Debit | Credit | Statement |
|---|---|---|---|---|
| Jan. 2, 2013 | Investment in Associate | \$480,000 | | [[Balance sheet]] |
| | Cash | | \$480,000 | [[Balance sheet]] |

*ABC handed over cash and received an investment asset. No P&L impact.*

**Step 2: XYZ reports NI = \$200,000 for 2013**

ABC's share = $20\% \times \$200{,}000 = \$40{,}000$

| Date | Account | Debit | Credit | Statement |
|---|---|---|---|---|
| Dec. 31, 2013 | Investment in Associate | \$40,000 | | [[Balance sheet]] ↑ |
| | Investment Income | | \$40,000 | [[Income statement]] ↑ |

*ABC recognizes its share of XYZ's earnings. The investment balance grows, and income is reported.*

**Step 3: Dec. 31, 2013 — FV per share = \$12.00**

→ **No entry.** Under the equity method, [[Fair value]] changes are completely ignored. Even though the market says ABC's shares are now worth \$12 × 48,000 = \$576,000, ABC keeps the investment at \$480,000 + \$40,000 = \$520,000.

**Step 4: Jan. 28, 2014 — XYZ pays total cash dividend of \$100,000**

ABC's share = $20\% \times \$100{,}000 = \$20{,}000$

| Date | Account | Debit | Credit | Statement |
|---|---|---|---|---|
| Jan. 28, 2014 | Cash | \$20,000 | | [[Balance sheet]] ↑ |
| | Investment in Associate | | \$20,000 | [[Balance sheet]] ↓ |

*Cash comes in, investment balance goes down. No [[Income statement]] impact. The dividend is NOT income.*

### 📝 Textbook Example: Three-Year Tracking (MarkMeldrum Notes)

> Assume a 20% interest purchased for \$200,000.

| Year | Investee NI | Investee Dividends | Investor's Share of NI | Investor's Share of Div |
|---|---|---|---|---|
| 2010 | \$200,000 | \$50,000 | \$40,000 | \$10,000 |
| 2011 | \$300,000 | \$100,000 | \$60,000 | \$20,000 |
| 2012 | \$400,000 | \$200,000 | \$80,000 | \$40,000 |

**Investment in Associate Balance:**

| | Amount | [[Income statement]] / Cash Effect |
|---|---|---|
| Initial Cost | \$200,000 | — |
| + 2010 Income share | +40,000 | IS: +\$40,000 |
| − 2010 Dividends | −10,000 | Cash: +\$10,000 |
| + 2011 Income share | +60,000 | IS: +\$60,000 |
| − 2011 Dividends | −20,000 | Cash: +\$20,000 |
| + 2012 Income share | +80,000 | IS: +\$80,000 |
| − 2012 Dividends | −40,000 | Cash: +\$40,000 |
| **Ending Balance** | **\$310,000** | |

Over three years, the investment grew from \$200k to \$310k. The investor reported \$180k of income on the [[Income statement]], but only received \$70k in actual cash (dividends). This illustrates a critical point: **equity method earnings are largely non-cash.**

## 💰 Excess Purchase Price — The Tricky Part

In practice, the purchase price almost always **exceeds** the investor's proportionate share of the investee's [[Book value]]. Why? Because many assets on the investee's [[Balance sheet]] are recorded at historical cost, which is often below [[Fair value]]. And there's [[Goodwill]] — value for things like brand reputation, customer relationships, and synergies that aren't on the [[Balance sheet]] at all.

### The Allocation Process

$$\text{Excess} = \text{Purchase Price} - (\%\text{ owned} \times BV_{\text{investee's net assets}})$$

This excess is allocated in two steps:

**Step 1: Allocate to specific identifiable assets** whose [[Fair value]] > [[Book value]]
- These amounts are **amortized** over the useful life of those assets
- The amortization reduces both the Investment in Associate (B/S) and Investment Income (I/S) each period
- Note: this allocation is NOT formally recorded on the investee's books — it's an adjustment the investor makes on its own books

**Step 2: Whatever is left = [[Goodwill]]**
- [[Goodwill]] is included in the carrying amount of the investment (not separately recognized)
- It is **NOT amortized** (because it has an indefinite life)
- Instead, the **entire equity method investment** is tested for [[Impairment]] at each [[Balance sheet]] date

### 📝 Textbook Example: Parker and Prince (CFA Institute Curriculum, Example 3)

> On Jan. 1, 2018, Parker Company acquires **30%** of Prince Inc. for **€500,000**.

**Prince's Balance Sheet:**

| | [[Book value]] | [[Fair value]] | Difference |
|---|---|---|---|
| Current Assets | €100,000 | €100,000 | €0 |
| Plant & Equipment | €1,900,000 | €2,200,000 | €300,000 |
| **Total Assets** | **€2,000,000** | **€2,300,000** | |
| Liabilities | €800,000 | €800,000 | €0 |
| **Net Assets** | **€1,200,000** | **€1,500,000** | **€300,000** |

PP&E has 10-year remaining life, straight-line [[Depreciation]].

**Step 1: Calculate the Excess**

$$\text{Purchase price} = €500{,}000$$

$$30\% \times BV = 30\% \times €1{,}200{,}000 = €360{,}000$$

$$\text{Excess purchase price} = €500{,}000 - €360{,}000 = €140{,}000$$

**Step 2: Allocate to Identifiable Assets**

$$\text{PP\&E excess} = 30\% \times €300{,}000 = €90{,}000$$

**Step 3: Residual = [[Goodwill]]**

$$\text{[[Goodwill]]} = €140{,}000 - €90{,}000 = €50{,}000$$

**Step 4: Annual Amortization**

$$\text{PP\&E amort.} = \frac{€90{,}000}{10 \text{ years}} = €9{,}000 \text{ per year}$$

| Component | Excess (€) | Useful Life | Annual Amort. (€) |
|---|---|---|---|
| Plant & Equipment | 90,000 | 10 years | 9,000 |
| Land (if any) | — | Indefinite | 0 |
| [[Goodwill]] | 50,000 | Indefinite | 0 |
| **Total** | **140,000** | | **9,000** |

**Prince reports NI = €100,000 and pays Dividends = €50,000 in 2018.**

**Investment in Prince, year-end 2018:**

| | Amount |
|---|---|
| Purchase price | €500,000 |
| + Parker's share of NI ($30\% \times €100{,}000$) | +30,000 |
| − Dividends received ($30\% \times €50{,}000$) | −15,000 |
| − Amortization of excess ($€90{,}000 \div 10$) | −9,000 |
| **Ending balance** | **€506,000** |

> [!tip] **Alternative Verification**
> The textbook shows you can verify this balance:
> $$\text{Parker's share of Prince's net equity} = 30\% \times (€1{,}200{,}000 + €100{,}000 - €50{,}000) = 30\% \times €1{,}250{,}000 = €375{,}000$$
> $$+ \text{Unamortized excess} = €140{,}000 - €9{,}000 = €131{,}000$$
> $$= €375{,}000 + €131{,}000 = €506{,}000 ✓$$

## 🔄 Transactions with Associates — Unrealized Profit Elimination

This is one of the trickiest exam topics. When the investor and the associate trade with each other, any **unrealized profit** from those intercompany transactions must be eliminated until the goods are sold to an outside third party or consumed.

### Upstream vs. Downstream

| Direction | Flow | Profit Originally Recorded On |
|---|---|---|
| **Upstream** | Associate → Investor | Associate's P&L |
| **Downstream** | Investor → Associate | Investor's P&L |

In either case, the investor must **remove its proportionate share of unrealized profit** from its Investment Income.

> [!example] **Real-World Analogy**
> Imagine you own 25% of a furniture factory (the associate). The factory sells you \$100,000 worth of furniture at a 40% markup. At year-end, you haven't resold \$25,000 worth of that furniture. The factory booked a "profit" on selling to you, but that profit isn't *real* yet because the goods are still sitting in your warehouse. You need to strip out your share of that phantom profit.

### 📝 Textbook Example: Wicker and Foxworth — Upstream Sale (CFA Institute Curriculum, Example 4)

> Jan. 1, 2018: Wicker acquires **25%** of Foxworth for **€1,000,000**.
> - BV of Foxworth = €3,800,000
> - FV exceeds BV only for a building: undervalued by €40,000, 20-year remaining life
> - Foxworth's 2018 NI = €20,000; Dividends = €3,200
> - During 2018, Foxworth sold inventory to Wicker (upstream). **€8,000 profit** from this sale is included in Foxworth's NI. The inventory has NOT been resold to an outside party.

**Excess Purchase Price Allocation:**

$$\text{Purchase Price} = €1{,}000{,}000$$

$$25\% \times BV = 25\% \times €3{,}800{,}000 = €950{,}000$$

$$\text{Excess} = €50{,}000$$

$$\text{Building} = 25\% \times €40{,}000 = €10{,}000 \quad (\text{amortized over 20 years} = €500/\text{yr})$$

$$\text{[[Goodwill]]} = €50{,}000 - €10{,}000 = €40{,}000$$

**2018 Equity Income:**

| Component | Amount |
|---|---|
| Wicker's share of Foxworth NI ($25\% \times €20{,}000$) | €5,000 |
| − Amortization of building excess ($€10{,}000 \div 20$) | (€500) |
| − Unrealized profit on upstream sale ($25\% \times €8{,}000$) | (€2,000) |
| **Equity Income 2018** | **€2,500** |

**Investment Balance at Dec. 31, 2018:**

| | Amount |
|---|---|
| Purchase price | €1,000,000 |
| + Equity income | +2,500 |
| − Dividends ($25\% \times €3{,}200$) | −800 |
| **Ending balance** | **€1,001,700** |

### 📝 Textbook Example: Jones and Jason — Downstream Sale (CFA Institute Curriculum, Example 5)

> Jones owns **25%** of Jason. Annual amortization of excess = €8,000.
> In 2017, **Jones sells** €96,000 of inventory **to Jason** for €160,000 (downstream).
> Jason resells 75% (€120,000/€160,000) of this in 2017. The remaining 25% is sold in 2018.
> Jason NI: 2017 = €800,000; 2018 = €820,000.

**Jones's profit on the intercompany sale:**

$$€160{,}000 - €96{,}000 = €64{,}000 \text{ total margin}$$

**How much is unrealized?** Jason hasn't resold 25% of the goods:

$$\text{Unrealized profit} = 25\% \times €64{,}000 = €16{,}000$$

**Jones must eliminate its share (downstream = 100% of the unrealized portion attributed to Jones, but proportionate to ownership):**

$$\text{Jones's elimination} = 25\% \times €16{,}000 = €4{,}000$$

> Wait — why 25% of the unrealized profit? Because in a downstream sale, the unrealized profit sits on the **investor's** P&L. Both IFRS and US GAAP require elimination to the extent of the investor's interest. Jones owns 25%, so 25% of the \$16,000 unrealized profit is eliminated.

**2017 Equity Income:**

$$25\% \times €800{,}000 = €200{,}000$$
$$- \text{Amort.} = (€8{,}000)$$
$$- \text{Unrealized profit} = (€4{,}000)$$
$$= €188{,}000$$

**2018 Equity Income** (the 25% of inventory is now sold to a third party → profit is realized):

$$25\% \times €820{,}000 = €205{,}000$$
$$- \text{Amort.} = (€8{,}000)$$
$$+ \text{Previously unrealized profit, now realized} = €4{,}000$$
$$= €201{,}000$$

> [!tip] **Notice the Reversal**
> In 2017, the unrealized profit was **subtracted**. In 2018, when Jason sold the remaining inventory to an outside party, the same amount was **added back**. The total equity income over both years is the same as if there had been no intercompany transaction — the adjustment just shifts the timing.

## ⚖️ Fair Value Option & Impairment

### Fair Value Option

Both [[IFRS]] and [[US GAAP]] allow an alternative: instead of the equity method, the investment can be reported at [[Fair value]] with changes going through [[Net income]].

| | IFRS | US GAAP |
|---|---|---|
| **Who can elect FV option?** | **Restricted**: only venture capital firms, mutual funds, trusts, and similar entities | **All entities** |
| **Measurement** | [[Fair value]] on B/S | [[Fair value]] on B/S |
| **Unrealized G/L** | → [[Net income]] | → [[Net income]] |
| **Dividends/Interest** | → [[Net income]] | → [[Net income]] |
| **Excess over BV** | Not amortized | Not amortized |

### Impairment

- Both standards require **periodic reviews** of equity method investments for [[Impairment]]
- The **entire [[Carrying value]]** is tested (not individual components)
- If impaired → write down to **recoverable amount** → loss recognized in [[Net income]]
- Reversals: **Prohibited** under [[US GAAP]]; limited reversal allowed under [[IFRS]]

> The textbook states: "As goodwill is not reported separately it is not specifically tested for impairment. Rather, the entire equity method investment is tested for impairment at each balance sheet date." *(CFA Institute Curriculum, LM1)*

## 🔍 Issues for Analysts

The curriculum highlights several challenges:

1. **Is the equity method even appropriate?** A company with 19% might use it to avoid reporting associate losses. A company with 25% might be frozen out by a controlling shareholder.

2. **One-line consolidation hides leverage.** The "Investment in Associate" is a single line on the B/S. It could be masking huge liabilities inside the associate. Debt ratios of the investor look better than economic reality.

3. **Revenue disconnect.** Investment Income shows up in [[Net income]], but the investor's [[Revenue]] line does NOT include the associate's revenues. This makes net profit margin look artificially high.

4. **Non-cash earnings.** Equity method income is largely non-cash. The investor only receives cash when the associate pays dividends. A company could report growing equity income while receiving minimal cash.

---

# Part 4: Business Combinations (Control, > 50%)

## 👑 The Concept: You Run the Show

When an investor obtains **control** — typically through owning more than 50% of voting rights — the accounting shifts dramatically. The investor (now called the **parent**) must prepare **consolidated financial statements** that combine the financial statements of the parent and all its subsidiaries as if they were a **single economic entity**.

> [!example] **Real-World Analogy**
> Think of a parent company as the head of a family. Each subsidiary is a family member with their own bank accounts, jobs, and expenses. When the family prepares a "consolidated household budget," they add up ALL income and ALL expenses across all family members — but they eliminate any transactions between family members (like when Mom pays Son for mowing the lawn — that's not "real" income to the family as a whole). That's consolidation.

### Types of Business Combinations (US GAAP Distinction)

The textbook (CFA Institute Curriculum, Exhibit 5) distinguishes:

| Type | Formula | What Happens |
|---|---|---|
| **Merger** | $A + B = A$ | B ceases to exist. A absorbs B's net assets. |
| **Acquisition** | $A + B = (A + B)$ | Both continue as legal entities. Parent–subsidiary relationship. Parent does NOT need 100%. |
| **Consolidation** | $A + B = C$ | Both A and B cease to exist. A new entity C is formed. |

> Under [[IFRS]], there is **no distinction** — all are simply "business combinations."

### Historical Evolution

This is testable context:

| Period | Treatment |
|---|---|
| Pre-June 2001 | Both pooling of interests ($BV_A + BV_B$) and purchase method ($BV_A + FV_B$) were allowed |
| Post-June 2001 | US GAAP: Purchase method only. IFRS: Still allowed both |
| Post-March 2004 | Both IFRS and US GAAP: Purchase method only |
| Post-Jan 2013 | Both IFRS and US GAAP: **[[Acquisition method]]** (replaces purchase method, largely similar but with refinements) |

## 📐 The Acquisition Method — Three Core Issues

> [!important] Both [[IFRS]] and [[US GAAP]] **require** the [[Acquisition method]] for all business combinations.

The purchase price ("consideration given") — including both **clear** and **contingent** consideration — represents the [[Fair value]] of the acquisition.

### <span style="color:#c0392b">Issue ①: Recognition and Measurement of Identifiable Assets & Liabilities</span>

**A) Identifiable Tangible and [[Intangible assets]] & Liabilities:**
- All must be measured at **[[Fair value]]** as of the acquisition date
- This includes assets and liabilities **not previously recognized** by the acquiree — such as internally generated brands, patents, and customer lists that were never on the acquiree's books
- Financial assets of the acquiree are reclassified into the **acquirer's business model** (FVPL, FVOCI, or amortised cost)

**B) Contingent Liabilities:**

| | IFRS | US GAAP |
|---|---|---|
| **Recognition criteria** | Present obligation from past events **AND** can be measured reliably | Divides into contractual vs. non-contractual. Contractual: at FV. Non-contractual: if "more likely than not" meets definition |
| **Expected future costs** | NOT included (e.g., restructuring costs the acquirer plans) | Same |

**C) Indemnification Assets:**
The seller sometimes guarantees the buyer against specific contingencies. If the buyer recognizes a contingent liability of \$20M and the seller indemnifies costs above \$15M, the buyer also records a **\$5M indemnification asset**.

### <span style="color:#c0392b">Issue ②: Goodwill — Partial vs. Full</span>

[[Goodwill]] is the premium paid above the [[Fair value]] of identifiable net assets. It represents things like brand reputation, skilled workforce, expected synergies, and strategic value that can't be separately identified and put on a [[Balance sheet]].

[[Goodwill]] is **never amortized** (it has an indefinite life). It is **tested for [[Impairment]] at least annually**.

There are two methods to calculate [[Goodwill]]:

#### Partial Goodwill (IFRS only)

$$\boxed{GW_{\text{partial}} = \text{FV of consideration (price paid)} - (\% \text{ acquired} \times FV_{\text{net identifiable assets}})}$$

This method recognizes only the **acquirer's share** of goodwill.

#### Full Goodwill (US GAAP mandatory; IFRS optional)

$$\boxed{GW_{\text{full}} = FV_{\text{entity as a whole}} - FV_{\text{net identifiable assets}}}$$

$$\text{where } FV_{\text{entity}} = \frac{\text{Price Paid}}{\%\text{ acquired}}$$

This method recognizes goodwill for **the entire entity**, including the minority's share.

#### 📝 Textbook Example (CFA Institute Curriculum & MarkMeldrum Notes)

> Acquirer pays **€800,000 for 80%** of the target. $FV_{\text{net identifiable assets}} = €900{,}000$.

$$FV_{\text{entity}} = \frac{€800{,}000}{0.80} = €1{,}000{,}000$$

| | Partial Goodwill | Full Goodwill |
|---|---|---|
| Numerator | FV of consideration = €800,000 | $FV_{\text{entity}}$ = €1,000,000 |
| Less | $80\% \times €900{,}000 = €720{,}000$ | $€900{,}000$ |
| **[[Goodwill]]** | **€80,000** | **€100,000** |

> [!note] **Bargain Purchase**
> If the purchase price is *less than* the proportionate FV of net identifiable assets, the difference is a **gain** recognized immediately on the [[Income statement]]. The textbook calls this a "bargain acquisition." In practice, this is rare and usually triggers a reassessment of whether all assets and liabilities were properly valued.

### <span style="color:#c0392b">Issue ③: Non-Controlling Interest (NCI)</span>

When the parent acquires less than 100% (but > 50%), the remaining equity belongs to **non-controlling (minority) shareholders**. NCI is presented as a **separate component of shareholders' equity** on the consolidated [[Balance sheet]].

| Method | NCI Calculation |
|---|---|
| **Full Goodwill** | $NCI = \%_{\text{minority}} \times FV_{\text{entity}}$ |
| **Partial Goodwill** (IFRS only) | $NCI = \%_{\text{minority}} \times FV_{\text{net identifiable assets}}$ |

#### 📝 Textbook Example (CFA Institute Curriculum)

> Parent acquires **90%** of Subsidiary for **€180,000**. $FMV_{\text{entity}} = €200{,}000$. $FV_{\text{net identifiable assets}} = €160{,}000$.

**Goodwill:**

$$\text{Partial: } €180{,}000 - (90\% \times €160{,}000) = €180{,}000 - €144{,}000 = €36{,}000$$

$$\text{Full: } €200{,}000 - €160{,}000 = €40{,}000$$

**NCI:**

$$\text{Partial: } 10\% \times €160{,}000 = €16{,}000$$

$$\text{Full: } 10\% \times €200{,}000 = €20{,}000$$

**Consolidated Balance Sheet at Acquisition Date:**

| Item (€000) | Full Goodwill | Partial Goodwill |
|---|---|---|
| Cash and receivables | 55 | 55 |
| Inventory | 205 | 205 |
| PP&E (net) | 390 | 390 |
| **[[Goodwill]]** | **40** | **36** |
| **Total Assets** | **690** | **686** |
| Payables | 75 | 75 |
| Long-term debt | 190 | 190 |
| **Total Liabilities** | **265** | **265** |
| **NCI** | **20** | **16** |
| Capital stock | 267 | 267 |
| [[Retained Earnings]] | 138 | 138 |
| **Total Equity** | **425** | **421** |
| **Total L&E** | **690** | **686** |

## 📊 The Consolidation Process

The consolidated statements combine the parent and subsidiary **as if they were one entity**:

1. **Add together** all assets, liabilities, revenues, and expenses of both entities
2. **Eliminate all intercompany transactions** — to avoid double-counting and premature [[Revenue]] recognition
3. **Allocate the subsidiary's NI** between the parent's shareholders and NCI

> [!example] **Why Eliminate Intercompany Transactions?**
> Imagine Parent sells \$1M of goods to Subsidiary. If we don't eliminate this, the consolidated entity would show \$1M of revenue that was essentially "selling to yourself." No real economic value was created — the goods just moved from one pocket to another. The elimination ensures the consolidated financials only reflect transactions with **outside parties**.

### Impact on Ratios — Full vs. Partial Goodwill

Using the 90% acquisition example from the textbook:

| Ratio | Full Goodwill | Partial Goodwill | Why Different? |
|---|---|---|---|
| **ROA** | $\frac{57.15}{690} = 8.28\%$ | $\frac{57.15}{686} = 8.33\%$ | Full GW → higher assets → lower ROA |
| **ROE** | $\frac{57.15}{425} = 13.45\%$ | $\frac{57.15}{421} = 13.57\%$ | Full GW → higher equity (via NCI) → lower ROE |

> [!tip] **The Key Insight**
> Full goodwill **inflates** both total assets and total equity (through larger NCI), which **depresses** return ratios. The income statement is **identical** regardless of which goodwill method is used — the only differences are on the [[Balance sheet]].

## 💥 Goodwill Impairment

[[Goodwill]] must be tested **annually** for [[Impairment]]. If impaired, it is written down and the loss is reported as a **separate line item** on the consolidated [[Income statement]]. The write-down is **never reversible** under either standard.

### IFRS Approach (One-Step)

1. Allocate total [[Goodwill]] to **cash-generating units** (CGUs) that benefit from synergies
2. Compare **recoverable amount** (higher of: value in use, or FV less costs to sell) with **[[Carrying value]]** of each CGU
3. If recoverable amount < [[Carrying value]]:
   - Impairment loss first applied to **[[Goodwill]]**
   - Once GW = 0, remaining loss allocated to **other assets pro-rata**

### US GAAP Approach (Two-Step)

1. Allocate [[Goodwill]] to **reporting units**
2. **Step 1**: Compare $FV_{\text{unit}}$ with [[Carrying value]] of the whole reporting unit
   - If $FV_{\text{unit}} \geq$ [[Carrying value]] → no impairment
3. **Step 2** (if Step 1 fails): Calculate **implied [[Goodwill]]** = $FV_{\text{unit}} - FV_{\text{net assets of unit}}$
   - Impairment loss = Current GW − Implied GW
   - Applied to the unit until GW = 0; **no allocation to other assets**

### 📝 Textbook Example: Goodwill Impairment (MarkMeldrum Notes)

> CGU/Reporting Unit: [[Carrying value]] = \$1.4M (includes \$300k [[Goodwill]]). $FV_{\text{net assets}} = \$1.2M$.

**Scenario A: Recoverable/FV = \$1.3M**

| | IFRS | US GAAP |
|---|---|---|
| Recoverable/FV | \$1.3M | \$1.3M |
| [[Carrying value]] | \$1.4M | \$1.4M |
| Total loss | \$100k | — |
| Applied to GW | \$100k → GW goes from \$300k to \$200k | Implied GW = \$1.3M − \$1.2M = \$100k. Loss = \$300k − \$100k = **\$200k** |
| Other assets | \$0 | \$0 (GAAP never allocates beyond GW) |

> [!warning] **Different Results!**
> In Scenario A, IFRS writes off \$100k but US GAAP writes off \$200k. This is because IFRS compares recoverable amount to carrying value directly (one-step), while US GAAP calculates an "implied goodwill" and compares it to actual goodwill (two-step).

**Scenario B: Recoverable/FV = \$800k**

| | IFRS | US GAAP |
|---|---|---|
| Total impairment | \$1.4M − \$800k = \$600k | — |
| GW write-down | \$300k (all GW eliminated) | Implied GW = \$800k − \$1.2M = negative → \$0. Loss = \$300k − \$0 = **\$300k** |
| Remaining to other assets | \$300k → pro-rata to other assets | **\$0** (US GAAP stops at GW) |

> Under IFRS, the \$300k excess loss after eliminating goodwill gets spread across the other assets. Under US GAAP, once goodwill hits zero, that's it — no further write-downs from the goodwill impairment test.

---

# Part 5: Special Purpose Entities (SPE) / Variable Interest Entities (VIE)

## 🏗️ The Concept: Control Without Voting

A **[[Special purpose entity]]** (SPE) — or **Variable Interest Entity** (VIE) under [[US GAAP]] — is a legal entity created by a **sponsor company** for a narrow, specific purpose. The sponsor often retains the economic risks and rewards even though it may have little or no **voting control**.

> [!example] **Real-World Analogy: The Shell Company**
> Imagine a manufacturer that wants to build a new factory but doesn't want the debt on its books. It creates a separate LLC (the SPE), gets a bank to lend to that LLC, and the LLC builds the factory. The manufacturer then leases the factory from the LLC. On paper, the manufacturer doesn't "own" the factory and doesn't owe the debt. But economically? It bears all the risk — if the factory fails, the manufacturer can't just walk away because it guarantees the LLC's debt. 
>
> Before modern accounting rules, companies like **Enron** exploited this structure to hide billions in debt off their [[Balance sheet]]. The post-Enron accounting reforms were designed to prevent exactly this.

### Typical SPE Structure

```
   ┌──────────────┐          ┌──────────────┐         ┌──────────┐
   │   SPONSOR    │          │     SPE      │◄────────│   DEBT   │
   │   COMPANY    │◄─ lease ─│              │ borrows │  MARKET  │
   │              │─ cash ──▶│  (minimal    │─────────▶          │
   │ • transfers  │  lease   │   3rd-party  │         └──────────┘
   │   assets     │  pymts   │   equity)    │
   │ • retains    │          │              │
   │   risk of    │          │  Builds or   │
   │   default    │          │  acquires    │
   │ • retains    │          │  assets at   │
   │   beneficial │          │  lower r_d   │
   │   interest   │          └──────────────┘
   └──────────────┘
```

**The end result**: The sponsor's [[Balance sheet]] looks the **same** whether it borrowed directly to buy the asset or used the SPE structure. The SPE was just a financial engineering vehicle. The textbook (MarkMeldrum notes) emphasizes: once consolidated, the economic reality is identical.

### When Must the Sponsor Consolidate?

**IFRS (IFRS 10):**
- The definition of **control** now encompasses SPEs
- Control = ability to direct relevant activities + exposure to variable returns
- If the sponsor has control → **must consolidate**

**US GAAP (FASB ASC 810):**
- Uses the **VIE** framework. An SPE is a VIE when:
  1. ① Total **equity at risk is insufficient** to finance activities without additional support
  2. ② Equity investors **lack**:
     - The ability to make decisions
     - The obligation to absorb expected losses
     - The right to receive expected residual returns
- The **primary beneficiary** (the party absorbing the majority of expected losses or receiving the majority of expected residual returns) must **consolidate** the VIE

> [!tip] **Exam Tip**
> The curriculum note (Schweser/MarkMeldrum) makes an important point: *"In a VIE, the capital source labeled as stockholders' equity is not truly equity, as the amount is insufficient to have the risk/return characteristics of equity."* The "equity" in a VIE is often just a thin sliver designed to meet legal requirements — the real risk-bearing capital is the variable interest held by the sponsor.

### 📝 Textbook Example: SPE Consolidation (Schweser Notes)

> Company P wants to borrow \$100M. It can either:
> - **Option A**: Borrow directly → Cash ↑ \$100M, Debt ↑ \$100M
> - **Option B**: Create SPE, sell \$100M of accounts receivable to SPE, SPE borrows \$100M from bank

**Before [[Consolidation|consolidation]] (Option B):** Company P's B/S shows A/R ↓ \$100M, Cash ↑ \$100M — looks like a sale, no new debt!

**After [[Consolidation|consolidation]]:** SPE's debt gets added back. A/R goes back up. The [[Balance sheet|balance sheet]] looks **identical to Option A**.

> The lesson: SPE consolidation rules exist specifically to prevent companies from hiding [[Liabilities|liabilities]] off the [[Balance sheet]].

---

# Part 6: Impact on Financial Statements and Ratios (LOS 7.c)

## 📊 Equity Method vs. Acquisition Method — Side by Side

This is where everything comes together. The CFA curriculum expects you to trace the effects of each method through every financial statement and ratio.

| Metric | Equity Method | [[Acquisition|Acquisition]] (Consolidation) |
|---|---|---|
| **[[Revenue]]** | ❌ Not included (only "Equity Income" line) | ✅ 100% of subsidiary's revenues included |
| **Expenses** | ❌ Not included | ✅ 100% of subsidiary's expenses included |
| **[[Net income]] (to parent)** | ✅ **Same** | ✅ **Same** |
| **Total Assets** | **Lower** (single-line "Investment in Associate") | **Higher** (all sub's assets + [[Goodwill]]) |
| **Total [[Liabilities|Liabilities]]** | **Lower** | **Higher** (all sub's [[Liabilities|liabilities]] added) |
| **Equity (excl. NCI)** | **Same** | **Same** |
| **[[Net profit margin|Net Profit Margin]]in|Profit Margin]]** | **Higher** (same NI ÷ lower revenue) | **Lower** (same NI ÷ much higher revenue) |
| **ROA** | **Higher** (same NI ÷ lower assets) | **Lower** (same NI ÷ much higher assets) |
| **ROE (excl. NCI)** | **Same** | **Same** |
| **Leverage (D/E)** | **Lower** | **Higher** (sub's debt gets added) |
| **[[Current ratio|Current ratio]]** | Different | Different (sub's current A&L added) |

> [!warning] **The Critical Insight**
> **[[Net income]] to the parent is the SAME** under both methods. The equity method picks up the investor's share of NI as a single line item. Consolidation picks up 100% of revenues and expenses then subtracts the NCI's share. The result for the parent's shareholders is identical.
>
> But everything else differs — assets, liabilities, revenues, expenses, and therefore most ratios.

> [!example] **Why This Matters in Practice**
> Suppose Company A has a 40% stake in Company B. Under the equity method, Company A's [[Balance sheet]] might show a clean, low-leverage structure. But if you mentally "consolidated" Company B (even though it's not required at 40%), you'd see that Company B has massive debt. An analyst who only looks at Company A's reported numbers might dramatically underestimate the economic leverage.
>
> This is why the curriculum says analysts should be skeptical of equity method accounting and consider the associate's own financial statements.

---

# Part 7: Master Formula Sheet

## 📐 Equity Method Formulas

### Investment Balance

$$\boxed{\text{Inv. in Assoc.} = \text{Cost} + \Sigma(\% \times NI) - \Sigma(\% \times \text{Div}) - \Sigma(\text{Amort. of Excess}) \pm \text{Unrealized Profit Adj.}}$$

### Equity Income (for any given period)

$$\boxed{\text{Equity Income} = (\% \times NI) - \text{Amort. of Excess} - \text{Current Unrealized Profit} + \text{Prior Unrealized Profit Now Realized}}$$

### Excess Purchase Price

$$\boxed{\text{Excess} = \text{Purchase Price} - (\% \times BV_{\text{investee's net assets}})}$$

### Allocation of Excess

$$\text{To specific assets} = \% \times (FV_{\text{asset}} - BV_{\text{asset}})$$

$$\text{Annual amort. per asset} = \frac{\text{Allocated amount}}{\text{Remaining useful life}}$$

$$\text{[[Goodwill]]} = \text{Total Excess} - \text{Amount allocated to specific assets}$$

## 📐 Acquisition Method Formulas

### Goodwill — Partial (IFRS only)

$$\boxed{GW_{\text{partial}} = \text{Price Paid} - (\%_{\text{acquired}} \times FV_{\text{net identifiable assets}})}$$

### Goodwill — Full (GAAP mandatory, IFRS optional)

$$\boxed{GW_{\text{full}} = FV_{\text{entity}} - FV_{\text{net identifiable assets}}}$$

$$\text{where } FV_{\text{entity}} = \frac{\text{Price Paid}}{\%_{\text{acquired}}}$$

### Non-Controlling Interest

$$\boxed{NCI_{\text{full}} = \%_{\text{minority}} \times FV_{\text{entity}}}$$

$$\boxed{NCI_{\text{partial}} = \%_{\text{minority}} \times FV_{\text{net identifiable assets}}}$$

### Goodwill Impairment — IFRS

$$\boxed{\text{Impairment} = \text{Carrying Value of CGU} - \text{Recoverable Amount of CGU}}$$

*Loss first to GW, then pro-rata to other assets.*

### Goodwill Impairment — US GAAP

$$\boxed{\text{Implied GW} = FV_{\text{reporting unit}} - FV_{\text{net assets of unit}}}$$

$$\boxed{\text{Impairment Loss} = \text{Current GW} - \text{Implied GW}}$$

*No allocation beyond GW.*

---

# Part 8: IFRS vs. US GAAP — Complete Comparison

| Topic | IFRS | US GAAP |
|---|---|---|
| **Financial Assets — Classification** | Business model + SPPI test. Three categories: Amortised cost, FVPL, FVOCI | Intent-based. HTM, Trading, AFS |
| **Financial Assets — Equity FVOCI** | Allowed (irrevocable); gains never recycled | Generally not available for equity |
| **Financial Assets — Reclassification** | Debt only, when business model changes | Generally not permitted |
| **Financial Assets — [[Impairment|Impairment]]** | Expected credit loss model | CECL model (similar concept) |
| **Associates — FV Option** | Restricted (VC, MF, trusts) | Available to all entities |
| **Associates — [[Impairment|Impairment]] Reversal** | Allowed (limited) | Prohibited |
| **Business Combinations — Structure** | No distinction (all are "business combinations") | Merger, [[Acquisition|Acquisition]], Consolidation |
| **Business Combinations — Goodwill** | Partial OR Full goodwill | Full goodwill **only** |
| **Business Combinations — NCI** | Proportionate share of FV of net assets (partial) or FV of entity (full) | FV of entity (full) only |
| **Goodwill Impairment** | One-step: compare recoverable amount to [[Carrying value|carrying value]]; excess loss goes to other assets pro-rata | Two-step: implied GW test; loss stops at GW = 0 |
| **Contingent Liabilities** | Present obligation + reliably measurable | Contractual: at FV. Non-contractual: "more likely than not" |
| **SPE/VIE** | Control-based (IFRS 10) — encompasses SPEs | VIE framework (ASC 810) — primary beneficiary consolidates |

---

> [!abstract] **Final Exam Strategy**
> 1. **Know the journal entries cold.** Be able to write the debit/credit for initial recording, NI recognition, dividend receipt, and amortization of excess under the equity method.
> 2. **Master the goodwill calculations.** Full vs. partial, and how each affects NCI, total assets, and ratios.
> 3. **Intercompany profit elimination** (upstream vs. [[Downstream|downstream]]) is a guaranteed exam topic. Practice the timing of when profits are deferred and when they're reversed.
> 4. **Ratio analysis** — be able to explain *why* the equity method shows higher margins and ROA than consolidation, even though NI to the parent is the same.
> 5. **SPE/VIE** — focus on *when* consolidation is required (primary beneficiary test for GAAP, control test for IFRS).
> 6. **IFRS vs. GAAP differences** — especially goodwill impairment (one-step vs. two-step) and partial vs. full goodwill.
