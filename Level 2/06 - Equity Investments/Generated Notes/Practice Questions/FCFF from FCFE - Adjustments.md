---
title: "Practice Q - FCFF from FCFE Adjustments"
subject: "Equity Investments"
tags: [CFA-L2, practice-question, equity-valuation, FCFF, FCFE, free-cash-flow]
source: "unknown"
date: 2026-04-11
---

# FCFF from FCFE — Direction of Adjustments

## Question

![[attachments/2026-04-11-fcff-from-fcfe-adjustments.png]]

**An analyst trying to determine FCFF from FCFE is *most likely* to make the following adjustments:**

- A. Add after-tax interest expense and net borrowing.
- B. Add after-tax interest expense and subtract net borrowing.
- C. Subtract after-tax interest expense and add net borrowing.

---

## Correct Answer: B — Add after-tax interest expense and subtract net borrowing

### What is this testing?

This question is testing whether you truly understand what **[[FCFF]]** and **[[FCFE]]** actually *represent* — not just whether you can recite a formula. The exam writers want to know: can you move fluidly *between* the two measures without getting the signs confused?

The trick is that most students memorize the forward direction (FCFE from FCFF) but freeze when asked the reverse. Yet both adjustments are the same math, just rearranged. If you understand the underlying logic, the direction is automatic.

### The Core Relationship

Start with the textbook definition that links the two measures. **[[FCFE]]** is what's left for equity holders *after* the company has paid interest to debtholders and settled with them on principal:

$$\text{FCFE} = \text{FCFF} - \text{Interest}(1 - t) + \text{Net Borrowing}$$

Where:
- **Interest(1 − t)** = after-tax interest expense paid to debtholders (a real cash outflow FCFE holders bear)
- **Net Borrowing** = new debt issued minus debt repaid (a cash *inflow* if the company borrowed more than it paid back)

Both terms exist because FCFE is the cash available to equity holders *after* the company has fully settled with creditors for the period.

### The Reverse: FCFF from FCFE

To go the other direction, just algebraically rearrange the equation above. Solve for FCFF:

$$\text{FCFF} = \text{FCFE} + \text{Interest}(1 - t) - \text{Net Borrowing}$$

That rearrangement is the entire answer:

- **Add** after-tax interest expense → undo the interest payment so you're back at the pre-debt-service cash flow
- **Subtract** net borrowing → remove the debt financing cash that only equity holders were "given" by creditors

This matches answer **B** exactly.

### The Intuition — Why These Signs?

Here's the tangible way to think about it. Imagine a pizza — the total cash the business generated from operations after reinvesting. That whole pizza is **FCFF** (the cash available to *all* capital providers, debt and equity together).

Now the company slices the pizza:
1. **Pays the bank** — slices off after-tax interest expense and hands it to debtholders
2. **Settles debt principal** — if the company borrowed *more* than it paid back, debtholders handed *back* a slice (net borrowing is positive); if it paid down debt, debtholders took another slice (net borrowing is negative)
3. **Equity gets what's left** — that remainder is **FCFE**

To get the original pizza (FCFF) back from the leftover slice (FCFE), you must:
- **Add the interest slice back** (you took it out → put it back) ✅
- **Give back what debtholders handed you** (you got that slice for free → return it). If net borrowing was positive (bank gave you cash), you must subtract it to undo the gift.

```
FCFF  ──── (subtract after-tax interest) ────▶  ??
       ──── (add net borrowing) ────────────▶  FCFE

Reverse direction:
FCFE  ──── (add after-tax interest) ─────────▶  ??
       ──── (subtract net borrowing) ────────▶  FCFF
```

The two adjustments simply run in opposite directions. Memorize the forward equation and algebraic rearrangement does the rest — no separate fact to memorize.

### Why After-Tax Interest (Not Gross)?

This is a subtle but critical detail: we add back **interest(1 − t)**, not raw interest. The reason is that interest expense is **tax-deductible** — so when a company pays $100 of interest at a 25% tax rate, only $75 actually leaves the firm on a net basis (the other $25 is "refunded" via lower taxes). FCFF is an after-tax measure, so to be consistent, the interest we add back must also be on an after-tax basis.

If you added back *gross* interest, you'd double-count the tax shield and inflate FCFF.

See [[FCFF and FCFE - Starting Points Deep Dive]] for the full derivation and why every formula — starting from net income, EBIT, EBITDA, or CFO — bakes in this same tax adjustment.

---

## The Trap — Most Tempting Wrong Answer: A

**A. Add after-tax interest expense and net borrowing.**

### Why it looks right

This is the answer most students pick when they're thinking directionally but not carefully. The reasoning goes something like: *"FCFF is the bigger number — it's the whole pizza for all capital providers. FCFE is the smaller slice for equity only. To go from the small number to the big number, I add stuff. Add interest. Add borrowing. Done."*

It's seductive because the first adjustment (adding after-tax interest) is correct. Getting the first piece right lulls you into assuming the same direction works for the second piece.

### The specific mistake

The mistake is forgetting that **net borrowing and interest affect FCFE in *opposite directions***. Look at the original equation again:

$$\text{FCFE} = \text{FCFF} \underbrace{- \text{Interest}(1 - t)}_{\text{subtraction}} \underbrace{+ \text{Net Borrowing}}_{\text{addition}}$$

Interest is *subtracted* when moving from FCFF to FCFE. Net borrowing is *added*. When you reverse direction, you must flip *both* signs — not just one. That means:

- Interest: was subtracted → becomes added ✅
- Net borrowing: was added → becomes subtracted ✅

Answer A flips only the interest sign and leaves net borrowing with the wrong sign, revealing the student didn't actually run the algebra — they just guessed the direction.

### How to avoid it on exam day

**The 3-second check:** Whenever you're asked to move between FCFF and FCFE, write down the base equation first — don't try to do it in your head:

$$\text{FCFE} = \text{FCFF} - \text{Int}(1-t) + \text{NB}$$

Then solve for whichever variable you want. The algebra is trivial, and the signs fall out mechanically. No memorization of "which direction adds what" required.

**Alternative check:** Ask yourself *"Who benefits from each cash flow?"*
- Interest payments go *out* to debtholders → they reduce FCFE (so adding them back going the other way gives FCFF)
- Net borrowing comes *in* from debtholders → it gives cash to FCFE that FCFF doesn't contain (so to get back to FCFF, we subtract that "gifted" cash)

If the economic story of where cash is flowing makes sense, the signs will too.

---

## Key Takeaway

> [!tip] Memory Hook
> **FCFF and FCFE differ by *debt-related* cash flows.** Interest and net borrowing always move in *opposite directions* when you flip between the two measures. Write the base equation, then rearrange — never guess the signs.

$$\text{FCFF} = \text{FCFE} + \text{Interest}(1-t) - \text{Net Borrowing}$$

---

## Related Concepts

- [[FCFF and FCFE - Starting Points Deep Dive]] — full derivation of both measures from every starting point (NI, EBIT, EBITDA, CFO)
- [[FCFF]] — cash available to all capital providers
- [[FCFE]] — cash available to equity holders after debt service
- [[Free Cash Flow Valuation]] — the broader DCF framework using these measures
- [[CFA_Glossary/Cash flow from operations]] — CFO is the most common starting point for both FCFF and FCFE
- [[WACC]] — the discount rate used with FCFF (vs. cost of equity with FCFE)
- [[Net Borrowing]] — new debt issued minus debt repaid in a period
- [[After-Tax Cost of Debt]] — why we use interest(1 − t) and not gross interest
