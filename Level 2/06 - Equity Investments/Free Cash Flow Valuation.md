---
title: "CFA L2 - Free Cash Flow Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity-valuation, FCFF, FCFE, DCF, free-cash-flow]
aliases: ["FCF Valuation", "FCFF Valuation", "FCFE Valuation", "Free Cash Flow Models"]
---

# Free Cash Flow Valuation

## The Story: Why Cash Is King

Imagine you're buying a small business — say, a bakery. The owner shows you the accounting books: "We made $200,000 in profit last year!" Impressive, right? But then you ask, "So how much *actual cash* did the bakery generate that the owner could take home?" Turns out, after buying a new oven ($80,000), building up flour [[Inventory|inventory]] ($15,000), and paying back a bank loan ($30,000), the owner really only had $75,000 of *free cash* to pocket.

That's the difference between **[[Accounting profit|accounting profit]]** and **[[Free cash flow|free cash flow]]**. Profit is a story told by accounting rules. [[Free cash flow|Free cash flow]] is the hard cash left over after a business has paid for everything it needs to keep running and growing. When we value a company, we don't care about accounting tricks — we care about the real cash investors can extract.

[[Free cash flow|Free cash flow]] [[Valuation|valuation]] is the workhorse of professional equity analysis. It works for companies that don't pay dividends, companies that pay erratic dividends, and companies where the analyst wants to take a "what if I owned the whole thing?" perspective.

---

## FCFF vs. FCFE: Two Flavors of Free Cash Flow

There are two ways to slice the "free cash" pie, depending on whose perspective you're taking.

### Free Cash Flow to the Firm (FCFF)

**FCFF** is the total cash available to *everyone* who funded the business — both the **stockholders** (equity investors) and the **bondholders/lenders** (debt investors). Think of it as the cash the business generates before deciding how to split it between the bank and the owners.

Because FCFF belongs to all capital providers, it is calculated **before** interest payments are made. To value the whole firm using FCFF, you discount at the **[[WACC]]** ([[Weighted average cost of capital|Weighted Average Cost of Capital]]al|Cost of Capital]]) — the blended cost of all the firm's capital.

$$\text{Firm Value} = \sum \frac{FCFF_t}{(1 + WACC)^t}$$

To get **equity value** from firm value:

$$\text{Equity Value} = \text{Firm Value} - \text{Market Value of Debt}$$

### Free Cash Flow to Equity (FCFE)

**FCFE** is the cash left over *just for equity holders* after the company has:
- Paid all operating expenses
- Made all necessary capital investments
- Paid interest and [[Principal|principal]] to lenders

It's the residual — what flows to shareholders after everyone else has been served. To value equity directly using FCFE, you discount at the **[[Cost of equity|cost of equity]]** ($r$), not WACC.

$$\text{Equity Value} = \sum \frac{FCFE_t}{(1 + r)^t}$$

### Side-by-Side Comparison

| | FCFF | FCFE |
|---|---|---|
| Cash available to | All investors (debt + equity) | Equity holders only |
| [[Discount rate|Discount rate]] | [[WACC]] | [[Cost of equity]] ($r$) |
| Produces | Firm (enterprise) value | Equity value directly |
| Interest treatment | Calculated *before* debt payments | Calculated *after* debt payments |
| To get equity value | Subtract debt from firm value | Already equity value |
| Best for | Levered companies, changing [[Capital structure|capital structure]] | Stable [[Capital structure|capital structure]] |

> [!tip] The Ownership Perspective
> FCFE represents what a company *could* pay as dividends — its **dividend-paying capacity** — not what it actually pays. If you bought the entire company, FCFE is the cash you could extract. This is why FCFE is the "control" perspective: a majority owner would have access to the full FCFE, even if the board currently chooses to retain most of it.

---

## Calculating FCFF: Four Starting Points

