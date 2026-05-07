---
title: Beneish M-Score
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - reporting-quality
  - earnings-manipulation
  - forensic-accounting
aliases:
  - Beneish M-score
  - M-score
  - Beneish model
---

# Beneish M-Score

The Beneish M-score is a forensic accounting model that flags companies with a higher probability of earnings manipulation. It does not prove fraud. It says the pattern of financial statement variables looks statistically similar to past manipulators.

For CFA Level II, the goal is usually interpretation, not memorizing every coefficient.

## The Model

The eight-variable version is:

$$
M = -4.84 + 0.920(DSRI) + 0.528(GMI) + 0.404(AQI) + 0.892(SGI)
$$

$$
+ 0.115(DEPI) - 0.172(SGAI) + 4.679(Accruals) - 0.327(LEVI)
$$

A common cutoff is:

$$
M > -1.78
$$

If the M-score is greater than -1.78, the company is flagged as a potential manipulator. Greater means less negative, so -1.20 is more concerning than -2.30.

## Variables

| Variable | Meaning | Value above 1 often suggests |
|---|---|---|
| DSRI | Days sales receivable index | Receivables growing faster than sales; possible revenue recognition issue |
| GMI | Gross margin index | Gross margin deterioration; pressure to manipulate |
| AQI | Asset quality index | More "soft" assets; possible capitalization of expenses |
| SGI | Sales growth index | High growth pressure to maintain trend |
| DEPI | Depreciation index | Lower depreciation rate; possible longer useful lives or higher salvage values |
| SGAI | SG&A index | Worsening SG&A efficiency |
| Accruals | Accrual intensity | Earnings less cash-backed |
| LEVI | Leverage index | More debt pressure |

## Selected Formulas

Days sales receivable index:

$$
DSRI =
\frac{AR_t / Sales_t}{AR_{t-1} / Sales_{t-1}}
$$

Gross margin index:

$$
GMI =
\frac{Gross\ margin_{t-1}}{Gross\ margin_t}
$$

Sales growth index:

$$
SGI =
\frac{Sales_t}{Sales_{t-1}}
$$

Accruals:

$$
Accruals =
\frac{NI - CFO}{Total\ assets}
$$

## Interpretation

Suppose a company has:

$$
M = -1.23
$$

Because -1.23 is greater than -1.78, the model flags the company as a potential manipulator.

The analyst should then inspect the drivers. If DSRI, GMI, SGI, and DEPI are all elevated, the story might be:

- Receivables are growing faster than sales.
- Margins are deteriorating.
- Growth expectations are high.
- Depreciation assumptions may be more aggressive.

That combination does not prove fraud, but it gives a focused investigation path.

## Limitations

| Limitation | Implication |
|---|---|
| Statistical association, not proof | A flagged company needs further analysis |
| Model can be gamed | Managers aware of the model may manage inputs |
| Predictive power can decline | Historical relationships may weaken |
| Accounting data are incomplete | Qualitative evidence still matters |
| Industry differences matter | Compare with business model context |

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "A flagged M-score proves manipulation." | False. It indicates elevated probability. |
| "-2.5 is more concerning than -1.2." | False. Higher, less negative scores are more concerning. |
| "Memorize all coefficients." | Interpretation is usually more important. |
| "One variable explains the whole score." | False. The model combines multiple signals. |

## Memory Hook

Beneish is a smoke alarm, not a conviction.

It tells you where to investigate.

## Related Concepts

- [[Financial Reporting Quality vs Earnings Quality]]
- [[Earnings manipulation]]
- [[Accruals Ratio]]
- [[Revenue recognition]]
- [[Forensic accounting]]

