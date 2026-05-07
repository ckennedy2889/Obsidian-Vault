---
title: Institutional Risk Measures
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, institutional-investors, risk-measures]
aliases: [Risk Measures by Institution, Bank Risk Measures, Asset Manager Risk Measures, Hedge Fund Risk Measures, Pension Fund Risk Measures, Insurer Risk Measures]
---

# Institutional Risk Measures

## Intuition

Different institutions worry about different ways of failing.

A bank can fail because leverage and balance-sheet risk overwhelm its capital. A traditional asset manager can fail the mandate by drifting too far from the benchmark. A pension fund can fail because assets do not cover liabilities. An insurer can fail because investment losses and insurance claims hit at the same time.

So CFA does not expect one universal risk dashboard. It expects you to match the risk measure to the institution's business model.

See: [[Measuring and Managing Market Risk]] · [[Risk Limits and Capital Allocation]] · [[Parametric Historical and Monte Carlo VaR]]

## Big Rule

Risk measures depend on:

- the institution's assets,
- the institution's liabilities,
- leverage,
- regulation,
- whether performance is absolute or benchmark-relative,
- and whether the main risk is market risk alone or market risk plus liability risk.

## Summary Table

| Institution | Primary risk measures | Why these fit |
|---|---|---|
| **Banks** | [[Value at Risk (VaR)]], economic capital, sensitivity measures, leverage measures, stress testing, asset-liability mismatch measures | Banks are leveraged and regulated; trading losses can impair capital |
| **Traditional asset managers** | Position size, [[Tracking Error]], ex ante tracking error, active share, beta, duration, scenario analysis | Long-only managers are usually benchmark-relative and less levered |
| **Hedge funds** | VaR, leverage, gross exposure, long/short exposure, sensitivities, scenario analysis, stress tests, maximum drawdown | Hedge funds often use leverage, derivatives, shorts, and absolute-return targets |
| **Defined benefit pension funds** | Surplus at risk, asset-liability matching, duration/convexity of assets versus liabilities, glide path analysis | Pension risk is asset value relative to liability value |
| **P&C insurers** | Investment sensitivities, VaR, capital at risk, scenario analysis combining market and insurance risks | Claims are often catastrophe-driven and not highly correlated with markets |
| **Life insurers** | ALM, sensitivity of assets and annuity liabilities, scenario analysis with market and mortality risks | Long-dated liabilities are highly sensitive to discount rates and longevity |

## Banks

Banks care about whether losses can impair economic capital.

Typical measures:

- VaR for trading books.
- Sensitivities such as duration, DV01/PVBP, credit spread exposure, and FX exposure.
- Scenario analysis and stress testing for the full balance sheet.
- Leverage measures.
- Economic capital.
- Asset-liability mismatch measures.
- Risk broken down by geography and business unit.

### Why

Banks are leveraged institutions. A small percentage loss on assets can be large relative to equity capital. They also face regulatory scrutiny, so they need measures that connect market losses to capital adequacy.

Economic capital is central:

$$
\text{Economic capital} = \text{capital needed to survive severe business losses}
$$

## Traditional Asset Managers

Traditional long-only asset managers usually care about **relative risk** because clients hire them to manage against a benchmark.

Typical measures:

- Position size.
- Active share.
- Ex ante tracking error.
- Ex post tracking error.
- Beta and market sensitivity.
- Duration and interest-rate sensitivity for fixed-income portfolios.
- Historical and hypothetical scenario analysis.
- Options risk if derivatives are used.

### Active share

Active share measures how different the portfolio is from the benchmark:

$$
\text{Active Share}
= \frac{1}{2}\sum_i |w_{P,i} - w_{B,i}|
$$

Intuition: if a manager owns almost the same securities in almost the same weights as the benchmark, active share is low.

### Ex ante vs ex post tracking error

| Measure | Direction | Main use |
|---|---|---|
| **Ex ante tracking error** | Forward-looking | Risk estimation for the current portfolio |
| **Ex post tracking error** | Backward-looking | Performance attribution and manager skill assessment |

Traditional asset managers mostly use **ex ante tracking error** for risk control because it asks how the current portfolio may underperform the benchmark in the future.

## Hedge Funds

Hedge fund measures depend heavily on strategy, but common measures include:

- sensitivity analysis,
- leverage measures,
- gross exposure,
- net exposure,
- long-side and short-side risk,
- scenario analysis,
- stress testing,
- VaR for short horizons,
- maximum drawdown.

### Gross and net exposure

For a long-short fund:

$$
\text{Gross exposure} = |\text{Long exposure}| + |\text{Short exposure}|
$$

$$
\text{Net exposure} = \text{Long exposure} - \text{Short exposure}
$$

Gross exposure captures total market activity and leverage better than net exposure alone.

Example:

- Long exposure = 140% of NAV.
- Short exposure = 60% of NAV.

Then:

$$
\text{Gross exposure} = 140\% + 60\% = 200\%
$$

$$
\text{Net exposure} = 140\% - 60\% = 80\%
$$

A vignette that gives only net exposure may hide substantial leverage.

### Maximum drawdown

Maximum drawdown is the largest peak-to-trough decline over a specified period.

It is useful when returns are non-normal, because standard deviation and beta can understate the pain of large downside moves.

## Defined Benefit Pension Funds

Defined benefit pension funds care about the relationship between assets and liabilities.

Core identity:

$$
\text{Surplus} = \text{Market value of assets} - \text{PV of liabilities}
$$

The key risk is not that assets fall in isolation. The key risk is that the surplus deteriorates.

