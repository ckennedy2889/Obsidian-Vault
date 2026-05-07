# 📗 Fair Value Through Other Comprehensive Income (FVOCI)

---

> [!info] **The Big Picture — "I Want to See the Market Value, But Don't Mess with My Earnings"**
> FVOCI is the compromise category. Imagine a pension fund that holds bonds for income *but* might sell some if conditions warrant. It wants the balance sheet to reflect reality (fair value), but it doesn't want every market wobble running through net income and spooking the board. So FVOCI says: "Show the fair value on the balance sheet, put interest income through P&L, but park the unrealized gains and losses off to the side in OCI — the equity section's quiet corner." It's fair value accounting with a **noise filter** on the income statement.

---

## 🔑 Core Concept

Under FVOCI, the investment is:
1. **Carried at fair value** on the [[balance sheet]] (same as FVPL)
2. **Interest/dividend income** flows through the [[income statement]] (same as both others)
3. **Unrealized gains and losses** bypass the income statement and go to **[[Other Comprehensive Income]]** (accumulated in equity as AOCI)

$$\text{B/S Value} = \text{Fair Value at Reporting Date}$$

$$\text{I/S} = \text{Interest or Dividend Income only}$$

$$\text{OCI} = \text{Unrealized Gain or Loss}$$

---

## 📋 When Does FVOCI Apply?

```
┌──────────────────────────────────────────────────────────────┐
│                    FVOCI CLASSIFICATION                      │
│                                                              │
│   ┌─── DEBT at FVOCI ──────────────────────────────────────┐ │
│   │                                                        │ │
│   │  Must pass BOTH tests:                                 │ │
│   │  ✅ Business Model: "Hold-to-collect AND sell"          │ │
│   │     (collects cash flows but may also sell)             │ │
│   │  ✅ Cash Flow Test: Solely principal + interest          │ │
│   │                                                        │ │
│   │  Key distinction from Amortized Cost:                  │ │
│   │  → Amortized Cost = hold to collect (no selling)       │ │
│   │  → FVOCI = hold to collect AND sell                    │ │
│   └────────────────────────────────────────────────────────┘ │
│                                                              │
│   ┌─── EQUITY at FVOCI ────────────────────────────────────┐ │
│   │                                                        │ │
│   │  • Must NOT be held for trading                        │ │
│   │  • Management makes an IRREVOCABLE election            │ │
│   │    at purchase to designate as FVOCI                   │ │
│   │  • Alternative is FVPL (also irrevocable)              │ │
│   │  • Only DIVIDEND income goes to I/S                    │ │
│   │                                                        │ │
│   │  ⚠️ IFRS ONLY — US GAAP does NOT allow                │ │
│   │     FVOCI for equity                                   │ │
│   └────────────────────────────────────────────────────────┘ │
└──────────────────────────────────────────────────────────────┘
```

---

## 📊 Financial Statement Impact

### The Three-Statement Map

```
┌─────────────── BALANCE SHEET ──────────────────┐
│                                                │
│  Assets:  Investment at FAIR VALUE   ✅        │
│                                                │
│  Equity:  Accumulated OCI (AOCI)               │
│           ← unrealized G/L parked here         │
└────────────────────────────────────────────────┘

┌─────────────── INCOME STATEMENT ───────────────┐
│                                                │
│  Interest Revenue (debt) or                    │
│  Dividend Income (equity)            ✅ → I/S  │
│                                                │
│  Unrealized G/L?                     🚫 NO     │
│  (goes to OCI, NOT income statement)           │
└────────────────────────────────────────────────┘

┌─── OTHER COMPREHENSIVE INCOME (OCI) ──────────┐
│                                                │
│  Unrealized Gains                    ✅ → OCI  │
│  Unrealized Losses                   ✅ → OCI  │
│                                                │
│  Accumulates in shareholders' equity           │
│  as AOCI until the asset is sold               │
└────────────────────────────────────────────────┘
```

### What Goes Where

| Item | Where It Appears |
|---|---|
| Fair value | Balance Sheet |
| Interest income (debt — effective interest method) | Income Statement |
| Dividend income (equity) | Income Statement |
| Unrealized gains & losses | OCI → Accumulated OCI in equity |
| Realized gains & losses (on sale) | See "recycling" rules below |

