---
title: Mark to Market
subject: Economics
tags: [CFA-L2, economics, derivatives, financial-statement-analysis, forwards, futures, fair-value]
aliases: [Mark-to-market, Marking to market, MTM, MtM, Daily settlement, Forward mark-to-market, Mark-to-market value]
---

# Mark to Market

## The Real-World Analogy

Imagine you agreed last month to buy a house in six months for $500,000.

Today, similar houses are selling for $550,000.

You have not bought the house yet. No cash has changed hands. But your contract is valuable because it lets you buy something for less than its current market price.

If someone asked:

> What is that contract worth today?

You would not answer:

```text
Zero, because I have not settled yet.
```

You would answer:

```text
It is worth something because market prices moved.
```

That is the broad idea of [[Level 2/Generated Notes/03 - Economics/Mark to Market]]:

> Revalue a position using current market prices or current fair value, not the old original price.

The phrase becomes tricky because CFA uses it in several related but different ways.

## One-Minute Version

[[Level 2/Generated Notes/03 - Economics/Mark to Market]] means updating the value of a financial asset, liability, or contract to its current market value or fair value.

There are three CFA contexts you should keep separate:

| Context | What mark to market means |
|---|---|
| General valuation / accounting | Revalue an asset or liability to current market value or [[fair value]] |
| FX [[forward contract]] | Calculate the current value of an old forward by comparing it with today's forward rate |
| [[futures contract]] | Daily settlement of gains/losses through the margin account |

The clean mental split:

```text
Forward:
Value accumulates until settlement.
MtM value = present value of closeout gain/loss.

Future:
Gain/loss is settled daily.
After daily settlement, contract value resets to zero.

Accounting fair value:
Balance sheet is updated to current fair value.
Where the gain/loss goes depends on classification.
```

## LOS Coverage

The most direct CFA Level II LOS is in [[Economics]]:

> Calculate the mark-to-market value of a forward contract.

The idea also appears in [[CFA_Glossary/Derivatives]] through [[futures contract]] daily settlement and in [[Financial Statement Analysis]] through [[fair value]] measurement.

For exam purposes, you should be able to:

| CFA task | What you need to know |
|---|---|
| Define mark to market | Revalue to current market/fair value |
| Value an FX forward before expiration | Offset the old forward with a current forward, then discount the settlement cash flow |
| Distinguish forwards from futures | Forwards accumulate value; futures settle daily |
| Explain variation margin | Daily cash movement from futures mark-to-market |
| Interpret accounting effect | Fair value gains/losses may hit income statement or OCI |

## The Big Idea

Mark to market asks:

> What is the position worth today, given today's market conditions?

That sounds simple, but it changes depending on the instrument.

For an asset with an observable market price:

```text
Mark-to-market value = current market price
```

For a forward contract:

```text
Mark-to-market value = PV of the gain/loss from closing the old contract today
```

For a futures contract:

```text
Marking to market = daily cash settlement of price changes
```

Those are related because all three use current market information.

They differ because the cash flow mechanics differ.

## Why Mark to Market Exists

Historical cost tells you what something cost in the past.

Market value tells you what it is worth now.

If the market moved, old cost can become stale.

Example:

```text
Bought bond at 100
Market price now 92
```

If you report the bond at 100, the balance sheet may hide the current economic loss.

Marking to market updates the value to 92.

The deep reason:

```text
Markets move
  |
  v
Old transaction prices become stale
  |
  v
Current economic exposure changes
  |
  v
Mark to market reveals current value
```

The trade-off:

| Benefit | Cost |
|---|---|
| More current information | More volatility in reported values |
| Shows current gains/losses | Can make income/equity jump around |
| Reduces hidden exposures | Requires reliable fair value estimates |

## General Fair Value Meaning

In the broad accounting sense, mark to market means revaluing an item to current [[fair value]].

If a security is carried at fair value, its balance sheet amount updates as market value changes.

Example:

```text
Original cost: $100
Current fair value: $108
Mark-to-market gain: $8
Balance sheet value: $108
```

