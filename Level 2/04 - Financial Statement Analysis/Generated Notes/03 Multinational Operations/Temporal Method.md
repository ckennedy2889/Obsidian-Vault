---
title: Temporal Method
subject: Financial Statement Analysis
tags: [CFA-L2, FSA, multinational-operations, currency-translation, temporal-method]
aliases: [Temporal method, Remeasurement method, Remeasurement]
---

# Temporal Method

## The Real-World Analogy

The temporal method asks: "What would the subsidiary's accounts look like if they had originally been recorded in the parent's currency?"

So it preserves the measurement basis:

```text
Current-value items -> current exchange rate
Historical-cost items -> historical exchange rate
```

## Plain-English Definition

The temporal method is used when the subsidiary's [[Functional currency]] is the parent's [[Presentation currency]].

It is also used under US GAAP for hyperinflationary subsidiaries.

The subsidiary is viewed as an extension of the parent, not as an independent local operation.

## Translation Rules

| Item | Exchange rate used |
|---|---|
| Monetary assets | Current rate |
| Monetary liabilities | Current rate |
| Nonmonetary assets at historical cost | Historical rate |
| Nonmonetary liabilities at historical cost | Historical rate |
| Nonmonetary items at current value | Current rate |
| Common stock / APIC | Historical rate |
| Revenues | Average rate |
| Most expenses | Average rate |
| COGS | Historical rate if inventory at historical cost |
| Depreciation | Historical rate tied to fixed assets |
| Remeasurement gain/loss | Income statement |

## Balance Sheet Exposure

Under the temporal method, only monetary items translated at the current rate are exposed.

The exposed position is:

$$
\text{Net monetary exposure}
=\text{Monetary assets}-\text{Monetary liabilities}
$$

Many subsidiaries have net monetary liability exposure because payables and debt exceed cash and receivables.

## Gain/Loss Direction

For a net monetary liability exposure:

| Foreign currency movement | Effect |
|---|---|
| Foreign currency strengthens | Translation loss |
| Foreign currency weakens | Translation gain |

Why? If liabilities are monetary and translated at the current rate, a stronger foreign currency makes those liabilities more expensive in the parent's currency.

For a net monetary asset exposure, the direction reverses.

## Worked Example

Suppose a subsidiary has:

| Item | Foreign currency |
|---|---:|
| Monetary assets | 300 |
| Monetary liabilities | 800 |

Net monetary exposure:

$$
300-800=-500
$$

This is a net monetary liability exposure.

If the foreign currency strengthens, the translated value of liabilities rises more than monetary assets. The subsidiary records a remeasurement loss in the income statement.

## Ratio Effects

Temporal method can distort almost all ratios because different items in the same financial statement may use different exchange rates.

Examples:

| Ratio | Why distorted |
|---|---|
| Gross margin | Sales often average rate; COGS may historical rate |
| Fixed asset turnover | Sales average rate; fixed assets historical rate |
| Current ratio | Monetary and nonmonetary current assets may use different rates |
| ROA | NI affected by remeasurement gain/loss; assets use mixed rates |

## Current Rate Method vs Temporal Method

| Feature | Current Rate Method | Temporal Method |
|---|---|---|
| When used | Functional currency differs from parent currency | Functional currency equals parent currency |
| BS exposure | Net assets | Net monetary assets/liabilities |
| Assets | All current rate | Monetary current; nonmonetary historical unless at current value |
| COGS/depreciation | Average rate | Historical rate |
| Translation gain/loss | OCI/equity | Income statement |
| Income volatility | Lower | Higher |

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Translating all assets at current rate | That is current rate method, not temporal |
| Sending gain/loss to OCI | Temporal remeasurement gain/loss hits income |
| Forgetting COGS/depreciation historical rates | Match expenses to inventory/PPE historical rates |
| Ignoring net monetary exposure | Direction of gain/loss depends on monetary assets vs liabilities |
| Thinking currency strengthening always helps | With net monetary liabilities, strengthening creates a loss |

## Memory Hook

```text
Temporal preserves time:
historical-cost items use historical rates.
current-value items use current rates.
remeasurement gain/loss hits income.
```

## Related Concepts

- [[Current Rate Method]]
- [[Functional currency]]
- [[Presentation currency]]
- [[Monetary assets]]
- [[Nonmonetary assets]]
- [[Foreign currency transaction]]
- [[Multinational Operations]]
- [[Hyperinflation]]