Analysts arrive at FCFF from different places on the financial statements. Each formula makes adjustments to undo accounting distortions and isolate true cash generation.

### Starting from Net Income

$$\boxed{FCFF = NI + NCC + Int(1-t) - FCInv - WCInv}$$

| Term | What it is | Why we adjust |
|------|-----------|---------------|
| $NI$ | [[Net income|Net income]] | Starting point — [[Accounting profit|accounting profit]] after all expenses and taxes |
| $NCC$ | Net noncash charges ([[Depreciation|depreciation]], amortization, impairments) | Add back: these reduced NI on paper but no cash left the building |
| $Int(1-t)$ | After-tax interest expense | Add back: NI already deducted interest, but FCFF is pre-debt. We use after-tax because interest created a real tax shield |
| $FCInv$ | Fixed capital investment (capex net of asset sales) | Subtract: cash spent on new PP&E. $FCInv = \text{Capex} - \text{Proceeds from sales}$ |
| $WCInv$ | [[Working capital|Working capital]] investment (change in non-cash [[Current assets|current assets]] minus change in non-debt [[Current liabilities|current liabilities]]es|liabilities]]) | Subtract: cash absorbed by growing [[Inventory|inventory]], receivables, etc. |

**Why after-tax interest?** Interest expense in the [[Income statement|income statement]] reduced [[Taxable income|taxable income]], creating a tax saving. If we add back the *full* interest, we'd overstate FCFF because that tax saving was real. So we add back only $Int \times (1 - t)$ — the net cash cost of interest.

**What counts as NCC?** Primarily [[Depreciation]] and [[amortization]]. Also: [[Impairment|impairment]] charges, losses on asset sales (add back), gains on asset sales (subtract), deferred tax changes, and amortization of bond discount/premium. The key test: did cash actually move? If not, undo it.

> [!warning] Noncash Charge Traps
> - **[[Restructuring|Restructuring]] charges**: Add back the noncash portion, but [[Restructuring|restructuring]] *cash* payments are real — don't add those back.
> - **Gains on sale**: These *increased* NI but the actual cash from the sale shows up in $FCInv$. Subtract the gain from NCC to avoid double-counting.
> - **Losses on sale**: These *decreased* NI but the actual cash is already in $FCInv$. Add the loss back via NCC.

---

### Starting from EBIT

$$\boxed{FCFF = EBIT(1-t) + Dep - FCInv - WCInv}$$

EBIT is already *before* interest, so we don't need to add interest back. We just tax it (as if the firm had no debt), then add back [[Depreciation|depreciation]] (the main noncash charge embedded in EBIT), and subtract capital spending and [[Working capital|working capital]] changes.

This formula is popular because it cleanly separates operating performance from [[Capital structure|capital structure]] decisions.

---

### Starting from EBITDA

$$\boxed{FCFF = EBITDA(1-t) + Dep \times t - FCInv - WCInv}$$

EBITDA already excludes [[Depreciation|depreciation]], so when we tax EBITDA we *over-tax* it (because in reality, [[Depreciation|depreciation]] shields some income from taxes). The $Dep \times t$ term adds back just the **tax shield** — the tax savings that depreciation provides.

**Why the formula looks weird:** $EBITDA(1-t) + Dep \times t$ is mathematically identical to $(EBITDA - Dep)(1-t) + Dep = EBIT(1-t) + Dep$. It's just rearranged.

---

### Starting from CFO (Cash Flow from Operations)

$$\boxed{FCFF = CFO + Int(1-t) - FCInv}$$

CFO already incorporates noncash charges and [[Working capital|working capital]] changes (the accounting standard requires these adjustments in the cash flow statement). So we only need to:
- Add back after-tax interest (because CFO is computed *after* interest under most accounting standards)
- Subtract fixed capital investment

This is the simplest path when you have a clean cash flow statement.

---

## Calculating FCFE: Three Starting Points