---

## ♻️ Recycling — The Critical Debt vs. Equity Distinction

> [!danger] **This is a high-yield exam topic**

"Recycling" refers to what happens to the unrealized G/L sitting in AOCI **when the asset is sold**. The rules differ for debt and equity:

```
┌───────────────────────────────────────────────────────────┐
│                 RECYCLING RULES (IFRS 9)                  │
│                                                           │
│   DEBT FVOCI:                                             │
│   ┌─────────────────────────────────────────────────────┐ │
│   │  When sold → accumulated unrealized G/L             │ │
│   │  is "RECYCLED" from OCI → Income Statement          │ │
│   │                                                     │ │
│   │  OCI balance is reclassified to P&L                 │ │
│   │  (i.e., the gain/loss is finally recognized         │ │
│   │   in net income upon sale)                          │ │
│   └─────────────────────────────────────────────────────┘ │
│                                                           │
│   EQUITY FVOCI:                                           │
│   ┌─────────────────────────────────────────────────────┐ │
│   │  When sold → accumulated unrealized G/L             │ │
│   │  is NOT recycled to the income statement            │ │
│   │                                                     │ │
│   │  Instead, it is transferred within equity           │ │
│   │  from AOCI → Retained Earnings                      │ │
│   │                                                     │ │
│   │  The gain/loss NEVER hits net income                 │ │
│   └─────────────────────────────────────────────────────┘ │
└───────────────────────────────────────────────────────────┘
```

> [!example] **Why This Matters**
> A company holds equity shares designated as FVOCI. It buys them at $50 and they rise to $80. That $30 gain sits in AOCI. When the company sells at $80, that $30 gain does **not** move to the income statement — it goes from AOCI to retained earnings. Net income is **never** impacted by the capital gain. Only dividends received during the holding period ever appeared in net income.

---

## 🧮 Worked Example: Midland Corporation

> [!example] **Setup (same bond)**
> Midland purchases a **9% annual coupon bond** with:
> - Face value: **$100,000**
> - Purchase price: **$96,209** (bought at a discount)
> - Yield to maturity: **10%**
> - Fair value at year-end: **$98,500**

### Step-by-Step Under FVOCI

**1. Interest Revenue (Income Statement)**

$$\text{Interest Revenue} = \$96{,}209 \times 10\% = \$9{,}621$$

Same as amortized cost and FVPL — the effective interest calculation is identical.

**2. Unrealized Gain (OCI — NOT Income Statement)**

$$\text{Unrealized Gain} = \$98{,}500 - \$96{,}830 = \$1{,}670$$

This $1,670 goes to **OCI** and accumulates in **AOCI** within shareholders' equity. It does **not** appear in the income statement.

**3. Year-End Carrying Value (Balance Sheet)**

$$\text{B/S Value} = \$98{,}500 \;\text{(fair value — same as FVPL)}$$

### Summary Table

| Line Item | Amount |
|---|---|
| **Balance Sheet: Investment** | $98,500 |
| **Income Statement: Interest Revenue** | $9,621 |
| **Income Statement: Unrealized G/L** | $0 |
| **OCI: Unrealized Gain** | $1,670 |
| **Total Comprehensive Income impact** | $11,291 |

> [!tip] **Notice**
> Total comprehensive income ($9,621 + $1,670 = $11,291) is the **same** as FVPL. The difference is where the pieces show up: under FVPL the entire $11,291 hits net income; under FVOCI only $9,621 hits net income and $1,670 goes to OCI.

---

## 🔀 Side-by-Side: All Three Classifications

> [!important] **The Midland Bond — One Asset, Three Stories**

| | Amortized Cost | FVPL | FVOCI |
|---|---|---|---|
| **B/S: Investment** | $96,830 | $98,500 | $98,500 |
| **I/S: Interest Revenue** | $9,621 | $9,621 | $9,621 |
| **I/S: Unrealized G/L** | — | $1,670 gain | — |
| **OCI: Unrealized G/L** | — | — | $1,670 gain |
| **Net Income Impact** | $9,621 | $11,291 | $9,621 |
| **Total Comp. Income** | $9,621 | $11,291 | $11,291 |

