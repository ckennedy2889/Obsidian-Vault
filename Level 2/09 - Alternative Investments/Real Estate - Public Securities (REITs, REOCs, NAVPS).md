# Real Estate — Public Securities (REITs, REOCs, NAVPS)

> [!info] CFA L2 — [[Alternative investments|Alternative Investments]] | Module 3
> **Investments in [[Real estate|Real Estate]] through Publicly Traded Securities**
> Source: CFA Program Curriculum 2025 Level 2, Volume 8

---

## LOS (a): Types of Publicly Traded Real Estate Securities

Think of publicly traded [[Real estate|real estate]] securities as **ways to own a slice of buildings and properties without having to buy an entire building yourself** — like buying a share of a pizza instead of the whole pie.

There are three main types:

### 1. Real Estate Investment Trusts ([[REIT]])

A [[REIT]] is a company that owns, operates, and sometimes develops income-producing [[Real estate]] (think office buildings, malls, apartments, warehouses). It's structured as a special tax-advantaged entity.

> [!question] Why do REITs exist?
> Before [[REIT|REITs]], only wealthy people and big institutions could invest in [[Real estate]]. The US Congress created REITs in 1960 so that ordinary investors could pool their money and get access to large-scale, professionally managed [[Real estate|real estate]] — much like a [[Mutual fund]], but for properties instead of stocks.

There are two sub-types:

- **[[Equity REIT|Equity REITs]]** own and operate actual [[Real estate|real estate]]. Their income comes from collecting rent.
- **[[Mortgage REIT|Mortgage REITs]]** don't own buildings — they make or invest in *loans* secured by real estate. Their income comes from interest on those loans.

> [!important] Key REIT Requirements
> - Must distribute **90–100% of [[Taxable income|taxable income]]** as [[dividends]] to shareholders. *Why?* This is the trade-off for their tax advantage — they avoid corporate-level income tax, but they must pass nearly all earnings through to investors.
> - Must invest at least **75% of assets** in [[Real estate]].
> - Must derive at least **75% of income** from rental income or [[mortgage]] interest.
> - In the US: must have at least 100 shareholders, and no 5 or fewer shareholders can own more than 50% of shares (the **"5/50 rule"**). *Why?* To prevent a single person or small group from creating a private tax shelter disguised as a REIT.

Most US [[REIT|REITs]] are **self-managed** (executives are employees of the REIT). **Externally managed** REITs hire third-party advisers, which can create [[conflicts of interest]] — the adviser may want to grow the fund (more fees) rather than maximize shareholder value.

### 2. Real Estate Operating Companies ([[REOC]])

A [[REOC]] is an **ordinary, taxable** real estate company. Think of it as a [[REIT]] without the tax break but with more freedom.

> [!question] Why would a company be a REOC instead of a REIT?
> - Their country doesn't have a REIT tax structure.
> - They do a lot of **development-for-sale** (build and flip), which [[REIT|REITs]] can't do extensively.
> - They offer services like [[Brokerage|brokerage]] or third-party property management that don't qualify under REIT rules.

Because [[REOC|REOCs]] aren't required to distribute income, they can **reinvest cash flows** into growth — giving them more operating flexibility but subjecting them to [[double taxation]] (corporate tax + investor tax on [[dividends]]).

### 3. Mortgage-Backed Securities ([[MBS]])

These are **debt instruments**, not equity. They represent claims on cash flows from pools of [[mortgage]] loans. [[RMBS]] (residential) pools can contain thousands of loans; [[CMBS]] (commercial) pools are smaller, sometimes as few as one loan.

---

## LOS (b): Net Asset Value Per Share ([[NAVPS]]) — Justification and Estimation

### Why Use NAVPS Instead of [[Book value]]?

**[[Book value per share]] (BVPS)** is based on [[Historical cost|historical cost]] accounting. Here's the problem: imagine you bought a downtown office building in 1990 for \$5 million. On the books (under [[US GAAP]]), it's been depreciated down to maybe \$2 million. But today it's actually worth \$25 million. [[Book value]] is wildly misleading for [[Real estate]] because:

1. Real estate often **appreciates** over time, but accounting [[Depreciation]] keeps grinding the [[Book value|book value]] down.
2. [[Accelerated depreciation]] further understates carrying values.

**[[NAVPS]]** fixes this by using **market values** for everything — what the properties are actually worth today, not what someone paid for them years ago.