Where the gain goes depends on accounting classification.

| Classification | Balance sheet | Unrealized fair value change |
|---|---|---|
| [[Fair Value Through Profit or Loss]] / FVPL | Fair value | Income statement |
| [[Fair Value Through OCI]] / FVOCI | Fair value | Other comprehensive income |
| [[Amortized Cost]] | Amortized cost | Usually ignored in carrying value, disclosed separately if required |

This is the FSA trap:

> Marking something to fair value does not automatically mean the gain hits net income.

It depends on classification.

## Forward Contract Mark-to-Market

An FX [[forward contract]] usually has zero value when initiated.

Why zero?

Because the initial forward rate is set so neither side has an advantage at inception.

But after inception, market rates change.

The old contract may become favorable or unfavorable.

The mark-to-market value is:

> The present value of the gain or loss you would lock in by offsetting the old forward at today's forward rate.

The forward contract does not settle daily.

So value can accumulate.

```text
t=0
Enter forward at F0
Value usually = 0

t=now
Market forward rate has changed to Ft
Old contract may have positive or negative value

t=maturity
Forward cash flow settles
```

## Why Use an Offsetting Forward?

To mark a forward to market, imagine closing it out.

If you are long the base currency under the original forward, you entered a contract to buy the base currency later.

To close that exposure today, you would enter the opposite contract:

```text
Original: Buy base currency forward
Offset:   Sell base currency forward
```

If you are short the base currency:

```text
Original: Sell base currency forward
Offset:   Buy base currency forward
```

The offsetting forward locks in the gain or loss at the original settlement date.

Then you discount that future gain/loss to today.

The workflow:

```text
1. Identify original position: long or short base currency
2. Enter imaginary offsetting forward at today's market forward rate
3. Calculate cash flow at original settlement date
4. Discount that cash flow back to today
```

## Forward Mark-to-Market Formula

For a long forward position:

$$
V_t = \frac{(F_t - F_0) \times Q}{1 + r \times \frac{\text{days}}{360}}
$$

Where:

| Symbol | Meaning |
|---|---|
| $V_t$ | Mark-to-market value today |
| $F_t$ | Current forward rate for the remaining maturity |
| $F_0$ | Original contracted forward rate |
| $Q$ | Contract size |
| $r$ | Interest rate for the currency of the cash flow |

For a short forward position, the sign reverses:

$$
V_t = \frac{(F_0 - F_t) \times Q}{1 + r \times \frac{\text{days}}{360}}
$$

The intuition:

```text
Long forward benefits when current forward price rises above original forward price.
Short forward benefits when current forward price falls below original forward price.
```

## Bid-Offer Trap in FX Forwards

The exam may give bid and offer quotes.

The key is that mark-to-market assumes an offsetting position.

If the original position is long the base currency, you close by selling the base currency.

Selling uses the dealer's bid.

If the original position is short the base currency, you close by buying the base currency.

Buying uses the dealer's offer.

| Original position | Offset action | Quote side |
|---|---|---|
| Long base currency | Sell base currency forward | Bid |
| Short base currency | Buy base currency forward | Offer |

Memory hook:

```text
You sell at bid.
You buy at offer.
```

## Why Discount the Forward Gain or Loss?

The forward gain or loss is locked in today, but it is paid at the original settlement date.

That means it is a future cash flow.

Future cash flows must be discounted to get today's value.

Mechanism:

```text
Settlement gain/loss
  |
  v
Cash occurs at maturity, not today
  |
  v
Discount to present value
  |
  v
Mark-to-market value today
```

Use the interest rate of the currency in which the cash flow is denominated.

If the gain/loss is in AUD, use the AUD interest rate.

If it is in USD, use the USD interest rate.

## Worked Forward Example

Suppose three months ago, you entered a six-month forward contract to buy GBP 10,000,000 against AUD.

Original forward rate:

```text
F0 = 1.8100 AUD/GBP
```

Today, there are three months left.

Current three-month forward quote:

```text
1.8340 / 1.8345 AUD/GBP
```

Three-month AUD interest rate:

```text
2.40% annualized
```

### Step 1: Identify the Position

You originally agreed to buy GBP.

So you are long GBP.

To close, you would sell GBP forward.

Selling GBP uses the bid:

```text
Ft = 1.8340 AUD/GBP
```

### Step 2: Calculate Settlement Gain

You can buy GBP under the old contract at:

```text
1.8100 AUD/GBP
```

You can sell GBP under the offsetting contract at:

```text
1.8340 AUD/GBP
```

Profit per GBP:

$$
1.8340 - 1.8100 = 0.0240 \text{ AUD/GBP}
$$

Contract size:

$$
10{,}000{,}000 \text{ GBP}
$$

Settlement gain:

$$
0.0240 \times 10{,}000{,}000 = 240{,}000 \text{ AUD}
$$

### Step 3: Discount to Today

There are 90 days left.

Discount factor denominator:

$$
1 + 0.024 \times \frac{90}{360}
$$

Compute:

$$
\frac{90}{360} = 0.25
$$

$$
0.024 \times 0.25 = 0.006
$$

$$
1 + 0.006 = 1.006
$$

Present value:

$$
\frac{240{,}000}{1.006} = 238{,}568.59
$$

So the mark-to-market value is approximately:

$$
\text{AUD }238{,}569
$$

Why positive?

Because you locked in buying GBP at 1.8100, and today you could sell that GBP forward at 1.8340. The old contract is favorable.

## Futures Marking to Market

For [[futures contract|futures contracts]], marking to market means daily settlement.

Futures accounts are adjusted every day for that day's gain or loss.

The daily cash flow is called [[variation margin]].

If the futures price rises:

```text
Long futures position gains.
Short futures position loses.
```

If the futures price falls:

```text
Long futures position loses.
Short futures position gains.
```

The clearinghouse moves cash between margin accounts.

That is why futures are different from forwards.

## Why Futures Reset to Zero

A forward contract can accumulate value because gains and losses are not settled daily.

A futures contract is marked to market each day, so the day's gain/loss is paid immediately through the margin account.

After the daily settlement:

```text
Futures contract value = 0
```

This does not mean the trader has no gain or loss.

It means the gain or loss has already been transferred as cash.

The value is no longer sitting inside the contract.

It is in the margin account.

```text
Forward:
Gain/loss accumulates inside contract.

Future:
Gain/loss is pulled out daily as cash.
```

This is a high-probability exam distinction.

## Futures Daily Settlement Example

Suppose you are long one futures contract.

Yesterday's settlement price:

```text
100
```

Today's settlement price:

```text
103
```

Contract multiplier:

```text
$1,000 per point
```

Daily gain:

$$
(103 - 100) \times 1{,}000 = 3{,}000
$$

The clearinghouse credits your margin account:

$$
\$3{,}000
$$

After this daily settlement, the futures contract itself is reset so its value is zero at the new settlement price.

Tomorrow's gain or loss is measured from 103.

## Forward vs Futures Mark-to-Market

| Feature | Forward contract | Futures contract |
|---|---|---|
| Trading venue | OTC/private | Exchange-traded |
| Initial value | Usually zero | Usually zero after margin deposit |
| Value over life | Can become positive or negative | Reset to zero after daily settlement |
| Settlement of gains/losses | At maturity or closeout | Daily |
| MTM calculation | PV of closeout gain/loss | Daily price change credited/debited to margin |
| Credit risk | Higher counterparty risk | Lower due to clearinghouse and margin |

Memory hook:

```text
Forward MTM = value of old deal today.
Futures MTM = daily cash settlement.
```

## Mark to Market vs Realized Gain

Mark-to-market gains can be unrealized.

If an asset rises in value but you have not sold it, the gain may be unrealized.

Example:

```text
Bought at 100
Current fair value 108
Unrealized gain 8
```

Whether that gain appears in net income depends on accounting classification.

