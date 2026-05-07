# Real Estate — Private Investment and Valuation

> [!info] CFA L2 — [[Alternative investments|Alternative Investments]] | Module 2
> **Overview of Types of [[Real estate|Real Estate]] Investment**
> Source: CFA Program Curriculum 2025 Level 2, Volume 8

---

## LOS (a): Real Estate Investment Features and Economic Value Drivers

### Why Real Estate Is Unique as an Asset Class

[[Real estate]] sits at the intersection of a physical asset and a financial investment. Unlike stocks or bonds, each property is **unique** — no two buildings are identical in location, condition, or tenant mix. This creates both opportunities and challenges.

### Portfolio Benefits of Real Estate

- **Current income:** [[NOI]] from rents provides steady cash flow
- **Appreciation:** Property values tend to rise over the long term
- **[[Inflation]] hedging:** Lease step-up clauses and rising replacement costs provide a natural hedge
- **[[Diversification]]:** Low [[Correlation]] with traditional stocks and bonds (especially private [[Real estate|real estate]])

### Key Financial Metrics

#### [[NOI]] (Net Operating Income)

The single most important number in [[Real estate]] [[Valuation|valuation]] — it measures how much cash a property generates from operations:

$$\text{NOI} = \text{EGI} - \text{Operating Expenses} - \text{Property Maintenance Allowance}$$

Where **EGI (Effective Gross Income)** = Gross potential rental income − vacancy/collection losses + other income

> [!tip] Analogy
> [[NOI]] is like the "[[Operating profit|operating profit]]" of a property. It tells you how much money the building makes from rent after paying all the bills to keep it running — but *before* paying the mortgage or taxes.

#### Capital Structure Metrics

| Metric | Formula | What It Tells You | Target |
|---|---|---|---|
| **[[DSCR]]** (Debt Service Coverage Ratio) | $\frac{\text{NOI}}{\text{Debt Service}}$ | Can the property's income cover its mortgage payments? | ≥ 1.2× |
| **[[LTV]]** (Loan-to-Value) | $\frac{\text{Loan Amount}}{\text{Appraised Value}}$ | How much of the property is financed with debt? | Lower = less risky |
| **[[Equity dividend rate]]** | $\frac{\text{NOI} - \text{Debt Service}}{\text{Equity}}$ | What cash return does the equity investor earn? | Higher = better |

#### Worked Example — Wallonia Transit Warehouse

**Given:**
- Property value = EUR 3,750,000
- Original mortgage = EUR 3,000,000 at 4% interest
- Annual mortgage payment = EUR 220,745
- First-year interest = EUR 120,000
- [[NOI]] = EUR 406,750

**Step 1: LTV after Year 1**

First, find remaining mortgage balance. [[Principal|Principal]] paid = Payment − Interest:

$$\text{Principal paid} = 220{,}745 - 120{,}000 = 100{,}745$$

$$\text{Remaining balance} = 3{,}000{,}000 - 100{,}745 = 2{,}899{,}255$$

$$\text{LTV} = \frac{2{,}899{,}255}{3{,}750{,}000} = 0.773 = 77.3\%$$

**Step 2: [[DSCR]]**

$$\text{DSCR} = \frac{406{,}750}{220{,}745} = 1.84$$

> [!success] Interpretation
> A [[DSCR]] of 1.84 means the property generates 84% more income than needed to cover debt payments — a comfortable cushion.

#### Leveraged vs. Unleveraged [[IRR]]

| | Leveraged IRR | Unleveraged IRR |
|---|---|---|
| **PV (initial outflow)** | −Equity (down payment) | −Full purchase price |
| **PMT (periodic cash flow)** | NOI − Debt Service | NOI |
| **FV (terminal cash flow)** | Sale price − Mortgage balance | Sale price |
| **N** | Holding years | Holding years |
| **Solve for** | I/Y | I/Y |

> [!question] Why does leverage amplify returns?
> When you borrow to buy a property, you control a larger asset with less of your own money. If the property appreciates, your return on *your* money is magnified. But this works both ways — if the property loses value, your losses are also amplified.

---

## LOS (b): The [[Real Estate Cycle]] — Four Phases

The [[real estate cycle]] reflects the health and direction of the property market. Understanding where you are in the cycle is critical for investment timing.

| Phase | What's Happening | Key Indicators |
|---|---|---|
| **1. Recovery** | Trough — economy stabilizing after downturn | Low construction, tight credit, high vacancy, uncertain outlook |
| **2. [[Expansion|Expansion]]** | Growth — demand picking up | [[Economic growth|Economic growth]], easing credit, rising prices, new construction begins |
| **3. Oversupply** | Peak/decline — too much new supply | Slowing growth, property glut, falling rents and prices |
| **4. [[Recession|Recession]]** | [[Contraction|Contraction]] — market correction | Economic slowdown, tight credit, construction halts, prices at lows |

