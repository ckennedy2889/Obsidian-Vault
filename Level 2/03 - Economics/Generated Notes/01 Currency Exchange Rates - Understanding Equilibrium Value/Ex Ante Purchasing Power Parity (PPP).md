---
title: Ex Ante Purchasing Power Parity (PPP)
subject: Economics
tags: [CFA-L2, economics, currency-exchange-rates, international-parity, purchasing-power-parity]
aliases: [Ex ante PPP, Ex-ante PPP, Ex ante version of PPP, Ex-ante version of PPP, Expected PPP, Ex ante purchasing power parity]
---

# Ex Ante Purchasing Power Parity (PPP)

## The Real-World Analogy

Imagine two countries sell the same basket of goods.

Today, the baskets are roughly comparable after converting currencies.

Now suppose investors expect one country's prices to rise much faster next year.

If that high-inflation country's currency did not depreciate, its goods would become too expensive relative to the other country.

So ex ante PPP says:

> The currency with higher expected inflation should be expected to depreciate.

That is the entire intuition.

Inflation weakens purchasing power. Exchange rates should adjust so that expected inflation differences do not permanently make one country's goods too expensive or too cheap.

```text
Higher expected inflation
  |
  v
Domestic purchasing power falls faster
  |
  v
Currency expected to depreciate
  |
  v
Exchange rate adjusts toward purchasing-power parity
```

## One-Minute Version

[[Ex ante PPP]] is the forward-looking version of [[relative PPP]].

It says the expected percentage change in the spot exchange rate should equal the difference in expected inflation rates.

Using CFA's $S_{f/d}$ convention:

$$
\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e
$$

Where:

| Symbol | Meaning |
|---|---|
| $S_{f/d}$ | Spot exchange rate quoted as foreign currency per 1 domestic currency |
| $\%\Delta S_{f/d}^{e}$ | Expected percentage change in the spot rate |
| $\pi_f^e$ | Expected foreign inflation |
| $\pi_d^e$ | Expected domestic inflation |

The memory hook:

```text
Higher expected inflation -> expected currency depreciation.
Lower expected inflation  -> expected currency appreciation.
```

But always check the quote direction.

If the quote is USD/EUR, the euro is the base currency and USD is the price currency. A rise in USD/EUR means one euro costs more dollars, so EUR appreciates against USD and USD depreciates against EUR.

## LOS Coverage

Ex ante PPP belongs in the CFA Level II [[Economics]] reading on currency exchange rates and international parity conditions.

Relevant LOS themes:

| LOS idea | What you need to know |
|---|---|
| Explain international parity conditions | Ex ante PPP links expected spot changes to expected inflation differentials |
| Describe relations among parity conditions | Ex ante PPP connects to [[uncovered interest rate parity]], [[International Fisher Effect]], and [[real interest rate parity]] |
| Evaluate PPP as a forecast tool | PPP is more useful as a long-run anchor than a short-run forecast |

## The Big Idea

PPP begins with purchasing power.

If the same goods cost very different amounts across countries after exchange-rate conversion, there is pressure for prices or exchange rates to adjust.

The clean economic story:

```text
Inflation changes local price levels.
Exchange rates should adjust to offset inflation differences.
```

If Country A has higher inflation than Country B, Country A's goods become more expensive in local currency terms.

To preserve relative purchasing power, Country A's currency should depreciate.

That depreciation makes Country A's goods cheaper to foreigners, offsetting some of the inflation effect.

Ex ante PPP applies that logic before the inflation happens.

It asks:

> Given expected inflation in each country, what exchange-rate change should we expect?

## Absolute PPP vs Relative PPP vs Ex Ante PPP

The three PPP versions are related but not the same.

| Version | Formula idea | Uses | Main question |
|---|---|---|---|
| [[Absolute PPP]] | $S_{f/d} = P_f / P_d$ | Current price levels | What exchange rate equalizes price levels now? |
| [[Relative PPP]] | $\%\Delta S_{f/d} \approx \pi_f - \pi_d$ | Actual inflation | How should the spot rate change given actual inflation differences? |
| [[Ex ante PPP]] | $\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e$ | Expected inflation | How should the spot rate be expected to change? |

