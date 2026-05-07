---
title: "CFA L2 - Cash Flow from Operations (CFO)"
subject: "Financial Statement Analysis"
tags: [CFA-L2, cash-flow, CFO, financial-statements, indirect-method, direct-method]
aliases: ["CFO", "Cash Flow from Operations", "Operating Cash Flow", "Cash from Operations"]
---

# Cash Flow from Operations (CFO)

## The Restaurant That Reveals Everything

Imagine you own a restaurant. At the end of the month, your accountant tells you: "Congratulations, you made $50,000 in profit!" But when you check your bank account, there's only $28,000 more than last month. Where did the other $22,000 go?

The answer is buried in the gap between **accounting profit** and **actual cash**. Maybe you bought $8,000 worth of extra wine inventory that's sitting in the cellar. Maybe a corporate client ran up a $6,000 tab that they haven't paid yet. Maybe you owe your meat supplier $3,000 less than before because you paid them early. And your accountant recorded $11,000 of "depreciation" on your kitchen equipment — an expense that reduced your profit but didn't involve writing a single check.

**Cash Flow from Operations (CFO)** is the number that bridges this gap. It answers the question: "How much *actual cash* did the business generate from doing what it does — serving food, selling widgets, writing software — before any investing or financing decisions?"

CFO strips away the accounting fictions and balance sheet movements to reveal the raw cash-generating power of the core business.

---

## Where CFO Sits in the Cash Flow Statement

The [[cash flow statement]] splits all cash movements into three buckets:

```
┌──────────────────────────────────────────────────────┐
│              Cash Flow Statement                      │
├──────────────────────────────────────────────────────┤
│  1. CFO — Cash from Operating Activities              │
│     (Running the business day-to-day)                 │
│                                                       │
│  2. CFI — Cash from Investing Activities              │
│     (Buying/selling long-term assets)                 │
│                                                       │
│  3. CFF — Cash from Financing Activities              │
│     (Borrowing, repaying debt, issuing/buying stock,  │
│      paying dividends)                                │
├──────────────────────────────────────────────────────┤
│  Net change in cash = CFO + CFI + CFF                 │
└──────────────────────────────────────────────────────┘
```

CFO is the first and most important section. It tells you whether the company's actual *business* — not its investments, not its financing — is generating cash.

---

## Two Methods: Indirect and Direct

### The Indirect Method — Start from Profit, Work Backward

The indirect method is how **virtually every company** reports CFO in practice. It starts with **Net Income** (the bottom line of the income statement) and systematically reverses every item that made profit different from cash.

The logic: "Accounting said we earned X. But here's everything in X that wasn't actually cash, and here's all the cash that moved but wasn't in X."

**General structure:**

$$\boxed{CFO = NI + \text{Noncash charges} \pm \text{Gains/losses on sales} \pm \Delta\text{Working capital}}$$

Every adjustment falls into one of three categories:

1. **Noncash charges** — things that reduced profit but didn't cost cash
2. **Non-operating items** — things in profit that belong in the investing/financing sections
3. **Working capital changes** — cash that moved because of balance sheet changes, not income statement activity

---

### The Direct Method — Just List the Cash

The direct method ignores Net Income entirely. It simply lists:

```
Cash received from customers
− Cash paid to suppliers
− Cash paid to employees
− Cash paid for other operating expenses
− Cash paid for interest
− Cash paid for taxes
= CFO
```

It's a checkbook register. No adjustments, no reconciliation — just "what cash came in and what cash went out for operations."

**Why it's preferred by standard-setters:** The IASB and the CFA curriculum both prefer the direct method because it's transparent. You can see *exactly* which cash flows are large, which are growing, and which are volatile. The indirect method obscures this behind a wall of adjustments.

**Why almost nobody uses it:** Companies' accounting systems track *accrual* transactions (revenue when earned, expenses when incurred), not cash transactions. Reconstructing every cash receipt and payment is expensive and burdensome. So the indirect method dominates in practice, and the direct method appears mainly in exam questions.

> [!note] The Exam Angle
> You need to know both methods exist. The indirect method is far more heavily tested because it connects to the FCFF/FCFE formulas. The direct method mainly appears in "which method is preferred by IASB?" conceptual questions.

---

## The Indirect Method: Every Adjustment Explained

Let's return to the restaurant — now called **Chef's Table Inc.** — and trace every adjustment with a physical event.

