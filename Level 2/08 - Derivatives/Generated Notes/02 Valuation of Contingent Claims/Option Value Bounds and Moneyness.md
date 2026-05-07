---
title: Option Value Bounds and Moneyness
subject: Derivatives
tags: [CFA-L2, derivatives, options, arbitrage, moneyness]
aliases: [Option value bounds, Option lower bounds, Option upper bounds, Intrinsic value, Time value, Moneyness]
---

# Option Value Bounds and Moneyness

## The Real-World Analogy

An [[Option]] is like a coupon with optionality. A call is a coupon that lets you buy something at a fixed price. A put is a coupon that lets you sell something at a fixed price. Because the holder can choose whether to use the coupon, the option should never have negative value. Because the coupon only gives a specific right, it also cannot be worth more than the maximum value of that right.

Those simple limits create arbitrage bounds. If an option trades outside them, a trader can buy the underpriced package, sell the overpriced package, and lock in a riskless profit.

## The Big Idea

An option premium has two parts:

$$
\text{Option premium} = \text{Intrinsic value} + \text{Time value}
$$

| Component | Meaning |
|---|---|
| [[Intrinsic value]] | Value if the option were exercised immediately |
| [[Time value]] | Extra value from the possibility that the option becomes more valuable before expiration |

For a call:

$$
\text{Intrinsic value} = \max(0, S_0 - X)
$$

For a put:

$$
\text{Intrinsic value} = \max(0, X - S_0)
$$

## Moneyness

[[Moneyness]] describes where the underlying price sits relative to the strike.

| Option | In the money | At the money | Out of the money |
|---|---|---|---|
| Call | $S_0 > X$ | $S_0 = X$ | $S_0 < X$ |
| Put | $S_0 < X$ | $S_0 = X$ | $S_0 > X$ |

Moneyness is about intrinsic value today. It is not the same thing as profitability after considering the option premium paid.

## Upper Bounds

An option cannot be worth more than the most valuable thing it can deliver.

For calls:

$$
c \le S_0
$$

The call gives the right to buy the stock, not the right to receive more than the stock itself.

For puts:

$$
P_{American} \le X
$$

$$
p_{European} \le PV(X)
$$

The most a put can pay at expiration is the strike price, which occurs if the stock falls to zero. An American put can be exercised immediately, so its upper bound is $X$. A European put cannot be exercised before expiration, so the maximum payoff must be discounted to today.

## Lower Bounds For European Options

For a non-dividend-paying stock, [[Put-Call Parity and Option Arbitrage|put-call parity]] is:

$$
S_0 + p_0 = c_0 + PV(X)
$$

Because option values cannot be negative, the lower bounds are:

$$
c_0 \ge \max(0, S_0 - PV(X))
$$

$$
p_0 \ge \max(0, PV(X) - S_0)
$$

If the stock pays known dividends before expiration, adjust the stock price downward:

$$
c_0 \ge \max(0, S_0 - PV(Div) - PV(X))
$$

$$
p_0 \ge \max(0, PV(X) - [S_0 - PV(Div)])
$$

Dividends reduce call lower bounds and increase put lower bounds because dividends reduce the effective forward value of the stock.

## Why Bounds Create Arbitrage

Suppose a European call is priced below its lower bound:

$$
c_0 < S_0 - PV(X)
$$

Then the call is too cheap relative to the stock and bond. The arbitrage is:

1. Buy the underpriced call.
2. Short the stock.
3. Invest $PV(X)$ at the risk-free rate.

At expiration, the call and stock positions offset, and the bond grows to the strike price. The initial mispricing becomes riskless profit.

The general rule is the same as all no-arbitrage relationships:

```text
Buy the cheap side. Sell the expensive side.
```

## Worked Numerical Example

Assume a non-dividend-paying stock trades at $52, the strike is $50, the risk-free rate is 4%, and expiration is one year.

The present value of the strike is:

$$
PV(X)=\frac{50}{1.04}=48.08
$$

The European call lower bound is:

$$
c_0 \ge \max(0, 52 - 48.08)=3.92
$$

If the call trades for $3.00, it is below the lower bound by $0.92.

Set up the arbitrage:

| Action | Cash flow today |
|---|---:|
| Buy call | -3.00 |
| Short stock | +52.00 |
| Invest $PV(X)$ | -48.08 |
| Net cash inflow | +0.92 |

At expiration:

| Stock outcome | Call | Short stock | Bond | Net payoff |
|---|---:|---:|---:|---:|
| $S_T > 50$ | Exercise; buy stock for 50 | Deliver stock to close short | Bond pays 50 | 0 |
| $S_T \le 50$ | Expires worthless | Buy stock in market to close short | Bond pays 50 | $50-S_T \ge 0$ |

The trader receives $0.92 today and has no loss at expiration.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Confusing moneyness with profitability | Says an ITM option is profitable even if premium paid was too high | Moneyness ignores premium |
| Using $X$ instead of $PV(X)$ for European bounds | Overstates or understates lower/upper bounds | Discount the strike for European options |
| Treating European and American put upper bounds the same | Gives European put upper bound as $X$ | European put upper bound is $PV(X)$ |
| Ignoring dividends | Uses stock price without dividend adjustment | Use $S_0-PV(Div)$ in parity-based bounds |
| Assuming time value is always positive for every option style | Misses early exercise logic for deep ITM American puts | Time value can be effectively sacrificed when early exercise is optimal |

## Memory Hooks

**Call cannot be worth more than the stock.**

**European put cannot be worth more than the present value of the strike.**

**Moneyness is before premium; profit is after premium.**

## Related Concepts

- [[Put-Call Parity and Option Arbitrage]]
- [[Intrinsic value]]
- [[Time value]]
- [[Exercise value]]
- [[Call option]]
- [[Put option]]
- [[European option]]
- [[American-style]]
- [[No-arbitrage pricing]]
