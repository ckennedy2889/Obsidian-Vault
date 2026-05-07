---
title: Skewness
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, risk-management, return-distributions, statistics]
aliases: [Positive skewness, Negative skewness, Right skew, Left skew, Sample skewness]
---

# Skewness

## Real-World Analogy

Imagine two managers both average 1% per month. One manager makes roughly 1% every month, with occasional small surprises in either direction. The other manager makes 1% most months, but once every few years loses 25% in a panic unwind.

The average return may look similar. The standard deviation may even look tolerable before the bad month arrives. But the second manager has a very different shape of risk. That shape is what [[Skewness]] is trying to describe.

Skewness answers:

> Are the extreme outcomes mostly on the upside or mostly on the downside?

## Plain-English Definition

Skewness measures the asymmetry of a distribution.

A symmetric distribution has balanced left and right tails. A skewed distribution has one tail that is longer or more extreme than the other.

For investments, skewness is about whether the surprise outcomes are mainly good surprises or bad surprises.

## CFA Definition

Skewness is the third standardized moment of a distribution:

$$
\text{Skewness} = E\left[\left(\frac{R - \mu}{\sigma}\right)^3\right]
$$

where:

| Symbol | Meaning |
|---|---|
| $R$ | Return |
| $\mu$ | Expected return or mean return |
| $\sigma$ | Standard deviation of returns |
| $E[\cdot]$ | Expected value |

The standardization by $\sigma$ makes skewness unitless. The cube is the key: cubing preserves the sign. Large positive deviations remain positive; large negative deviations remain negative.

## Why the Cube Matters

Variance squares deviations:

$$
(R - \mu)^2
$$

Squaring makes both positive and negative surprises positive. That is useful for measuring total dispersion, but it loses direction.

Skewness cubes deviations:

$$
(R - \mu)^3
$$

Cubing keeps direction:

| Return surprise | Squared term | Cubed term |
|---:|---:|---:|
| $+5$ | $+25$ | $+125$ |
| $-5$ | $+25$ | $-125$ |

So skewness tells you whether the extreme deviations lean positive or negative.

## Positive Skewness

Positive skewness means the right tail is longer or more extreme.

```text
Most outcomes: small losses or modest gains
Rare outcome: very large gain
Tail direction: right side
```

For a positively skewed distribution:

$$
\text{Mean} > \text{Median}
$$

Why? Because a few very large positive outcomes pull the average upward.

Examples:

- [[Long call]]
- [[Long put]] as crisis insurance
- Long straddle or long strangle
- Trend following / managed futures
- Venture-capital-style payoff profiles

The investor may lose a little many times, but one large winner can dominate the distribution.

## Negative Skewness

Negative skewness means the left tail is longer or more extreme.

```text
Most outcomes: small gains
Rare outcome: very large loss
Tail direction: left side
```

For a negatively skewed distribution:

$$
\text{Mean} < \text{Median}
$$

Why? Because a few very large negative outcomes pull the average downward.

Examples:

- [[FX carry trade]]
- Short put
- Short volatility
- [[Merger Arbitrage Payoff Structure]]
- Credit carry
- Levered relative-value trades

These strategies can look smooth for a long time, then suddenly take a large loss.

## Mean, Median, and Mode

The relationship between mean and median is one of the easiest exam handles.

| Distribution | Tail | Relationship |
|---|---|---|
| Symmetric | Balanced | Mean = median |
| Positively skewed | Long right tail | Mean > median |
| Negatively skewed | Long left tail | Mean < median |

Intuition:

- The median is the middle observation.
- The mean is pulled by extreme values.
- Therefore the mean gets dragged toward the long tail.

## Worked Example

Consider two six-month return histories.

| Month | Strategy A | Strategy B |
|---:|---:|---:|
| 1 | 1% | -1% |
| 2 | 1% | -1% |
| 3 | 1% | -1% |
| 4 | 1% | -1% |
| 5 | 1% | -1% |
| 6 | -10% | 10% |

Strategy A has many small gains and one large loss.

Its rough shape:

```text
Large left-tail loss + many small gains = negative skewness
```

