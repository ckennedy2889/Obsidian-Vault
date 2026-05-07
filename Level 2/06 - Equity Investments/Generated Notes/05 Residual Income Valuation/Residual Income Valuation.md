---
title: "Residual Income Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity, residual-income, valuation]
aliases:
  - Residual income model
  - Economic profit
  - Clean surplus relation
  - Persistence factor
---

# Residual Income Valuation

[[Residual income]] valuation starts with a simple criticism of accounting income: the income statement subtracts interest expense, but it does **not** subtract the opportunity cost of common equity capital. A company can report positive net income and still destroy value if it earns less than shareholders require.

Residual income fixes that by charging earnings for the cost of equity.

## Core Formula

Per-share residual income in period \(t\):

$$
RI_t = E_t - rB_{t-1}
$$

Where:

| Term | Meaning |
|---|---|
| \(RI_t\) | Residual income per share in period \(t\) |
| \(E_t\) | Earnings per share in period \(t\) |
| \(r\) | Required return on equity |
| \(B_{t-1}\) | Beginning book value per share |

Equivalent form:

$$
RI_t = (ROE_t-r)B_{t-1}
$$

The mechanism is:

1. Earnings belong to common shareholders.
2. But shareholders require a return on beginning book equity.
3. Only earnings above that required return are residual income.

If \(ROE > r\), residual income is positive and the firm creates value. If \(ROE < r\), residual income is negative and the firm destroys value.

## Intrinsic Value Formula

The value of equity equals current book value plus the present value of expected future residual income:

$$
V_0 = B_0 + \sum_{t=1}^{\infty}\frac{RI_t}{(1+r)^t}
$$

Or:

$$
V_0 = B_0 + \sum_{t=1}^{\infty}\frac{E_t-rB_{t-1}}{(1+r)^t}
$$

This is the big intuition: **book value is the starting capital base; residual income is the value added above the required return on that capital.**

## Clean Surplus Relation

Residual income valuation depends on the [[clean surplus relation]]:

$$
B_t = B_{t-1} + E_t - D_t
$$

Ending book value equals beginning book value plus earnings minus dividends.

The clean surplus relation assumes that changes in book value, other than ownership transactions, pass through earnings. If gains and losses bypass the income statement and go directly to equity through OCI, clean surplus may be violated.

Common clean-surplus issues:

- Unrealized gains and losses in other comprehensive income.
- Foreign currency translation adjustments.
- Certain pension adjustments.
- Accounting write-downs or write-ups that distort book value.

## Worked Example

A stock has:

- Current book value: \(B_0 = \$6.00\)
- Required return: \(r = 10\%\)
- The company will liquidate after Year 3.

Forecasts:

| Year | EPS | Dividend |
|---:|---:|---:|
| 1 | \$2.00 | \$1.00 |
| 2 | \$2.50 | \$1.25 |
| 3 | \$4.00 | \$12.25 |

Step 1: Calculate book values using clean surplus.

$$
B_1 = 6.00 + 2.00 - 1.00 = \$7.00
$$

$$
B_2 = 7.00 + 2.50 - 1.25 = \$8.25
$$

Step 2: Calculate residual income using beginning book value.

$$
RI_1 = 2.00 - 0.10(6.00) = \$1.40
$$

$$
RI_2 = 2.50 - 0.10(7.00) = \$1.80
$$

$$
RI_3 = 4.00 - 0.10(8.25) = \$3.175
$$

Step 3: Discount residual income and add current book value.

$$
V_0 = 6.00 + \frac{1.40}{1.10} + \frac{1.80}{1.10^2} + \frac{3.175}{1.10^3}
$$

$$
V_0 = 6.00 + 1.2727 + 1.4876 + 2.3854 = \$11.15
$$

## Single-Stage Residual Income Model

If ROE and growth are expected to remain constant:

$$
V_0 = B_0 + \frac{(ROE-r)B_0}{r-g}
$$

This can also be written:

$$
\frac{V_0}{B_0} = 1 + \frac{ROE-r}{r-g}
$$

### Relation to Justified P/B

The justified price-to-book ratio is:

$$
\frac{P_0}{B_0} = 1 + \frac{ROE-r}{r-g}
$$

Interpretation:

| Condition | Residual income | Justified P/B |
|---|---:|---:|
| \(ROE > r\) | Positive | Greater than 1 |
| \(ROE = r\) | Zero | Equal to 1 |
| \(ROE < r\) | Negative | Less than 1 |

The exam likes this because it connects residual income to market-based valuation. A high P/B is justified only if the firm is expected to earn ROE above its required return.

## Persistence Factor

Competitive forces usually push abnormal profitability toward normal levels. The persistence factor, \(\omega\), models how quickly residual income fades after the explicit forecast period.

| Persistence factor | Meaning |
|---:|---|
| \(\omega = 1\) | Residual income persists indefinitely |
| \(\omega = 0\) | Residual income disappears immediately |
| \(0 < \omega < 1\) | Residual income fades gradually |

Higher persistence is more plausible when:

- The firm has durable competitive advantages.
- The industry has high entry barriers.
- Historical residual income is stable.
- Dividend payout is low and reinvestment opportunities are strong.

Lower persistence is more plausible when:

- ROE is unusually high or unusually low.
- Accruals are high.
- Earnings include nonrecurring items.
- Competition can quickly imitate the business model.

## Strengths

Residual income valuation is useful when:

- The company does not pay dividends.
- Free cash flow is negative or volatile.
- Terminal value would dominate a DDM or FCF model.
- Book value is meaningful.
- The analyst wants to focus explicitly on economic profitability.

Because the model starts with book value, less of the estimated value may sit in a distant terminal value compared with some DCF models.

## Weaknesses

Residual income valuation can be unreliable when:

- Accounting quality is poor.
- Book value is not economically meaningful.
- Clean surplus is violated.
- ROE is temporarily distorted.
- Required accounting adjustments are large.

The model is only as good as the accounting numbers feeding it.

## RI vs EVA

Do not confuse residual income with [[Economic Value Added]].

| Measure | Perspective | Formula intuition |
|---|---|---|
| Residual income | Common shareholders | Net income minus equity charge |
| EVA | All capital providers | NOPAT minus WACC charge on total capital |

Residual income deducts:

$$
r \times \text{Beginning book value of equity}
$$

EVA deducts:

$$
WACC \times \text{Total capital}
$$

## Exam Traps

- **Use beginning book value.** The equity charge is \(rB_{t-1}\), not \(rB_t\).
- **Clean surplus matters.** OCI items can break the relation between earnings and book value.
- **Positive net income is not enough.** Value is created only if earnings exceed the equity charge.
- **If \(ROE = r\), value equals book value.**
- **High P/B requires expected ROE above the cost of equity.**
- **Persistence is about abnormal earnings fade.** A lower \(\omega\) means residual income fades faster.
- **RI is not EVA.** RI charges equity capital against net income; EVA charges total capital against NOPAT.

## Memory Hook

**Book value is the capital already in the business. Residual income is what the business earns above the rent shareholders charge for that capital.**
