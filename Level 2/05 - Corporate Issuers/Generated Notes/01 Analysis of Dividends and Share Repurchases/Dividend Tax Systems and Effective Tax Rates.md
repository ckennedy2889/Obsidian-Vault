---
title: "Dividend Tax Systems and Effective Tax Rates"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, dividends, taxes, payout-policy]
aliases:
  - Double taxation system
  - Dividend imputation tax system
  - Split-rate tax system
  - Effective tax rate on dividends
---

# Dividend Tax Systems and Effective Tax Rates

Dividend tax systems matter because they change the after-tax cash shareholders receive. For CFA Level II, the exam usually gives one currency unit, or 100 currency units, of pre-tax corporate earnings and asks how much tax is paid under different dividend tax systems.

The clean way to solve every version is:

1. Start with pre-tax corporate earnings.
2. Apply the corporate tax that applies to distributed earnings.
3. Treat the after-corporate-tax amount as the dividend.
4. Apply shareholder-level dividend tax, unless the system gives a credit.
5. Compare total tax to original pre-tax earnings.

## Three Systems

| System | Core idea | Effective tax intuition |
|---|---|---|
| [[Double taxation system]] | Earnings taxed at corporate level, then dividends taxed again at shareholder level | Corporate tax plus personal tax on after-tax earnings |
| [[Dividend imputation tax system]] | Shareholder gets credit for corporate tax already paid | Effective tax equals shareholder marginal tax rate |
| [[Split-rate tax system]] | Distributed earnings receive a lower corporate tax rate than retained earnings | Use the distributed-earnings corporate rate, then shareholder dividend tax |

## Double Taxation System

Under double taxation, dividends are taxed twice:

1. Corporate income tax is paid on pre-tax earnings.
2. Personal dividend tax is paid on the after-tax dividend.

Formula:

$$
\text{Effective tax rate}
= 1 - \frac{EBT(1-T_c)(1-T_d)}{EBT}
$$

This simplifies to:

$$
\text{Effective tax rate} = T_c + (1-T_c)T_d
$$

Where:

| Term | Meaning |
|---|---|
| \(T_c\) | Corporate tax rate |
| \(T_d\) | Personal tax rate on dividends |

### Worked Example

A company earns \$100 before tax. The corporate tax rate is 35%. The shareholder tax rate on dividends is 15%. The firm distributes all after-tax earnings.

Corporate tax:

$$
100 \times 0.35 = \$35
$$

After-tax dividend:

$$
100 - 35 = \$65
$$

Shareholder tax:

$$
65 \times 0.15 = \$9.75
$$

Total tax:

$$
35 + 9.75 = \$44.75
$$

Effective tax rate:

$$
\frac{44.75}{100} = 44.75\%
$$

Do not add 35% and 15% to get 50%. The shareholder tax applies only to the after-corporate-tax dividend.

## Dividend Imputation Tax System

Under a dividend imputation system, corporate tax paid becomes a credit to the shareholder. The goal is to tax distributed corporate earnings once, at the shareholder's marginal tax rate.

Core rule:

$$
\text{Effective tax rate} = T_d
$$

Where \(T_d\) is the shareholder's marginal tax rate.

### Worked Example

A company earns A\$100 before tax. The corporate tax rate is 30%. The firm distributes all after-tax earnings.

Corporate tax:

$$
100 \times 0.30 = A\$30
$$

Cash dividend:

$$
100 - 30 = A\$70
$$

Now compare two shareholders.

| Shareholder | Marginal tax rate | Tax on grossed-up income | Imputation credit | Additional tax/refund | Effective tax rate |
|---|---:|---:|---:|---:|---:|
| A | 15% | A\$15 | A\$30 | A\$15 refund | 15% |
| B | 47% | A\$47 | A\$30 | A\$17 tax due | 47% |

The cash mechanics differ by shareholder, but the effective tax rate equals each shareholder's marginal tax rate.

## Split-Rate Tax System

Under a split-rate system, distributed earnings and retained earnings face different corporate tax rates. Distributed earnings usually receive a lower corporate tax rate. Dividends are then taxed again at the shareholder level.

Formula:

$$
\text{Effective tax rate}
= 1 - \frac{EBT(1-T_{cd})(1-T_d)}{EBT}
$$

This simplifies to:

$$
\text{Effective tax rate} = T_{cd} + (1-T_{cd})T_d
$$

Where:

| Term | Meaning |
|---|---|
| \(T_{cd}\) | Corporate tax rate on distributed earnings |
| \(T_d\) | Personal tax rate on dividends |

The retained-earnings tax rate is not used for the dividend portion.

### Worked Example

A company allocates €100 of pre-tax earnings to be distributed as dividends. The corporate tax rate on retained earnings is 35%, the corporate tax rate on distributed earnings is 20%, and the shareholder dividend tax rate is 35%.

Use the 20% distributed-earnings corporate rate:

$$
100 \times 0.20 = €20
$$

Dividend after corporate tax:

$$
100 - 20 = €80
$$

Shareholder tax:

$$
80 \times 0.35 = €28
$$

Total tax:

$$
20 + 28 = €48
$$

Effective tax rate:

$$
\frac{48}{100} = 48\%
$$

## Comparison

Assume \(EBT = 100\), \(T_c = 35\%\), \(T_{cd} = 20\%\), and \(T_d = 15\%\).

| System | Effective tax rate |
|---|---:|
| Double taxation | \(35\% + 65\%(15\%) = 44.75\%\) |
| Dividend imputation | \(15\%\) |
| Split-rate | \(20\% + 80\%(15\%) = 32.00\%\) |

## Why This Affects Payout Policy

Tax systems influence whether investors prefer dividends, repurchases, or retention.

If dividends are heavily taxed, shareholders may prefer [[share repurchases]] or capital gains. If imputation credits remove the double-tax penalty, dividends become more attractive. If distributed earnings receive a lower corporate tax rate, firms may have a stronger incentive to pay dividends than under a pure double-taxation system.

## Exam Traps

- **Do not add tax rates under double taxation.** Apply personal tax to after-corporate-tax dividends.
- **Imputation effective tax rate equals shareholder marginal tax rate.** The corporate tax becomes a credit.
- **Use the distributed-earnings corporate tax rate in split-rate systems.** Ignore the retained-earnings rate for the distributed portion.
- **Start from pre-tax corporate earnings.** The denominator for effective tax rate is the original pre-tax amount.
- **Separate cash received from effective tax rate.** Imputation can produce refunds or additional tax, but the effective rate still equals the shareholder's tax rate.

## Memory Hook

**Double tax: company then shareholder. Imputation: shareholder rate wins. Split-rate: lower distributed corporate rate, then shareholder.**
