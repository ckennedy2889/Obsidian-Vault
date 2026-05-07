---
title: "Estimating the Cost of Debt"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, cost-of-capital, debt, WACC]
aliases:
  - Cost of debt
  - Matrix pricing
  - Rate implicit in the lease
  - Incremental borrowing rate
  - Country risk premium
---

# Estimating the Cost of Debt

The [[cost of debt]] is the return debt investors require to lend to the company today. For WACC, you want the **marginal current market cost**, not the coupon rate on old debt and not the historical rate the company happened to negotiate years ago.

The baseline intuition is:

$$
r_d = r_f + \text{credit spread}
$$

For international borrowers, add country risk when appropriate:

$$
r_d = r_f + \text{credit spread} + \text{country risk premium}
$$

## Method Selection

| Situation | Best estimate |
|---|---|
| Liquid publicly traded straight debt | Yield to maturity on current debt |
| Longest debt is illiquid but shorter debt is liquid | Use the more reliable liquid issue |
| Thinly traded or non-traded rated debt | Matrix pricing using similar rated bonds |
| Unrated debt | Infer synthetic rating from ratios, then add rating spread |
| Bank debt | Current bank borrowing rate if it reflects current risk |
| Finance lease | Rate implicit in the lease; if unavailable, incremental borrowing rate |
| Foreign borrower or emerging market exposure | Add country risk premium when not already embedded |

## Publicly Traded Debt

If the company has publicly traded, option-free debt, use the current [[yield to maturity]].

The ideal bond is:

- Straight, not convertible.
- Noncallable or option-free.
- Long maturity.
- Liquidly traded.
- Representative of the company's current credit risk.

### Why YTM, not coupon?

The coupon is the contractual interest rate set when the bond was issued. YTM reflects the return investors require today at the current market price. Cost of capital is about today's opportunity cost, so use YTM.

## Matrix Pricing

Use matrix pricing when the company's own debt is not traded or is thinly traded.

The process:

1. Identify bonds with similar credit ratings and maturities.
2. Estimate their YTMs.
3. Build a maturity-yield matrix.
4. Interpolate to the target maturity.

Linear interpolation:

$$
y_x = y_s + \left(\frac{y_l-y_s}{M_l-M_s}\right)(M_x-M_s)
$$

Where:

| Term | Meaning |
|---|---|
| \(y_x\) | Interpolated yield |
| \(y_s\) | Yield at shorter maturity |
| \(y_l\) | Yield at longer maturity |
| \(M_x\) | Target maturity |
| \(M_s\) | Shorter maturity |
| \(M_l\) | Longer maturity |

### Worked Example

A company has thinly traded 6-year BB debt. Similar liquid BB bonds have these average yields:

| Maturity | Yield |
|---:|---:|
| 4 years | 5.33% |
| 7 years | 5.39% |

Interpolate the 6-year yield:

$$
y_6 = 5.33\% + \left(\frac{5.39\%-5.33\%}{7-4}\right)(6-4)
$$

$$
y_6 = 5.33\% + (0.02\%)(2) = 5.37\%
$$

Estimated pre-tax cost of debt is 5.37%.

## Synthetic Credit Rating

If the company has no rated debt, infer a rating from financial ratios.

Common ratios:

- [[Interest coverage ratio]]
- Debt-to-equity
- Debt-to-EBITDA
- EBITDA margin
- Cash flow stability

Once the synthetic rating is estimated:

$$
r_d = r_f + \text{spread for synthetic rating}
$$

### Judgment matters

If one ratio maps to BBB and another maps to BB, the analyst should not mechanically average the ratings. The right rating depends on trends, industry context, cyclicality, asset quality, and management risk.

## Bank Debt

In some markets, bank loans are the main source of debt capital. Use the rate on a new or current bank loan only if it reflects:

- Current market rates.
- Current company credit risk.
- Comparable maturity.
- Comparable seniority and collateral.

An old bank loan rate may be stale if rates or credit quality have changed.

## Lease-Based Estimates

A finance lease is economically similar to secured borrowing.

### Rate implicit in the lease

The [[rate implicit in the lease]] is the discount rate that equates:

$$
\text{PV of lease payments} + \text{PV of residual value}
= \text{Fair value of leased asset} + \text{Lessor initial direct costs}
$$

It is solved as an IRR.

### Worked Example

A company signs a 15-year lease with:

- Annual payments: \$10 million
- Residual value: \$30 million
- Fair value of leased asset: \$120 million
- Lessor initial direct cost: \$5 million

Set up the calculator:

- \(PV = -125\)
- \(N = 15\)
- \(PMT = 10\)
- \(FV = 30\)

Solve:

$$
I/Y = 4.28\%
$$

So the RIIL is 4.28%.

If the RIIL is unavailable, use the [[incremental borrowing rate]], the rate the company would pay on a similar secured borrowing.

## Country Risk Premium

For foreign borrowers or companies exposed to riskier markets, the cost of debt may need a country risk premium.

Country risk can reflect:

- Political instability.
- Exchange rate risk.
- Weak investor protection.
- Lower capital market development.
- Macroeconomic volatility.

If a benchmark country yield is 4.20% and the relevant country's median interest rate is 6.80%, then:

$$
\text{Country risk premium} = 6.80\% - 4.20\% = 2.60\%
$$

Then:

$$
r_d = r_f + \text{credit spread} + 2.60\%
$$

## After-Tax Cost of Debt in WACC

The WACC uses after-tax cost of debt when interest is tax-deductible:

$$
r_d(1-t)
$$

But do not apply the tax adjustment if the tax shield is not usable. For example, if the company has no taxable income or has reached a legal limit on interest deductibility, the after-tax benefit may be reduced or unavailable.

## Exam Traps

- **Use YTM, not coupon rate.** Coupon is historical; YTM is current required return.
- **Use liquid debt if the longest-maturity bond is stale or thinly traded.**
- **Match rating and maturity in matrix pricing.** Do not interpolate across unrelated credit risk.
- **Do not mechanically average conflicting synthetic-rating signals.** Use judgment.
- **Use pre-tax \(r_d\) for estimating the cost of debt, then after-tax \(r_d(1-t)\) inside WACC.**
- **No tax shield means no after-tax reduction.** If interest is not deductible, use pre-tax debt cost in WACC.
- **Lease borrowing is secured.** RIIL or IBR should reflect collateral and lease term.
- **Country risk may belong in debt cost.** Do not assume all country risk only affects equity.

## Memory Hook

**If it trades, use yield. If it does not, build a yield. If it is foreign, check country risk.**
