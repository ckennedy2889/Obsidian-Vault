---
title: Historical vs Monte Carlo Simulation
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, simulation, historical-simulation, Monte-Carlo, bootstrapping, sensitivity-analysis]
aliases: [Historical Simulation, Monte Carlo Simulation, Bootstrapping, Simulation Inputs, Tail Dependence, Simulation Sensitivity Analysis]
---

# Historical vs Monte Carlo Simulation

## Intuition

Backtesting asks:

> What happened when the strategy walked through actual history in order?

Simulation asks a broader question:

> What else could happen if returns are random?

There are two main simulation approaches:

- **Historical simulation:** randomly reshuffle actual past returns.
- **Monte Carlo simulation:** randomly draw from a specified statistical model.

Historical simulation trusts the data. Monte Carlo trusts the model.

See: [[Backtesting and Simulation]] · [[Backtesting Biases and Pitfalls]] · [[Trade Return Distributions - Skewness and Kurtosis]]

## Historical Simulation

Historical simulation uses actual historical returns, but it does not replay them in chronological order. Instead, it randomly samples from the historical data.

Mechanism:

$$
r_t^{\text{sim}} \sim \{r_1, r_2, \ldots, r_N\}
$$

The analyst draws a historical return, records it in a simulated path, then draws again.

## Bootstrapping

**Bootstrapping** means sampling **with replacement**.

Example:

Suppose historical monthly returns are:

| Month | Return |
|---|---:|
| 1 | 2.0% |
| 2 | -1.0% |
| 3 | 4.0% |
| 4 | -6.0% |
| 5 | 1.5% |

A bootstrapped five-month simulated path might be:

| Simulated draw | Historical month selected | Return |
|---|---:|---:|
| 1 | 3 | 4.0% |
| 2 | 3 | 4.0% |
| 3 | 5 | 1.5% |
| 4 | 1 | 2.0% |
| 5 | 4 | -6.0% |

Month 3 can appear twice because the sampling is with replacement.

> [!warning] Fixed Income Trap
> Bootstrapping here means random sampling with replacement. It is unrelated to bootstrapping spot rates in fixed income.

## Monte Carlo Simulation

Monte Carlo simulation uses a probability model.

Instead of drawing directly from historical returns, the analyst:

1. chooses key decision variables,
2. specifies a distribution for each variable,
3. calibrates the distribution parameters,
4. draws random observations,
5. computes the strategy return,
6. repeats many times.

Common distribution choices:

- normal,
- lognormal,
- uniform,
- Student's t,
- skewed t,
- multivariate versions of these distributions.

## Comparison

| Feature | Historical simulation | Monte Carlo simulation |
|---|---|---|
| Source of randomness | Actual historical observations | Statistical distribution |
| Distribution assumption | None beyond representativeness of history | Explicit model choice |
| Can include historical skew and fat tails? | Yes, if present in sample | Yes, only if modeled |
| Can create never-seen events? | No | Yes |
| Transparency | High | Lower |
| Complexity | Lower | Higher |
| Main weakness | Past may not represent future | Model may be misspecified |

## Simulation Steps

The standard simulation workflow:

1. Select the target variable, usually strategy return.
2. Determine key decision variables, such as asset returns, factor returns, volatilities, correlations, and portfolio weights.
3. Select number of trials, often 1,000 to 10,000.
4. Specify how each variable is generated.
5. Draw random values.
6. Compute the target variable for that draw.
7. Repeat for all trials.
8. Analyze the output distribution.

## Model Calibration

Monte Carlo needs calibrated inputs:

- mean return,
- standard deviation,
- correlations,
- skewness,
- kurtosis,
- tail dependence,
- factor loadings,
- portfolio weights,
- rebalancing rules.

Calibration uses historical data, regressions, and distribution-fitting methods. The model should fit enough structure to be useful without becoming too complex to estimate reliably.

## The Complexity Tradeoff

There is a practical tension:

| Model type | Strength | Weakness |
|---|---|---|
| Too simple | Low estimation error, easy to understand | High specification error if reality is non-normal or nonlinear |
| Too complex | Can fit historical details | High estimation error; parameters are noisy and fragile |

A multivariate normal model is simple, but it ignores skewness, excess kurtosis, and tail dependence. A skewed t model can capture tails better, but it requires more parameter estimates.

