---
title: Parametric Historical and Monte Carlo VaR
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, VaR, parametric-VaR, historical-simulation, Monte-Carlo]
aliases: [VaR Estimation Methods, Parametric VaR, Variance-Covariance VaR, Historical Simulation VaR, Monte Carlo VaR]
---

# Parametric Historical and Monte Carlo VaR

## Intuition

[[Value at Risk (VaR)]] is a left-tail cutoff. It says:

> Over a specified horizon, there is only a specified probability that losses will be worse than this number.

The exam problem is that there is not one way to find the cutoff. There are three main recipes:

1. **Parametric VaR:** trust the formula.
2. **Historical simulation VaR:** trust the past.
3. **Monte Carlo VaR:** trust the model.

All three produce a VaR number, but they delegate trust to different assumptions.

See: [[Measuring and Managing Market Risk]] · [[Conditional VaR (CVaR) and Expected Shortfall]] · [[Stress Testing and Scenario Analysis]]

## VaR Interpretation

A weekly 5% VaR of $1 million means:

> There is a 5% probability that the portfolio will lose **more than** $1 million over one week.

It does **not** mean $1 million is the maximum loss. Losses beyond VaR are exactly what [[Conditional VaR (CVaR) and Expected Shortfall]] tries to measure.

## The Three Methods

| Method | Core assumption | How the cutoff is found | Best for | Main weakness |
|---|---|---|---|---|
| **Parametric / variance-covariance** | Risk factors follow an assumed distribution, usually normal | Compute mean and standard deviation, then use a critical value | Linear portfolios, quick reporting | Normality and covariance estimates can be wrong |
| **Historical simulation** | The lookback period is representative of the future | Revalue today's portfolio using historical risk-factor changes, then rank losses | Portfolios where past data include relevant tail events | Future may not resemble the lookback period |
| **Monte Carlo simulation** | The analyst's chosen model for distributions, correlations, and pricing is valid | Simulate many random scenarios, revalue the portfolio, then rank losses | Nonlinear and path-dependent portfolios | Model risk and computational complexity |

## Method 1: Parametric VaR

Parametric VaR is also called **variance-covariance VaR** because it estimates portfolio risk using means, variances, and covariances.

Under a normal distribution:

$$
\text{VaR}_{p} = (z_p\sigma_P - \mu_P) \times V
$$

Equivalently:

$$
\text{VaR}_{p} = [\mu_P - z_p\sigma_P](-1)\times V
$$

where:

| Symbol | Meaning |
|---|---|
| $p$ | Tail probability, such as 5% or 1% |
| $z_p$ | Positive standard-normal critical value |
| $\mu_P$ | Expected portfolio return over the VaR horizon |
| $\sigma_P$ | Portfolio standard deviation over the VaR horizon |
| $V$ | Portfolio market value |

Common critical values:

| Tail probability | Confidence language | $z$ value |
|---|---|---|
| 5% | 95% confidence | 1.645 or 1.65 |
| 1% | 99% confidence | 2.326 or 2.33 |
| 0.1% | 99.9% confidence | 3.090 |

### Portfolio variance input

For a two-asset portfolio:

$$
\sigma_P^2 =
w_A^2\sigma_A^2
+ w_B^2\sigma_B^2
+ 2w_Aw_B\rho_{AB}\sigma_A\sigma_B
$$

This is why the covariance estimate matters. A small change in correlation can materially change VaR.

### Parametric worked example

A portfolio has:

- Market value $V = \$150,000,000$
- Daily expected return $\mu_P = 0.0384\% = 0.000384$
- Daily standard deviation $\sigma_P = 0.9960\% = 0.009960$
- 1-day 1% VaR, so $z = 2.33$

Compute VaR:

$$
\text{VaR}_{1\%} = [0.000384 - 2.33(0.009960)](-1)\times \$150{,}000{,}000
$$

$$
= [0.000384 - 0.0232068](-1)\times \$150{,}000{,}000
$$

$$
= 0.0228228 \times \$150{,}000{,}000
$$

$$
= \boxed{\$3{,}423{,}420}
$$

Interpretation: there is a 1% probability of losing more than about $3.42 million in one day, given the model assumptions.

### Scaling horizons

If daily returns are independent and identically distributed:

$$
\mu_{\text{annual}} = 250\mu_{\text{daily}}
$$

$$
\sigma_{\text{annual}} = \sigma_{\text{daily}}\sqrt{250}
$$

The trap: expected return scales with time, but volatility scales with the **square root** of time.

## Method 2: Historical Simulation VaR

Historical simulation asks:

> What would today's portfolio have lost if the actual historical risk-factor moves had happened again?

Steps:

1. Choose a lookback period, such as 250 or 500 trading days.
2. Apply each historical risk-factor change to today's portfolio.
3. Revalue the portfolio for each historical day.
4. Sort returns or P&L from worst to best.
5. Pick the percentile loss matching the VaR tail probability.

### Historical simulation worked example

A risk manager has 250 daily P&L observations and wants 1-day 5% VaR.

Tail count:

$$
250 \times 5\% = 12.5
$$

For exam purposes, use the conservative cutoff: round up to the 13th worst observation.

If the 13th worst P&L is a loss of $820,000, then:

$$
\text{1-day 5% historical VaR} = \boxed{\$820{,}000}
$$

Interpretation: based on the historical lookback period, 5% of days produced losses of about $820,000 or worse.

### Why it helps

Historical simulation does not assume normality. If the lookback period includes skewness, fat tails, jumps, and option nonlinearity, those effects are embedded in the historical outcomes.

### Why it fails

