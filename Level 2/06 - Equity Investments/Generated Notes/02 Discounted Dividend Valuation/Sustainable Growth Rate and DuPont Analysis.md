---
title: "Sustainable Growth Rate and DuPont Analysis"
subject: "Equity Investments"
tags: [CFA-L2, equity, DDM, sustainable-growth, DuPont]
aliases:
  - Sustainable growth rate
  - PRAT model
  - Retention ratio
  - Plowback ratio
---

# Sustainable Growth Rate and DuPont Analysis

The [[sustainable growth rate]] is the growth rate a company can maintain without issuing new common equity, assuming its profitability, payout policy, and capital structure remain stable.

In DDM problems, this is often the growth rate used in the Gordon growth model when the company is mature and growing at a steady long-run rate.

## Core Formula

$$
g = b \times ROE
$$

Where:

| Term | Meaning |
|---|---|
| \(g\) | Sustainable growth rate |
| \(b\) | Retention ratio, or plowback ratio |
| \(ROE\) | Return on equity |

The retention ratio is:

$$
b = 1 - \text{Dividend payout ratio}
$$

If a company earns ROE on retained earnings and retains \(b\) of earnings, then book value, earnings, and dividends can grow at \(b \times ROE\), assuming no new equity issuance and stable ROE.

## Why the Formula Works

Suppose beginning book equity is \(B_0\). The company earns:

$$
E_1 = ROE \times B_0
$$

It retains:

$$
b \times E_1
$$

That retained amount increases equity. Growth in equity is:

$$
\frac{bE_1}{B_0}
= \frac{b(ROE \times B_0)}{B_0}
= b \times ROE
$$

If ROE and payout are stable, earnings and dividends grow with book equity.

## DuPont Decomposition

ROE can be decomposed as:

$$
ROE =
\frac{NI}{Sales}
\times
\frac{Sales}{Assets}
\times
\frac{Assets}{Equity}
$$

Or:

$$
ROE = \text{Profit margin} \times \text{Asset turnover} \times \text{Financial leverage}
$$

Substitute into \(g=b \times ROE\):

$$
g =
\text{Profit margin}
\times
\text{Retention rate}
\times
\text{Asset turnover}
\times
\text{Financial leverage}
$$

This is often called the PRAT model:

| Letter | Driver |
|---|---|
| P | Profit margin |
| R | Retention rate |
| A | Asset turnover |
| T | Financial leverage |

## Worked Example

A company has:

- ROA = 10%
- Equity multiplier = 1.25
- Retention ratio = 30%

First calculate ROE:

$$
ROE = ROA \times \text{Equity multiplier}
$$

$$
ROE = 10\% \times 1.25 = 12.5\%
$$

Then calculate sustainable growth:

$$
g = b \times ROE = 0.30 \times 12.5\% = 3.75\%
$$

The company can sustainably grow at 3.75% without issuing new common equity, assuming stable profitability, payout, and leverage.

## Link to DDM

The Gordon growth model is:

$$
V_0 = \frac{D_1}{r-g}
$$

Sustainable growth can provide \(g\), but only if the company is in a mature, stable phase.

Do not use an unsustainably high historical growth rate as perpetual \(g\). Perpetual growth must be economically plausible.

## Link to Justified P/E

The justified leading P/E is:

$$
\frac{P_0}{E_1} = \frac{1-b}{r-g}
$$

Since:

$$
g = b \times ROE
$$

Increasing retention has two opposing effects:

| Effect | Direction |
|---|---|
| Higher \(b\) raises \(g\) | Increases justified P/E by lowering \(r-g\) |
| Higher \(b\) lowers payout \(1-b\) | Decreases justified P/E by lowering numerator |

This is the [[dividend displacement of earnings]] idea. Retaining more earnings creates value only when the firm reinvests at returns above the required return.

## Value Creation Rule

| Condition | Effect of retaining more earnings |
|---|---|
| \(ROE > r\) | Retention creates value |
| \(ROE = r\) | Retention is value-neutral |
| \(ROE < r\) | Retention destroys value |

The reason: retained earnings are not free. Shareholders require return \(r\). If the company reinvests at ROE below \(r\), shareholders would have been better off receiving dividends and investing elsewhere.

## Assumptions

The sustainable growth formula assumes:

- No new common equity issuance.
- Constant ROE.
- Constant dividend payout ratio.
- Constant capital structure.
- Debt grows with equity to maintain leverage.
- Growth is internally financed through retained earnings.

If the firm is changing leverage aggressively or issuing new shares, \(g=b \times ROE\) no longer captures sustainable growth cleanly.

## Exam Traps

- **Use retention ratio, not payout ratio.** \(b = 1 - \text{payout ratio}\).
- **Do not use unsustainable ROE forever.** High ROE tends to attract competition.
- **Stable leverage is assumed.** Changing capital structure breaks the simple formula.
- **Use \(D_1\) in Gordon growth.** If given \(D_0\), calculate \(D_1 = D_0(1+g)\).
- **Higher retention is not automatically better.** It helps only if ROE exceeds the required return.
- **DuPont tells you why growth changes.** Growth can rise because of margins, turnover, leverage, or retention.

## Memory Hook

**Sustainable growth is retained earnings earning ROE.**

No retention, no internally financed growth. Low ROE, low-value growth.
