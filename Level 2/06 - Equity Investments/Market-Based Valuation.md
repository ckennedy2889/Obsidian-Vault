---
title: "Market-Based Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments]
aliases: []
---

# LM4: Market-Based Valuation — Price and Enterprise Value Multiples

---

## The Big Picture

Imagine you're shopping for a used car. You wouldn't just look at the sticker price in isolation — you'd compare it to similar cars. "Is $25,000 reasonable for a 2022 Honda Civic with 30,000 miles?" You'd check what other similar Civics are selling for, or you'd estimate what the car *should* be worth based on its condition, mileage, and features.

That's exactly what [[Price multiples]] and [[enterprise value multiples]] do for stocks. They give you a way to ask: **"Is this stock's price reasonable given what I'm getting?"**

There are two fundamental approaches:
1. **[[Method of comparables]]** — compare the stock to similar stocks (like checking other Civic prices)
2. **[[Method of Forecasted Fundamentals]]** — calculate what the multiple *should* be based on the company's own financials (like appraising the car based on its specs)

---

## 1. Method of Comparables vs. Method of Forecasted Fundamentals

### [[Method of comparables]]

**What it is:** You value a stock by comparing its [[Price multiple]] to a [[Benchmark|benchmark]] — typically the [[Median]] or [[mean]] multiple of a [[Peer group|peer group]] of similar companies.

**Economic rationale:** The [[Law of one price]] — two similar assets should sell at similar prices. If two companies have nearly identical risk, growth, and profitability, they should trade at similar P/E ratios. If one is cheaper, it might be [[undervalued]].

**Key limitation:** This is a *relative* [[Valuation|valuation]]. You're saying "Stock A is cheap *relative to* Stock B." But what if Stock B is also overpriced? Then Stock A might be fairly valued or even overpriced on an *absolute* basis. You're assuming the [[Benchmark|benchmark]] is correctly priced.

> **Real-world example:** MK Technologies trades at a [[trailing P/E]] of 25×, while its industry average is 32×. Relative to peers, MK appears [[undervalued]] — investors are paying less per dollar of earnings for MK than for the average competitor. But if the entire industry is in a bubble, MK could still be overpriced in absolute terms.

### [[Method of Forecasted Fundamentals]]

**What it is:** You use a [[discounted cash flow (DCF)]] model (like the [[Gordon Growth Model]]) to estimate what a stock's [[Intrinsic value]] should be, and then express that value as a multiple.

**Economic rationale:** The value used in the numerator comes from a DCF model — value equals the [[present value]] of expected future [[cash flows]] discounted at the appropriate risk-adjusted [[Required rate of return]]. This is an *absolute* [[Valuation|valuation]] anchored in [[Fundamentals|fundamentals]].

> **Real-world example:** Comtronics trades at $30. Analysts forecast next year's [[EPS]] at $4.00, with a 5% long-run [[growth rate]], a 60% [[Dividend payout ratio]], and a 14% [[required return]]. Using the [[Gordon Growth Model]]:
>
> $$V_0 = \frac{D_1}{r - g} = \frac{E_1 \times (1 - b)}{r - g} = \frac{4.00 \times 0.60}{0.14 - 0.05} = \frac{2.40}{0.09} = \$26.67$$
>
> The justified [[leading P/E]] is:
>
> $$\frac{V_0}{E_1} = \frac{26.67}{4.00} = 6.67\times$$
>
> The actual leading P/E is $30 / $4 = 7.5×. Since the actual P/E (7.5×) exceeds the [[Justified P/E|justified P/E]] (6.67×), the stock appears **[[overvalued]]**.

### Summary Comparison

| Feature | [[Method of comparables]] | [[Method of Forecasted Fundamentals]] |
|---|---|---|
| Based on | [[Peer group|Peer group]] multiples | [[DCF]] model output |
| Rationale | [[Law of one price]] | [[Present value]] of future cash flows |
| [[Valuation|Valuation]] type | Relative | Absolute |
| Weakness | Peers may be mispriced | Relies on model assumptions |

---

## 2. Justified Price Multiples

A **[[Justified price multiple]]** is the estimated [[Fair value|fair value]] of that multiple — what the multiple *should* be if the stock is fairly valued. It can be justified by either method:

- **From [[Comparables|comparables]]:** The justified P/B is the [[Median]] P/B of the [[Peer group|peer group]] (e.g., 2.2). If the stock's actual P/B is below 2.2, it may be [[undervalued]].
- **From [[Fundamentals|fundamentals]]:** The justified P/B is derived from a [[Valuation|valuation]] model (e.g., the [[Residual income model]] says the stock is worth $46, and [[BVPS]] is $23, so justified P/B = $46/$23 = 2.0).