Strategy B has many small losses and one large gain.

Its rough shape:

```text
Many small losses + large right-tail gain = positive skewness
```

Both strategies have an extreme observation, so both may have high [[kurtosis]]. But the direction of the extreme outcome is different. Skewness gives direction; kurtosis gives tail thickness.

## Skewness vs. Kurtosis

This distinction is exam gold.

| Concept | Measures | Question it answers |
|---|---|---|
| [[Skewness]] | Asymmetry | Which side has the larger tail? |
| [[Kurtosis]] | Tail thickness | Are extreme outcomes more common than normal? |
| [[Excess kurtosis]] | Kurtosis above normal | Are tails fatter than a normal distribution? |

Negative skewness plus excess kurtosis is the dangerous combination for many investment strategies:

```text
Negative skewness = bad surprises are on the left
Excess kurtosis = extreme surprises occur more often than normal
Together = left-tail crash risk
```

## Why Investors Care

Investors generally dislike negative skewness because losses hurt more than equivalent gains help. A strategy with negative skewness can look attractive in normal periods because it earns small steady returns. But the hidden risk is that a rare loss can erase years of gains.

This is why [[Sharpe ratio]] can mislead. Sharpe ratio uses standard deviation:

$$
\text{Sharpe ratio} = \frac{R_p - R_f}{\sigma_p}
$$

Standard deviation treats upside and downside volatility the same. But investors do not. A +20% surprise and a -20% surprise have very different consequences.

For skewed distributions, better tools include:

| Tool | Why it helps |
|---|---|
| [[Sortino ratio]] | Penalizes downside deviation, not upside volatility |
| [[Value at Risk]] | Focuses on left-tail loss threshold |
| [[Conditional VaR]] | Measures average loss after VaR is breached |
| Stress testing | Tests specific bad states |
| Drawdown analysis | Captures path-dependent pain |

## Trade Examples

| Strategy | Typical skewness | Why |
|---|---:|---|
| [[FX carry trade]] | Negative | Small carry income, rare crash when funding currency rallies |
| Short put | Negative | Premium income, large loss if underlying collapses |
| Covered call | Right tail capped | Upside sold away; downside remains |
| Protective put | Less negative / more positive | Left tail is truncated by insurance |
| Long call | Positive | Premium loss is limited; upside can be large |
| Long straddle | Positive convexity | Pays off if the market moves sharply either direction |
| [[Merger Arbitrage Payoff Structure]] | Negative | Deal spread gains, large loss if deal fails |
| Trend following | Often positive | Many small whipsaws, occasional large trend capture |

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Skewness measures fat tails" | No. Skewness measures asymmetry. Kurtosis measures fat tails. |
| "Negative skewness means most returns are negative" | Not necessarily. It often means many small gains and rare large losses. |
| "Positive skewness is always better" | Usually preferred, but it may come with premium drag or many small losses. |
| "Standard deviation captures skewness" | No. Standard deviation measures dispersion, not direction of tail risk. |
| "High Sharpe means low risk" | Not if returns have negative skewness and excess kurtosis. |
| "Carry trade has negative kurtosis" | Wrong. Carry trade has negative skewness and excess kurtosis. |

## Memory Hook

```text
Skew = side.
Kurtosis = tail thickness.

Negative skew: left-tail pain.
Positive skew: right-tail payoff.
```

## Exam-Day Checklist

When a vignette mentions skewness, ask:

- Is the long tail on the left or right?
- Are rare outcomes good or bad?
- Is the mean above or below the median?
- Is this a premium-collecting trade?
- Is the strategy short optionality or long optionality?
- Is the Sharpe ratio hiding left-tail risk?
- Does the question really mean kurtosis instead?

## Related Concepts

- [[Kurtosis]]
- [[Excess kurtosis]]
- [[Sample skewness]]
- [[Trade Return Distributions - Skewness and Kurtosis]]
- [[FX carry trade]]
- [[Carry Trades]]
- [[Merger Arbitrage Payoff Structure]]
- [[Value at Risk]]
- [[Conditional VaR]]
- [[Sortino ratio]]
