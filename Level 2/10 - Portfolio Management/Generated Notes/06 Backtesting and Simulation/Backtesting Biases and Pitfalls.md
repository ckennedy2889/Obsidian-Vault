---
title: Backtesting Biases and Pitfalls
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, backtesting, bias, data-snooping, look-ahead-bias, survivorship-bias]
aliases: [Backtesting Problems, Survivorship Bias, Look-Ahead Bias, Data Snooping, Overfitting, P-Hacking, Reporting Lag]
---

# Backtesting Biases and Pitfalls

## Intuition

A backtest is a historical simulation of a strategy. That makes it useful, but also dangerous.

The danger is that the analyst accidentally lets the strategy cheat:

- it invests only in companies that survived,
- it uses information before it was public,
- it tests hundreds of signals and reports only the winner,
- it ignores the cost of trading,
- or it assumes a past regime will repeat forever.

The CFA exam treats a flawed backtest as worse than no backtest because it gives false confidence.

See: [[Backtesting and Simulation]] · [[Using Multifactor Models]] · [[Skewness]] · [[Trade Return Distributions - Skewness and Kurtosis]]

## Master Table

| Pitfall | What goes wrong | Usual bias | Fix |
|---|---|---|---|
| **Survivorship bias** | Uses only securities that still exist today | Returns too high, risk too low | Use point-in-time universe including delisted firms |
| **Look-ahead bias** | Uses information unavailable at decision date | Returns too high, Sharpe too high | Use point-in-time data and proper reporting lags |
| **Reporting lag error** | Uses fundamentals before release date | Same as look-ahead bias | Lag accounting data by realistic publication delay |
| **Restatement bias** | Uses revised data instead of originally reported data | Strategy seems smarter than it was | Use data as originally available |
| **Data snooping / p-hacking** | Tests many models and keeps the winner | False positives | Require economic rationale, higher t-stat, cross-validation |
| **Overfitting** | Model memorizes historical noise | Great in-sample, poor out-of-sample | Simpler model, holdout sample, regularization |
| **Ignored transaction costs** | Assumes frictionless trading | Gross returns overstated | Include commissions, bid-ask, market impact, borrow costs |
| **Nonstationarity** | Assumes relationships are stable across regimes | Future performance disappoints | Test across regimes and use scenario analysis |

## Survivorship Bias

**Survivorship bias** occurs when the backtest includes only securities that survived to the end of the sample.

Example:

> An analyst tests a 20-year strategy by downloading today's S&P 500 constituents and pulling their historical prices.

Problem:

- Today's constituents are the winners that survived.
- Bankruptcies, delistings, and index removals are excluded.
- The strategy looks as if it avoided failed firms, even though it could not have known that in advance.

Mechanism:

$$
\text{Backtested universe} \neq \text{Actual investable universe at time } t
$$

Fix:

- Use point-in-time index membership.
- Include delisted firms and delisting returns.
- Reconstruct the investable universe as it actually existed on each rebalancing date.

Exam clue:

> "The analyst used current constituents and downloaded their historical returns."

That is survivorship bias.

## Look-Ahead Bias

**Look-ahead bias** occurs when the backtest uses information that was not known at the time of the simulated investment decision.

Example:

> A strategy rebalances on January 1 using full-year earnings for the prior fiscal year, even though those earnings were released in February.

The model is peeking into the future.

### Reporting lag

Financial statements are not available the instant the reporting period ends. A firm with a December 31 fiscal quarter may report results weeks later.

If the backtest uses the data on December 31 or January 1, it is cheating.

Fix:

- Lag fundamentals by a realistic delay, such as one to three months depending on the data.
- Prefer exact point-in-time release dates when available.
- Use data as it was known on the decision date.

### Restated data

Restated financials can create look-ahead bias.

If a company later corrects prior earnings, a historical investor did not know the corrected number at the time. A valid backtest should use originally reported figures, not cleaned-up hindsight.

Exam clue:

> "The analyst cleaned the historical database by replacing originally reported values with final restated values."

That sounds careful, but it introduces look-ahead bias.

## Data Snooping and P-Hacking

**Data snooping** occurs when an analyst tries many strategies or variables and reports only the ones that worked historically.

The problem is statistical inevitability.

If you test 100 unrelated signals at a 5% significance level, roughly 5 may look significant by pure chance.

$$
\text{False positives} \approx N \times \alpha
$$

With $N = 100$ and $\alpha = 5\%$:

$$
100 \times 5\% = 5
$$

Those five "discoveries" may have no economic meaning.

Fix:

- Require an economic rationale before testing.
- Use a higher critical t-statistic, such as 3 rather than 2.
- Use cross-validation.
- Test out-of-sample.
- Disclose the number of models tested.

Exam clue:

> "The analyst tested hundreds of variables and selected the one with the highest t-statistic."

That is data snooping, not skill.

## Overfitting

