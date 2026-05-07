---
title: "Practice Q - OHJR 1×4 FRA Settlement"
subject: "Derivatives"
tags: [CFA-L2, practice-question, FRA, forward-rate-agreement, settlement]
source: "unknown"
date: 2026-05-05
---

# OHJR 1×4 FRA Settlement

## Question

> OHJR entered into a 1 × 4 FRA as the fixed rate payer on a notional amount of GBP 9,000,000. At the time, the FRA was priced at 2.87%.
>
> If the 90-day MRR (based on a 360-day year) at expiry is 2.35%, and the appropriate discount rate for the settlement of FRA cash flows is 2.25%, the payment required to settle it will be *closest* to a:

(Answer choices not shown in the screenshot — solving for the numerical settlement value.)

---

## Correct Answer: OHJR pays ≈ **GBP 11,635**

### What is this testing?

The mechanics of cash-settling an [[FRA]] at expiration. CFA wants you to know three things at once:

1. **Notation:** a "1 × 4" FRA expires in 1 month and references a (4 − 1) = 3-month underlying rate.
2. **Direction:** the **fixed-rate payer** pays the agreed FRA rate and receives the realized [[MRR|Market Reference Rate]]. They profit when MRR > FRA rate; they lose when MRR < FRA rate.
3. **Timing:** the 3-month interest period runs from settlement (month 1) to month 4, so the natural cash flow occurs at month 4 — but FRAs settle in cash at expiration (month 1). That means the "interest difference" must be **discounted back** by the 3-month discount rate. This advance-discounting step is the whole point of the question.

### The correct approach

The standard CFA Level II FRA cash-settlement formula:

$$
\text{Settlement}_{T} \;=\; \frac{\big(\text{MRR}_{T} - \text{FRA}_{0}\big) \times \dfrac{D}{360} \times \text{Notional}}{1 + r_{\text{disc}} \times \dfrac{D}{360}}
$$

Symbols:
- $\text{MRR}_T$ = realized reference rate at expiration (here, 2.35%)
- $\text{FRA}_0$ = the rate locked in at inception (2.87%)
- $D$ = days in the underlying period (90)
- $r_{\text{disc}}$ = discount rate appropriate to the settlement date for the 90-day period (2.25%)
- Notional = GBP 9,000,000
- A **positive** result is a cash inflow to the fixed payer; **negative** is a payment owed.

### Step-by-step computation

**1. Rate differential (fixed payer perspective):**

$$\text{MRR} - \text{FRA} = 0.0235 - 0.0287 = -0.0052$$

Negative — the floating rate came in below the locked fixed rate, so the fixed payer is on the wrong side.

**2. Day-count fraction:**

$$\frac{D}{360} = \frac{90}{360} = 0.25$$

**3. Undiscounted interest difference (would-be cash flow at month 4):**

$$-0.0052 \times 0.25 \times 9{,}000{,}000 = -11{,}700$$

That is, GBP 11,700 of "lost interest" measured at the **end** of the 90-day period.

**4. Discount factor (move that month-4 cash flow back to month-1 settlement):**

$$1 + 0.0225 \times 0.25 = 1.005625$$

**5. Present-value the cash flow to settlement date:**

$$\text{Settlement} = \frac{-11{,}700}{1.005625} = -11{,}634.55$$

**OHJR pays ≈ GBP 11,635.** Rounded to GBP 11,634 or 11,635 depending on the answer-choice precision.

### The intuition

Why discount? Because the FRA's economic logic says: "if you had borrowed at the locked 2.87% but the world only charges 2.35%, your overpayment shows up as interest *at the end* of the 3-month borrowing window — month 4." But settlement happens at month 1. To pay that month-4 interest gap *now*, both parties need to agree on the present value of that future flow — discounted at the rate available *today* for 3-month money. That rate (2.25%) is given.

If you forget to discount, you compute GBP 11,700 — the right *direction* but the wrong *magnitude*. The discount step is small (≈0.56%) but CFA writers love putting both 11,700 and 11,635 in the answer choices to catch this.

### Sign convention check

- Fixed payer: pays fixed, receives floating. Cash flow = (floating − fixed) × … → here negative → **OHJR pays**.
- If the question had said "fixed receiver" or "long the floating leg," flip the sign.

---

## The Trap — Most Tempting Wrong Answer

The seductive distractor is **GBP 11,700** — the undiscounted number. It looks right because:

- The arithmetic feels complete: rate diff × day-count × notional. Easy mental check.
- A fresh learner thinks of an FRA like a forward on an interest rate, and the natural instinct is to settle for the full interest difference.

**The specific mistake:** ignoring that the FRA settles *at the start* of the 90-day notional period, not at the end. Without the divide-by-$(1 + r_{\text{disc}} \times D/360)$ step, you've effectively paid month-4 money on day 30, getting an extra 90 days of interest for free.

**How to avoid it on exam day:** When you see "FRA settles at expiration" + a *separate* discount rate explicitly listed, that discount rate is there for one reason — to discount. If the question gives you a number you don't end up using, you've made a mistake.

A second, smaller trap: confusing which rate is in the **numerator** (the locked FRA rate vs. the realized MRR) and which is in the **denominator** (the unrelated *current* 90-day discount rate). They are *not* the same — the denominator rate reflects market conditions at settlement, not the original deal.

---

## Key Takeaway

> [!tip] Memory Hook
> **"Difference, day-count, divide."** FRA settlement = (MRR − FRA) × (D/360) × Notional, then divide by (1 + disc × D/360). The fixed payer's cash flow has the sign of (MRR − FRA).

---

## Related Concepts

- [[FRA]] — Forward Rate Agreement structure and notation
- [[Forward Rate Agreement]]
- [[MRR]] — Market Reference Rate (replaced LIBOR)
- [[Pricing and Valuation of Forward Commitments]] — module 01 umbrella
- [[Forward Rate]]
- [[Discount Factor]]
- [[Day Count Convention]]