> [!tip] Analogy
> [[Book value]] is like judging how much your house is worth based on what your grandparents paid for it minus "wear and tear." [[NAVPS]] is like asking a real estate agent what it would sell for today.

> [!important] Key Point
> Shares priced **below** [[NAVPS]] suggest potential **undervaluation** (you're buying the real estate for less than it's worth). Shares priced **above** NAVPS suggest potential **overvaluation**. But premiums/discounts can be justified by management quality, [[Leverage]], governance, or market outlook.

### The NAVPS Calculation — Step by Step

$$\text{NAVPS} = \frac{\text{Net Asset Value}}{\text{Shares Outstanding}}$$

Where NAV is built up as follows:

| Step | Item |
|---|---|
| Start with | Last-12-month real estate [[NOI]] |
| − | Non-cash rents |
| + | Adjustment for full impact of acquisitions |
| = | **Pro forma cash NOI for last 12 months** |
| + | Next-12-month growth in [[NOI]] |
| = | **Estimated next-12-month cash NOI** |
| ÷ | Assumed [[Cap rate]] |
| = | **Estimated value of operating real estate** |
| + | Cash & [[Cash equivalents|cash equivalents]] |
| + | Land held for future development |
| + | [[Accounts receivable|Accounts receivable]] |
| + | Prepaid / other assets |
| = | **Estimated gross asset value** |
| − | Total debt |
| − | Other [[Liabilities|liabilities]] |
| = | **[[Net asset value|Net Asset Value]] (NAV)** |
| ÷ | Shares outstanding |
| = | **[[NAVPS]]** |

### What Each Piece Is and Why It's There

**[[NOI]] ([[Net operating income|Net Operating Income]]):** The property's income after paying [[operating expenses]] (property taxes, insurance, repairs, utilities, management) but *before* paying interest on debt, income taxes, or [[Depreciation]]. It's the most fundamental measure of how much cash a property generates.

$$\text{NOI} = \text{Gross Rental Revenue} - \text{Vacancy/Collection Loss} - \text{Operating Expenses}$$

> [!question] Why subtract non-cash rents?
> Under accounting rules, when a lease says rent starts at \$10/month and rises to \$14/month over 5 years, accountants record the *average* (\$12/month) every year — this is called **"straight-line" rent**. But the tenant isn't actually paying \$12 in year 1; they're paying \$10. We want *cash* [[NOI]], so we remove the non-cash portion.

> [!question] Why add the full-year impact of acquisitions?
> If you bought a building halfway through the year, your reported [[NOI]] only captures 6 months of income from it. We "annualize" it so our NOI reflects what a full year looks like going forward.

> [!question] Why grow NOI forward?
> We're trying to value the property based on *next year's* expected income, not last year's. It's like valuing a stock based on [[forward earnings]], not [[trailing earnings]].

### The [[Cap rate]] ($r_{cap}$)

This is the *market-required [[Current yield|current yield]]* on the property — what return investors demand from a property's income stream given its risk level. It's derived from observing what similar properties actually sold for in the market:

$$r_{cap} = \frac{\text{NOI}}{\text{Property Value}} \quad \Rightarrow \quad \text{Property Value} = \frac{\text{NOI}}{r_{cap}}$$

*Why?* A higher [[Cap rate]] means investors demand more income per dollar of property value (they view the property as riskier), which means the property is worth *less*. A lower [[Cap rate|cap rate]] means investors accept less income (they view it as safer/high-growth), making the property worth *more*.

> [!tip] Analogy
> The [[Cap rate]] is like a [[P/E ratio]] flipped upside down. A low [[Cap rate|cap rate]] = high "P/E" = expensive property (investors are paying a premium). A high [[Cap rate|cap rate]] = low "P/E" = cheap property.

> [!question] Why exclude goodwill, [[Deferred tax assets|deferred tax assets]], deferred financing expenses?
> These are "soft" or [[Intangible assets|intangible assets]] — they don't represent hard economic value you could actually sell. We want a "hard" NAV.

> [!question] Why exclude [[Deferred tax liabilities|deferred tax liabilities]]?
> [[Deferred taxes]] are an accounting provision, not a real economic liability that must be paid right now. Since we're estimating what the assets are *worth*, we strip out these accounting artifacts.

### Worked Example — NAVPS Calculation (Curriculum Exhibit 2)

