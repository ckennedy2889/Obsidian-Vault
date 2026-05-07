# Multinational Operations

> [!info] Module Overview
> This module covers how companies with international operations handle two key accounting challenges: (1) **[[Foreign currency|foreign currency]]cy transactions|[[Foreign currency|foreign currency]] transactions]]** — buying/selling goods in [[Currencies|currencies]] other than their own, and (2) **translating foreign subsidiary financial statements** — converting a subsidiary's books into the parent's reporting currency for [[Consolidation]]. Understanding these mechanics is critical for analyzing any company with global operations — which is most large companies today.
>
> **CFA Institute Curriculum Reference:** Level II, Volume 3, Learning Module 3
> **Mark Meldrum Notes:** Pages 40–59

---

## 1. Currency Terminology (LOS a)

> [!tip] The Real-World Setup
> Imagine you're Nestlé, headquartered in Switzerland. You have factories in Brazil, sales offices in Japan, and a subsidiary in the United States. Each of these locations uses a different currency day-to-day. But your investors in Zurich want to see everything in Swiss francs. How do you reconcile all of this? That's what this entire module answers.

### Three Currencies You Must Distinguish

**[[Local currency]]** — The national currency of the country where the entity is physically located. A Toyota factory in Kentucky operates in USD; that's the [[Local currency|local currency]] for that operation, even though Toyota's headquarters uses JPY.

**[[Functional currency]]** — The currency of the **primary economic environment** in which the entity operates. This is the currency in which the entity primarily generates and spends cash. Management determines this based on several factors (see below). Usually the [[Functional currency|functional currency]] equals the [[Local currency|local currency]] — but not always.

**[[Presentation currency]]** (Reporting Currency) — The currency in which the parent company prepares its [[consolidated financial statements]]. For a US-based parent, this is USD. For a German parent, EUR.

> [!example] Real-World Example: Exxon Mobil vs. Chevron
> Both are US oil companies ([[Presentation currency|presentation currency]] = USD), but they make **different [[Functional currency|functional currency]] choices** for their foreign subsidiaries:
> - **Exxon Mobil**: Uses local [[Currencies|currencies]] for many [[Downstream|downstream]]/chemical operations (e.g., GBP for UK operations, NOK for Norway) but uses USD for subsidiaries in high-[[Inflation|inflation]] countries and those selling into USD-denominated export markets.
> - **Chevron**: Designates USD as the [[Functional currency|functional currency]] for **substantially all** overseas operations.
>
> This single judgment call changes which translation method applies, which in turn changes reported [[Net income]], [[total assets]], and key [[financial ratios]]. Same industry, same economics, different accounting outcomes.

### Factors for Determining Functional Currency

Management considers these factors (per [[IAS 21]] / [[ASC 830]]):

| Factor | Points Toward [[Local currency|Local Currency]] | Points Toward Parent's Currency |
|--------|------------------------------|-------------------------------|
| Sales prices | Primarily influenced by local supply/demand | Primarily influenced by parent's currency or world markets |
| Markets | Sales mainly in local market | Sales mainly in parent's country or denominated in parent's currency |
| Expenses | Labor, materials sourced locally | Major inputs sourced from parent's country |
| Financing | Funded locally | Funded by parent |
| Cash flows | Operating cash retained locally | Cash flows remitted to parent regularly |

> [!warning] Exam Alert
> When factors give mixed signals, management uses **judgment**. This subjectivity means two identical companies can choose different functional [[Currencies|currencies]] — creating a comparability problem for analysts. The [[Functional currency|functional currency]] choice is the **single most important decision** in this module because it determines everything [[Downstream|downstream]]: which translation method is used, where translation gains/losses are reported, and how ratios are affected.

### The Decision Flowchart

```
Local Currency Financial Statements
            │
            ▼
   What is the Functional Currency?
            │
     ┌──────┴──────┐
     │             │
     ▼             ▼
 Foreign         Parent's
 Currency        Currency
 (≠ Parent's)   (= Parent's)
     │             │
     ▼             ▼
 CURRENT RATE   TEMPORAL
   METHOD        METHOD
     │             │
     ▼             ▼
 Translation    Remeasurement
 adjustment     gain/loss
 → OCI/Equity   → Income Statement
```

---

## 2. Foreign Currency Transaction Exposure (LOS b)

> [!tip] The Intuition
> Think of foreign currency transactions like placing a bet on exchange rates. When a US company sells goods to a French customer for €100,000 payable in 60 days, the US company is essentially saying: "I'll accept whatever €100,000 is worth in USD two months from now." That gap between the transaction date and the payment date is where the risk lives.

### What Creates Transaction Exposure?

A **[[foreign currency transaction]]** occurs when a company enters into a transaction denominated in a currency other than its [[Functional currency]]. Two common situations:

1. **Export sale / Import purchase** denominated in a foreign currency
2. **Borrowing or lending** where repayment is in a foreign currency