> [!important] Risk-Return Spectrum
> | Strategy | Risk | Return Target | Leverage | Description |
> |---|---|---|---|---|
> | **Core** | Low | Modest | Low | Stabilized, high-quality properties in prime locations |
> | **Core Plus** | Low-Medium | Moderate | Moderate | Core properties with minor value-add potential |
> | **Value-Add** | Medium-High | Higher | Higher | Properties needing renovation, re-leasing, or repositioning |
> | **Opportunistic** | High | Highest | Highest | Development, distressed assets, major repositioning |

---

## LOS (c): Commercial Property Types

| Property Type | Key Feature | Lease Structure | [[Risk factors|Risk Factors]] |
|---|---|---|---|
| **Residential (Multi-family)** | Short lease terms (typically 1 year) | Gross leases (landlord pays most expenses) | Most stable demand; affected by demographic trends |
| **Office** | Long leases (5–10+ years) | Net leases (tenant pays many expenses) | Remote work trends; high tenant improvement costs |
| **Industrial/Warehouse** | Simple structures, low maintenance | Net leases, long-term | E-commerce growth is a tailwind; location near transportation |
| **Retail** | Location is everything | Percentage rent (base + % of sales) | E-commerce disruption; anchor tenant risk |
| **Hotel/Hospitality** | "Nightly lease" — maximum revenue flexibility | No traditional lease — nightly rates | Most volatile; highly cyclical; labor-intensive |
| **Mixed-Use** | Combines multiple types | Varies | [[Diversification]] within a single property |

---

## LOS (d): Due Diligence and Valuation Approaches

### Due Diligence Process

Before acquiring a property, investors conduct thorough [[Due diligence|due diligence]] across six areas:

1. **Market Review and Outlook:** Assess current prices, economic uses, demand/supply changes, macro factors
2. **Current Lease Review:** Tenant rents/creditworthiness, market rents, vacancies, lease length
3. **Future Lease Outlook:** Costs/incentives for renewals, re-leasing challenges, zoning/legal changes
4. **Financial Review:** Analyze historical financials — is current [[NOI]] sustainable?
5. **Documentation Review:** Ensure property is free of liens, tax obligations, compliant with zoning and environmental regulations
6. **Property Inspection:** Comprehensive physical/engineering/environmental survey; review service agreements

### Three Valuation Approaches

#### Approach 1: Income Approach — [[Direct capitalization method]]

Uses a single year's [[NOI]] to estimate value, treating the income as a [[Perpetuity]]:

$$\text{Property Value} = \frac{\text{Expected NOI}}{\text{Capitalization Rate}}$$

Where the [[Cap rate]] combines the [[Required rate of return]] ($r$) with an implied constant growth rate ($g$):

$$\text{Cap Rate} = r - g$$

> [!tip] Analogy
> This is like the [[Gordon Growth Model]] for stocks: $P = \frac{D}{r - g}$. The property is the "stock," [[NOI]] is the "dividend," and the [[Cap rate]] is $(r - g)$.

> [!important] When to Use
> Most appropriate for properties that generate **[[Consistent|consistent]]** [[NOI]]. If NOI is expected to change significantly, project a **normalized** or **stabilized** NOI instead.

**Going-in [[Cap rate|cap rate]]** = Based on the first year of ownership (uses initial annual cash flow)
**[[Terminal cap rate]]** = Based on expected income for the period after anticipated sale (typically **higher** than going-in [[Cap rate|cap rate]] because older properties may not be as competitive)

##### Worked Example — Wallonia Transit (Direct Capitalization)

**Given:** [[NOI]] = EUR 406,750; Required return ($r$) = 12.5%; Growth ($g$) = 2%

$$\text{Property Value} = \frac{406{,}750}{0.125 - 0.02} = \frac{406{,}750}{0.105} = \text{EUR } 3{,}873{,}810$$

If service/repair costs rise 20% and [[NOI]] falls to EUR 382,600:

$$\text{Property Value} = \frac{382{,}600}{0.105} = \text{EUR } 3{,}643{,}810$$

> [!warning] The lower NOI reduces estimated property value by 6%.

#### Approach 1b: Income Approach — [[DCF Method]]

More appropriate when the analyst has greater [[Visibility|visibility]] into [[NOI]] dynamics:

$$\text{Property Value} = \sum_{i=1}^{n} \frac{\text{NOI}_{t+i}}{(1+r)^i} + \frac{\text{Terminal Value}}{(1+r)^n}$$

Where:

$$\text{Terminal Value} = \frac{\text{NOI}_n \times (1+g)}{r - g}$$

> [!question] Going-in [[Cap rate|Cap Rate]] vs. Terminal [[Cap rate|Cap Rate]]
> - **Going-in cap rate:** Used to value the property at purchase — reflects current market conditions and the first year's cash flow
> - **[[Terminal cap rate]]:** Used to estimate the property's sale price at the end of the holding period — typically **higher** than the going-in rate because the building is older and may face more competition

