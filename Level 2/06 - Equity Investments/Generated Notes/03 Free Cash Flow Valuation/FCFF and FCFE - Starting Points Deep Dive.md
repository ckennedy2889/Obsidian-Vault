---
title: "CFA L2 - FCFF and FCFE Starting Points Deep Dive"
subject: "Equity Investments"
tags: [CFA-L2, equity-valuation, FCFF, FCFE, free-cash-flow, financial-statements]
aliases: ["FCFF Formulas", "FCFE Formulas", "FCFF Starting Points", "FCFE Starting Points"]
---

# FCFF and FCFE — Every Starting Point, From the Ground Up

## The Factory That Explains Everything

We're going to follow one company through every formula: **SteelWorks Inc.**, a factory that makes industrial pipes. Throughout this note, every adjustment you see ties back to something physically happening at this factory — trucks arriving with raw steel, machines wearing out, invoices getting mailed, bank loans getting signed. Nothing is abstract.

Here's SteelWorks' financial data for the year:

| Item | Amount | What actually happened |
|------|--------|----------------------|
| Revenue | $1,000 | Sold pipes to customers |
| COGS | $500 | Bought raw steel, paid factory workers |
| Depreciation | $80 | Machines got older (paper charge — no cash moved) |
| SG&A | $100 | Salaries for salespeople, office rent |
| **EBITDA** | **$400** | $1,000 - $500 - $100 |
| **EBIT** | **$320** | $400 - $80 (depreciation) |
| Interest Expense | $50 | Paid the bank for a loan |
| Pre-tax Income | $270 | $320 - $50 |
| Taxes (30%) | $81 | Wrote a check to the government |
| **Net Income** | **$189** | What the accountant says we "earned" |

Other facts:
- Bought a new pipe-cutting machine for **$150** (capital expenditure)
- Sold an old forklift for **$25** (original book value $20, so **$5 gain** on sale — already in NI above)
- Inventory increased by **$30** (bought extra steel ahead of a big order)
- Accounts receivable increased by **$20** (customers owe us more than before)
- Accounts payable increased by **$15** (we owe our steel supplier more than before)
- Took out a new bank loan for **$100**; repaid **$40** on an old loan → **Net borrowing = $60**
- Tax rate: **30%**

Let's work through every formula.

---

## Part 1: The Four FCFF Starting Points

FCFF is the cash available to **all** investors — equity holders *and* debt holders. It's the "total pie" before any financing decisions. Because it belongs to everyone, it's calculated **before** interest payments leave the building.

---

### FCFF from Net Income

$$\boxed{FCFF = NI + NCC + Int(1-t) - FCInv - WCInv}$$

This is the "long way round." We start at the very bottom of the income statement and *undo* everything that wasn't real cash.

---

#### Adjustment 1: Net Noncash Charges (NCC) → Add Back

**What NCC represents:** Expenses the accountant recorded that *reduced profit on paper* but didn't involve any cash physically leaving the company's bank account. We need to reverse them because we only care about actual cash.

**The components:**

**Depreciation ($80)** — SteelWorks' pipe-cutting machines lose value over time. The accountant spreads the original purchase cost across the machine's useful life. This year, $80 of "wear and tear" was charged as an expense. But here's the thing: **nobody wrote a check for $80 this year**. The cash left the building *years ago* when the machine was originally bought. Depreciation is just an accounting allocation of that old cash payment across time. We add it back.

Real-world picture: the machine is sitting on the factory floor, slightly older. No cash moved. But NI was reduced by $80.

**Amortization** — Same concept as depreciation, but for **intangible assets** like patents, software licenses, or customer lists acquired in a merger. If SteelWorks bought a patent for a pipe-coating process and amortizes it over 10 years, each year's amortization charge is a noncash paper expense — add it back.

**Impairment charges** — Suppose SteelWorks acquired a smaller company years ago and recorded $200 of [[goodwill]]. This year, management realizes that acquisition hasn't worked out, so they "write down" the goodwill by $30. That $30 impairment charge hits the income statement as a loss — but **no cash went anywhere**. The goodwill was always just a balance sheet entry. Add it back.