FCFE starts from FCFF and subtracts what goes to debt holders, or starts from NI/CFO and adds net borrowing.

### Starting from FCFF

$$\boxed{FCFE = FCFF - Int(1-t) + \text{Net Borrowing}}$$

Take the total cash pie (FCFF), remove the after-tax interest paid to lenders, and add any new debt raised (net of repayments). What's left belongs to equity.

**Net Borrowing** = New debt issued − Debt [[Principal|principal]] repaid. If the company borrows $100M and repays $40M, net borrowing = $60M.

---

### Starting from Net Income

$$\boxed{FCFE = NI + NCC - FCInv - WCInv + \text{Net Borrowing}}$$

Notice the difference from the FCFF formula: **no $Int(1-t)$ add-back**. That's because NI already deducted interest — and FCFE is *after* debt payments, so we *want* interest deducted.

We add net borrowing because new debt provides cash to equity holders (even though it's borrowed, the cash is available to the firm and thus to equity after debt service).

---

### Starting from CFO

$$\boxed{FCFE = CFO - FCInv + \text{Net Borrowing}}$$

Simplest of all. CFO handles noncash charges and [[Working capital|working capital]]. Just subtract capex and add net borrowing.

---

## Quick-Reference Formula Table

```
┌─────────────────────────────────────────────────────────────┐
│                     FCFF FORMULAS                           │
├─────────────────────────────────────────────────────────────┤
│ From NI:     NI + NCC + Int(1−t) − FCInv − WCInv           │
│ From EBIT:   EBIT(1−t) + Dep − FCInv − WCInv               │
│ From EBITDA: EBITDA(1−t) + Dep×t − FCInv − WCInv           │
│ From CFO:    CFO + Int(1−t) − FCInv                         │
├─────────────────────────────────────────────────────────────┤
│                     FCFE FORMULAS                           │
├─────────────────────────────────────────────────────────────┤
│ From FCFF:   FCFF − Int(1−t) + Net Borrowing                │
│ From NI:     NI + NCC − FCInv − WCInv + Net Borrowing       │
│ From CFO:    CFO − FCInv + Net Borrowing                     │
└─────────────────────────────────────────────────────────────┘
```

> [!tip] Memory Hook: FCFF → FCFE
> FCFF is the *whole pie*. To get FCFE, **take away** the lender's slice (after-tax interest) and **add back** any new money borrowed (net borrowing). The pattern is always: remove debt costs, add debt inflows.

---

## How Business Decisions Affect FCFF and FCFE

This is a critical conceptual distinction and a frequent exam trap.

| Action | Effect on FCFF | Effect on FCFE |
|--------|---------------|----------------|
| **Pay dividends** | No effect | No effect |
| **Share repurchases** | No effect | No effect |
| **Issue new shares** | No effect | No effect |
| **Take on new debt** | No effect | ↑ in year of borrowing; ↓ in future years (interest + repayment) |
| **Repay debt** | No effect | ↓ in year of repayment |
| **Increase capex** | ↓ | ↓ |

**Why dividends and buybacks don't affect either:** They are *uses* of free cash flow, not determinants of it. FCFF and FCFE measure cash *generation*, not cash *distribution*. Whether the company pays a $1B dividend or sits on the cash, the FCFF and FCFE numbers are identical.

**Why debt changes don't affect FCFF but do affect FCFE:** FCFF is calculated before any debt decisions — it's the pre-financing cash flow. Debt is a financing choice that redistributes FCFF between debt and equity holders. FCFE, being the residual after debt service, is directly impacted by leverage changes.

> [!warning] Exam Trap: Leverage and FCFE
> Increasing leverage *increases* FCFE in the short term (cash inflow from borrowing) but *decreases* future FCFE (higher interest payments and eventual principal repayments). Over the full life of the debt, the present value nets out to zero — leverage reshuffles timing, it doesn't create free cash flow.

---

## FCFE vs. Dividend Discount Model (DDM)

If both models discount cash flows to equity, when do you use which?

| | DDM | FCFE Model |
|---|---|---|
| Discounts | Actual dividends paid | Potential dividends (cash available) |
| Perspective | Minority shareholder | Control/takeover perspective |
| Best when | Stable, predictable dividend history | Non-dividend payers, or dividends ≠ capacity |
| Problem | Ignores retained cash | Requires forecasting capex, WC, borrowing |

**When FCFE ≠ Dividends:** Companies routinely pay *less* than their FCFE — they accumulate cash, make acquisitions, or repay debt. For a minority investor who can't force a payout change, the DDM may be more relevant. For someone evaluating a takeover, FCFE is the right measure because the acquirer controls the cash.

**When FCFE ≈ Dividends:** Mature "dividend machines" — utilities, REITs, consumer staples — where payout ratios are high and stable. Here, DDM and FCFE models converge.

---

## Why Net Income and EBITDA Are Poor Cash Flow Proxies

### Net Income's Blind Spots

Net income includes noncash charges (depreciation, impairments), excludes capital expenditures entirely, and ignores working capital changes. A company can report rising net income while its actual cash generation is collapsing — because it's spending massively on new equipment or tying cash up in inventory.

$$\text{NI} \neq \text{Cash flow because: NI includes noncash items and excludes real cash outlays}$$

### EBITDA's Blind Spots

EBITDA is even more misleading as a cash proxy:
- **Ignores taxes** — taxes are very real cash outflows
- **Ignores capex** — a capital-intensive business might have massive required reinvestment
- **Ignores working capital** — growing companies often consume large amounts of cash in receivables and inventory
- **Doesn't equal cash from operations** — EBITDA is a *profit* metric, not a *cash flow* metric

> [!danger] The EBITDA Trap
> EBITDA was originally designed as a quick-and-dirty measure of a firm's ability to service debt. It was *never* meant to proxy for free cash flow. Two companies with identical EBITDA can have wildly different free cash flows if one is capital-light (a software company) and the other is capital-heavy (an airline). Using EBITDA as a valuation shortcut systematically overvalues capital-intensive businesses.

---

## Valuation Models

### Single-Stage (Stable-Growth) Models

For mature companies growing at a constant rate forever — the [[Gordon Growth Model]] applied to free cash flows instead of dividends.

**FCFF version:**

$$\text{Firm Value} = \frac{FCFF_1}{WACC - g}$$

**FCFE version:**

$$\text{Equity Value} = \frac{FCFE_1}{r - g}$$

Where $FCFF_1$ or $FCFE_1$ is next year's expected free cash flow, and $g$ is the perpetual growth rate (which must be ≤ long-term nominal GDP growth).

**When to use:** The company is already mature, growing at or below the economy's rate, with stable margins, capex roughly equal to depreciation, and a settled capital structure.

---

### Two-Stage Models

Company grows fast for a defined period, then abruptly shifts to stable growth forever.

$$\text{Firm Value} = \sum_{t=1}^{n} \frac{FCFF_t}{(1+WACC)^t} + \frac{TV_n}{(1+WACC)^n}$$

Where the **terminal value** at year $n$ is:

$$TV_n = \frac{FCFF_{n+1}}{WACC - g_L}$$

The same structure applies to FCFE models, substituting $r$ for $WACC$.

**When to use:** Company has a clear, identifiable high-growth phase (patent protection, first-mover advantage) with a definable end date, after which growth normalizes.

---

### Three-Stage Models

Growth → Transition → Maturity. The middle "transition" phase can use the [[Level 2/Generated Notes/06 - Equity Investments/H-Model]] concept (linearly declining growth) or explicit year-by-year forecasts.

**When to use:** Young companies with high current growth that will gradually decelerate as the market matures and competition intensifies. Most realistic for high-growth tech, biotech, or emerging-market companies.

### Model Selection Guide

| Company Stage | Growth Pattern | Model |
|--------------|----------------|-------|
| Mature, stable | Constant $g$ ≈ GDP | Single-stage |
| High growth with clear end | Fast then sudden drop | Two-stage |
| High growth fading gradually | Fast → transition → stable | Three-stage / H-Model |

---

## Terminal Value

Terminal value typically dominates total valuation — often **60–90%** of total firm value. This makes its calculation critical.

### Approach 1: Gordon Growth (Perpetuity)

$$TV_n = \frac{FCF_{n+1}}{r^* - g_L}$$

Where $r^*$ is WACC (for FCFF) or $r$ (for FCFE), and $g_L$ is the long-term stable growth rate.

**Advantage:** Grounded in fundamentals.
**Risk:** Extremely sensitive to $r^*$ and $g_L$ — a 0.5% change in either can swing terminal value by 20%+.

### Approach 2: Exit Multiple

$$TV_n = FCF_n \times \text{Multiple}$$

Or more commonly: $TV_n = EBITDA_n \times \text{EV/EBITDA multiple}$.

**Advantage:** Market-based, easy to benchmark.
**Risk:** Circular — you're using market multiples to estimate "intrinsic" value.

---

## Sensitivity Analysis

Because FCF valuations depend heavily on forecasted inputs, analysts routinely stress-test the key assumptions.

**The inputs that matter most:**

1. **Growth rate ($g$)** — especially the terminal growth rate, because it affects the massive terminal value
2. **Discount rate ($WACC$ or $r$)** — small changes produce large valuation swings when $g$ is close to the discount rate
3. **Terminal value assumptions** — since TV is 60–90% of total value, the terminal growth rate and exit multiple are the single biggest "lever"
4. **Capex and working capital** — determine how much of operating cash flow actually becomes free cash flow

Analysts typically present a **sensitivity table** showing value across a range of growth rate and WACC assumptions:

```
                    WACC
              8%     9%     10%    11%
g = 3%     $85    $72    $62    $54
g = 4%     $98    $80    $68    $59
g = 5%     $120   $92    $76    $64
g = 6%     $160   $110   $86    $71
```

Notice how value explodes when $g$ approaches $WACC$ (bottom-left) — the model becomes unstable. This is inherent to all [[Perpetuity|perpetuity]]-based models.

---

## Valuation Decision: Over/Under/Fairly Valued

The decision framework is identical to DDM:

$$\text{Intrinsic Value} > \text{Market Price} \Rightarrow \text{Undervalued (Buy)}$$
$$\text{Intrinsic Value} < \text{Market Price} \Rightarrow \text{Overvalued (Sell/Avoid)}$$
$$\text{Intrinsic Value} \approx \text{Market Price} \Rightarrow \text{Fairly Valued}$$

For FCFF models, remember the extra step:

$$\text{Equity Value per Share} = \frac{\text{Firm Value} - \text{Debt} + \text{Cash}}{Shares\ Outstanding}$$

---

## Worked Example: FCFF Calculation and Two-Stage Valuation

### Part A — Calculate FCFF from Net Income

**Company data (millions):**
- Net Income: $240
- Depreciation: $300
- Interest Expense: $100
- Tax Rate: 40%
- Capital Expenditures: $400
- Working Capital Increase: $45

$$FCFF = NI + Dep + Int(1-t) - FCInv - WCInv$$
$$FCFF = 240 + 300 + 100(1-0.40) - 400 - 45$$
$$FCFF = 240 + 300 + 60 - 400 - 45 = \mathbf{\$155M}$$

### Part B — Calculate FCFE from FCFF

**Additional data:** Net Borrowing = $75M

$$FCFE = FCFF - Int(1-t) + \text{Net Borrowing}$$
$$FCFE = 155 - 60 + 75 = \mathbf{\$170M}$$

### Part C — Two-Stage FCFF Valuation

**Cool-Tech Inc.**
- Current FCFF: $100M
- Stage 1 growth: 20% for 2 years
- Stage 2 growth: 5% forever
- WACC: 10%
- Debt: $500M
- Shares outstanding: 50M

**Step 1 — Forecast high-growth cash flows.**

| Year | FCFF |
|------|------|
| 1 | $100 × 1.20 = $120M |
| 2 | $120 × 1.20 = $144M |

**Step 2 — Terminal value at end of Year 2.**

$$TV_2 = \frac{FCFF_3}{WACC - g_L} = \frac{144 \times 1.05}{0.10 - 0.05} = \frac{151.2}{0.05} = \$3{,}024M$$

**Step 3 — Discount everything to today.**

$$PV(Year\ 1) = \frac{120}{1.10^1} = \$109.09M$$

$$PV(Year\ 2 + TV) = \frac{144 + 3{,}024}{1.10^2} = \frac{3{,}168}{1.21} = \$2{,}618.18M$$

$$\text{Firm Value} = 109.09 + 2{,}618.18 = \mathbf{\$2{,}727.27M}$$

**Step 4 — Find equity value and per-share value.**

$$\text{Equity Value} = 2{,}727.27 - 500 = \$2{,}227.27M$$

$$\text{Value per Share} = \frac{2{,}227.27}{50} = \mathbf{\$44.55}$$

If Cool-Tech trades at $38, it's undervalued. At $52, it's overvalued.

> [!warning] [[Terminal value|Terminal Value]] [[Dominance|Dominance]]
> In this example, $TV_2 = \$3{,}024M$ — and its present value ($2{,}503M$) is 92% of the total firm value. This is typical. Always sanity-check whether the terminal growth rate and exit assumptions are reasonable, because they drive almost everything.

---

## Exam Traps Summary

> [!danger] Watch Out For These
> - **FCFF uses WACC; FCFE uses $r$ ([[Cost of equity|cost of equity]])** — don't mix [[Discount rates|discount rates]].
> - **After-tax interest**: Always $Int(1-t)$. If you add back pre-tax interest to get FCFF, you'll overstate it.
> - **Dividends don't affect FCFF or FCFE**: They are *uses* of cash, not determinants.
> - **Debt affects FCFE but not FCFF**: New borrowing increases FCFE; FCFF is capital-structure neutral.
> - **NI ≠ FCFF**: Never use [[Net income|net income]] as a proxy for cash flow. The adjustments exist for a reason.
> - **EBITDA ≠ FCFF**: EBITDA ignores taxes, capex, and working capital — three of the biggest cash items.
> - **[[Terminal value|Terminal value]] [[Dominance|dominance]]**: TV is typically 60–90% of firm value. A small error in $g_L$ or WACC is amplified enormously.
> - **Firm value → Equity value**: When using FCFF models, you *must* subtract debt to get equity value. Easy to forget under exam pressure.
> - **$FCFF_1$ not $FCFF_0$**: [[Valuation|Valuation]] models use *next year's* cash flow. Grow current FCF by $(1+g)$ first.

---

## Related Concepts

- [[WACC]] — [[Discount rate|discount rate]] for FCFF models
- [[Cost of equity]] — [[Discount rate|discount rate]] for FCFE models
- [[Gordon Growth Model]] — foundation of [[Terminal value|terminal value]] calculation
- [[Discounted Dividend Valuation]] — the DDM alternative to FCF
- [[Level 2/Generated Notes/06 - Equity Investments/H-Model]] — transition growth concept applicable to three-stage FCF models
- [[Depreciation]] — the largest noncash charge in most FCFF calculations
- [[Working capital]] — the WCInv adjustment
- [[PVGO]] — connects FCF-based value to growth opportunities
- [[Justified Leading and Trailing PE]] — [[Price multiples|price multiples]] derived from similar [[Fundamentals|fundamentals]]