**Chef's Table financial data:**

| Item | Amount |
|------|--------|
| Net Income | $50,000 |
| Depreciation (kitchen equipment) | $11,000 |
| Amortization (liquor license) | $2,000 |
| Gain on sale of old pizza oven | $3,000 |
| Loss on write-down of goodwill | $5,000 |
| Increase in deferred tax liability | $1,500 |
| Increase in accounts receivable | $6,000 |
| Increase in inventory (wine cellar) | $8,000 |
| Decrease in prepaid expenses | $1,000 |
| Increase in accounts payable | $4,000 |
| Increase in accrued wages | $2,500 |

---

### Category 1: Noncash Charges → Add Back

These items reduced Net Income on paper but no cash physically left the bank account.

---

**Depreciation: +$11,000**

Chef's Table owns ovens, refrigerators, stoves, and dishwashers worth $110,000. The accountant spreads that cost over 10 years — charging $11,000/year as an "expense." This $11,000 reduced Net Income, but think about what *actually* happened: the equipment just got one year older. Nobody wrote a check. The cash left the building *years ago* when the equipment was purchased.

We add it back because we need to undo this paper-only reduction in profit.

Physical reality: the ovens are sitting in the kitchen, slightly more worn. No cash moved this year.

---

**Amortization: +$2,000**

Same idea as depreciation, but for an *intangible* asset. Chef's Table paid $20,000 for a premium liquor license ten years ago and amortizes it over 10 years. This year's $2,000 charge reduced NI but didn't involve any cash — the license is just an entry on the balance sheet getting smaller.

Physical reality: the license hangs on the wall. No cash moved.

---

**Impairment / Write-down of goodwill: +$5,000**

Chef's Table acquired a small catering business three years ago and recorded $30,000 of [[goodwill]] (the premium paid above the fair value of tangible assets). This year, management determined the catering business isn't worth what they thought — so they "wrote down" goodwill by $5,000. This charge hit the income statement as a loss.

But did any cash leave? No. Goodwill was always just a balance sheet entry representing an overpayment made years ago. The write-down is an accounting acknowledgment of a past mistake, not a current cash event.

Physical reality: nothing happened at the restaurant. An accountant made a journal entry.

---

**Increase in deferred tax liability: +$1,500**

Chef's Table's tax expense on the income statement was $15,000, but the actual check to the government was only $13,500. The $1,500 difference is a **deferred tax liability** — taxes owed in the future, not paid today.

Why the difference? Common reason: the government allows **accelerated depreciation** for tax purposes. Chef's Table might depreciate equipment over 5 years for taxes but 10 years for financial reporting. In the early years, tax depreciation is higher → taxable income is lower → cash taxes are lower than book tax expense. The difference accumulates as a deferred tax liability.

The $1,500 that NI treated as a tax expense but that never left the bank account gets added back.

Physical reality: the government got $13,500. The income statement said $15,000. Chef's Table kept the $1,500 difference — for now.

---

### Category 2: Non-Operating Gains/Losses → Remove

These items are in Net Income but don't belong in *operating* cash flows. They're investing or financing events that got mixed into profit.

---

**Gain on sale of old pizza oven: −$3,000**

Chef's Table sold a worn-out pizza oven (book value $7,000) for $10,000. The $3,000 gain increased Net Income. But two problems:

1. Selling equipment is an *investing* activity, not an operating activity. The cash from the sale belongs in CFI, not CFO.
2. If we leave the gain in CFO *and* record the $10,000 cash proceeds in CFI, we've double-counted $3,000.

So we subtract the gain from CFO. The full $10,000 of cash shows up in CFI (investing section), and CFO is kept "clean" — only reflecting the actual business of running a restaurant.

Physical reality: a truck came and took away the old oven. The restaurant received $10,000 cash. That event is investing, not operating.

> [!warning] Flip for Losses
> If the oven had been sold for $5,000 (a $2,000 loss), that loss *decreased* Net Income. But the loss isn't an operating cash outflow — the $5,000 cash received is an investing inflow. We *add back* the loss to undo its drag on NI.
>
> **Rule:** Gains → subtract from CFO. Losses → add back to CFO. The actual cash shows up in CFI.

---

### Category 3: Working Capital Changes → The Cash Cycle

This is where the gap between "profit" and "cash" really lives. Every time the balance sheet's current assets or current liabilities change, cash is either being consumed or released — even if the income statement doesn't show it.

