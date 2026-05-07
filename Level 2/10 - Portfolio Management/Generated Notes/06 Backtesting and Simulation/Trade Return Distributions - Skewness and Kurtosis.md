---
title: Trade Return Distributions - Skewness and Kurtosis
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, risk-management, skewness, kurtosis, derivatives, alternatives]
aliases: [Trade return distributions, Strategy return distributions, Skewness and kurtosis in trading, Fat-tail trade profiles]
---

# Trade Return Distributions - Skewness and Kurtosis

## Real-World Analogy

Think of every trade as a machine that converts market states into returns.

Some machines are boring most of the time but occasionally explode. That is the classic [[carry trade]], [[short put]], [[merger arbitrage]], or short-volatility profile: small steady gains, rare large losses. The distribution usually has [[negative skewness]] and [[excess kurtosis]].

Other machines bleed small amounts most of the time but occasionally produce a huge win. That is the classic long-option, long-volatility, crisis-alpha, or trend-following profile: many small losses or modest returns, rare large gains. The distribution usually has [[positive skewness]] and fat tails.

The exam point is that the average return and standard deviation are not enough. Two strategies can have the same mean and volatility but radically different tail risk.

## The Statistics First

### Mean and Variance Are Not Enough

The normal distribution is fully described by:

$$
\mu = E(R)
$$

and:

$$
\sigma^2 = E[(R - \mu)^2]
$$

But most real investment strategies are not normal. They can be asymmetric, fat-tailed, path-dependent, levered, or option-like. That means you also need [[skewness]] and [[kurtosis]].

### Skewness

Skewness measures asymmetry:

$$
\text{Skewness} = E\left[\left(\frac{R - \mu}{\sigma}\right)^3\right]
$$

| Type | Shape | Interpretation | Typical trade profile |
|---|---|---|---|
| Positive skewness | Long right tail | Rare very large gains | Long calls, long puts, long straddles, trend following |
| Negative skewness | Long left tail | Rare very large losses | Carry trades, short puts, merger arbitrage, credit carry |
| Near-zero skewness | Symmetric | Upside and downside tails roughly balanced | Linear diversified exposure, many market-neutral portfolios before stress |

The cube matters. Cubing preserves the sign, so extreme positive returns pull skewness up and extreme negative returns pull skewness down.

### Kurtosis

Kurtosis measures tail heaviness:

$$
\text{Kurtosis} = E\left[\left(\frac{R - \mu}{\sigma}\right)^4\right]
$$

The normal distribution has kurtosis of 3. CFA often focuses on excess kurtosis:

$$
\text{Excess kurtosis} = \text{Kurtosis} - 3
$$

| Type | Meaning | Interpretation |
|---|---|---|
| Mesokurtic | Kurtosis = 3 | Normal-like tails |
| Leptokurtic | Kurtosis > 3 | Fat tails; more extreme outcomes than normal |
| Platykurtic | Kurtosis < 3 | Thin tails; fewer extremes than normal |

Kurtosis does not tell you direction. A strategy can have fat upside tails, fat downside tails, or both. That is why CFA often pairs the words:

```text
Negative skewness + excess kurtosis = nasty left-tail crash risk
Positive skewness + excess kurtosis = lottery-like upside convexity
```

## The Big Distribution Map

| Trade / strategy | Typical skewness | Typical kurtosis | Return pattern | Core risk |
|---|---:|---:|---|---|
| [[FX carry trade]] | Negative | Excess | Small gains, occasional crash | Funding currency rallies / risk-off unwind |
| Short put | Negative | Excess | Premium income, rare large loss | Underlying collapses |
| Short call | Negative for short option seller | Excess | Premium income, potentially unlimited loss | Underlying rallies sharply |
| Covered call | Less upside, still downside | Often non-normal | Premium income with capped gains | Gives away right tail |
| Protective put | Positive / less negative | Option-driven | Downside floor, upside retained | Premium drag |
| Long call | Positive | Excess | Small premium loss, rare large gain | Needs large upside move |
| Long put | Positive in crisis states | Excess | Insurance payoff in selloff | Premium drag / timing |
| Long straddle / strangle | Positive convexity | Excess | Loses premium unless big move occurs | Realized vol too low |
| Short straddle / strangle | Negative | Excess | Steady premium, crash loss | Volatility spike / gap move |
| [[Merger arbitrage]] | Negative | Excess | Small deal spread gains, rare deal-break loss | Event risk |
| Credit carry / selling credit protection | Negative | Excess | Coupon/spread income, default shock | Spread widening / default cluster |
| Fixed-income relative value | Usually negative in stress | Excess | Small arbitrage gains, rare liquidity loss | Leverage + convergence failure |
| Trend following / managed futures | Positive in stress | Excess | Whipsaw losses, crisis winners | Trend reversals |
| Global macro | Often positive in stress but heterogeneous | Excess | Lumpy gains/losses | Bad macro timing / leverage |
| Equity long-only | Often negative | Excess | Equity risk premium with crash risk | Market drawdown |
| Market neutral | Near-zero in calm periods, negative in stress | Excess | Smooth until correlations break | Crowding / deleveraging |