**Deferred tax changes** — Sometimes the tax bill the accountant calculates (the "tax expense" on the income statement) differs from the actual check written to the government. The difference is a **deferred tax liability** or asset. If the company's tax expense was $81 but they only actually paid $75 in cash, there's a $6 noncash tax charge embedded in NI. That $6 gets added back as part of NCC.

Why does this happen? Timing differences. For example, the government might let SteelWorks depreciate machines *faster* for tax purposes (accelerated depreciation) than the accountant does for financial reporting. So the real tax bill is lower right now, even though the "book" tax expense is higher.

**Gains and losses on asset sales** — SteelWorks sold an old forklift for $25 that had a book value of $20, recording a **$5 gain**. This gain increased Net Income. But here's the problem: the $25 cash from selling the forklift will show up in $FCInv$ (we'll get to that). If we leave the gain in NI *and* count the cash in FCInv, we **double-count** the cash. So we subtract the gain as part of NCC.

Flip it: if they'd sold the forklift for $15 (a **$5 loss**), NI would have been reduced by a loss that didn't represent a cash outflow beyond the actual $15 received. The $15 cash shows up in FCInv. We add the loss back via NCC.

| Noncash charge | Example | Direction | Why |
|---|---|---|---|
| Depreciation | Machine aging | **Add back** | Paper expense, no cash left |
| Amortization | Patent write-off | **Add back** | Paper expense, no cash left |
| Impairment | Goodwill write-down | **Add back** | Balance sheet adjustment, no cash left |
| Deferred tax increase | Tax timing difference | **Add back** | Tax expense > cash tax paid |
| Gain on asset sale | Forklift sold above book | **Subtract** | Avoid double-counting with FCInv |
| Loss on asset sale | Forklift sold below book | **Add back** | Avoid understating cash flow |

For SteelWorks: $NCC = 80\ (depreciation) - 5\ (gain\ on\ sale) = 75$

---

#### Adjustment 2: After-Tax Interest $[Int(1-t)]$ → Add Back

**The logic:** Net Income was calculated *after* subtracting $50 of interest paid to the bank. But FCFF is supposed to represent cash available to *all* investors — including the bank that receives that interest. So we need to "put the interest back in the pie."

**Why after-tax, not pre-tax?** This is the most conceptually tricky part. When SteelWorks paid $50 in interest, that $50 was **tax-deductible**. It reduced taxable income by $50, which saved them $50 × 30% = $15 in taxes. So the true *net* cost of paying that interest was only $50 - $15 = $35.

If we added back the full $50, we'd be overstating FCFF — because $15 of that was a "phantom" cost that was offset by tax savings. The **tax shield** ($15) is real: the government collected less money because of the interest payment. We only add back $Int(1-t) = 50(1-0.30) = $35$.

Real-world picture: SteelWorks wrote a $50 check to the bank. But because of that payment, they wrote a $15 *smaller* check to the government. Net cash impact: $35.

$$Int(1-t) = 50 \times (1 - 0.30) = \$35$$

---

#### Adjustment 3: Fixed Capital Investment (FCInv) → Subtract

**What FCInv is:** Cash spent on long-term physical assets (property, plant, equipment) *net of* any cash received from selling old assets.

$$FCInv = \text{Capital expenditures} - \text{Proceeds from asset sales}$$

SteelWorks bought a new pipe-cutting machine for $150 and sold an old forklift for $25:

$$FCInv = 150 - 25 = \$125$$

**Why we subtract it:** This is real cash leaving the building — a truck showed up with a new machine, and SteelWorks wrote a check for $150. This cash is no longer "free" — it's been invested back into the business. We subtract it because FCFF measures cash available to investors *after* the company has reinvested what it needs to keep operating and growing.

**Why net of proceeds:** The $25 from selling the forklift is cash *coming in*. It partially offsets the capex outflow. We net the two because we want to know: on balance, how much cash went into (or came out of) long-term assets?

> [!tip] Where to Find FCInv
> On the cash flow statement, look in **Cash Flow from Investing Activities**: "Purchases of PP&E" (outflow) and "Proceeds from sale of assets" (inflow). Alternatively: $FCInv = \text{Ending net PP\&E} - \text{Beginning net PP\&E} + \text{Depreciation}$.

---

