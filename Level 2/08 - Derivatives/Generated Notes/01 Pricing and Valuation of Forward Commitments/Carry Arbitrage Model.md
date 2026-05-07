---
title: Carry Arbitrage Model
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, no-arbitrage, forwards-futures]
aliases: [Cost of carry model, Carry arbitrage, Reverse carry arbitrage, No-arbitrage forward price]
---

# Carry Arbitrage Model

## The Real-World Analogy

The [[Carry Arbitrage]] model says a forward price should equal the cost of buying the asset today and carrying it until delivery. If you can buy wheat today, store it, insure it, finance it, and deliver it later, then a forward contract for future delivery cannot be priced far away from that all-in carry cost. If it is, an arbitrageur can do the cheaper path and sell the expensive path.

The same logic applies to financial assets. For a stock index, the carrying cost is financing. The carry benefit is dividends. For a bond, the benefit is coupon income. For a commodity, storage is a cost and convenience yield is a benefit.

## The Big Idea

At initiation, the no-arbitrage forward price is set so the contract value is zero:

$$
V_0 = 0
$$

That does not mean the forward price is a forecast of the future spot price. It means the forward price prevents a riskless trade between:

```text
Buy asset today and carry it
versus
Enter forward contract for future delivery
```

## No Cash Flows From The Underlying

If the underlying has no dividends, coupons, storage costs, insurance costs, or other carrying benefits/costs:

$$
F_0 = S_0(1+r)^T
$$

With continuous compounding:

$$
F_0 = S_0e^{r_cT}
$$

The mechanism is financing. To replicate future ownership, borrow $S_0$, buy the asset now, and carry it to time $T$. At maturity, the loan payoff is $S_0(1+r)^T$, so the forward delivery price must match that amount.

## Benefits And Costs Of Carry

Most assets are not clean. Holding the spot asset may produce benefits or costs before delivery.

| Item | Examples | Effect on forward price | Why |
|---|---|---:|---|
| Carry benefit | Dividends, coupons, lease income, convenience yield | Decreases $F_0$ | Spot owner receives the benefit; forward holder does not |
| Carry cost | Storage, insurance, spoilage, financing beyond the risk-free rate | Increases $F_0$ | Spot owner must pay the cost to carry the asset |

With discrete cash flows:

$$
F_0 =
\left[
S_0 + PV_0(\text{costs}) - PV_0(\text{benefits})
\right](1+r)^T
$$

With continuous yields:

$$
F_0 =
S_0e^{(r_c + \text{cost yield} - \text{benefit yield})T}
$$

For an equity index with continuous dividend yield $\delta$:

$$
F_0 = S_0e^{(r_c-\delta)T}
$$

## Arbitrage When The Forward Price Is Too High

If the market forward price is above fair value:

$$
F_{market} > F_{fair}
$$

then the forward is expensive. Use carry arbitrage:

1. Borrow cash.
2. Buy the underlying spot.
3. Short the overpriced forward.
4. At maturity, deliver the asset into the forward, receive the high forward price, repay the loan, and keep the difference.

The idea is: buy cheap spot exposure and sell expensive forward exposure.

## Arbitrage When The Forward Price Is Too Low

If the market forward price is below fair value:

$$
F_{market} < F_{fair}
$$

then the forward is cheap. Use reverse carry arbitrage:

1. Short-sell the underlying.
2. Invest the short-sale proceeds.
3. Go long the underpriced forward.
4. At maturity, use the forward to buy the asset cheaply, return it to close the short, and keep the invested proceeds net of the forward price.

The idea is: sell expensive spot exposure and buy cheap forward exposure.

## Forward Value After Initiation

Pricing gives the delivery price at initiation. Valuation gives the mark-to-market value later.

For a long forward at time $t$:

$$
V_t =
\frac{F_t - F_0}{(1+r)^{T-t}}
$$

where $F_t$ is the current fair forward price for the remaining life and $F_0$ is the original locked-in delivery price.

Equivalent form for an asset with no remaining cash flows:

$$
V_t =
S_t - \frac{F_0}{(1+r)^{T-t}}
$$

For assets with remaining benefits:

$$
V_t =
\left[S_t - PV_t(\text{benefits}) + PV_t(\text{costs})\right]
-
\frac{F_0}{(1+r)^{T-t}}
$$

The long benefits when the current fair forward price rises above the original locked-in price.

## Futures Versus Forwards

Forwards and futures often share the same no-arbitrage pricing formula. Their values behave differently:

| Contract | Value behavior |
|---|---|
| Forward | Value accumulates until settlement |
| Futures | Marked to market daily; value resets through margin settlement |

If interest rates are stochastic and correlated with futures prices, futures and forward prices may differ. CFA usually starts with the no-arbitrage equivalence, then tests whether you understand daily settlement and margining.

## Worked Numerical Example: Continuous Yield

Suppose an equity index is at 3,500. The continuously compounded risk-free rate is 0.15%, the continuous dividend yield is 3.00%, and maturity is three months.

$$
S_0 = 3{,}500
$$

$$
r_c = 0.0015
$$

$$
\delta = 0.0300
$$

$$
T = 0.25
$$

The fair futures price is:

$$
F_0 = 3{,}500e^{(0.0015-0.0300)(0.25)}
$$

$$
F_0 = 3{,}500e^{-0.007125}
$$

$$
F_0 \approx 3{,}475.15
$$

The futures price is below spot because the dividend yield benefit is larger than the financing cost.

## Worked Numerical Example: Forward Value After Initiation

A long one-year forward was entered at $F_0=1{,}000$. Seven months later, the spot price is $1{,}050$. There are five months left. The present value of remaining storage costs is $4$, the present value of remaining income benefits is $28$, and the annual risk-free rate is 2%.

First calculate the current fair forward price:

$$
F_t =
\left(1{,}050 + 4 - 28\right)(1.02)^{5/12}
$$

$$
F_t =
1{,}026(1.00828)
=
1{,}034.50
$$

Now value the old long forward:

$$
V_t =
\frac{1{,}034.50 - 1{,}000}{(1.02)^{5/12}}
$$

$$
V_t =
\frac{34.50}{1.00828}
=
34.22
$$

The long forward is worth $34.22 because the current fair delivery price is above the old locked-in delivery price.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating $F_0$ as a forecast | Candidate interprets the forward as expected future spot | $F_0$ is a no-arbitrage carry price |
| Subtracting dividends after compounding | Uses $S_0(1+r)^T - D$ | Subtract the present value of benefits first |
| Treating convenience yield as a cost | Raises commodity forward price incorrectly | Convenience yield is a benefit of owning the physical asset |
| Mixing compounding conventions | Uses $e^{rT}$ with discrete rates or $(1+r)^T$ with continuous yields | Match the formula to the stated compounding |
| Reporting new forward price as old forward value | Stops after calculating $F_t$ | Value is discounted difference between $F_t$ and locked-in $F_0$ |

## Memory Hooks

**Costs carry forward price up; benefits pull it down.**

**Too high: buy spot, short forward. Too low: short spot, long forward.**

**Forward price is a deal term; forward value is mark-to-market.**

## Related Concepts

- [[Forward Price vs Forward Rate]]
- [[Forward contract]]
- [[Futures contract]]
- [[No-arbitrage pricing]]
- [[Carry costs]]
- [[Convenience yield]]
- [[Dividend yield]]
- [[Mark to Market]]
- [[Currency Swaps]]
- [[Interest Rate Swaps]]
