---
title: "FCFF vs FCFE Valuation Framework"
subject: "Equity Investments"
tags: [CFA-L2, equity, free-cash-flow, valuation, FCFF, FCFE]
aliases:
  - FCFF valuation
  - FCFE valuation
  - Free cash flow valuation
  - Free cash flow to the firm
  - Free cash flow to equity
---

# FCFF vs FCFE Valuation Framework

Free cash flow valuation asks: **how much cash can the business distribute after it funds operations and required investment?**

The key distinction is who the cash flow belongs to.

| Cash flow | Belongs to | Discount rate | Valuation output |
|---|---|---|---|
| [[Free Cash Flow to the Firm]] | Debt and equity providers | [[WACC]] | Firm value |
| [[Free Cash Flow to Equity]] | Common shareholders | Required return on equity | Equity value |

## FCFF

FCFF is cash flow available to all capital providers after operating expenses, taxes, fixed capital investment, and working capital investment.

Starting from net income:

$$
FCFF = NI + NCC + Int(1-t) - FCInv - WCInv
$$

Starting from CFO:

$$
FCFF = CFO + Int(1-t) - FCInv
$$

Starting from EBIT:

$$
FCFF = EBIT(1-t) + Dep - FCInv - WCInv
$$

Starting from EBITDA:

$$
FCFF = EBITDA(1-t) + Dep(t) - FCInv - WCInv
$$

### Why after-tax interest is added back

Net income is after interest expense. But FCFF is before payments to debt holders. To move from net income back to a firm-level cash flow, add back after-tax interest:

$$
Int(1-t)
$$

The tax shield remains because taxes actually paid were lower due to interest deductibility.

## FCFE

FCFE is cash flow available to common shareholders after debt holders have been paid and after net borrowing has occurred.

Starting from net income:

$$
FCFE = NI + NCC - FCInv - WCInv + \text{Net borrowing}
$$

Starting from CFO:

$$
FCFE = CFO - FCInv + \text{Net borrowing}
$$

Link from FCFF:

$$
FCFE = FCFF - Int(1-t) + \text{Net borrowing}
$$

Debt affects FCFE because borrowing gives cash to equity holders today, while interest and principal repayment reduce future cash available to equity.

## Target Debt Ratio FCFE

When a company maintains a target debt ratio, the FCFE formula can be written:

$$
FCFE = NI - (1-DR)(FCInv-Dep) - (1-DR)(WCInv)
$$

Where \(DR\) is the debt ratio used to finance incremental investment.

The intuition: if debt finances \(DR\) of new investment, equity only has to finance \(1-DR\).

## Discount Rate Matching

Never mismatch cash flows and discount rates.

| Cash flow | Correct discount rate | Wrong pairing |
|---|---|---|
| FCFF | WACC | Cost of equity |
| FCFE | Required return on equity | WACC |

After discounting FCFF:

$$
\text{Equity value} = \text{Firm value} - \text{Market value of debt}
$$

After discounting FCFE, the result is already equity value.

## Single-Stage Models

If FCFF grows at a constant rate:

$$
V_{\text{firm}} = \frac{FCFF_1}{WACC-g}
$$

Then:

$$
V_{\text{equity}} = V_{\text{firm}} - \text{Market value of debt}
$$

If FCFE grows at a constant rate:

$$
V_{\text{equity}} = \frac{FCFE_1}{r-g}
$$

Where \(r\) is the required return on equity.

## When to Use FCFF vs FCFE

| Situation | Preferred model | Why |
|---|---|---|
| Stable leverage and positive FCFE | FCFE | Directly values equity |
| Changing capital structure | FCFF | WACC is usually more stable than cost of equity and FCFE |
| Negative FCFE due to leverage or reinvestment | FCFF | Firm cash flow may still be positive |
| Control perspective | FCFF or FCFE | Free cash flow reflects capacity to pay, not current dividend policy |
| Dividends differ from capacity to pay | FCFF or FCFE | Better than DDM |

## Worked Example

A company reports:

- Net income: \$100
- Depreciation: \$20
- Interest expense: \$15
- Tax rate: 30%
- Fixed capital investment: \$40
- Working capital investment: \$10
- Net borrowing: \$25

FCFF:

$$
FCFF = 100 + 20 + 15(1-0.30) - 40 - 10
$$

$$
FCFF = 100 + 20 + 10.5 - 40 - 10 = \$80.5
$$

FCFE:

$$
FCFE = 100 + 20 - 40 - 10 + 25 = \$95
$$

Link:

$$
FCFE = 80.5 - 10.5 + 25 = \$95
$$

The link works because FCFF is before debt payments, while FCFE is after after-tax interest but includes net borrowing.

## Working Capital Investment

Working capital investment should reflect operating working capital.

Usually exclude:

- Cash and cash equivalents.
- Notes payable and short-term debt.

Cash is the output of the cash flow calculation. Short-term debt is financing, not operating working capital.

## Dividends and Repurchases

Dividends and share repurchases do not determine FCFF or FCFE. They are distributions of free cash flow, not operating sources or required reinvestment.

Exam trap: if a vignette gives dividends paid, do not subtract dividends in FCFE unless the question is asking for a reconciliation of cash or payout, not free cash flow.

## EBITDA Is Not Free Cash Flow

EBITDA ignores:

- Taxes.
- Working capital investment.
- Fixed capital investment.
- Depreciation tax shield details.

Starting from EBITDA:

$$
FCFF = EBITDA(1-t) + Dep(t) - FCInv - WCInv
$$

The \(Dep(t)\) term is the depreciation tax shield, not full depreciation. Starting from EBIT after tax, you add back full depreciation because EBIT has already subtracted it.

## Exam Traps

- **Match cash flow and discount rate.** FCFF with WACC; FCFE with cost of equity.
- **Subtract debt only after FCFF valuation.** FCFE valuation already gives equity value.
- **Do not subtract dividends or repurchases from FCFE.** They are uses of FCFE.
- **Debt issuance increases FCFE, not FCFF.**
- **After-tax interest links FCFF and FCFE.** Use \(Int(1-t)\), not pretax interest.
- **Exclude cash and short-term debt from working capital investment.**
- **EBITDA is not cash flow.** It ignores taxes and reinvestment.
- **Use FCFF when capital structure is changing or FCFE is negative.**

## Memory Hook

**FCFF pays everyone, so discount at WACC. FCFE pays shareholders, so discount at equity cost.**
