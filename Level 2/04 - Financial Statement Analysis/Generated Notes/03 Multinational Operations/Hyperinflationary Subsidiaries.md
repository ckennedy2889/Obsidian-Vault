---
title: Hyperinflationary Subsidiaries
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - multinational-operations
  - hyperinflation
  - currency-translation
aliases:
  - Hyperinflationary subsidiary
  - Hyperinflationary economies
  - Disappearing plant problem
---

# Hyperinflationary Subsidiaries

Hyperinflation breaks ordinary translation logic because local currency amounts lose purchasing power so quickly that historical accounting numbers become misleading. A factory recorded years ago in a collapsing currency can look tiny when translated at today's exchange rate, even if the factory's real productive capacity has not disappeared.

That is the disappearing plant problem.

## Definition

For CFA Level II, hyperinflation is generally associated with cumulative inflation of about 100% or more over three years.

| Standard | Hyperinflation signal |
|---|---|
| US GAAP | Cumulative three-year inflation exceeds 100% |
| IFRS | Cumulative inflation approaches or exceeds 100% over three years, with qualitative judgment |

## US GAAP Treatment

Under US GAAP, the functional currency of a subsidiary in a hyperinflationary economy is treated as the parent's reporting currency. The subsidiary is remeasured using the [[Temporal Method]].

Key consequences:

- Monetary assets and liabilities are remeasured at the current rate.
- Non-monetary items carried at historical cost use historical rates.
- COGS and depreciation tied to historical-cost assets use historical rates.
- Remeasurement gains and losses go to the [[Income statement]].

US GAAP avoids translating old fixed assets at the severely weakened current exchange rate, but it does not first restate local-currency statements for inflation.

## IFRS Treatment

IFRS first restates the subsidiary's financial statements for inflation under IAS 29, then translates the inflation-adjusted statements at the current exchange rate.

The sequence matters:

1. Restate local-currency financial statements for inflation.
2. Recognize purchasing power gains or losses.
3. Translate the restated statements at the current exchange rate.

## IFRS Restatement Logic

| Item | Restatement treatment |
|---|---|
| Monetary assets and liabilities | Not restated because they are already current purchasing power claims |
| Non-monetary assets and liabilities | Restated using the general price index from acquisition date to balance sheet date |
| Share capital and other equity components | Restated from the beginning of the period or contribution date |
| Retained earnings | Usually becomes the balancing figure |
| Income statement items | Restated from the date when originally recorded |

During inflation:

- Holding monetary assets creates a purchasing power loss because cash buys less.
- Holding monetary liabilities creates a purchasing power gain because repayment occurs with cheaper currency.

## Worked Intuition

A US parent owns land in a hyperinflationary country. The land cost 1,000 local units when the exchange rate was 1 local unit per USD. Years later, the exchange rate is 10 local units per USD.

If translated only at the current rate:

$$
\text{Translated land} = \frac{1{,}000}{10} = 100
$$

The land appears to shrink from 1,000 to 100 in parent-currency terms.

Under IFRS, if the price index increased tenfold, the land is first restated:

$$
1{,}000 \times 10 = 10{,}000
$$

Then translated at the current rate:

$$
\frac{10{,}000}{10} = 1{,}000
$$

The inflation restatement prevents the real asset from disappearing merely because the currency collapsed.

## US GAAP vs IFRS

| Issue | US GAAP | IFRS |
|---|---|---|
| First step | Use temporal method | Restate for inflation |
| Translation rate after adjustment | Mixed rates under temporal method | Current rate after restatement |
| Gain/loss location | Income statement | Purchasing power gain/loss in income |
| Main advantage | Preserves historical-cost non-monetary assets from current-rate collapse | Better reflects current purchasing power |

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Hyperinflation is treated the same under IFRS and US GAAP." | False. This is the major multinational operations difference. |
| "IFRS translates first, then restates." | False. IFRS restates for inflation first, then translates. |
| "Monetary assets are restated for inflation." | False under IFRS. They already represent current monetary claims. |
| "Holding monetary liabilities during inflation is bad." | Not necessarily. Inflation creates a purchasing power gain for monetary liabilities. |

## Memory Hook

US GAAP says: "Use temporal."

IFRS says: "Inflation first, translation second."

## Related Concepts

- [[Temporal Method]]
- [[Current Rate Method]]
- [[Functional Currency]]
- [[Purchasing power]]
- [[Inflation]]