---

**Increase in accounts receivable: −$6,000**

A corporate client held a private dinner and ran up a $6,000 bill. Chef's Table recorded the revenue (it's in NI as part of the $50,000 profit). But the client hasn't paid yet. The $6,000 is sitting in "accounts receivable" — an IOU, not cash.

Net Income says we earned this money. Cash says we haven't received it. We subtract the increase in A/R to correct for this overstatement.

Physical reality: the dinner happened, the food was served, but the check hasn't arrived in the mail.

---

**Increase in inventory: −$8,000**

Chef's Table bought $8,000 of premium wine to stock the cellar for the holiday season. The wine is sitting on shelves — an asset, not an expense yet (it becomes an expense when it's sold and recognized in COGS). So this $8,000 cash outflow didn't reduce NI at all. But the cash is gone — it's been converted from dollars in the bank into bottles on a shelf.

We subtract the inventory increase because cash left the building but NI didn't notice.

Physical reality: cases of wine were delivered. A check was written. The income statement is oblivious.

---

**Decrease in prepaid expenses: +$1,000**

Last year, Chef's Table prepaid $3,000 for a full year of pest control service. This year, $1,000 of that prepayment was "used up" and recognized as an expense. The $1,000 hit the income statement (reducing NI), but no cash was paid this year — the cash was paid last year.

We add back the decrease in prepaid expenses because this year's expense was covered by last year's cash.

Physical reality: the pest control company came and sprayed. No check was written. The payment happened twelve months ago.

---

**Increase in accounts payable: +$4,000**

Chef's Table received $4,000 worth of beef from its meat supplier but hasn't paid the bill yet. The beef was used in the kitchen, and the cost was recognized in COGS (reducing NI). But the cash is still in Chef's Table's bank account — the supplier is essentially extending a short-term, interest-free loan.

We add the increase in A/P because NI was reduced (via COGS) but cash wasn't spent.

Physical reality: the meat arrived, the steaks were served, the supplier sent an invoice, but the check hasn't been mailed yet.

---

**Increase in accrued wages: +$2,500**

Chef's Table owes its kitchen staff $2,500 in wages earned in the last week of December but not yet paid (payday is January 5). The wage expense was recorded in NI (reducing profit), but no cash was disbursed.

We add the increase in accrued wages because the expense is on the books but the cash hasn't left.

Physical reality: the cooks worked their shifts. The money is owed but still in the bank.

---

### The Master Rule for Working Capital

The pattern is consistent and logical once you see it:

