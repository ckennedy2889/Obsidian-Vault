---
title: "Estimating the Required Return on Equity"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, cost-of-capital, equity, valuation]
aliases:
  - Required return on equity
  - Cost of equity
  - Bond yield plus risk premium
  - Build-up approach
  - Expanded CAPM
---

# Estimating the Required Return on Equity

The [[required return on equity]] is harder to observe than the [[cost of debt]] because common equity has no promised yield. Equity investors are residual claimants, so analysts estimate the return they require using models.

The exam usually tests two things:

1. Can you choose the right model for the facts?
2. Can you avoid mixing inputs from different models?

## Method Map

| Method | Formula | Best use |
|---|---|---|
| [[Dividend Discount Model]] | \(r_e = \frac{D_1}{P_0}+g\) | Dividend-paying public companies with stable growth |
| Bond-yield-plus-risk-premium | \(r_e = r_d + RP\) | Public companies with traded long-term debt |
| [[Capital Asset Pricing Model]] | \(r_e = r_f + \beta(ERP)\) | Public companies with observable beta |
| Multifactor models | \(r_e = r_f + \sum \beta_i RP_i\) | Public companies with multiple systematic risk drivers |
| Expanded CAPM | \(r_e = r_f + \beta(ERP)+SP+IP+SCRP\) | Private companies with public comparable betas |
| Build-up approach | \(r_e = r_f + ERP+SP+IP+SCRP\) | Private companies when beta is not reliable |

## Dividend Discount Model

For a stable dividend-paying company:

$$
r_e = \frac{D_1}{P_0}+g
$$

Where:

| Term | Meaning |
|---|---|
| \(D_1\) | Expected dividend next period |
| \(P_0\) | Current stock price |
| \(g\) | Expected constant dividend growth rate |

### Worked Example

A company trades at €40. It is expected to pay a €1.04 dividend next year. Dividends are expected to grow at 4%.

$$
r_e = \frac{1.04}{40}+0.04 = 0.026+0.04 = 6.6\%
$$

### When DDM is weak

DDM is less reliable when:

- The company does not pay dividends.
- Dividends are unstable.
- Growth is not expected to be constant.
- The market price embeds a changing valuation multiple.

Exam trap: use \(D_1\), not \(D_0\). If the question gives the most recent dividend, grow it first.

## Bond-Yield-Plus-Risk-Premium Method

The bond-yield-plus-risk-premium method starts with the yield on the company's long-term debt and adds an equity risk premium over the firm's own debt.

$$
r_e = r_d + RP
$$

Where:

| Term | Meaning |
|---|---|
| \(r_d\) | YTM on the company's long-term debt |
| \(RP\) | Extra premium required for equity over company debt |

### Worked Example

The company's long-term bond YTM is 8.0%. The analyst estimates that equity requires a 3.8% premium over debt.

$$
r_e = 8.0\% + 3.8\% = 11.8\%
$$

### Strength and weakness

This method is useful when the company has liquid traded debt. Its weakness is that the equity-over-debt premium is judgmental.

Exam trap: use long-term debt YTM, not coupon rate and not short-term debt unless it is the only reliable market signal.

## CAPM

CAPM estimates required return from exposure to market risk:

$$
r_e = r_f + \beta(ERP)
$$

Where:

| Term | Meaning |
|---|---|
| \(r_f\) | Risk-free rate |
| \(\beta\) | Equity beta |
| \(ERP\) | Equity risk premium |

### Worked Example

Risk-free rate is 4.0%, ERP is 3.9%, and beta is 0.8.

$$
r_e = 4.0\% + 0.8(3.9\%) = 4.0\% + 3.12\% = 7.12\%
$$

### Beta estimation

For a public company, beta is often estimated by regressing stock returns against market index returns.

For a private company, analysts often:

1. Find comparable public companies.
2. Unlever their betas.
3. Average or select an asset beta.
4. Relever beta to the private company's target capital structure.

## Multifactor Models

Multifactor models extend CAPM by adding other systematic risk factors.

General form:

$$
r_e = r_f + \sum_{i=1}^{n}\beta_i RP_i
$$

