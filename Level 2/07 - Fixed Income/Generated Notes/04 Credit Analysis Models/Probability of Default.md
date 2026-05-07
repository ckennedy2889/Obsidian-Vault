---
title: Probability of Default
subject: Fixed Income
tags: [CFA-L2, fixed-income, probability-of-default, credit-risk, expected-loss, cva, cds, credit-spreads]
aliases: [probability of default, POD, default probability, default risk, cumulative default probability, conditional probability of default]
---

# Probability of Default

## The Real-World Analogy

Imagine lending money to a friend who promises to pay you back in three annual installments.

You care about three different questions:

```text
Will they miss the first payment?
If they make the first payment, will they miss the second?
What is the total chance that something goes wrong at any point?
```

Those are all default-probability questions, but they are not the same question.

In fixed income, this distinction matters because a bond's value depends not only on whether default might happen, but also on:

```text
when default might happen,
how likely it is in each period,
how much value is recovered if it happens,
and how those expected losses are discounted.
```

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] is the likelihood that a borrower fails to meet its promised debt obligations on time.

For a bond issuer, default can mean:

| Default Form | Meaning |
|---|---|
| Missed interest payment | Coupon is not paid when due |
| Missed principal payment | Maturity or amortization payment is not paid |
| Bankruptcy | Issuer enters a legal default/restructuring process |
| Restructuring | Bondholders are forced to accept worse terms |

In simple language:

```text
POD measures the chance that promised cash flows do not arrive as promised.
```

## CFA Definition

The glossary definition:

```text
The probability that a bond issuer will not meet its contractual obligations on schedule.
```

Related terms:

| Term | Meaning |
|---|---|
| [[Default risk]] | Risk that the borrower fails to pay |
| [[Probability of survival]] | Probability the issuer does not default through a date |
| [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] | Conditional probability of default given prior survival |
| Cumulative POD | Probability of default at any time through a horizon |

## Why Probability of Default Exists

Default risk turns promised cash flows into expected cash flows.

An option-free default-free bond can be valued by discounting promised payments.

A risky bond cannot be valued that simply because promised cash flows may not be received.

The valuation problem becomes:

```text
Promised cash flows
- probability-weighted expected default losses
= risky bond value
```

That is why POD is central to:

| Area | How POD Is Used |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | POD times loss severity |
| [[Credit Valuation Adjustment]] | Present value of expected credit losses |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] pricing | Higher POD increases protection value |
| [[Credit spread risk]] | Higher POD widens credit spreads |
| [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]] | POD timing shapes the credit curve |
| Credit rating analysis | Ratings summarize relative credit risk but do not by themselves give exact POD |

## The Mechanism

The mechanism is:

```text
Borrower credit quality weakens
-> probability of default rises
-> expected loss rises
-> investors demand more spread
-> risky bond price falls
```

Why price falls:

```text
If expected cash flows are lower or riskier,
the bond must offer a higher expected return.
For an existing bond, that higher required return shows up as a lower price.
```

This is the core credit-risk chain.

## Three POD Concepts CFA Can Test

### 1. Single-Period POD

This is the probability of default during one period.

Example:

```text
There is a 2% chance the issuer defaults over the next year.
```

### 2. Conditional POD / Hazard Rate

This is the probability of default during a period given that default has not already occurred.

Example:

```text
If the issuer survives Year 1,
there is a 3% chance it defaults in Year 2.
```

This is [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]].

### 3. Cumulative POD

This is the probability of default at any time through a horizon.

Example:

```text
There is an 18.3% chance the issuer defaults at some point during the next 10 years.
```

CFA questions often mix these up.

## Probability of Survival

[[Probability of survival]] is the mirror image of default probability.

If default probability for one period is 2%, survival probability for that period is:

$$
1-0.02=0.98=98\%
$$

For multiple periods, survival probabilities multiply.

If the period hazard rates are $h_1,h_2,\ldots,h_t$:

$$
\text{Survival through }t
=
\prod_{i=1}^{t}(1-h_i)
$$

Cumulative POD is:

$$
\text{Cumulative POD through }t
=
1-\prod_{i=1}^{t}(1-h_i)
$$

The reason is simple:

```text
To survive through Year 3,
the issuer must survive Year 1 and Year 2 and Year 3.
```

"And" probabilities multiply.

## Worked Example: Two-Year POD

Suppose:

| Period | Conditional POD / Hazard Rate |
|---|---:|
| Year 1 | 2% |
| Year 2 | 4% |

Survival through Year 1:

$$
1-0.02=0.98
$$

Conditional survival through Year 2:

$$
1-0.04=0.96
$$

Survival through Year 2:

$$
0.98\times0.96=0.9408=94.08\%
$$

Cumulative POD through Year 2:

$$
1-0.9408=0.0592=5.92\%
$$

