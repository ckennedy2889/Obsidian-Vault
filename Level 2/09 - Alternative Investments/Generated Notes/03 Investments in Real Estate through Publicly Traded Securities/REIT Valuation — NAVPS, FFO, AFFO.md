---
title: REIT Valuation — NAVPS, FFO, AFFO
subject: Alternative Investments
tags:
  - CFA-L2
  - alternative-investments
  - real-estate
  - REITs
  - NAVPS
  - FFO
  - AFFO
  - cap-rate
  - valuation
aliases:
  - NAVPS
  - FFO
  - AFFO
  - funds from operations
  - adjusted funds from operations
  - net asset value per share
  - REIT valuation
  - P/FFO
  - P/AFFO
---

# REIT Valuation — NAVPS, FFO, AFFO

## The Real-World Analogy

Imagine you own an apartment building. At year-end, your accountant reports a $50,000 loss because the building "depreciated" by $80,000. But your building is actually worth more than it was last year — real estate tends to appreciate. Your accountant's loss is a fiction driven by accounting rules, not economic reality.

REITs have this problem at scale. Their income statements are dominated by large depreciation charges that have nothing to do with whether the properties are generating cash. So analysts invented alternative measures — FFO, AFFO, and NAV — to cut through the accounting noise and reveal what the REIT is actually worth and actually earning.

## Plain-English Definition

**NAVPS (Net Asset Value Per Share):** The private-market value of the REIT's properties minus all liabilities, divided by shares outstanding. It asks: "What would a private buyer pay for this portfolio of buildings today?"

**FFO (Funds From Operations):** Net income with depreciation added back and gains from property sales removed. It's a better measure of recurring operating cash flow than GAAP net income.

**AFFO (Adjusted Funds From Operations):** FFO further adjusted for non-cash rent items and recurring maintenance capital expenditure. It's the best proxy for sustainable cash available for distribution.

---

## Why CFA Tests This

The LOS requires:
- Calculating NAVPS from given inputs
- Calculating FFO and AFFO from given financials
- Using P/FFO and P/AFFO as relative valuation multiples
- Understanding what drives REIT valuation multiples

The exam loves to test the depreciation add-back logic, the non-cash rent subtraction, and which items belong in FFO vs AFFO.

---

## Approach 1: Net Asset Value Per Share (NAVPS)

### The Logic

NAVPS values the REIT as a portfolio of real estate assets, not as a going-concern income stock. It represents **what the properties would fetch in the private market** if the REIT were liquidated today.

### The Calculation Process — Step by Step

**Step 1: Estimate Next 12 Months (NTM) Cash NOI**

Start with the last 12 months' Net Operating Income (NOI) and make adjustments:

| Adjustment | Why |
|---|---|
| Subtract non-cash (straight-line) rent | Early lease years: straight-line rent > cash rent; must use actual cash |
| Add full-year impact of acquisitions | A building acquired mid-year only shows 6 months of NOI; annualize it |
| Apply estimated growth rate | NTM = forward-looking, not trailing |

$$\text{NTM Cash NOI} = (\text{Trailing NOI} - \text{Non-cash rent} + \text{Acquisition adjustment}) \times (1 + g)$$

**Step 2: Capitalize the Cash NOI**

$$\text{Value of Operating Real Estate} = \frac{\text{NTM Cash NOI}}{\text{Cap Rate}}$$

The **cap rate** is the market's required return on the property portfolio, derived from comparable private-market transactions. A lower cap rate = higher property value (markets are willing to pay more for each dollar of NOI).

> [!warning] Cap Rate Selection Is Critical
> The cap rate used must reflect the type of property (office, retail, industrial, residential), the location, and current market conditions. If the exam gives you a cap rate, use it exactly as given — don't infer a "better" one.

**Step 3: Add Other Assets**

$$\text{Gross Asset Value (GAV)} = \text{Value of Operating Real Estate} + \text{Cash} + \text{Accounts Receivable} + \text{Land Held for Development}$$

Note: Land is **never depreciated** (infinite life) and is already at or near market value on the balance sheet if recently acquired.

**Step 4: Subtract All Liabilities**

$$\text{NAV} = \text{GAV} - \text{Total Debt (market value)} - \text{Other Liabilities}$$

