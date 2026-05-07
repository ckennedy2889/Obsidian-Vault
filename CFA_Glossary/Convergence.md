---
title: Convergence
subject: Derivatives
tags: [CFA-L2, derivatives, forwards, futures, no-arbitrage, cost-of-carry]
aliases: [Forward convergence, Futures convergence, Forward price convergence, Basis convergence, Convergence to spot]
---

# Convergence

## The Real-World Analogy

Imagine you reserve a hotel room today for a stay three months from now. Today, the reservation price can differ from tonight's walk-in price because the hotel is really pricing a future stay. There is time, uncertainty, financing, and convenience between now and then.

But on the actual night of the stay, there is no longer a "future stay" to price. The reservation for tonight and the room available tonight point to the same economic thing: use of the room now.

That is the intuition behind convergence. A [[Forward contract]] or [[Futures contract]] can trade away from the [[Spot price]] before expiration because it is pricing delivery later. At expiration, delivery is now. The derivative price and spot price must collapse into the same price, or arbitrage becomes immediate.

## The Big Idea

In Level II Derivatives, **convergence** means:

$$
F_T = f_T = S_T
$$

where:

| Symbol | Meaning |
|---|---|
| $F_T$ | [[Forward price]] at expiration |
| $f_T$ | [[Futures contract\|Futures]] price at expiration |
| $S_T$ | [[Spot price]] at expiration |

The key phrase is **at expiration**. Before expiration, the forward or futures price can be above or below spot because it reflects [[Cost of carry]], financing, storage, dividends, coupons, convenience yield, and other benefits or costs of holding the underlying. At expiration, those remaining carry effects over the contract's remaining life are zero.

## Why The Rule Exists

The [[No-arbitrage pricing]] logic is simple:

```text
Before expiration:
Forward/futures price = price for future delivery
Spot price            = price for immediate delivery

At expiration:
Forward/futures delivery = immediate delivery
Spot delivery            = immediate delivery
```

Once both prices refer to the same asset delivered at the same time and place, they must be the same price. If not, a trader could buy in the cheaper market and sell in the more expensive market at the same moment.

## Formula Version

For a simple non-income-producing asset:

$$
F_t = S_t(1+r)^{T-t}
$$

With continuous compounding:

$$
F_t = S_te^{r(T-t)}
$$

The convergence mechanism is visible in the exponent. As time passes, the remaining life $T-t$ shrinks. At expiration:

$$
T-t=0
$$

Therefore:

$$
F_T = S_T(1+r)^0
$$

and:

$$
(1+r)^0 = 1
$$

so:

$$
F_T = S_T
$$

With continuous compounding:

$$
F_T = S_Te^{r(0)}=S_Te^0=S_T
$$

The same logic applies when the asset has carry benefits or carry costs. For example, with a continuous dividend yield $q$:

$$
F_t = S_te^{(r-q)(T-t)}
$$

At expiration:

$$
F_T=S_Te^{(r-q)(0)}=S_T
$$

Carry only matters over remaining time. When no remaining time exists, there is nothing left to finance, store, receive, or forego.

## Mechanism: Basis Goes To Zero

The **basis** is the difference between the cash/spot price and the futures or forward price. Depending on convention, it may be written as:

$$
\text{Basis}=S_t-F_t
$$

or:

$$
\text{Basis}=F_t-S_t
$$

The sign convention is less important than the convergence idea:

$$
\text{Basis at expiration}=0
$$

Before expiration, basis exists because spot ownership and forward/futures exposure are not identical:

| Owner of spot asset | Long forward/futures |
|---|---|
| Pays financing cost or gives up cash today | Usually pays no full purchase price today |
| May receive dividends, coupons, lease income, or convenience benefits | Does not receive those interim ownership benefits |
| May pay storage, insurance, or carrying costs | Does not directly carry the asset |
| Has immediate control of the asset | Has delivery/settlement exposure later |

As expiration approaches, the time value of those differences disappears.

