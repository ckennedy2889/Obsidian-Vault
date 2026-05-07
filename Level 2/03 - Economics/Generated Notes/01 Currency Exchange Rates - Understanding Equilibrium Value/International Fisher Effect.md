---
title: International Fisher Effect
subject: Economics
tags: [CFA-L2, economics, exchange-rates, parity-conditions]
aliases: [International Fisher effect, IFE, international Fisher relation]
---

# International Fisher Effect

## Real-World Analogy

Imagine two banks offering one-year deposits. A U.S. bank pays 4%, and a Brazilian bank pays 9%. At first glance, the Brazilian deposit looks better. The [[International Fisher Effect]] says: slow down. A higher nominal interest rate is often not a free lunch. It may simply be compensation for higher expected inflation in that country.

If Brazil is expected to have 5% more inflation than the United States, then the 9% nominal rate may leave investors with roughly the same real return as the 4% U.S. rate. The extra nominal yield is offset by loss of purchasing power and, in currency terms, expected depreciation.

## Plain-English Definition

The International Fisher Effect says that differences in nominal interest rates across countries should reflect differences in expected inflation across those countries.

In simple terms:

> The country with the higher nominal interest rate is usually the country with higher expected inflation, not necessarily the country offering a better real return.

## CFA Definition

The International Fisher Effect is the proposition that:

$$
i_f - i_d = \pi_f^e - \pi_d^e
$$

where:

| Symbol | Meaning |
|---|---|
| $i_f$ | Foreign nominal interest rate |
| $i_d$ | Domestic nominal interest rate |
| $\pi_f^e$ | Expected foreign inflation |
| $\pi_d^e$ | Expected domestic inflation |

The logic comes from combining the domestic [[Fisher effect]] with [[real interest rate parity]].

## Derivation

Start with the Fisher relation for each country:

$$
i_d = r_d + \pi_d^e
$$

$$
i_f = r_f + \pi_f^e
$$

Subtract the domestic equation from the foreign equation:

$$
i_f - i_d = (r_f - r_d) + (\pi_f^e - \pi_d^e)
$$

Now apply [[real interest rate parity]], which assumes real interest rates converge across countries:

$$
r_f = r_d
$$

So:

$$
r_f - r_d = 0
$$

That leaves:

$$
\boxed{i_f - i_d = \pi_f^e - \pi_d^e}
$$

## Mechanism

The rule exists because nominal interest rates mix two things together: the real required return and expected inflation.

If one country has a higher nominal interest rate, there are two possible reasons. Either investors are receiving a higher real return, or expected inflation is higher. The International Fisher Effect assumes that capital can move freely enough across countries that real interest rates are competed toward equality. If one country offered a higher real return with the same risk, global capital would flow there, pushing asset prices up and real returns down until the advantage disappeared.

Once real rates are equalized, the only reason nominal rates differ is expected inflation.

That is the mechanism:

```text
Nominal rate = real rate + expected inflation
Free capital flows push real rates toward equality
Therefore nominal rate differences mostly reflect expected inflation differences
Higher expected inflation -> higher nominal rate -> expected currency depreciation
```

## Connection to Exchange Rates

The International Fisher Effect itself is an interest-rate/inflation relation. But CFA usually teaches it inside the broader exchange-rate parity framework.

If a country has higher expected inflation, [[Purchasing Power Parity]] says its currency should depreciate over time. If the same country also has a higher nominal interest rate, the higher yield should be offset by expected currency depreciation.

That is why the high-yield currency is not automatically attractive.

Approximate relationship:

$$
\%\Delta S_{f/d}^e \approx i_f - i_d
$$

under [[uncovered interest rate parity]], and:

$$
\%\Delta S_{f/d}^e \approx \pi_f^e - \pi_d^e
$$

under ex ante [[Purchasing Power Parity]].

If both relationships hold, then:

$$
i_f - i_d = \pi_f^e - \pi_d^e
$$

which is the International Fisher Effect.

## Worked Example

Suppose:

| Item | Eurozone | South Africa |
|---|---:|---:|
| Expected inflation | 9.00% | 13.00% |
| Nominal interest rate | 10.09% | ? |

Use the International Fisher Effect to estimate South Africa's nominal interest rate.

First, estimate the real rate in the eurozone:

$$
r_{EUR} \approx i_{EUR} - \pi_{EUR}^e
$$

$$
r_{EUR} = 10.09\% - 9.00\% = 1.09\%
$$

Under real interest rate parity:

