# Module 5: Residual Income Valuation

---

## Overview & The Big Idea

Imagine you lend your friend $100,000 to start a lemonade stand. At the end of the year, he proudly tells you: "Great news — we made $5,000 in profit!" But you think: "Wait... I could have put that $100,000 in an index fund and earned $10,000. You actually *destroyed* $5,000 of my wealth."

That's [[Residual income]] in a nutshell. Traditional accounting says "we're profitable!" but **[[Residual income|residual income]] asks: "Are we profitable *enough* to justify the capital shareholders invested?"**

Traditional [[Net income]] already deducts [[Interest Expense]] (the cost of borrowing from lenders), but it **never** deducts a charge for [[Equity Capital]] — the money shareholders put in. [[Residual income]] fixes this by subtracting an [[Equity charge]] — the minimum return shareholders *should* earn for the risk they're taking.

---

## LOS 21.a: Calculate and Interpret Residual Income, EVA, and MVA

### Residual Income (RI)

**What it is:** The profit left over *after* paying both your debt holders (interest) AND your equity holders (their [[Opportunity cost|opportunity cost]]).

**Formula:**

$$RI = \text{Net Income} - \text{Equity Charge}$$

Where the [[Equity charge]] = [[Book value of equity]] × [[Required Rate of Return on Equity]] ($r$)

$$RI = NI - (r \times B_{t-1})$$

**What each variable means and why it's there:**
- **$NI$** = [[Net income]]: The [[Accounting profit|accounting profit]] after interest and taxes. We start here because it's the "official" profit number.
- **$r$** = [[Cost of equity]]: The return shareholders *require* for bearing the risk of owning this stock (their [[Opportunity cost]]). Why? Because shareholders could invest their money elsewhere — we need to check if the company is beating that alternative.
- **$B_{t-1}$** = [[Book value of equity]] at the *beginning* of the period: This is the shareholders' investment in the company (assets minus [[Liabilities|liabilities]] on the [[Balance sheet]]). We use *beginning* [[Book value|book value]] because that's what was invested throughout the period to generate earnings.

**In plain words:** "How much did we earn beyond the minimum our shareholders demanded?"

> [!tip] Analogy
> Think of it like a landlord. Your building generates $50,000/year in rent ([[Net income]]). But the building is worth $500,000, and if you sold it and invested in the stock market, you'd expect 8% = $40,000/year ([[Equity charge]]). Your [[Residual income]] is $50,000 − $40,000 = **$10,000**. You're creating real wealth because you're beating your next-best alternative.

---

### Worked Example: Calculating Residual Income

**Madeira Fruit Suppliers (MFS):**
- Total assets: $1.4 billion
- [[Equity Capital]]: $800 million
- [[Debt Capital]]: $600 million
- [[Cost of equity]]: 12.3%
- [[Net income]]: $80,520,000

**Step 1:** Calculate the [[Equity charge]]

$$\text{Equity Charge} = r \times B_{t-1} = 0.123 \times \$800{,}000{,}000 = \$98{,}400{,}000$$

**Why:** This is the minimum profit shareholders expected. It represents what they *could have earned* investing their $800M elsewhere at a 12.3% return.

**Step 2:** Calculate [[Residual income]]

$$RI = NI - \text{Equity Charge} = \$80{,}520{,}000 - \$98{,}400{,}000 = -\$17{,}880{,}000$$

**Interpretation:** Even though MFS reported positive [[Net income]] of $80.5M (looks profitable!), it actually **destroyed shareholder value** by $17.9M. The company failed to earn enough to compensate shareholders for the risk they took. An accountant says "profitable." An economist says "value-destroying."

---

### Economic Value Added (EVA)

![[RI-vs-EVA-Comparison.excalidraw]]

[[EVA]] is a commercial (branded by Stern Stewart & Co.) version of [[Residual income]], but it operates at the **total capital** level (both debt + equity) instead of just equity.

$$EVA = NOPAT - (C\% \times TC)$$

**What each variable means:**
- **$NOPAT$** = [[Net Operating Profit After Taxes]]: Profits from operations *before* deducting interest. Why? Because EVA looks at ALL capital providers (debt AND equity), not just equity holders. So we use a profit number that hasn't yet paid the debt holders.
- **$C\%$** = [[WACC]] ([[Weighted average cost of capital|Weighted Average Cost of Capital]]al|Cost of Capital]]): The blended cost of ALL capital — both debt and equity, weighted by their proportions. Why? Because we're measuring whether the company beats the cost of ALL its funding sources.
- **$TC$** = [[Total Capital]]: The total amount of money invested by both debt and equity holders (*beginning* of year). Why? That's the total investment base that needs to be compensated.

