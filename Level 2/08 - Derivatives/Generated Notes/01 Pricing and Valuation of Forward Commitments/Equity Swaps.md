---
title: Equity Swaps
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, swaps, equity-swaps]
aliases: [Equity swap, Total return swap, Equity-for-equity swap, Price return swap]
---

# Equity Swaps

## The Real-World Analogy

An [[Equity swap]] lets an investor rent the return of an equity position without buying the shares. One side receives the return on a stock, basket, or index. The other side receives a fixed rate, floating rate, or another equity return. The notional amount is the measuring base for cash flows.

The structure is useful when an institution wants economic equity exposure but does not want to trade the underlying shares because of taxes, regulation, custody, operational limits, or balance-sheet constraints.

## The Big Idea

At least one leg of an equity swap is based on equity performance. The common forms are:

| Swap type | Leg 1 | Leg 2 |
|---|---|---|
| Equity versus fixed | Equity return | Fixed rate |
| Equity versus floating | Equity return | Floating MRR |
| Equity versus equity | Equity return A | Equity return B |

Most CFA examples treat the equity leg as a [[Total return swap|total return]] leg, meaning dividends are included and assumed reinvested unless the question says otherwise. If the question says price return only, dividends are excluded.

## Pricing At Initiation

Pricing a swap means finding the fixed rate that makes the initial value zero.

For an equity-versus-fixed swap, the fixed rate is priced like a plain vanilla [[Interest Rate Swaps|interest rate swap]]:

$$
r_{fixed}
=
\frac{1 - DF_n}{\sum_{i=1}^{n}DF_i}
\times
\frac{1}{AP}
$$

The expected return on the equity index is not used. This is a major exam trap. The equity leg is synthetically financed at the risk-free curve; the fixed rate is driven by discount factors, not by an analyst's view of equity performance.

For an equity-versus-floating swap, there is usually no fixed rate to solve for because the floating leg resets to par. For an equity-versus-equity swap, no initial pricing rate is needed because the position can be viewed as receiving one equity return and paying another.

## Directionality

If you receive equity and pay fixed:

| Equity return | Fixed payment | Net effect |
|---:|---:|---|
| Strong positive | Still paid | Usually gain |
| Small positive below fixed rate | Still paid | Usually loss |
| Negative | Pay the negative equity return and pay fixed | Larger loss |

The last row is the trap. The equity leg is not floored at zero. If the index return is -6% and you are receiving equity, you effectively owe 6% on the equity leg, then also owe the fixed leg if you are the fixed-rate payer.

## Valuation After Initiation

Equity swaps are often valued as an equity position minus a bond position. The exact form depends on which leg you receive.

For receive equity, pay fixed, per $1 notional:

$$
V_{receive-equity}
=
\frac{S_t}{S_{reset}}
-
\left[
AP \times r_{fixed,0}\sum DF_i + DF_n
\right]
$$

For receive fixed, pay equity:

$$
V_{receive-fixed}
=
\left[
AP \times r_{fixed,0}\sum DF_i + DF_n
\right]
-
\frac{S_t}{S_{reset}}
$$

Then multiply by notional.

Use $S_{reset}$, the index level at the last settlement/reset date, not necessarily the original index level at swap inception. This matters when the swap has already made one or more settlements.

## Equity-For-Equity Swaps

A one-equity-for-another swap is like being long one equity exposure and short another:

$$
V = NA(R_{received} - R_{paid})
$$

If you receive Stock B and pay Stock A, and since the last reset Stock B is down 0.8% while Stock A is up 1.3%, then:

$$
V = NA(-0.008 - 0.013) = -0.021NA
$$

With a $1,000,000 notional, the value is:

$$
-0.021(1{,}000{,}000) = -21{,}000
$$

The negative return on the received leg hurts you, and the positive return on the paid leg also hurts you.

## Worked Numerical Example

Assume an investor entered a receive-fixed, pay-equity swap six months ago with a €10,000,000 notional. The fixed rate is 1.50% annually. The equity index was 100 at the last reset date and is now 105. Current interest rates have fallen, and the present value of the remaining fixed leg, including the bond-style principal component, is €10,216,019.

First value the equity leg:

$$
V_{equity}
=
\frac{105}{100}
\times
10{,}000{,}000
=
10{,}500{,}000
$$

Because the investor receives fixed and pays equity:

$$
V_{swap}
=
V_{fixed} - V_{equity}
$$

$$
V_{swap}
=
10{,}216{,}019 - 10{,}500{,}000
=
-283{,}981
$$

The position is negative even though falling interest rates helped the fixed leg. The equity index rose 5%, and the investor is obligated to pay that equity return.

## Cash-Settlement Example

Suppose a $5,000,000 quarterly equity swap pays the equity index total return and receives fixed at 1.60% annually. The quarterly fixed rate is:

$$
1.60\% \times \frac{90}{360} = 0.40\%
$$

If the equity return for the quarter is +4.00%, the receive-equity side receives:

$$
5{,}000{,}000(0.0400 - 0.0040)
=
180{,}000
$$

If the equity return for the next quarter is -6.00%, the receive-equity side pays:

$$
5{,}000{,}000(-0.0600 - 0.0040)
=
-320{,}000
$$

The receive-equity side owes $320,000. The equity loss and the fixed payment both move against it.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Using expected equity return to price the swap | Candidate plugs in a forecast return | Fixed rate comes from discount factors, not expected equity performance |
| Forgetting dividends in total return | Treats total return as price-only return | Include dividends if the leg is total return |
| Flooring negative equity returns at zero | Understates losses to receive-equity side | Equity leg can be negative |
| Using inception index instead of reset index | Overstates or understates the equity leg after prior settlements | Use the index level at the last reset date |
| Treating equity-for-equity as needing a fixed rate | Searches for a swap rate that is irrelevant | Value as received return minus paid return |

## Memory Hooks

**Equity swap fixed rate ignores equity expectations.** The fixed leg is priced from the interest-rate curve.

**Receive equity means receive the good and the bad.** Negative equity return becomes a payment obligation.

**Use the last reset level.** Valuation between dates measures return since the most recent settlement.

## Related Concepts

- [[Equity swap]]
- [[Total return swap]]
- [[Interest Rate Swaps]]
- [[Swap rate]]
- [[Market reference rate]]
- [[Discount factor]]
- [[Synthetic replication]]
- [[Forward Price vs Forward Rate]]