$$
r_{ZAR} = r_{EUR} = 1.09\%
$$

Now add South Africa's expected inflation:

$$
i_{ZAR} = r_{ZAR} + \pi_{ZAR}^e
$$

$$
i_{ZAR} = 1.09\% + 13.00\% = 14.09\%
$$

So the estimated South African nominal interest rate is:

$$
\boxed{14.09\%}
$$

## Why Higher Interest Does Not Mean Higher Real Return

This is the exam intuition. If South Africa pays 14.09% and the eurozone pays 10.09%, the naive answer is: South Africa looks better by 4%.

But expected inflation is also 4% higher:

$$
13.00\% - 9.00\% = 4.00\%
$$

So the nominal interest-rate advantage is eaten by higher expected inflation. The real return is the same:

$$
14.09\% - 13.00\% = 1.09\%
$$

$$
10.09\% - 9.00\% = 1.09\%
$$

## Relationship to Other Parity Conditions

| Parity condition | Core idea | CFA use |
|---|---|---|
| [[Fisher effect]] | $i = r + \pi^e$ | Splits a nominal rate into real return and expected inflation |
| [[International Fisher Effect]] | $i_f - i_d = \pi_f^e - \pi_d^e$ | Links cross-country nominal rate differentials to expected inflation differentials |
| [[Real interest rate parity]] | $r_f = r_d$ | Assumption that real returns converge across countries |
| Ex ante [[Purchasing Power Parity]] | Expected currency change reflects expected inflation differential | Higher-inflation currency should depreciate |
| [[Uncovered interest rate parity]] | Expected currency change reflects nominal interest-rate differential | Higher-yield currency should depreciate enough to offset yield advantage |
| [[Covered Interest Rate Parity]] | Forward rates are set by spot rates and interest-rate differentials | Arbitrage relationship, generally stronger than UIP |

## Assumptions

The International Fisher Effect works cleanly only if:

| Assumption | Why it matters |
|---|---|
| Real interest rates are equal across countries | Otherwise nominal rate differences can reflect different real returns, not just inflation |
| Capital can flow freely | If capital cannot move, real rates may not converge |
| Countries have similar risk | Higher sovereign, currency, or political risk can require a higher real return |
| Inflation expectations are accurate | If expected inflation is wrong, the relation can fail ex post |
| Investors are not demanding changing risk premia | Risk premia can create persistent deviations |

## What Breaks in the Real World

The largest failure mode is risk. Emerging-market currencies often have higher nominal rates, but not only because expected inflation is higher. Investors may demand extra real compensation for sovereign risk, capital controls, liquidity risk, political risk, and currency crash risk.

So the more complete intuition is:

```text
Nominal rate differential
= expected inflation differential
+ real risk premium differential
+ possible market frictions
```

CFA often wants you to know the clean parity condition first, then recognize why it fails in practice.

## Exam Traps

| Trap | Why it is wrong | Correct thinking |
|---|---|---|
| "Higher nominal rate means better investment" | The higher nominal rate may only compensate for higher expected inflation | Compare real rates, not nominal rates |
| Confusing IFE with PPP | PPP links inflation to exchange-rate changes; IFE links nominal rates to expected inflation | They connect, but they are not identical |
| Forgetting the real-rate assumption | IFE requires real interest rate parity | If real rates differ, the formula does not hold cleanly |
| Treating parity as guaranteed | IFE is an equilibrium condition, not a perfect forecast | Risk premia and frictions cause deviations |
| Mixing domestic and foreign signs | CFA exchange-rate notation can flip the expected appreciation/depreciation direction | Define the quote and track which currency has higher inflation |

## Memory Hook

**IFE = international Fisher = interest differences are inflation differences.**

If real rates are equal, the extra nominal yield is just extra expected inflation.

## Exam-Day Checklist

When you see International Fisher Effect in a vignette, ask:

- Which country has the higher nominal interest rate?
- Is that country also expected to have higher inflation?
- Are real interest rates assumed equal?
- Is the question asking for a nominal rate, expected inflation, or real rate?
- Is CFA testing the clean parity formula or a real-world violation due to risk premia?
- Is the exchange-rate quote direct or indirect?

## Related Concepts

- [[Fisher effect]]
- [[Real interest rate parity]]
- [[Purchasing Power Parity]]
- [[Ex Ante Purchasing Power Parity (PPP)]]
- [[Uncovered interest rate parity]]
- [[Covered Interest Rate Parity]]
- [[Forward rate parity]]
- [[Carry Trades]]
