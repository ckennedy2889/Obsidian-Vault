---
title: Hedge Ratio
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - delta
  - hedging
  - binomial
aliases:
  - hedge ratio
  - option hedge ratio
  - delta hedge ratio
  - binomial hedge ratio
  - h ratio
---

# Hedge Ratio

## The Real-World Analogy

Imagine you run a bookstore and promise a customer, "If the price of this rare book rises next month, I will still sell it to you at today's price." You have effectively sold the customer an option. If the book price rises, you are exposed.

To hedge, you might buy some fraction of the rare book today. If the price rises, your book inventory gains value and offsets the promise you sold. The question is: **how much of the book should you hold per promise sold?**

That number is the hedge ratio.

In options, the hedge ratio tells you how many units of the [[Underlying|underlying asset]] are needed to offset the price risk of one option.

## The Big Idea

In CFA Level II Derivatives, the hedge ratio usually means the option's [[Delta|delta]].

Plain English:

> The hedge ratio is the amount of underlying asset needed to hedge one option.

For a call option, delta is positive because the call value rises when the underlying price rises. For a put option, delta is negative because the put value falls when the underlying price rises.

| Option | Delta / hedge ratio sign | Why |
|---|---:|---|
| Long call | Positive | Gains when underlying rises |
| Long put | Negative | Loses value when underlying rises |
| Short call | Negative option exposure | Loses when underlying rises |
| Short put | Positive option exposure | Loses when underlying falls |

The hedge trade takes the opposite side of your option delta exposure.

## Why CFA Tests This

CFA tests hedge ratio because it is the mechanical bridge between option pricing and no-arbitrage. If an option can be replicated by stock plus borrowing or lending, then the option's price cannot be arbitrary. If it is too high or too low, an arbitrageur can trade the option against the replicating portfolio.

The exam uses hedge ratio in three common ways:

1. Calculate the binomial hedge ratio.
2. Build the arbitrage trade when an option is overpriced or underpriced.
3. Interpret delta as the hedge ratio in [[Black-Scholes-Merton Model|BSM]] and [[Delta Hedging and Gamma Risk|dynamic hedging]].

## Binomial Hedge Ratio

In a one-period [[Binomial Option Pricing Model]], the stock can move to an up-state price $S^+$ or a down-state price $S^-$. The option has corresponding values $c^+$ and $c^-$ for a call, or $p^+$ and $p^-$ for a put.

For a call:

$$
h = \frac{c^+ - c^-}{S^+ - S^-}
$$

For a put:

$$
h = \frac{p^+ - p^-}{S^+ - S^-}
$$

This is just slope:

$$
\text{Hedge ratio}
= \frac{\text{change in option value}}{\text{change in underlying value}}
$$

That is why hedge ratio and delta are the same concept.

## Why the Formula Works

Suppose you are short one call and long $h$ shares of stock. The portfolio value at expiration is:

$$
V = hS - c
$$

For the hedge to be riskless, the up-state and down-state values must be equal:

$$
hS^+ - c^+ = hS^- - c^-
$$

Move terms around:

$$
hS^+ - hS^- = c^+ - c^-
$$

Factor out $h$:

$$
h(S^+ - S^-) = c^+ - c^-
$$

Solve:

$$
h = \frac{c^+ - c^-}{S^+ - S^-}
$$

The hedge ratio is the number of shares that makes the stock gain exactly offset the option loss across the two states.

## Worked Example

Assume:

- Current stock price: $S_0 = 30$.
- Up factor: $u = 1.333$.
- Down factor: $d = 0.75$.
- Strike price: $X = 30$.
- Risk-free rate: 7%.

Stock prices:

$$
S^+ = 30(1.333) \approx 40
$$

$$
S^- = 30(0.75) = 22.50
$$

Call payoffs:

$$
c^+ = \max(40 - 30,0) = 10
$$

$$
c^- = \max(22.50 - 30,0) = 0
$$

Hedge ratio:

$$
h = \frac{10 - 0}{40 - 22.50}
= \frac{10}{17.50}
= 0.5714
$$

This means one call option behaves like 0.5714 shares of stock in this one-period model.

If you sell 100 calls, you hedge by buying:

$$
100 \times 0.5714 = 57.14 \text{ shares}
$$

## Arbitrage: Option Overpriced vs Underpriced

The hedge ratio tells you the stock position in the replicating portfolio. Then the arbitrage direction depends on whether the market option price is too high or too low.

