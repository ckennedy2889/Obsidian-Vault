---
title: International Parity Conditions
subject: Economics
tags: [CFA-L2, Economics, ExchangeRates, ParityConditions]
aliases: [currency parity conditions, FX parity conditions, international parity relationships, parity conditions]
---

# International Parity Conditions

## The Real-World Analogy

Think of the international parity conditions as a set of no-free-lunch pressure valves.

Money can earn interest in one country, prices can rise faster in another country, and currencies can move between now and the future. The parity conditions explain how those pieces should fit together in a frictionless world.

If they did not fit together, investors could get something for nothing:

```text
Borrow cheap
Invest rich
Hedge the currency
Lock in a free profit
```

The CFA exam cares about which relationships are enforced by arbitrage and which are only long-run or expectation-based tendencies.

## The Five Main Parity Conditions

| Parity Condition | Links | Enforced By Arbitrage? | Core Idea |
|---|---|---:|---|
| [[Covered interest rate parity]] | Spot rate, forward rate, and interest rates | Yes | Hedged foreign and domestic investments should earn the same return |
| [[Uncovered interest rate parity]] | Expected spot change and interest rates | No | High-interest-rate currency should depreciate enough to offset the yield advantage |
| [[Forward rate parity]] | Forward rate and expected future spot rate | No | Forward rate is an unbiased predictor of future spot |
| [[Purchasing Power Parity]] | Exchange rates and inflation | No | Higher-inflation currency should depreciate |
| [[International Fisher Effect]] | Nominal interest rates and expected inflation | No | Nominal rate differentials reflect expected inflation differentials |

## Quote Convention

For a quote:

```text
Price currency / Base currency
```

example:

```text
USD/EUR
```

USD is the price currency and EUR is the base currency. The quote is the number of US dollars per one euro.

For parity formulas, use the numerator-denominator rule:

```text
Interest rate for numerator currency goes in the numerator.
Interest rate for denominator currency goes in the denominator.
```

For `USD/EUR`, the USD interest rate belongs in the numerator and the EUR interest rate belongs in the denominator.

## 1. Covered Interest Rate Parity

[[Covered interest rate parity]] says the forward premium or discount must exactly offset the interest-rate differential.

For a quote:

```text
P/B
```

the covered-interest-parity forward rate is:

$$
\boxed{
F_{P/B} = S_{P/B} \times \frac{1 + i_P(T)}{1 + i_B(T)}
}
$$

where:

| Term | Meaning |
|---|---|
| $F_{P/B}$ | Forward rate in price currency per one base currency |
| $S_{P/B}$ | Spot rate in price currency per one base currency |
| $i_P$ | Interest rate of the price currency |
| $i_B$ | Interest rate of the base currency |
| $T$ | Fraction of a year |

### Why It Works

The investor has two choices:

```text
Choice 1: Invest domestically
Choice 2: Convert to foreign currency, invest abroad, lock in forward conversion back
```

If both choices are fully hedged and risk-free, they must earn the same return. If not, arbitrageurs borrow in the low-return path and invest in the high-return path until prices adjust.

### Worked Example

Suppose:

| Input | Value |
|---|---:|
| Spot rate, $S_{USD/EUR}$ | 1.3000 |
| USD interest rate | 8% |
| EUR interest rate | 6% |
| Time | 1 year |

Then:

$$
F_{USD/EUR} = 1.3000 \times \frac{1.08}{1.06}
$$

$$
F_{USD/EUR} = 1.3000 \times 1.0188679 = 1.3245
$$

If the market forward rate is above 1.3245, the euro is too expensive forward. If it is below 1.3245, the euro is too cheap forward.

Exam point:

```text
Covered = hedged = forward contract used = arbitrage enforces it.
```

## 2. Uncovered Interest Rate Parity

[[Uncovered interest rate parity]] removes the forward hedge.

It says the expected currency movement should offset the interest-rate differential.

Approximate version:

$$
\boxed{
\%\Delta S_{P/B}^{e} \approx i_P - i_B
}
$$

For a `P/B` quote, if the base currency has the higher interest rate, the base currency is expected to depreciate.

### Why It Works

If one country offers a higher nominal interest rate, investors should not earn a free expected return just by moving money there. The high-yield currency is expected to depreciate enough to offset the extra interest.

```text
Higher foreign interest rate
  |
  v
Higher yield advantage
  |
  v
Expected currency depreciation offsets the advantage
  |
  v
Expected returns equalize
```

### Key Assumption

UIP assumes investors are [[Risk neutral]] and do not require a risk premium for bearing currency risk.

That assumption often fails in the short run. This is why [[Carry Trades]] can be profitable for long periods.

## 3. Forward Rate Parity

[[Forward rate parity]] says:

$$
\boxed{
F_{P/B} = E(S_{P/B, future})
}
$$

The forward rate is an unbiased predictor of the future spot rate.

This is not enforced by arbitrage. The forward rate is a traded price, but the future spot rate is uncertain.

Exam point:

```text
Covered interest parity must hold by arbitrage.
Forward rate parity does not have to hold.
```

