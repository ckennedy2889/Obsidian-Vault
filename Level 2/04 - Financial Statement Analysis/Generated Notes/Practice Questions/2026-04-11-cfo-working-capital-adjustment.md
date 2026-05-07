---
title: "Practice Q - CFO Working Capital Adjustment Direction"
subject: "Financial Statement Analysis"
tags: [CFA-L2, practice-question, cash-flow-statement, working-capital, indirect-method]
source: "unknown"
date: 2026-04-11
---

# CFO Working Capital Adjustment: Which Direction?

## Question

In a given year a company's inventory and accounts receivable increase more than the increase in accrued expenses and trade payables. The adjustment to net income to account for the change for calculating CFO will most likely be:

- A. Positive.
- B. Negative.
- C. No adjustment required.

---

## Correct Answer: B — Negative

### What is this testing?

This question tests your command of the **indirect method** of computing [[Cash Flow from Operations (CFO)]], which is covered in the [[Cash Flow Statement]] reading. The exam loves this topic because it's conceptually simple but easy to get backwards under time pressure. The core skill: knowing whether a working capital change adds to or subtracts from net income when bridging to cash.

### The correct approach

The indirect method starts with [[Net Income]] (an accrual-based figure) and adjusts it to arrive at actual cash collected and paid. The two types of working capital items move in opposite directions:

$$\text{CFO} = \text{Net Income} + \text{Non-cash charges} - \Delta\text{Current Assets} + \Delta\text{Current Liabilities}$$

Think of it this way: **current assets are things the company is owed or holds** — increases in them mean cash hasn't arrived yet (AR up = you earned it but didn't collect it; inventory up = you paid cash for goods but haven't sold them). **Current liabilities are things the company owes** — increases in them mean the company used a good or service but hasn't paid cash yet (AP up = you received goods but haven't paid; accrued expenses up = you incurred a cost but haven't paid).

| Working Capital Item | Direction | Adjustment to Net Income |
|---|---|---|
| Accounts Receivable ↑ | Current asset increases | **Subtract** |
| Inventory ↑ | Current asset increases | **Subtract** |
| Trade Payables ↑ | Current liability increases | **Add** |
| Accrued Expenses ↑ | Current liability increases | **Add** |

### Step-by-step computation

The question doesn't give dollar figures, but we can illustrate with a concrete example. Suppose:

$$\Delta\text{AR} = +\$30,\quad \Delta\text{Inventory} = +\$20,\quad \Delta\text{AP} = +\$10,\quad \Delta\text{Accrued Expenses} = +\$15$$

Asset increases > Liability increases by the problem's premise (here $50 vs $25).

$$\text{Net working capital adjustment} = -(\Delta\text{AR} + \Delta\text{Inventory}) + (\Delta\text{AP} + \Delta\text{Accrued Expenses})$$

$$= -(30 + 20) + (10 + 15) = -50 + 25 = -\$25$$

The net adjustment is **negative** — it reduces CFO below net income.

### The intuition

Net income captures revenue when *earned* and expenses when *incurred* — cash doesn't have to move. If AR rises, the firm recorded sales revenue but customers haven't paid yet, so CFO overstates the cash actually received. If inventory rises, the firm spent cash to build up stock but that spending isn't in [[Cost of Goods Sold (COGS)]] yet — so net income overstates how much cash is still in the firm. Both are drains on CFO relative to net income.

Conversely, if AP rises, the firm recorded an expense (reducing net income) but hasn't paid the supplier — so CFO is actually *better* than net income implied. The two sides are pulling in opposite directions. When asset increases dominate, the drain wins.

---

## The Trap — Most Tempting Wrong Answer

**Answer A (positive)** is the trap. A test-taker who half-remembers the rule might think: "liabilities going up is a positive adjustment, assets going up is positive… so it's positive." This confuses the *direction* of each item.

The specific mistake is **inverting the sign convention for current assets**: increases in current assets are a *use* of cash (negative), not a source. Someone who drills "add back non-cash items" might loosely extend that to "add back working capital changes" — but that only applies to liability increases, not asset increases.

**How to avoid it:** Anchor on a one-line memory rule and never deviate: *"Current assets up → subtract. Current liabilities up → add."* If asset increases > liability increases, the subtractions outweigh the additions → net negative.

---

## Key Takeaway

> [!tip] Memory Hook
> AR and inventory going up = cash you're missing. AP and accruals going up = cash you're keeping. When you're "missing" more than you're "keeping," CFO is dragged below net income → the adjustment is **negative**.

---

## Related Concepts

- [[Cash Flow from Operations (CFO)]] — the line item being calculated
- [[Cash Flow Statement]] — indirect vs. direct method presentation
- [[Working Capital]] — current assets minus current liabilities
- [[Net Income]] — accrual-based starting point for indirect method
- [[Accounts Receivable]] — key current asset; increase = subtract from CFO
- [[Inventory]] — key current asset; increase = subtract from CFO
- [[Accounts Payable]] — key current liability; increase = add to CFO