| Market condition | Trade | Why |
|---|---|---|
| Option overpriced | Sell option, buy replicating portfolio | You sell the expensive thing and buy the cheaper equivalent |
| Option underpriced | Buy option, short replicating portfolio | You buy the cheap thing and sell the expensive equivalent |

For a call, the replicating portfolio is:

```text
Long h shares
Borrow/lend the balancing amount
```

If the call is overpriced, sell the call and buy $h$ shares per call. If the call is underpriced, buy the call and short $h$ shares per call.

## Delta Hedging Interpretation

In the [[Black-Scholes-Merton Model]], the call hedge ratio is:

$$
\Delta_{\text{call}} = N(d_1)
$$

For a non-dividend-paying stock, put-call parity gives:

$$
\Delta_{\text{put}} = N(d_1) - 1
$$

For a stock with a continuous dividend yield $\delta$, the deltas are adjusted by the dividend discount factor:

$$
\Delta_{\text{call}} = e^{-\delta T}N(d_1)
$$

$$
\Delta_{\text{put}} = -e^{-\delta T}N(-d_1)
$$

This means:

- A call delta of 0.60 means one call behaves like 0.60 shares.
- A put delta of -0.40 means one put behaves like short 0.40 shares.

To create a delta-neutral hedge:

$$
\text{Share hedge} = -(\text{option position delta})
$$

More generally, if you hedge one instrument with another hedging instrument:

$$
N_H = -\frac{\text{Portfolio delta}}{\Delta_H}
$$

where $N_H$ is the number of hedging instruments and $\Delta_H$ is the delta of the hedging instrument. If the hedge instrument is the underlying stock, $\Delta_H = 1$.

Example: if you are short 10,000 calls and each call has delta 0.60, your option position delta is:

$$
-10{,}000(0.60) = -6{,}000
$$

To neutralize it, buy 6,000 shares.

## Dynamic Hedging and Gamma

The hedge ratio is not fixed. As the underlying price, time to expiration, volatility, and rates change, delta changes.

That is why delta hedging is dynamic:

```text
Underlying price moves
  |
  v
Delta changes
  |
  v
Hedge ratio becomes stale
  |
  v
Hedger rebalances shares
```

[[Gamma]] measures how fast delta changes as the underlying price changes. High gamma means the hedge ratio moves quickly, so the hedge needs frequent rebalancing.

This is the failure mode CFA likes: a delta hedge protects against small, immediate price moves. It does not perfectly protect against large moves, jumps, transaction costs, or stale rebalancing.

## Do Not Confuse It With Minimum-Variance Hedge Ratio

The phrase "hedge ratio" can also appear in futures and cross-hedging.

| Context | Hedge ratio means | Formula idea |
|---|---|---|
| Options / binomial / BSM | Delta: underlying units per option | $h = \frac{\Delta option}{\Delta underlying}$ |
| Futures cross-hedging | Futures exposure needed to minimize variance | $h^* = \rho \frac{\sigma_S}{\sigma_F}$ |
| Fixed-income futures hedging | Contracts needed to hedge duration/PVBP exposure | Match portfolio PVBP to futures PVBP |

For Level II option questions, assume "hedge ratio" means delta unless the question explicitly gives futures hedge variables, correlation, duration, or PVBP.

## Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating hedge ratio as a probability | Confuses delta with risk-neutral probability | Hedge ratio is slope; probability is $\pi$ |
| Reversing the arbitrage trade | Buys overpriced option or sells underpriced option | Sell expensive side, buy cheap equivalent |
| Forgetting scale | Calculates $h$ for one option but ignores number of contracts | Multiply by number of options |
| Missing put sign | Treats put hedge ratio as positive | Put delta is usually negative |
| Thinking delta hedge is permanent | Ignores gamma | Rebalance as delta changes |
| Mixing option hedge ratio with futures minimum-variance hedge ratio | Uses wrong formula family | Identify the instrument first |

## Memory Hooks

**Hedge ratio is slope.** Option change divided by stock change.

**Delta is the hedge ratio.** If one call has delta 0.60, it behaves like 0.60 shares.

**Sell expensive, buy cheap.** If the option is overpriced, sell it and buy the replicating portfolio.

## Related Concepts

- [[Delta]]
- [[Delta Hedging and Gamma Risk]]
- [[Gamma]]
- [[Binomial Option Pricing Model]]
- [[Black-Scholes-Merton Model]]
- [[Option Greeks]]
- [[Minimum-variance hedge ratio]]
