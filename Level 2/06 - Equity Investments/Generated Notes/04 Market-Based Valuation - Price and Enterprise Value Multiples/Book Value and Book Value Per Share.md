---
title: Book Value and Book Value Per Share
subject: Equity Investments
tags:
  - CFA-L2
  - equity-valuation
  - book-value
  - price-to-book
  - balance-sheet
  - shareholders-equity
aliases:
  - BVPS
  - Book Value Per Share
  - Net Asset Value Per Share
---

# Book Value and Book Value Per Share

## The Real-World Analogy: What Would You Get If You Liquidated the Business?

Imagine you buy a small restaurant. You pay $200,000 for it. But what does the restaurant *actually own*? It owns kitchen equipment worth $80,000, furniture worth $20,000, a lease deposit of $5,000, and has $15,000 cash in the register. It also owes $40,000 on a loan to buy the equipment. So if you stripped the whole thing down, sold the assets, and paid off every debt, you'd walk away with $80K + $20K + $5K + $15K − $40K = **$80,000**. That's the **book value** — the net worth of the business as recorded on paper.

Now divide that $80,000 by the number of ownership "shares" (say you split the restaurant into 1,000 equal shares), and each share represents $80 of net underlying assets. That's **book value per share** (BVPS).

In the public markets, this exact same logic applies to corporations — but instead of kitchen equipment and leases, you're looking at billions of dollars of assets, liabilities, and decades of accounting history.

---

## What "Book Value" Actually Means