## Short Volatility: The Classic Negative-Skew Trade

Short-volatility trades get paid for accepting other investors' fear. You collect premium or yield during normal times, but you are exposed to a jump event.

The trade usually looks good in ordinary data:

```text
Month 1: +0.8%
Month 2: +1.0%
Month 3: +0.7%
Month 4: +0.9%
Month 5: -12.0%
```

The average may still be positive, and the Sharpe ratio may look fine before the crash appears. But the distribution has a long left tail.

### Short Put

A short put earns the premium if the underlying stays above the strike. The maximum gain is limited to the premium, but the loss can be very large if the underlying falls.

Payoff at expiration:

$$
\text{Short put payoff} = -\max(K - S_T, 0)
$$

Profit:

$$
\text{Short put profit} = \text{premium received} - \max(K - S_T, 0)
$$

This creates:

- capped upside;
- large downside;
- negative skewness;
- excess kurtosis if crashes are rare but severe.

### Short Straddle

A short straddle sells a call and a put at the same strike:

$$
\text{Short straddle payoff} = -\max(S_T - K, 0) - \max(K - S_T, 0)
$$

The seller earns premium if the underlying stays near the strike. But a large move either direction creates a large loss.

This is not just negative skewness. It can have fat tails on both sides of the underlying move. From the trader's return perspective, both tails are bad because either a sharp rally or sharp selloff hurts the short straddle.

## Long Volatility: Positive Convexity and Right-Skew

Long-volatility trades pay premium to own convexity. They often lose small amounts repeatedly, then make a large gain when the market moves sharply.

### Long Call

A long call has limited loss and large upside:

$$
\text{Long call profit} = \max(S_T - K, 0) - C_0
$$

where $C_0$ is the premium paid.

The most you can lose is the premium. The upside can be very large. That is positive skewness.

### Long Put

A long put has limited loss and large payoff when the underlying falls:

$$
\text{Long put profit} = \max(K - S_T, 0) - P_0
$$

For a portfolio, long puts reduce left-tail risk. They transform a long-equity distribution from:

```text
Full downside + full upside
```

into:

```text
Limited downside + full upside - insurance premium
```

That is why a [[protective put]] is portfolio insurance.

## Covered Calls: Income Today, Right Tail Sold Away

A covered call is:

```text
Long stock + short call
```

It earns option premium, which cushions small losses and boosts returns in flat markets. But it caps the upside because the short call gives away gains above the strike.

The distribution changes like this:

| Feature | Long stock | Covered call |
|---|---:|---:|
| Upside | Unlimited | Capped |
| Downside | Large | Large, slightly cushioned by premium |
| Income | Dividend only | Dividend plus option premium |
| Skew effect | Equity often has negative skew | Right tail truncated; left tail remains |

This is an exam trap. A covered call is not strong downside protection. It is yield enhancement with capped upside.

## Protective Puts: Buying the Left-Tail Floor

A protective put is:

```text
Long stock + long put
```

It creates a floor:

$$
\text{Minimum terminal value} \approx K - P_0
$$

The put truncates the left tail. You pay a premium, so expected return may fall in ordinary markets, but crash risk is reduced.

The return profile becomes more convex:

- small premium drag in normal markets;
- large benefit in crashes;
- upside retained.

## Carry Trades: Negative Skewness Plus Excess Kurtosis

The [[FX carry trade]] borrows in a low-yielding funding currency and invests in a high-yielding investment currency.

Approximate profit:

$$
\text{Carry profit} \approx \text{interest differential} - \text{depreciation of investment currency}
$$

The trade works when [[uncovered interest rate parity]] fails in the short run. If the high-yield currency does not depreciate enough to offset the interest differential, the carry trader profits.

But carry has a dangerous distribution:

| Feature | Why it happens |
|---|---|
| Many small gains | Interest differential accrues steadily |
| Negative skewness | Funding currency can rally sharply in risk-off periods |
| Excess kurtosis | Unwinds are clustered and extreme |
| Crash risk | Leverage and crowded exits amplify losses |

The key CFA line: carry trade returns generally have **negative skewness and excess kurtosis**.

If a vignette says "negative kurtosis and excess skewness," that is wrong. The correct description is negative skewness and excess kurtosis.

## Merger Arbitrage: Insurance-Like Left-Tail Risk

Merger arbitrage often earns the deal spread if a merger closes. The manager typically buys the target and, in stock deals, may short the acquirer.

The return pattern resembles selling insurance:

```text
Deal closes: earn small spread
Deal fails: lose a lot as target price falls back
```

That creates:

- steady small positive returns;
- high apparent Sharpe ratio in calm periods;
- significant left-tail risk;
- negative skewness;
- excess kurtosis.

The source of non-normality is event risk. One failed deal can wipe out many successful spread captures.

## Credit Carry and Selling Protection

Credit strategies that earn spread income often look like short-put strategies on credit markets.

Examples:

- buying high-yield bonds for extra spread;
- selling credit default swap protection;
- levered loans or structured credit carry;
- fixed-income arbitrage that is long less-liquid spread assets and short safer/liquid instruments.