**Given data for a [[REIT]]:**
- Last-12-month [[NOI]] = \$270,432
- [[Non-cash rent|Non-cash rent]] = \$7,667
- [[Acquisition|Acquisition]] adjustment = \$4,534
- NOI growth rate = 1.5%
- [[Cap rate]] = 7.00%
- Other assets: Cash = \$65,554; Land = \$34,566; AR = \$45,667; Prepaid = \$23,456
- Total debt = \$1,010,988; Other liabilities = \$119,886
- Shares outstanding = 55,689

**Step 1: Pro forma cash NOI**

$$270{,}432 - 7{,}667 + 4{,}534 = \$267{,}299$$

We removed the [[Non-cash rent|non-cash rent]] (getting to actual cash received) and added the full-year effect of mid-year acquisitions.

**Step 2: Estimated next-12-month cash NOI**

$$267{,}299 \times (1 + 0.015) = 267{,}299 \times 1.015 = \$271{,}308$$

We grew it forward by 1.5% because we want to value based on expected future income.

**Step 3: Value of operating real estate**

$$\frac{271{,}308}{0.07} = \$3{,}875{,}829$$

Dividing by the [[Cap rate]] converts the income stream into a lump-sum property value. Think of it like: "If this property yields 7% per year, how much would I need to invest to generate \$271,308 per year? Answer: \$3.875 million."

**Step 4: Estimated gross asset value**

$$3{,}875{,}829 + 65{,}554 + 34{,}566 + 45{,}667 + 23{,}456 = \$4{,}045{,}072$$

We add all the other tangible assets the [[REIT]] owns.

**Step 5: [[Net asset value|Net Asset Value]]**

$$4{,}045{,}072 - 1{,}010{,}988 - 119{,}886 = \$2{,}914{,}198$$

Subtract all the real (hard) [[Liabilities|liabilities]].

**Step 6: [[NAVPS]]**

$$\frac{2{,}914{,}198}{55{,}689} = \$52.33$$

> [!success] Interpretation
> On a per-share basis, the [[Underlying|underlying]] [[Real estate]] is worth about **\$52.33**. If the stock trades at \$48, the market is pricing it at a **discount** to NAV (potentially undervalued). If at \$58, it's at a **premium**.

### Important NAV Caveats

- **NAV treats the [[REIT]] as a static pool of assets.** In reality, management can add or subtract value by buying/selling properties, making smart (or dumb) capital allocation decisions. NAV doesn't capture this [[Going-concern value|going-concern value]].
- **NAV uses private market [[Comparables|comparables]].** Since the [[Cap rate|cap rates]] and price-per-square-foot figures come from private market transactions, NAV reflects what a *private buyer* would pay — which may differ from what public stock market investors value the company at.
- **NAV can be subjective** in illiquid markets, for undeveloped land, or for unique properties with few [[Comparables|comparables]].

---

## LOS (c): Funds from Operations ([[FFO]]) and Adjusted Funds from Operations ([[AFFO]])

### Why Do We Need FFO?

Regular [[GAAP]] **[[Net income]]** is a poor measure of a [[REIT]]'s true economic performance because of two big distortions:

1. **[[Depreciation]] of real estate:** Accounting rules force REITs to depreciate buildings over time. But real estate often *appreciates*, so this [[Depreciation|depreciation]] charge doesn't reflect economic reality. It makes the REIT look less profitable than it really is.
2. **Gains/losses on property sales:** When a REIT sells a property it bought 20 years ago for a big gain, that's a one-time windfall — not representative of ongoing earning power.

[[FFO]] strips both of these out to get a cleaner picture of recurring operating performance.

### FFO Formula

$$\boxed{FFO = \text{Net Income} + \text{Depreciation \& Amortization} - \text{Net Gains on Sale of Real Property}}$$

**In plain English:** Start with [[Net income]]. Add back the [[Depreciation]]/[[amortization]] (because it's a non-cash charge that doesn't reflect economic reality for real estate). Then remove any gains from selling properties (because those are one-time, not sustainable).

**What each variable captures:**
- **[[Net income]]:** The accounting bottom line — includes [[Depreciation|depreciation]] and gains/losses that distort [[REIT]] performance.
- **+ [[Depreciation]] & [[Amortization]]:** Added back because buildings don't actually lose value the way a machine does. The amortization includes leasing commissions and tenant improvement costs that were capitalized.
- **− Net gains on sale of property:** Removed because selling a building for a profit doesn't represent *ongoing* income you can count on next year.

### AFFO Formula