#### Adjustment 4: Working Capital Investment (WCInv) → Subtract

**What WCInv is:** The change in cash tied up in the company's day-to-day operating cycle. Formally:

$$WCInv = \Delta(\text{Non-cash current assets}) - \Delta(\text{Non-debt current liabilities})$$

This is where the money lives between the time you buy raw materials and the time you collect cash from customers. Let's trace it through SteelWorks:

**Non-cash current assets that increased (cash got trapped):**
- **Inventory +$30**: SteelWorks bought extra steel coils ahead of a big pipe order. Those coils are sitting in the warehouse. The company paid cash for them, but hasn't turned them into revenue yet. That $30 is "trapped" in the warehouse — real cash is gone, but it doesn't show up as an expense yet. We subtract it.
- **Accounts receivable +$20**: SteelWorks delivered pipes worth $20 to a customer who hasn't paid yet. The income statement recorded this as revenue (and it's in NI), but the cash hasn't arrived. We subtract it — NI overstates actual cash received.

**Non-debt current liabilities that increased (cash was saved):**
- **Accounts payable +$15**: SteelWorks received $15 worth of steel from its supplier but hasn't paid the bill yet. This is like an interest-free loan from the supplier — the company has the steel *and* still has the cash. This *reduces* the working capital investment because less cash was needed.

$$WCInv = (30 + 20) - 15 = \$35$$