> [!important] Key Distinction: RI vs. EVA
> **[[Residual income]]** uses [[Net income]] (after interest) and charges only for [[Equity Capital]] using [[Cost of equity]].
> **[[EVA]]** uses [[NOPAT]] (before interest) and charges for **all capital** (debt + equity) using [[WACC]].
> Both are measuring the same thing conceptually — **[[Economic profit|economic profit]]** — just from different vantage points.

**Common EVA Adjustments** (to make accounting numbers closer to economic reality):
- **R&D:** Capitalize and amortize (don't expense immediately) — why? R&D creates long-term value, not just a one-year cost
- **Deferred Taxes:** Eliminate; use only cash taxes — why? Deferred taxes are an accounting timing difference, not real economic cost
- **[[LIFO reserve|LIFO Reserve]]:** Add back to capital — why? [[LIFO]] understates [[Inventory|inventory]] value in inflationary periods
- **Operating Leases:** Treat as capital leases — why? They represent real financing obligations

---

### Worked Example: EVA and MVA

**VBM, Inc.:**
- [[NOPAT]]: $2,100
- [[WACC]]: 14.2%
- Invested capital (beginning of year): $18,000
- Invested capital (end of year): $21,000
- Stock price: $25/share, 800 shares outstanding
- [[Market value|Market value]] of long-term debt: $4,000

**Step 1:** Calculate the [[Capital charge|capital charge]]

$$\text{Capital Charge} = WACC \times TC = 0.142 \times \$18{,}000 = \$2{,}556$$

**Why beginning-of-year?** That's the capital that was *working* throughout the year to produce those profits.

**Step 2:** Calculate [[EVA]]

$$EVA = \$2{,}100 - \$2{,}556 = -\$456$$

**Interpretation:** VBM destroyed $456 of value. It didn't earn enough to cover the cost of ALL its capital.

**Step 3:** Calculate [[Market Value Added]] (MVA)

$$MVA = \text{Market Value of Company} - \text{Book Value of Total Capital}$$

$$\text{Market Value} = (\$25 \times 800) + \$4{,}000 = \$24{,}000$$

$$MVA = \$24{,}000 - \$21{,}000 = \$3{,}000$$

**Why end-of-year capital for MVA?** Because we're comparing [[Market value|market value]] at a point in time to the [[Book value|book value]] at that *same* point in time.

**What MVA tells us:** Despite the negative EVA this year, the market still values VBM at $3,000 above its [[Book value|book value]] — suggesting investors expect future value creation.

---

## LOS 21.b: Uses of Residual Income Models

[[Residual income]] models aren't just for stock [[Valuation|valuation]]. They serve three main purposes:

1. **Equity [[Valuation|Valuation]]:** Estimate the [[Intrinsic value]] of a stock — this is our primary focus
2. **Measuring Internal Corporate Performance:** Evaluate whether business divisions are creating value (did the electronics division earn above its [[Cost of capital|cost of capital]]?)
3. **Executive Compensation:** Tie bonuses to [[EVA]] or [[Residual income]] so managers are rewarded for creating *real* [[Economic profit|economic profit]], not just [[Accounting profit|accounting profit]]
4. **Goodwill [[Impairment|Impairment]] Testing:** Assess whether [[Goodwill]] on the [[Balance sheet|balance sheet]] is still justified

> [!example] Real World
> Coca-Cola has historically used [[EVA]]-based compensation. A division manager who grows revenue but earns below the [[Cost of capital|cost of capital]] would see *negative* EVA — and a smaller bonus. This aligns management incentives with shareholder interests better than using [[Net income]] alone.

---

## LOS 21.c: The Residual Income Valuation Model

### The Core Idea

The [[Residual income model]] says: **A stock's value = what shareholders already own ([[Book value]]) + the present value of all future wealth the company will create above the minimum required return.**

Think of it like buying a house:
- **[[Book value]]** = the current appraised value of the house (what you "own" today)
- **[[PV of Future Residual Income]]** = the premium or discount based on whether the house is in a neighborhood that's *improving* (positive RI) or *declining* (negative RI)

### General Residual Income Model

$$V_0 = B_0 + \sum_{t=1}^{\infty} \frac{E_t - r B_{t-1}}{(1+r)^t}$$

Or equivalently:

$$V_0 = B_0 + \sum_{t=1}^{\infty} \frac{(ROE_t - r) \times B_{t-1}}{(1+r)^t}$$

**What each variable means:**

| Variable | Name | What It Is | Why It's There |
|---|---|---|---|
| $V_0$ | [[Intrinsic value]] | [[Fair value|Fair value]] of stock today | This is what we're solving for |
| $B_0$ | Current [[Book value per share]] | Shareholders' equity ÷ shares outstanding | The "anchor" — what shareholders already own on paper |
| $E_t$ | Expected [[EPS]] in period $t$ | Forecasted [[Earnings per share|earnings per share]] | The [[Accounting profit|accounting profit]] we expect the company to generate |
| $r$ | [[Cost of equity]] | [[Required rate of return|Required rate of return]] | The [[Discount rate|discount rate]] AND the [[Hurdle rate|hurdle rate]] for the [[Equity charge|equity charge]] |
| $B_{t-1}$ | Beginning [[Book value per share]] | [[Book value|Book value]] at start of period $t$ | The equity base that generated earnings in period $t$ |
| $ROE_t$ | [[Return on Equity]] in period $t$ | $E_t / B_{t-1}$ | Measures how efficiently the company uses shareholders' capital |

**In plain words:** "The stock is worth its book value TODAY, plus the present value of every dollar of profit above and beyond what shareholders require, forever into the future."

### The [[Clean surplus relation]]

The model relies on a critical accounting identity:

$$B_t = B_{t-1} + E_t - D_t$$

**In plain words:** Ending [[Book value]] = Beginning Book Value + [[Earnings]] − [[Dividends]]

**Why this matters:** This equation ties together the [[Balance sheet]] and the [[Income statement]]. It says the only things that change [[Book value]] are (1) earning money and (2) paying out money. If items bypass the [[Income statement]] and go directly to equity (called [[Clean Surplus Violations]]), this relationship breaks, and our model becomes less reliable.

> [!tip] Analogy
> Think of [[Book value]] as your bank account balance. It goes up when you earn money ([[Earnings]]) and down when you spend it ([[Dividends]]). The [[Clean surplus relation]] says no money appears or disappears through a side door. If it does (like a mysterious deposit or withdrawal that doesn't show on your [[Income statement|income statement]]), the math gets messy.

---

### Forecasting Residual Income — Worked Example

**Delilah Cosmetics:**
- Current [[Book value per share]] ($B_0$): $6.00
- [[Cost of equity]] ($r$): 10%
- [[EPS]] Year 1 ($E_1$): $1.00
- [[EPS]] Year 2 ($E_2$): $1.25
- [[Dividend]] Year 1 ($D_1$): $0.40
- [[Dividend]] Year 2 ($D_2$): $0.40

**Step 1:** Calculate Year 1 [[Residual income]]

$$RI_1 = E_1 - r \times B_0 = \$1.00 - (0.10 \times \$6.00) = \$1.00 - \$0.60 = \$0.40$$

The company earned $1.00, but shareholders *required* $0.60 (10% of their $6.00 investment). The excess $0.40 is economic value creation.

**Step 2:** Calculate $B_1$ using the [[Clean surplus relation]]

$$B_1 = B_0 + E_1 - D_1 = \$6.00 + \$1.00 - \$0.40 = \$6.60$$

Why did book value grow? Because the company retained $0.60 of earnings (earned $1.00, paid out $0.40).

**Step 3:** Calculate Year 2 [[Residual income]]

$$RI_2 = E_2 - r \times B_1 = \$1.25 - (0.10 \times \$6.60) = \$1.25 - \$0.66 = \$0.59$$

Notice the [[Equity charge]] is higher in Year 2 ($0.66 vs. $0.60) because [[Book value]] grew — there's more capital invested, so the hurdle is higher.

---

### Value Recognition: RI vs. DDM vs. FCFE

A critical advantage of the [[Residual income model]]: **value is recognized earlier** compared to [[DDM]] or [[FCFE]] models.

**Why?** In a [[DDM]] or [[FCFE]] model, a huge chunk of the estimated value comes from the [[Terminal value]] — a number far in the future that's very uncertain. The [[Residual income model]] starts with [[Book value]] (a known, current number), which typically represents a large portion of total value. The future [[Residual income]] you're discounting is just the *incremental* value above book — a much smaller (and less uncertain) piece.

> [!example] Real World Comparison
> Imagine valuing Amazon in 2005 using a [[DDM]]. Amazon paid zero dividends, had negative [[Free cash flow|free cash flow]], and almost all value came from a [[Terminal value|terminal value]] 10+ years out — extremely uncertain. But with a [[Residual income model]], you start with Amazon's book value (known!) and only need to forecast the *excess* returns. Less of the value depends on guessing what happens in 2015+.

---

## LOS 21.d: Fundamental Determinants of Residual Income

The two **fundamental drivers** of [[Residual income]] are:

1. **[[ROE]] in excess of [[Cost of equity]]** ($ROE - r$): If the company earns 15% on equity but shareholders only require 10%, there's a 5% "spread" that creates value. The *wider* this spread, the more [[Residual income|residual income]].

2. **[[Earnings Growth Rate]]** ($g$): Faster growth means the equity base grows faster (through retained earnings), which amplifies future [[Residual income|residual income]] — but *only if* ROE > r. If ROE < r, faster growth actually *destroys more value* because you're reinvesting at below the cost of capital.

> [!warning] Critical Insight
> Growth only creates value when $ROE > r$. A company growing at 20% but earning ROE of 8% when the [[Cost of equity|cost of equity]] is 10% is like a lemonade stand that loses money on every cup — selling more cups doesn't help. You're reinvesting shareholders' money at returns *below* what they could get elsewhere.

---

## LOS 21.e: Residual Income and the Justified P/B Ratio

The [[Residual income model]] is most closely linked to the [[Price-to-Book Ratio]] ([[P/B Ratio]]):

| Condition | What Happens | Justified P/B |
|---|---|---|
| $ROE > r$ | Positive [[Residual income]]; company creates value | **P/B > 1** (stock worth more than book value) |
| $ROE = r$ | Zero [[Residual income]]; company just meets hurdle | **P/B = 1** (stock worth exactly book value) |
| $ROE < r$ | Negative [[Residual income]]; company destroys value | **P/B < 1** (stock worth less than book value) |

**Why?** The [[Residual income model]] says $V_0 = B_0 + PV(\text{future RI})$. If future RI is positive, $V_0 > B_0$, so $P/B > 1$. It's that simple.

> [!example] Real World
> Tech companies like Apple often trade at P/B ratios of 40x+ because their [[ROE]] far exceeds their [[Cost of equity]] — they generate enormous [[Residual income|residual income]] from brand, ecosystem lock-in, and intellectual property that doesn't show up in [[Book value]]. A declining coal company might trade at P/B < 1 because its ROE has fallen below its cost of equity — the market says its assets are worth more liquidated than as a going concern.

**[[Tobin's Q]]** is a related concept:

$$Q = \frac{\text{Market Value of Assets}}{\text{Replacement Cost of Assets}}$$

If $Q > 1$, the company is worth more alive than the cost to rebuild it — similar logic to P/B > 1 from positive residual income.

---

## LOS 21.f: Single-Stage (Constant-Growth) Residual Income Model

### The Formula

If we assume **constant [[ROE]]** and **constant [[Earnings Growth Rate]]** forever, the general model simplifies to:

$$V_0 = B_0 + \frac{ROE - r}{r - g} \times B_0$$

**What this formula is saying in plain words:** "The stock is worth its book value PLUS a premium (or discount) based on how much ROE exceeds (or falls short of) the [[Cost of equity|cost of equity]], scaled by how fast the company is growing."

**What each piece means:**

| Component | Meaning | Why It's There |
|---|---|---|
| $B_0$ | Current [[Book value per share]] | The baseline — what shareholders own today |
| $ROE - r$ | The "spread" | If ROE > r, the company is creating value; this is the *engine* of residual income |
| $r - g$ | [[Capitalization rate|Capitalization rate]] | Converts a growing stream of RI into a present value (same logic as [[Gordon Growth Model]]: the wider the gap between required return and growth, the lower the PV multiplier) |
| $\frac{ROE - r}{r - g} \times B_0$ | PV of all future [[Residual income]] | The total premium above book value that the stock deserves |

> [!important] This IS the Gordon Growth Model in Disguise
> If you use the same inputs (same ROE, same $g$, same $r$), this formula gives you the **exact same answer** as the [[Gordon Growth Model]] ($V_0 = D_1 / (r - g)$). They're mathematically equivalent — just framed differently.

---

### Worked Example: Single-Stage RI Model

**Western Atlantic Railroad:**
- $B_0$ = $23.00 per share
- [[ROE]] = 14%
- $r$ ([[Cost of equity]]) = 12%
- [[Dividend payout ratio]] = 60%

**Step 1:** Calculate the [[Sustainable growth rate]] ($g$)

$$g = ROE \times (1 - \text{Payout Ratio}) = 0.14 \times (1 - 0.60) = 0.14 \times 0.40 = 5.6\%$$

**Why?** Growth comes from retained earnings. If the company earns 14% on equity and keeps 40% of earnings, equity grows by 5.6% per year.

**Step 2:** Apply the single-stage model

$$V_0 = B_0 + \frac{ROE - r}{r - g} \times B_0$$

$$V_0 = 23.00 + \frac{0.14 - 0.12}{0.12 - 0.056} \times 23.00$$

$$V_0 = 23.00 + \frac{0.02}{0.064} \times 23.00$$

$$V_0 = 23.00 + 0.3125 \times 23.00$$

$$V_0 = 23.00 + 7.19 = \$30.19$$

**Interpretation:** The stock is worth $30.19. Of that, $23.00 is the book value (what shareholders already own), and $7.19 is the premium for the company's ability to earn above its [[Cost of equity|cost of equity]].

**Step 3:** Verify with [[Gordon Growth Model]]

$$E_1 = B_0 \times ROE = 23.00 \times 0.14 = \$3.22$$

$$D_1 = E_1 \times \text{Payout} = 3.22 \times 0.60 = \$1.932$$

$$V_0 = \frac{D_1}{r - g} = \frac{1.932}{0.12 - 0.056} = \frac{1.932}{0.064} = \$30.19 \checkmark$$

Same answer — confirming these models are equivalent under [[Consistent|consistent]] assumptions.

---

### Worked Example: Koninklijke Philips

**Given:**
- $B_0$ = €13.22
- [[ROE]] = 12%
- $g$ = 6.75%
- $r$ = 8.5%

$$V_0 = 13.22 + \frac{0.12 - 0.085}{0.085 - 0.0675} \times 13.22 = 13.22 + \frac{0.035}{0.0175} \times 13.22$$

$$V_0 = 13.22 + 2.0 \times 13.22 = 13.22 + 26.44 = €39.66$$

The stock is valued at nearly **3× book value** because its ROE (12%) far exceeds its [[Cost of equity|cost of equity]] (8.5%), and growth is strong (6.75%).

---

## LOS 21.g: Implied Growth Rate

We can reverse-engineer the market's expected [[Growth Rate]] by plugging in the **current market price** instead of solving for value:

$$g = r - \frac{(ROE - r) \times B_0}{V_0 - B_0}$$

**Worked Example (Philips continued):**

Using the market price of €35.40 instead of our calculated €39.66:

$$35.40 = 13.22 + \frac{0.12 - 0.085}{0.085 - g} \times 13.22$$

$$35.40 - 13.22 = \frac{0.035 \times 13.22}{0.085 - g}$$

$$22.18 = \frac{0.4627}{0.085 - g}$$

$$0.085 - g = \frac{0.4627}{22.18} = 0.02086$$

$$g = 0.085 - 0.02086 = 6.41\%$$

**Interpretation:** The market is pricing in a 6.41% growth rate — slightly below the analyst's 6.75% estimate. If the analyst is right, the stock might be slightly undervalued.

---

## LOS 21.f & 21.h: Multistage Residual Income Model

### Why We Need Multiple Stages

The single-stage model assumes [[ROE]] stays above [[Cost of equity]] **forever**. But in reality, competition erodes excess profits over time. New competitors enter high-ROE industries, driving returns down toward the cost of equity. This is [[Mean reversion]] of ROE.

The multistage model handles this by:
1. **Forecasting RI explicitly** for a near-term period (where we have good [[Visibility|visibility]])
2. **Making an assumption about [[Continuing residual income]]** for everything beyond that horizon

### The Multistage Formula

$$V_0 = B_0 + \sum_{t=1}^{T} \frac{E_t - r B_{t-1}}{(1+r)^t} + \frac{P_T - B_T}{(1+r)^T}$$

**The three components:**
1. **$B_0$:** Current [[Book value]] — the known starting point
2. **$\sum \frac{E_t - rB_{t-1}}{(1+r)^t}$:** PV of forecasted [[Residual income]] during the explicit forecast period
3. **$\frac{P_T - B_T}{(1+r)^T}$:** PV of [[Continuing residual income]] — the premium (or discount) to book value at the end of the forecast horizon

### The Persistence Factor ($\omega$) Approach

Using a [[Persistence Factor]] $\omega$ (omega) between 0 and 1:

$$V_0 = B_0 + \sum_{t=1}^{T-1} \frac{E_t - r B_{t-1}}{(1+r)^t} + \frac{E_T - r B_{T-1}}{(1+r-\omega)(1+r)^{T-1}}$$

### Four Assumptions About Continuing Residual Income

| Assumption | $\omega$ Value | What It Means | When to Use |
|---|---|---|---|
| RI persists forever at current level | $\omega = 1$ | Company maintains its competitive advantage indefinitely | Extremely strong [[Moat]] (rare) |
| RI drops to zero immediately | $\omega = 0$ | ROE instantly equals cost of equity after forecast horizon | Highly competitive industry, no moat |
| RI declines gradually to zero | $0 < \omega < 1$ | ROE slowly reverts to cost of equity | **Most realistic** — gradual competition erodes advantage |
| RI declines to long-run industry level | Use $P_T/B_T$ ratio | ROE stabilizes at an industry norm | Mature, stable industries |

**What drives a higher [[Persistence Factor]]?**
- Low [[Dividend payout ratio]] (more reinvestment sustains growth)
- Historically high RI persistence in the industry
- Strong [[Competitive Advantage]] / [[Economic Moat]]

**What drives a lower [[Persistence Factor]]?**
- High [[ROE]] (attracts competitors faster)
- Significant [[Non-Recurring Items]] (inflating current RI)
- High [[Accounting Accruals]] (earnings quality concerns)

---

### Worked Example: Multistage RI Model — Java Metals

**Given:**
- $B_0$ = $5.00/share
- [[ROE]] = 15% for next 5 years
- $r$ = 10%
- No dividends (all earnings reinvested)
- Continuing RI = 0 after Year 5 ($\omega = 0$)

**Step 1:** Build the forecast table year by year

| Year | Beginning BV ($B_{t-1}$) | Earnings ($E_t = ROE \times B_{t-1}$) | Equity Charge ($r \times B_{t-1}$) | Residual Income ($E_t - r \times B_{t-1}$) | Ending BV ($B_t = B_{t-1} + E_t$) |
|---|---|---|---|---|---|
| 1 | $5.000 | $0.750 | $0.500 | $0.250 | $5.750 |
| 2 | $5.750 | $0.863 | $0.575 | $0.288 | $6.613 |
| 3 | $6.613 | $0.992 | $0.661 | $0.331 | $7.604 |
| 4 | $7.604 | $1.141 | $0.760 | $0.380 | $8.745 |
| 5 | $8.745 | $1.312 | $0.875 | $0.437 | $10.057 |

**Why no dividends matter here:** Since all earnings are reinvested, $B_t = B_{t-1} + E_t$ (nothing paid out). This causes book value — and therefore RI — to grow each year.

**Step 2:** Discount each year's RI back to today

$$PV(RI_1) = \frac{0.250}{1.10^1} = 0.227$$

$$PV(RI_2) = \frac{0.288}{1.10^2} = 0.238$$

$$PV(RI_3) = \frac{0.331}{1.10^3} = 0.249$$

$$PV(RI_4) = \frac{0.380}{1.10^4} = 0.260$$

$$PV(RI_5) = \frac{0.437}{1.10^5} = 0.271$$

$$\sum PV(RI) = 0.227 + 0.238 + 0.249 + 0.260 + 0.271 = 1.245$$

**Step 3:** Add to Book Value

$$V_0 = B_0 + \sum PV(RI) + \underbrace{\frac{P_T - B_T}{(1+r)^T}}_{= 0 \text{ (RI drops to zero)}}$$

$$V_0 = 5.00 + 1.245 + 0 = \$6.245$$

**Interpretation:** Java Metals is worth $6.245. The $1.245 premium over book value represents the value of 5 years of earning 15% when only 10% was required.

---

### What If RI Persists Forever? (Adding Terminal Value)

Using the Zenlandia Chemical example from the textbook — if Year 20 residual income of ZL$23.87 persists forever as a perpetuity:

$$TV = \frac{RI_{20}}{r} = \frac{23.8664}{0.12} = ZL\$198.89$$

$$PV(TV) = \frac{198.89}{1.12^{20}} = ZL\$20.62$$

This adds ZL$20.62 to the base valuation — a significant addition showing that even with the RI model, terminal value assumptions matter (though less so than with [[DDM]] or [[FCFE]]).

---

## LOS 21.i: Comparing RI Models to DDM and FCFE Models

| Feature | [[Residual income model]] | [[DDM]] / [[FCFE]] |
|---|---|---|
| **What you discount** | Book value + stream of residual income | Stream of dividends or free cash flows |
| **Terminal value importance** | Relatively small portion of total value | Often dominates total value (60-80%+) |
| **Data required** | Accounting data (BV, NI, ROE) | Cash flow forecasts |
| **Works for non-dividend payers?** | Yes | DDM: No / FCFE: Yes |
| **Works with negative FCF?** | Yes | Problematic |
| **Sensitivity to terminal assumptions** | Lower | Higher |
| **Key assumption** | [[Clean surplus relation]] holds | Cash flow patterns are predictable |

**Theoretical Equivalence:** Under fully consistent assumptions (same forecasts for earnings, dividends, book value, same discount rate), **all three models give the same answer.** The differences in practice arise because:
- We can't forecast all inputs with equal accuracy
- Some models' assumptions fit certain companies better
- The residual income model's earlier value recognition reduces forecasting error

> [!example] When to Choose Each
> - **[[DDM]]:** Company pays stable, predictable dividends (e.g., a regulated utility like Duke Energy)
> - **[[FCFE]]:** Positive, predictable free cash flows but erratic dividends (e.g., Berkshire Hathaway)
> - **[[Residual income model]]:** Negative FCF, no dividends, uncertain [[Terminal value|terminal value]] (e.g., early-stage biotech company with high R&D spending but strong IP)

---

## LOS 21.j: Strengths and Weaknesses

### Strengths

1. **[[Terminal value|Terminal value]] doesn't dominate:** Because [[Book value]] (known today) is a big part of the answer, we're less reliant on guessing what happens 10+ years from now
2. **Uses readily available data:** [[Book value]], [[Net income]], and [[ROE]] come directly from financial statements — no complex cash flow adjustments needed
3. **Works without dividends:** Perfect for companies like Amazon or Tesla that reinvest everything
4. **Works with negative FCF:** Companies spending heavily on growth (negative [[FCFE]]) can still be valued — their [[Book value]] and [[ROE]] are still observable
5. **Focuses on economic profitability:** Forces us to think about whether the company truly creates value beyond the [[Cost of capital|cost of capital]]

### Weaknesses

1. **Vulnerable to accounting manipulation:** Managers can inflate [[Net income]] through aggressive revenue recognition, capitalizing expenses, etc.
2. **Requires significant adjustments:** Raw accounting data often needs many corrections (LIFO to FIFO, operating leases, off-balance-sheet items)
3. **Requires [[Clean surplus relation]]:** If items bypass the [[Income statement]] (like [[Other comprehensive income]]), the model's accuracy suffers unless adjustments are made
4. **Assumes interest expense reflects true [[Cost of debt|cost of debt]]:** If debt is mispriced or off-market, the model's inputs are distorted

### When to Use (Most Appropriate)

- Company doesn't pay dividends or dividends are unpredictable
- Expected [[FCFE]] is negative for several years
- [[Terminal value|Terminal value]] forecasts are highly uncertain

### When NOT to Use (Least Appropriate)

- Significant [[Clean Surplus Violations]] that can't be adjusted for
- [[Book value]] and [[ROE]] are highly unpredictable
- Company in a jurisdiction with opaque or unreliable accounting standards

---

## LOS 21.k: Accounting Issues in Applying Residual Income Models

### 1. Clean Surplus Violations

**The Problem:** Certain items bypass the [[Income statement]] and go directly to [[Shareholders' Equity]] through [[Other comprehensive income]] ([[OCI]]):

- [[Foreign Currency Translation]] gains/losses
- Certain [[Pension Adjustments]]
- Gains/losses on [[Hedging Instruments]]
- Changes in [[Revaluation Surplus]] (IFRS only)
- Changes in the value of certain [[Liabilities]] due to [[Credit risk|credit risk]] changes (IFRS only)
- Unrealized gains/losses on [[Available-for-Sale Securities]]

**The Effect:** [[Book value]] is still correct (it includes [[Accumulated OCI]]), but [[Net income]] is understated or overstated. Since [[ROE]] = NI / Equity, [[ROE]] is distorted, and therefore so is our [[Residual income]] forecast.

**The Fix:** If the OCI items are expected to be temporary and reverse over time, they may wash out. If they're persistent and one-directional, the analyst must adjust [[Net income]] to include them, effectively using [[Comprehensive income]] instead.

### 2. Balance Sheet Adjustments for Fair Value

**The Problem:** [[Accrual Accounting]] causes many assets/[[Liabilities|liabilities]] to be reported at [[Historical cost]], not [[Fair value]].

**Common Adjustments:**
- **[[Operating Leases]]:** Capitalize them (add asset and liability). This doesn't change equity, but affects future earnings forecasts
- **[[LIFO]] [[Inventory|Inventory]]:** Add the [[LIFO reserve]] to [[Inventory|inventory]] and equity to convert to [[FIFO]] — gives a more current measure of asset values
- **[[Pension]] Obligations:** Adjust to reflect [[Funded status]] ([[Fair value|fair value]] of plan assets minus [[PBO]])
- **[[Deferred tax liabilities]]:** If not expected to reverse (e.g., from accelerating [[Depreciation|depreciation]] in a growing company), reclassify as equity
- **[[Reserves and Allowances]]:** Ensure they reflect expected economic losses

### 3. Intangible Assets

**Two key issues:**

**a) Intangibles from acquisitions:**
When Company A acquires Company B, the combined entity may have new [[Intangible assets]] on its [[Balance sheet|balance sheet]] (licenses, customer lists, etc.) that weren't there before. The [[Amortization]] of these assets reduces reported [[ROE]] for the combined entity, making it look less valuable — even though the actual business hasn't changed. **Fix:** Remove the amortization of [[Acquisition|acquisition]]-related intangibles when computing [[ROE]] for the RI model.

**b) R&D expenditures:**
Under most accounting standards, [[R&D]] is expensed immediately, which *understates* [[Book value]] (no asset is recorded) and makes [[ROE]] look artificially high. For mature companies, the analyst should assess the long-term [[Productivity|productivity]] of R&D: productive R&D increases true [[ROE]]; unproductive R&D decreases it.

### 4. Non-Recurring Items

One-time gains (like selling a building) or losses (like [[Restructuring|restructuring]] charges) inflate or deflate [[Net income]] for one period. If the analyst naively uses this distorted income to forecast future [[ROE]], the [[Residual income]] model will give a wrong answer. **Fix:** Strip out [[Non-Recurring Items]] to get a "normalized" earnings figure.

### 5. Aggressive Accounting Practices

**The Problem:** If a company capitalizes an expense (e.g., puts marketing costs on the [[Balance sheet|balance sheet]] as an asset instead of expensing them), it simultaneously *overstates* current earnings AND *overstates* book value. If an analyst uses these inflated numbers to predict future [[ROE]], the RI model overestimates value.

**Example:** A company with $1,000,000 book value and $200,000 pre-tax earnings has ROE of 20%. If it capitalizes a $50,000 expense, book value becomes $1,050,000 and earnings become $250,000 — ROE jumps to 23.8%. The analyst might project this inflated ROE forward, overvaluing the company.

### 6. International Considerations

Different accounting standards ([[IFRS]] vs. [[US GAAP]]) create comparability issues:
- [[IFRS]] allows [[Revaluation]] of fixed assets; [[US GAAP]] does not
- Treatment of R&D capitalization differs
- [[LIFO]] is allowed under [[US GAAP]] but prohibited under [[IFRS]]

The RI model works best when [[Clean Surplus Violations]] are limited and accounting rules don't result in delayed recognition of economic events.

---

## Formula Summary (Mark Meldrum Notation)

### Residual Income

$$RI = NI - (r \times B_{t-1})$$

### EVA

$$EVA = NOPAT - (C\% \times TC)$$

### MVA

$$MVA = \text{Market Value of Company} - \text{Book Value of Total Capital}$$

### General RI Model

$$V_0 = B_0 + \sum_{t=1}^{\infty} \frac{E_t - r B_{t-1}}{(1+r)^t}$$

$$\text{or: } V_0 = B_0 + \sum_{t=1}^{\infty} \frac{(ROE_t - r) B_{t-1}}{(1+r)^t}$$

### Single-Stage (Constant Growth) RI Model

$$V_0 = B_0 + \frac{ROE - r}{r - g} \times B_0$$

### Implied Growth Rate

$$g = r - \frac{(ROE - r) \times B_0}{V_0 - B_0}$$

### Multistage RI Model

$$V_0 = B_0 + \sum_{t=1}^{T} \frac{E_t - r B_{t-1}}{(1+r)^t} + \frac{P_T - B_T}{(1+r)^T}$$

### With Persistence Factor ($\omega$)

$$V_0 = B_0 + \sum_{t=1}^{T-1} \frac{E_t - r B_{t-1}}{(1+r)^t} + \frac{E_T - r B_{T-1}}{(1+r - \omega)(1+r)^{T-1}}$$

### Variable Definitions

| Variable | Definition |
|---|---|
| $V_0$ | Value of a share of stock today ($t = 0$) |
| $B_0$ | Current per-share [[Book value of equity]] |
| $B_t$ | Expected per-share [[Book value of equity]] at time $t$; $B_t = B_{t-1} + E_t - D_t$ |
| $r$ | [[Required Rate of Return on Equity]] ([[Cost of equity]]) |
| $E_t$ | Expected [[EPS]] for period $t$ |
| $\omega$ | [[Persistence Factor]] (between 0 and 1) |
| $ROE$ | [[Return on Equity]] |
| $g$ | [[Earnings Growth Rate]] |
| $P_T$ | Expected per-share price at terminal time $T$ |
| $NOPAT$ | [[Net Operating Profit After Taxes]] |
| $C\%$ | [[Cost of capital]] (%) i.e., [[WACC]] |
| $TC$ | [[Total Capital]] |

---

## Decision Framework: When to Use Which Model

```
Is the company paying stable, predictable dividends?
├── YES → Use DDM
└── NO → Does the company have positive, predictable FCFE?
    ├── YES → Use FCFE model
    └── NO → Is clean surplus accounting roughly maintained?
        ├── YES → Use Residual Income Model ✓
        └── NO → Can you adjust for clean surplus violations?
            ├── YES → Use Residual Income Model (with adjustments) ✓
            └── NO → Reconsider FCFE model or use multiple approaches
```

---

## Key Takeaways for the Exam

1. [[Residual income]] = [[Net income]] − ([[Cost of equity]] × Beginning [[Book value]]). If RI > 0, the company creates value beyond the cost of capital.

2. [[EVA]] is the firm-level version: [[NOPAT]] − ([[WACC]] × [[Total Capital]]). Same concept, different scope.

3. The RI model values a stock as **Book Value + PV(future RI)**. [[Book value]] is the anchor; the RI stream is the premium/discount.

4. If $ROE > r$: justified P/B > 1. If $ROE = r$: P/B = 1. If $ROE < r$: P/B < 1.

5. The single-stage model $V_0 = B_0 + \frac{ROE - r}{r - g} \times B_0$ gives the **same answer** as the [[Gordon Growth Model]] under [[Consistent|consistent]] assumptions.

6. [[Continuing residual income]] is handled via a [[Persistence Factor]] ($\omega$). Most realistically, RI fades toward zero as competition erodes excess returns ($0 < \omega < 1$).

7. RI models recognize value **earlier** than [[DDM]]/[[FCFE]] because [[Book value]] (known today) is a big chunk of the answer.

8. Biggest [[Accounting risk|accounting risk]]: [[Clean Surplus Violations]]. Watch for items that bypass the [[Income statement]] and go directly to equity.

9. Always adjust for: [[LIFO]] reserves, off-balance-sheet items, intangible asset distortions, and non-recurring items.

---

*Tags: #CFA #Level2 #EquityValuation #ResidualIncome #EVA #MVA #CleanSurplus #[[Valuation|Valuation]]*
