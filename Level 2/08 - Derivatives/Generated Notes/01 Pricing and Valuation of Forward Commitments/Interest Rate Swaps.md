---
title: Interest Rate Swaps
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, swaps, interest-rates]
aliases: [Fixed-for-floating interest rate swap, Plain vanilla interest rate swap, Swap fixed rate, SFR]
---

# Interest Rate Swaps

## The Real-World Analogy

An [[Interest rate swap]] is like two borrowers agreeing to trade the type of interest bill they each face. One side says, "I will pay you a fixed rate every period." The other says, "I will pay you whatever the floating [[Market reference rate|market reference rate]] turns out to be." They do not exchange the loan principal. They only exchange the net difference in interest payments on a notional amount.

The practical use is risk transformation. A company with floating-rate debt can use a swap to synthetically convert that exposure into fixed-rate debt. A company with fixed-rate debt can use the opposite swap to synthetically create floating-rate exposure.

## The Big Idea

A plain vanilla fixed-for-floating swap is a series of forward commitments. At each settlement date, one party pays fixed and receives floating; the other receives fixed and pays floating.

| Position | Pays | Receives | Gains when |
|---|---:|---:|---|
| Fixed-rate payer | Fixed swap rate | Floating MRR | Rates rise |
| Fixed-rate receiver | Floating MRR | Fixed swap rate | Rates fall |

The directionality is the same as a [[Forward Rate Agreements (FRAs)|long FRA]] for the fixed-rate payer: paying fixed and receiving floating benefits when future floating rates rise.

## Bond-Replication Intuition

The cleanest mental model is to rewrite the swap as two bond positions:

| Swap position | Bond replication | Duration intuition |
|---|---|---|
| Pay fixed, receive floating | Short fixed-rate bond + long floating-rate bond | Negative duration |
| Receive fixed, pay floating | Long fixed-rate bond + short floating-rate bond | Positive duration |

Why does the pay-fixed side have negative duration? A fixed-rate bond loses value when rates rise. The pay-fixed side is short that fixed-rate bond, so it gains when rates rise. The floating leg resets to market, so its value stays close to par on reset dates.

## Pricing The Swap Fixed Rate

Pricing a swap means solving for the fixed rate that makes the swap worth zero at initiation. At that rate, the present value of the fixed leg equals the present value of the floating leg.

On a reset date, the floating-rate bond is worth par. Per $1 notional, the fixed leg is worth:

$$
B_{fixed} = PMT \sum_{i=1}^{n} DF_i + DF_n
$$

At initiation:

$$
B_{fixed} = B_{floating} = 1
$$

So:

$$
1 = PMT \sum_{i=1}^{n} DF_i + DF_n
$$

Solving for the periodic fixed payment rate:

$$
PMT = \frac{1 - DF_n}{\sum_{i=1}^{n} DF_i}
$$

If payments are quarterly or semiannual, convert between the periodic rate and annualized swap rate using the accrual period:

$$
\text{Annualized SFR} =
\frac{1 - DF_n}{\sum_{i=1}^{n} DF_i}
\times \frac{1}{AP}
$$

where $AP$ is the accrual period, such as $90/360$ for quarterly payments or $180/360$ for semiannual payments.

## Why The Formula Works

The numerator $1 - DF_n$ is the present value of principal repayment that the floating leg effectively supplies at the final date. The denominator $\sum DF_i$ is the annuity factor for the fixed coupons. Dividing the two tells you the fixed coupon rate that makes the fixed-rate bond worth par.

That is why a swap fixed rate is economically a par coupon rate. The swap rate is the fixed coupon that makes the fixed leg equal to a par floating leg.

## Valuation After Initiation

Valuation asks what an existing swap is worth after market rates have changed. CFA Level II focuses on valuation **on settlement dates after settlement has occurred**, because the floating leg resets to par and the formula is clean.

For the fixed-rate receiver:

$$
V_{receive-fixed}
=
NA(FS_0 - FS_t)\sum_{i=1}^{n} DF_i
$$

For the fixed-rate payer:

$$
V_{pay-fixed}
=
NA(FS_t - FS_0)\sum_{i=1}^{n} DF_i
$$

where:

| Symbol | Meaning |
|---|---|
| $NA$ | Notional amount |
| $FS_0$ | Original fixed swap rate in the existing contract |
| $FS_t$ | Current market fixed swap rate for the remaining maturity |
| $\sum DF_i$ | Sum of current discount factors for remaining settlement dates |

The sign check matters more than memorizing the formula. If you receive fixed at 5% and the market now pays only 4%, your receive-fixed position is valuable. If you pay fixed at 5% and the market now pays only 4%, your pay-fixed position is costly.

## Worked Numerical Example

Assume a five-year annual-pay interest rate swap is being priced from the following discount factors:

| Year | Discount factor |
|---:|---:|
| 1 | 0.990099 |
| 2 | 0.977876 |
| 3 | 0.965136 |
| 4 | 0.951529 |
| 5 | 0.937467 |
| Sum | 4.822107 |

The annual swap fixed rate is:

$$
SFR =
\frac{1 - DF_5}{\sum DF_i}
$$

$$
SFR =
\frac{1 - 0.937467}{4.822107}
$$

$$
SFR =
\frac{0.062533}{4.822107}
= 0.012968
= 1.2968\%
$$

Now suppose an investor is the receive-fixed party on a €100,000,000 swap entered two years ago at a fixed rate of 2.00%. Today there are exactly five years left, and the current market fixed rate for a five-year swap is 1.2968%. The current discount-factor sum is 4.822107.

Because the investor receives 2.00% when the market would now pay only 1.2968%, the position should be positive.

$$
V_{receive-fixed}
=
100{,}000{,}000(0.0200 - 0.012968)(4.822107)
$$

$$
V_{receive-fixed}
=
100{,}000{,}000(0.007032)(4.822107)
$$

$$
V_{receive-fixed}
=
3{,}390{,}905
$$

The receive-fixed party has a positive value of about €3.39 million. The pay-fixed party has the same value with the opposite sign.

## Payment-Date Versus Between-Payment Valuation

The simple CFA formula works on a settlement date because the floating leg has just reset. Between settlement dates, accrued interest and the partially known floating payment complicate the valuation. The Level II curriculum emphasizes the settlement-date version, so if an item set gives a valuation date exactly after settlement, use the clean formula.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Confusing price with value | Treats the fixed swap rate and the mark-to-market amount as the same thing | Price is the fixed rate; value is the dollar or euro amount |
| Reversing payer/receiver signs | Gives positive value to the wrong counterparty | Fixed payer gains when rates rise; fixed receiver gains when rates fall |
| Forgetting the accrual period | Uses an annual formula for quarterly or semiannual payments | Use periodic payments or multiply by $1/AP$ for annualized SFR |
| Treating notional as exchanged | Adds principal exchange to an interest rate swap | Plain vanilla interest rate swaps do not exchange notional |
| Valuing between settlement dates with reset-date formula | Ignores accrued and partially known cash flows | Confirm the question says valuation is on a settlement/reset date |

## Memory Hooks

**Swap rate = par coupon.** It is the fixed coupon that makes the fixed leg worth par, just like the floating leg on reset dates.

**Pay fixed = short bond.** If rates rise, the short fixed-rate bond position gains value.

**Price is a rate; value is money.** This distinction appears repeatedly in forward commitments.

## Related Concepts

- [[Forward Rate Agreements (FRAs)]]
- [[Forward Price vs Forward Rate]]
- [[Interest rate swap]]
- [[Swap rate]]
- [[Market reference rate]]
- [[Discount factor]]
- [[Duration]]
- [[No-arbitrage pricing]]