Exam interpretation:

```text
The two-year default probability is not 2% + 4% = 6%.
It is 5.92% because Year 2 default can happen only if the issuer survives Year 1.
```

## Worked Example: Constant Annual POD

Suppose an issuer has a constant 2% annual hazard rate for 10 years.

Survival through 10 years:

$$
0.98^{10}=0.817
$$

Cumulative POD:

$$
1-0.817=0.183=18.3\%
$$

The intuition:

```text
A small annual default probability can compound into a large long-horizon default probability.
```

This is why long-maturity credit spreads can be meaningfully wider than short-maturity spreads.

## Period POD vs Conditional POD

If the hazard rate is constant at 1.25%, the period-by-period unconditional POD declines slightly because fewer issuers remain alive to default later.

Year 1 POD:

$$
1.25\%
$$

Year 2 period POD:

$$
1.25\%\times(1-1.25\%)
$$

$$
=1.25\%\times98.75\%
=1.2344\%
$$

Year 3 period POD:

$$
1.25\%\times97.5156\%
=1.2189\%
$$

Do not interpret this as the issuer becoming safer each year.

The conditional probability is still 1.25%.

The unconditional period probability falls because some issuers would already have defaulted earlier.

## Expected Loss

POD becomes economically meaningful when combined with loss severity.

$$
\text{Expected Loss}=\text{POD}\times\text{LGD}
$$

Where:

$$
\text{LGD}=(1-\text{Recovery Rate})\times\text{Exposure}
$$

If using percentages:

$$
\text{Expected Loss \%}=\text{POD}\times(1-\text{Recovery Rate})
$$

## Worked Example: Expected Loss

Suppose:

| Input | Value |
|---|---:|
| Exposure | $1,000,000 |
| POD | 3% |
| Recovery rate | 40% |

LGD:

$$
(1-0.40)\times \$1{,}000{,}000
=\$600{,}000
$$

Expected loss:

$$
0.03\times \$600{,}000
=\$18{,}000
$$

Interpretation:

```text
The expected loss is not the loss if default happens.
It is the probability-weighted average loss before knowing whether default occurs.
```

## Credit Valuation Adjustment

[[Credit Valuation Adjustment]] is the present value of expected credit losses.

The general structure is:

$$
\text{CVA}
=
\sum_t
\text{Expected Loss}_t \times \text{Discount Factor}_t
$$

And:

$$
\text{Expected Loss}_t
=
\text{POD}_t\times\text{LGD}_t
$$

So the chain is:

```text
POD -> expected loss -> discounted expected loss -> CVA -> risky value adjustment
```

A higher POD increases CVA, which lowers the value of the risky bond or credit exposure.

In compact valuation language:

$$
\text{Risky Bond Value}
\approx
\text{Default-Free Bond Value}
-
\text{CVA}
$$

So if POD rises:

```text
Expected losses rise -> CVA rises -> risky bond value falls.
```

## Credit Spread Link

A simple credit spread approximation is:

$$
\text{Credit Spread}\approx \text{POD}\times\text{LGD\%}
$$

If:

| Input | Value |
|---|---:|
| POD | 2% |
| Recovery rate | 60% |
| LGD | 40% |

Then:

$$
\text{Credit Spread}
\approx0.02\times0.40=0.0080=80\text{ bps}
$$

This is why:

```text
Higher POD -> wider spread.
Lower recovery -> wider spread.
Higher expected loss -> wider spread.
```

## CDS Link

In a [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]], the protection buyer pays a spread to receive compensation if default occurs.

The higher the POD:

```text
the more valuable the protection leg,
the higher the fair CDS spread.
```

Simple CDS approximation:

$$
\text{CDS Spread}\approx(1-\text{Recovery Rate})\times\text{POD}
$$

Same expected-loss logic, just applied to a credit derivative.

## Actual vs Risk-Neutral POD

CFA can test the difference between historical/actual default probabilities and market-implied/risk-neutral default probabilities.

| Type | Meaning | Usually Used For |
|---|---|---|
| Actual / historical POD | Real-world estimate of default frequency | Credit research, risk management |
| Risk-neutral POD | Default probability implied by market prices | Valuation of risky bonds and CDS |

Risk-neutral PODs are often higher than actual PODs because market prices include risk premia.

Why?

Investors do not only care about the average expected loss.

They also require compensation for:

```text
uncertainty about default timing,
bad-state-of-the-world losses,
illiquidity,
model risk,
and risk aversion.
```

Exam implication:

```text
Do not treat a market-implied POD as a pure historical forecast.
```

## Credit Ratings and POD

Credit ratings rank borrowers by credit quality, but ratings are not themselves exact PODs.

Important distinction:

| Concept | Meaning |
|---|---|
| Rating | Ordinal ranking of credit risk |
| POD | Numerical default probability |