**Why "non-cash" and "non-debt"?** We exclude cash itself from current assets (obviously — we're trying to measure cash flow, not include cash as a use of cash). We exclude short-term debt from current liabilities because borrowing decisions are financing activities — they belong in the "Net Borrowing" bucket for FCFE, not in operating working capital.

| Working capital item | Change | Cash effect | Treatment |
|---------------------|--------|-------------|-----------|
| Inventory ↑ | +$30 | Cash trapped in warehouse | **Subtract** (use of cash) |
| Accounts receivable ↑ | +$20 | Revenue earned but cash not collected | **Subtract** (use of cash) |
| Accounts payable ↑ | +$15 | Bills owed but not yet paid | **Nets against above** (source of cash) |
| **Net WCInv** | | | **$35** |

> [!warning] WCInv Sign Convention
> An *increase* in working capital is a cash *outflow* (subtract from FCFF). A *decrease* is a cash *inflow* (adds to FCFF). If SteelWorks' customers had paid faster and receivables *fell*, that would be cash flowing *in* — a negative WCInv, which boosts FCFF.

---

#### Putting It All Together

$$FCFF = NI + NCC + Int(1-t) - FCInv - WCInv$$
$$FCFF = 189 + 75 + 35 - 125 - 35 = \mathbf{\$139}$$

What this means: SteelWorks generated $139 of real, spendable cash that belongs to both its shareholders and its bank — after all operating costs, after reinvesting in the business, after building up inventory. This is the "total pie."

---

### FCFF from EBIT

$$\boxed{FCFF = EBIT(1-t) + Dep - FCInv - WCInv}$$

**Why this works:** EBIT (Earnings Before Interest and Taxes) sits *above* interest expense on the income statement. Interest hasn't been subtracted yet — it's still in the number. So we don't need to add it back. That eliminates one adjustment entirely.

**The hypothetical tax: $EBIT(1-t)$**

This is the part that confuses people. We're *not* saying the company actually paid $EBIT \times t$ in taxes. We're asking: "What *would* the tax bill be if this company had zero debt?"

A company with no debt has no interest deduction, so its entire EBIT would be taxable. By computing $EBIT(1-t)$, we get the **after-tax operating income of an unlevered firm** — also called **NOPAT** (Net Operating Profit After Tax). This is the "clean" operating cash flow before any financing decisions.

$$EBIT(1-t) = 320 \times (1-0.30) = \$224$$

**Why add depreciation back separately?** EBIT was calculated *after* subtracting depreciation ($EBITDA - Dep = EBIT$). Since depreciation is a noncash charge, we add it back — same reason as in the NI formula.

$$FCFF = 224 + 80 - 125 - 35 = \mathbf{\$144}$$

> [!note] Why Doesn't This Match Exactly?
> The small difference from the NI method ($139 vs $144) occurs because the NI method properly handles the gain on asset sale, and this simplified EBIT example doesn't separately adjust for it. In practice, if you handle all noncash items consistently, both methods produce the same FCFF. The gain on sale ($5) and its tax effect ($5 × 0.30 = $1.50) would reconcile the two.

**When to use this starting point:** When you want a clean picture of *operating* performance, independent of capital structure. This is the preferred starting point for many analysts because EBIT is a "capital-structure-neutral" number — two companies with identical operations but different debt levels will have the same EBIT.

---

### FCFF from EBITDA

$$\boxed{FCFF = EBITDA(1-t) + Dep \times t - FCInv - WCInv}$$

**Why this looks strange:** EBITDA already has depreciation added back (that's the "DA" in EBITDA). So when we tax EBITDA, we're *over-taxing* — we're computing taxes as if depreciation didn't exist as a deduction. But in reality, depreciation *does* reduce the company's tax bill. We need to give credit for that tax saving.

**The depreciation tax shield: $Dep \times t$**

Every dollar of depreciation the accountant records reduces taxable income by one dollar, which saves the company $t cents in taxes. For SteelWorks:

$$\text{Dep tax shield} = 80 \times 0.30 = \$24$$

This $24 is *real cash* that stayed in SteelWorks' bank account because the government said "since your machines are wearing out, you owe us $24 less in taxes." The machine didn't actually cost $24 this year — but the tax savings is real.

**The algebra (proving it's identical to the EBIT formula):**

$$EBITDA(1-t) + Dep \times t$$
$$= (EBIT + Dep)(1-t) + Dep \times t$$
$$= EBIT(1-t) + Dep(1-t) + Dep \times t$$
$$= EBIT(1-t) + Dep - Dep \times t + Dep \times t$$
$$= EBIT(1-t) + Dep \checkmark$$

The two formulas are *algebraically identical*. They differ only in which line of the income statement you start from.

$$FCFF = 400(1-0.30) + 80(0.30) - 125 - 35$$
$$= 280 + 24 - 125 - 35 = \mathbf{\$144}$$

**When to use this starting point:** When EBITDA is the number you're given (common in LBO analysis, credit analysis, and when comparing firms across different tax jurisdictions and depreciation policies).

---

### FCFF from CFO (Cash Flow from Operations)

$$\boxed{FCFF = CFO + Int(1-t) - FCInv}$$

**Why this is the simplest formula:** The [[cash flow statement]] has already done most of the work for you. CFO starts with Net Income and adjusts for:
- All noncash charges (depreciation, amortization, impairments, deferred taxes) ✓
- All working capital changes (inventory, receivables, payables) ✓
- Gains/losses on asset sales ✓

So $NCC$ and $WCInv$ are already handled. You only need two more adjustments:
1. **Add back after-tax interest** — because CFO was computed after interest was paid (under US GAAP), but FCFF is pre-debt
2. **Subtract FCInv** — because capital expenditures show up in the *investing* section of the cash flow statement, not in CFO

Real-world picture: you open the company's cash flow statement, find "Cash from Operations," add back what the bank got (net of tax savings), and subtract what went into new machines. Done.

> [!danger] IFRS vs. US GAAP Trap
> This is one of the most tested traps on the exam.
> 
> **US GAAP:** Interest paid is *always* classified in CFO. So it's already been subtracted from CFO. You **must** add $Int(1-t)$ back.
> 
> **IFRS:** Companies can *choose* to classify interest paid in either CFO or CFF (Cash Flow from Financing). If the company puts interest in **financing activities**, then CFO was never reduced by interest — and you should **not** add it back. If they put it in **operating activities** (the more common choice), then the same US GAAP treatment applies.
> 
> **Always check the classification.** If the exam specifies "interest paid is classified as a financing activity under IFRS," then: $FCFF = CFO - FCInv$ (no interest adjustment needed).

> [!warning] Another CFO Trap: Dividends Received and Interest Received
> Under IFRS, dividends and interest *received* can be classified in either operating or investing activities. If they're in CFO but you're trying to get a "clean" operating FCFF, you might need to remove them. US GAAP requires interest and dividends received in CFO, which is usually fine for FCFF since they're operating items for financial companies.

---

## Part 2: The Three FCFE Starting Points

FCFE is the cash left over **for equity holders only** — after all operating costs, reinvestment, *and* after the bank has been paid. It's the residual. The "what's left for the owners after everyone else is served" number.

---

### FCFE from FCFF

$$\boxed{FCFE = FCFF - Int(1-t) + \text{Net Borrowing}}$$

**The logic in one sentence:** Start with the total pie (FCFF), remove the bank's slice (after-tax interest), and add any new money the bank loaned in (net borrowing).

**Why subtract after-tax interest?** FCFF includes cash that belongs to the bank. To isolate the equity holders' portion, we remove the interest cost — again, after-tax, because the tax shield is a real benefit to the firm.

**What is Net Borrowing?**

$$\text{Net Borrowing} = \text{New debt issued} - \text{Debt principal repaid}$$

SteelWorks took out a $100 loan and repaid $40 on an existing loan:

$$\text{Net Borrowing} = 100 - 40 = \$60$$

**Why add net borrowing?** When the company borrows $100, that cash flows into the firm. Even though it creates a future obligation, *right now* it's cash that's available. From the equity holder's perspective, the borrowed money funds investments that would otherwise consume equity cash. If SteelWorks borrows $100 to buy a machine, that's $100 the shareholders *didn't* have to put up.

When the company repays $40, that's cash flowing *out* to the bank — cash that can't go to shareholders.

$$FCFE = 139 - 35 + 60 = \mathbf{\$164}$$

---

### FCFE from Net Income

$$\boxed{FCFE = NI + NCC - FCInv - WCInv + \text{Net Borrowing}}$$

**Compare this to FCFF from NI:** The only differences are:
1. **No $Int(1-t)$ add-back** — Net Income already deducted interest. For FCFE, we *want* interest deducted because equity holders only get what's left after the bank is paid. So we leave it out.
2. **Add Net Borrowing** — New debt provides cash; repayment consumes cash.

$$FCFE = 189 + 75 - 125 - 35 + 60 = \mathbf{\$164}$$

> [!tip] Memory Hook: FCFF from NI vs. FCFE from NI
> The formulas are almost twins. FCFF adds back interest (because it's the total pie). FCFE skips interest (because the bank is already paid) but adds net borrowing (because borrowed cash is available to equity).
>
> ```
> FCFF = NI + NCC + Int(1-t) - FCInv - WCInv
> FCFE = NI + NCC             - FCInv - WCInv + Net Borrowing
>                ↑                                    ↑
>          interest IN                          borrowing IN
>        (bank's share                       (bank's new
>         still in pie)                        cash infusion)
> ```

---

### FCFE from CFO

$$\boxed{FCFE = CFO - FCInv + \text{Net Borrowing}}$$

**The simplest formula of all.** CFO already handles noncash charges, working capital, *and* interest (under US GAAP, interest is included in CFO, so it's already deducted — which is what we want for FCFE).

All that's left:
- Subtract **FCInv** (capex isn't in CFO — it's in investing activities)
- Add **Net Borrowing** (debt issuance/repayment is in financing activities)

**When to use:** When you have a clean cash flow statement and want the fastest path to FCFE.

---

## The Complete SteelWorks Summary

```
┌─────────────────────────────────────────────────────────────────┐
│                    SteelWorks Inc. — FCFF                        │
├─────────────────────────────────────────────────────────────────┤
│ From NI:   189 + 75 + 35 − 125 − 35           = $139           │
│ From EBIT: 224 + 80 − 125 − 35                = $144*          │
│ From EBITDA: 280 + 24 − 125 − 35              = $144*          │
│ From CFO:  (would need CFO from cash flow stmt)                 │
├─────────────────────────────────────────────────────────────────┤
│ *Slight difference due to gain-on-sale handling                 │
├─────────────────────────────────────────────────────────────────┤
│                    SteelWorks Inc. — FCFE                        │
├─────────────────────────────────────────────────────────────────┤
│ From FCFF: 139 − 35 + 60                      = $164           │
│ From NI:   189 + 75 − 125 − 35 + 60           = $164           │
│ From CFO:  (would need CFO from cash flow stmt)                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## The Accounting Connection Map

Every FCFF/FCFE adjustment traces back to a specific place on the financial statements:

```
INCOME STATEMENT                 BALANCE SHEET              CASH FLOW STATEMENT
┌─────────────────┐          ┌──────────────────┐         ┌─────────────────────┐
│ Revenue          │          │ ASSETS            │         │ CFO                 │
│ − COGS           │          │  Cash             │         │  (NI + NCC − WCInv) │
│ − Dep (→NCC)     │──────────│  A/R (→WCInv)     │─────────│                     │
│ − SGA            │          │  Inventory(→WCInv)│         │ CFI                 │
│ = EBIT           │          │  PP&E (→FCInv)    │         │  (−Capex + Proceeds)│
│ − Interest(→add  │          │                   │         │  = −FCInv           │
│   back for FCFF) │          │ LIABILITIES       │         │                     │
│ − Tax            │          │  A/P (→WCInv)     │         │ CFF                 │
│ = Net Income     │          │  Debt (→Net Borr.) │         │  (Net Borrowing)    │
└─────────────────┘          └──────────────────┘         └─────────────────────┘
```

| FCFF/FCFE Term | Financial Statement Source | Line Item |
|---|---|---|
| Net Income | Income Statement | Bottom line |
| EBIT | Income Statement | Operating profit |
| EBITDA | Income Statement | EBIT + Dep & Amort |
| Depreciation (NCC) | Income Statement / CF Statement | Expense line or CFO add-back |
| Interest expense | Income Statement | Below EBIT |
| Tax rate | Income Statement | Tax expense ÷ pre-tax income |
| FCInv (capex) | CF Statement — Investing | "Purchase of PP&E" |
| Proceeds from sales | CF Statement — Investing | "Proceeds from sale of assets" |
| WCInv | Balance Sheet (comparative) | Δ in current assets − Δ in current liabilities |
| Net Borrowing | CF Statement — Financing | "Proceeds from debt" − "Repayment of debt" |
| CFO | CF Statement — Operating | First subtotal |

---

## Exam Traps: The Complete List

> [!danger] Critical Traps
> 
> **1. After-tax interest, not pre-tax**
> Always $Int \times (1-t)$. Pre-tax interest overstates FCFF because it ignores the tax shield.
> 
> **2. Gains/losses on asset sales**
> Gains must be *subtracted* from NCC (or they'll be double-counted with FCInv proceeds). Losses must be *added back*.
> 
> **3. FCInv is net of proceeds**
> $FCInv = \text{Capex} - \text{Proceeds from asset sales}$. Don't just use gross capex.
> 
> **4. WCInv excludes cash and short-term debt**
> Cash is what we're measuring. Short-term debt is a financing item (goes in net borrowing for FCFE).
> 
> **5. WCInv sign: increase = subtract**
> Rising inventory or receivables *consume* cash. Rising payables *save* cash.
> 
> **6. FCFE from NI: NO interest add-back**
> Interest is already deducted in NI, and FCFE *should* be after interest. Don't add it back.
> 
> **7. IFRS interest classification**
> Under IFRS, if interest paid is in financing activities (not CFO), do *not* add it back when computing FCFF from CFO — it was never subtracted.
> 
> **8. Net borrowing includes only debt, not equity**
> Share issuance does not affect FCFF or FCFE. Net borrowing = new debt issued − debt repaid.
> 
> **9. EBITDA formula: $Dep \times t$, not $Dep$**
> From EBITDA, you add back only the *tax shield*, not the full depreciation — because EBITDA never subtracted depreciation in the first place.
> 
> **10. Preferred dividends**
> If Net Income is "Net Income available to common," preferred dividends have already been deducted. Add them back (after tax) for FCFF since preferred holders are capital providers too.

---

## Related Concepts

- [[Free Cash Flow Valuation]] — the valuation models that use these formulas
- [[WACC]] — discount rate for FCFF
- [[Cost of Equity]] — discount rate for FCFE
- [[Depreciation]] — the largest NCC in most companies
- [[Working Capital]] — the operating cycle that drives WCInv
- [[Deferred Tax]] — creates timing differences between book and cash taxes
- [[Goodwill]] — subject to impairment (a common NCC)
- [[Cash Flow Statement]] — where CFO, FCInv, and Net Borrowing live
