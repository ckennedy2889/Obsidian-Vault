---
title: Real Estate Valuation Methods
subject: Alternative Investments
tags:
  - CFA-L2
  - alternative-investments
  - real-estate
  - valuation
  - NOI
  - cap-rate
  - DCF
  - sales-comparison
  - cost-approach
  - direct-capitalization
aliases:
  - real estate appraisal
  - income approach
  - direct capitalization
  - sales comparison approach
  - cost approach
  - NOI
  - cap rate
  - property valuation
---

# Real Estate Valuation Methods

## The Real-World Analogy

When a bank decides how much to lend you for a property purchase, it requires an appraisal. The appraiser isn't guessing — they use three distinct lenses to estimate what the property is truly worth.

First, how much income does it generate? (Income approach — the most important for commercial property.)
Second, what did similar properties nearby sell for recently? (Sales comparison — like pricing a used car by finding comparable sales.)
Third, what would it cost to build this from scratch today, minus wear and tear? (Cost approach — the "rebuild it" test.)

These three methods form the backbone of private real estate valuation. They should arrive at similar values; if they don't, something needs explaining.

## Plain-English Definition

Private real estate is valued using three primary approaches:
1. **Income Approach** — value based on the property's ability to generate income
2. **Sales Comparison Approach** — value based on recent sales of comparable properties
3. **Cost Approach** — value based on what it would cost to reproduce the property, net of depreciation

Each is suited to different property types and market conditions. Analysts typically use multiple methods and reconcile the results.

---

## Why CFA Tests This

The LOS requires:
- Describing and applying all three valuation approaches
- Calculating NOI correctly (and knowing what NOT to include)
- Applying the direct capitalization formula
- Building a DCF with terminal value using the terminal cap rate
- Understanding when each method is most appropriate

---

## The Foundation: Net Operating Income (NOI)

NOI is the property-level equivalent of EBITDA — it measures the income the property generates before financing costs and taxes. It is the core input to income-based valuation.

### The NOI Waterfall

$$\text{Potential Gross Income (PGI)} = \text{Full-occupancy rent} + \text{Other income}$$

$$-\ \text{Vacancy and Collection Losses}$$

$$= \text{Effective Gross Income (EGI)}$$

$$-\ \text{Operating Expenses (property taxes, insurance, maintenance, management)}$$

$$= \boxed{\text{Net Operating Income (NOI)}}$$

> [!danger] Critical Exam Trap — What NOI Excludes
> **DO NOT subtract from NOI:**
> - Interest expense (NOI is pre-financing)
> - Income taxes (NOI is pre-tax)
> - Depreciation (NOI is a cash measure, not GAAP)
> - Capital expenditures (maintenance CAPEX)
>
> These exclusions are tested constantly. NOI is purely a property-level operating measure.

### The Cap Rate

The **capitalization rate** (cap rate) is the market's required return on the property, adjusted for growth:

$$\text{Cap Rate} = r - g$$

Where $r$ = required return and $g$ = expected perpetual NOI growth rate.

**Why it matters:** The cap rate is the discount rate minus growth — just like the Gordon Growth Model denominator. A lower cap rate means investors are willing to pay more for each dollar of NOI.

| Cap Rate | Implied Valuation |
|---|---|
| High cap rate (e.g., 10%) | Lower price per dollar of NOI — higher required return or lower growth |
| Low cap rate (e.g., 5%) | Higher price per dollar of NOI — safer asset or stronger growth |

---

## Approach 1: Income Approach

### A. Direct Capitalization Method

**When to use:** Stable, income-producing properties with consistent NOI (e.g., fully-leased office or industrial).

$$\boxed{\text{Property Value} = \frac{\text{NOI}_1}{\text{Cap Rate}}}$$

