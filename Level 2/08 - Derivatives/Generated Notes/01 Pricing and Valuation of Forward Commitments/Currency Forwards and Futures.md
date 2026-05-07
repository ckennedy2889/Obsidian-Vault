---
title: Currency Forwards and Futures
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, currency-forwards, fx]
aliases: [FX forwards, Currency forward, Currency futures, Covered interest parity forward pricing]
---

# Currency Forwards and Futures

## The Real-World Analogy

A [[Currency forward]] is like locking in the exchange rate for a future trip, invoice, or investment. If a US investor knows she must pay euros in six months, she can agree today on the future USD/EUR rate. The forward rate is not a guess about where the spot rate will be. It is the exchange rate that prevents arbitrage between investing in the two currencies.

The pricing mechanism is [[Covered interest rate parity]]: once the currency exposure is hedged with a forward contract, borrowing and lending in either currency should produce the same risk-free result.

## Quote Convention

CFA FX notation can flip your answer if you do not label units.

Write the exchange rate as:

$$
S_{price/base}
$$

meaning:

```text
units of price currency per 1 unit of base currency
```

Example:

$$
S_{USD/EUR}=1.1649
$$

means 1 EUR costs 1.1649 USD. EUR is the base currency. USD is the price currency.

## Covered Interest Parity Pricing

For a quote expressed as price currency per base currency:

$$
F_{price/base}
=
S_{price/base}
\times
\frac{1+r_{price}T}{1+r_{base}T}
$$

With continuous compounding:

$$
F_{price/base}
=
S_{price/base}e^{(r_{price}-r_{base})T}
$$

The price-currency interest rate goes in the numerator. The base-currency interest rate goes in the denominator.

Why? Think of two ways to end with price currency:

1. Invest price currency domestically.
2. Convert to base currency, invest at the base rate, and lock in conversion back using a forward.

If those hedged returns differ, arbitrageurs borrow in the low-return path and invest in the high-return path until the forward rate adjusts.

## Forward Premium And Discount

The currency with the higher interest rate generally trades at a forward discount. The currency with the lower interest rate trades at a forward premium.

| Interest-rate relationship | Forward relationship |
|---|---|
| Price-currency rate > base-currency rate | $F_{price/base} > S_{price/base}$ |
| Price-currency rate < base-currency rate | $F_{price/base} < S_{price/base}$ |

This statement is about the quote. It is not necessarily a forecast of future spot movement.

## Arbitrage Logic

If the market forward is too high relative to covered interest parity, sell the overpriced forward side. If the market forward is too low, buy the underpriced forward side.

For a quote $S_{price/base}$:

| Mispricing | Strategy intuition |
|---|---|
| Forward too high | Borrow base, convert to price, invest price, sell base forward |
| Forward too low | Borrow price, convert to base, invest base, buy base forward |

The exact cash-flow setup depends on the quote, but the rule is consistent: sell what is overpriced and finance it through the cheaper replication path.

## Valuation After Initiation

The original forward rate is locked in, but the contract's value changes as spot rates, interest rates, and time to maturity change.

For a long forward position in the base currency, valued in price currency:

$$
V_t =
S_{t,price/base}
-
F_{0,price/base}e^{-(r_{price}-r_{base})(T-t)}
$$

This compares the current spot value of the base currency to the present value of the locked-in forward payment, adjusted for the interest-rate differential over the remaining life.

With discrete compounding, the same logic is:

$$
V_t =
S_t
-
F_0
\frac{1+r_{base}(T-t)}{1+r_{price}(T-t)}
$$

For the short forward position, reverse the sign.

## Worked Numerical Example: Pricing

A German company will receive South Korean won in 75 days and wants a KRW/EUR forward rate. The spot quote is:

$$
S_{KRW/EUR}=1{,}300
$$

The KRW risk-free rate is 0.75%, the EUR risk-free rate is -0.25%, and the continuously compounded horizon is:

$$
T = \frac{75}{365}=0.2055
$$

KRW is the price currency and EUR is the base currency:

$$
F_{KRW/EUR}
=
1{,}300e^{(0.0075 - (-0.0025))(75/365)}
$$

$$
F_{KRW/EUR}
=
1{,}300e^{0.0100(0.2055)}
$$

$$
F_{KRW/EUR}
=
1{,}300(1.002057)
=
1{,}302.67
$$

Because the EUR has the lower interest rate, it trades at a forward premium: one EUR buys more KRW forward than spot.

## Worked Numerical Example: Valuation

An investor is long a one-year USD/EUR forward, meaning the investor will buy EUR and pay USD. The original forward rate is:

$$
F_0 = 1.201 \text{ USD/EUR}
$$

Immediately after initiation, spot is:

$$
S_t = 1.192 \text{ USD/EUR}
$$

The USD risk-free rate is 0.75%, the EUR risk-free rate is -0.25%, and one year remains.

For a long base-currency position:

$$
V_t =
S_t - F_0e^{-(r_{USD}-r_{EUR})T}
$$

$$
V_t =
1.192 - 1.201e^{-(0.0075 - (-0.0025))(1)}
$$

$$
V_t =
1.192 - 1.201e^{-0.0100}
$$

$$
V_t =
1.192 - 1.189
=
0.003 \text{ USD/EUR}
$$

The long EUR forward has a small positive mark-to-market value.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Inverting the quote | Uses EUR/USD when the formula is set up for USD/EUR | Write units next to every rate |
| Putting the wrong rate in the numerator | Uses base rate over price rate | For $S_{price/base}$, price rate goes on top |
| Treating forward premium as a forecast | Says the high-interest currency is "expected" to depreciate under covered parity | CIRP is arbitrage pricing, not an expectation model |
| Forgetting to discount valuation | Calculates the maturity cash-flow difference only | Mark-to-market is present value today |
| Ignoring bid/offer when provided | Uses midpoint when closing trade requires bid or offer | Long base closes by selling base forward, so use bid if bid/offer is tested |

## Memory Hooks

**Label the quote before touching the formula.**

**Higher-rate currency trades at a forward discount.**

**Covered parity removes the free lunch, not uncertainty.**

## Related Concepts

- [[Covered interest rate parity]]
- [[Spot and Forward FX Rates]]
- [[International Parity Conditions]]
- [[Carry Trades]]
- [[Forward Price vs Forward Rate]]
- [[Currency Swaps]]
- [[Exchange rate]]
- [[Forward contract]]