$$\boxed{AFFO = FFO - \text{Non-cash (Straight-line) Rent} - \text{Recurring Maintenance Capex}}$$

**In plain English:** Start with [[FFO]], then subtract two more things that FFO misses: (1) the "phantom" rent that accountants book but tenants haven't actually paid yet, and (2) the money the [[REIT]] *must* spend to keep its buildings in good shape and keep tenants happy.

**What each adjustment captures:**
- **− Non-cash (straight-line) rent:** If accounting says you earned \$12M in rent but tenants only paid \$10M in cash, the \$2M difference is non-cash. We remove it because we want to know actual cash earnings.
- **− Recurring maintenance [[capex]]:** Things like roof repairs, parking lot repaving, tenant buildouts, leasing commissions. These are costs the REIT *must* incur to maintain rental income. [[FFO]] ignores them, making it look too generous.

> [!important] Why AFFO > FFO as an Economic Measure
> [[AFFO]] is superior to [[FFO]] as a measure of economic income because it accounts for the [[capital expenditures]] necessary to maintain the property portfolio's earning power. It also better approximates the [[REIT]]'s **sustainable dividend-paying capacity** — how much it can actually afford to pay out as [[dividends]] without running its properties into the ground.
>
> However, AFFO is **harder to estimate** and more subjective because the "right" amount of recurring capex varies by analyst and company. That's why FFO (standardized by [[Nareit]]) is more commonly reported.

### Worked Example — Calculating FFO from AFFO

**Given:**
- [[AFFO]] = \$4,000,000
- AFFO per share = \$5.00
- [[Non-cash rent|Non-cash rent]] = \$215,000
- Recurring maintenance [[capex]] = \$700,000

**Step 1: Find [[FFO]]** (rearrange the AFFO formula)

Since $AFFO = FFO - \text{Non-cash rent} - \text{Recurring capex}$, we get:

$$FFO = AFFO + \text{Non-cash rent} + \text{Recurring capex}$$

$$FFO = 4{,}000{,}000 + 215{,}000 + 700{,}000 = \$4{,}915{,}000$$

**Step 2: Find shares outstanding**

$$\text{Shares} = \frac{AFFO}{AFFO/\text{share}} = \frac{4{,}000{,}000}{5.00} = 800{,}000$$

**Step 3: FFO per share**

$$\frac{4{,}915{,}000}{800{,}000} = \$6.14$$

---

## LOS (d): REIT Valuation — Three Approaches

### Approach 1: Net Asset Value ([[NAVPS]])

Already covered above. You calculate what the [[Underlying|underlying]] properties are worth, subtract debts, divide by shares.

### Approach 2: Relative Value (P/FFO and P/AFFO)

This is the [[REIT]] equivalent of using a [[P/E ratio]] for regular stocks. The idea: "How much are investors paying per dollar of [[FFO]] (or [[AFFO]]) generated by this REIT, and how does that compare to its peers?"

**P/FFO Approach:**

$$\text{Value per share} = \frac{FFO}{\text{Shares outstanding}} \times \text{Sector average P/FFO multiple}$$

$$= \text{FFO per share} \times \text{P/FFO multiple}$$

**P/AFFO Approach:**

$$\text{Value per share} = \text{AFFO per share} \times \text{P/AFFO multiple}$$

Where:

$$\text{AFFO per share} = \frac{FFO - \text{Non-cash rents} - \text{Recurring maintenance capex}}{\text{Shares outstanding}}$$

> [!question] Why use a sector average multiple?
> You compare the [[REIT]] to peers that own similar property types (office vs. office, mall vs. mall). This controls for differences in risk profiles across property types.

**What drives higher multiples?**
1. **Higher expected growth** in [[FFO]]/[[AFFO]] → higher multiple (just like high-growth stocks get higher [[P/E ratio|P/E ratios]])
2. **Lower risk** → higher multiple. Apartments have more stable cash flows than hotels, so apartment [[REIT|REITs]] trade at higher multiples.
3. **Lower [[Leverage]]** → higher multiple. More debt = more risk = investors demand higher returns = lower price per dollar of FFO.

### Worked Example — P/FFO (REIT B from Exhibit 1)

**Given:**
- [[FFO]] = \$290,612
- Shares outstanding = 67,900
- Property subsector average P/FFO multiple = 13.5×

**Step 1: FFO per share**

$$\frac{290{,}612}{67{,}900} = \$4.28$$

