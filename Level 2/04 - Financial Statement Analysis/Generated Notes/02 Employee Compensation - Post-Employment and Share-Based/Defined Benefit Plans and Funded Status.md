---
title: Defined Benefit Plans and Funded Status
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - employee-compensation
  - pensions
  - defined-benefit-plans
aliases:
  - Defined benefit plans
  - Funded status
  - PBO
  - Projected benefit obligation
  - Net pension liability
---

# Defined Benefit Plans and Funded Status

A defined benefit pension plan is a promise. The employer promises future retirement benefits, usually based on salary and years of service. That promise creates a long-term obligation today, even though the cash will be paid to employees years from now.

The core CFA issue is that pension accounting depends on estimates: discount rates, salary growth, mortality, inflation, and expected asset returns. Small assumption changes can move liabilities, income, OCI, and valuation materially.

## Defined Contribution vs Defined Benefit

| Feature | Defined contribution plan | Defined benefit plan |
|---|---|---|
| Employer promise | Contribute a specified amount | Pay specified future benefits |
| Investment risk | Employee | Employer |
| Accounting complexity | Low | High |
| Balance sheet risk | Usually minimal | Can create large net pension asset or liability |

In a defined contribution plan, the employer records expense equal to the contribution owed for the period. In a defined benefit plan, the employer must estimate the present value of promised benefits and compare it with plan assets.

## Funded Status

The balance sheet anchor is funded status:

$$
\text{Funded status}
= FV_{\text{plan assets}} - \text{Pension obligation}
$$

| Funded status | Meaning | Balance sheet presentation |
|---|---|---|
| Positive | Plan assets exceed obligation | Net pension asset |
| Negative | Obligation exceeds plan assets | Net pension liability |

The obligation is often called the [[Projected benefit obligation (PBO)]] under US GAAP or defined benefit obligation under IFRS.

## What Changes the Obligation?

The pension obligation increases when employees earn additional benefits, interest accrues on the liability, assumptions become less favorable, or plan amendments increase benefits.

It decreases when benefits are paid.

Common drivers:

- Current service cost.
- Past service cost.
- Interest cost.
- Actuarial gains and losses.
- Benefits paid.

## What Changes Plan Assets?

Plan assets increase from employer contributions and investment returns. They decrease when benefits are paid.

Plan assets belong to the pension trust, not the operating company. They are generally bankruptcy-remote and cannot simply be pulled back by the sponsor.

## IFRS Pension Cost

Under IFRS, pension cost has three broad pieces:

| Component | Location | Meaning |
|---|---|---|
| Service cost | Income statement, usually operating | Benefits earned or amended during the period |
| Net interest expense/income | Income statement, below operating | Beginning funded status multiplied by discount rate |
| Remeasurements | OCI | Actuarial gains/losses and asset return differences |

IFRS net interest uses the same discount rate for the obligation and plan assets.

$$
\text{Net interest expense}
= \text{Beginning net pension liability} \times r_{\text{discount}}
$$

If the plan is overfunded, the same logic creates net interest income.

## US GAAP vs IFRS

| Component | IFRS | US GAAP |
|---|---|---|
| Current service cost | Income statement | Income statement |
| Past service cost | Immediate income statement recognition | OCI first, then amortized to income |
| Interest on obligation | Net interest using discount rate | Gross interest cost on beginning obligation |
| Return on plan assets | Uses discount rate in net interest | Expected return on plan assets reduces pension expense |
| Actuarial gains/losses | OCI, not recycled | OCI, then amortized using corridor approach |

The total economic pension cost can be the same, but IFRS and US GAAP split the cost differently between income and OCI.

## Corridor Approach

Under US GAAP, actuarial gains and losses accumulated in AOCI are amortized only if they exceed a corridor:

$$
\text{Corridor}
= 10\% \times \max(\text{Beginning PBO}, \text{Beginning plan assets})
$$

Only the excess over the corridor is amortized into income over the remaining service lives of employees.

## Worked Example

Beginning PBO is 24,000. Beginning plan assets are 22,500. The discount rate is 6%.

Funded status:

$$
22{,}500 - 24{,}000 = -1{,}500
$$

The plan is underfunded and reports a net pension liability of 1,500.

Under IFRS, net interest expense is:

$$
1{,}500 \times 6\% = 90
$$

If current service cost is 4,000, IFRS income statement pension expense before other details is:

$$
4{,}000 + 90 = 4{,}090
$$

## Assumption Effects

| Assumption change | Effect on PBO | Effect on expense |
|---|---|---|
| Higher discount rate | Lower PBO | Lower service/interest cost pressure |
| Lower discount rate | Higher PBO | Higher cost pressure |
| Higher salary growth | Higher PBO | Higher service cost |
| Longer life expectancy | Higher PBO | Higher expected benefit payments |
| Higher expected return on assets under US GAAP | No PBO effect | Lower reported pension expense |

## Analyst Implications

Analysts should test whether assumptions are aggressive relative to peers and history. A high discount rate, low salary growth, or high expected return on plan assets can make reported results look better without improving economics.

For valuation, analysts often:

- Treat underfunded pension status as debt-like.
- Adjust operating income when pension expense classification differs.
- Compare actual asset returns with expected returns.
- Watch for large OCI balances that may later affect income under US GAAP.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Plan assets belong to the company." | They belong to the pension trust and are restricted. |
| "A higher discount rate increases PBO." | False. A higher discount rate lowers the present value of obligations. |
| "IFRS amortizes actuarial gains/losses through the income statement." | False. They stay in OCI. |
| "US GAAP and IFRS balance sheets differ for funded status." | Generally no. The major differences are income statement and OCI classification. |

## Memory Hook

Funded status asks: "Has the company set aside enough assets for the promise it made?"

## Related Concepts

- [[Projected benefit obligation (PBO)]]
- [[Plan assets]]
- [[Other comprehensive income]]
- [[Discount rate]]
- [[Earnings quality]]