| Change | Effect on Cash | Adjustment to NI |
|--------|---------------|-------------------|
| Current asset ↑ (A/R, inventory, prepaid) | Cash consumed (trapped in assets) | **Subtract** |
| Current asset ↓ | Cash released (assets converted to cash) | **Add** |
| Current liability ↑ (A/P, accrued wages) | Cash conserved (owe money but haven't paid) | **Add** |
| Current liability ↓ | Cash consumed (paid off obligations) | **Subtract** |

> [!tip] Memory Hook: "Sources and Uses"
> - **Asset increases** = cash was **used** to acquire the asset → subtract
> - **Asset decreases** = cash was **sourced** by liquidating the asset → add
> - **Liability increases** = cash was **sourced** by delaying payment → add
> - **Liability decreases** = cash was **used** to pay off the obligation → subtract
>
> Or even simpler: **Assets move opposite to cash. Liabilities move same as cash.**

---

### Chef's Table CFO — Complete Calculation

```
Net Income                                   $50,000
                                            ────────
NONCASH CHARGES
  + Depreciation                            +$11,000
  + Amortization                             +$2,000
  + Goodwill impairment                      +$5,000
  + Increase in deferred tax liability       +$1,500
                                            ────────
NON-OPERATING ITEMS
  − Gain on sale of pizza oven               −$3,000
                                            ────────
WORKING CAPITAL CHANGES
  − Increase in accounts receivable          −$6,000
  − Increase in inventory                    −$8,000
  + Decrease in prepaid expenses             +$1,000
  + Increase in accounts payable             +$4,000
  + Increase in accrued wages                +$2,500
                                            ────────
CASH FLOW FROM OPERATIONS (CFO)             $60,000
```

Chef's Table reported $50,000 of profit but generated $60,000 of operating cash. The extra $10,000 came mainly from noncash charges ($19,500) offsetting cash trapped in working capital ($6,500 net use).

---

## The Accounting Connection Map

Every single adjustment traces back to a specific location on the financial statements:

```
INCOME STATEMENT                          BALANCE SHEET (Comparative)
┌──────────────────────┐                  ┌───────────────────────────┐
│ Revenue               │                  │ CURRENT ASSETS             │
│ − COGS                │                  │  Cash ← (what we solve for)│
│ − Depreciation ───────│──── add back     │  A/R ─────── Δ → subtract │
│ − Amortization ───────│──── add back     │  Inventory ── Δ → subtract│
│ − SGA                 │                  │  Prepaid ──── Δ → add     │
│ + Gain on sale ───────│──── subtract     │                            │
│ − Impairment ─────────│──── add back     │ NONCURRENT ASSETS          │
│ − Interest            │                  │  PP&E (→ FCInv, not CFO)   │
│ − Tax expense ────────│──┐               │                            │
│ = Net Income ─────────│──│── START HERE  │ CURRENT LIABILITIES        │
└──────────────────────┘  │               │  A/P ─────── Δ → add      │
                           │               │  Accrued ──── Δ → add     │
                           │               │  Short-term debt (exclude!)│
                           │               │                            │
                           │               │ NONCURRENT LIABILITIES     │
                           └──────────────│  Deferred tax ─ Δ → add   │
                                           └───────────────────────────┘
```

---

## IFRS vs. US GAAP: The Classification Trap

The same economic event can appear in different sections of the cash flow statement depending on which accounting rules the company follows. This is one of the most heavily tested traps because it directly affects FCFF and FCFE calculations.

| Item | US GAAP | IFRS | Why It Matters |
|------|---------|------|---------------|
| **Interest paid** | Must be in **CFO** | Choice: **CFO or CFF** | If in CFF under IFRS, CFO is higher. When computing FCFF from CFO, don't add back interest that was never subtracted. |
| **Interest received** | Must be in **CFO** | Choice: **CFO or CFI** | Affects comparability between companies |
| **Dividends paid** | Must be in **CFF** | Choice: **CFO or CFF** | If in CFO under IFRS, CFO looks lower |
| **Dividends received** | Must be in **CFO** | Choice: **CFO or CFI** | If in CFI under IFRS, CFO is lower |
| **Taxes paid** | Must be in **CFO** | **CFO** (unless specifically linked to investing/financing) | Usually the same treatment |

> [!danger] The FCFF-from-CFO Trap
> The formula $FCFF = CFO + Int(1-t) - FCInv$ assumes interest was subtracted from CFO (US GAAP default). 
>
> **If an IFRS company classifies interest paid in financing activities:**
> - Interest was *never* subtracted from CFO
> - CFO is already "pre-interest"
> - Do **not** add $Int(1-t)$ back — you'd be adding interest that was never removed
> - Formula becomes: $FCFF = CFO - FCInv$
>
> **Always check the classification before applying the formula.**

---

## Why CFO ≠ Free Cash Flow

CFO is necessary but not sufficient. It tells you how much cash operations generated, but a company can't just hand all of it to investors. There are two critical things CFO ignores:

**1. Capital expenditures (FCInv)**

Chef's Table *must* replace worn-out ovens and refrigerators just to keep operating. If CFO is $60,000 but the restaurant needs to spend $25,000 on a new dishwasher, only $35,000 is truly "free." CFO doesn't subtract this because capex is classified as an *investing* activity — it shows up in CFI, not CFO.

A company can report beautiful CFO while its factories are crumbling — because the cash needed to replace aging equipment isn't deducted from CFO.

**2. Debt service**

CFO under US GAAP includes interest payments but does **not** include principal repayments (those are in CFF). A company drowning in debt repayments can have strong CFO while actually having no free cash at all.

$$\text{Free Cash Flow} = CFO - \text{Capex}$$
$$\text{(This is the simplest version — FCFF and FCFE formulas add more nuance)}$$

> [!warning] The "High CFO" Mirage
> A company reporting $500M of CFO that spends $480M on maintenance capex has only $20M of truly free cash. Always look at CFO *relative to* required reinvestment, not CFO alone.

---

## Red Flags: How Companies Inflate CFO

CFO can be manipulated. Smart analysts know where to look.

### 1. Stretching Payables

**The trick:** In the last week of the quarter, the company deliberately delays paying supplier invoices. Accounts payable spike, and since rising A/P *adds* to CFO, the operating cash flow looks inflated.

**Real-world example:** Chef's Table owes its meat supplier $20,000 due December 28. They "accidentally" delay payment to January 3. December's CFO is inflated by $20,000. January's will be deflated — but that's next quarter's problem.

**How to detect:** Watch **Days Payable Outstanding (DPO)**. If DPO is rising quarter after quarter without a business explanation, the company may be artificially delaying payments.

### 2. Securitizing Receivables

**The trick:** The company sells its accounts receivable to a bank or special-purpose entity for immediate cash. A/R drops (which adds to CFO), and the company reports strong operating cash flow.

**Real-world example:** Chef's Table has $100,000 in corporate catering invoices due in 60 days. They sell these IOUs to a bank for $95,000 in cash today. A/R drops by $100,000 → CFO gets a huge one-time boost. But next quarter, those receivables are gone — the boost doesn't repeat.

**How to detect:** Look for sudden drops in A/R that don't match revenue trends. Check footnotes for "sale of receivables" or "factoring."

### 3. Capitalizing Operating Expenses

**The trick:** The company reclassifies a routine operating expense as a capital expenditure. This moves the cash outflow from CFO (operating) to CFI (investing). CFO rises, but the cash is still gone — it just appears in a different section.

**Real-world example:** A software company has $10M in developer salaries. Instead of expensing them (which would reduce CFO), the company argues these developers are "building a long-term asset" and capitalizes the cost. The $10M cash outflow moves from CFO to CFI. Operating profit and CFO both look $10M better. But the company's total cash position is unchanged.

**How to detect:** Compare CFO growth to net income growth. If CFO is growing much faster than NI, check whether capex (in CFI) is growing suspiciously fast too. Also compare the company's capitalization policies to industry peers.

### 4. Channel Stuffing

**The trick:** The company ships excess product to distributors at quarter-end, recognizing revenue immediately. Revenue and NI rise. But the distributors haven't sold through the inventory — and may return it next quarter.

**How to detect:** Inventory at distributors rising, A/R rising faster than revenue, revenue spikes followed by returns.

---

## Quick Diagnostic Ratios

| Ratio | Formula | What it tells you |
|-------|---------|-------------------|
| CFO / Net Income | $CFO \div NI$ | Cash quality of earnings. Ratio > 1 is healthy. If NI is growing but this ratio is falling, earnings quality is deteriorating. |
| CFO / Total Debt | $CFO \div \text{Total Debt}$ | Ability to service debt from operations |
| CFO − Capex (simple FCF) | $CFO - \text{Capex}$ | Cash left after maintaining the business |
| DPO trend | $\frac{A/P}{\text{COGS}} \times 365$ | Rising DPO = potential payables manipulation |
| DSO trend | $\frac{A/R}{\text{Revenue}} \times 365$ | Rising DSO = revenue recognition concern |

---

## CFO and the FCFF/FCFE Bridge

CFO is the starting point for the simplest FCFF and FCFE formulas:

$$FCFF = CFO + Int(1-t) - FCInv$$

$$FCFE = CFO - FCInv + \text{Net Borrowing}$$

CFO has already done the heavy lifting: noncash charges are added back, working capital changes are accounted for, and gains/losses are reclassified. The FCFF formula only needs to undo the interest (to make it pre-debt) and subtract capex. The FCFE formula only needs to subtract capex and add borrowing.

This is why understanding CFO deeply unlocks the entire [[FCFF and FCFE - Starting Points Deep Dive|FCFF and FCFE framework]].

---

## Related Concepts

- [[FCFF and FCFE - Starting Points Deep Dive]] — how CFO feeds into free cash flow formulas
- [[Free Cash Flow Valuation]] — valuation models built on FCFF and FCFE
- [[Depreciation]] — the largest noncash charge in most CFO calculations
- [[Working Capital]] — the operating cycle that drives WCInv adjustments
- [[Deferred Tax]] — creates timing differences between book tax and cash tax
- [[Accounts Receivable]] — revenue earned but cash not collected
- [[Accounts Payable]] — expenses incurred but cash not paid
- [[Goodwill]] — subject to impairment write-downs (noncash)
- [[Cash Flow Statement]] — the financial statement where CFO lives