The easiest way to remember:

```text
Absolute PPP = price levels.
Relative PPP = actual inflation.
Ex ante PPP = expected inflation.
```

Ex ante means "before the fact."

So ex ante PPP uses expected future inflation, not realized past inflation.

## Why Higher Inflation Means Depreciation

Suppose Australia has higher expected inflation than the United States.

Australian prices are expected to rise faster.

If the AUD exchange rate did not adjust, Australian goods would become more expensive relative to US goods.

That would reduce demand for Australian goods and Australian dollars.

So PPP says the AUD should depreciate.

Mechanism:

```text
Higher expected inflation in Australia
  |
  v
Australian goods expected to become more expensive
  |
  v
AUD purchasing power expected to fall
  |
  v
AUD expected to depreciate
```

This is not arbitrage in the same clean sense as [[covered interest rate parity]].

It is an economic equilibrium tendency.

Goods markets, trade frictions, non-tradable goods, taxes, tariffs, and transport costs keep PPP from holding exactly, especially in the short run.

## The Formula

Using the CFA convention:

$$
\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e
$$

This quote convention matters.

$S_{f/d}$ means:

```text
foreign currency price of 1 domestic currency
```

So if $S_{f/d}$ rises, the domestic currency appreciates because it buys more foreign currency.

If $S_{f/d}$ falls, the domestic currency depreciates.

The formula says:

| If... | Then... |
|---|---|
| $\pi_f^e > \pi_d^e$ | $S_{f/d}$ expected to rise |
| $\pi_f^e < \pi_d^e$ | $S_{f/d}$ expected to fall |

Why?

If foreign inflation is higher than domestic inflation, the foreign currency should depreciate. Since the quote is foreign currency per domestic currency, one domestic currency should buy more foreign currency. Therefore, $S_{f/d}$ rises.

## Quote Direction: The Main Exam Trap

The inflation logic is simple.

The quote direction is where the exam gets you.

Always ask:

```text
Which currency is the base currency?
Which currency is the price currency?
What does an increase in the quoted exchange rate mean?
```

Example:

```text
USD/EUR = 1.10
```

This means:

```text
1 EUR costs 1.10 USD
```

EUR is the base currency.

USD is the price currency.

If USD/EUR rises from 1.10 to 1.13:

```text
1 EUR costs more USD
EUR appreciates
USD depreciates
```

If USD/EUR falls from 1.10 to 1.07:

```text
1 EUR costs fewer USD
EUR depreciates
USD appreciates
```

So do not just say "higher inflation means the exchange rate goes down."

That depends on whether the high-inflation currency is in the numerator or denominator of the quote.

The safer rule:

> Higher expected inflation currency should depreciate.

Then translate that depreciation into the quoted exchange-rate direction.

## Worked Example: USD/AUD

Suppose:

```text
Current spot rate: USD/AUD = 1.00
Expected Australian inflation: 5%
Expected US inflation: 2%
```

The quote USD/AUD means:

```text
1 AUD costs 1.00 USD
```

AUD is the base currency.

USD is the price currency.

Australia has higher expected inflation:

```text
5% > 2%
```

So AUD should depreciate relative to USD.

If AUD depreciates, one AUD should cost fewer USD.

So USD/AUD should fall.

Use the inflation differential:

$$
\%\Delta S_{\text{USD/AUD}}^e
= \pi_{\text{USD}}^e - \pi_{\text{AUD}}^e
$$

Substitute:

$$
\%\Delta S_{\text{USD/AUD}}^e
= 2\% - 5\%
$$

$$
\%\Delta S_{\text{USD/AUD}}^e
= -3\%
$$

Expected future spot:

$$
E(S_1) = S_0(1 + \%\Delta S^e)
$$

$$
E(S_1) = 1.00(1 - 0.03)
$$

$$
E(S_1) = 0.97 \text{ USD/AUD}
$$

Interpretation:

```text
AUD depreciates because Australia has higher expected inflation.
USD/AUD falls from 1.00 to 0.97.
```