## Multivariate Distributions

If assets or factors are correlated, do not simulate each one independently.

Wrong approach:

$$
r_A \sim F_A,\quad r_B \sim F_B
\quad\text{independently}
$$

Better approach:

$$
\begin{bmatrix}
r_A \\
r_B
\end{bmatrix}
\sim \text{Joint distribution with correlation}
$$

Reason: portfolio risk depends on co-movement. Ignoring correlation can understate or overstate diversification.

## Tail Dependence

Tail dependence means variables tend to crash together in the tails.

Normal correlation can miss this because normal distributions can make extreme joint losses look too rare.

Example:

- In normal markets, equities and credit spreads may have moderate correlation.
- In crisis markets, equities fall and credit spreads widen together.

If the Monte Carlo model ignores this tail dependence, downside risk is understated.

## Sensitivity Analysis

Sensitivity analysis asks:

> How do simulation results change if an input assumption changes?

It is especially useful after Monte Carlo because Monte Carlo output is only as good as the model assumptions.

Examples:

- Change normal distribution to skewed t distribution.
- Increase volatility assumptions.
- Increase correlation during stress.
- Reduce expected returns.
- Add fatter tails.
- Change rebalance frequency.

Then compare outputs such as:

- average return,
- volatility,
- [[Sharpe Ratio]],
- [[Sortino ratio]],
- maximum drawdown,
- [[Conditional VaR (CVaR) and Expected Shortfall]].

## Worked Example: Normal vs Skewed t

A risk officer simulates a strategy with 1,000 Monte Carlo trials.

### Baseline model

- Multivariate normal returns.
- Expected annual return = 8%.
- Volatility = 12%.
- 95% CVaR = -18%.
- Maximum drawdown = -24%.

### Sensitivity model

The officer reruns the simulation using a multivariate skewed t distribution to allow fat tails and negative skewness.

- Expected annual return = 7.5%.
- Volatility = 13%.
- 95% CVaR = -28%.
- Maximum drawdown = -39%.

Interpretation:

The average return barely changed, but tail risk worsened sharply. The strategy's risk was hidden by the normality assumption.

## Historical Scenario Analysis vs Historical Simulation

Do not confuse these.

| Tool | What it does | Sequence preserved? |
|---|---|---|
| **Historical scenario analysis** | Replays a specific event, such as 2008 | Yes |
| **Historical simulation** | Randomly samples historical returns to create many paths | No |

Historical scenario analysis asks:

> What if 2008 happened again?

Historical simulation asks:

> What random paths can we build from past returns?

## Exam Traps

| Trap | Correct response |
|---|---|
| Say Monte Carlo automatically fixes fat tails | Only if fat-tailed distributions are specified |
| Confuse bootstrapping with fixed-income spot-rate bootstrapping | Here it means sampling with replacement |
| Treat historical simulation as chronological backtesting | Historical simulation randomly samples past data |
| Ignore tail dependence | Joint crashes can be understated |
| Model correlated assets independently | Use a multivariate distribution |
| Assume more simulation trials fix model error | More trials reduce sampling error, not misspecification |
| Trust historical simulation when the sample lacks crises | It cannot draw events that never occurred in the sample |
| Treat sensitivity analysis as a separate forecast | It is a robustness test of assumptions |

## Memory Hook

> **Historical simulation shuffles the past. Monte Carlo invents futures from a model. Sensitivity analysis asks what breaks if the model is wrong.**

## Exam-Day Checklist

1. Identify whether the process replays history, shuffles history, or draws from a distribution.
2. If sampling with replacement is mentioned, think bootstrapping.
3. If multiple assets or factors are correlated, require a multivariate distribution.
4. Check whether skewness, excess kurtosis, and tail dependence are modeled.
5. Interpret simulation output using return, risk, and downside metrics.
6. Use sensitivity analysis to test distributional and parameter assumptions.
7. Remember that historical simulation depends on the quality and completeness of the historical dataset.

## Related Concepts

- [[Backtesting and Simulation]]
- [[Backtesting Biases and Pitfalls]]
- [[Skewness]]
- [[Trade Return Distributions - Skewness and Kurtosis]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
- [[Parametric Historical and Monte Carlo VaR]]
