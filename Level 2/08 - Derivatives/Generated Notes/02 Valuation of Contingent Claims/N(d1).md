---
title: N(d1)
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - BSM
  - delta
  - hedge-ratio
aliases:
  - N(d1)
  - N(d_1)
  - Nd1
  - BSM N(d1)
  - d1
---

# N(d1)

## The Real-World Analogy

Think of a call option as a levered stock position. It is not the same as owning one full share, because the option only participates meaningfully when the stock is high enough. But it is also not just a lottery ticket, because before expiration its value moves with the stock.

`N(d1)` answers the practical hedger's question:

> If I own one call option, how much stock exposure do I effectively have right now?

If `N(d1) = 0.62`, one call behaves like owning about 0.62 shares for a small stock-price move.

## The Big Idea

In the [[Black-Scholes-Merton Model]], `N(d1)` is the call option's [[Delta|delta]]:

$$
\Delta_{\text{call}} = N(d_1)
$$

For a non-dividend-paying stock, it is also the number of shares in the call's replicating portfolio.

The European call formula is:

$$
c = S N(d_1) - Xe^{-rT}N(d_2)
$$

Read it as:

```text
Call value
= stock-like component
- borrowed bond component
```

The stock-like component is:

$$
S N(d_1)
$$

That is why CFA says a call can be viewed as a leveraged stock investment where `N(d1)` shares are purchased using borrowed funds.

## Formula

For a non-dividend-paying stock:

$$
d_1 =
\frac{\ln(S/X) + \left(r + \frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

$$
N(d_1) = \text{standard normal CDF evaluated at } d_1
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Current stock price |
| $X$ | Strike price |
| $r$ | Continuously compounded risk-free rate |
| $\sigma$ | Annual volatility |
| $T$ | Time to expiration |
| $N(\cdot)$ | Standard normal cumulative distribution function |

For a dividend-paying stock with continuous dividend yield $\delta$:

$$
d_1 =
\frac{\ln(S/X) + \left(r-\delta + \frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

and the call delta becomes:

$$
\Delta_{\text{call}} = e^{-\delta T}N(d_1)
$$

## Why `N(d1)` Is Delta

Delta is the slope of the option price with respect to the underlying stock price:

$$
\Delta = \frac{\partial c}{\partial S}
$$

In BSM, differentiating the call formula with respect to $S$ gives:

$$
\Delta_{\text{call}} = N(d_1)
$$

The intuition is cleaner than the calculus: a call option is replicated by buying stock and borrowing. The amount of stock needed in the replicating portfolio is the hedge ratio. BSM says that hedge ratio is `N(d1)`.

So:

```text
N(d1)
  |
  v
Call delta
  |
  v
Shares needed to replicate one call
  |
  v
Small-move stock exposure of the call
```

## What `d1` Measures

`d1` is a standardized measure of how far the stock's current forward-adjusted position is from the strike, with volatility and time used as the scale.

The numerator:

$$
\ln(S/X) + \left(r + \frac{1}{2}\sigma^2\right)T
$$

combines:

- Current moneyness: $\ln(S/X)$.
- Risk-free growth: $rT$.
- Volatility adjustment: $\frac{1}{2}\sigma^2T$.

The denominator:

$$
\sigma\sqrt{T}
$$

is the standard deviation of log return over the option's life.

So `d1` says:

> How many volatility-standard-deviation units is the stock's adjusted position above or below the strike?

## Why `N(d1)` Is Not the Probability of Exercise

The probability-style term in BSM is `N(d2)`, not `N(d1)`.

`N(d1)` is higher than the exercise probability because it is not merely asking, "Will the call finish in the money?" It is asking, "How much stock exposure does this option have today?"

When the call finishes in the money, the stock price in those successful states can be far above the strike. The call's stock-like exposure reflects not just the chance of success but the stock-weighted value of success.

That extra stock-weighting is why:

$$
d_1 = d_2 + \sigma\sqrt{T}
$$

and therefore:

$$
N(d_1) > N(d_2)
$$

for any option with positive volatility and time to expiration.

## Worked Example

Assume:

- $S = 100$.
- $X = 100$.
- $r = 5\%$ continuously compounded.
- $\sigma = 30\%$.
- $T = 1$ year.

Compute:

$$
d_1 =
\frac{\ln(100/100) + (0.05 + 0.30^2/2)(1)}
{0.30\sqrt{1}}
$$

$$
d_1 =
\frac{0 + 0.05 + 0.045}{0.30}
= \frac{0.095}{0.30}
= 0.3167
$$

Look up the cumulative normal value:

$$
N(d_1)=N(0.3167)\approx 0.624
$$

Interpretation:

- One call behaves like 0.624 shares for a small stock move.
- A market maker short 10,000 calls would buy about 6,240 shares to delta hedge.
- The call's stock component in the BSM formula is:

$$
S N(d_1)=100(0.624)=62.40
$$

This does **not** mean there is a 62.4% chance of exercise. In this same example, `N(d2)` is about 0.507, which is the risk-neutral exercise probability.

## Dividend and Currency Carry Adjustments

For assets with carry benefits, the stock-like component is reduced by the present value of the carry benefit.

Dividend-paying stock:

$$
c = S e^{-\delta T}N(d_1)-Xe^{-rT}N(d_2)
$$

Call delta:

$$
\Delta_{\text{call}}=e^{-\delta T}N(d_1)
$$

Currency option:

$$
c = S e^{-r_fT}N(d_1)-Xe^{-r_dT}N(d_2)
$$

Currency call delta with respect to the spot exchange rate:

$$
\Delta_{\text{call}}=e^{-r_fT}N(d_1)
$$

The carry yield lowers effective exposure because holding the underlying directly includes cash-flow benefits that the option holder does not receive in the same way.

## Connection to `N(d2)`

| Term | Meaning | In the call formula |
|---|---|---|
| `N(d1)` | Delta / stock exposure / hedge ratio | Multiplies $S$ |
| `N(d2)` | Risk-neutral probability of exercise | Multiplies $PV(X)$ |

Memory version:

```text
N(d1): how much stock?
N(d2): how likely exercise?
```

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| `N(d1)` is the probability the call expires ITM | False. That is `N(d2)`. |
| `N(d1)` equals call delta even with dividends | Need dividend adjustment: $e^{-\delta T}N(d_1)$. |
| `N(d1)` and `N(d2)` are interchangeable | False. They multiply different pieces of the BSM formula. |
| Higher `N(d1)` always means higher option value by itself | Usually, but option value also depends on $S$, $X$, rates, volatility, and time. |
| Delta hedge is permanent | False. Delta changes as stock price, time, and volatility change. |

## Memory Hooks

**`d1` is for delta.**

**`N(d1)` tells you how much stock is hiding inside the option.**

**`N(d2)` is the probability-style term; `N(d1)` is the hedge-ratio term.**

## Related Concepts

- [[N(d2)]]
- [[Black-Scholes-Merton Model]]
- [[Option Greeks]]
- [[Delta Hedging and Gamma Risk]]
- [[Hedge Ratio]]
- [[Risk-Neutral Probabilities]]