**Book value** (also called **shareholders' equity** or **net assets**) is the accounting value of what shareholders own after all creditors have been paid. It lives entirely on the [[Balance Sheet]] and is calculated as:

$$\text{Book Value} = \text{Total Assets} - \text{Total Liabilities}$$

This is not a market value. It is not what the company could sell for. It is the *historical, accounting-based* measure of what shareholders have put in plus what the company has retained over time.

Shareholders' equity on the balance sheet is built from several components:

| Component | What it represents |
|---|---|
| **Common stock (par value)** | The legal face value of shares issued — often a trivially small number (e.g., $0.01/share) |
| **Additional paid-in capital (APIC)** | The *excess* investors paid over par value when shares were originally issued |
| **Retained earnings** | Cumulative net income the company kept rather than paying out as dividends |
| **Accumulated other comprehensive income (AOCI)** | Unrealized gains/losses on certain items (e.g., available-for-sale securities, pension adjustments) that bypass the income statement |
| **Treasury stock** | Shares the company has repurchased from the market — recorded as a *negative* (it reduces equity) |

Put it all together:

$$\text{Book Value} = \text{Par Value} + \text{APIC} + \text{Retained Earnings} + \text{AOCI} - \text{Treasury Stock}$$

---

## Book Value Per Share (BVPS)

Once you have total book value, dividing by the number of shares outstanding tells you how much of that net accounting wealth each share "represents":

$$\boxed{\text{BVPS} = \frac{\text{Total Shareholders' Equity} - \text{Preferred Equity}}{\text{Common Shares Outstanding}}}$$

The **preferred equity** subtraction is critical. Preferred shareholders have a senior claim to assets over common shareholders. When we talk about "book value per *common* share," we must strip out the value belonging to preferred stockholders first — just as they'd get paid first in a liquidation before common shareholders see a cent.

> [!tip] Why subtract preferred equity?
> Think of it like a bankruptcy waterfall: debt holders get paid first, then preferred shareholders, and only then do common shareholders get what's left. BVPS measures only what common shareholders would theoretically receive. Preferred equity is already "spoken for."

### Which share count to use?

Use **shares outstanding** — the shares actually held by the public and other investors. Do *not* use **authorized shares** (the maximum the company is legally allowed to issue) or **issued shares** (all shares ever created, including treasury shares). Treasury shares are shares the company has repurchased and holds itself — they carry no voting rights and receive no dividends, so they don't belong in the denominator.

$$\text{Shares Outstanding} = \text{Shares Issued} - \text{Treasury Shares}$$

---

## Worked Numerical Example

**Scenario:** TechCo Inc. has the following balance sheet items:

| Item | Amount |
|---|---|
| Total Assets | $5,200,000 |
| Total Liabilities | $3,100,000 |
| Preferred Equity (200 shares, $500 par) | $100,000 |
| Common Shares Issued | 50,000 |
| Treasury Shares | 5,000 |

**Step 1 — Calculate total shareholders' equity:**

$$\text{Total Equity} = \$5{,}200{,}000 - \$3{,}100{,}000 = \$2{,}100{,}000$$

**Step 2 — Subtract preferred equity to get common equity:**

$$\text{Common Equity} = \$2{,}100{,}000 - \$100{,}000 = \$2{,}000{,}000$$

**Step 3 — Calculate shares outstanding:**

$$\text{Shares Outstanding} = 50{,}000 - 5{,}000 = 45{,}000 \text{ shares}$$

**Step 4 — Calculate BVPS:**

$$\text{BVPS} = \frac{\$2{,}000{,}000}{45{,}000} = \$44.44 \text{ per share}$$

If TechCo's stock is currently trading at $89, the [[Price-to-Book Ratio]] (P/B) is:

$$\text{P/B} = \frac{\$89}{\$44.44} = 2.0\times$$

This means investors are willing to pay $2 for every $1 of accounting net worth — implying they believe the business can generate returns *above* its cost of equity, creating value beyond what's on the books.

---

## Why Book Value Differs from Market Value

This gap — which can be enormous — is one of the most important things to understand in equity analysis.

**Book value is backward-looking.** Assets are recorded at *historical cost* (minus depreciation), not what they'd fetch in the market today. A piece of land bought in 1985 for $500,000 might be worth $10 million now, but the balance sheet still shows $500,000.

**Book value ignores intangibles.** A pharmaceutical company's most valuable assets are its drug patents, R&D pipeline, and brand reputation. Under accounting rules ([[IFRS vs. GAAP]]), most internally generated intangibles are *expensed*, not capitalized. They never appear on the balance sheet at all, so book value dramatically understates the true economic worth.

**Market value reflects future expectations.** The stock price embeds investors' expectations about future cash flows, competitive advantages, and growth. Book value reflects only what has already happened.

```
                    +---------------------+
  BOOK VALUE        |  Historical costs   |
  (Balance Sheet)   |  Depreciated assets |
                    |  Retained earnings  |
                    +---------------------+
                             ↕  GAP = "unrecorded" intangibles,
                                       growth expectations,
                                       market sentiment
                    +---------------------+
  MARKET VALUE      |  Future cash flows  |
  (Stock Price ×    |  Brand / patents    |
   Shares Out.)     |  Competitive moat   |
                    +---------------------+
```

---

## When Book Value is Most Useful

Book value and BVPS are most meaningful for **asset-heavy, capital-intensive businesses** where most value really does sit on the balance sheet:

| Industry | Why P/B is relevant |
|---|---|
| **Banks and financial institutions** | Assets are mostly financial instruments marked close to market; equity = net financial assets |
| **Insurance companies** | Balance sheet is the product — premiums collected vs. claims owed |
| **REITs and real estate** | Property assets are tangible and can be appraised |
| **Manufacturing / utilities** | Heavy plant & equipment; less reliance on unrecorded intangibles |

It is *much less* useful for technology, software, pharmaceutical, or brand-driven companies where intangible value dominates.

---

## Book Value in Equity Valuation: The P/B Ratio

For CFA Level 2, book value is primarily encountered through the **[[Price-to-Book Ratio]]** (P/B or P/BV):

$$\text{P/B} = \frac{\text{Market Price per Share}}{\text{Book Value per Share}}$$

The **justified P/B** (what the ratio *should* be based on fundamentals) is derived from the [[Gordon Growth Model]] rearrangement:

$$\text{Justified P/B} = \frac{ROE - g}{r - g}$$

Where:
- $ROE$ = Return on Equity (net income ÷ book equity)
- $g$ = sustainable growth rate
- $r$ = required return on equity

This is a crucial insight: **a company deserves a P/B above 1.0 only if its ROE exceeds its cost of equity.** If ROE = r, then justified P/B = 1.0 — you'd pay exactly book value. If ROE < r (the company destroys value), justified P/B < 1.0 — the company is worth *less* than its accounting net worth.

> [!example] Justified P/B in action
> A bank has ROE = 12%, required return r = 10%, and sustainable growth g = 4%.
> $$\text{Justified P/B} = \frac{0.12 - 0.04}{0.10 - 0.04} = \frac{0.08}{0.06} = 1.33\times$$
> Investors should pay 1.33× book value. If the bank currently trades at 0.9× book, it looks undervalued relative to fundamentals.

---

## Important Accounting Adjustments

Raw book value from the financial statements isn't always the right number. Analysts often adjust:

**1. Intangible assets and goodwill** — [[Goodwill]] (from acquisitions) and other acquired intangibles inflate book value but may have little or no liquidation value. Many analysts strip these out to get **tangible book value**:

$$\text{Tangible Book Value} = \text{Book Value} - \text{Goodwill} - \text{Other Intangibles}$$

**2. Off-balance sheet items** — Operating leases (pre-IFRS 16 for older data), securitized receivables, and similar structures may hide real liabilities, overstating book value.

**3. Fair value vs. historical cost** — Under [[IFRS vs. GAAP]], certain assets (investment properties, available-for-sale securities) may be carried at fair value, making IFRS balance sheets somewhat closer to market reality than historical-cost GAAP statements.

---

## Memory Hook

**"BVPS = What you'd get in a neat, orderly liquidation — no fire sale, just pay off everyone and split the rest."**

Or use the acronym **PARTS** to remember what builds equity:
- **P**ar value of common stock
- **A**dditional paid-in capital
- **R**etained earnings
- **T**reasury stock (subtract!)
- **S**trong winds of AOCI (other comprehensive income)

---

## Related Notes

- [[Price-to-Book Ratio]]
- [[Justified Leading and Trailing PE]]
- [[PVGO - Present Value of Growth Opportunities]]
- [[DuPont Analysis & ROE]]
- [[Gordon Growth Model]]
- [[Goodwill]]
- [[IFRS vs. GAAP]]
- [[Balance Sheet]]
