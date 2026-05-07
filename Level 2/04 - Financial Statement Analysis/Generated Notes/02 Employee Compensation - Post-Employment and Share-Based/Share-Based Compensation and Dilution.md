---
title: Share-Based Compensation and Dilution
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - employee-compensation
  - share-based-compensation
  - dilution
aliases:
  - Share-based compensation
  - Stock compensation
  - RSUs
  - Stock options compensation
  - SBC dilution
---

# Share-Based Compensation and Dilution

Share-based compensation pays employees with equity or equity-linked awards. It can preserve cash and align employees with shareholders, but it is not free. Existing shareholders give up part of the company through dilution, and analysts must treat SBC as an economic compensation cost.

## Main Instruments

| Instrument | Basic idea | Key feature |
|---|---|---|
| Restricted stock / RSUs | Shares or share units that vest over time | Retention value even if share price falls |
| Stock options | Employee call options on company stock | Upside-heavy payoff; can expire worthless |
| SARs / phantom shares | Cash or share payout based on share performance | Mimics equity exposure |
| ESPP / ESOP | Employee share purchase or ownership plans | Employees acquire shares, often at a discount |

Options encourage risk-taking more than RSUs because options have asymmetric payoff: upside participation with limited downside once underwater.

## Vesting Conditions

| Condition | Requirement | Accounting intuition |
|---|---|---|
| Service condition | Employee stays for a specified period | Expense recognized over service period; reversed if forfeited |
| Performance condition | Non-market target is met, such as EPS | Expense depends on whether target is probable |
| Market condition | Share-price or market-relative target | Reflected in grant-date fair value; expense is not reversed solely because condition fails |

## Expense Recognition

For equity-settled awards, compensation expense is generally based on grant-date fair value and recognized over the vesting period.

The accounting mechanism:

1. Estimate fair value at grant date.
2. Spread compensation expense over the service or vesting period.
3. Increase equity as compensation is recognized.
4. Adjust for forfeitures when required.

This means SBC is noncash in the period of expense recognition, but it is still a real cost because it transfers ownership value to employees.

## Tax Effects

Book expense and tax deductions often differ.

| Item | Financial reporting | Tax return |
|---|---|---|
| Timing | Over vesting period | Usually at settlement or exercise |
| Amount | Grant-date fair value | Settlement value for RSUs or intrinsic value for options |

If the share price rises, the tax deduction can exceed book expense. If the share price falls, the deduction can be lower than book expense.

| Scenario | IFRS | US GAAP |
|---|---|---|
| Tax deduction exceeds book expense | Excess benefit generally goes to equity | Decreases income tax expense |
| Tax deduction is below book expense | Shortfall generally goes to equity | Increases income tax expense |

Under US GAAP, large SBC tax windfalls can make the effective tax rate look unusually low during periods of rising share prices.

## Dilution

Basic shares increase when awards settle or options are exercised. Diluted shares include the effect of potentially dilutive awards, commonly using the [[Treasury stock method]].

For options, the intuition is:

1. Assume in-the-money options are exercised.
2. The company receives exercise proceeds.
3. The company uses those proceeds to repurchase shares at the average market price.
4. Net new shares are added to diluted shares.

Approximate incremental shares:

$$
\text{Incremental shares}
= N_{\text{options}}
- \frac{N_{\text{options}} \times X}{P}
$$

where $X$ is exercise price and $P$ is average market price.

If options are out of the money, they are antidilutive and excluded.

## Analyst Implications

Analysts should:

- Treat SBC as recurring compensation, especially for technology and growth companies.
- Use fully diluted share counts in valuation.
- Avoid adding back SBC blindly when estimating sustainable cash generation.
- Consider future dilution from unvested awards.
- Separate operating performance from tax-rate changes caused by SBC windfalls or shortfalls.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "SBC is noncash, so it is not an economic cost." | False. It transfers equity value to employees. |
| "Options always dilute." | False. Out-of-the-money options are antidilutive for diluted EPS. |
| "RSUs and options create the same incentives." | False. Options have more upside asymmetry. |
| "A low effective tax rate from SBC is always sustainable." | False. It depends partly on share price performance. |

## Memory Hook

SBC saves cash today by paying with ownership.

That makes the cost easy to miss, not economically free.

## Related Concepts

- [[RSU]]
- [[Stock options]]
- [[Treasury stock method]]
- [[Diluted EPS]]
- [[Effective tax rate]]