```
    Where Does the $1,670 Unrealized Gain Go?

    Amortized Cost:    NOWHERE  ─── completely invisible
                                    
    FVPL:              ──────── → INCOME STATEMENT
                                    ↓
                                  Net Income ↑
                                    
    FVOCI:             ──────── → OCI
                                    ↓
                                  AOCI in Equity ↑
                                  (Net Income unaffected)
```

---

## 🔄 IFRS vs. US GAAP Comparison

| Feature | IFRS 9 — FVOCI | US GAAP — Available-for-Sale (AFS) |
|---|---|---|
| **Debt securities** | ✅ FVOCI option available | ✅ AFS classification available |
| **Equity securities** | ✅ FVOCI available (irrevocable election) | ❌ **No FVOCI for equity** — all equity at FVPL |
| **B/S measurement** | Fair value | Fair value |
| **Interest income (debt)** | Effective interest method → I/S | Effective interest method → I/S |
| **Unrealized G/L** | OCI | OCI |
| **Recycling (debt)** | Yes — reclassified to I/S on sale | Yes — reclassified to I/S on sale |
| **Recycling (equity)** | No — AOCI → Retained Earnings | N/A (no equity FVOCI under US GAAP) |
| **Reclassification out** | Debt: only if business model changes. Equity: never | Debt: permitted between categories |
| **Impairment** | Expected credit loss model | CECL model (ASC 326) |

> [!danger] **The #1 US GAAP vs. IFRS Trap**
> Under **US GAAP**, equity investments **cannot** be classified as FVOCI (available-for-sale). All equity goes through the income statement (FVPL equivalent). This is one of the most commonly tested differences. If a question says "US GAAP" and "equity investment," unrealized gains/losses **always** go to net income.

---

## ⚠️ Analyst Considerations

> [!warning] **OCI Is Not "Free" Income**
> Just because unrealized G/L goes to OCI doesn't mean it's economically irrelevant. Analysts should:
> 1. **Monitor AOCI balances** — large accumulated unrealized losses signal potential future write-downs or realized losses
> 2. **Compare net income vs. comprehensive income** — a big gap suggests significant FVOCI portfolio movements
> 3. **Watch for "cherry-picking"** — management can sell FVOCI winners (booking gains to I/S via recycling for debt) while holding losers in OCI
> 4. **Adjust for comparability** — if one company uses FVPL and another FVOCI for similar holdings, their net income numbers aren't directly comparable

---

## 🧠 Quick Mental Model

```
┌──────────────────────────────────────────────────────┐
│   FAIR VALUE THROUGH OTHER COMPREHENSIVE INCOME      │
│                                                      │
│   B/S:  Fair Value (same as FVPL)                    │
│   I/S:  Interest/Dividends ONLY                      │
│   OCI:  Unrealized G/L parked here                   │
│                                                      │
│   Fair value changes? → ✅ B/S updated               │
│   Unrealized G/L?     → ✅ OCI (bypasses net income) │
│   Earnings volatility → 📉 SMOOTHED                 │
│                                                      │
│   Recycling (debt)?   → ✅ OCI → I/S on sale         │
│   Recycling (equity)? → ❌ OCI → Ret. Earnings       │
│                                                      │
│   Think: "I want fair value on the B/S but I         │
│           don't want market noise in net income.      │
│           OCI is my shock absorber."                  │
└──────────────────────────────────────────────────────┘
```

---

## 🗺️ Master Classification Decision Tree

> [!tip] **Use this to determine classification on exam questions**

```
                        FINANCIAL ASSET
                             │
                    ┌────────┴────────┐
                    │                 │
                  DEBT              EQUITY
                    │                 │
          ┌─────── Pass ──────┐    Held for
          │  both tests?      │    trading?
          │                   │      │
         YES                 NO    ┌─┴──┐
          │                   │   YES   NO
     ┌────┴────┐              │    │     │
     │         │              │  FVPL  Choose:
  Hold to   Hold to           │       ┌──┴──┐
  collect   collect           │     FVPL  FVOCI
  ONLY?     AND sell?         │    (irrevocable)
     │         │              │
  Amortized  FVOCI          FVPL
   Cost                   (default)
     │
  (May elect
   FVPL to avoid
   accounting
   mismatch)
```
