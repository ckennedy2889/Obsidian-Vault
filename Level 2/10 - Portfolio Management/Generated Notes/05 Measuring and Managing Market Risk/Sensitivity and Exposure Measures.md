---
title: Sensitivity and Exposure Measures
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, sensitivity-analysis, beta, duration, convexity, greeks]
aliases: [Sensitivity Risk Measures, Exposure Measures, Beta Duration Convexity Greeks, PVBP, PV01, Delta Gamma Vega]
---

# Sensitivity and Exposure Measures

## Intuition

Sensitivity measures answer a local question:

> If one risk factor moves a little, how much does my portfolio value change?

They are useful because they tell a manager **what is driving risk**. [[Value at Risk (VaR)]] may say the portfolio can lose $10 million, but sensitivity measures tell whether the risk is coming from equity beta, duration, credit spread exposure, or option gamma/vega.

The limitation is just as important: sensitivity measures do **not** tell the probability of the risk-factor move.

See: [[Measuring and Managing Market Risk]] · [[Stress Testing and Scenario Analysis]] · [[Parametric Historical and Monte Carlo VaR]]

## Sensitivity vs VaR vs Scenario Analysis

| Tool | Question answered | Probability attached? | Main weakness |
|---|---|---:|---|
| **Sensitivity measure** | What happens if one factor changes? | No | Local and usually one-factor |
| **VaR** | How large is the loss cutoff at a chosen probability? | Yes | Hides risk drivers and tail severity |
| **Scenario analysis** | What happens if several factors change together? | Usually no | Scenario choice is subjective |

Good risk management uses all three.

## Equity Exposure: Beta

For equities, the main exposure measure is beta:

$$
\beta_i = \frac{\text{Cov}(R_i, R_M)}{\text{Var}(R_M)}
$$

Beta measures sensitivity to market returns.

| Beta | Interpretation |
|---:|---|
| 0.5 | Moves about half as much as the market |
| 1.0 | Moves about with the market |
| 1.5 | Moves about 1.5 times the market |
| -0.5 | Moves opposite the market, on average |

In CAPM:

$$
E(R_i) = R_F + \beta_i[E(R_M)-R_F]
$$

In multifactor models, beta generalizes to multiple factor sensitivities:

$$
E(R_i) = R_F + \sum_{k=1}^{K}\beta_{i,k}\lambda_k
$$

See: [[APT Arbitrage Opportunities]] · [[Using Multifactor Models]]

## Fixed-Income Exposure: Duration

Duration measures bond price sensitivity to yield changes.

Modified duration approximation:

$$
\%\Delta P \approx -\text{ModDur}\times \Delta y
$$

If modified duration is 6 and yields rise by 50 bps:

$$
\%\Delta P \approx -6 \times 0.005 = -3.0\%
$$

### Modified vs effective duration

| Measure | Best use |
|---|---|
| **Modified duration** | Option-free bonds with stable cash flows |
| **Effective duration** | Bonds with embedded options or uncertain cash flows |

Exam trap:

> Callable bonds, putable bonds, and mortgage-backed securities require effective duration because cash flows change when rates change.

## Fixed-Income Exposure: Convexity

Duration is linear, but the bond price-yield relationship is curved. Convexity adds the second-order correction:

$$
\%\Delta P \approx
-\text{ModDur}\times \Delta y
+ \frac{1}{2}\text{Convexity}\times(\Delta y)^2
$$

Convexity matters more when yield changes are large.

### Duration-convexity worked example

A bond portfolio has:

- Modified duration = 4.241
- Convexity = 22.1
- Yield increase = 50 bps = 0.005

First-order duration effect:

$$
-4.241 \times 0.005 = -0.021205
$$

Second-order convexity effect:

$$
\frac{1}{2}\times 22.1 \times (0.005)^2
= 0.5 \times 22.1 \times 0.000025
= 0.00027625
$$

Total estimated price change:

$$
-0.021205 + 0.00027625 = -0.02092875
$$

$$
\boxed{-2.09\%}
$$

## Fixed-Income Exposure: PVBP / PV01

PVBP, also called PV01, is the price value of a basis point:

> How many dollars does the portfolio gain or lose for a 1 bp change in yield?

Approximation:

$$
\text{PVBP} = \text{ModDur}\times \text{Portfolio value}\times 0.0001
$$