## Worked Example: USD/EUR

Suppose:

```text
Current spot rate: USD/EUR = 1.10
Expected US inflation: 4.0%
Expected Eurozone inflation: 1.5%
```

The quote USD/EUR means:

```text
1 EUR costs 1.10 USD
```

EUR is the base currency.

USD is the price currency.

The United States has higher expected inflation:

```text
4.0% > 1.5%
```

So USD should depreciate relative to EUR.

If USD depreciates, one EUR should cost more USD.

So USD/EUR should rise.

Use the formula:

$$
\%\Delta S_{\text{USD/EUR}}^e
= \pi_{\text{USD}}^e - \pi_{\text{EUR}}^e
$$

$$
\%\Delta S_{\text{USD/EUR}}^e
= 4.0\% - 1.5\%
$$

$$
\%\Delta S_{\text{USD/EUR}}^e
= 2.5\%
$$

Expected future spot:

$$
E(S_1) = 1.10(1 + 0.025)
$$

$$
E(S_1) = 1.10(1.025)
$$

$$
E(S_1) = 1.1275 \text{ USD/EUR}
$$

Interpretation:

```text
USD depreciates because US expected inflation is higher.
EUR appreciates.
USD/EUR rises from 1.10 to 1.1275.
```

## Relationship to UIP

[[Uncovered interest rate parity]] says:

$$
\%\Delta S_{f/d}^{e} = i_f - i_d
$$

Ex ante PPP says:

$$
\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e
$$

They both forecast the expected spot change.

UIP uses nominal interest rate differentials.

Ex ante PPP uses expected inflation differentials.

If both hold, then:

$$
i_f - i_d = \pi_f^e - \pi_d^e
$$

That expression is the [[International Fisher Effect]] when real interest rates are equal.

The intuition:

```text
High nominal interest rate
  |
  v
May just compensate for high expected inflation
  |
  v
High-inflation currency expected to depreciate
  |
  v
No free lunch from the higher nominal yield
```

## Relationship to Real Interest Rate Parity

The [[Fisher effect]] says:

$$
i = r + \pi^e
$$

So:

$$
r = i - \pi^e
$$

If both UIP and ex ante PPP hold:

$$
i_f - i_d = \pi_f^e - \pi_d^e
$$

Rearrange:

$$
i_f - \pi_f^e = i_d - \pi_d^e
$$

Therefore:

$$
r_f = r_d
$$

That is [[real interest rate parity]].

In plain English:

> If expected currency depreciation fully offsets nominal interest-rate differences, then real risk-free returns are equal across countries.

In reality, real rates may differ because of country risk, capital controls, taxes, liquidity differences, and risk premiums.

## Does Ex Ante PPP Hold?

PPP is not enforced by riskless arbitrage.

That is different from [[covered interest rate parity]], which is tightly linked to arbitrage because investors can borrow, lend, exchange currencies, and lock in the forward rate.

PPP depends on goods-market adjustment.

Goods-market adjustment is slow and messy.

Reasons PPP fails in the short run:

| Friction | Why it matters |
|---|---|
| Non-tradable goods | You cannot ship haircuts, housing, or local services |
| Transportation costs | Arbitrage in goods is expensive |
| Tariffs and trade barriers | Goods prices may not equalize internationally |
| Different consumption baskets | CPI baskets are not identical across countries |
| Sticky prices | Local prices do not adjust instantly |
| Risk premiums and capital flows | FX can move for reasons unrelated to inflation |

Exam memory:

```text
CIP holds by arbitrage.
PPP does not.
```

PPP is more useful as a long-run anchor.

It is weak over short horizons but tends to perform better over long horizons, especially when inflation differences are large and persistent.

## Forecasting Use

Ex ante PPP can be used to forecast future spot exchange rates:

$$
E(S_1) = S_0(1 + \pi_f^e - \pi_d^e)
$$

This is an approximation.

A more exact compounding version is:

$$
E(S_1) = S_0 \times \frac{1+\pi_f^e}{1+\pi_d^e}
$$

CFA often uses the approximate percentage-change version for small inflation rates:

