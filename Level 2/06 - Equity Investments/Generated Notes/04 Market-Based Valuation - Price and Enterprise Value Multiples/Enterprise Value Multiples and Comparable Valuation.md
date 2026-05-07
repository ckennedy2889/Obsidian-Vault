---
title: "Enterprise Value Multiples and Comparable Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity, market-based-valuation, multiples, enterprise-value]
aliases:
  - Enterprise value multiples
  - EV EBITDA
  - Method of comparables
  - Harmonic mean
  - Numerator denominator consistency
---

# Enterprise Value Multiples and Comparable Valuation

Market-based valuation uses the price of similar assets to infer value. The intuition is the [[law of one price]]: similar businesses with similar risk, growth, and profitability should trade at similar valuation multiples.

The exam's main challenge is consistency. The numerator and denominator must belong to the same capital providers.

## Two Ways to Use Multiples

| Method | Logic | Output |
|---|---|---|
| Method of comparables | Compare a company's multiple with peer, industry, or index multiples | Relative valuation signal |
| Forecasted fundamentals | Derive a justified multiple from a DCF model | Fundamental fair-value multiple |

If a company trades below peers, it may be undervalued, but only if its growth, risk, profitability, accounting, and capital structure are truly comparable.

## Trailing vs Leading Multiples

| Multiple type | Denominator | Strength | Weakness |
|---|---|---|---|
| Trailing | Historical results, often TTM | Based on actual reported data | Backward-looking; can create look-ahead bias |
| Leading | Forecasted next-year or forward results | Forward-looking | Depends on forecast quality |

Valuation is forward-looking, so leading multiples are often preferred when forecasts are reliable.

## Numerator-Denominator Consistency

This is the most important rule in the reading.

| Numerator | Claim represented | Valid denominator examples |
|---|---|---|
| Price or market value of equity | Common equity holders | EPS, net income, book value of equity, FCFE |
| Enterprise value | Debt, preferred, and common equity holders | Sales, EBITDA, EBIT, FCFF |

Invalid pairings:

- Price / EBITDA
- Price / EBIT
- EV / net income
- EV / EPS
- EV / FCFE

Why? EBITDA and EBIT are available before payments to debt holders, so they belong with enterprise value. Net income and EPS are after interest, so they belong with equity value.

## Enterprise Value

[[Enterprise value]] is the market value of the operating business available to all capital providers:

$$
EV = \text{Market value of common equity}
+ \text{Market value of preferred equity}
+ \text{Market value of debt}
- \text{Cash and short-term investments}
$$

Cash is subtracted because an acquirer who buys the whole firm receives the cash, which offsets the gross acquisition cost.

Exam trap: use market value of debt and preferred equity when available. Book value may be used as a proxy only when market value is unavailable or close to book.

## Common Price Multiples

| Multiple | Useful when | Main weakness |
|---|---|---|
| P/E | Earnings are positive and meaningful | EPS can be negative, cyclical, or manipulated |
| P/B | Book value is meaningful, especially banks and financials | Weak for firms dominated by intangible assets |
| P/S | Earnings are negative or margins are temporarily depressed | Ignores cost structure and profitability |
| P/CF | Cash flow is more stable than earnings | Cash-flow definitions vary |

### Justified P/E

From the Gordon growth model:

Leading P/E:

$$
\frac{P_0}{E_1} = \frac{\text{Payout ratio}}{r-g}
$$

Trailing P/E:

$$
\frac{P_0}{E_0} = \frac{\text{Payout ratio}(1+g)}{r-g}
$$

### Justified P/B

$$
\frac{P_0}{B_0} = \frac{ROE-g}{r-g}
$$

Justified P/B rises with ROE and growth, and falls as required return rises.

### Justified P/S

$$
\frac{P_0}{S_0}
= \text{Net profit margin}
\times
\frac{\text{Payout ratio}(1+g)}{r-g}
$$

This shows why P/S cannot be interpreted without margins. A low-margin retailer should not trade at the same P/S as a high-margin software firm.

## Enterprise Value Multiples

### EV/EBITDA

EV/EBITDA is one of the most common firm-value multiples:

$$
\frac{EV}{EBITDA}
$$

Strengths:

- Less affected by capital structure than P/E.
- Useful for comparing companies with different debt levels.
- Less affected by depreciation and amortization choices.
- EBITDA is usually positive more often than net income.

Weaknesses:

- EBITDA ignores capital expenditures.
- EBITDA ignores working capital investment.
- EBITDA can overstate cash flow for growing or capital-intensive firms.
- It can make highly leveraged firms look deceptively comparable.

### EV/Sales

EV/Sales is useful when EBITDA is negative or temporarily distorted.

It is often better than P/S when leverage differs across companies because EV includes debt and equity.

Weakness:

- Sales say nothing about margins. A high EV/Sales multiple is justified only if the firm can convert revenue into profitable cash flow.

## Method of Comparables

The standard workflow:

1. Choose comparable companies.
2. Select relevant multiples.
3. Adjust accounting differences where possible.
4. Compute peer multiples.
5. Use median or harmonic mean rather than relying on outlier-sensitive arithmetic mean.
6. Apply the selected multiple to the subject company's metric.
7. Interpret differences using fundamentals.

Comparable companies should have similar:

- Industry.
- Growth.
- Profitability.
- Risk.
- Capital intensity.
- Accounting policies.
- Capital structure, especially when using equity multiples.

## Harmonic Mean

The harmonic mean is often preferred for averaging multiples:

$$
\text{Harmonic mean} = \frac{n}{\sum_{i=1}^{n}\frac{1}{X_i}}
$$

It reduces the upward distortion from very high multiples.

### Worked Example

Three companies have P/E ratios of 10, 20, and 100.

Arithmetic mean:

$$
\frac{10+20+100}{3}=43.33
$$

Harmonic mean:

$$
\frac{3}{\frac{1}{10}+\frac{1}{20}+\frac{1}{100}}
= \frac{3}{0.10+0.05+0.01}
= \frac{3}{0.16}
= 18.75
$$

The harmonic mean is less distorted by the 100x outlier.

## Negative Denominators

A negative P/E is not economically meaningful. If earnings are negative, use:

- Earnings yield \(E/P\)
- P/S
- EV/Sales
- Normalized earnings
- Forward earnings if credible

Do not average negative P/E ratios into a peer group.

## Look-Ahead Bias

Look-ahead bias occurs when a backtest uses information that was not available at the decision date.

Example: using full-year EPS on January 1 to compute a trailing P/E, even though the annual report was not released until February or March.

The exam may test whether a historical valuation strategy accidentally uses future information.

## Exam Traps

- **Match numerator and denominator.** Equity value with equity flows; enterprise value with firm flows.
- **Subtract cash in EV.** Cash offsets acquisition cost.
- **Do not use negative P/E.** Use E/P or another multiple.
- **P/S ignores margins.** A lower P/S is not automatically cheaper.
- **EV/EBITDA ignores capex and working capital.** It is not true free cash flow.
- **Forward multiples are preferred when forecasts are reliable.** Trailing multiples are not automatically better because they use actual data.
- **Use harmonic mean for average multiples when appropriate.** Arithmetic means can be inflated by outliers.
- **Comparable does not mean identical.** Always explain differences in growth, risk, ROE, and margins.

## Memory Hook

**Price belongs with after-interest equity metrics. EV belongs with before-interest firm metrics.**
