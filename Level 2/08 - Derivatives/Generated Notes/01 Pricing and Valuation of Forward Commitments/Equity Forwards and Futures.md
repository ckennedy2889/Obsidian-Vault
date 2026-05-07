---
title: Equity Forwards and Futures
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, equity-forwards, futures]
aliases: [Equity forward, Equity futures, Stock forward, Equity index futures, Dividend-adjusted forward price]
---

# Equity Forwards and Futures

## The Real-World Analogy

An [[Equity forward]] is like agreeing today to buy or sell a stock in the future at a fixed price. The forward price must be linked to today's stock price because an arbitrageur can always buy the stock now, finance it, collect any dividends, and deliver it later. The fair forward price is the price that makes that carry trade break even.

For equity index futures, the same logic applies to a whole basket of stocks. Instead of valuing every dividend separately, the exam often models index dividends as a continuous dividend yield.

## The Big Idea

An equity forward price is the future value of the stock after adjusting for dividends. Dividends are carry benefits to the spot owner, not to the long forward holder, so dividends reduce the fair forward price.

| Underlying | Carry benefit | Pricing implication |
|---|---|---|
| Non-dividend stock | None | Forward price is spot compounded at risk-free rate |
| Dividend-paying stock | Discrete dividends | Subtract PV of dividends before compounding |
| Equity index | Continuous dividend yield | Reduce the exponent by dividend yield |

## No-Dividend Stock Forward

If the stock pays no dividends before maturity:

$$
F_0 = S_0(1+r)^T
$$

With continuous compounding:

$$
F_0 = S_0e^{r_cT}
$$

The mechanism is financing. Buying the stock today costs $S_0$. Carrying it to maturity costs interest. The forward price must equal the future value of that financed stock purchase.

## Discrete Dividends

If known dividends are paid during the life of the forward:

$$
F_0 = (S_0 - PVD)(1+r)^T
$$

Equivalently:

$$
F_0 = S_0(1+r)^T - FVD
$$

where $PVD$ is the present value of dividends paid before the forward matures, and $FVD$ is the future value of those dividends at maturity.

Only include dividends paid before contract maturity. A dividend paid after the forward matures is irrelevant.

## Continuous Dividend Yield

For an equity index with continuous dividend yield $\delta_c$:

$$
F_0 = S_0e^{(r_c-\delta_c)T}
$$

If $\delta_c > r_c$, the forward or futures price can be below the spot index level because dividend benefits outweigh financing costs.

## Value After Initiation

The original forward price is locked in. The contract value changes when the spot price, rates, dividends, or time to maturity change.

For a long equity forward with remaining discrete dividends:

$$
V_t =
(S_t - PVD_t)
-
\frac{F_0}{(1+r)^{T-t}}
$$

Equivalently:

$$
V_t =
\frac{F_t - F_0}{(1+r)^{T-t}}
$$

where $F_t$ is the current fair forward price for the remaining life.

For the short forward:

$$
V_{short,t} = -V_{long,t}
$$

## Dividend Announcement Effects

Unexpected dividend news changes forward values immediately.

| New information | Effect on fair forward price | Long forward value | Short forward value |
|---|---:|---:|---:|
| Dividend increase or new dividend before maturity | Decreases | Decreases | Increases |
| Dividend decrease or cancellation | Increases | Increases | Decreases |

The spot price may not move in the question, but the forward value still changes because $PVD_t$ changes.

## Arbitrage Strategies

If the market forward is too high:

1. Borrow money.
2. Buy the stock or index basket.
3. Short the overpriced forward.
4. Use delivery proceeds to repay the loan and keep the excess.

If the market forward is too low:

1. Short-sell the stock or index basket.
2. Invest the proceeds.
3. Go long the underpriced forward.
4. Use the forward purchase to close the short sale and keep the excess.

Dividends complicate the cash flows but not the logic. The spot owner receives dividends; the short seller may owe dividends; the forward holder does not receive interim dividends directly.

## Worked Numerical Example: Discrete Dividend

A stock trades at $100. The one-year risk-free rate is 5%. The stock will pay a $2 dividend in six months.

First find the present value of the dividend:

$$
PVD =
\frac{2}{(1.05)^{0.5}}
=
1.9518
$$

Then price the one-year forward:

$$
F_0 =
(100 - 1.9518)(1.05)
$$

$$
F_0 =
98.0482(1.05)
=
102.95
$$

Equivalently, future value the dividend to maturity and subtract:

$$
FVD =
2(1.05)^{0.5}
=
2.0494
$$

$$
F_0 =
100(1.05)-2.0494
=
102.95
$$

## Worked Numerical Example: Value After Initiation

Continue the prior example. Six months have passed, the dividend has just been paid, the stock price is $110, and six months remain. The original forward price was $102.95.

Because no dividends remain before maturity:

$$
F_t =
110(1.05)^{0.5}
=
112.72
$$

The long forward value is:

$$
V_t =
\frac{112.72 - 102.95}{(1.05)^{0.5}}
$$

$$
V_t =
\frac{9.77}{1.0247}
=
9.53
$$

The long is valuable because it is locked into buying at $102.95 when the current fair forward price is $112.72.

## Worked Numerical Example: Equity Index Futures

An equity index is at 1,140. The continuously compounded risk-free rate is 4.6%, the continuous dividend yield is 2.1%, and the futures contract matures in 140 days.

$$
T = \frac{140}{365}=0.3836
$$

$$
F_0 =
1{,}140e^{(0.046-0.021)(0.3836)}
$$

$$
F_0 =
1{,}140e^{0.00959}
=
1{,}150.99
$$

The futures price is above spot because the financing rate exceeds the dividend yield.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Including dividends after maturity | Subtracts benefits the spot owner will not receive during the forward life | Include only dividends before contract maturity |
| Subtracting dividends at the wrong date | Mixes present and future values | Either subtract $PVD$ before compounding or subtract $FVD$ after compounding |
| Forgetting dividend-announcement effect | Leaves forward value unchanged when expected dividends change | Higher expected dividends reduce long forward value |
| Reporting price instead of value | Calculates $F_t$ and stops | Value is discounted difference between $F_t$ and $F_0$ |
| Using discrete compounding for continuous yield | Applies $(1+r)^T$ to an index yield question | Use $e^{(r_c-\delta_c)T}$ when rates/yields are continuous |

## Memory Hooks

**Dividends belong to the spot owner, not the forward holder.**

**Subtract dividends before compounding, or future-value them and subtract at maturity.**

**Long forward likes higher spot, lower dividends, and lower locked-in price.**

## Related Concepts

- [[Carry Arbitrage Model]]
- [[Forward Price vs Forward Rate]]
- [[Forward contract]]
- [[Futures contract]]
- [[Dividend yield]]
- [[Present value]]
- [[Mark to Market]]
- [[No-arbitrage pricing]]
