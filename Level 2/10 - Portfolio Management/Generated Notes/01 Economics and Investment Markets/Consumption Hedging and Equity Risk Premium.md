---
title: Consumption Hedging and Equity Risk Premium
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, economics, consumption-hedging, equity-risk-premium, marginal-utility]
aliases: [Consumption Hedging, Equity Risk Premium, ERP, Intertemporal Rate of Substitution, Marginal Utility of Consumption]
---

# Consumption Hedging and Equity Risk Premium

## Intuition

An asset is most valuable when it pays off exactly when investors most need money.

Bad economic times are when investors value extra consumption the most. Jobs are insecure, income is lower, portfolios are down, and marginal utility of consumption is high. So an asset that pays well in recessions is a **good consumption hedge**.

Equities usually do the opposite. They tend to fall in recessions, right when investors most want wealth. That is why equities require a positive [[equity risk premium]].

See: [[Economics and Investment Markets Framework]] · [[Credit spreads]] · [[Commercial Real Estate]]

## Marginal Utility of Consumption

Marginal utility is the extra satisfaction from one more unit of consumption.

Because of diminishing marginal utility:

| State | Wealth / consumption | Marginal utility of extra consumption |
|---|---|---|
| Expansion | High | Low |
| Recession | Low | High |

This is the mechanism behind consumption hedging.

An extra dollar in a recession is more valuable than an extra dollar in a boom.

## Intertemporal Rate of Substitution

The intertemporal rate of substitution compares the utility of future consumption with the utility of current consumption.

Conceptually:

$$
m_{t,s} = \frac{MU_{t+s}}{MU_t}
$$

where:

| Symbol | Meaning |
|---|---|
| $MU_t$ | Marginal utility of current consumption |
| $MU_{t+s}$ | Expected marginal utility of future consumption |
| $m_{t,s}$ | Intertemporal marginal rate of substitution |

If future consumption is expected to be abundant, future marginal utility is low. If future consumption is expected to be scarce, future marginal utility is high.

## Link to Real Risk-Free Rates

### Strong expected future economy

If investors expect high future income:

1. Future consumption is expected to be plentiful.
2. Marginal utility of future consumption falls.
3. Investors feel less need to save.
4. The real risk-free rate must rise to induce saving.

So stronger expected growth tends to be associated with higher real rates.

### Weak expected future economy

If investors expect recession:

1. Future consumption is expected to be scarce.
2. Marginal utility of future consumption rises.
3. Investors want to save more today.
4. The real risk-free rate can fall because investors are already willing to defer consumption.

Exam trap:

> A bad economy does not automatically mean higher real default-free rates. In this framework, weak expected growth pushes real risk-free rates down.

## Risk Premium Mechanism

Assets are priced based on how their payoffs covary with marginal utility.

| Asset payoff pattern | Investor value | Required risk premium |
|---|---|---|
| Pays off in bad times | Very valuable | Low or even negative |
| Pays off in good times but fails in bad times | Less valuable | Positive |

Reason:

- A payoff in a recession arrives when $MU$ is high.
- A payoff in a boom arrives when $MU$ is low.

Investors will pay more for recession payoffs, which lowers the asset's expected return.

## Good Consumption Hedges

A good consumption hedge provides wealth when investors most need it.

Examples:

- default-free government bonds that rise when growth expectations deteriorate,
- assets with stable cash flows during recessions,
- inflation-linked bonds for inflation-sensitive consumption needs, depending on the risk being hedged.

Good hedges are valuable, so investors accept lower expected returns.

## Why Equities Require a Positive Risk Premium

Equities are claims on corporate cash flows. Corporate earnings and equity prices are generally procyclical:

- expansions: profits rise, equity prices rise,
- recessions: profits fall, equity prices fall.

That means equities tend to pay off when marginal utility is low and perform poorly when marginal utility is high.

Equities are therefore poor consumption hedges.

The compensation for holding that bad timing is the equity risk premium:

$$
\text{Required equity return} = \text{default-free rate} + \text{risk premiums}
$$

The equity risk premium is positive because equities fail investors in bad consumption states.

## The Reversed Logic Trap

Wrong:

> Equities have high expected returns because they are good hedges.

Correct:

> Equities have high expected returns because they are poor hedges.

Good hedges are expensive and have lower expected returns. Poor hedges are cheaper and must offer higher expected returns.

## Commercial Real Estate Comparison

Commercial real estate has both bond-like and equity-like features.

### Bond-like cash flows

Rental income can be relatively stable because lease contracts lock in payments. Tenant credit quality matters, like bond issuer credit quality.

### Equity-like property values

Property values are cyclical because they depend on:

- economic growth,
- occupancy,
- market rents,
- cap rates,
- discount rates,
- terminal value expectations.

So commercial real estate can have relatively stable rental cash flows but still cyclical market values.

### Consumption hedge conclusion

Commercial real estate property values often fall in downturns, so the asset class is not a strong consumption hedge. Investors require risk premiums for:

- terminal value uncertainty,
- illiquidity,
- tenant credit risk,
- cyclical property values.

## Worked Example: Ranking Required Risk Premiums

Assume three assets:

| Asset | Payoff behavior in recession | Consumption hedge quality |
|---|---|---|
| Asset A | Pays more in recession | Good |
| Asset B | Stable payoff | Moderate |
| Asset C | Falls sharply in recession | Poor |

Required risk premium ranking:

$$
\text{Asset C} > \text{Asset B} > \text{Asset A}
$$

Reason: Asset C performs badly when marginal utility is high, so investors demand the most compensation.

## Exam Traps

| Trap | Correct response |
|---|---|
| Say equities earn a high premium because they are good consumption hedges | Equities are poor consumption hedges, so they require a positive premium |
| Say good hedges require high expected return | Good hedges are valuable and therefore have lower required premiums |
| Treat a recession as automatically raising real risk-free rates | Weak expected growth tends to reduce real rates through higher saving demand |
| Treat commercial real estate cash flows and values as equally cyclical | Rental cash flows may be steadier; property values are more cyclical |
| Ignore marginal utility | The value of payoff timing depends on when consumption is most valuable |

## Memory Hook

> **Good hedge = pays in bad times = lower premium. Poor hedge = fails in bad times = higher premium.**

For equities:

> **Stocks pay when you least need help and fall when you most need help. That is the ERP.**

## Exam-Day Checklist

1. Identify whether the asset pays off in good or bad economic states.
2. Link bad states to high marginal utility of consumption.
3. If the asset pays in bad states, assign good hedge and lower premium.
4. If the asset fails in bad states, assign poor hedge and positive premium.
5. For equities, remember poor hedge means positive ERP.
6. For real estate, separate rental cash flow stability from property value cyclicality.

## Related Concepts

- [[Economics and Investment Markets Framework]]
- [[Credit spreads]]
- [[Commercial Real Estate]]
- [[Business Cycle]]
- [[Risk Premium]]
