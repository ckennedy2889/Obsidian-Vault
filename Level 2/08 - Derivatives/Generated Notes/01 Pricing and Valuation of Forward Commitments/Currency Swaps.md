---
title: Currency Swaps
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, swaps, currency-swaps]
aliases: [Cross-currency swap, Fixed-for-fixed currency swap, FX swap valuation]
---

# Currency Swaps

## The Real-World Analogy

A [[Currency swap]] is like two companies temporarily trading borrowing identities. A US company needs Australian dollars, and an Australian company needs US dollars. Instead of each firm borrowing in an unfamiliar market, they exchange principal today, pay interest in the currency they owe, and exchange the same principal amounts back at maturity.

The important difference from a plain [[Interest Rate Swaps|interest rate swap]] is that a currency swap usually exchanges notional principal. The principal is not just a calculator input; it is part of the cash-flow package.

## The Big Idea

A fixed-for-fixed currency swap is economically a pair of fixed-rate bonds in two different currencies:

```text
Receive Currency A fixed cash flows
minus
Pay Currency B fixed cash flows converted at the current spot exchange rate
```

If you receive Currency A and pay Currency B, you are long a Currency A fixed-rate bond and short a Currency B fixed-rate bond.

## Notional Exchange

Currency swaps normally include two principal exchanges:

| Date | Cash flow |
|---|---|
| Initiation | Exchange notional amounts at the spot exchange rate |
| Maturity | Re-exchange the same notional amounts |

If the spot rate is $S_0^{A/B}$, meaning units of Currency A per 1 unit of Currency B, then:

$$
NA_A = S_0^{A/B} \times NA_B
$$

The inception exchange happens at the market spot rate, so it does not create value by itself. The contract value at initiation is zero because the two principal amounts are equivalent at $S_0$ and the fixed rates are set from each currency's yield curve.

## Pricing Fixed Rates In Each Currency

Pricing a fixed-for-fixed currency swap means determining:

| Item | How it is found |
|---|---|
| Notional in each currency | Current spot exchange rate |
| Fixed rate in Currency A | Currency A discount curve |
| Fixed rate in Currency B | Currency B discount curve |

Each fixed rate is priced exactly like a par fixed rate on that currency's own curve:

$$
r_k =
\frac{1 - DF_{n,k}}{\sum_{i=1}^{n} DF_{i,k}}
\times \frac{1}{AP}
$$

where $k$ is the currency, $DF_{n,k}$ is the final discount factor in that currency, and $AP$ is the accrual period.

The mechanism is the same as a [[Swap rate]] calculation: the fixed coupon rate is set so the fixed-rate bond in that currency is worth par. A currency swap simply does that twice, once in each currency.

## Valuation After Initiation

After initiation, value each currency leg as a bond using the current discount curve for that currency. Then convert one leg into the other currency using the current spot exchange rate.

For a receive Currency A, pay Currency B swap valued in Currency A:

$$
V_{swap,A} = V_A - S_t^{A/B}V_B
$$

Expanded:

$$
V_{swap,A}
=
NA_A\left[(AP \times r_{A,0})\sum DF_{i,A}+DF_{n,A}\right]
-
S_t^{A/B}
NA_B\left[(AP \times r_{B,0})\sum DF_{i,B}+DF_{n,B}\right]
$$

Use the original fixed rates in the coupon terms because those are the contract rates. Use current discount factors and the current spot exchange rate because valuation happens today.

## Directionality

If you receive Currency A and pay Currency B, the position gains value when:

| Driver | Why value increases |
|---|---|
| Currency A appreciates versus Currency B | Incoming Currency A cash flows are worth more |
| Currency A rates fall | The long Currency A fixed-rate bond rises in value |
| Currency B rates rise | The short Currency B fixed-rate bond liability falls in value |

The reverse position has the opposite exposures.

## Worked Numerical Example

Assume a US company enters a one-year quarterly fixed-for-fixed currency swap. It receives A$100,000,000 and pays USD. The spot exchange rate is:

$$
S_0 = 1.1400 \text{ AUD per USD}
$$

The USD notional is:

$$
NA_{USD} =
\frac{100{,}000{,}000}{1.1400}
=
87{,}719{,}298
$$

The swap uses quarterly payments, so:

$$
AP = \frac{90}{360}=0.25
$$

Suppose the AUD curve has $\sum DF_{AUD}=3.933870$ and $DF_{4,AUD}=0.972763$. The AUD fixed rate is:

$$
r_{AUD}
=
\frac{1 - 0.972763}{3.933870}\times 4
=
0.027695
=
2.7695\%
$$

Suppose the USD curve has $\sum DF_{USD}=3.995009$ and $DF_{4,USD}=0.997506$. The USD fixed rate is:

$$
r_{USD}
=
\frac{1 - 0.997506}{3.995009}\times 4
=
0.002497
=
0.2497\%
$$

Now value the swap 60 days later to the US company that receives AUD and pays USD. The current spot rate is:

$$
S_t = 1.1300 \text{ AUD per USD}
$$

Current AUD discount factors give $\sum DF_{AUD}=3.967683$ and $DF_{n,AUD}=0.986031$. Current USD discount factors give $\sum DF_{USD}=3.994841$ and $DF_{n,USD}=0.998336$.

Value the AUD leg in AUD:

$$
V_{AUD}
=
100{,}000{,}000
\left[
(0.25)(0.027695)(3.967683)+0.986031
\right]
$$

$$
V_{AUD}
=
100{,}000{,}000(1.01350248)
=
A\$101{,}350{,}248
$$

Value the USD leg in USD:

$$
V_{USD}
=
87{,}719{,}298
\left[
(0.25)(0.002497)(3.994841)+0.998336
\right]
$$

$$
V_{USD}
\approx
US\$87{,}792{,}088
$$

Convert the AUD leg into USD:

$$
\frac{A\$101{,}350{,}248}{1.1300}
=
US\$89{,}690{,}485
$$

Net the received leg minus the paid leg:

$$
V_{swap,USD}
=
89{,}690{,}485 - 87{,}792{,}088
=
US\$1{,}898{,}397
$$

The value is positive to the US company because the received AUD leg is worth more than the paid USD leg after updating both interest-rate curves and the exchange rate.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Forgetting principal exchange | Values only coupon differences | Currency swaps include final notional repayment |
| Using one discount curve | Discounts both legs with the same rates | Discount each leg using that currency's curve |
| Inverting the FX quote incorrectly | Multiplies when the quote requires division, or vice versa | Write the quote units before calculating |
| Using new fixed rates as coupons | Replaces contract coupons with current market coupons | Use original fixed rates for cash flows; current rates only for discounting |
| Treating it like a single-currency swap | Applies $NA(FS_0-FS_t)\sum DF$ directly | Value two bond legs and convert to one currency |

## Memory Hooks

**Currency swap = two bonds plus FX.** If you remember only one thing, remember that valuation is bond-leg PVs translated at today's spot rate.

**Each currency lives on its own curve.** AUD cash flows use AUD rates; USD cash flows use USD rates.

**Notional comes back.** Unlike a plain interest rate swap, principal is usually exchanged at inception and maturity.

## Related Concepts

- [[Currency swap]]
- [[Interest Rate Swaps]]
- [[Swap rate]]
- [[Covered interest rate parity]]
- [[Exchange rate]]
- [[Discount factor]]
- [[Forward Price vs Forward Rate]]
- [[No-arbitrage pricing]]
