---
title: Triangular Arbitrage
subject: Economics
tags: [CFA-L2, Economics, ExchangeRates, Arbitrage]
aliases: [triangular arbitrage in FX, currency triangular arbitrage, FX triangular arbitrage]
---

# Triangular Arbitrage

## The Real-World Analogy

Imagine three currency booths arranged in a triangle:

```text
USD -> MXN -> AUD -> USD
```

If the three booths quote inconsistent exchange rates, you might be able to walk around the triangle and end with more USD than you started with. That is [[Triangular arbitrage]].

The CFA version is the same idea, but with bid-offer spreads. You must always trade at the side of the quote that a real customer would get.

## Definition

[[Triangular arbitrage]] exploits inconsistencies among three pairwise exchange rates.

It exists when:

```text
Direct quote for a currency pair
  !=
Cross rate implied by the other two currency pairs
```

After transaction costs and bid-offer spreads, a true arbitrage opportunity means:

```text
Start with one currency
Trade through two others
Return to the starting currency
End with more than you started with
```

## The Core Cross-Rate Idea

If exchange rates are quoted as:

$$
\frac{A}{B}
\quad \text{and} \quad
\frac{B}{C}
$$

then the implied cross rate is:

$$
\frac{A}{C} = \frac{A}{B} \times \frac{B}{C}
$$

The shared currency cancels:

$$
\frac{A}{B} \times \frac{B}{C} = \frac{A}{C}
$$

## Inverting Quotes

If you are given:

$$
\frac{A}{B}_{bid/offer}
$$

and need:

$$
\frac{B}{A}
$$

then bid and offer swap when inverted:

$$
\left(\frac{B}{A}\right)_{bid} = \frac{1}{\left(\frac{A}{B}\right)_{offer}}
$$

$$
\left(\frac{B}{A}\right)_{offer} = \frac{1}{\left(\frac{A}{B}\right)_{bid}}
$$

Why? Because the dealer's bid in one direction is the customer's offer in the opposite direction.

## The Trading Rule

Use the same rule as normal FX quote conversion:

```text
Up the quote -> bid -> multiply
Down the quote -> ask -> divide
```

For a quote:

```text
Price currency / Base currency
```

Moving from base to price is up the quote. Moving from price to base is down the quote.

## Worked Example

Given:

```text
USD/AUD = 0.6000 / 0.6015
USD/MXN = 0.0933 / 0.0935
Dealer quote: MXN/AUD = 6.3000 / 6.3025
```

Start with USD 1,000,000 and test the path:

```text
USD -> MXN -> AUD -> USD
```

### Step 1: Convert USD To MXN

Quote:

```text
USD/MXN = 0.0933 / 0.0935
```

Going from USD to MXN means moving down the quote, so use the ask and divide:

$$
\frac{1{,}000{,}000}{0.0935} = 10{,}695{,}187.17 \text{ MXN}
$$

### Step 2: Convert MXN To AUD

Quote:

```text
MXN/AUD = 6.3000 / 6.3025
```

Going from MXN to AUD means moving down the quote, so use the ask and divide:

$$
\frac{10{,}695{,}187.17}{6.3025} = 1{,}696{,}975.04 \text{ AUD}
$$

### Step 3: Convert AUD To USD

Quote:

```text
USD/AUD = 0.6000 / 0.6015
```

Going from AUD to USD means moving up the quote, so use the bid and multiply:

$$
1{,}696{,}975.04 \times 0.6000 = 1{,}018{,}185.02 \text{ USD}
$$

### Step 4: Calculate Profit

$$
1{,}018{,}185.02 - 1{,}000{,}000 = 18{,}185.02 \text{ USD}
$$

There is an arbitrage profit of about USD 18,185.

## Why The Arbitrage Exists

The dealer's `MXN/AUD` quote is inconsistent with the rates implied by the other two quotes. The dealer is effectively selling AUD too cheaply relative to the USD/AUD and USD/MXN markets.

Arbitrageurs exploit this until buying pressure and selling pressure force quotes back into consistency.

```text
Mispriced quote
  |
  v
Arbitrageurs buy cheap currency route
  |
  v
Arbitrageurs sell expensive currency route
  |
  v
Dealer quotes adjust
  |
  v
Arbitrage disappears
```

## Exam Process

Use this checklist:

1. Draw the currency triangle.
2. Pick a starting currency and direction.
3. At each leg, decide whether you are moving up or down the quote.
4. Use bid/multiply when going up.
5. Use ask/divide when going down.
6. Compare ending amount with starting amount.
7. If ending amount is higher, the difference is arbitrage profit.
8. If not, test the other direction.

## Exam Traps

| Trap | Correction |
|---|---|
| Using midquotes | Use bid and offer quotes exactly. |
| Forgetting to test both directions | Arbitrage may exist in only one direction. |
| Inverting without swapping bid and offer | Inversion always swaps bid and offer. |
| Using the implied cross rate in the actual trade | Trade using the dealer quotes provided. |
| Multiplying when moving down the quote | Down the quote means ask and divide. |
| Dividing when moving up the quote | Up the quote means bid and multiply. |

## Memory Hook

```text
Triangle test:
Walk the triangle.
Use real bid/ask prices.
If you return home richer, arbitrage exists.
```

## Related Concepts

- [[Triangular arbitrage]]
- [[Arbitrage]]
- [[Cross rate]]
- [[Bid–offer spread]]
- [[Exchange rate]]
- [[Spot exchange rate]]
- [[Pip]]
