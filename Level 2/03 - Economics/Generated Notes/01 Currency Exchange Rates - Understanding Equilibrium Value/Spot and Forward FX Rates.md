---
title: Spot and Forward FX Rates
subject: Economics
tags: [CFA-L2, Economics, ExchangeRates, ForwardRates]
aliases: [spot and forward rates, FX spot and forward rates, forward premium and discount, all-in forward rate]
---

# Spot and Forward FX Rates

## The Real-World Analogy

A spot exchange rate is the price for exchanging currency now.

A forward exchange rate is the price for exchanging currency later, agreed today.

It is like buying airline tickets:

```text
Spot rate = price if you travel now
Forward rate = price locked in today for travel later
```

The forward price may differ from the spot price because money in each currency earns different interest rates between today and the forward settlement date.

## Spot Rate

A [[Spot exchange rate]] is the exchange rate for immediate currency delivery.

In FX markets, "immediate" usually means settlement two business days after the trade date:

```text
T + 2
```

Example:

```text
USD/EUR = 1.2000
```

means one euro costs 1.2000 US dollars.

## Forward Rate

A [[Forward exchange rate]] is an exchange rate agreed today for a currency exchange at a future date.

A [[Forward contract]] specifies:

| Contract Term | Meaning |
|---|---|
| Currency pair | The two currencies exchanged |
| Notional amount | The amount of currency to exchange |
| Forward rate | The exchange rate locked in today |
| Settlement date | The future date of exchange |

Forward contracts are commonly quoted for maturities such as:

```text
30 days, 60 days, 90 days, 180 days, 1 year
```

## Forward Premium And Forward Discount

For a quote:

```text
Price currency / Base currency
```

the premium or discount refers to the **base currency**.

If:

$$
F > S
$$

then the base currency is at a forward premium.

If:

$$
F < S
$$

then the base currency is at a forward discount.

The basic amount of the premium or discount is:

$$
\text{Forward premium or discount} = F - S
$$

where:

| Symbol | Meaning |
|---|---|
| $F$ | Forward rate |
| $S$ | Spot rate |

## Example: Premium

Suppose:

```text
USD/EUR spot = 1.2000
USD/EUR forward = 1.2500
```

The base currency is EUR.

Since:

$$
1.2500 > 1.2000
$$

EUR trades at a forward premium.

The premium is:

$$
1.2500 - 1.2000 = 0.0500 \text{ USD/EUR}
$$

## Forward Points And All-In Forward Rates

Forward quotes are often shown as points added to or subtracted from the spot quote.

For most non-JPY pairs:

```text
1 pip = 0.0001
```

If the forward points are positive, add them to the spot quote.

If the forward points are negative, subtract them from the spot quote.

The all-in forward quote is:

$$
\text{All-in forward} = \text{Spot quote} + \text{Forward points}
$$

where forward points are converted into decimal form.

## Worked Example: All-In Forward Quote

Suppose:

```text
AUD/CAD spot = 1.0511 / 1.0519
30-day forward points = +3.9 / +4.1
```

Because the points are quoted in pips:

$$
3.9 \text{ pips} = 0.00039
$$

$$
4.1 \text{ pips} = 0.00041
$$

The 30-day forward bid is:

$$
1.0511 + 0.00039 = 1.05149
$$

The 30-day forward offer is:

$$
1.0519 + 0.00041 = 1.05231
$$

So the all-in 30-day forward quote is:

```text
AUD/CAD = 1.05149 / 1.05231
```

## Interest Rate Intuition

Under [[Covered interest rate parity]], the forward premium or discount offsets the interest-rate differential.

For a quote stated as:

```text
Price currency / Base currency
```

the covered-interest-parity forward rate is:

$$
F_{P/B} = S_{P/B} \times \frac{1 + i_P(T)}{1 + i_B(T)}
$$

where:

| Term | Meaning |
|---|---|
| $F_{P/B}$ | Forward exchange rate in price currency per one base currency |
| $S_{P/B}$ | Spot exchange rate in price currency per one base currency |
| $i_P$ | Interest rate for the price currency |
| $i_B$ | Interest rate for the base currency |
| $T$ | Fraction of a year to settlement |

The currency with the higher interest rate generally trades at a forward discount.

Why?

If one currency offers a higher interest rate and no forward adjustment existed, investors could borrow in the low-rate currency, invest in the high-rate currency, lock in the future exchange rate with a forward, and earn arbitrage profits. The forward discount removes that free lunch.

```text
Higher interest rate currency
  |
  v
More attractive to invest in
  |
  v
Forward market must offset the yield advantage
  |
  v
Higher-rate currency trades at forward discount
```

## Exam Traps

| Trap | Correction |
|---|---|
| Thinking the premium applies to the numerator currency | The premium or discount applies to the base currency. |
| Forgetting that the base currency is the denominator | In `USD/EUR`, EUR is the base currency. |
| Adding negative forward points | Negative points are subtracted. |
| Treating points as whole units | Convert pips to decimals. |
| Forgetting bid and offer are adjusted separately | Add bid points to spot bid and offer points to spot offer. |
| Confusing forward premium with expected appreciation | A forward premium is a quoted forward relationship, not necessarily a forecast. |

## Memory Hook

```text
Forward premium/discount belongs to the base.
F > S -> base at premium.
F < S -> base at discount.
```

## Related Concepts

- [[Spot exchange rate]]
- [[Forward exchange rate]]
- [[Forward contract]]
- [[Forward premium]]
- [[Forward discount]]
- [[Covered interest rate parity]]
- [[Bid–offer spread]]
- [[Pip]]
- [[Mark-to-market]]