Example:

- Portfolio value = $100 million
- Modified duration = 6.5

$$
\text{PVBP} = 6.5 \times \$100{,}000{,}000 \times 0.0001
$$

$$
= \boxed{\$65{,}000}
$$

A 1 bp yield increase costs about $65,000.

## Option Exposure: The Greeks

Options are nonlinear, so several sensitivities are needed.

| Greek | Measures | Intuition |
|---|---|---|
| **Delta** $\Delta$ | Option price sensitivity to underlying price | Directional exposure |
| **Gamma** $\Gamma$ | Delta sensitivity to underlying price | Curvature / changing delta |
| **Vega** $\nu$ | Option price sensitivity to implied volatility | Volatility exposure |
| **Theta** $\Theta$ | Option price sensitivity to time passing | Time decay |
| **Rho** $\rho$ | Option price sensitivity to interest rates | Rate exposure |

### Delta

If a call option has delta 0.60, a $1 increase in the underlying increases the call value by about $0.60.

If a put option has delta -0.50, a $1 increase in the underlying decreases the put value by about $0.50.

### Gamma

Gamma measures how delta changes.

It is the option version of convexity. Delta is first-order; gamma is second-order.

## Delta-Gamma Approximation

For options:

$$
\Delta V \approx \Delta \times \Delta S
+ \frac{1}{2}\Gamma(\Delta S)^2
$$

where:

| Symbol | Meaning |
|---|---|
| $\Delta V$ | Change in option value |
| $\Delta$ | Option delta |
| $\Delta S$ | Change in underlying price |
| $\Gamma$ | Option gamma |

The second-order term matters for large moves or high-gamma options.

Exam trap:

> The gamma term uses $\frac{1}{2}$ and squares the underlying price change.

## Advantages of Sensitivity Measures

| Advantage | Why it matters |
|---|---|
| Transparent | Shows which factor drives risk |
| Fast | Often easy to compute |
| Hedgeable | Links directly to hedging trades |
| Per-factor | Separates equity, rate, volatility, and other exposures |
| Complements VaR | Explains risk drivers hidden inside aggregate VaR |

## Limitations of Sensitivity Measures

| Limitation | Example |
|---|---|
| No probability | Duration says loss per yield move, not probability of the move |
| Local approximation | Delta or duration can fail for large moves |
| Often one-factor | Real crises involve multiple risk factors |
| Correlation ignored | Individual sensitivities may miss joint moves |
| Nonlinear payoffs need full revaluation | Options and embedded-option bonds may require pricing models |

## When to Full Revalue

Use pricing models rather than simple sensitivities when:

- risk-factor moves are large,
- options are material,
- bonds have embedded options,
- payoff is path dependent,
- correlations or volatilities change,
- stress scenario affects several factors at once.

Scenario analysis should revalue positions under the scenario risk factors rather than relying only on linear approximations.

## Exam Traps

| Trap | Correct response |
|---|---|
| Use beta/duration/delta to estimate probability | Sensitivities do not attach probabilities |
| Use modified duration for callable bonds or MBS | Use effective duration |
| Ignore convexity for a large rate move | Add the convexity term |
| Forget the minus sign in duration | Bond prices move inversely with yields |
| Forget $\frac{1}{2}$ or square in convexity/gamma term | Second-order approximations require both |
| Treat delta as constant for large underlying moves | Delta changes; gamma captures that |
| Say VaR and sensitivity are substitutes | They are complements |

## Memory Hook

> **Beta for stocks, duration for bonds, Greeks for options.**

And:

> **Sensitivity tells direction and size, not probability.**

## Exam-Day Checklist

1. Identify the asset type: equity, fixed income, option.
2. Match the sensitivity: beta, duration/PVBP, or Greeks.
3. For fixed income, decide modified vs effective duration.
4. For large rate moves, include convexity.
5. For options, include gamma when delta alone is insufficient.
6. If probability is requested, move to VaR.
7. If multiple factors move together, move to scenario analysis.

## Related Concepts

- [[Measuring and Managing Market Risk]]
- [[Stress Testing and Scenario Analysis]]
- [[Parametric Historical and Monte Carlo VaR]]
- [[Risk Limits and Capital Allocation]]
- [[Institutional Risk Measures]]