> [!important] Key Principle
> The transaction creates a [[Foreign currency]] [[asset]] (receivable) or [[liability]] (payable) on the company's books. As exchange rates change between the transaction date and settlement date, the functional currency value of that asset or liability changes — creating gains or losses.

### Accounting Treatment: Settlement Before Balance Sheet Date

> [!example] FinnCo Imports from Mexico (CFA Curriculum Example)
> **Setup:** FinnCo (functional currency = EUR) buys inventory from Mexico for MXN 100,000 on November 1. Payment due December 15.
>
> | Date | MXN/EUR Rate | EUR Value of MXN 100,000 |
> |------|-------------|------------------------|
> | Nov 1 (transaction) | 0.0684 | €6,840 |
> | Dec 15 (settlement) | 0.0703 | €7,030 |
>
> **What happens:**
> - Nov 1: Record inventory at €6,840, AP at €6,840
> - Dec 15: Pay €7,030 for MXN 100,000 (peso strengthened!)
> - **Foreign exchange loss = €190** (realized, reported on [[Income statement]])
> - Inventory stays at €6,840 (cost is locked at transaction date)
> - Cash outflow = €7,030
>
> **The intuition:** FinnCo could have paid €6,840 on day one. By waiting 45 days, the peso got more expensive, costing an extra €190.

### Accounting Treatment: Balance Sheet Date Falls Between Transaction and Settlement

This is the more common exam scenario and involves **unrealized** gains/losses.

> [!example] FinnCo Exports to UK (CFA Curriculum Example)
> **Setup:** FinnCo sells goods to a UK customer for £10,000 on November 15, 20X1. Payment due January 15, 20X2. FinnCo's fiscal year ends December 31.
>
> | Date | £/EUR Rate | EUR Value of £10,000 | Change |
> |------|-----------|---------------------|--------|
> | Nov 15, 20X1 | 1.460 | €14,600 | — |
> | Dec 31, 20X1 | 1.480 | €14,800 | +€200 |
> | Jan 15, 20X2 | 1.475 | €14,750 | −€50 |
>
> **Accounting entries:**
> - **20X1:** Unrealized FX gain of €200 recognized in income (pound strengthened → AR worth more)
> - **20X2:** FX loss of €50 recognized in income (pound weakened slightly)
> - **Net realized gain over full period:** €150 = €14,750 − €14,600 ✓
>
> **Key insight for analysts:** The €200 gain in 20X1 was **unrealized** — the pound could have reversed course. This is one of the rare situations where accounting standards require recognizing an unrealized gain in [[Net income]].

### Quick Reference: Direction of FX Transaction Gains/Losses

| | Foreign Currency **Strengthens** | Foreign Currency **Weakens** |
|---|---|---|
| **Asset exposure** (AR in foreign currency) | **Gain** — your receivable buys more functional currency | **Loss** — your receivable buys less functional currency |
| **Liability exposure** (AP in foreign currency) | **Loss** — your payable costs more functional currency | **Gain** — your payable costs less functional currency |

> [!warning] Analyst Considerations
> - Neither [[IFRS]] nor [[US GAAP]] specifies **where** on the [[Income statement]] FX transaction gains/losses must appear — could be operating or non-operating income
> - If Company A reports FX gains in operating income and Company B reports them below the line, **[[operating margin]] is not directly comparable**
> - These gains/losses are reported on a **gross basis** only if material; otherwise they may be netted
> - Companies often use [[forward contracts]], [[options]], or other [[Level 2/08 - Derivatives/Derivatives]] to [[hedge]] transaction exposure

---

## 3. Exchange Rates and Translated Sales (LOS c)

> [!tip] The Intuition
> When BMW translates its US subsidiary's USD sales into EUR, the translated amount depends on two things: (1) how many cars were sold and at what price (real business performance), and (2) what the USD/EUR exchange rate was during the year. A weak dollar makes US sales look smaller in EUR terms, even if the US business is booming.

### How Exchange Rate Changes Affect Translated Sales

For a subsidiary with **foreign currency as its functional currency** (current rate method), revenues are translated at the **[[average exchange rate]]** for the period.

$$\text{Translated Sales (Parent Currency)} = \text{Sales (Foreign Currency)} \times \text{Average Exchange Rate}$$

If the foreign currency **strengthens** → translated sales **increase**
If the foreign currency **weakens** → translated sales **decrease**

> [!example] Real-World: Yahoo! Asia-Pacific Segment
> Yahoo! reported that 19.0% of its total revenue came from Asia-Pacific. However, if exchange rates had remained unchanged, that figure would have been only 17.9%. The difference? Foreign currencies appreciated against the USD, inflating translated revenues by approximately $59 million.
>
> **Analyst takeaway:** Approximately 2 percentage points of Asia-Pacific's revenue share came from currency movements, not real business growth.