Exclude "soft" liabilities like deferred tax liabilities — these are not real cash obligations.

**Step 5: Divide by Shares**

$$\boxed{\text{NAVPS} = \frac{\text{NAV}}{\text{Shares Outstanding}}}$$

### Worked NAVPS Example

**Given:**
- Trailing 12-month NOI: $10,000,000
- Non-cash straight-line rent: $200,000
- Growth estimate: 3%
- Cap rate: 6.5%
- Cash and receivables: $500,000
- Total debt: $60,000,000
- Shares outstanding: 5,000,000

**Step 1 — NTM Cash NOI:**

$$= (10{,}000{,}000 - 200{,}000) \times 1.03 = 9{,}800{,}000 \times 1.03 = \$10{,}094{,}000$$

**Step 2 — Value of Operating Real Estate:**

$$= \frac{\$10{,}094{,}000}{0.065} = \$155{,}292{,}308$$

**Step 3 — GAV:**

$$= \$155{,}292{,}308 + \$500{,}000 = \$155{,}792{,}308$$

**Step 4 — NAV:**

$$= \$155{,}792{,}308 - \$60{,}000{,}000 = \$95{,}792{,}308$$

**Step 5 — NAVPS:**

$$= \frac{\$95{,}792{,}308}{5{,}000{,}000} = \mathbf{\$19.16}$$

If the REIT trades at $18, it's at a **discount to NAV** (potential buy signal). If it trades at $21, it's at a **premium to NAV**.

---

## Approach 2: FFO and AFFO

### Why GAAP Net Income Fails for REITs

GAAP requires depreciation of real estate assets. But real estate often *appreciates* over time. The result: a REIT can show a large GAAP net loss while actually generating strong cash flow. GAAP net income is nearly useless for REIT valuation.

FFO was developed by the National Association of Real Estate Investment Trusts (NAREIT) to solve this.

### FFO — Funds From Operations

**Formula:**

$$\boxed{\text{FFO} = \text{Net Income} + \text{Depreciation \& Amortization} - \text{Net Gains from Property Sales}}$$

Or in table form:

| Item | Adjustment |
|---|---|
| Net Income (GAAP) | Starting point |
| + Depreciation and Amortization | Add back (non-cash; real estate appreciates) |
| − Net Gains on Property Sales | Remove (non-recurring, distorts operating income) |
| + Net Losses on Property Sales | Add back (symmetric treatment) |
| **= FFO** | |

**Why these adjustments?**

1. **Add back depreciation:** Buildings do not "wear out" like machinery. The depreciation charge is a GAAP convention, not an economic cost. Adding it back reveals true operating cash generation.

2. **Remove property sale gains/losses:** Selling a building is a one-time event, not part of recurring operations. It should not inflate (or deflate) the measure of sustainable earnings.

### AFFO — Adjusted Funds From Operations

**Formula:**

$$\boxed{\text{AFFO} = \text{FFO} - \text{Non-cash (Straight-line) Rent} - \text{Recurring Maintenance CAPEX} - \text{Leasing Commissions}}$$

| Item | Adjustment |
|---|---|
| FFO | Starting point |
| − Non-cash straight-line rent | Remove accounting artifact; use only actual cash rent |
| − Recurring maintenance CAPEX | Cash needed to keep properties in rentable condition |
| − Leasing commissions and tenant improvements | Cash costs of re-leasing space |
| **= AFFO** | |

**Why AFFO is better than FFO:**

AFFO reflects the cash that is truly available to distribute to shareholders after keeping the properties in good shape. FFO ignores the capital spending required to maintain the portfolio. AFFO is the more accurate measure of **dividend-paying capacity**.

### Non-Cash Straight-Line Rent — Explained

Lease contracts often have built-in rent step-ups (e.g., 3% per year). GAAP requires "straight-lining" — averaging the total contractual rent over the lease term and recognizing a smooth amount each period.

In early years: **Cash rent < Straight-line rent** → GAAP shows more income than cash received → subtract to get cash reality
In later years: **Cash rent > Straight-line rent** → GAAP shows less income than cash received → add back

For the NAVPS calculation (cash NOI) and AFFO, you always want **actual cash rent**, so subtract the excess straight-line rent.