$$
\%\Delta S_{f/d}^{e} \approx \pi_f^e - \pi_d^e
$$

For high inflation, the exact version may be preferable.

## Common Wrong Reasoning

### Wrong: "Ex ante PPP uses actual inflation."

Why it is wrong: Actual inflation belongs to relative PPP. Ex ante PPP uses expected inflation.

Correct idea:

```text
Relative PPP = actual inflation.
Ex ante PPP = expected inflation.
```

### Wrong: "The higher inflation currency always makes the quoted exchange rate rise."

Why it is wrong: The quote direction matters. Higher inflation means the high-inflation currency should depreciate. Whether the quote rises or falls depends on where that currency appears in the quote.

Correct idea:

```text
First decide which currency depreciates.
Then translate into the quote.
```

### Wrong: "PPP is enforced by arbitrage like covered interest rate parity."

Why it is wrong: PPP relies on goods-market adjustment, not clean financial arbitrage. Transportation costs, non-tradable goods, tariffs, and different baskets prevent exact arbitrage.

Correct idea:

```text
CIP = arbitrage enforced.
PPP = long-run economic anchor.
```

### Wrong: "High interest rate means a currency should appreciate."

Why it is wrong: Under parity logic, high nominal interest rates may reflect high expected inflation. The high-rate currency may be expected to depreciate.

Correct idea:

```text
High nominal rate may just compensate for expected inflation.
```

### Wrong: "Ex ante PPP is a reliable short-run forecast."

Why it is wrong: PPP often fails in the short run. Exchange rates can move because of capital flows, risk sentiment, policy changes, and shocks.

Correct idea:

```text
PPP is better long-run than short-run.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Expected inflation rates | Ex ante PPP |
| Actual inflation rates | Relative PPP |
| Price levels / CPI ratio | Absolute PPP |
| Higher expected inflation | Currency expected to depreciate |
| Forecast future spot with inflation | Use ex ante PPP |
| Interest rate differential | UIP or International Fisher Effect |
| Real rates equal across countries | Real interest rate parity |
| Arbitrage-enforced parity | Covered interest rate parity, not PPP |
| Short-run FX forecast | PPP may be weak; current spot/random walk may perform well |
| Long-run fair value | PPP can serve as an anchor |

## Minimum Memorization

```text
Ex ante PPP = forward-looking relative PPP.

Formula:
%ΔS(f/d)^e = πf^e - πd^e

Meaning:
Expected spot change = expected foreign inflation - expected domestic inflation

Rule:
Higher expected inflation currency should depreciate.

Trap:
Quote direction determines whether the exchange rate number rises or falls.
```

Relations:

```text
UIP:          %ΔS^e = i_f - i_d
Ex ante PPP: %ΔS^e = π_f^e - π_d^e
IFE:          i_f - i_d = π_f^e - π_d^e
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. What does "ex ante" mean?
2. How is ex ante PPP different from relative PPP?
3. How is relative PPP different from absolute PPP?
4. What is the formula for ex ante PPP using $S_{f/d}$?
5. Why should a high expected inflation currency depreciate?
6. Why does quote direction matter?
7. If USD/EUR rises, which currency appreciated?
8. How do you forecast the future spot rate from expected inflation?
9. Why is PPP not arbitrage-enforced?
10. Why is PPP better as a long-run anchor than a short-run forecast?
11. How does ex ante PPP connect to UIP?
12. How does it connect to the International Fisher Effect?
13. How does it imply real interest rate parity if combined with UIP?

## Related Concepts

- [[Ex ante version of PPP]]
- [[Purchasing power parity]]
- [[Purchasing power parity (PPP)]]
- [[Absolute PPP]]
- [[Relative PPP]]
- [[Law of one price]]
- [[Spot rate]]
- [[Exchange rate]]
- [[Expected inflation]]
- [[Fisher effect]]
- [[International Fisher Effect]]
- [[Uncovered interest rate parity]]
- [[Covered interest rate parity]]
- [[Forward rate parity]]
- [[Real interest rate parity]]
- [[Current account]]
- [[Carry trade]]
