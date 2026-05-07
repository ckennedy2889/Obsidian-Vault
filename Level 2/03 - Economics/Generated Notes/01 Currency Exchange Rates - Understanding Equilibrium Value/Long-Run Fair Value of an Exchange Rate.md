---
title: Long-Run Fair Value of an Exchange Rate
subject: Economics
tags: [CFA-L2, Economics, ExchangeRates, FairValue, PPP]
aliases: [exchange rate fair value, long-run exchange rate fair value, assessing exchange rate fair value, real exchange rate mean reversion]
---

# Long-Run Fair Value of an Exchange Rate

## The Real-World Analogy

An exchange rate can wander away from fair value like a stock price can wander away from intrinsic value.

In the short run, the currency may be pushed around by capital flows, sentiment, policy surprises, and risk appetite. In the long run, the currency has to make economic sense: countries must remain competitive, external balances must be financeable, and relative prices cannot drift forever without adjustment.

So fair value is not a precise point. It is more like a gravitational center.

```text
Short run: exchange rates can wander.
Long run: relative prices and external balance pull them back.
```

## Definition

The long-run fair value of an [[Exchange rate]] is an estimate of the exchange-rate level consistent with sustainable relative prices, external balances, and macroeconomic fundamentals.

CFA emphasizes that fair value is an assessment, not a point forecast.

```text
Fair value asks:
Is the currency cheap, expensive, or roughly aligned with fundamentals?
```

## Why Long-Run Fair Value Matters

Exchange-rate fair value matters because currency misvaluation affects:

| Area | Why It Matters |
|---|---|
| International valuation | Foreign asset returns depend on currency movement |
| Export competitiveness | Overvalued currencies hurt exporters |
| Inflation | Depreciation raises import prices |
| Capital flows | Overvaluation can reverse when investors lose confidence |
| Currency crisis risk | Persistent misalignment can make a peg or managed rate fragile |

## Approach 1: Purchasing Power Parity

[[Purchasing Power Parity]] is the most important long-run fair-value anchor.

The intuition:

```text
If one country has higher inflation than another,
its currency should depreciate over time
so that relative purchasing power stays aligned.
```

### Relative PPP

Relative PPP says exchange-rate changes should offset inflation differentials.

For a quote:

```text
Price currency / Base currency
```

the approximate relationship is:

$$
\%\Delta S_{P/B} \approx \pi_P - \pi_B
$$

where:

| Term | Meaning |
|---|---|
| $\%\Delta S_{P/B}$ | Percentage change in the exchange rate |
| $\pi_P$ | Inflation rate of the price currency country |
| $\pi_B$ | Inflation rate of the base currency country |

If the base currency country has higher inflation, the base currency should depreciate.

## Real Exchange Rate

The [[Real exchange rate]] adjusts the nominal exchange rate for relative price levels.

For a `P/B` quote:

$$
q_{P/B} = S_{P/B} \times \frac{CPI_B}{CPI_P}
$$

where:

| Term | Meaning |
|---|---|
| $q_{P/B}$ | Real exchange rate |
| $S_{P/B}$ | Nominal exchange rate |
| $CPI_B$ | Price level of the base currency country |
| $CPI_P$ | Price level of the price currency country |

If relative PPP holds exactly, the real exchange rate is constant.

In practice, the real exchange rate fluctuates around a mean-reverting level.

```text
Real exchange rate far above normal
  |
  v
Currency may be overvalued

Real exchange rate far below normal
  |
  v
Currency may be undervalued
```

## Approach 2: Mean Reversion In The Real Exchange Rate

CFA often frames fair value through mean reversion.

The logic:

```text
Relative PPP does not hold exactly in the short run.
But real exchange rates often move around long-run averages.
```

If a currency's real exchange rate is substantially above its historical mean, the currency may be overvalued and vulnerable to depreciation.

If a currency's real exchange rate is substantially below its historical mean, the currency may be undervalued and may appreciate over time.

## Approach 3: External Balance And Balance Of Payments

Another fair-value lens asks whether a country's external position is sustainable.

Persistent [[Current account]] deficits can signal that a country is absorbing more from the rest of the world than it produces for export.

```text
Persistent current account deficit
  |
  v
Needs capital inflows to finance deficit
  |
  v
External debt may rise
  |
  v
Investors may demand higher risk premium
  |
  v
Currency depreciation risk rises
```

But a deficit is not automatically bad. It depends on what finances it and whether the borrowing supports productive investment.

## Approach 4: Productivity And The Balassa-Samuelson Effect

Fast-growing economies may experience real currency appreciation if productivity rises faster in the tradable-goods sector.

The mechanism:

```text
Tradable-sector productivity rises
  |
  v
Wages rise in tradable sector
  |
  v
Wages also rise in non-tradable sector
  |
  v
Non-tradable prices rise
  |
  v
Overall price level rises
  |
  v
Real exchange rate appreciates
```

This matters because not every real appreciation is overvaluation. Some appreciation may be justified by stronger productivity growth.

## Forecasting Methods And Their Limits

| Method | What It Uses | Best Use | Main Limit |
|---|---|---|---|
| Current spot rate | Today's market price | Short-run benchmark | Does not explain fair value |
| Forward rate | Spot rate and interest differentials | Hedged pricing, not pure forecast | Forward rates are often poor spot forecasts |
| PPP | Inflation and price levels | Long-run fair-value anchor | Weak short-run predictor |
| UIP | Interest differentials | Expected currency change under risk neutrality | Often fails in short/medium run |
| Real exchange-rate mean reversion | Historical real exchange-rate levels | Valuation assessment | The mean itself can shift |
| External balance | Current account, capital flows, debt sustainability | Crisis and sustainability analysis | Deficits can be sustainable if capital is productive |

## Worked Example: PPP Fair Value

Suppose:

| Input | Value |
|---|---:|
| Current spot, $S_{USD/AUD}$ | 1.0000 |
| Expected US inflation | 2% |
| Expected Australian inflation | 5% |

Using ex-ante relative PPP:

$$
\%\Delta S_{USD/AUD} \approx \pi_{USD} - \pi_{AUD}
$$

$$
\%\Delta S_{USD/AUD} \approx 2\% - 5\% = -3\%
$$

Expected fair-value movement:

$$
S_1 \approx 1.0000 \times (1 - 0.03) = 0.9700
$$

The AUD is the base currency. Because Australia has higher expected inflation, AUD is expected to depreciate, so the USD/AUD quote falls.

## Exam Traps

| Trap | Correction |
|---|---|
| Treating PPP as a short-run trading signal | PPP works better over long horizons. |
| Assuming the forward rate is an unbiased spot forecast | Forward rates often fail as future spot predictors. |
| Calling all real appreciation overvaluation | Productivity growth can justify real appreciation. |
| Ignoring quote convention | For `P/B`, the base currency is in the denominator. |
| Treating current account deficits as automatically unsustainable | Sustainability depends on financing quality, debt level, and investor confidence. |
| Forgetting that risk premia matter | Emerging-market currencies may require higher real returns because of sovereign and currency risk. |

## Memory Hook

```text
Spot is where currency is.
PPP is where prices say it should drift.
Real exchange rate is the valuation gauge.
External balance asks whether the path can be financed.
```

## Related Concepts

- [[Exchange rate]]
- [[Purchasing Power Parity]]
- [[Ex Ante Purchasing Power Parity (PPP)]]
- [[International Parity Conditions]]
- [[Real exchange rate]]
- [[Current account]]
- [[Balance of payments]]
- [[Currency Crisis Warning Signs]]
- [[Forward rate parity]]
- [[Uncovered interest rate parity]]