---

## 4. Current Rate Method vs. Temporal Method (LOS d)

This is the core of the module. These two methods produce **dramatically different** financial statement results.

### Current Rate Method (All-Current Method)

**When to use:** Functional currency ≠ Parent's presentation currency (i.e., the subsidiary operates relatively independently in its local economy)

**The philosophy:** Translate the subsidiary's financial statements as a whole, preserving the relationships that exist in the foreign currency statements. The subsidiary is viewed as a **self-contained entity**.

| Item | Exchange Rate Used |
|------|-------------------|
| **All assets** | [[Current exchange rate]] (BS date) |
| **All liabilities** | Current exchange rate (BS date) |
| **Common stock, APIC** | [[Historical exchange rate]] (date issued) |
| **[[Retained earnings]]** | Calculated (rolled forward) |
| **Revenues** | [[Average exchange rate]] for the period |
| **All expenses** (including [[COGS]], [[Depreciation]]) | Average exchange rate |
| **[[Dividends]]** | Historical rate (date declared) |
| **Translation adjustment** | Plug to balance → **[[Other comprehensive income]]** (equity) |

> [!important] Balance Sheet Exposure: **Net Assets** (Assets − Liabilities)
> Since all assets and all liabilities are translated at the current rate, the **entire equity position** (net assets) is exposed to exchange rate changes. Since most companies have positive equity (assets > liabilities), most subsidiaries have a **net asset exposure** under this method.

### Temporal Method (Remeasurement)

**When to use:** Functional currency = Parent's presentation currency (i.e., the subsidiary is essentially an extension of the parent)

**The philosophy:** Translate as if the subsidiary had originally recorded its transactions in the parent's currency. Preserves the **measurement basis** (historical cost vs. current value) after translation.

| Item | Exchange Rate Used |
|------|-------------------|
| **Monetary assets** (cash, receivables) | Current exchange rate |
| **Non-monetary assets at historical cost** (inventory at cost, [[PPE]], [[Intangible assets]]) | Historical exchange rate |
| **Non-monetary assets at current value** (inventory at [[NRV]], [[Fair value]] items) | Current exchange rate |
| **All liabilities** (mostly monetary) | Current exchange rate |
| **Common stock, APIC** | Historical exchange rate |
| **Retained earnings** | Calculated (rolled forward) |
| **Revenues** | Average exchange rate |
| **Most expenses** | Average exchange rate |
| **[[COGS]]** | Historical rate (matching inventory) |
| **[[Depreciation]]** | Historical rate (matching fixed asset) |
| **Remeasurement gain/loss** | Plug to balance → **[[Income statement]]** |

> [!important] Balance Sheet Exposure: **Net Monetary Assets/Liabilities**
> Only items translated at the current rate are "exposed." Under the temporal method, this means monetary assets and monetary liabilities. Since most companies have more monetary liabilities (AP, debt) than monetary assets (cash, AR), most subsidiaries have a **net monetary liability exposure** under this method.

### Side-by-Side Comparison