The numerator is the **expected Year 1 NOI** (i.e., next 12 months' income). This is identical in form to a perpetual growth model:

$$V = \frac{NOI_1}{r - g} = \frac{NOI_1}{\text{Cap Rate}}$$

**Worked Example:**

A warehouse generates NOI of €406,750. The required return is 12.5%, and NOI grows at 2% per year.

$$\text{Cap Rate} = 12.5\% - 2\% = 10.5\%$$

$$\text{Value} = \frac{€406{,}750}{0.105} = \mathbf{€3{,}873{,}810}$$

**Sensitivity check:** If the cap rate were 9.5% instead:

$$\text{Value} = \frac{€406{,}750}{0.095} = €4{,}281{,}579 \quad (+10.5\% \text{ higher})$$

This illustrates how sensitive property values are to cap rate changes — a 1% shift in cap rate can move value by 10%+.

### B. Discounted Cash Flow (DCF) Method

**When to use:** Properties with variable NOI — lease expirations, value-add situations, development projects, or short-term market cycles.

**Steps:**
1. Project NOI for each year of the holding period (typically 5–10 years)
2. Estimate the **terminal value** (resale price) at the end of the holding period
3. Discount all cash flows at the required return $r$

$$\text{Terminal Value} = \frac{NOI_{n+1}}{\text{Terminal Cap Rate}}$$

$$\text{Property Value} = \sum_{t=1}^{n}\frac{NOI_t}{(1+r)^t} + \frac{TV}{(1+r)^n}$$

> [!warning] Going-In vs. Terminal Cap Rate
> The **terminal cap rate is typically higher** than the going-in cap rate. Why? By the time you sell the property, it will be older, less modern, and potentially less competitive. A higher cap rate on exit reflects higher perceived risk at that point. If the exam gives you both rates, use the terminal cap rate only for the terminal value calculation.

**Worked Example:**

An investor projects a 5-year hold. Year 6 NOI = $3,439,613. Terminal cap rate = 6%. Discount rate = 9%.

$$\text{Terminal Value} = \frac{\$3{,}439{,}613}{0.06} = \$57{,}326{,}883$$

The property value today = PV of Year 1–5 NOIs + PV of $57,326,883 at Year 5.

If Year 1–5 NOIs PV = $12,000,000 (hypothetical):

$$V = \$12{,}000{,}000 + \frac{\$57{,}326{,}883}{(1.09)^5} = \$12{,}000{,}000 + \$37{,}252{,}000 = \mathbf{\$49{,}252{,}000}$$

---

## Approach 2: Sales Comparison Approach

**When to use:** Residential properties, or commercial properties in active markets with many comparable transactions.

**How it works:** Find recently sold properties similar to the subject, adjust for differences, and estimate the subject's value from the adjusted comparable prices.

### Common Units of Comparison

| Unit | Typical Use |
|---|---|
| **Price per square foot** | Office, retail, industrial, residential |
| **Gross Income Multiplier (GIM)** | Multi-family or small income properties |
| **Price per unit** | Apartment buildings |

$$\text{GIM} = \frac{\text{Sale Price}}{\text{Gross Rental Income}}$$

$$\text{Property Value} = \text{GIM} \times \text{Subject's Gross Income}$$

### Adjustments to Comparables

You always adjust the **comparable's price** to make it equivalent to the **subject property**. The rule:

- If the comparable is **superior** to the subject in some respect → make a **negative adjustment** (reduce comparable's price)
- If the comparable is **inferior** → make a **positive adjustment** (increase comparable's price)

Common adjustment factors: location, size, age/condition, amenities, sale date (market conditions).

**Worked Example:**

Subject: 5-year-old office building, 10,000 sq ft
Comparable: sold for $103.20/sq ft, 2 years old, otherwise similar

The comparable is **newer** (superior) → negative adjustment, say −3% for age.

$$\text{Adjusted comparable price} = \$103.20 \times (1 - 0.03) = \$103.20 \times 0.97 = \$100.10/\text{sq ft}$$

$$\text{Subject estimated value} = \$100.10 \times 10{,}000 = \mathbf{\$1{,}001{,}000}$$

---

## Approach 3: Cost Approach

**When to use:** Special-use properties with few comparable sales (hospitals, schools, churches), new construction, or properties where income approach doesn't apply.

**The logic:** No rational investor will pay more for an existing building than it would cost to build a new one with the same utility — after adjusting for the fact that the existing building has aged.

$$\boxed{\text{Property Value} = \text{Land Value} + \text{Replacement Building Cost} - \text{Accumulated Depreciation}}$$

### Three Forms of Depreciation in Real Estate

| Type | Description | Example |
|---|---|---|
| **Physical deterioration** | Normal wear and tear | Roof needs replacement |
| **Functional obsolescence** | Outdated design or features | No central A/C in 1960s office |
| **External (economic) obsolescence** | External factors reduce value | New highway creates noise next door |

> [!danger] Land Is Never Depreciated
> Land has infinite life. Never apply depreciation to land in the cost approach — only to the improvements (building) built on the land.

**Worked Example:**

- Land value: €750,000
- Replacement cost of building (new): €3,600,000
- Building age: 4 years, estimated useful life: 30 years

**Depreciation:**

$$\text{Annual depreciation} = \frac{€3{,}600{,}000}{30} = €120{,}000/\text{year}$$

$$\text{Accumulated depreciation} = 4 \times €120{,}000 = €480{,}000$$

**Property Value:**

$$= €750{,}000 + €3{,}600{,}000 - €480{,}000 = \mathbf{€3{,}870{,}000}$$

---

## Highest and Best Use

The **highest and best use** principle states that property is valued at its most economically productive use, not necessarily its current use.

A use must be:
1. **Legally permissible** (zoning allows it)
2. **Physically possible** (site can support it)
3. **Financially feasible** (generates a positive return)
4. **Maximally productive** (highest value among feasible uses)

**Implication:** A parking lot in a commercial district might be valued as the site for a potential office tower, even though it's currently used for parking. The current use is just one option.

---

## Method Comparison and Selection

| | Income — Direct Cap | Income — DCF | Sales Comparison | Cost Approach |
|---|---|---|---|---|
| **Best for** | Stable income-producing commercial | Variable NOI, development | Residential, active markets | Special-use, new construction |
| **Key input** | Stabilized NOI, cap rate | Projected NOIs, terminal cap rate | Comparable sales | Replacement cost, land value |
| **Limitation** | Assumes constant growth | Requires detailed projections | Needs active comparable market | Subjective depreciation |
| **Exam frequency** | High (cap calculations) | Medium-high (DCF setup) | Medium | Low-medium |

---

## Exam Traps

> [!danger] Key Real Estate Valuation Exam Traps

| Trap | Correct Understanding |
|---|---|
| Include interest expense in NOI | Never — NOI is pre-financing |
| Use same cap rate for going-in and terminal | Terminal cap rate is typically **higher** (property is older at sale) |
| Depreciate land | Land has infinite life — **never depreciate** |
| Adjust the subject, not the comparable | In sales comparison, adjust the **comparable's price** to match the subject |
| Higher cap rate = higher value | Opposite: higher cap rate = lower value ($V = NOI / \text{cap rate}$) |
| NOI includes depreciation deduction | NOI is cash-based, no depreciation |
| In oversupply, cost approach gives reliable value | Actually, during oversupply, replacement cost may exceed market value — cost approach overestimates |

---

## Memory Hooks

- **NOI = EGI − OE**: NO interest, NO taxes, NO depreciation, NO CAPEX
- **Direct cap formula = NOI ÷ cap rate**: like Gordon Growth Model ($D_1 / (r-g)$)
- **Cap rate = r − g**: higher growth → lower cap rate → higher value
- **Terminal cap rate > going-in cap rate**: older at exit → more risk
- **Sales comparison: adjust the comp**: if comp is better, mark it down; if worse, mark it up
- **Cost approach: land never depreciates**

---

## Related Concepts

- [[REIT Valuation — NAVPS, FFO, AFFO]] — NAVPS uses the direct capitalization method at portfolio level
- [[Real Estate - Private Investment and Valuation]] — broader overview of private real estate features
- [[Real Estate - Public Securities (REITs, REOCs, NAVPS)]] — public market approach to real estate
- [[Free Cash Flow to Equity]] — AFFO is conceptually similar; both measure distributable cash
- [[Dividend Discount Model]] — direct cap method is structurally identical to the Gordon Growth Model
