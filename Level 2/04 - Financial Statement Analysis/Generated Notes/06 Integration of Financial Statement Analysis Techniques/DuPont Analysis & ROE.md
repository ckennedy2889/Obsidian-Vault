---
title: "CFA L2 - DuPont Analysis & ROE"
subject: "Financial Statement Analysis"
tags: [CFA-L2, FSA, DuPont, ROE, profitability, leverage, efficiency]
aliases: ["DuPont", "Return on Equity Decomposition", "ROE Decomposition"]
---

# DuPont Analysis & ROE

[[Return on Equity|ROE]] is a single percentage that tells you how much profit a company generates for every dollar its owners have invested. But here's the thing — looking at ROE alone is like looking at the final score of a basketball game without knowing *why* the team won. Was it great shooting? Tight defense? They just happened to play more minutes? The number tells you the outcome, not the story.

That's exactly what [[DuPont Analysis]] fixes. It's the tool financial analysts use to crack ROE open and see what's actually driving it — whether the company is genuinely profitable, brutally efficient, or just running on borrowed money.

---

## Why Decompose ROE at All?

The whole point is to "seek granularity." A company might report a healthy, stable ROE for years running — and on the surface, everything looks fine. But DuPont analysis might reveal that the actual business is quietly deteriorating (margins shrinking, fewer sales per dollar of assets), and the only reason ROE hasn't fallen is that management has been piling on debt to compensate. That's a very different story from a company that's genuinely thriving. Without decomposition, you'd never know.

Think of it like a doctor looking at a patient's blood pressure. A normal reading doesn't mean the patient is healthy — you need to understand what's driving it.

---

## The 3-Factor DuPont Model

The 3-factor model breaks [[Return on Equity|ROE]] into three engines: **Profitability**, **Efficiency**, and **Leverage**.

**Final formula:**

$$ROE = \text{Net Profit Margin} \times \text{Asset Turnover} \times \text{Financial Leverage}$$

**Derivation — watch how the fractions cancel:**

$$ROE = \frac{\text{Net Income}}{\text{Sales}} \times \frac{\text{Sales}}{\text{Avg Assets}} \times \frac{\text{Avg Assets}}{\text{Avg Equity}} = \frac{\text{Net Income}}{\text{Avg Equity}}$$

The Sales cancel, the Assets cancel, and you're left with Net Income over Equity — which is exactly what ROE is. The decomposition isn't magic, it's just algebra. But it's *useful* algebra because each piece tells you something different.

**What each component means:**

[[Net Profit Margin]] $= \frac{NI}{Sales}$ — This is the **Offense**. For every dollar the company brings in, how much does it actually keep after paying all its costs? A higher margin means the company is either charging premium prices, controlling costs well, or both.

[[Asset Turnover]] $= \frac{Sales}{Avg\ Assets}$ — This is the **Speed**. How hard is the company working its assets? A factory that generates $5 of sales for every $1 of machinery is far more efficient than one generating $1 for $1.

[[Financial Leverage]] $= \frac{Avg\ Assets}{Avg\ Equity}$ — This is the **Multiplier**. How much of the company's asset base is funded by debt vs. by shareholders? A leverage ratio of 3.0 means $3 of assets for every $1 of equity — the rest is borrowed.

**Real-world analogy — the car wash students:**

Imagine two students running car washes. Student A charges $50 for a full detail and washes 2 cars a day. Student B charges $5 for a quick rinse and washes 20 cars a day. Both might pocket $100 at the end of the day, but they're running completely different businesses. Student A has high margin, low turnover. Student B has low margin, high turnover. DuPont is what lets you see that distinction when you're just handed "$100 profit."

---

## The 5-Factor DuPont Model

The 5-factor model goes one level deeper. It takes the [[Net Profit Margin]] from the 3-factor model and splits it into three pieces to show you exactly how much of the company's profitability is being eaten by interest payments and taxes.

**Final formula:**

$$ROE = \text{Tax Burden} \times \text{Interest Burden} \times \text{EBIT Margin} \times \text{Asset Turnover} \times \text{Financial Leverage}$$

**Derivation:**

$$ROE = \frac{NI}{EBT} \times \frac{EBT}{EBIT} \times \frac{EBIT}{Revenue} \times \frac{Sales}{Avg\ Assets} \times \frac{Avg\ Assets}{Avg\ Equity}$$

Again, the fractions cancel down to $\frac{NI}{Avg\ Equity}$.

**The three new components:**