---

## Approach 3: Relative Value Multiples

### P/FFO

$$P/FFO = \frac{\text{Share Price}}{\text{FFO per Share}}$$

Most widely used REIT multiple. Similar to P/E for stocks. Readily available from market data.

**Limitation:** Ignores the capital expenditure needed to maintain the property portfolio.

### P/AFFO

$$P/AFFO = \frac{\text{Share Price}}{\text{AFFO per Share}}$$

More accurate measure of value but requires more estimation (CAPEX assumptions vary by analyst).

### What Drives Higher Multiples

| Driver | Effect on Multiple |
|---|---|
| Higher expected NOI growth | Higher multiple (growth premium) |
| Lower risk property type | Higher multiple (e.g., industrial > office post-COVID) |
| Lower financial leverage | Higher multiple (less equity risk) |
| Strong management track record | Higher multiple |
| Favorable cap rate environment | Higher multiple (lower rates → higher property values) |

---

## IFRS vs. US GAAP for REITs

| | US GAAP | IFRS |
|---|---|---|
| **Investment property accounting** | Cost model (historical cost − depreciation) | Fair value model allowed |
| **Depreciation** | Always required | Not required if using fair value model |
| **Unrealized gains/losses** | Not recognized | Flow through income statement (IFRS fair value) |
| **Impact on FFO** | Must add back depreciation | May not need to if using fair value (no depreciation) |
| **Impact on net income** | Understates value | May reflect market values more directly |

> [!note] IFRS Fair Value Trap
> Under IFRS fair value model, increases in property values flow through net income. If the exam asks you to calculate FFO under IFRS, check whether depreciation exists — if the company uses fair value accounting, there may be no depreciation to add back.

---

## Summary Comparison: FFO vs AFFO vs Net Income

| Metric | Depreciation | Gains/Losses | Non-cash Rent | Maintenance CAPEX | Purpose |
|---|---|---|---|---|---|
| Net Income | Included | Included | Included | Included | GAAP compliance |
| FFO | Added back | Removed | Included | Included | Operating performance |
| AFFO | Added back | Removed | Removed (cash only) | Deducted | Dividend capacity |

---

## Exam Traps

> [!danger] Key REIT Valuation Exam Traps

| Trap | Correct Understanding |
|---|---|
| Depreciation reduces real estate value | Real estate typically appreciates — GAAP depreciation is unrealistic, so add it back in FFO |
| Land is depreciated | Land is **never depreciated** (infinite life) |
| Straight-line rent is added back in AFFO | Straight-line rent (non-cash) is **subtracted** — AFFO uses actual cash rent |
| Property sale gains stay in FFO | Gains (and losses) on property sales are **removed** from FFO — they're non-recurring |
| FFO = AFFO | FFO ignores maintenance CAPEX and non-cash rent adjustments; AFFO includes them |
| Cap NOI with forward cap rates | Always use a cap rate consistent with current **private market transactions** for comparable properties |
| P/FFO is more accurate than P/AFFO | P/AFFO is more accurate; P/FFO ignores capital spending requirements |

---

## Memory Hooks

- **FFO = Net Income + Depreciation − Gains**: "FFO adds the D, removes the G" (D = Depreciation, G = Gains)
- **AFFO = FFO − Non-cash − Capex**: one step cleaner, removes the accounting artifacts
- **NAVPS = NOI ÷ Cap Rate → minus debt ÷ shares**: think "cap and divide"
- **Straight-line rent SUBTRACT**: early years get more accounting income than cash — remove it to find cash
- **P/AFFO > P/FFO in accuracy**: AFFO reflects real cash, FFO doesn't account for maintenance

---

## Related Concepts

- [[Real Estate - Public Securities (REITs, REOCs, NAVPS)]] — broader coverage of REIT types and structures
- [[Real Estate Valuation Methods]] — direct capitalization, DCF, and sales comparison for private real estate
- [[NOI and Cap Rate]] — the building blocks of real estate income valuation
- [[Dividend Discount Model]] — REIT dividends often modeled with DDM due to high payout ratios
- [[Free Cash Flow to Equity]] — AFFO is conceptually close to FCFE for REITs
