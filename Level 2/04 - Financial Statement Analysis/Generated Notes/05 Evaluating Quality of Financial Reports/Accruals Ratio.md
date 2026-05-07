---
title: Accruals Ratio
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - earnings-quality
  - accruals
  - integration
aliases:
  - Accruals ratio
  - Balance sheet accruals ratio
  - Cash flow accruals ratio
  - NOA accruals ratio
---

# Accruals Ratio

Earnings can be split into cash and accrual components. The cash component is usually more persistent and harder to manipulate. The accrual component depends more on estimates, timing choices, and management judgment.

The accruals ratio measures how much of earnings is tied to accruals rather than cash.

## Core Intuition

$$
\text{Earnings} = \text{Cash flow} + \text{Accruals}
$$

Lower accruals generally indicate higher [[Earnings quality]]. High positive accruals mean earnings are less cash-backed and may be less persistent.

The persistence point is the reason the ratio matters. Cash-flow-backed earnings tend to persist better than accrual-heavy earnings. In regression language, analysts often expect the coefficient on cash flow persistence to be higher than the coefficient on accrual persistence:

$$
Earnings_{t+1} = a + \beta_1(Cash\ flow_t) + \beta_2(Accruals_t) + \epsilon
$$

If $\beta_1 > \beta_2$, the cash component of earnings is more persistent than the accrual component.

## Net Operating Assets

Both common accruals ratio approaches scale by average [[Net Operating Assets]].

$$
NOA =
(\text{Total assets} - \text{Cash} - \text{Marketable securities})
- (\text{Total liabilities} - \text{Total debt})
$$

Operating assets exclude cash and marketable securities. Operating liabilities exclude financing debt.

Average NOA:

$$
\text{Average NOA}
= \frac{NOA_{END} + NOA_{BEG}}{2}
$$

## Balance Sheet Approach

The balance sheet approach measures accruals as the change in net operating assets.

$$
\text{Accruals}_{BS}
= NOA_{END} - NOA_{BEG}
$$

$$
\text{Accruals ratio}_{BS}
= \frac{NOA_{END} - NOA_{BEG}}
{(NOA_{END} + NOA_{BEG})/2}
$$

If NOA increases substantially, earnings may have been supported by accrual buildup rather than cash realization.

## Cash Flow Statement Approach

The cash flow approach starts with net income and subtracts cash flow components connected to operating and investing activity.

$$
\text{Accruals}_{CF}
= NI - CFO - CFI
$$

$$
\text{Accruals ratio}_{CF}
= \frac{NI - CFO - CFI}
{(NOA_{END} + NOA_{BEG})/2}
$$

[[CFF]] is excluded because financing cash flows relate to how the business is funded, not whether earnings were cash-backed.

## Sign Interpretation

| Accruals ratio | Interpretation |
|---:|---|
| Low or negative | Earnings are more cash-supported; usually higher quality |
| High positive | Earnings rely more on accruals; higher risk of weak persistence |
| Rising over time | Potential deterioration in earnings quality |

Context matters. A growing firm may naturally build working capital, but persistent high positive accruals deserve scrutiny.

## Worked Example

A company reports:

- Beginning NOA: 900.
- Ending NOA: 1,100.
- Net income: 160.
- CFO: 120.
- CFI: -30.

Balance sheet accruals:

$$
1{,}100 - 900 = 200
$$

Average NOA:

$$
\frac{1{,}100 + 900}{2} = 1{,}000
$$

Balance sheet accruals ratio:

$$
\frac{200}{1{,}000} = 20\%
$$

Cash flow accruals:

$$
160 - 120 - (-30) = 70
$$

Cash flow accruals ratio:

$$
\frac{70}{1{,}000} = 7\%
$$

The two approaches can differ because they use different data and can be affected by acquisitions, divestitures, and classification issues.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Higher accruals ratio means higher earnings quality." | Usually false. Lower accruals are generally better. |
| "CFF is included in the cash flow accruals formula." | False. Use NI minus CFO minus CFI. |
| "NOA equals total assets minus total liabilities." | False. Remove financial assets and financing liabilities. |
| "Negative CFI is subtracted as a positive use of cash." | Be careful with signs: $NI - CFO - CFI$ means subtracting a negative CFI increases accruals. |

## Memory Hook

Accruals ratio asks: "How much of earnings has not turned into cash?"

## Related Concepts

- [[Net Operating Assets]]
- [[Cash Flow from Operations]]
- [[Financial Reporting Quality vs Earnings Quality]]
- [[Beneish M-Score]]
- [[Earnings quality]]
