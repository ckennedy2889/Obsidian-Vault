# 📘 Amortized Cost

---

> [!info] **The Big Picture — "I'm Holding This Until I Get Paid Back"**
> Think of amortized cost like buying a certificate of deposit at your bank. You don't care what someone *else* would pay for that CD tomorrow — you're just going to sit there, collect your interest, and get your principal back at maturity. The market can go wild; you're indifferent. Your accounting reflects that indifference: you carry the asset at what you paid (adjusted for any premium/discount), not what the market says it's worth today.

---

## 🔑 Core Concept

Amortized cost = **Original cost** ± cumulative amortization of any [[premium]] or [[discount]]

The asset is **NOT** marked to [[fair value]] on the [[balance sheet]]. Subsequent changes in market value are completely **ignored**.

---

## 📋 Qualification Criteria (Two Tests)

> [!important] **Both tests must be passed — no exceptions**

```
┌─────────────────────────────────────────────────────────────┐
│              AMORTIZED COST ELIGIBILITY                     │
│                                                             │
│   Test 1: BUSINESS MODEL TEST                               │
│   ┌───────────────────────────────────────────────────────┐ │
│   │ "Are you holding this to collect contractual          │ │
│   │  cash flows?" (hold-to-collect model)                 │ │
│   └───────────────────────────────────────────────────────┘ │
│                        AND                                  │
│   Test 2: CASH FLOW CHARACTERISTIC TEST                     │
│   ┌───────────────────────────────────────────────────────┐ │
│   │ "Are the contractual cash flows SOLELY                │ │
│   │  principal + interest on principal?"                   │ │
│   └───────────────────────────────────────────────────────┘ │
│                                                             │
│   ✅ Pass Both  →  Amortized Cost                           │
│   ❌ Fail Either →  Must use FVPL or FVOCI                  │
└─────────────────────────────────────────────────────────────┘
```

> [!warning] **Debt securities ONLY**
> Equity instruments are **never** eligible for amortized cost under IFRS 9. Amortized cost is exclusively for debt instruments whose cash flows are principal and interest.

---

## 📊 Financial Statement Impact

### Balance Sheet

$$\text{B/S Value} = \text{Purchase Price} + \text{Amortized Discount} \;(\text{or} - \text{Amortized Premium})$$

The carrying value **converges toward par** over the life of the bond, regardless of what happens to market prices.

```
      Carrying Value Over Time (Discount Bond)
      
   Par ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ · 
                                            ·
                                       ·
                                  ·        ← Amortization of
                             ·               discount pulls
                        ·                    carrying value
                   ·                         UP toward par
              ·
   Cost  ·
   ────────────────────────────────────────────►
   Purchase                               Maturity
```

### Income Statement

$$\text{Interest Revenue} = \text{Beginning Carrying Value} \times \text{Effective Yield (Market Rate at Purchase)}$$

> [!tip] **Key Insight**
> Interest revenue is **NOT** the coupon payment. It's the economically correct interest computed using the [[effective interest method]]. The difference between the coupon cash received and the interest revenue is the amortization of premium/discount.

$$\text{Amortization} = \text{Interest Revenue} - \text{Coupon Payment}$$

### What Goes Where

| Item | Where It Appears |
|---|---|
| Carrying value (amortized cost) | Balance Sheet — financial assets |
| Interest revenue (effective interest) | Income Statement |
| Unrealized gains/losses | **NOWHERE** — completely ignored |
| Realized gains/losses | Income Statement (only upon sale or derecognition) |

---

## 🧮 Worked Example: Midland Corporation

> [!example] **Setup**
> Midland purchases a **9% annual coupon bond** with:
> - Face value: **$100,000**
> - Purchase price: **$96,209** (bought at a discount)
> - Yield to maturity: **10%**
> - Fair value at year-end: **$98,500**

### Step-by-Step Under Amortized Cost

**1. Interest Revenue (Income Statement)**

$$\text{Interest Revenue} = \$96{,}209 \times 10\% = \$9{,}621$$

**2. Coupon Cash Received**

$$\text{Coupon} = \$100{,}000 \times 9\% = \$9{,}000$$

**3. Discount Amortization**

$$\text{Amortization} = \$9{,}621 - \$9{,}000 = \$621$$

**4. Year-End Carrying Value (Balance Sheet)**

$$\text{Carrying Value} = \$96{,}209 + \$621 = \$96{,}830$$

> [!danger] **The $98,500 fair value is COMPLETELY IGNORED**
> Even though the bond's market value rose to $98,500, the balance sheet reports $96,830 (amortized cost). The $1,670 unrealized gain ($98,500 − $96,830) appears **nowhere** in the financial statements.

### Summary Table

| Line Item | Amount |
|---|---|
| **Balance Sheet: Investment** | $96,830 |
| **Income Statement: Interest Revenue** | $9,621 |
| **Income Statement: Unrealized G/L** | $0 |
| **OCI: Unrealized G/L** | $0 |
| **Total Comprehensive Income impact** | $9,621 |

---

## 🔄 IFRS vs. US GAAP Comparison

| Feature | IFRS 9 — Amortized Cost | US GAAP — Held-to-Maturity (HTM) |
|---|---|---|
| **Applicable to** | Debt only | Debt only |
| **Classification basis** | Business model + cash flow tests | Management intent & ability to hold to maturity |
| **B/S measurement** | Amortized cost | Amortized cost |
| **Interest income** | Effective interest method | Effective interest method |
| **Unrealized G/L** | Not recognized | Not recognized |
| **Impairment model** | Expected credit loss (forward-looking) | Current expected credit loss (CECL) under ASC 326 |
| **Reclassification** | Permitted only if business model changes (very rare) | Permitted but "taints" the entire HTM portfolio |

---

## ⚠️ Analyst Considerations

> [!warning] **Hidden Risk**
> Because amortized cost ignores market value changes, a bond portfolio could have **significant unrealized losses** that don't show up anywhere in the financial statements. Analysts should:
> 1. Check the **notes/disclosures** for fair value of amortized cost securities
> 2. Consider the **gap between carrying value and fair value** as a measure of hidden risk
> 3. Remember that **selling** an amortized cost security triggers immediate recognition of the entire gain or loss in the income statement — this creates potential for [[earnings management]]

> [!tip] **Exam Tip**
> If a question says the bond "meets the business model and cash flow tests," that's your cue for amortized cost. The balance sheet value will **NOT** be fair value — it will be the original cost adjusted for amortization. Only interest revenue hits the income statement; unrealized G/L is invisible.

---

## 🧠 Quick Mental Model

```
┌──────────────────────────────────────────────────────┐
│                  AMORTIZED COST                      │
│                                                      │
│   B/S:  Cost ± amortized premium/discount            │
│   I/S:  Interest revenue (effective interest)        │
│   OCI:  Nothing                                      │
│                                                      │
│   Fair value changes? → 🚫 IGNORED                   │
│   Unrealized G/L?     → 🚫 NOT RECOGNIZED            │
│   Realized G/L?       → ✅ Only on sale              │
│                                                      │
│   Think: "I'm a patient lender. I don't care         │
│           what the market thinks my loan is worth."   │
└──────────────────────────────────────────────────────┘
```