#### Approach 2: Cost Approach

$$\text{Value} = \text{Land Value} + \text{Building Replacement Cost} - \text{Depreciation} - \text{Obsolescence}$$

> [!tip] When to Use
> Useful when comparing cost of new construction to [[Market value|market value]]. Investors should not pay more than the cost of vacant land + development of a comparable property.

##### Worked Example — Cost Approach

**Given:** Construction cost of identical building = USD 57M; Land value = USD 7M; Total [[Depreciation|depreciation]] = USD 5M

$$\text{Value} = 57{,}000{,}000 + 7{,}000{,}000 - 5{,}000{,}000 = \text{USD } 59{,}000{,}000$$

#### Approach 3: Sales Comparison Approach

A relative [[Valuation|valuation]] approach — compare recent sales prices of **similar properties** and adjust for differences. Similar to using [[P/E ratio|multiples]] in [[Equity Valuation]].

> [!tip] When to Use
> Most reliable in markets with **frequent transactions** of similar properties (e.g., single-family residential). Less useful for unique or rarely-traded commercial properties.

> [!abstract] Best Practice
> Consider **multiple [[Valuation|valuation]] methods** for a comprehensive analysis. Different methods will give different answers — an analyst should examine assumptions to understand why.

---

## LOS (e): Real Estate Investment Indexes

### Types of Indexes

#### 1. Appraisal-Based Indexes (e.g., [[NCREIF]], [[GREFI]])

- Based on **appraised values** of properties, not actual transactions
- Properties are appraised periodically (quarterly or annually)

$$\text{NCREIF Holding Period Return} = \frac{\text{NOI} - \text{Capex} + (\text{Ending MV} - \text{Beginning MV})}{\text{Beginning Market Value}}$$

> [!warning] Appraisal Smoothing Bias
> Appraisals tend to **lag** actual market conditions because appraisers rely partly on previous valuations. This creates artificially:
> - **Lower reported [[Volatility]]** (prices look smoother than reality)
> - **Lower reported [[Correlation]]** with other asset classes
> - **Overstated [[Sharpe ratio|Sharpe ratios]]**

##### The Unsmoothing Formula

To correct for [[appraisal smoothing]], analysts "unsmooth" the returns:

$$R_t^* = \frac{R_t - \alpha \cdot R_{t-1}}{1 - \alpha}$$

Where:
- $R_t^*$ = unsmoothed (true) return
- $R_t$ = reported (smoothed) return
- $R_{t-1}$ = previous period's reported return
- $\alpha$ = smoothing [[Parameter|parameter]] (typically estimated from data)

> [!important] After unsmoothing, true [[Volatility|volatility]] is **higher** and true correlations with other asset classes are **higher** than the raw appraisal-based data suggests. This means the [[diversification]] benefit of [[Real estate|real estate]] is **overstated** by raw appraisal indexes.

#### 2. Transaction-Based Indexes

- **Repeat Sales Index:** Uses data only from properties that have sold **more than once** — measures price changes between sales of the same property
- **Hedonic Index:** Uses regression to control for differences in property characteristics (size, location, age, quality) — can use all transactions, not just repeat sales

#### 3. Public Market Indexes (e.g., [[FTSE NAREIT]], [[S&P REIT]])

- Based on traded [[REIT]] share prices
- Real-time pricing, highly liquid
- But: contaminated by stock market sentiment, so short-term [[Correlation]] with equities is high

---

## Key Formulas Summary

| Formula | Expression |
|---|---|
| [[NOI]] | $\text{EGI} - \text{Operating Expenses} - \text{Maintenance Allowance}$ |
| [[Direct capitalization method]] | $\text{Value} = \frac{\text{NOI}}{r - g}$ |
| [[DCF Method]] | $\text{Value} = \sum \frac{\text{NOI}_{t+i}}{(1+r)^i} + \frac{TV}{(1+r)^n}$ |
| [[Terminal value]] | $TV = \frac{\text{NOI}_n(1+g)}{r - g}$ |
| [[Cost approach|Cost Approach]] | $\text{Land} + \text{Replacement Cost} - \text{Depreciation}$ |
| [[DSCR]] | $\frac{\text{NOI}}{\text{Debt Service}}$ |
| [[LTV]] | $\frac{\text{Loan Amount}}{\text{Appraised Value}}$ |
| [[Equity dividend rate]] | $\frac{\text{NOI} - \text{Debt Service}}{\text{Equity}}$ |
| [[NCREIF]] HPR | $\frac{\text{NOI} - \text{Capex} + \Delta\text{MV}}{\text{Beginning MV}}$ |
| Unsmoothing | $R_t^* = \frac{R_t - \alpha R_{t-1}}{1 - \alpha}$ |

---

*See also: [[Real Estate - Public Securities (REITs, REOCs, NAVPS)]] | [[Commodities and Commodity Derivatives]] | [[Hedge Fund Strategies]]*
