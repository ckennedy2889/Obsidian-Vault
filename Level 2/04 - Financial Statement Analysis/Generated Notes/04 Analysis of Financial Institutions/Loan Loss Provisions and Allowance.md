---
title: Loan Loss Provisions and Allowance
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - financial-institutions
  - banks
  - credit-risk
aliases:
  - Loan loss provision
  - Allowance for loan losses
  - Provision for credit losses
  - Expected credit loss
---

# Loan Loss Provisions and Allowance

Loan loss accounting is where bank earnings quality often hides. A bank estimates future credit losses, records an expense today, and builds a contra-asset allowance against loans. If estimates are too optimistic, current earnings and equity are overstated.

## Provision vs Allowance

| Item | Financial statement | Meaning |
|---|---|---|
| Loan loss provision | Income statement expense | Current-period addition to expected credit losses |
| Allowance for loan losses | Balance sheet contra-asset | Cumulative reserve against loans |
| Net charge-offs | Balance sheet allowance reduction | Loans written off net of recoveries |

The allowance is a stock. The provision is a flow.

## Allowance Roll-Forward

$$
\text{Ending allowance}
= \text{Beginning allowance}
+ \text{Provision}
- \text{Net charge-offs}
$$

Rearranged:

$$
\text{Provision}
= \text{Ending allowance}
- \text{Beginning allowance}
+ \text{Net charge-offs}
$$

This roll-forward helps detect whether provision expense is keeping up with actual losses and loan growth.

## Expected Loss

A simple credit-risk frame is:

$$
EL = PD \times LGD \times EAD
$$

where:

- $PD$ = probability of default.
- $LGD$ = loss given default.
- $EAD$ = exposure at default.

Some CFA contexts simplify expected loss to:

$$
EL \approx PD \times LGD
$$

as a rate on exposure.

## Key Ratios

| Ratio | Formula | Interpretation |
|---|---|---|
| Provision ratio | Provision / Average loans | Current credit cost intensity |
| Allowance ratio | Allowance / Total loans | Reserve cushion against loans |
| Coverage ratio | Allowance / Non-performing loans | Reserve coverage of troubled loans |
| Net charge-off ratio | Net charge-offs / Average loans | Realized credit losses |
| NPL ratio | Non-performing loans / Total loans | Asset quality deterioration |

## Earnings Management Risk

Management has discretion in estimating credit losses.

Aggressive reporting may show:

- Low provisions despite rising non-performing loans.
- Falling allowance coverage as credit quality worsens.
- Provision expense below net charge-offs for an extended period.
- Sudden large provisions after years of under-reserving.

Conservative or income-smoothing reporting may show:

- Excessive provisions in good years.
- Reserve releases in weak years to support earnings.

## Analyst Implications

An analyst should connect provisions to the credit cycle.

If unemployment rises, borrower stress increases, and non-performing loans grow, provisions should usually rise. If they do not, reported earnings may be overstated.

The allowance should also be judged relative to:

- Loan portfolio growth.
- Loan mix and concentration.
- Non-performing loans.
- Charge-off history.
- Macroeconomic outlook.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Allowance and provision are the same." | False. Allowance is balance sheet stock; provision is income statement flow. |
| "Lower provisions always mean better credit quality." | Not necessarily. They may mean under-reserving. |
| "Charge-offs are new expected losses." | Charge-offs are actual write-offs of loans previously judged impaired. |
| "A high coverage ratio is always bad." | It can indicate conservative reserving or poor loan quality; context matters. |

## Memory Hook

Provision is the expense you add this year.

Allowance is the cushion you have built so far.

## Related Concepts

- [[Allowance for loan losses]]
- [[Loan loss provisions]]
- [[CAMELS Bank Analysis]]
- [[Asset quality]]
- [[Expected credit loss]]

