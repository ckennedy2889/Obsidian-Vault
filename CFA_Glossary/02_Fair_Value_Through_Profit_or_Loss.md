# 📕 Fair Value Through Profit or Loss (FVPL)

---

> [!info] **The Big Picture — "I'm a Trader, and Every Market Move Hits My Bottom Line"**
> Imagine you're a day-trader watching a stock ticker. Every uptick makes you richer *on paper*, every downtick makes you poorer — and your accountant records it all, every single period, directly into your income. That's FVPL. The balance sheet always shows today's market price, and the income statement absorbs **all** the volatility — both realized *and* unrealized gains and losses. Nothing is hidden, nothing is deferred. Maximum transparency, maximum income statement noise.

---

## 🔑 Core Concept

Under FVPL, the investment is:
1. **Carried at fair value** on the [[balance sheet]]
2. **All changes in fair value** (realized AND unrealized) flow through the [[income statement]]

$$\text{B/S Value} = \text{Fair Value at Reporting Date}$$

$$\text{I/S Impact} = \text{Interest/Dividend Income} + \text{Unrealized G/L} + \text{Realized G/L}$$

---

## 📋 When Does FVPL Apply?

```
┌─────────────────────────────────────────────────────────────┐
│                   FVPL CLASSIFICATION                       │
│                                                             │
│   MANDATORY FVPL:                                           │
│   ┌───────────────────────────────────────────────────────┐ │
│   │ • Debt that FAILS the business model OR              │ │
│   │   cash flow characteristic test                      │ │
│   │ • Equity securities held for TRADING                 │ │
│   │ • ALL derivatives (unless hedging instruments)       │ │
│   │ • Assets with EMBEDDED derivatives                   │ │
│   │   (e.g., convertible bonds → whole instrument        │ │
│   │    measured at FVPL)                                 │ │
│   └───────────────────────────────────────────────────────┘ │
│                                                             │
│   VOLUNTARY (FAIR VALUE OPTION):                            │
│   ┌───────────────────────────────────────────────────────┐ │
│   │ • Management may ELECT FVPL to avoid an              │ │
│   │   "accounting mismatch" (e.g., asset at amortized    │ │
│   │    cost but related liability at fair value)         │ │
│   │ • Equity securities not held for trading             │ │
│   │   (alternative to FVOCI — choice is IRREVOCABLE)     │ │
│   └───────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

> [!important] **Irrevocable Election for Equity**
> For non-trading equity investments, management chooses between FVPL and FVOCI **at purchase**. Once made, this choice **cannot be changed**. There is no going back.

---

## 📊 Financial Statement Impact

### Balance Sheet

$$\text{Investment Value} = \text{Fair Value at Period End}$$

The carrying value moves up and down each period to reflect market prices.

### Income Statement — Everything Flows Through

```
┌──────────────────────────────────────────────────┐
│              INCOME STATEMENT (FVPL)             │
│                                                  │
│   Interest / Dividend Income        ✅ → I/S     │
│   Unrealized Gains                  ✅ → I/S     │
│   Unrealized Losses                 ✅ → I/S     │
│   Realized Gains (on sale)          ✅ → I/S     │
│   Realized Losses (on sale)         ✅ → I/S     │
│                                                  │
│   OCI Impact?                       🚫 NOTHING   │
│                                                  │
│   "Everything through the front door (P&L)."     │
└──────────────────────────────────────────────────┘
```

### What Goes Where

| Item | Where It Appears |
|---|---|
| Fair value | Balance Sheet |
| Interest/dividend income | Income Statement |
| Unrealized gains & losses | Income Statement |
| Realized gains & losses | Income Statement |
| OCI | Nothing — OCI is not used |

---

## 🧮 Worked Example: Midland Corporation

> [!example] **Setup (same bond)**
> Midland purchases a **9% annual coupon bond** with:
> - Face value: **$100,000**
> - Purchase price: **$96,209** (bought at a discount)
> - Yield to maturity: **10%**
> - Fair value at year-end: **$98,500**

### Step-by-Step Under FVPL

**1. Interest Revenue (Income Statement)**

$$\text{Interest Revenue} = \$96{,}209 \times 10\% = \$9{,}621$$

> [!tip] Interest revenue is still calculated using the [[effective interest method]] — the same as amortized cost. The classification doesn't change how you measure interest income.

**2. Unrealized Gain (Income Statement)**

The bond's amortized cost at year-end would be $96,830 ($96,209 + $621 discount amortization). But fair value is $98,500.

$$\text{Unrealized Gain} = \$98{,}500 - \$96{,}830 = \$1{,}670$$

This gain goes **directly to the income statement** — not OCI.

**3. Year-End Carrying Value (Balance Sheet)**

$$\text{B/S Value} = \$98{,}500 \;\text{(fair value)}$$

### Summary Table

| Line Item | Amount |
|---|---|
| **Balance Sheet: Investment** | $98,500 |
| **Income Statement: Interest Revenue** | $9,621 |
| **Income Statement: Unrealized Gain** | $1,670 |
| **OCI: Unrealized G/L** | $0 |
| **Total I/S Impact** | **$11,291** |

---

## 📈 Earnings Volatility — The Key Analyst Issue

> [!warning] **FVPL Creates Maximum Earnings Volatility**
> Because every market fluctuation runs through the income statement, companies with large FVPL portfolios will show volatile net income that may have nothing to do with operational performance.

```
   Net Income Over Time — FVPL vs. Amortized Cost
   
   FVPL:
   ╭╮   ╭─╮        ╭╮
   │ ╰╮╭╯  ╰╮  ╭╮ ╭╯│     ← Wild swings from
   │   ╰╯    ╰──╯╰─╯ │       unrealized G/L
   ╰──────────────────╯
   
   Amortized Cost:
   ──────────────────────    ← Smooth, predictable
                               interest income only