The normal state is coupon/spread collection. The crash state is spread widening, default clustering, liquidity disappearing, or funding drying up.

That produces:

```text
Small positive carry most periods
Rare large negative drawdowns during credit stress
```

So the distribution is usually negatively skewed and leptokurtic.

## Trend Following and Managed Futures: Right-Skew in Stress

Trend following is different. It tends to cut losers and ride winners. A managed futures program can go long assets trending up and short assets trending down across equities, bonds, currencies, and commodities.

In choppy markets, the strategy may get whipsawed:

```text
Small loss, small loss, small gain, small loss
```

But in a crisis with persistent trends, it can make large gains:

```text
Long bonds, short equities, long USD, short commodities
```

That gives many managed futures strategies positive skewness, especially during market stress.

CFA contrast:

| Strategy | Stress-period skew |
|---|---|
| Carry trade | Negative |
| Merger arbitrage | Negative |
| Credit carry | Negative |
| Managed futures / trend following | Often positive |
| Global macro | Can be positive, but more heterogeneous |

## Market Neutral and Relative Value: Calm Until Correlations Break

Market-neutral and relative-value trades try to remove broad market beta and profit from relative mispricing.

In calm markets, the return distribution may look stable:

```text
Small gains from convergence
Low beta
Low volatility
```

But many relative-value trades rely on leverage and stable correlations. During stress, relationships that looked reliable can break down. Liquidity disappears, financing terms tighten, and everyone may try to exit the same trade at once.

That creates hidden kurtosis:

- ordinary volatility looks low;
- tail losses are larger than expected;
- correlations jump exactly when diversification is needed.

This is why a "low volatility" strategy can still be dangerous.

## Worked Mini Example: Same Mean, Different Tail Risk

Suppose two strategies each have an average monthly return near 1%.

| Month | Strategy A: carry-like | Strategy B: trend-like |
|---:|---:|---:|
| 1 | 1.0% | -0.5% |
| 2 | 0.8% | -0.4% |
| 3 | 1.1% | -0.6% |
| 4 | 0.9% | 0.2% |
| 5 | 1.2% | -0.3% |
| 6 | -8.0% | 8.0% |

Strategy A has five small gains and one large loss. That is negative skewness.

Strategy B has several small losses and one large gain. That is positive skewness.

Both have a large outlier, so both can show excess kurtosis. But the direction of the important tail is different.

That is the whole reason skewness and kurtosis must be read together.

## Why Sharpe Ratio Can Mislead

The [[Sharpe ratio]] uses mean return divided by standard deviation:

$$
\text{Sharpe ratio} = \frac{R_p - R_f}{\sigma_p}
$$

The problem is that standard deviation treats upside and downside volatility symmetrically. A strategy with many small gains and rare crashes may show a strong Sharpe ratio until the crash arrives.

For non-normal strategies, consider:

| Measure | Better for |
|---|---|
| [[Sortino ratio]] | Downside deviation |
| [[Value at Risk]] | Quantile loss threshold |
| [[Conditional VaR]] | Average loss beyond VaR |
| Maximum drawdown | Path-dependent investor pain |
| Stress testing | Scenario tail risk |
| Skewness and kurtosis | Distribution shape |

## Exam Traps

| Trap | Correct CFA interpretation |
|---|---|
| "High Sharpe means safe" | Not if the strategy has negative skewness and excess kurtosis |
| "Kurtosis tells direction" | No. Kurtosis tells tail thickness; skewness tells direction |
| "Covered calls protect downside" | Only slightly through premium; they mainly cap upside |
| "Carry trade has negative kurtosis" | Wrong. Carry has negative skewness and excess kurtosis |
| "Market neutral means no tail risk" | Wrong. Crowding, leverage, and liquidity can create fat tails |
| "Long options are always bad because premium drag" | They can be valuable because they add convexity and crisis payoff |
| "Normal VaR is enough" | Normal VaR ignores skewness, excess kurtosis, and tail dependence |

## Memory Hook

```text
Short optionality = pays often, crashes rarely.
Long optionality = bleeds often, wins rarely.

Skew says which side the dangerous tail is on.
Kurtosis says how often extreme outcomes show up.
```

## Exam-Day Checklist

When CFA asks about a trade's distribution, identify:

- Is the trade long or short optionality?
- Are gains capped or losses capped?
- Does the trade collect carry/premium most of the time?
- What happens in a volatility spike?
- Is the dangerous tail left or right?
- Does leverage turn a small spread into crash risk?
- Are reported returns smoothed by illiquidity or stale pricing?
- Would Sharpe ratio understate the true risk?
- Should you use Sortino, CVaR, drawdown, stress tests, or skew/kurtosis?

## Related Concepts

- [[Skewness]]
- [[Kurtosis]]
- [[Excess kurtosis]]
- [[FX carry trade]]
- [[Carry Trades]]
- [[Merger Arbitrage Payoff Structure]]
- [[Backtesting and Simulation]]
- [[Measuring and Managing Market Risk]]
- [[Value at Risk]]
- [[Conditional VaR]]
- [[Sortino ratio]]
- [[Covered call]]
- [[Protective put]]
- [[Short put]]
- [[Trend following]]