### Surplus at risk

**Surplus at risk** is a VaR-style measure applied to the surplus:

$$
\text{Surplus at Risk} = \text{potential decline in } (A - L)
$$

This matters because liabilities move when discount rates change. A pension fund can lose surplus even if assets perform well, if liability values rise more.

### Asset-liability matching

To reduce surplus uncertainty, pension funds often match asset duration and convexity to liability duration and convexity. This is the logic behind liability-driven investing.

### Glide path

A glide path is a multi-year plan for adjusting contributions, asset allocation, or hedging to move the plan away from an underfunded or overfunded status.

## Insurers

Insurance companies hold investment portfolios to support policyholder claims and reserves. Their risk measures must consider both market risk and insurance risk.

## Property and Casualty Insurers

P&C insurers sell policies such as auto, home, liability, health, and catastrophe coverage.

Typical measures:

- sensitivity of investment portfolio to market risk factors,
- VaR and capital at risk for investment assets,
- scenario analysis combining insurance and market risks,
- reserve adequacy measures,
- reinsurance analysis,
- geographical diversification of insurance exposure.

### Why P&C differs

P&C claim risk is often not highly correlated with investment market risk. A hurricane can create claims regardless of whether equities are rising or falling. But stress scenarios still need to combine claim events with market shocks because the insurer's investment portfolio may be needed to pay extraordinary claims.

## Life Insurers

Life insurers sell life insurance and annuity products. Their liabilities are often long-dated and sensitive to discount rates and mortality assumptions.

Typical measures:

- asset-liability matching,
- interest-rate sensitivity of assets and liabilities,
- scenario analysis combining market and mortality risks,
- residual mismatch risk between assets and liabilities,
- reserve adequacy.

### Why life insurers differ

Life insurer liabilities can be highly sensitive to market risk because discount rates affect the present value of long-dated annuity payments. A lower discount rate increases the present value of liabilities.

If annuity payments last longer because mortality improves, liabilities also rise.

## Comparison Grid for Vignettes

| Vignette clue | Most likely institution | Risk measure to pick |
|---|---|---|
| Trading book, leverage, geographic/business-unit risk | Bank | VaR, economic capital, stress tests |
| Benchmark-relative equity portfolio | Traditional asset manager | Active share, tracking error |
| Long-short positions, gross exposure, drawdowns | Hedge fund | Leverage, gross exposure, maximum drawdown, VaR |
| Assets versus PV of future benefit payments | Defined benefit pension fund | Surplus at risk, ALM |
| Catastrophe claims plus investment portfolio | P&C insurer | Scenario analysis, capital at risk, reinsurance |
| Annuities, mortality, discount-rate-sensitive liabilities | Life insurer | ALM, liability sensitivity, scenario analysis |

## Worked Examples

### Example 1: Traditional asset manager

A long-only equity manager has:

- active share of 75%,
- ex ante tracking error of 5%,
- ex post tracking error of 3%.

Interpretation:

- Active share says the portfolio is meaningfully different from the benchmark.
- Ex ante tracking error says the current portfolio has 5% expected active risk going forward.
- Ex post tracking error says past realized benchmark-relative volatility was 3%.

For risk control today, ex ante tracking error is more relevant.

### Example 2: Pension fund

A pension plan has:

- Assets = $1,000 million.
- PV liabilities = $1,100 million.

Surplus:

$$
\text{Surplus} = \$1{,}000 - \$1{,}100 = -\$100\text{ million}
$$

The plan is underfunded. If rates fall and the PV of liabilities rises to $1,180 million while assets rise only to $1,030 million:

$$
\text{New surplus} = \$1{,}030 - \$1{,}180 = -\$150\text{ million}
$$

The plan's asset portfolio gained value, but surplus worsened. That is why pensions focus on asset-liability risk, not asset risk alone.

## Exam Traps

| Trap | Correct response |
|---|---|
| Use active share for banks | Active share is most specific to traditional asset managers |
| Use surplus at risk for asset managers | Surplus at risk belongs to defined benefit pension funds |
| Use maximum drawdown for long-only benchmark managers by default | Maximum drawdown is especially relevant for hedge funds and non-normal returns |
| Focus only on asset volatility for pensions | Pension risk is assets minus liabilities |
| Treat P&C and life insurers the same | P&C risk is more catastrophe/claims-driven; life insurer liabilities are long-dated and discount-rate-sensitive |
| Use net exposure alone for hedge funds | Gross exposure can reveal hidden leverage |
| Confuse ex ante and ex post tracking error | Ex ante is forward-looking risk; ex post is backward-looking realized active risk |

## Memory Hook

> **Banks need capital. Managers need benchmark control. Hedge funds need leverage and drawdown control. Pensions need surplus. Insurers need ALM plus claims.**

## Exam-Day Checklist

1. Identify the institution first.
2. Ask whether the target is absolute risk, relative risk, or liability-relative risk.
3. Check whether leverage is central.
4. If benchmark-relative, think active share and tracking error.
5. If liability-relative, think surplus at risk and ALM.
6. If long-short or nonlinear returns, think gross exposure, VaR, stress tests, and maximum drawdown.
7. If insurer, distinguish P&C from life.

## Related Concepts

- [[Risk Limits and Capital Allocation]]
- [[Parametric Historical and Monte Carlo VaR]]
- [[Stress Testing and Scenario Analysis]]
- [[Active Risk and Tracking Error]]
- [[Information Ratio]]
- [[Sharpe Ratio]]