**Overfitting** occurs when a model is so tuned to historical data that it captures noise rather than persistent structure.

Symptoms:

- Excellent in-sample Sharpe ratio.
- Poor out-of-sample performance.
- Many parameters relative to available observations.
- Complex rules with little economic intuition.

Mechanism:

The model has low historical error because it memorizes the sample. But its estimation error is high because the parameters are fragile.

Fix:

- Use simpler models.
- Penalize complexity.
- Keep a true holdout sample.
- Use rolling-window or walk-forward validation.
- Require economic intuition for every factor.

## Transaction Costs and Trading Constraints

Many backtests report gross returns, but investors receive net returns.

Important costs:

- commissions,
- bid-ask spreads,
- market impact,
- taxes,
- borrow fees for short positions,
- financing costs,
- turnover limits,
- liquidity constraints.

Example:

> A small-cap mean-reversion strategy earns 8% gross alpha with 600% annual turnover.

If round-trip trading costs are 75 bps:

$$
\text{Cost drag} = 6.00 \times 0.75\% = 4.50\%
$$

Net alpha:

$$
8.00\% - 4.50\% = 3.50\%
$$

The strategy is still positive, but much weaker. If costs were 150 bps, net alpha would be negative:

$$
8.00\% - 6.00 \times 1.50\% = -1.00\%
$$

Exam clue:

> "The strategy rebalances daily in illiquid securities and ignores trading costs."

The backtest is likely overstated.

## Nonstationarity and Regime Dependence

Financial markets are not stationary. Means, volatilities, correlations, and factor premia change across regimes.

Examples:

- Equity-bond correlations can shift from negative to positive.
- Value strategies can underperform for long stretches.
- Volatility can jump from calm to crisis regimes.
- Liquidity can disappear exactly when it is needed.

Fix:

- Use long samples covering multiple regimes.
- Analyze performance separately in expansions, recessions, low-volatility periods, and high-volatility periods.
- Run historical scenario analysis.
- Use sensitivity analysis to test assumptions.

See: [[Stress Testing and Scenario Analysis]].

## Bias Diagnosis by Vignette Language

| Vignette wording | Bias |
|---|---|
| "Current index constituents were used for the full 20-year period" | Survivorship bias |
| "The model used annual earnings on the fiscal year-end date" | Look-ahead bias via reporting lag |
| "Restated earnings were used for historical accuracy" | Look-ahead / restatement bias |
| "Hundreds of variables were tested and the best was selected" | Data snooping |
| "Model has 40 parameters and fits past data almost perfectly" | Overfitting |
| "Daily rebalancing but no transaction cost assumption" | Ignored transaction costs |
| "Strategy worked only in the low-rate era" | Nonstationarity / regime dependence |

## Worked Example: Identifying Multiple Biases

An analyst tests a stock-selection strategy from 2004 to 2024. The strategy:

- uses today's Russell 3000 members,
- ranks stocks each January 1 using full-year earnings ending December 31,
- tests 300 valuation ratios and selects the best one,
- rebalances weekly,
- ignores transaction costs.

Diagnosis:

| Fact | Problem |
|---|---|
| Today's Russell 3000 members | Survivorship bias |
| December 31 earnings used January 1 | Look-ahead bias / reporting lag |
| 300 ratios tested | Data snooping |
| Best ratio selected after testing | Overfitting risk |
| Weekly rebalancing, no costs | Gross return overstated |

The correct conclusion is not "the strategy works." The correct conclusion is that the evidence is unreliable until those issues are fixed.

## Exam Traps

| Trap | Correct response |
|---|---|
| Treat survivorship bias as harmless because the universe is diversified | Diversification does not fix missing failed firms |
| Treat restated data as more accurate and therefore better | It may be more accurate now, but it was not available then |
| Confuse data snooping with look-ahead bias | Data snooping tests too many models; look-ahead uses future information |
| Accept a high in-sample Sharpe ratio | Ask whether it survives out-of-sample testing |
| Ignore costs because the strategy has high gross alpha | High turnover can erase alpha |
| Assume long history solves everything | Long history can still hide regime dependence |

## Memory Hook

> **Survivorship = who is in the universe. Look-ahead = what the model knew. Data snooping = how many times the analyst searched. Overfitting = how tightly the model memorized.**

## Exam-Day Checklist

1. Was the universe point-in-time?
2. Were delisted firms included?
3. Was every data item available on the decision date?
4. Were reporting lags and restatements handled correctly?
5. How many strategies or variables were tested?
6. Is there an economic rationale?
7. Did the model work out-of-sample?
8. Were transaction costs, liquidity, and shorting constraints included?
9. Was performance tested across regimes?

## Related Concepts

- [[Backtesting and Simulation]]
- [[Using Multifactor Models]]
- [[Fama-French Model]]
- [[Skewness]]
- [[Trade Return Distributions - Skewness and Kurtosis]]
- [[Parametric Historical and Monte Carlo VaR]]