This matters for analysis:

| Gain type | Meaning |
|---|---|
| Realized gain | Position has been sold or settled |
| Unrealized gain | Position still held, value changed |
| MTM gain | Current value increased relative to carrying/contract value |

The analyst should ask:

> Did this gain produce cash, or is it only a revaluation?

## Common Wrong Reasoning

### Wrong: "Mark to market always means cash changes hands."

Why it is wrong: General fair-value revaluation may create an unrealized gain/loss. Cash changes hands daily for futures, but not necessarily for accounting fair value or forwards.

Correct idea:

```text
Futures MTM -> daily cash settlement.
Forward/accounting MTM -> current value measurement.
```

### Wrong: "Forward and futures mark-to-market work the same way."

Why it is wrong: Forwards can accumulate value until settlement. Futures settle daily through margin accounts.

Correct idea:

```text
Forward value accumulates.
Future value resets after daily settlement.
```

### Wrong: "A futures contract has no gain because its value is reset to zero."

Why it is wrong: The gain/loss has been transferred into or out of the margin account. The contract value resets, but the trader's wealth changed.

Correct idea:

```text
Futures gain/loss appears as variation margin.
```

### Wrong: "For forward MTM, just calculate the settlement gain and stop."

Why it is wrong: The settlement gain occurs at maturity. The mark-to-market value today is the present value of that future gain/loss.

Correct idea:

```text
Forward MTM = discounted closeout cash flow.
```

### Wrong: "Use the midquote when offsetting an FX forward."

Why it is wrong: You transact with the dealer. If you sell, use bid. If you buy, use offer.

Correct idea:

```text
Long base -> close by selling -> bid.
Short base -> close by buying -> offer.
```

### Wrong: "Fair value changes always hit net income."

Why it is wrong: FVPL changes hit income, but FVOCI changes go through OCI.

Correct idea:

```text
Fair value on balance sheet does not always mean fair value change in net income.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Current value of an old forward | Compare old forward rate to current forward rate |
| Long base currency forward | Close by selling base at bid |
| Short base currency forward | Close by buying base at offer |
| Forward MTM value today | Discount settlement gain/loss |
| Futures margin account adjusted daily | Marking to market / daily settlement |
| Variation margin | Cash movement from daily futures MTM |
| Futures value after daily settlement | Zero |
| Asset carried at fair value | Balance sheet updated to fair value |
| FVPL | Fair value changes through income statement |
| FVOCI | Fair value changes through OCI |

## Minimum Memorization

```text
Mark to market = revalue to current market/fair value.

Forward MTM:
Current forward rate vs original forward rate
Calculate settlement gain/loss
Discount to today

Long forward benefits if current forward > original forward.
Short forward benefits if current forward < original forward.

Futures MTM:
Daily settlement
Variation margin moves cash
Contract value resets to zero after settlement
```

Most important distinction:

```text
Forward = value accumulates.
Future = gains/losses settle daily.
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. What does mark to market mean in general?
2. Why does an old forward contract gain or lose value after inception?
3. Why does a forward MTM calculation use an offsetting contract?
4. Why do you discount the forward closeout gain/loss?
5. If you are long the base currency, which quote side do you use to close?
6. If you are short the base currency, which quote side do you use to close?
7. Why can a forward accumulate value but a future resets to zero?
8. What is variation margin?
9. Why does a futures value of zero after settlement not mean no profit or loss?
10. How can fair value changes affect net income differently under FVPL vs FVOCI?

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Mark to Market]]
- [[Marking to market]]
- [[Forward contract]]
- [[Futures contract]]
- [[Daily settlement]]
- [[Variation margin]]
- [[Settlement price]]
- [[Fair value]]
- [[Fair Value Through Profit or Loss]]
- [[Fair Value Through OCI]]
- [[Amortized Cost]]
- [[Unrealized gain]]
- [[Unrealized loss]]
- [[Spot rate]]
- [[Forward rate]]
- [[Bid-offer spread]]
- [[Covered interest rate parity]]