An A rating does not mean:

```text
The issuer has exactly x% probability of default.
```

To get a POD, analysts need default studies, market-implied spreads, CDS data, or a credit model.

## Credit Curve Implications

POD timing shapes the [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]].

| POD Pattern | Credit Curve Shape |
|---|---|
| Low near-term POD, higher long-term POD | Upward-sloping credit curve |
| Similar conditional POD across maturities | Flatter credit curve |
| High near-term POD | Downward-sloping / inverted credit curve |

If a credit curve is inverted, the market is often saying:

```text
The issuer may default soon,
but if it survives the near-term stress,
longer-term prospects may be less bad.
```

## Real-World / Vignette Scenarios

### Scenario 1: Recession Risk

A cyclical issuer faces falling revenue and rising leverage during a recession.

Analysts raise POD estimates.

Expected loss rises.

Credit spreads widen.

Bond prices fall.

Exam implication:

```text
In weaker economic conditions, credit-sensitive bonds underperform because POD rises.
```

### Scenario 2: Improving Balance Sheet

An issuer sells assets and uses the proceeds to repay debt.

Leverage falls.

POD falls.

Spreads tighten.

Bond prices rise.

Exam implication:

```text
Lower expected default risk supports tighter spreads and higher risky bond values.
```

### Scenario 3: Distressed Issuer

A company faces a major debt maturity in six months and may not refinance.

Near-term POD spikes.

Short-term spreads rise above long-term spreads.

The credit curve inverts.

Exam implication:

```text
High near-term POD often shows up as an inverted credit curve.
```

## Comparisons

| Concept | What It Measures | Common Trap |
|---|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Chance of default | Confusing period, conditional, and cumulative POD |
| [[Probability of survival]] | Chance of no default through a horizon | Adding survival rates instead of multiplying |
| [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] | Conditional default probability given survival | Treating it as unconditional POD |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Loss if default occurs | Confusing it with expected loss |
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | Probability-weighted loss | Forgetting to multiply by POD |
| [[Credit spread risk]] | Price risk from changing spreads | Treating spread widening as good for bondholders |

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Add conditional PODs directly | Default can happen only once | Use survival multiplication |
| Treat hazard rate as cumulative POD | Hazard rate is conditional for a period | Cumulative POD is one minus survival |
| Confuse expected loss with LGD | LGD is loss if default occurs; expected loss weights by probability | EL = POD x LGD |
| Forget recovery rate | Lower recovery increases loss severity | LGD% = 1 - recovery rate |
| Think ratings provide exact PODs | Ratings are ordinal | Need default data/model/market prices for numerical POD |
| Treat risk-neutral POD as historical forecast | Market prices include risk premia | Risk-neutral POD is for valuation |
| Ignore timing of default | Earlier default losses have different PV impact | Use period PODs and discount factors |
| Think higher POD can coexist with tighter spread all else equal | Higher expected loss requires more compensation | Higher POD widens spreads, all else equal |
| Misread inverted credit curve | It often signals near-term stress | Short spreads above long spreads mean high near-term POD |
| Forget the risky-bond valuation adjustment | Credit losses reduce value | Risky value is approximately default-free value minus CVA |
| Ignore POD/recovery interaction when solving from market price | Different POD and recovery assumptions can fit the same price | For a given price, higher assumed recovery can imply higher solved POD |

## Memory Hooks

```text
POD is the chance cash flows break.
```

```text
Survival multiplies. Default is one minus survival.
```

```text
Expected loss = how likely x how bad.
```

```text
Ratings rank risk; POD measures it.
```

## Exam-Day Checklist

When a POD question appears, ask:

1. Is the question asking for period POD, conditional POD, or cumulative POD?
2. Do I need to calculate survival first?
3. Are probabilities annual, quarterly, conditional, or cumulative?
4. Is recovery rate given so I can calculate LGD?
5. Is the question asking for expected loss, CVA, CDS spread, or bond value?
6. Are the probabilities actual/historical or risk-neutral/market-implied?
7. What does the credit curve shape imply about near-term vs long-term POD?

Then use:

| Task | Formula |
|---|---|
| Survival through $t$ | $\prod_{i=1}^{t}(1-h_i)$ |
| Cumulative POD through $t$ | $1-\prod_{i=1}^{t}(1-h_i)$ |
| Period POD | $h_t\times\text{survival to }t-1$ |
| LGD | $(1-\text{Recovery Rate})\times\text{Exposure}$ |
| Expected loss | $\text{POD}\times\text{LGD}$ |
| Simple credit spread | $\text{POD}\times\text{LGD\%}$ |

## Related Concepts

- [[Default risk]]
- [[Probability of survival]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Recovery rate]]
- [[Credit Valuation Adjustment]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS spread]]
- [[Credit spread risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Structural Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]]