It assumes the selected history is relevant. A calm lookback period can understate risk before a crisis. A crisis-heavy lookback period can overstate risk after conditions normalize.

## Method 3: Monte Carlo VaR

Monte Carlo simulation asks:

> If our model of the risk factors is right, what losses appear in thousands of simulated futures?

Steps:

1. Identify risk factors.
2. Specify distributions for those risk factors.
3. Specify correlations or a multivariate distribution when risk factors move together.
4. Generate thousands of random scenarios.
5. Revalue the portfolio under each scenario.
6. Sort simulated P&L from worst to best.
7. Pick the percentile loss.

### Monte Carlo worked example

A manager runs 10,000 simulations and wants 99% VaR.

Tail count:

$$
10{,}000 \times 1\% = 100
$$

If the 100th worst simulated loss is $4.6 million:

$$
\text{99% Monte Carlo VaR} = \boxed{\$4.6\text{ million}}
$$

The 99% [[Conditional VaR (CVaR) and Expected Shortfall]] would average the worst 100 simulated losses. VaR only picks the cutoff.

### Why it helps

Monte Carlo is the most flexible method. It can model:

- options and nonlinear payoffs,
- path-dependent instruments,
- non-normal distributions,
- changing volatility,
- correlated risk factors,
- fat tails and skewness if the model includes them.

### Why it fails

Monte Carlo is only as good as the model. If the analyst assumes multivariate normal returns when actual returns have fat tails and asymmetric dependence, the simulated tail will be too mild.

## Method Selection Rules

| Vignette clue | Best answer |
|---|---|
| Simple linear portfolio, quick estimate, normality assumed | Parametric VaR |
| Options or nonlinear instruments, but rich historical data | Historical simulation or Monte Carlo |
| Exotic derivatives or path-dependent payoffs | Monte Carlo |
| No distributional assumption desired | Historical simulation |
| Need shocks that never occurred historically | Monte Carlo or scenario analysis |
| Need a transparent, easy-to-audit method | Parametric or historical |
| Need model flexibility | Monte Carlo |

## Advantages and Limitations

| Method | Advantages | Limitations |
|---|---|---|
| Parametric | Fast, transparent, easy to communicate, needs relatively few inputs | Poor for options, sensitive to $\mu$, $\sigma$, and correlations, often understates fat-tail risk |
| Historical simulation | No distribution assumption, intuitive, can reflect actual historical skew and option behavior | Fully dependent on lookback period, misses events absent from history, treats past as representative |
| Monte Carlo | Most flexible, handles nonlinear and path-dependent portfolios, can model custom distributions | Computationally intensive, less transparent, highly sensitive to model specification |

## Tail Indexing

When a vignette gives ranked outcomes, convert confidence level into tail count.

Formula:

$$
\text{Tail count} = N(1 - X)
$$

where $N$ is observations or simulations and $X$ is confidence level.

Examples:

| Setup | Tail count | VaR cutoff |
|---|---:|---|
| 250 observations, 95% confidence | $250(0.05)=12.5$ | 13th worst observation |
| 500 observations, 99% confidence | $500(0.01)=5$ | 5th worst observation |
| 1,000 simulations, 99% confidence | $1{,}000(0.01)=10$ | 10th worst simulation |
| 10,000 simulations, 99% confidence | $10{,}000(0.01)=100$ | 100th worst simulation |

If the exam gives a convention, follow it. If not, use the conservative tail observation rather than interpolating unless the prompt explicitly asks for interpolation.

## VaR vs CVaR

VaR answers:

$$
\text{Where does the tail begin?}
$$

CVaR answers:

$$
\text{How bad is the average loss inside the tail?}
$$

Two portfolios can have identical VaR but very different tail losses. CVaR will distinguish them; VaR may not.

## Exam Traps

| Trap | Correct response |
|---|---|
| Define VaR as the maximum loss | VaR is a cutoff loss; worse losses can occur |
| Forget the horizon | VaR is meaningless without time horizon |
| Forget the tail probability | VaR is meaningless without confidence level or loss probability |
| Use linear time scaling for volatility | Volatility scales by $\sqrt{T}$ |
| Use parametric VaR for options without caution | Options are nonlinear; parametric normal VaR can fail badly |
| Treat historical simulation as forward-looking truth | It is only as good as the lookback period |
| Treat Monte Carlo as objective | It depends on chosen distributions, correlations, and pricing models |
| Pick the wrong ranked observation | Convert confidence to tail count before selecting the cutoff |
| Confuse VaR and CVaR | VaR is cutoff; CVaR is average tail loss |

## Memory Hook

> **P-H-M: Formula, Past, Model.**

- **Parametric:** formula.
- **Historical:** past.
- **Monte Carlo:** model.

The method's strength is also its weakness because that is where the trust sits.

## Exam-Day Checklist

1. Identify horizon and confidence level.
2. Identify the VaR method.
3. For parametric VaR, use the correct $z$ value and scale volatility by $\sqrt{T}$.
4. For historical or Monte Carlo VaR, rank losses from worst to best.
5. Convert confidence level into tail count.
6. Interpret VaR as a probability of exceeding the cutoff, not a maximum loss.
7. If the portfolio contains options, be skeptical of simple parametric VaR.
8. If the question asks about tail severity, move from VaR to [[Conditional VaR (CVaR) and Expected Shortfall]].

## Related Concepts

- [[Measuring and Managing Market Risk]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
- [[Incremental VaR]]
- [[Stress Testing and Scenario Analysis]]
- [[Backtesting and Simulation]]
- [[Skewness]]
- [[Trade Return Distributions - Skewness and Kurtosis]]