| Feature | Current Rate Method | Temporal Method |
|---------|-------------------|-----------------|
| **When used** | Functional currency ≠ parent's currency | Functional currency = parent's currency |
| **Assets/Liabilities** | All at current rate | Monetary at current; non-monetary at historical |
| **Revenues** | Average rate | Average rate |
| **COGS, Depreciation** | Average rate | Historical rate |
| **Translation gain/loss** | [[CTA]] in [[shareholders' equity]] (OCI) | Gain/loss in [[Net income]] |
| **BS exposure** | Net assets | Net monetary assets/liabilities |
| **Income volatility** | Lower (gain/loss bypasses IS) | Higher (gain/loss hits IS directly) |
| **Ratio preservation** | Pure BS and IS ratios preserved | Almost all ratios distorted |

---

## 5. Translation Calculations — The Canadaco Example (LOS e)

> [!info] Setup
> Interco (parent, EUR) establishes Canadaco (subsidiary, CAD) on January 1, 20X1. The question: What does Canadaco look like in EUR on the parent's consolidated statements?
>
> **Exchange rates during 20X1:**
> - January 1: C$1 = €0.70
> - Average: C$1 = €0.75
> - December 31: C$1 = €0.80
>
> The Canadian dollar **strengthened** against the euro during the year.

### Retained Earnings — Both Methods Use the Same Logic

$$\text{Beg. R/E (PC)} + \text{NI (PC)} - \text{Dividends (PC)} = \text{End. R/E (PC)}$$

Where:
- Beginning R/E is translated by the method used to derive prior-period R/E
- NI is translated using the method's IS translation rules
- Dividends are translated at the **historical rate on the date declared**

### Current Rate Method Results (Canadaco)

| Item | C$ | Rate | € |
|------|-----|------|---|
| **Balance Sheet** | | | |
| Cash | 980,000 | 0.80 C | 784,000 |
| Accounts Receivable | 900,000 | 0.80 C | 720,000 |
| Inventory | 1,200,000 | 0.80 C | 960,000 |
| PP&E (net) | 2,700,000 | 0.80 C | 2,160,000 |
| **Total Assets** | **5,780,000** | | **4,624,000** |
| AP | 450,000 | 0.80 C | 360,000 |
| LT Notes Payable | 3,000,000 | 0.80 C | 2,400,000 |
| Capital Stock | 1,500,000 | 0.70 H | 1,050,000 |
| Retained Earnings | 830,000 | from IS | 612,000 |
| **CTA** | — | plug | **202,000** |
| **Total L + E** | **5,780,000** | | **4,624,000** |
| | | | |
| **Income Statement** | | | |
| Sales | 12,000,000 | 0.75 A | 9,000,000 |
| COGS | (9,000,000) | 0.75 A | (6,750,000) |
| Gross Profit | 3,000,000 | | 2,250,000 |
| Net Income | 1,180,000 | | 885,000 |

*C = Current rate; A = Average rate; H = Historical rate*

The **positive CTA of €202,000** arises because the CAD strengthened and the subsidiary has net assets exposed. This CTA sits in [[shareholders' equity]] — it does **not** flow through the income statement.

### Temporal Method Results (Canadaco)

| Item | C$ | Rate | € |
|------|-----|------|---|
| **Balance Sheet** | | | |
| Cash | 980,000 | 0.80 C | 784,000 |
| Accounts Receivable | 900,000 | 0.80 C | 720,000 |
| Inventory | 1,200,000 | 0.74 H | 888,000 |
| PP&E (net) | 2,700,000 | 0.70 H | 1,890,000 |
| **Total Assets** | **5,780,000** | | **4,282,000** |
| AP | 450,000 | 0.80 C | 360,000 |
| LT Notes Payable | 3,000,000 | 0.80 C | 2,400,000 |
| Capital Stock | 1,500,000 | 0.70 H | 1,050,000 |
| Retained Earnings | 830,000 | plug | 472,000 |
| **Total L + E** | **5,780,000** | | **4,282,000** |
| | | | |
| **Income Statement** | | | |
| Sales | 12,000,000 | 0.75 A | 9,000,000 |
| COGS | (9,000,000) | 0.74 H | (6,660,000) |
| Depreciation | (300,000) | 0.70 H | (210,000) |
| Other Expenses | (1,520,000) | 0.75 A | (1,140,000) |
| Income before transl. | 1,180,000 | | 990,000 |
| **Translation loss** | — | plug | **(245,000)** |
| **Net Income** | **1,180,000** | | **745,000** |

The **translation loss of €245,000** hits the income statement directly because Canadaco has a net monetary liability exposure (monetary liabilities of C$3,450,000 > monetary assets of C$1,880,000) and the CAD **strengthened** — meaning those liabilities cost more in EUR terms.

### Comparing the Two Methods

| Metric | Current Rate (€) | Temporal (€) | Difference |
|--------|-----------------|--------------|------------|
| Sales | 9,000,000 | 9,000,000 | 0% |
| Net Income | 885,000 | 745,000 | +18.8% |
| Total Assets | 4,624,000 | 4,282,000 | +8.0% |
| Total Equity | 1,864,000 | 1,522,000 | +22.5% |

> [!warning] Why the Differences Matter
> The **same subsidiary** with the **same economic reality** produces dramatically different consolidated results depending on which method is used. This is entirely driven by management's choice of functional currency — a subjective judgment. Analysts comparing Exxon Mobil (local functional currencies) to Chevron (USD functional currency) must adjust for these differences to make meaningful comparisons.

---

## 6. Effect of Currency Movements on Financial Statements (LOS e, continued)

The table below is one of the **highest-yield exhibits** for the exam. It summarizes how exchange rate changes affect translated financial statements under each method.

### Master Reference Table: Currency Movement Effects

| Scenario | Temporal (Net Monetary **Liability** Exposure) | Temporal (Net Monetary **Asset** Exposure) | Current Rate Method |
|----------|----------------------------------------------|------------------------------------------|-------------------|
| **Foreign currency STRENGTHENS** | ↑ Revenues, ↑ Assets, ↑ Liabilities, **↓ Net Income**, ↓ Shareholders' Equity, **Translation Loss** | ↑ Revenues, ↑ Assets, ↑ Liabilities, **↑ Net Income**, ↑ SE, **Translation Gain** | ↑ Revenues, ↑ Assets, ↑ Liabilities, ↑ Net Income, ↑ SE, **Positive CTA** |
| **Foreign currency WEAKENS** | ↓ Revenues, ↓ Assets, ↓ Liabilities, **↑ Net Income**, ↑ SE, **Translation Gain** | ↓ Revenues, ↓ Assets, ↓ Liabilities, **↓ Net Income**, ↓ SE, **Translation Loss** | ↓ Revenues, ↓ Assets, ↓ Liabilities, ↓ Net Income, ↓ SE, **Negative CTA** |

> [!tip] Memory Aid
> - **Current rate method:** Everything moves in the same direction as the currency. Currency strengthens → everything goes up. Gain/loss goes to equity.
> - **Temporal method (net monetary liability — the typical case):** Revenue and assets still follow the currency, but **net income moves opposite** to the currency direction. Currency strengthens → translation loss → lower net income. This is because the company's monetary liabilities (translated at higher current rate) are bigger than its monetary assets.

---

## 7. Effects on Financial Ratios (LOS f)

### Current Rate Method: Ratio Effects

**Pure [[Balance sheet]] ratios** (e.g., [[Current ratio]], [[Quick ratio]], [[Debt-to-equity ratio]]) — **PRESERVED** after translation. Why? Both numerator and denominator are translated at the same rate (current rate), so the rate cancels out.

**Pure [[Income statement]] ratios** (e.g., [[Gross profit margin]], [[operating margin]], [[Net profit margin]], [[interest coverage ratio]]) — **PRESERVED** after translation. Both numerator and denominator use the average rate.

**Mixed ratios** (e.g., [[return on assets]], [[return on equity]], [[asset turnover]], [[receivables turnover]]) — **CHANGED** after translation. The numerator (IS item) uses the average rate while the denominator (BS item) uses the current rate.

> [!important] Direction of Change for Mixed Ratios (Current Rate Method)
> If the foreign currency is **depreciating**: Average rate > Current rate → IS items translated at higher rate than BS items → Mixed ratios with IS numerator and BS denominator **increase**
>
> If the foreign currency is **appreciating**: Average rate < Current rate → Mixed ratios **decrease**

> [!example] Concrete Example
> [[Return on assets]] = Net Income / Total Assets
> - Net Income translated at average rate (say, 0.75)
> - Total Assets translated at current rate (say, 0.80 if currency strengthened)
> - In local currency: ROA = 1,180 / 5,780 = 20.4%
> - After translation: ROA = 885 / 4,624 = 19.1%
> - The ratio **decreased** because the CAD strengthened (average < current)

### Temporal Method: Ratio Effects

Under the temporal method, **almost all ratios are distorted** — even pure ratios — because different items within the same financial statement use different exchange rates.

For example, [[Gross profit margin]]:
- Sales translated at average rate
- COGS translated at historical rate (because inventory is non-monetary)
- These are different rates → gross margin is distorted

### Comparing Ratios Between Methods

The procedure for analyzing any ratio:

1. Is the foreign currency appreciating or depreciating?
2. What rate translates the **numerator** under each method?
3. What rate translates the **denominator** under each method?
4. Which method gives a bigger/smaller numerator? Denominator?
5. Determine the ratio effect

> [!example] Fixed Asset Turnover (Revenue / Fixed Assets), Foreign Currency Depreciating
> - **Numerator (Revenue):** Average rate under both methods → **Same**
> - **Denominator (Fixed Assets):** Current rate (current rate method) vs. Historical rate (temporal method)
> - Depreciating currency → Historical rate > Current rate → Fixed assets **larger** under temporal
> - Result: Fixed asset turnover is **lower** under the temporal method

| Ratio | Current Rate vs. Temporal (Depreciating FC) |
|-------|---------------------------------------------|
| Gross Profit Margin | Higher under current rate (COGS at lower avg rate vs. higher historical rate under temporal) |
| Net Profit Margin | Depends on size of translation gain/loss |
| Fixed Asset Turnover | Higher under current rate (fixed assets at lower current rate) |
| AR Turnover | **Same** under both (Sales at avg, AR at current under both methods) |
| Current Ratio | Higher under current rate (inventory at current vs. historical) |
| D/E Ratio | Lower under current rate (equity is larger due to CTA) |

---

## 8. Hyperinflationary Economies (LOS g)

> [!tip] The "Disappearing Plant" Problem
> Imagine a US parent owns a factory in Argentina. The factory was built for ARS 100 million when $1 = ARS 10 (so $10 million equivalent). After years of hyperinflation, the exchange rate is $1 = ARS 1,000. If you translate the factory at the current rate: ARS 100 million / 1,000 = **$100,000**. A $10 million factory appears to be worth $100,000! The plant has "disappeared" from the consolidated balance sheet. This is the disappearing plant problem.

### Definition of Hyperinflation

| Standard | Definition |
|----------|-----------|
| [[US GAAP]] ([[ASC 830]]) | Cumulative three-year [[Inflation]] rate exceeds **100%** (~26% annually compounded) |
| [[IFRS]] ([[IAS 29]]) | Cumulative inflation **approaching or exceeding 100%** over three years (plus qualitative judgment) |

### Two Very Different Approaches

```
Hyperinflationary Subsidiary
           │
    ┌──────┴──────┐
    │             │
    ▼             ▼
 US GAAP        IFRS
    │             │
    ▼             ▼
 Use TEMPORAL   Step 1: RESTATE for
 METHOD         local inflation
 (no inflation  (IAS 29 procedures)
 adjustment)        │
    │             ▼
    │         Step 2: TRANSLATE
    │         at CURRENT rate
    │             │
    ▼             ▼
 Gain/loss    Gain/loss from
 on IS        purchasing power
              on IS
```

### IFRS Restatement Procedures (IAS 29)

**Balance Sheet:**
- [[Monetary assets]] and [[monetary liabilities]]: **Not restated** (already at current purchasing power)
- [[Non-monetary assets]] and liabilities: **Restated** by multiplying historical cost by the change in the general price index from acquisition date to BS date
- [[Shareholders' equity]] components (except [[retained earnings]]): Restated from beginning of period
- [[Retained earnings]]: **Plug figure** to balance the BS

**Income Statement:**
- All items restated by applying the change in the general price index from the dates when items were originally recorded
- A **net [[purchasing power]] gain or loss** is recognized:
  - Holding **monetary assets** during inflation → **[[Purchasing power loss]]** (your cash buys less)
  - Holding **monetary liabilities** during inflation → **[[Purchasing power gain]]** (you repay with cheaper currency)

> [!example] Turkey Example (CFA Curriculum)
> A US parent buys land in Turkey for TL 542,700,000 on Jan 1, 2000 when $1 = TL 542,700.
>
> | | Jan 1/00 | Dec 31/00 | Dec 31/01 | Dec 31/02 |
> |---|---------|-----------|-----------|-----------|
> | TL per USD | 542,700 | 670,880 | 1,474,525 | 1,669,000 |
> | **Current rate method:** | $1,000 | $809 | $368 | $325 |
> | **Temporal method:** | $1,000 | $1,000 | $1,000 | $1,000 |
>
> Under the current rate method, the land "disappears" from $1,000 to $325. Under the temporal method, it stays at $1,000 (historical cost preserved).
>
> Under **IFRS** (restate then translate), if cumulative inflation was ~207% over 3 years, the restated value would be: TL 542,700,000 × (1,669,000/542,700) = TL ~1.67 billion, translated at current rate = **$1,000**. The IFRS approach better reflects that the land's real value hasn't changed — it's the currency that deteriorated.

> [!warning] Key Exam Distinction
> - **US GAAP**: Temporal method. No inflation adjustment. Translation gain/loss on IS. Avoids disappearing plant but doesn't reflect inflation's impact on real values.
> - **IFRS**: Restate for inflation first, then translate everything at current rate. More complex but arguably more faithful to economic reality. Purchasing power gain/loss on IS.

---

## 9. Effective Tax Rate (LOS h)

> [!tip] The Intuition
> A US company earning 60% of profits domestically (35% tax rate) and 40% in Ireland (12.5% tax rate) will have a blended [[effective tax rate]] below 35%. But a Dutch company earning 40% domestically (25% tax rate) and 60% in the US will have an effective rate **above** 25%. The geographic mix of profits drives the effective rate.

### How Multinational Operations Affect Taxes

Companies pay taxes in **each country where they earn profits**. The [[effective tax rate]] on [[consolidated financial statements]] is a weighted blend of all jurisdictions.

$$\text{Effective Tax Rate} = \frac{\text{Total [[Income Tax Expense]]}}{\text{Total Pre-tax Income}} = \text{Weighted average of all jurisdictions}$$

### Key Disclosure: Statutory-to-Effective Rate Reconciliation

Both [[IFRS]] and [[US GAAP]] require companies to reconcile their [[statutory tax rate]] to their [[effective tax rate]]. The line item "effect of foreign operations" or "earnings taxed at other than statutory rate" reveals whether international operations are tax-beneficial.

> [!example] Heineken vs. Colgate-Palmolive (CFA Curriculum)
> - **Heineken** (Netherlands, 25% statutory): Foreign operations **increased** effective rate by 3.5 percentage points → Heineken earns significant profits in **higher-tax** countries
> - **Colgate-Palmolive** (US, 35% statutory): Foreign operations **decreased** effective rate by 1.7 percentage points → Colgate earns significant profits in **lower-tax** countries
>
> **Analyst use:** If the mix of profits shifts toward lower-tax jurisdictions (e.g., a company expands more aggressively in Singapore vs. Germany), the effective rate should decrease, boosting after-tax earnings. Conversely, expansion into higher-tax countries raises the effective rate.

### Factors That Can Change the Effective Tax Rate

- Changes in the **geographic mix** of profits between high-tax and low-tax countries
- Changes in **tax rates** in specific countries
- **[[Transfer pricing]]** between subsidiaries (companies may allocate costs/revenues to shift profits to lower-tax jurisdictions, subject to regulatory limits)
- **Tax treaties** between countries that prevent double-taxation (most countries grant credits for taxes paid abroad)

> [!example] Profit Mix Shift Example
> | | Year 0 | Year 1 | Year 2 | Year 3 |
> |---|--------|--------|--------|--------|
> | Profit in Country A (40% tax) | 100 | 100 | 100 | 100 |
> | Profit in Country B (10% tax) | 100 | 115 | 132 | 152 |
> | Total Tax | 50 | 52 | 53 | 55 |
> | **Effective Tax Rate** | **25%** | **24%** | **23%** | **22%** |
>
> Even though no tax rates changed, the effective rate drops because the **faster-growing jurisdiction** (Country B) has a lower rate. An analyst who misses this trend will overestimate future tax expense.

---

## 10. Sales Growth Sustainability (LOS i)

### Decomposing Sales Growth

For a [[Multinational corporation]], sales growth has three components:

$$\text{Sales Growth} = f(\text{Volume Change}, \text{Price Change}, \text{Exchange Rate Change})$$

> [!important] The Core Analyst Insight
> Growth from **volume and price changes** is considered **more sustainable** because management has some control over these levers. Growth from **exchange rate changes** is **less sustainable** because currency movements are largely outside management's control and can reverse quickly.

**Organic growth** = Sales growth excluding currency effects and acquisitions/divestitures. This is what analysts focus on to assess the quality of a company's revenue growth.

> [!example] BCN, Inc. — American Multinational (Curriculum-Style Example)
> | Region | Reported Growth | FX Effect | Organic Growth |
> |--------|----------------|-----------|---------------|
> | North America ex-US | 2% | −3% | **5%** |
> | Europe | 2% | +2% | **0%** |
> | Asia-Pacific | 7% | +4% | **3%** |
>
> **Analysis:**
> - **North America ex-US** looks like only 2% growth, but the local currency depreciated. Stripping out FX, organic growth was actually **5%** — strong real performance masked by currency headwinds.
> - **Europe** shows 2% growth, but **all of it** came from currency appreciation. Organic growth was **zero** — no real volume or pricing gains.
> - **Asia-Pacific** grew 7% on paper, but 4 points came from FX. Organic growth was a moderate 3%.
>
> **Conclusion:** North America ex-US has the most sustainable growth despite the lowest reported growth number.

Companies often disclose FX effects on sales in their **MD&A** section. Look for language like "excluding the impact of foreign currency" or "on a constant currency basis."

---

## 11. Currency Fluctuations and Financial Results (LOS j)

### Sensitivity Analysis

Many multinationals disclose how currency movements affect their results. For example, Nokia disclosed:
- 40% of net sales were in USD or USD-linked currencies
- 60% of components were sourced in USD
- A 4.2% appreciation of USD had a **positive effect on revenue** but a **negative effect on costs**, resulting in a slightly negative impact on [[Operating profit]]

This illustrates that currency effects are **not one-directional** — they affect revenues and costs differently depending on where you sell vs. where you source.

### Framework for Analyzing Currency Impact

```
Company with Foreign Operations
          │
    ┌─────┴─────┐
    │           │
    ▼           ▼
Revenue       Cost
Exposure      Exposure
    │           │
    ▼           ▼
Where do      Where are
you SELL?     inputs SOURCED?
    │           │
    ▼           ▼
If foreign    If foreign
currency      currency
strengthens:  strengthens:
Revenue ↑     Costs ↑
    │           │
    └─────┬─────┘
          │
          ▼
    Net Effect on
    Operating Profit
    depends on the
    BALANCE between
    revenue and cost
    exposure
```

> [!example] Real-World: A US Retailer vs. A US Manufacturer
> **US Retailer (e.g., Walmart):** Revenue mostly in USD (domestic sales), but sources goods from China (CNY costs). If CNY strengthens → costs rise but revenues unchanged → **profits squeezed**.
>
> **US Manufacturer (e.g., Boeing):** Revenue in multiple [[Currencies|currencies]] (international sales), but sources labor/materials domestically in USD. If foreign currencies strengthen → translated revenue rises but costs unchanged → **profits expand**.

### Using Both Methods Simultaneously

A [[Multinational corporation|multinational corporation]]on|corporation]] may need to use **both** translation methods at the same time:
- Some subsidiaries with a foreign functional currency → **[[Current rate method|current rate method]]** → CTA in equity
- Other subsidiaries with the parent's functional currency → **[[Temporal method|temporal method]]** → gain/loss in income

This means the consolidated financial statements can simultaneously show:
- A **remeasurement gain/loss in [[Net income|net income]]** (from [[Temporal method|temporal method]] subsidiaries)
- A **[[cumulative translation adjustment]] in equity** (from [[Current rate method|current rate method]] subsidiaries)

> [!warning] Comparability Alert
> Because companies are **not required** to separately disclose the transaction gain/loss component vs. the [[Temporal method|temporal method]] remeasurement gain/loss, an analyst may struggle to decompose the total FX gain/loss reported in income. The [[CTA]] in equity is usually easier to track.

---

## 12. IFRS vs. US GAAP Summary

| Topic | IFRS | US GAAP |
|-------|------|---------|
| FX transaction gains/losses | Recognized in P&L | Recognized in P&L |
| Placement of FX gains/losses in IS | Not specified | Not specified |
| Translation method selection | Based on functional currency | Based on functional currency (identical logic) |
| [[Current rate method|Current rate method]] CTA | In equity (OCI) | In equity (OCI) |
| [[Temporal method|Temporal method]] gain/loss | In [[Net income|net income]] | In [[Net income|net income]] ("remeasurement") |
| **Hyperinflation treatment** | **Restate for [[Inflation|inflation]] (IAS 29) → translate at current rate** | **Use temporal method (no restatement)** |
| Definition of hyperinflation | ~100% cumulative over 3 years + judgment | >100% cumulative over 3 years |
| Disposal of foreign entity | CTA recycled to IS | CTA recycled to IS |

> [!tip] Good News for Exam Prep
> IFRS and US GAAP are **virtually identical** on multinational operations — the **only major difference** is the treatment of hyperinflationary economies. Everything else (transaction accounting, functional currency determination, translation methods, ratio effects) is the same.

---

## 13. Key Formulas

**[[Foreign currency|Foreign currency]] transaction gain/loss:**
$$\text{Gain/Loss} = \text{Amount in FC} \times (\text{Exchange Rate}_{\text{settlement}} - \text{Exchange Rate}_{\text{transaction}})$$

*Positive = gain on asset exposure when FC strengthens; loss on liability exposure when FC strengthens*

**Translation adjustment ([[Current rate method|current rate method]]):**
$$\text{CTA} = \text{Plug to balance the translated BS}$$

*Accumulated in [[shareholders' equity]] as a component of [[OCI]]*

**Remeasurement gain/loss (temporal method):**
$$\text{Remeasurement G/L} = \text{Plug to balance the translated BS (through IS)}$$

**Retained earnings roll-forward (both methods):**
$$\text{End R/E}_{PC} = \text{Beg R/E}_{PC} + \text{NI}_{PC} - \text{Div}_{PC}$$

Where $\text{NI}_{PC}$ is derived from translating the IS using the appropriate method, and $\text{Div}_{PC}$ is translated at the historical rate when declared.

**Effective tax rate:**
$$\text{Effective Tax Rate} = \text{Statutory Rate} \pm \text{Foreign Rate Differential} \pm \text{Other Adjustments}$$

**Sales decomposition:**
$$\Delta\text{Sales} = \Delta\text{Volume} + \Delta\text{Price} + \Delta\text{Exchange Rate}$$

---

## 14. Practice Framework: Solving Translation Problems

> [!tip] Step-by-Step Approach for Exam Questions
> 1. **Identify the functional currency** — Does it equal the parent's [[Presentation currency|presentation currency]]?
>    - Yes → Temporal method
>    - No → Current rate method
>    - Hyperinflationary? → Check IFRS vs. US GAAP rules
> 2. **Determine the exchange rate direction** — Did the [[Foreign currency|foreign currency]] strengthen or weaken?
> 3. **Apply the correct rates** to each line item
> 4. **Translate the IS first** (to get NI for the R/E calculation)
> 5. **Roll forward R/E** using the translated IS figures
> 6. **Translate the BS** (everything except R/E and the adjustment)
> 7. **Plug the adjustment:**
>    - Current rate → CTA in equity
>    - Temporal → Remeasurement gain/loss in IS (then re-derive R/E)
> 8. **Verify:** Assets = [[Liabilities|Liabilities]] + Equity

---

## 15. Key Takeaways for Analysts

> [!important] What You Need to Remember
> 1. The **functional currency choice** is management's most impactful judgment in this area — it determines the method, which determines the numbers.
> 2. Under the **current rate method**, pure ratios are preserved but the CTA in equity can be massive and invisible to income-focused analysts.
> 3. Under the **temporal method**, income is more volatile because translation gains/losses hit the IS directly.
> 4. **Hyperinflation** is the one area where IFRS and US GAAP diverge meaningfully.
> 5. When evaluating sales growth, **always decompose** into organic (volume + price) and currency-driven components. Currency-driven growth is not sustainable.
> 6. The **effective tax rate** reflects the geographic mix of profits — track trends in this rate as the company's international footprint evolves.
> 7. When comparing companies (e.g., Exxon vs. Chevron), check whether they use the same functional currency approach. If not, you may need to adjust one company's results to make them comparable — one approach is to add the CTA to [[Net income|net income]] for both companies (a "[[clean surplus]]" approach).