```text
Long time to maturity
  -> carry effects can be large
  -> forward/futures price can differ from spot

Near maturity
  -> little time left for carry effects
  -> basis shrinks

At expiration
  -> no time left for carry effects
  -> forward/futures price = spot price
```

## Worked Numerical Example

Suppose a non-dividend-paying stock has a current spot price of $100, the annual risk-free rate is 6%, and the forward has six months to expiration.

The no-arbitrage forward price is:

$$
F_0=S_0(1+r)^T
$$

$$
F_0=100(1.06)^{0.5}
$$

$$
(1.06)^{0.5}=1.02956
$$

$$
F_0=102.96
$$

The forward price is above spot because the forward buyer does not pay $100 today. The spot buyer must finance the purchase for six months, so the forward delivery price includes that financing cost.

Now move forward in time and assume the spot price remains $100 only to isolate the convergence effect.

| Time remaining | Formula | Forward price |
|---:|---|---:|
| 0.50 years | $100(1.06)^{0.50}$ | $102.96$ |
| 0.25 years | $100(1.06)^{0.25}$ | $101.47$ |
| 0.01 years | $100(1.06)^{0.01}$ | $100.06$ |
| 0.00 years | $100(1.06)^0$ | $100.00$ |

The forward price is not "predicting" the future spot price. It is spot plus the cost of carrying the asset over the remaining time. As remaining time goes to zero, the carry adjustment goes to zero.

## What If They Do Not Converge?

Suppose at expiration the spot price is $100, but the expiring forward or futures price is $101.

An arbitrageur could:

1. Buy the asset in the spot market for $100.
2. Sell or settle through the derivative at $101.
3. Lock in $1 per unit, ignoring frictions.

If the derivative price were $99 while spot was $100, the arbitrage reverses:

1. Buy through the derivative at $99.
2. Sell in the spot market for $100.
3. Lock in $1 per unit, ignoring frictions.

That immediate arbitrage pressure is why convergence is not just a pattern. Under the CFA no-arbitrage framework, it is a pricing condition.

## Forward Price, Original Contract Price, And Forward Value

This is the exam trap. Convergence applies to the **current expiring forward/futures price**, not necessarily to the original contract price that was locked in months ago.

Suppose you entered a long forward six months ago at:

$$
F_0=102.96
$$

At expiration, the spot price is:

$$
S_T=110
$$

The current expiring forward price converges to spot:

$$
F_T=S_T=110
$$

But your original delivery price remains:

$$
F_0=102.96
$$

Your long forward payoff is:

$$
S_T-F_0=110-102.96=7.04
$$

So do not say "the original forward price becomes the spot price." It does not. The original contract price is fixed. The **current market forward price for a contract expiring now** converges to the spot price.

## Common Exam Traps

| Trap | Why it is tempting | Correct exam reflex |
|---|---|---|
| "Forward price equals expected future spot price" | The contract settles in the future, so it feels like a forecast | Forward price is a no-arbitrage carry price, not automatically a forecast |
| "The original forward price changes into spot" | Both are called forward prices in casual speech | Original $F_0$ stays fixed; current $F_t$ changes |
| "Basis is always zero" | Basis is zero at expiration | Basis can be positive or negative before expiration |
| "Convergence means the forward value goes to zero" | Price and value are easy to mix up | Forward value at expiration is $S_T-F_0$ for the long |
| "Carry disappears because rates become zero" | The formula adjustment disappears | Rates do not need to be zero; remaining time becomes zero |

## Memory Hook

```text
Carry needs time.
At expiration, time is gone.
No time -> no carry -> forward/futures price = spot.
```

## Related Concepts

- [[Forward price]]
- [[Forward value]]
- [[Forward contract]]
- [[Futures contract]]
- [[Spot price]]
- [[Cost of carry]]
- [[Carry arbitrage model]]
- [[No-arbitrage pricing]]
- [[Basis]]
- [[Contango]]
- [[Backwardation]]