[[Tax Burden]] $= \frac{NI}{EBT}$ — How much profit survives after the government takes its share. If a company has a tax burden of 0.70, it means 70 cents of every pre-tax dollar makes it to the bottom line. Higher is better for the company.

[[Interest Burden]] $= \frac{EBT}{EBIT}$ — How much of the operating profit is left after paying interest on debt. A ratio of 1.0 means the company has no debt — nothing is being lost to interest. The lower this falls, the more the company's debt is eating into profits.

[[EBIT Margin]] $= \frac{EBIT}{Revenue}$ — This is the purest measure of operating profitability. It strips out both taxes (which management can't fully control) and interest (which depends on financing decisions) to show how good the actual business is at making money.

---

## Worked Numerical Example — Gadget Corp

Let's bring this to life with a realistic company. Here are Gadget Corp's numbers for the year:

| Line Item | Amount |
|---|---|
| Revenue | $1,000,000 |
| EBIT (Operating Profit) | $150,000 |
| EBT (Pre-tax Profit) | $130,000 |
| Net Income | $91,000 |
| Average Total Assets | $500,000 |
| Average Shareholders' Equity | $250,000 |

**3-Factor calculation:**

$$\text{Net Profit Margin} = \frac{91{,}000}{1{,}000{,}000} = 9.1\%$$

$$\text{Asset Turnover} = \frac{1{,}000{,}000}{500{,}000} = 2.0\times$$

$$\text{Financial Leverage} = \frac{500{,}000}{250{,}000} = 2.0\times$$

$$ROE = 9.1\% \times 2.0 \times 2.0 = \mathbf{36.4\%}$$

**5-Factor calculation (same company, more detail):**

$$\text{Tax Burden} = \frac{91{,}000}{130{,}000} = 0.70$$

$$\text{Interest Burden} = \frac{130{,}000}{150{,}000} = 0.867$$

$$\text{EBIT Margin} = \frac{150{,}000}{1{,}000{,}000} = 15\%$$

$$ROE = 0.70 \times 0.867 \times 15\% \times 2.0 \times 2.0 = \mathbf{36.4\%}$$

Same answer — but now you can see that interest is quietly consuming about 13% of the company's operating profit (the interest burden of 0.867 tells you that), and taxes are taking 30 cents on every pre-tax dollar.

---

## Side-by-Side: Luxury Brand vs. Supermarket

Different industries naturally land in different corners of the DuPont framework. A luxury brand and a supermarket can have similar ROEs while running completely opposite businesses:

| | **Luxury Brand (e.g. Ferrari)** | **Supermarket (e.g. Walmart)** |
|---|---|---|
| **Strategy** | Differentiation — unique products at premium prices | Cost leadership — lowest prices, razor-thin margins |
| **[[Net Profit Margin]]** | High — keeps a lot from each sale | Low — keeps a few cents per dollar |
| **[[Asset Turnover]]** | Low — doesn't sell many units | High — inventory flies off the shelves |
| **[[Financial Leverage]]** | Often moderate | Often moderate to high |
| **ROE driver** | Margin | Turnover |
| **Vulnerability** | Volume collapse if brand weakens | Margin collapse if competitors undercut on price |

This is why you can't just compare ROE numbers across industries — a 20% ROE at Ferrari and a 20% ROE at Walmart are built completely differently. DuPont tells you *how* the sausage is made.

---

## How Analysts Detect "Masked" Problems

The most dangerous pattern DuPont reveals is **rising leverage papering over falling margins**. Here's how it plays out:

| Year | [[Net Profit Margin]] | [[Asset Turnover]] | [[Financial Leverage]] | ROE |
|---|---|---|---|---|
| Year 1 | 10% | 1.0× | 2.0× | **20%** |
| Year 2 | 8% | 1.0× | 2.5× | **20%** |
| Year 3 | 5% | 1.0× | 4.0× | **20%** |

On the surface? Rock solid. Three years of steady 20% ROE. In reality? The business is deteriorating — margins have been cut in half — and management is compensating by borrowing more and more money. Leverage has doubled. The ROE looks fine, but the company is walking into a debt trap. When it can no longer afford the interest payments, it all unravels at once.

This is exactly the kind of thing DuPont is designed to catch. Without decomposing ROE, you'd have no idea.

---

## Related Notes

- [[Financial Statement Analysis]]
- [[Return on Equity]]
- [[Net Profit Margin]]
- [[Asset Turnover]]
- [[Financial Leverage]]
- [[EBIT]]
- [[Intercorporate Investments]]
- [[Evaluating Quality of Financial Reports]]
- [[Integration of Financial Statement Analysis Techniques]]

---