## 4. Purchasing Power Parity

[[Purchasing Power Parity]] links exchange rates to price levels and inflation.

### Absolute PPP

Absolute PPP says equivalent baskets of goods should cost the same across countries after converting currencies.

For a `P/B` quote:

$$
S_{P/B} = \frac{\text{Price level}_P}{\text{Price level}_B}
$$

In practice, absolute PPP often fails because of transportation costs, tariffs, non-traded goods, taxes, and different consumption baskets.

### Relative PPP

Relative PPP says exchange-rate changes should offset inflation differentials.

Approximate version:

$$
\boxed{
\%\Delta S_{P/B} \approx \pi_P - \pi_B
}
$$

If the base currency country has higher inflation, the base currency should depreciate.

For example, if:

| Currency Area | Expected Inflation |
|---|---:|
| USD | 2% |
| AUD | 5% |

For `USD/AUD`:

$$
\%\Delta S_{USD/AUD} \approx 2\% - 5\% = -3\%
$$

The AUD, the base currency, is expected to depreciate by about 3%, so the USD/AUD quote falls.

## 5. International Fisher Effect

The domestic Fisher relation is:

$$
i \approx r + \pi^e
$$

where:

| Term | Meaning |
|---|---|
| $i$ | Nominal interest rate |
| $r$ | Real interest rate |
| $\pi^e$ | Expected inflation |

The [[International Fisher Effect]] combines the Fisher relation with real interest rate parity.

If real interest rates are equal across countries, nominal interest-rate differences should reflect expected inflation differences:

$$
\boxed{
i_P - i_B \approx \pi_P^e - \pi_B^e
}
$$

The country with higher expected inflation should have a higher nominal interest rate.

## How The Conditions Connect

The relationships fit together like this:

```text
Covered interest parity
  |
  v
Forward premium/discount offsets interest differential

International Fisher effect
  |
  v
Interest differential reflects expected inflation differential

Ex-ante PPP
  |
  v
Expected inflation differential predicts expected currency change

Uncovered interest parity
  |
  v
Interest differential predicts expected currency change

Forward rate parity
  |
  v
Forward rate equals expected future spot
```

If [[Uncovered interest rate parity]] and [[Covered interest rate parity]] both hold, then [[Forward rate parity]] holds:

```text
CIP links forward rates to interest rates.
UIP links expected spot changes to interest rates.
Therefore forward rates align with expected future spot rates.
```

If [[International Fisher Effect]] and ex-ante [[Purchasing Power Parity]] both hold, then UIP also holds:

```text
Interest differentials reflect expected inflation differentials.
Expected inflation differentials predict currency changes.
Therefore interest differentials predict currency changes.
```

## Forecasting Future Spot Rates

CFA wants you to know that these methods are not equally reliable.

| Forecasting Method | Short-Run Usefulness | Long-Run Usefulness | Key Caveat |
|---|---:|---:|---|
| Current spot rate | Often hard to beat in the short run | Weak for long-run fair value | Exchange rates often behave close to a random walk |
| Forward rate | Poor unbiased predictor in practice | Mixed | Forward rate reflects interest differentials, not pure expectations |
| PPP | Poor short-run predictor | Better long-run anchor | Real exchange rates can deviate for years |
| UIP | Often fails in short/medium run | Better long-run tendency | Risk premiums and carry trade behavior matter |

Exam point:

```text
Covered interest parity is an arbitrage relationship.
PPP, UIP, Fisher, and forward rate parity are forecasting/equilibrium relationships.
```

## Exam Traps

| Trap | Correction |
|---|---|
| Treating all parity conditions as arbitrage conditions | Only covered interest parity is enforced by arbitrage. |
| Forgetting the numerator-denominator rule | For `USD/EUR`, USD rates go in the numerator, EUR rates in the denominator. |
| Thinking high nominal interest currencies should appreciate under UIP | UIP says the higher-yield currency should depreciate enough to offset the yield advantage. |
| Confusing forward premium with expected appreciation | A forward premium is a quoted forward relationship, not necessarily a forecast. |
| Using PPP as a short-run trading rule | PPP is more useful as a long-run fair-value anchor. |
| Forgetting UIP assumes risk neutrality | Risk premiums can make UIP fail. |
| Mixing Mundell-Fleming and UIP | Mundell-Fleming can say higher policy-driven real rates appreciate a currency in the short run; UIP is an expected-return parity condition. |

## Memory Hook

```text
CIP is Covered, Contracted, and Compelled by arbitrage.
UIP is Uncovered, Uncertain, and Usually unreliable short run.
PPP is Prices.
Fisher is Inflation into interest rates.
Forward parity says Forward = Future expected spot.
```

## Related Concepts

- [[Covered interest rate parity]]
- [[Uncovered interest rate parity]]
- [[Forward rate parity]]
- [[Purchasing Power Parity]]
- [[Ex Ante Purchasing Power Parity (PPP)]]
- [[International Fisher Effect]]
- [[Spot and Forward FX Rates]]
- [[Carry Trades]]
- [[Mundell-Fleming Model]]
- [[Exchange rate]]