```

> [!example] **Real-World Analogy**
> Consider two identical insurance companies holding the same bond portfolio. Company A classifies bonds as FVPL; Company B uses amortized cost. In a quarter where bond prices drop 5%, Company A reports a massive loss while Company B's income is barely affected. Same economic reality — drastically different reported earnings.

---

## 🔄 IFRS vs. US GAAP Comparison

| Feature              | IFRS 9 — FVPL                                                     | US GAAP — Trading (Debt) / All Equity                                      |
| -------------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **Applicable to**    | Debt and equity                                                   | Debt: trading classification; Equity: **all** equity investments (default) |
| **Key difference**   | Equity can be FVPL *or* FVOCI (irrevocable choice)                | **All equity** at FVPL — no FVOCI option for equity under US GAAP          |
| **B/S measurement**  | Fair value                                                        | Fair value                                                                 |
| **Unrealized G/L**   | Income statement                                                  | Income statement                                                           |
| **Derivatives**      | FVPL (unless hedging)                                             | FVPL (unless hedging)                                                      |
| **Reclassification** | Equity: never (irrevocable). Debt: only if business model changes | Debt: permitted between categories. Equity: no reclassification            |

> [!danger] **Critical US GAAP Difference**
> Under US GAAP, **ALL equity investments** (except equity method or consolidation) are measured at fair value through net income. There is **no FVOCI option** for equity. This is a fundamental difference from IFRS 9. Under US GAAP, the only way to avoid P&L volatility from equity holdings is if the equity lacks a readily determinable fair value (in which case cost minus impairment may be used).

---

## 🧪 Debt vs. Equity Nuances Under FVPL

```
┌──────────────────────────────────────────────────────────┐
│                    FVPL SECURITIES                        │
│                                                          │
│   ┌─── DEBT at FVPL ───┐    ┌─── EQUITY at FVPL ───┐    │
│   │                     │    │                       │    │
│   │ Income = effective  │    │ Income = dividends    │    │
│   │ interest method     │    │ received              │    │
│   │                     │    │                       │    │
│   │ + Unrealized G/L    │    │ + Unrealized G/L      │    │
│   │ → all to I/S        │    │ → all to I/S          │    │
│   │                     │    │                       │    │
│   │ Can be reclassified │    │ CANNOT be             │    │
│   │ (if business model  │    │ reclassified          │    │
│   │  changes — rare)    │    │ (irrevocable)         │    │
│   └─────────────────────┘    └───────────────────────┘    │
└──────────────────────────────────────────────────────────┘
```

---

## ⚠️ Analyst Considerations

> [!tip] **Stripping Out the Noise**
> When analyzing a company with significant FVPL holdings:
> 1. **Separate operating income from investment income** — unrealized G/L on FVPL securities is not core operating performance
> 2. **Exclude unrealized gains from sustainable earnings** — they reverse if prices mean-revert
> 3. **Compare companies carefully** — different classification choices for the *same* type of investment create non-comparable earnings
> 4. **Watch for classification gaming** — management choosing FVPL to front-load unrealized gains (or choosing amortized cost to hide unrealized losses)

---

## 🧠 Quick Mental Model

```
┌──────────────────────────────────────────────────────┐
│         FAIR VALUE THROUGH PROFIT OR LOSS             │
│                                                      │
│   B/S:  Fair Value (market price)                    │
│   I/S:  Interest/Dividends + ALL unrealized G/L      │
│   OCI:  Nothing                                      │
│                                                      │
│   Fair value changes? → ✅ HIT THE INCOME STATEMENT  │
│   Unrealized G/L?     → ✅ RECOGNIZED IN P&L         │
│   Earnings volatility → 📈📉 MAXIMUM                │
│                                                      │
│   Think: "I'm a mark-to-market trader.               │
│           Every tick is real P&L."                    │
└──────────────────────────────────────────────────────┘
```