**[[Decision rule|Decision rule]]:**
- If **actual multiple < justified multiple** → stock may be [[undervalued]]
- If **actual multiple > justified multiple** → stock may be [[overvalued]]

---

## 3. Price Multiples — Rationales and Drawbacks

### 3a. [[Price-to-Earnings (P/E) Ratio]]

**What it is:** How much investors pay per dollar of earnings.

$$P/E = \frac{\text{Market Price per Share}}{\text{Earnings per Share (EPS)}}$$

**Why it matters:** [[Earnings]] power is the chief driver of [[Investment value]]. The P/E is the single most popular valuation metric among professional investors.

**Two versions:**

| Version | Formula | When to Use |
|---|---|---|
| **[[Trailing P/E]]** | $P_0 / E_0$ (last 4 quarters' [[EPS]]) | When earnings are stable and predictable |
| **[[Forward P/E]]** (leading) | $P_0 / E_1$ (next year's expected [[EPS]]) | When looking forward; preferred by analysts |

**Rationales for using P/E:**
- [[Earnings]] power is the primary determinant of [[Investment value]]
- Widely recognized and used by investors
- P/E differences are significantly related to long-run average stock returns

**Drawbacks of P/E:**
- [[EPS]] can be negative or zero, making P/E meaningless
- The volatile, transitory portion of earnings makes interpretation difficult (the **[[Molodovsky effect]]** — P/Es tend to be high at the bottom of the [[Business cycle|business cycle]] when earnings are depressed, and low at the top when earnings are inflated)
- Management discretion in accounting can distort reported [[EPS]]

### 3b. [[Price-to-Book (P/B) Ratio]]

$$P/B = \frac{\text{Market Price per Share}}{\text{Book Value per Share (BVPS)}}$$

**[[Book value]]** is [[shareholders' equity]] divided by shares outstanding — it represents the accounting value of the net assets that belong to shareholders.

**Rationales:**
- [[Book value]] is usually positive even when [[EPS]] is negative, so P/B can be used when P/E cannot
- [[Book value]] is more stable than [[EPS]]
- Appropriate for firms with mostly liquid assets (banks, insurance companies)
- Useful for valuing companies expected to go out of business ([[Liquidation value]])

**Drawbacks:**
- Does not capture the value of [[Intangible assets]] (brand, patents, [[Human capital|human capital]])
- Can mislead when there are significant size differences between firms
- Different accounting conventions (e.g., [[IFRS]] vs [[US GAAP]] treatment of asset revaluations) reduce comparability
- [[Inflation|Inflation]] and technological change cause [[Book value]] and [[Market value]] to diverge

### 3c. [[Price-to-Sales (P/S) Ratio]]

$$P/S = \frac{\text{Market Price per Share}}{\text{Sales per Share}}$$

**Rationales:**
- Sales are meaningful even for distressed firms (unlike negative [[EPS]])
- Sales revenue is less subject to manipulation than [[EPS]] or [[Book value]]
- P/S is more stable than P/E

**Drawbacks:**
- P/S ignores differences in [[Cost structure|cost structure]] — two companies with the same revenue but very different profitability will have the same P/S
- Revenue recognition practices can still distort sales
- A company can have growing sales but still be unprofitable

### 3d. [[Price-to-Cash Flow (P/CF) Ratio]]

$$P/CF = \frac{\text{Market Price per Share}}{\text{Cash Flow per Share}}$$

**[[Cash flow]]** can be defined several ways: [[CFO]] ([[Cash Flow from Operations|cash flow from operations]]), [[FCFE]] ([[Free cash flow|free cash flow]]ow to equity|[[Free cash flow|free cash flow]] to equity]]), or earnings plus non-cash charges.

**Rationales:**
- Cash flow is harder to manipulate than [[earnings]]
- More stable than [[EPS]]

**Drawbacks:**
- Different definitions of [[cash flow]] reduce comparability
- [[EBITDA]] and simple cash flow measures ignore [[Working capital]] changes

### 3e. [[Dividend Yield (D/P)]]

$$\text{Trailing Dividend Yield} = \frac{D_0}{P_0} \qquad \text{Leading Dividend Yield} = \frac{D_1}{P_0}$$

**Rationales:**
- [[Dividends]] contribute to total [[investment return]]
- [[Dividends]] are considered less risky than [[capital appreciation]]

**Drawbacks:**
- Ignores [[capital appreciation]] — an incomplete measure of return
- The [[Dividend displacement of earnings]] concept: dividends paid now may reduce future earnings and growth

> **Real-world example:** OnePrice, Inc. just paid a $0.50 dividend. Forecasted dividends for the next four quarters are $0.50, $0.55, $0.60, and $0.65. Price = $47.50.
>
> $$\text{Trailing D/P} = \frac{4 \times 0.50}{47.50} = \frac{2.00}{47.50} = 4.21\%$$
>
> $$\text{Leading D/P} = \frac{0.50 + 0.55 + 0.60 + 0.65}{47.50} = \frac{2.30}{47.50} = 4.84\%$$

---

## 4. Underlying Earnings, Normalized EPS, and Earnings Yield

### [[Underlying earnings]]

**What it is:** Earnings that exclude [[nonrecurring items]] — things like gains/losses from asset sales, [[write-downs]], [[Restructuring|restructuring]] charges, and changes in [[Accounting estimates|accounting estimates]]. Also called **persistent**, **continuing**, or **[[Core earnings|core earnings]]**.

**Why it matters:** To use P/E effectively, you need an [[EPS]] figure that reflects the company's true, ongoing earning power — not one distorted by one-time events.

> **Real-world example — Magnolia Enterprises:**
>
> 12-month [[EPS]] = $1.45 + $1.30 + $1.40 + $1.35 = C$5.50
>
> But there was a C$0.30 gain from an asset sale (nonrecurring — subtract it) and a C$0.55 [[Restructuring|restructuring]] charge (nonrecurring — add it back):
>
> $$\text{Underlying EPS} = 5.50 - 0.30 + 0.55 = C\$5.75$$

### [[Normalized EPS]]

When earnings are distorted by the **[[Business cycle]]** (not just one-time items), analysts use [[Normalized EPS]] — an estimate of what [[EPS]] would be under mid-cycle conditions.

**Why normalize?** Because of the **[[Molodovsky effect]]**: at the bottom of a [[Recession|recession]], earnings are depressed, so P/E looks artificially high. At the peak of a boom, earnings are inflated, so P/E looks artificially low. Normalizing removes this distortion.

**Two methods:**

**Method 1: [[Method of Historical Average EPS]]**

$$\text{Normalized EPS} = \frac{\sum_{i=1}^{n} EPS_i}{n}$$

Simply average [[EPS]] over the most recent full [[Business cycle]].

*Limitation:* Ignores changes in firm size. If a company has doubled in size, averaging old (smaller) EPS with current (larger) EPS understates current earning power.

**Method 2: [[Method of Average ROE]]** *(preferred)*

$$\text{Normalized EPS} = \frac{\sum_{i=1}^{n} ROE_i}{n} \times BVPS_n$$

Average the [[Return on equity (ROE)]] over the cycle, then multiply by current [[book value per share (BVPS)]]. This accounts for changes in firm size because you're applying a normalized *rate of return* to the *current* asset base.

> **Real-world example — Magnolia Enterprises:**
>
> | Year | [[EPS]] | [[ROE]] | [[BVPS]] |
> |---|---|---|---|
> | 2019 | C$3.00 | 10.2% | C$29.41 |
> | 2020 | C$3.75 | 12.0% | C$31.25 |
> | 2021 | C$4.50 | 13.1% | C$34.35 |
> | 2022 | C$5.75 | 15.4% | C$37.34 |
>
> **Method 1 (Historical Average EPS):**
>
> $$\frac{3.00 + 3.75 + 4.50 + 5.75}{4} = C\$4.25$$
>
> **Method 2 (Average ROE):**
>
> $$\text{Avg ROE} = \frac{0.102 + 0.120 + 0.131 + 0.154}{4} = 0.12675$$
>
> $$\text{Normalized EPS} = 0.12675 \times 37.34 = C\$4.73$$
>
> Method 2 gives a higher result because it accounts for the firm's growth (increasing [[BVPS]]).

### [[Earnings Yield (E/P)]]

$$E/P = \frac{\text{EPS}}{\text{Price per Share}}$$

**Why use it?** When [[EPS]] is negative, the [[P/E ratio]] is meaningless (you can't interpret a negative P/E). But [[Earnings yield]] always works because price is never negative.

**Interpretation:**
- **High E/P** → cheap stock (you get a lot of earnings per dollar of price)
- **Low E/P** → expensive stock

You can rank securities from cheapest to most expensive using E/P, even when some have negative earnings — something P/E cannot do.

---

## 5. Fundamental Factors That Influence Price Multiples

These relationships come from the [[Gordon Growth Model]] and tell you **what drives each multiple up or down**.

| Multiple | Increases when... | Decreases when... |
|---|---|---|
| [[P/E]] | [[Growth rate]] ↑ | [[Required return]] ↑ |
| [[P/B]] | [[ROE]] ↑ (relative to r) | [[Required return]] ↑ |
| [[P/S]] | [[Profit margin]] ↑, [[growth rate]] ↑ | [[Required return]] ↑ |
| [[P/CF]] | [[Cash flow growth]] ↑ | [[Required return]] ↑ |
| [[Dividend yield (D/P)]] | [[Required return]] ↑ | [[Growth rate]] ↑ |

Notice that [[Dividend yield]] moves in the *opposite* direction from the other multiples with respect to growth. A high [[Dividend yield]] stock is typically a low-growth, value-oriented stock — the company is returning cash rather than reinvesting for growth.

---

## 6. Cross-Sectional Regression for Predicted P/E

**What it is:** Instead of using a single formula, you run a [[regression]] across many stocks at a point in time, with [[P/E]] as the [[Dependent|dependent]]nt variable|[[Dependent|dependent]] variable]] and fundamental factors (like [[growth rate]], [[Beta]], [[Payout ratio]]) as [[Independent|independent]] variables.

$$\text{Predicted P/E} = a_0 + a_1 \times (\text{DPR}) + a_2 \times (\beta) + a_3 \times (g)$$

Where:
- $a_0$ = intercept
- $DPR$ = [[Dividend payout ratio]]
- $\beta$ = [[Beta]] (measure of [[Systematic risk|systematic risk]])
- $g$ = expected [[earnings growth rate]]

> **Example:** An analyst values a utility with DPR = 0.50, β = 0.95, g = 0.06. The regression equation is:
>
> $$\text{Predicted P/E} = 10.29 + 8.21(0.50) + (-1.45)(0.95) + 14.14(0.06)$$
>
> $$= 10.29 + 4.105 - 1.378 + 0.848 = 13.87$$
>
> If the actual P/E is 12.0, the stock appears **[[undervalued]]** (actual < predicted). If the actual P/E is 15.0, the stock appears **[[overvalued]]**.

**Limitations of cross-sectional regression:**
- Predictive power may not hold for different time periods or samples
- The relationships between P/E and fundamentals can change over time
- **[[CFA_Glossary/Multicollinearity]]** — the independent variables (growth, beta, payout) are often correlated with each other, making individual coefficients hard to interpret

---

## 7. Justified Multiples from Forecasted Fundamentals

These are the core formulas that derive each multiple from the [[Gordon Growth Model]].

### [[Justified Forward P/E]]

$$\frac{P_0}{E_1} = \frac{D_1/E_1}{r - g} = \frac{DPR}{r - g}$$

**In plain English:** The justified forward P/E equals the [[Dividend payout ratio]] divided by the difference between the [[required return]] and the [[growth rate]].

- $P_0$ = current stock price (what we're solving for as a ratio)
- $E_1$ = next year's expected [[EPS]]
- $D_1$ = next year's expected [[dividend per share]]
- $DPR$ = [[Dividend payout ratio]] = $D_1 / E_1$ = the fraction of earnings paid as dividends
- $r$ = [[Required rate of return]] on equity — the return investors demand given the stock's risk
- $g$ = expected constant [[growth rate]] of dividends/earnings

**Why each variable is there:**
- **DPR in numerator:** A company that pays out more of its earnings has a higher P/E, all else equal, because investors receive more cash directly
- **r in denominator:** Higher required returns mean investors demand a lower price for each dollar of earnings → lower P/E
- **g in denominator (subtracted from r):** Higher growth makes future earnings more valuable → higher P/E (because $r - g$ gets smaller, making the fraction larger)

### [[Justified Trailing P/E]]

$$\frac{P_0}{E_0} = \frac{DPR \times (1 + g)}{r - g}$$

Same logic, but since we're dividing by *current* earnings rather than *next year's* earnings, we multiply by $(1 + g)$ to account for one year of growth.

> **Worked Example:**
>
> A stock has DPR = 40%, r = 11%, g = 5%.
>
> $$\text{Justified Leading P/E} = \frac{0.40}{0.11 - 0.05} = \frac{0.40}{0.06} = 6.67\times$$
>
> $$\text{Justified Trailing P/E} = \frac{0.40 \times 1.05}{0.11 - 0.05} = \frac{0.42}{0.06} = 7.0\times$$
>
> The trailing P/E is higher because current earnings ($E_0$) are smaller than next year's ($E_1$), so dividing price by a smaller number gives a bigger ratio.

### [[Justified P/B]]

$$\frac{P_0}{B_0} = \frac{ROE - g}{r - g}$$

**In plain English:** The justified P/B equals the spread of [[ROE]] over the [[growth rate]], divided by the spread of the [[required return]] over the [[growth rate]].

- $B_0$ = current [[Book value per share]]
- $ROE$ = [[return on equity]] — how much profit the company generates per dollar of shareholders' equity
- $r$ = [[Required rate of return]]
- $g$ = [[Sustainable growth rate]] = $b \times ROE$, where $b$ = [[retention rate]]

**Key insight:** What really drives P/B is **how [[ROE]] compares to r**. If [[ROE]] > r, the company is creating value (earning more on its investments than investors demand), so P/B > 1. If [[ROE]] < r, the company is destroying value, so P/B < 1.

> **Worked Example:**
>
> ROE = 14%, r = 8%, g = 4%.
>
> $$\frac{P_0}{B_0} = \frac{0.14 - 0.04}{0.08 - 0.04} = \frac{0.10}{0.04} = 2.5\times$$
>
> This means investors are willing to pay 2.5× the [[Book value|book value]] because the company earns well above its [[Cost of equity|cost of equity]].

### [[Justified P/S]]

$$\frac{P_0}{S_0} = \frac{(E_0/S_0)(1 - RR)(1 + g)}{r - g}$$

Where:
- $E_0/S_0$ = [[Net profit margin]] — what fraction of each dollar of sales becomes profit
- $RR$ = [[retention rate]] ($b$) — the fraction of earnings reinvested (so $1 - RR$ = [[Dividend payout ratio]])
- $g$ = [[growth rate]]
- $r$ = [[required return]]

**In plain English:** The P/S ratio depends on how profitable each dollar of sales is ([[Profit margin]]), how much is paid out, and how fast the company is growing. A company with a fat [[Profit margin]] and high growth will have a high P/S.

You can also express this more simply as:

$$\frac{P_0}{S_0} = \frac{P_0}{E_0} \times \frac{E_0}{S_0} = \text{Trailing P/E} \times \text{Profit Margin}$$

> **Worked Example:**
>
> DPR = 40%, ROE = 8.3%, EPS = $4.25, Sales per share = $218.75, g = 5%, r = 10%.
>
> **Step 1:** Calculate [[Profit margin]]:
> $$E_0/S_0 = 4.25 / 218.75 = 0.0194$$
>
> **Step 2:** Apply the formula:
> $$\frac{P_0}{S_0} = \frac{0.0194 \times (1 - 0.60) \times (1.05)}{0.10 - 0.05} = \frac{0.0194 \times 0.40 \times 1.05}{0.05} = \frac{0.008148}{0.05} = 0.163\times$$
>
> Wait — let's double-check: retention rate = 1 − DPR = 1 − 0.40 = 0.60, so $(1 - RR) = (1 - 0.60) = 0.40$. That checks out.

---

## 8. The PEG Ratio

$$\text{PEG} = \frac{P/E}{g}$$

Where $g$ is stated in percentage terms (e.g., if growth = 12%, use 12, not 0.12).

**What it does:** The [[PEG ratio]] adjusts the [[P/E]] for expected [[growth]]. Think of it as asking: "How much P/E am I paying per unit of growth?"

**Interpretation:**
- **Lower PEG** → more attractive (you're paying less per unit of growth)
- **PEG = 1** is sometimes used as a rough [[Benchmark|benchmark]] for [[Fair value|fair value]]
- If PEG < 1, the stock may be [[undervalued]] relative to its growth

**Two versions:**

$$\text{Forward PEG} = \frac{P_0/E_1}{g} \qquad \text{Trailing PEG} = \frac{P_0/E_0}{g}$$

> **Real-world example:**
>
> | Company | Price | Forecast EPS | Forward P/E | Growth (%) | PEG |
> |---|---|---|---|---|---|
> | Adesivo | BRL 14.72 | BRL 0.91 | 16.18 | 16.67 | **0.97** |
> | Enviado | BRL 72.20 | BRL 3.10 | 23.29 | 21.91 | **1.06** |
> | Gesticular | BRL 132.16 | BRL 2.85 | 46.37 | 32.33 | **1.43** |
>
> Adesivo has the lowest PEG (0.97), making it the most attractively valued based on PEG.

**Limitations of PEG:**
- Assumes a **linear** relationship between P/E and growth — but in reality, the relationship is not linear
- **Ignores risk** — two stocks with the same P/E and growth but different betas will have the same PEG, even though they shouldn't be valued the same
- Does not account for **differences in the duration of growth** — a company growing at 15% for 2 years is very different from one growing at 15% for 10 years

---

## 9. Price Multiples for Terminal Value in Multistage DCF Models

In a [[multistage DCF model]], you forecast cash flows explicitly for a few years, then estimate a **[[Terminal value]]** at the end. One common way to get [[Terminal value]] is with a [[Price multiple]].

$$V_n = \text{Benchmark trailing P/E} \times E_n$$

$$V_n = \text{Benchmark forward P/E} \times E_{n+1}$$

**In plain English:** At the end of your forecast horizon (year $n$), you estimate what the stock will be worth by multiplying expected earnings at that time by a reasonable P/E [[Benchmark|benchmark]] (from comparable companies or historical averages).

> **Example:**
>
> You're doing a 3-year DCF. At year 3, you forecast $E_3 = \$3.00$ and the industry average P/E is 14.3×.
>
> $$V_3 = 14.3 \times \$3.00 = \$42.90$$
>
> For comparison, using the [[Gordon Growth Model]] with the same data (average payout = 45%, ROE = 13%, r = 10%):
>
> $g = b \times ROE = 0.55 \times 0.13 = 7.15\%$
>
> $D_3 = \$3.00 \times 0.45 = \$1.35$
>
> $$V_3 = \frac{1.35 \times 1.0715}{0.10 - 0.0715} = \frac{1.4465}{0.0285} = \$50.76$$
>
> The GGM gives a higher [[Terminal value|terminal value]] ($50.76 vs. $42.90) — a difference of about 18%. This shows why the choice of [[Terminal value]] method matters significantly.

---

## 10. Evaluating Stocks Using Comparables

### The 4-Step Process

1. **Select and calculate** the [[Price multiple]] to use
2. **Select the benchmark** — [[Peer group|peer group]], industry, index, or historical average — and calculate the [[Median]] or [[mean]] of that multiple
3. **Compare** the stock's multiple to the benchmark
4. **Assess** whether any difference is explained by differences in **[[Fundamentals]]** (growth, risk, profitability), and adjust your conclusion accordingly

Step 4 is critical. Just because a stock has a lower P/E than its peers doesn't automatically mean it's [[undervalued]] — it might have lower P/E because it has lower growth, higher risk, or worse profitability.

### Common Benchmarks for P/E

- P/E of a similar company in the same industry
- [[Median]] or [[mean]] P/E of the peer group
- Industry average P/E
- P/E of a broad equity [[index]]
- The stock's own average historical P/E

> **Real-world example:**
>
> Company A and Company B are in the same industry:
>
> | | Company A | Company B |
> |---|---|---|
> | Price | £17.98 | £15.65 |
> | [[CF per share]] | £1.84 | £1.37 |
> | P/CF | 9.8× | 11.4× |
> | 5-yr growth forecast | 13.4% | 10.6% |
> | [[Beta]] | 1.50 | 1.50 |
>
> Company A has a *lower* P/CF but *higher* expected growth and the same risk. This is inconsistent — you'd expect the faster-growing company to have the higher multiple. Company A appears **relatively [[undervalued]]** compared to Company B.

---

## 11. Cash Flow Definitions for Price and EV Multiples

Different analysts use different definitions of "[[cash flow]]." Each has pros and cons:

| Measure | Definition | Limitation |
|---|---|---|
| **CF** (Earnings + non-cash charges) | [[Net income]] + [[Depreciation]] + [[amortization]] | Not a true cash flow — ignores [[Working capital]] changes and [[non-cash revenue]] |
| **[[CFO]]** ([[Cash Flow from Operations|Cash flow from operations]]) | From the cash flow statement | Can be influenced by [[Working capital]] management |
| **[[FCFE]]** ([[Free cash flow to equity|Free cash flow to equity]]) | [[CFO]] – [[CapEx]] + net borrowing | Most theoretically sound, but more volatile |
| **[[EBITDA]]** | [[Net income]] + interest + taxes + D&A | Pre-interest, so matches to [[Enterprise value]]; but ignores [[CapEx]] and [[Working capital]] |

**[[FCFE]]** has the strongest link to [[valuation theory]], but in practice, CF and [[EBITDA]] are more commonly used because they're simpler and more stable.

---

## 12. Enterprise Value Multiples

### [[Enterprise Value (EV)]]

$$EV = MV_e + MV_d + MV_{pr} - \text{Cash} - \text{Marketable Securities}$$

Where:
- $MV_e$ = [[market value of common equity]] (shares × price)
- $MV_d$ = [[market value of debt]]
- $MV_{pr}$ = [[market value of preferred stock]]
- Cash and [[marketable securities]] are subtracted because they're non-operating assets

**Why subtract cash?** If you bought the entire company, you'd get the cash on the [[Balance sheet|balance sheet]]. So the net cost of acquiring the business is total capital minus the cash you'd receive. Think of it like buying a house — if the house comes with $10,000 in a safe, the effective price you're paying for the *house itself* is the purchase price minus $10,000.

### [[EV/EBITDA]]

$$\frac{EV}{EBITDA}$$

**Why use it over P/E?**
- [[EBITDA]] is a pre-interest figure, so it's a flow to **all providers of capital** (both debt and equity). This makes [[EV/EBITDA]] better for comparing companies with different [[Financial leverage]] (debt levels)
- By adding back [[Depreciation]] and [[amortization]], it controls for differences in capital intensity
- [[EBITDA]] is usually positive even when [[EPS]] is negative

**Drawbacks:**
- If [[Working capital]] is growing, [[EBITDA]] overstates [[CFA_Glossary/Cash flow from operations]]
- [[FCFF]] ([[Free cash flow to the firm|free cash flow to the firm]]) has a stronger theoretical link to valuation because it captures actual [[capital expenditures]]
- [[EBITDA]] is adequate only if [[Depreciation]] roughly equals [[CapEx]]

> **Worked Example — Boulevard Industries:**
>
> | Item | Value (Sf) |
> |---|---|
> | Share price | 22.50 |
> | Shares outstanding | 40 million |
> | [[Market value|Market value]] of debt | 137 million |
> | Cash & marketable securities | 62.3 million |
> | [[Net income|Net income]] | 137.5 million |
> | Interest expense | 6.9 million |
> | D&A | 10.4 million |
> | Taxes | 95.9 million |
>
> **Step 1:** Calculate EV:
> $$EV = (40 \times 22.50) + 137 - 62.3 = 900 + 137 - 62.3 = Sf\ 974.7\ \text{million}$$
>
> **Step 2:** Calculate EBITDA:
> $$EBITDA = 137.5 + 6.9 + 95.9 + 10.4 = Sf\ 250.7\ \text{million}$$
>
> **Step 3:** Calculate the ratio:
> $$EV/EBITDA = \frac{974.7}{250.7} = 3.89\times$$

### Other EV Multiple Variants

| Variant | When to Use |
|---|---|
| **EV/FCFF** | Strongest theoretical basis |
| **EV/EBITDAR** | When rent expense ($R$) varies across [[Comparables|comparables]] (e.g., airlines, retail) |
| **EV/EBITA** | When [[amortization]] (of intangibles) is the major non-cash charge |
| **EV/EBIT** | When [[Depreciation]] and [[amortization]] are minor |
| **EV/Sales** | Controls for different capital structures (unlike P/S) |

---

## 13. Cross-Border Valuation Differences

Using [[Price multiples]] to compare companies across countries is challenging because of:

- **Accounting differences:** Treatment of [[Goodwill]], [[deferred taxes]], [[R&D]], [[pensions]], asset revaluations, and [[foreign exchange adjustments]] vary between [[IFRS]] and [[US GAAP]]
- **Cultural differences:** Different [[Corporate governance|corporate governance]] norms and business practices
- **Economic differences:** Varying levels of [[Risk]], [[growth opportunities]], and [[Inflation|inflation]]
- **Benchmarking difficulties:** P/Es for the same industry can vary widely across countries

**Which multiples are least/most affected?**
- **Least affected:** [[P/FCFE]] — because [[Free cash flow]] is based on actual cash, not accounting rules
- **Most affected:** [[P/B]], [[P/E]], [[P/EBITDA]], [[EV/EBITDA]] — more influenced by management's accounting choices

---

## 14. Momentum Indicators

[[Momentum indicators]] relate price or a fundamental (like [[EPS]]) to its own past values or expected values. They help identify stocks that may continue to outperform (or underperform).

### [[Unexpected earnings]] (Earnings Surprise)

$$UE_t = EPS_t - E(EPS_t)$$

The difference between what a company actually reported and what analysts expected. Positive surprises tend to lead to persistent positive [[abnormal returns]] (the market doesn't fully adjust to the news immediately).

### [[Standardized Unexpected Earnings (SUE)]]

$$SUE_t = \frac{EPS_t - E(EPS_t)}{\sigma[EPS_t - E(EPS_t)]}$$

**Why standardize?** A $0.10 earnings surprise means very different things for a company that typically surprises by $0.02 versus one that typically surprises by $0.50. SUE scales the surprise by its historical variability, making it comparable across firms.

### [[Relative Strength]]

Compares a stock's price performance during a period to its own history or to a peer group. The economic rationale is that patterns of **persistence** (momentum) or **reversal** ([[Mean reversion|mean reversion]]) may exist in stock returns.

---

## 15. Averaging Multiples: Harmonic Mean, Weighted Harmonic Mean, and Median

When computing an "average" [[P/E]] for a portfolio or index, the choice of averaging method matters enormously.

### [[Arithmetic mean]]

$$\bar{X} = \frac{\sum X_i}{n}$$

Simple average. **Problem:** easily distorted by outliers. A single stock with P/E = 200 can pull the average way up.

### [[Median]]

The middle value when sorted. Mitigates outlier effects. Very common for peer group benchmarks.

### [[Harmonic mean]]

$$X_H = \frac{n}{\sum_{i=1}^{n}(1/X_i)}$$

The reciprocal of the [[Arithmetic mean|arithmetic mean]] of the reciprocals. It inherently gives **less weight to higher P/Es** and more weight to lower P/Es, reducing the impact of large outliers.

### [[Weighted harmonic mean]]

$$X_{WH} = \frac{1}{\sum_{i=1}^{n}(w_i / X_i)}$$

Where $w_i$ = the portfolio weight (by [[Market value|market value]]) of stock $i$.

**Why this is the best measure for portfolios and indexes:** The [[Weighted harmonic mean]] precisely matches the directly calculated portfolio P/E (total market cap ÷ total earnings).

> **Example with Two Stocks:**
>
> | Stock | Market Cap (€M) | Earnings (€M) | P/E | Weight |
> |---|---|---|---|---|
> | Stock 1 | 715 | 71.50 | 10 | 55% |
> | Stock 2 | 585 | 29.25 | 20 | 45% |
>
> **Directly calculated portfolio P/E:**
> $$\frac{715 + 585}{71.50 + 29.25} = \frac{1300}{100.75} = 12.90$$
>
> **[[Arithmetic mean|Arithmetic mean]] P/E:** $(10 + 20)/2 = 15.0$ — too high!
>
> **Weighted [[Arithmetic mean|arithmetic mean]]:** $0.55(10) + 0.45(20) = 14.5$ — still too high
>
> **[[Harmonic mean|Harmonic mean]]:** $2 / (1/10 + 1/20) = 2/0.15 = 13.33$ — closer
>
> **[[Weighted harmonic mean|Weighted harmonic mean]]:** $1 / (0.55/10 + 0.45/20) = 1/0.0775 = 12.90$ — **exact match!**
>
> This is why index providers like S&P use the [[Weighted harmonic mean]] for index-level multiples.

---

## Quick Reference: All Key Formulas

| Formula | Expression |
|---|---|
| **[[Justified Forward P/E]]** | $\frac{P_0}{E_1} = \frac{DPR}{r - g}$ |
| **[[Justified Trailing P/E]]** | $\frac{P_0}{E_0} = \frac{DPR(1 + g)}{r - g}$ |
| **[[Justified P/B]]** | $\frac{P_0}{B_0} = \frac{ROE - g}{r - g}$ |
| **[[Justified P/S]]** | $\frac{P_0}{S_0} = \frac{(E_0/S_0)(1 - RR)(1 + g)}{r - g}$ |
| **[[PEG Ratio]]** | $PEG = \frac{P/E}{g}$ (g in %) |
| **[[Terminal value]]** | $V_n = \text{Benchmark P/E} \times E_n$ |
| **[[Enterprise value]]** | $EV = MV_e + MV_d + MV_{pr} - \text{Cash} - \text{Mkt Securities}$ |
| **[[Normalized EPS]] (Avg EPS)** | $\frac{\sum EPS_i}{n}$ |
| **[[Normalized EPS]] (Avg ROE)** | $\frac{\sum ROE_i}{n} \times BVPS_n$ |
| **[[Harmonic mean]]** | $X_H = \frac{n}{\sum(1/X_i)}$ |
| **[[Weighted harmonic mean]]** | $X_{WH} = \frac{1}{\sum(w_i/X_i)}$ |
| **[[Unexpected earnings]]** | $UE_t = EPS_t - E(EPS_t)$ |
| **[[SUE]]** | $SUE_t = \frac{EPS_t - E(EPS_t)}{\sigma[EPS_t - E(EPS_t)]}$ |

---

## Decision Framework: Which Multiple to Use When?

```
Is the company profitable?
├── YES → Use P/E (most common)
│   ├── Are earnings volatile or cyclical? → Use normalized P/E
│   └── Is there a major acquisition/restructuring? → Use forward P/E
├── NO (negative EPS) → 
│   ├── Is book value meaningful? → Use P/B
│   ├── Is the company generating revenue? → Use P/S
│   └── Is cash flow positive? → Use P/CF
│
Are you comparing companies with different leverage?
├── YES → Use EV/EBITDA (capital structure neutral)
│
Is this a capital-intensive industry?
├── YES → Use EV/EBITDA (controls for D&A differences)
│
Is this a cross-border comparison?
├── YES → Use P/FCFE (least affected by accounting differences)
│       or EV/Sales (capital structure neutral + less accounting noise)
```

---
