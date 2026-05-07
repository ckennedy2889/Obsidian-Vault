---
title: "Momentum Indicators in Equity Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, market-based-valuation, momentum]
aliases: ["Momentum indicators", "Earnings surprise", "Standardized unexpected earnings", "SUE", "Relative strength"]
---

# Momentum Indicators in Equity Valuation

[[Momentum indicators]] ask whether recent price or earnings information is continuing to push a stock in the same direction.

Most valuation tools are anchored on levels: P/E, P/B, EV/EBITDA, intrinsic value, book value, and cash flow. Momentum indicators are different. They look at changes and surprises. For Apple, a valuation analyst might ask: Is Apple's price strength continuing? Did reported EPS beat expectations? Is Apple outperforming Microsoft and Nvidia over the same window? These questions do not replace valuation, but they help explain market behavior around valuation.

In plain English:

```text
Momentum indicators compare price or fundamentals with their own past values or expected values.
```

## The Three CFA Momentum Indicators

CFA emphasizes three common momentum measures:

| Indicator | What it measures | Basic idea |
|---|---|---|
| [[Earnings surprise]] | Reported EPS versus expected EPS | Positive surprises may lead to continued abnormal returns |
| [[Standardized Unexpected Earnings]] (SUE) | Earnings surprise scaled by surprise volatility | Standardization makes surprises more comparable |
| [[Relative strength]] | Stock return versus peers or benchmark | Recent winners may continue outperforming |

## Earnings Surprise

Unexpected earnings, or earnings surprise, is:

$$
\text{Earnings Surprise} =
\text{Reported EPS} - \text{Expected EPS}
$$

If Apple reports quarterly EPS of $\$1.65$ when analysts expected $\$1.55$, the surprise is:

$$
\text{Earnings Surprise} =
1.65 - 1.55
= 0.10
$$

That is a positive surprise. The economic intuition is that analysts and investors may underreact to new information. If the surprise reveals stronger demand, better margins, or more durable earnings power, the stock may continue to adjust after the announcement.

## Standardized Unexpected Earnings

The problem with raw earnings surprise is scale. A $\$0.10$ surprise is large for a company that usually surprises by $\$0.02$, but small for a company that routinely surprises by $\$0.50$.

SUE scales the surprise:

$$
\text{SUE} =
\frac{\text{Reported EPS} - \text{Expected EPS}}
{\sigma(\text{Earnings Surprises})}
$$

where $\sigma(\text{Earnings Surprises})$ is the historical standard deviation of surprises.

Suppose Apple reports a $\$0.10$ EPS surprise and its historical standard deviation of EPS surprises is $\$0.04$:

$$
\text{SUE} =
\frac{0.10}{0.04}
= 2.50
$$

That means the surprise is 2.5 standard deviations above normal. A high positive SUE is stronger evidence of earnings momentum than the raw $\$0.10$ number alone.

## Relative Strength

Relative strength compares a stock's return with another stock, peer group, or benchmark:

$$
\text{Relative Strength} =
R_{\text{stock}} - R_{\text{benchmark}}
$$

If Apple rises 12% and the benchmark rises 7%, relative strength is:

$$
12\% - 7\% = 5\%
$$

The signal is positive because Apple outperformed.

## Apple Peer Example

Use recent monthly price data for Apple, Microsoft, and Nvidia.

| Company | Earlier close | Recent/current price | Approx. return |
|---|---:|---:|---:|
| Apple | $\$200.85$ | $\$287.70$ | 43.2% |
| Microsoft | $\$460.36$ | $\$413.77$ | -10.1% |
| Nvidia | $\$135.13$ | $\$207.10$ | 53.3% |

Apple's one-year price momentum was strongly positive:

$$
R_{\text{AAPL}} =
\frac{287.70}{200.85} - 1
= 43.2\%
$$

Relative to Microsoft:

$$
\text{Relative Strength}_{\text{AAPL vs MSFT}} =
43.2\% - (-10.1\%)
= 53.3\%
$$

Relative to Nvidia:

$$
\text{Relative Strength}_{\text{AAPL vs NVDA}} =
43.2\% - 53.3\%
= -10.1\%
$$

This shows why the benchmark matters. Apple had positive absolute momentum and strong relative strength versus Microsoft, but it underperformed Nvidia over the same window.

## How Momentum Fits With Valuation

Momentum does not tell you intrinsic value. It tells you about direction and information flow.

| Valuation question | Momentum contribution |
|---|---|
| Is the stock cheap or expensive? | Momentum does not answer directly |
| Are expectations being revised upward? | Earnings surprise and SUE help |
| Is the market rewarding the stock relative to peers? | Relative strength helps |
| Could a high multiple persist? | Positive momentum can explain near-term persistence |
| Is the stock vulnerable despite looking cheap? | Negative momentum may warn of deteriorating fundamentals |

For Apple, a high [[P/E Ratio]] plus positive relative momentum can mean the market is becoming more optimistic. But the analyst still needs to ask whether fundamentals justify the price. Momentum can support a thesis; it should not replace a thesis.

## Assumptions

Momentum indicators assume that markets may underreact or that trends can persist over short to intermediate horizons.

That assumption can fail. Prices can reverse, earnings surprises can be one-time events, and relative strength can be driven by sentiment rather than durable fundamentals.

| Momentum signal | Assumption | Failure mode |
|---|---|---|
| Positive earnings surprise | New information has not been fully priced | Surprise is temporary or low quality |
| High SUE | Surprise is large relative to normal variation | Historical surprise volatility is not representative |
| Strong relative strength | Outperformance may continue | Reversal after overreaction |

## Exam Traps

The first trap is treating momentum as intrinsic valuation. A positive momentum signal does not prove a stock is undervalued. It may simply mean the stock has been going up.

The second trap is ignoring the benchmark. "Relative strength" must be relative to something. Apple can outperform Microsoft and underperform Nvidia at the same time.

The third trap is forgetting to standardize surprises. A large raw surprise is not necessarily a large standardized surprise.

Finally, be careful with signs. A reported EPS below expected EPS is a negative surprise:

$$
\text{Reported EPS} - \text{Expected EPS} < 0
$$

That is negative earnings momentum, even if the company remained profitable.

## Memory Hook

> [!tip] Memory Hook
> Valuation asks, "What is it worth?" Momentum asks, "What direction is new information pushing it?"

## Related Concepts

- [[Market-Based Valuation]]
- [[Earnings surprise]]
- [[Unexpected earnings]]
- [[Scaled earnings surprise]]
- [[Relative Strength]]
- [[PEG Ratio]]
- [[Price-to-Earnings Ratio]]