**Step 2: Apply the multiple**

$$\$4.28 \times 13.5 = \$57.78$$

> [!success] Result
> The estimated value per share using the P/FFO approach is **\$57.78**.

### Worked Example — P/AFFO (REIT A from Exhibits 1 & 2)

**Given:**
- [[FFO]] = \$316,965
- Non-cash rents = \$25,991
- Recurring maintenance [[capex]] = \$63,769
- Shares outstanding = 56,100
- Property subsector average P/AFFO multiple = 18.3×

**Step 1: Calculate [[AFFO]]**

$$AFFO = 316{,}965 - 25{,}991 - 63{,}769 = \$227{,}205$$

**Step 2: AFFO per share**

$$\frac{227{,}205}{56{,}100} = \$4.05$$

**Step 3: Apply the multiple**

$$\$4.05 \times 18.3 = \$74.12$$

> [!success] Result
> The estimated value per share using P/AFFO is **\$74.12**.

### Approach 3: Discounted Cash Flow ([[Dividend discount model]])

Because [[REIT|REITs]] must pay out 90%+ of income as [[dividends]], they are natural candidates for a **[[Dividend discount model]] (DDM)**. This works exactly like DDMs you've seen for regular stocks.

**The idea:** The value of a [[REIT]] share = the [[present value]] of all future [[dividends]] you expect to receive.

For the CFA exam, a **two- or three-step DDM** is typically used:

$$V_0 = \sum_{t=1}^{n} \frac{D_t}{(1+r)^t} + \frac{D_{n+1}}{(r - g_L)} \times \frac{1}{(1+r)^n}$$

Where:
- $V_0$ = value of the [[REIT]] share today
- $D_t$ = expected [[dividends|dividend]] in year $t$
- $r$ = [[Required rate of return]] on equity ([[Cost of equity]])
- $g_L$ = long-term sustainable dividend growth rate (used for the [[Terminal value]])
- $n$ = number of years in the high/transition growth phase

**In plain English:** For the first few years, you project each dividend individually and [[Discount rate|discount]] it back to today. After that, you assume dividends grow at a constant long-term rate forever, and you use the [[Gordon Growth Model]] to get a [[Terminal value]], which you also discount back to today.

### Worked Example — DCF/DDM (REIT C from Exhibit 2)

**Given:**
- $D_1 = \$4.00$ (expected dividend next year)
- Growth rate in Years 2 and 3 = 4.5%
- Growth rate after Year 3 ([[Perpetuity|perpetuity]]) = 4.0%
- [[Cost of equity]] = 8%

**Step 1: Project dividends**

$$D_1 = \$4.00$$

$$D_2 = 4.00 \times 1.045 = \$4.18$$

$$D_3 = 4.18 \times 1.045 = \$4.37$$

**Step 2: [[Terminal value]] at end of Year 3**

After Year 3, dividends grow at 4.0% forever. The next dividend ($D_4$) is:

$$D_4 = 4.37 \times 1.04 = \$4.54$$

[[Terminal value|Terminal value]] (at end of Year 3, using the [[Gordon Growth Model]]):

$$TV_3 = \frac{D_4}{r - g_L} = \frac{4.54}{0.08 - 0.04} = \frac{4.54}{0.04} = \$113.58$$

**Step 3: Discount everything back to today**

$$V_0 = \frac{4.00}{1.08^1} + \frac{4.18}{1.08^2} + \frac{4.37 + 113.58}{1.08^3}$$

$$V_0 = \frac{4.00}{1.08} + \frac{4.18}{1.1664} + \frac{117.95}{1.2597}$$

$$V_0 = 3.70 + 3.58 + 93.63 = \$100.91$$

> [!success] Result
> The estimated value per share using the DDM is **\$100.91**.
> Notice how the [[Terminal value]] dominates — that's normal. The vast majority of a [[REIT]]'s value comes from the long-term stream of dividends stretching into [[Perpetuity|perpetuity]].

### Advantages and Disadvantages of P/FFO and P/AFFO Multiples

> [!success] Advantages
> - Widely accepted and easily understood across global markets
> - [[FFO]] estimates are readily available from data providers (Bloomberg, Refinitiv)
> - Multiples can be combined with growth expectations and [[Leverage]] ratios for deeper analysis

> [!warning] Disadvantages
> - May miss the value of non-income-producing assets like undeveloped land or properties under development
> - P/FFO ignores recurring [[capex]] needed to maintain properties
> - One-time items and accounting changes can distort [[FFO]] and complicate peer comparisons

