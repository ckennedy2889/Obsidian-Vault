---
title: "Commodity Swaps"
subject: "Alternative Investments"
tags: [CFA-L2, alternative-investments, commodities, swaps, derivatives]
aliases:
  - Commodity total return swap
  - Commodity excess return swap
  - Commodity basis swap
  - Commodity volatility swap
  - Commodity variance swap
---

# Commodity Swaps

Commodity swaps are OTC contracts that let an investor or hedger obtain a customized commodity exposure without storing the commodity or managing a rolling futures position.

The practical idea is simple: one party wants exposure to a commodity risk factor, and a dealer packages that exposure into a swap.

## Why Commodity Swaps Exist

Commodity futures are standardized. Real users of commodities often have exposures that are not standardized:

- Different grades.
- Different locations.
- Different delivery dates.
- Different benchmark prices.
- Exposure to volatility rather than price direction.

A swap can be customized to match the exact risk the user wants to hedge or take.

## Main Types

| Swap type | Variable payment based on | Typical use |
|---|---|---|
| [[Total return swap]] | Commodity futures total return, including collateral return | Gain broad commodity exposure |
| [[Excess return swap]] | Commodity price/index return above a benchmark, excluding collateral return | Hedge or express price exposure |
| [[Basis swap]] | Difference between two commodity prices | Hedge imperfect benchmark exposure |
| [[Commodity volatility swap]] | Realized commodity price volatility | Trade volatility without directional price bet |
| Commodity variance swap | Realized commodity price variance | Trade variance; variance is volatility squared |

## Total Return Swap

In a commodity total return swap, the long receives the total return on a commodity or commodity index and pays a fixed or floating financing rate.

The total return includes:

- Price return.
- Roll return.
- Collateral return.

Payoff to the long for a period:

$$
\text{Net payment} =
(\text{Commodity total return} - \text{Fixed swap payment rate})
\times \text{Notional}
$$

### Worked Example

A manager enters a two-year total return swap on oil with notional value of \$10 million. The manager is long the commodity return and pays 25 bps per month.

Month 1: WTI rises from \$41.50 to \$42.10.

Price return:

$$
\frac{42.10-41.50}{41.50}=1.45\%
$$

Net payment to the long:

$$
(1.45\%-0.25\%) \times 10{,}000{,}000 = 1.20\% \times 10{,}000{,}000 = \$120{,}000
$$

Month 2: WTI falls from \$42.10 to \$41.20.

Price return:

$$
\frac{41.20-42.10}{42.10}=-2.14\%
$$

Net payment from the long to the dealer:

$$
(-2.14\%-0.25\%) \times 10{,}000{,}000 = -2.39\% \times 10{,}000{,}000 = -\$239{,}000
$$

The long receives when commodity total return is positive enough and pays when it is negative.

## Excess Return Swap

An excess return swap pays based on commodity return above a benchmark or fixed level. It excludes the collateral return that would be part of a fully collateralized futures position.

In plain English:

- Total return swap = commodity futures return plus collateral yield.
- Excess return swap = commodity price/index excess return only.

This is useful when the investor wants the futures price exposure without the collateral component.

## Basis Swap

A basis swap pays based on the difference between two related commodity prices.

It is useful when the user is exposed to a commodity that does not have a liquid futures market, but a related benchmark does.

Example:

- A refiner uses a local crude grade with no liquid futures.
- Brent or WTI futures are liquid.
- The refiner hedges the broad oil price with liquid futures.
- The basis swap hedges the difference between the local crude price and the benchmark.

The risk being hedged is not the absolute commodity price; it is the changing spread between the two prices.

## Commodity Volatility and Variance Swaps

A commodity volatility swap pays based on realized volatility compared with a fixed volatility level set at inception.

The volatility buyer receives when realized volatility is higher than the fixed level. The volatility seller receives when realized volatility is lower.

Variance swaps are similar, but the payoff is based on variance:

$$
\text{Variance} = \text{Volatility}^2
$$

These instruments are useful for investors who want exposure to how much the commodity moves, not whether the commodity price rises or falls.

## Direction vs Magnitude

This distinction is exam-critical.

| Instrument | Pays based on price direction? | Pays based on movement magnitude? |
|---|---:|---:|
| Total return swap | Yes | Indirectly |
| Excess return swap | Yes | Indirectly |
| Basis swap | Spread direction | Spread movement |
| Volatility swap | No | Yes |
| Variance swap | No | Yes, squared |

A volatility swap can pay off when prices move sharply up or sharply down. Direction is not the point; realized movement is.

## Why Use Swaps Instead of Futures?

| Reason | Explanation |
|---|---|
| Customization | Swap terms can match grade, location, and timing |
| Operational simplicity | Investor avoids rolling futures directly |
| Exposure precision | Basis or volatility exposure can be isolated |
| Access | Some investors cannot easily trade futures or physical commodities |
| Hedging | Commercial users can match real input or output risks more closely |

## Exam Traps

- **Total return includes collateral return.** Excess return excludes it.
- **Long total return swap receives when commodity total return is positive.** Do not reverse the cash flow direction.
- **Basis swap hedges the spread between two commodity prices, not the outright price.**
- **Volatility swaps depend on movement magnitude, not price direction.**
- **Variance is volatility squared.** A variance swap is not just another name for a volatility swap.
- **Swaps are OTC and customized.** That creates counterparty and liquidity considerations.

## Memory Hook

**Total gets the whole futures package. Excess strips out collateral. Basis hedges the gap. Volatility trades the size of the move.**