The Fama-French five-factor version is:

$$
r_e = r_f + \beta_1ERP + \beta_2SMB + \beta_3HML + \beta_4RMW + \beta_5CMA
$$

Where:

| Factor | Meaning |
|---|---|
| \(ERP\) | Market equity risk premium |
| \(SMB\) | Size premium: small minus big |
| \(HML\) | Value premium: high book-to-market minus low book-to-market |
| \(RMW\) | Profitability premium: robust minus weak |
| \(CMA\) | Investment premium: conservative minus aggressive |

### Worked Example

Assume:

- \(r_f = 2.1\%\)
- \(\beta_1ERP = 1.1(3.2\%)\)
- \(\beta_2SMB = 0.2(1.3\%)\)
- \(\beta_3HML = -0.3(2.0\%)\)
- \(\beta_4RMW = 0.18(4.2\%)\)
- \(\beta_5CMA = 0.5(2.4\%)\)

Then:

$$
r_e =
2.1\% + 3.52\% + 0.26\% - 0.60\% + 0.756\% + 1.20\%
= 7.236\% \approx 7.2\%
$$

Exam trap: the beta in a multifactor model is a partial regression coefficient. Do not assume it equals the standalone CAPM beta.

## Private Company Cost of Equity

Private companies create estimation problems because:

- No traded share price exists.
- Return history is unavailable or unreliable.
- Shares are illiquid.
- Disclosure may be limited.
- Company-specific risks can be large.

### Expanded CAPM

Use expanded CAPM when a comparable public-company beta is available:

$$
r_e = r_f + \beta(ERP) + SP + IP + SCRP
$$

Where:

| Term | Meaning |
|---|---|
| \(SP\) | Size premium |
| \(IP\) | Industry risk premium |
| \(SCRP\) | Specific company risk premium |

Specific company risk can reflect key-person risk, customer concentration, supplier concentration, geographic concentration, weak governance, poor competitive position, or asset illiquidity.

### Build-Up Approach

Use the build-up approach when beta is not reliable:

$$
r_e = r_f + ERP + SP + IP + SCRP
$$

This effectively assumes average market beta of 1.0 and then adds premiums.

### Worked Example

A private company has:

- Risk-free rate: 5.41%
- ERP: 6.00%
- Size premium: 5.00%
- Specific company risk premium: 6.00%
- Country risk premium: 2.00%

Using a build-up approach:

$$
r_e = 5.41\% + 6.00\% + 5.00\% + 6.00\% + 2.00\%
= 24.41\%
$$

## Illiquidity and DLOM

Private-company shares are illiquid, but the curriculum often treats illiquidity through a [[discount for lack of marketability]] applied to the final equity value rather than by adding an illiquidity premium directly to \(r_e\).

Exam trap: if the vignette asks for a required return, add the listed risk premiums in the cost-of-equity model. If it asks for the final value of private equity, apply DLOM at the end when instructed.

## Choosing the Model

| Vignette clue | Likely method |
|---|---|
| Stable dividend payer, constant growth | DDM |
| Public company with liquid long-term debt and given equity-over-debt premium | Bond-yield-plus-risk-premium |
| Public company with beta and ERP | CAPM |
| Size/value/profitability/investment factor exposures | Fama-French or multifactor |
| Private company with public comparables | Expanded CAPM |
| Private company with no reliable beta | Build-up approach |

## Exam Traps

- **DDM uses \(D_1\), not \(D_0\).**
- **DDM estimates required return, not ERP.** Do not subtract the risk-free rate unless the question asks for ERP.
- **BYPRP uses debt YTM plus a premium.** Do not use coupon rate.
- **CAPM requires a risk-free rate and ERP with compatible horizons.**
- **Do not use CAPM beta inside Fama-French without support.** Multifactor betas are separate estimates.
- **Private-company premiums are additive in expanded CAPM or build-up.**
- **Apply DLOM to value, not automatically to \(r_e\), unless the vignette specifically instructs otherwise.**

## Memory Hook

**Public equity: dividends, debt yield, or beta. Private equity: borrow a beta or build the return.**