---

## LOS (e): Advantages and Disadvantages — Public vs. Private Real Estate

This is about the trade-offs between investing in [[Real estate]] via publicly traded securities ([[REIT|REITs]]/[[REOC|REOCs]]) versus buying property directly or through [[Private equity|private funds]].

### Public Real Estate (REITs/REOCs)

> [!success] Advantages
> - **[[Liquidity|Liquidity]]:** Buy and sell shares on stock [[Exchanges|exchanges]] any time
> - **Professional management** with [[Economies of scale|economies of scale]]
> - **[[Tax efficiency|Tax efficiency]]:** [[REIT|REITs]] avoid [[double taxation]] (corporate + investor level). Income is taxed only once, at the investor level
> - **Low investment minimums:** You can invest with just the price of one share
> - **[[Diversification]]:** Access to diversified portfolios across property types and geographies
> - **[[Transparency|Transparency]] and regulation:** Public disclosure requirements, readily available prices
> - **[[Limited liability]]:** You can only lose what you invested

> [!warning] Disadvantages
> - **Higher [[Volatility]]** than private [[Real estate]] because stock prices swing with overall equity market sentiment
> - **High short-term [[Correlation]] with the stock market**, which reduces the [[diversification]] benefit
> - **REIT structure limits activities:** Can't retain earnings to reinvest, can't do certain types of development
> - **Stock price may not reflect [[Underlying|underlying]] property values** — can trade at premium or discount to [[NAVPS|NAV]]
> - **[[Dividends]] taxed at ordinary income rates** (in many jurisdictions), which may be higher than [[capital gains]] rates

### Private Real Estate

> [!success] Advantages
> - **Direct exposure** to [[Real estate]] [[Fundamentals|fundamentals]] (not contaminated by stock market noise)
> - **Low [[Correlation|correlations]]** with other asset classes, offering true [[diversification]]
> - **Stable returns / low reported [[Volatility]]** (partly because [[appraisal smoothing|appraisals]] smooth out fluctuations)
> - **Control** over the actual property
> - **Wide range of strategies** with fewer restrictions
> - **Potential [[Illiquidity premium]]:** You may earn higher returns because you're compensated for not being able to sell easily

> [!warning] Disadvantages
> - **Low [[Liquidity]]:** Hard to sell quickly, especially in downturns
> - **High fees and expenses**
> - **[[Appraisal smoothing|Appraisal-based valuations]] lag** actual market conditions
> - **High investment minimums** and high-net-worth requirements
> - **Low [[Transparency|transparency]]** and fewer regulations
> - **High returns often depend on [[Leverage]]** (using a lot of debt)

> [!abstract] Bottom Line
> Many [[Institutional investors|institutional investors]] allocate to *both* public and private [[Real estate]] because they serve complementary roles. Public [[REIT|REITs]] provide [[Liquidity]] and easy access; private real estate provides [[diversification]] benefits and an [[Illiquidity premium]]. Over the long term, both track real estate [[Fundamentals|fundamentals]], but they can diverge significantly in the short term due to stock market sentiment affecting public REIT prices.

---

## Key Formulas Summary

| Formula | Expression |
|---|---|
| [[NOI]] | $\text{Gross Rental Revenue} - \text{Vacancy Loss} - \text{OpEx}$ |
| [[Cap rate]] | $r_{cap} = \frac{\text{NOI}}{\text{Property Value}}$ |
| [[NAVPS]] | $\frac{\text{NAV}}{\text{Shares Outstanding}}$ |
| [[FFO]] | $\text{Net Income} + \text{D\&A} - \text{Net Gains on Sale}$ |
| [[AFFO]] | $FFO - \text{Non-cash Rent} - \text{Recurring Capex}$ |
| P/FFO Value | $\text{FFO/share} \times \text{P/FFO multiple}$ |
| P/AFFO Value | $\text{AFFO/share} \times \text{P/AFFO multiple}$ |
| [[DDM]] | $V_0 = \sum \frac{D_t}{(1+r)^t} + \frac{TV_n}{(1+r)^n}$ |
| [[Gordon Growth Model]] | $TV = \frac{D_{n+1}}{r - g_L}$ |

---

*See also: [[Real Estate - Private Investment and Valuation]] | [[Commodities and Commodity Derivatives]] | [[Hedge Fund Strategies]]*
