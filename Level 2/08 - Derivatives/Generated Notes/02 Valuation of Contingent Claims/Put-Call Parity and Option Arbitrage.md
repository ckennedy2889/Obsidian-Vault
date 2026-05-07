---
title: Put-Call Parity and Option Arbitrage
subject: Derivatives
tags: [CFA-L2, derivatives, options, put-call-parity, arbitrage]
aliases: [Put-call parity, Fiduciary call, Protective put, Put-call-forward parity, Synthetic option positions]
---

# Put-Call Parity and Option Arbitrage

## The Real-World Analogy

[[Put-call parity]] is the options version of saying two different recipes produce the same finished meal. If two portfolios have exactly the same payoff at expiration in every possible stock-price state, they must have the same price today. If one recipe is cheaper, arbitrageurs buy the cheap one and sell the expensive one.

The two portfolios are a fiduciary call and a protective put.

## The Big Idea

For European options on the same underlying, with the same strike price and expiration:

| Portfolio | Components |
|---|---|
| Fiduciary call | Long call + risk-free bond that pays the strike $X$ at expiration |
| Protective put | Long stock + long put |

At expiration, both are worth:

$$
\max(S_T, X)
$$

Therefore, they must have the same value today.

## Why The Payoffs Match

| Expiration state | Fiduciary call: $c + PV(X)$ | Protective put: $S + p$ |
|---|---|---|
| $S_T > X$ | Call is exercised using bond proceeds; portfolio owns stock worth $S_T$ | Put expires worthless; stock is worth $S_T$ |
| $S_T < X$ | Call expires worthless; bond pays $X$ | Put is exercised; stock is sold for $X$ |

Same payoff in every state means same price today. This is no-arbitrage logic, not a probability forecast.

## Non-Dividend Put-Call Parity

For a non-dividend-paying stock:

$$
S_0 + p_0 = c_0 + \frac{X}{(1+r)^T}
$$

With continuous compounding:

$$
S_0 + p_0 = c_0 + Xe^{-rT}
$$

Rearranged:

$$
c_0 - p_0 = S_0 - PV(X)
$$

This says a long call plus short put equals a leveraged long stock position, which is also a synthetic [[Forward contract|forward]].

## Dividend-Paying Stock

If the stock pays known dividends before option expiration, the stock side must be adjusted because the stock owner receives dividends and option holders do not.

$$
S_0 - PV(Div) + p_0 = c_0 + PV(X)
$$

An equivalent put-call-forward parity expression is:

$$
PV(F_0) + p_0 = c_0 + PV(X)
$$

where $F_0$ is the forward price that already embeds dividends and carry costs.

## Synthetic Positions

Starting from:

$$
S_0 + p_0 = c_0 + PV(X)
$$

you can solve for any component:

| Desired synthetic | Formula | Trade |
|---|---|---|
| Synthetic long stock | $S_0 = c_0 - p_0 + PV(X)$ | Buy call, write put, lend PV(X) |
| Synthetic long call | $c_0 = S_0 + p_0 - PV(X)$ | Buy stock, buy put, borrow PV(X) |
| Synthetic long put | $p_0 = c_0 + PV(X) - S_0$ | Buy call, lend PV(X), short stock |
| Synthetic risk-free bond | $PV(X)=S_0+p_0-c_0$ | Buy stock, buy put, write call |
| Synthetic long forward | $c_0-p_0=S_0-PV(X)$ | Buy call, write put |

The signs matter. A minus sign means short or borrow; a plus sign means long or lend.

## Identifying Arbitrage

When parity is violated, use one rule:

```text
Buy the cheap side. Sell the expensive side.
```

If:

$$
S_0 + p_0 > c_0 + PV(X)
$$

then the protective put is expensive. Sell stock, write put, buy call, and lend PV(X).

If:

$$
S_0 + p_0 < c_0 + PV(X)
$$

then the fiduciary call is expensive. Buy stock, buy put, write call, and borrow PV(X).

At expiration, the offsetting portfolios cancel. The arbitrage profit is locked in at initiation.

## Worked Numerical Example

Assume European options on a non-dividend-paying stock:

| Input | Value |
|---|---:|
| Stock price, $S_0$ | $50.00 |
| Strike, $X$ | $50.00 |
| Call premium, $c_0$ | $6.00 |
| Put premium, $p_0$ | $4.00 |
| Risk-free rate | 5.00% |
| Time to expiration | 1 year |

First calculate the present value of the strike:

$$
PV(X)=\frac{50}{1.05}=47.62
$$

Value the protective put:

$$
S_0+p_0=50.00+4.00=54.00
$$

Value the fiduciary call:

$$
c_0+PV(X)=6.00+47.62=53.62
$$

Parity is violated:

$$
54.00 > 53.62
$$

The protective put is overpriced by $0.38. The arbitrage is:

| Action | Cash flow today |
|---|---:|
| Short stock | +50.00 |
| Write put | +4.00 |
| Buy call | -6.00 |
| Buy risk-free bond paying $50 | -47.62 |
| Net arbitrage profit | +0.38 |

At expiration, the long call plus bond and the short stock plus short put offset in every stock-price state. The $0.38 is the locked-in profit.

## American Options Trap

Strict put-call parity holds for European options because neither option can be exercised before expiration. American options can be exercised early, so exact equality can break. CFA may test bounds or qualitative early-exercise implications instead of a clean equality.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Forgetting to discount the strike | Uses $X$ instead of $PV(X)$ | The bond costs the present value of the strike today |
| Ignoring dividends | Uses $S_0$ without adjustment | Use $S_0 - PV(Div)$ or put-call-forward parity |
| Applying strict parity to American options | Gives exact price when early exercise matters | Strict equality is for European options |
| Reversing arbitrage trades | Sells cheap side and buys expensive side | Buy cheap, sell expensive |
| Misreading synthetic signs | Buys a component that should be shorted | Plus means long/lend; minus means short/borrow |

## Memory Hooks

**Fiduciary call = call plus cash. Protective put = stock plus insurance.**

**Same payoff, same price.**

**Buy cheap side, sell expensive side.**

## Related Concepts

- [[Put–call parity]]
- [[Put–call–forward parity]]
- [[Call option]]
- [[Put option]]
- [[Fiduciary call]]
- [[Protective put]]
- [[Forward contract]]
- [[No-arbitrage pricing]]
- [[Binomial Option Pricing Model]]
