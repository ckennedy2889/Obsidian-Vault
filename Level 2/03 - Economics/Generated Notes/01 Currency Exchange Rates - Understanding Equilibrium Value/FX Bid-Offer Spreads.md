---
title: FX Bid-Offer Spreads
subject: Economics
tags: [CFA-L2, Economics, ExchangeRates, BidOfferSpread]
aliases: [FX bid-offer spread, currency bid-offer spread, foreign exchange spread, bid-ask spread in FX]
---

# FX Bid-Offer Spreads

## The Real-World Analogy

An FX dealer is like a currency shop at an airport, but the exam version is cleaner and more precise.

The dealer posts two prices:

```text
One price to buy the base currency from you
One price to sell the base currency to you
```

The dealer buys low and sells high. The difference is the [[Bid–offer spread]].

## Quote Convention

An exchange rate quote such as:

```text
USD/EUR = 1.4124 / 1.4128
```

means:

| Part | Meaning |
|---|---|
| USD | Price currency |
| EUR | Base currency |
| 1.4124 | Dealer bid |
| 1.4128 | Dealer offer or ask |

The quote says one euro costs about 1.4124-1.4128 US dollars.

The dealer:

| Dealer Action | Price Used |
|---|---|
| Dealer buys the base currency | Bid |
| Dealer sells the base currency | Offer |

So for `USD/EUR`:

| Customer Wants To | Customer Action | Dealer Quote Used |
|---|---|---|
| Sell EUR for USD | Sell base currency | Bid |
| Buy EUR with USD | Buy base currency | Offer |

## Formula

The spread is:

$$
\text{Bid-offer spread} = \text{Offer price} - \text{Bid price}
$$

For `USD/EUR = 1.4124 / 1.4128`:

$$
\text{Spread} = 1.4128 - 1.4124 = 0.0004
$$

If the quote is shown to four decimal places, one [[Pip]] is usually:

$$
0.0001
$$

So:

$$
0.0004 = 4 \text{ pips}
$$

## Up-The-Bid, Down-The-Ask

This is the best CFA shortcut.

For a quote:

```text
Price currency / Base currency
```

Use:

```text
Up the quote -> bid -> multiply
Down the quote -> ask -> divide
```

Example:

```text
AUD/GBP = 1.5060 / 1.5067
```

Convert GBP 1,000,000 into AUD.

GBP is the base currency, so you are moving up from denominator to numerator:

```text
GBP -> AUD = up the quote
```

Use the bid and multiply:

$$
1{,}000{,}000 \times 1.5060 = 1{,}506{,}000 \text{ AUD}
$$

Convert AUD 1,000,000 into GBP.

AUD is the price currency, so you are moving down from numerator to denominator:

```text
AUD -> GBP = down the quote
```

Use the ask and divide:

$$
\frac{1{,}000{,}000}{1.5067} = 663{,}702.13 \text{ GBP}
$$

## Why Spreads Exist

The spread compensates the dealer for:

| Dealer Problem | Why It Widens The Spread |
|---|---|
| Inventory risk | The dealer may be left holding a currency that moves against them |
| Order-processing costs | Trading infrastructure, settlement, and staff cost money |
| Information risk | Better-informed traders may trade before prices adjust |
| Liquidity risk | Thinly traded pairs are harder to offset |

The spread is also an implicit transaction cost to the customer.

## Factors Affecting The Bid-Offer Spread

### Dealer Quote Factors

| Factor | Spread Effect |
|---|---|
| Interbank spread | Wider interbank spreads lead to wider customer spreads |
| Transaction size | Very large liquidity-demanding trades often get wider spreads |
| Dealer-client relationship | Preferred clients may receive tighter spreads |

### Interbank Spread Factors

| Factor | Spread Effect |
|---|---|
| Currency pair liquidity | Major pairs have tighter spreads; obscure crosses have wider spreads |
| Time of day | Spreads are narrowest when major trading centers overlap |
| Market volatility | Higher volatility widens spreads |

For forward FX quotes, spreads also tend to increase with maturity because longer contracts have:

| Forward-Specific Factor | Reason |
|---|---|
| Lower liquidity | Fewer traders in longer maturities |
| More counterparty credit risk | More time for a counterparty to default |
| More interest rate risk | Forward values depend on interest-rate differentials |

## Worked Example

A dealer quotes:

```text
USD/EUR = 1.1648 / 1.1652
```

### Spread

$$
1.1652 - 1.1648 = 0.0004
$$

That is 4 pips.

### Customer Buys EUR 2,000,000

The customer buys the base currency, so use the offer:

$$
2{,}000{,}000 \times 1.1652 = 2{,}330{,}400 \text{ USD}
$$

### Customer Sells EUR 2,000,000

The customer sells the base currency, so use the bid:

$$
2{,}000{,}000 \times 1.1648 = 2{,}329{,}600 \text{ USD}
$$

The round-trip cost is:

$$
2{,}330{,}400 - 2{,}329{,}600 = 800 \text{ USD}
$$

## Exam Traps

| Trap | Correction |
|---|---|
| Using the bid when buying the base currency | Buy base at the offer. |
| Using the offer when selling the base currency | Sell base at the bid. |
| Forgetting that the base currency is the denominator | In `USD/EUR`, EUR is the base currency. |
| Treating all pip values as 0.0001 | JPY quotes often use 0.01 as one pip. |
| Assuming larger trades always get tighter spreads | Large liquidity-demanding trades may widen spreads. |
| Ignoring maturity for forward spreads | Longer forward maturities usually have wider spreads. |

## Memory Hook

```text
Dealer buys low at bid.
Dealer sells high at ask.
You always get the worse side.
```

And:

```text
Up = bid = multiply.
Down = ask = divide.
```

## Related Concepts

- [[Bid–offer spread]]
- [[Bid price]]
- [[Offer price]]
- [[Pip]]
- [[Exchange rate]]
- [[Spot exchange rate]]
- [[Forward exchange rate]]
- [[Triangular arbitrage]]
