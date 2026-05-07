---
title: Current Rate Method
subject: Financial Statement Analysis
tags: [CFA-L2, FSA, multinational-operations, currency-translation, current-rate-method]
aliases: [Current rate method, All-current method, Current method]
---

# Current Rate Method

## The Real-World Analogy

The current rate method treats the foreign subsidiary as a self-contained business. You translate the subsidiary almost as a whole, using the current exchange rate for the balance sheet and average rate for the income statement.

```text
Independent foreign operation
  ->
foreign currency is functional currency
  ->
current rate method
```

## Plain-English Definition

The current rate method is used when the subsidiary's [[Functional currency]] differs from the parent's [[Presentation currency]].

It is used when the subsidiary operates relatively independently in its local economic environment.

## Translation Rules

| Item | Exchange rate used |
|---|---|
| Assets | Current rate at balance sheet date |
| Liabilities | Current rate at balance sheet date |
| Common stock / APIC | Historical rate |
| Retained earnings | Rolled forward |
| Revenues | Average rate |
| Expenses | Average rate |
| Dividends | Historical rate on declaration date |
| Translation gain/loss | OCI as cumulative translation adjustment |

The translation adjustment goes to equity, not net income.

## Balance Sheet Exposure

Under the current rate method, all assets and liabilities are translated at the current rate.

That means the exposed position is:

$$
\text{Net asset exposure}=\text{Assets}-\text{Liabilities}
$$

Most subsidiaries have positive net assets. If the foreign currency strengthens, translated net assets increase and the parent records a positive [[Cumulative translation adjustment|CTA]] in equity.

## Worked Example

Suppose a foreign subsidiary has:

| Item | Foreign currency | Current rate | Translated |
|---|---:|---:|---:|
| Assets | 1,000 | 0.80 | 800 |
| Liabilities | 600 | 0.80 | 480 |

Net asset exposure:

$$
1{,}000-600=400
$$

If the current rate rises from 0.70 to 0.80, the foreign currency strengthened. Net assets translate higher, creating a positive CTA in equity.

## Ratio Effects

Pure balance sheet ratios are preserved because both numerator and denominator use the current rate.

Pure income statement ratios are preserved because both numerator and denominator usually use the average rate.

Mixed ratios can change because the numerator and denominator use different rates.

| Ratio type | Effect |
|---|---|
| Current ratio | Preserved |
| Debt-to-equity | Preserved, assuming both translated at current rate except equity mechanics are handled consistently |
| Gross margin | Preserved |
| ROA / ROE / asset turnover | Can change |

## Currency Movement Effects

For a typical net asset exposure:

| Foreign currency movement | Current rate method effect |
|---|---|
| Strengthens | Assets up, liabilities up, equity up, positive CTA |
| Weakens | Assets down, liabilities down, equity down, negative CTA |

Net income translates with average exchange rates, while translation gains/losses bypass the income statement.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Sending translation gain/loss to income | Current rate method sends CTA to OCI/equity |
| Translating fixed assets at historical rate | Under current rate, all assets use current rate |
| Forgetting net asset exposure | Assets minus liabilities are exposed |
| Confusing functional and presentation currency | Current rate method when functional currency differs from parent presentation currency |
| Assuming all ratios are preserved | Mixed ratios can change |

## Memory Hook

```text
Current rate method:
Current for assets and liabilities.
Average for income statement.
CTA to equity.
```

## Related Concepts

- [[Temporal Method]]
- [[Functional currency]]
- [[Presentation currency]]
- [[Cumulative translation adjustment]]
- [[Other comprehensive income]]
- [[Multinational Operations]]
- [[Exchange rate]]
