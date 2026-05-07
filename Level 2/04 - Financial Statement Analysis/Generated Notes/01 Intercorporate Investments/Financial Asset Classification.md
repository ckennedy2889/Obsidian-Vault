---
title: Financial Asset Classification
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - intercorporate-investments
  - financial-assets
  - IFRS-9
aliases:
  - Amortized cost vs FVPL vs FVOCI
  - FVPL vs FVOCI
  - Financial assets classification
  - IFRS 9 financial assets
---

# Financial Asset Classification

Financial asset classification determines where valuation changes appear. The balance sheet may show cost or fair value, and the income statement may absorb all fair value volatility, only interest and dividends, or almost none of the market movement.

For CFA Level II, the core comparison is [[Amortised cost]], [[FVPL]], and [[FVOCI]].

## IFRS 9 Decision Logic

For debt instruments, IFRS starts with two questions:

1. What is the business model?
2. Do contractual cash flows pass the SPPI test, meaning solely payments of principal and interest?

| Business model / cash flow profile | Classification |
|---|---|
| Hold to collect contractual cash flows and cash flows are SPPI | Amortized cost |
| Hold to collect and sell, and cash flows are SPPI | FVOCI |
| Trading, non-SPPI, derivatives, or accounting mismatch election | FVPL |

Equity instruments are usually FVPL, unless IFRS permits an irrevocable election to classify a non-trading equity investment as FVOCI.

## Amortized Cost

Amortized cost is for debt instruments held to collect principal and interest.

Balance sheet:

$$
\text{Carrying value}
= \text{Initial cost}
\text{ discount amortization}
- \text{ premium amortization}
- \text{impairment}
$$

Income statement:

- Interest income is recognized using the [[effective interest method]].
- Fair value changes are ignored unless impairment occurs.

This produces smooth income but can hide market value changes.

## FVPL

FVPL means fair value through profit or loss.

Balance sheet:

- Asset is carried at fair value.

Income statement:

- Interest and dividends go to profit or loss.
- Realized and unrealized fair value gains and losses go to profit or loss.

FVPL creates the most net income volatility because every fair value change flows through earnings.

## FVOCI

FVOCI means fair value through other comprehensive income.

Balance sheet:

- Asset is carried at fair value.

Income statement and OCI:

- Interest income on debt goes to profit or loss.
- Dividends on equity generally go to profit or loss.
- Unrealized fair value gains and losses go to [[Other comprehensive income]].
- For debt FVOCI, realized gains and losses are recycled to profit or loss when sold.
- For IFRS equity FVOCI, gains and losses are not recycled to profit or loss.

FVOCI makes the balance sheet current while keeping some fair value noise out of net income.

## One Example Across the Three Categories

A company buys a bond for 96,209. The coupon is 9%, market yield is 10%, and year-end fair value is 98,500. Effective interest income is:

$$
96{,}209 \times 10\% = 9{,}621
$$

The amortized cost carrying value is:

$$
96{,}209 + 621 = 96{,}830
$$

The fair value gain relative to amortized cost is:

$$
98{,}500 - 96{,}830 = 1{,}670
$$

| Classification | Balance sheet | Income statement | OCI |
|---|---:|---:|---:|
| Amortized cost | 96,830 | 9,621 interest income | 0 |
| FVPL | 98,500 | 9,621 interest + 1,670 unrealized gain | 0 |
| FVOCI | 98,500 | 9,621 interest income | 1,670 unrealized gain |

Same economics. Different financial statement geography.

## IFRS vs US GAAP

| Issue | IFRS | US GAAP |
|---|---|---|
| Debt classification basis | Business model + SPPI | Management intent and ability |
| Debt categories | Amortized cost, FVPL, FVOCI | Held-to-maturity, trading, available-for-sale |
| Equity default | FVPL | FVPL |
| Equity FVOCI option | Allowed for some non-trading equities by irrevocable election | Generally not available |
| Reclassification | Debt only, when business model changes | Generally limited |

## Reclassification Traps

Under IFRS:

- Equity investment classification is irrevocable.
- Debt reclassification occurs only when the business model changes.
- A business model change should be significant and infrequent.
- Prior periods are not restated.

## Analyst Implications

Classification affects:

- Net income volatility.
- OCI and accumulated OCI.
- Comparability across firms.
- Ability to "cherry-pick" gains by selling appreciated FVOCI debt securities.
- Reported earnings quality when unrealized gains dominate profit.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Fair value on the balance sheet means fair value changes hit net income." | Not always. FVOCI sends unrealized gains/losses to OCI. |
| "Amortized cost ignores credit risk." | False. Impairment must still be considered. |
| "Equity FVOCI gains recycle to net income under IFRS." | False. Equity FVOCI gains do not recycle through P&L. |
| "FVPL and FVOCI have different balance sheet values." | Usually false. Both carry the asset at fair value. |

## Memory Hook

Amortized cost: cost-based balance sheet, interest in income.

FVPL: fair value balance sheet, all volatility in income.

FVOCI: fair value balance sheet, unrealized volatility parked in OCI.

## Related Concepts

- [[Amortised cost]]
- [[FVPL]]
- [[FVOCI]]
- [[Other comprehensive income]]
- [[Effective interest method]]

