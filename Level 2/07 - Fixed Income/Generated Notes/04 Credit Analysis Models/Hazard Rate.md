---
title: Hazard Rate
subject: Fixed Income
tags: [CFA-L2, fixed-income, hazard-rate, probability-of-default, cds, credit-risk, credit-spreads]
aliases: [hazard rate, conditional probability of default, default intensity, conditional default probability]
---

# Hazard Rate

## The Real-World Analogy

Imagine a company is walking across five bridges, one bridge per year.

The hazard rate for Year 3 is not:

```text
What is the chance the company defaults in Year 3 from today?
```

It is:

```text
If the company survived Years 1 and 2,
what is the chance it defaults during Year 3?
```

That conditional phrase is the entire concept.

Hazard rate is default probability for the survivors.

## Plain-English Definition

The [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] is the probability that an event occurs in a period, given that it has not already occurred.

In credit analysis:

```text
Hazard rate = probability of default in a period,
conditional on no prior default.
```

It is also called [[Default intensity]] or conditional default probability.

## CFA Definition

The glossary definition:

```text
The probability that an event will occur,
given that it has not already occurred.
```

For CFA fixed income, the event is usually default.

So the hazard rate is the conditional [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]].

## Why Conditional Probability Matters

Default can happen only once.

Once the issuer defaults, later scheduled default events no longer matter in the same way.

So a Year 5 default probability must account for whether the issuer survived Years 1 through 4.

That is why we separate:

| Concept | Meaning |
|---|---|
| Hazard rate | Conditional default probability in a period |
| Period POD | Unconditional probability of default occurring in that specific period |
| Survival probability | Probability the issuer has not defaulted through a date |
| Cumulative POD | Probability default occurs at any time through a horizon |

## Core Formulas

If $h_t$ is the hazard rate in period $t$:

$$
\text{POD}_t
=
h_t \times \text{Probability of survival to }t-1
$$

Survival through period $t$ is:

$$
\text{Survival through }t
=
\prod_{i=1}^{t}(1-h_i)
$$

Cumulative default probability through period $t$ is:

$$
\text{Cumulative POD through }t
=
1-\prod_{i=1}^{t}(1-h_i)
$$

If the hazard rate is constant at $h$:

$$
\text{Survival through }t=(1-h)^t
$$

$$
\text{Cumulative POD through }t=1-(1-h)^t
$$

In continuous-time models, the same intuition is often written with default intensity $\lambda$:

$$
\text{Survival to }t=e^{-\lambda t}
$$

$$
\text{Cumulative POD through }t=1-e^{-\lambda t}
$$

For CFA exam work, use the version implied by the question. If the data are annual or quarterly hazard rates, the discrete multiplication approach is usually the safer choice.

## Worked Example: Constant Hazard Rate

Suppose an issuer has a 2% annual hazard rate for 10 years.

One-year survival:

$$
1-0.02=0.98
$$

Ten-year survival:

$$
0.98^{10}=0.817
$$

Ten-year cumulative default probability:

$$
1-0.817=0.183=18.3\%
$$

Interpretation:

```text
A small annual conditional default probability can become
a much larger cumulative default probability over many years.
```

That is a major exam intuition.

## Worked Example: Different Hazard Rates by Year

Suppose hazard rates are:

| Year | Hazard Rate |
|---|---:|
| 1 | 2% |
| 2 | 3% |
| 3 | 4% |
| 4 | 5% |
| 5 | 6% |

Five-year survival:

$$
(1-0.02)(1-0.03)(1-0.04)(1-0.05)(1-0.06)
$$

$$
=0.98\times0.97\times0.96\times0.95\times0.94
=0.815
$$

Five-year cumulative default probability:

$$
1-0.815=0.185=18.5\%
$$

The rising hazard rates imply that conditional default risk is increasing over time.

## Period POD vs Hazard Rate

Suppose the annual hazard rate is constant at 1.25%.

Year 1 period POD:

$$
\text{POD}_1=1.25\%
$$

Year 2 period POD:

$$
\text{POD}_2=1.25\%\times(1-1.25\%)
$$

$$
=1.25\%\times98.75\%
=1.2344\%
$$

Why is Year 2's period POD lower than the hazard rate?

Because some issuers would have already defaulted in Year 1.

The Year 2 period POD is:

```text
probability of reaching Year 2 alive
x
conditional probability of defaulting in Year 2
```

## Expected Loss Link

Expected loss combines default probability with loss severity:

$$
\text{Expected Loss}=\text{POD}\times\text{LGD}
$$

Where:

$$
\text{LGD}=(1-\text{Recovery Rate})\times\text{Exposure}
$$

So hazard rates feed expected loss through period-by-period POD.

The chain is:

```text
Hazard rate -> period POD -> expected loss -> credit valuation adjustment / credit spread
```

## Credit Spread Link

A simple approximation is:

$$
\text{Credit Spread}\approx \text{POD}\times \text{LGD\%}
$$

For a one-period case:

| Input | Value |
|---|---:|
| POD / hazard rate | 3% |
| Recovery rate | 50% |
| LGD | 50% |

Then:

$$
\text{Spread}\approx0.03\times0.50=0.015=1.50\%=150\text{ bps}
$$

So:

```text
Higher hazard rate -> higher expected default cost -> wider credit spread.
```

## CDS Pricing Link

In a [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]], there are two legs:

| Leg | Who Pays? | What It Depends On |
|---|---|---|
| Premium leg | Protection buyer pays periodic CDS spread | Survival probability; payments stop after default |
| Protection leg | Protection seller pays if default occurs | Hazard rate, LGD, timing of default |

The fair CDS spread makes:

$$
\text{PV(Premium leg)}=\text{PV(Protection leg)}
$$

Hazard rate affects both legs:

```text
Higher hazard rate -> default more likely -> protection leg more valuable.
Higher hazard rate -> premiums more likely to stop early -> premium leg changes too.
```

The main direction is still clear:

```text
Higher hazard rate -> higher CDS spread.
```

## Credit Curve Implications

Hazard rates shape the [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]].

| Hazard Rate Pattern | Credit Curve Interpretation |
|---|---|
| Low near-term, higher long-term | Upward-sloping credit curve |
| Roughly constant | Flatter credit curve |
| High near-term, lower long-term | Downward-sloping / inverted credit curve |

An upward-sloping credit curve often means:

```text
The market is more worried about default later than default now.
```

An inverted credit curve often means:

```text
The market is worried about imminent default.
```

## Real-World Scenarios

### Scenario 1: Stable Investment-Grade Issuer

A strong issuer has low near-term hazard rates, but uncertainty increases over longer horizons.

Its credit curve may be upward sloping.

Implication:

```text
Longer-maturity bonds require more spread compensation.
```

### Scenario 2: Distressed Issuer

A distressed issuer may have very high near-term hazard rates.

Its short-term CDS spread can exceed its long-term CDS spread.

Implication:

```text
The credit curve can invert because the main question is near-term survival.
```

### Scenario 3: Improving Credit Outlook

A company sells assets, raises equity, and reduces leverage.

Expected future hazard rates may fall.

Implication:

```text
Credit spreads may tighten and the credit curve may flatten.
```

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Treat hazard rate as unconditional POD | Hazard rate is conditional on survival | Multiply by prior survival to get period POD |
| Add survival probabilities | Survival across periods multiplies | Use $\prod(1-h_i)$ |
| Add annual hazard rates to get cumulative default probability | That ignores compounding/survival | Cumulative POD is $1-\prod(1-h_i)$ |
| Forget default can happen only once | Later PODs depend on survival | Conditional logic matters |
| Think hazard rate affects only CDS protection leg | Premium payments stop after default too | Hazard rate affects both legs |
| Reverse the spread relationship | More default risk requires more compensation | Higher hazard rate widens spreads |
| Assume a flat credit curve means no default risk | It may mean similar hazard rates across maturities | The spread level can still be high |
| Confuse recovery rate and LGD | Higher recovery lowers LGD | LGD = 1 - recovery rate, in percentage terms |
| Confuse actual and risk-neutral default probabilities | Pricing uses risk-neutral probabilities that include risk premia | Market-implied hazard rates can exceed historical default rates |
| Mix discrete and continuous formulas | $(1-h)^t$ and $e^{-\lambda t}$ are different modeling conventions | Use the convention implied by the data |

## Memory Hooks

```text
Hazard rate = default probability for the survivors.
```

```text
Survival multiplies. Default is one minus survival.
```

```text
Higher hazard rate -> higher expected loss -> wider spread.
```

```text
Flat hazard rates tend to flatten the credit curve.
```

## Exam Decision Checklist

When you see a hazard-rate question, ask:

1. Is the question asking for conditional POD or cumulative POD?
2. Do I need survival probability first?
3. Are hazard rates constant or changing by period?
4. Is recovery rate given, so I can calculate LGD?
5. Is the question about expected loss, credit spreads, or CDS pricing?
6. Does the credit curve shape imply near-term or long-term default concern?

Then use:

| Task | Formula |
|---|---|
| Survival through $t$ | $\prod_{i=1}^{t}(1-h_i)$ |
| Cumulative POD through $t$ | $1-\prod_{i=1}^{t}(1-h_i)$ |
| Continuous survival to $t$ | $e^{-\lambda t}$ |
| Period POD | $h_t\times\text{survival to }t-1$ |
| Expected loss | $\text{POD}\times\text{LGD}$ |
| Simple spread approximation | $\text{POD}\times\text{LGD\%}$ |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Probability of survival]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Recovery rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Credit spread risk]]
- [[Credit Valuation Adjustment]]
- [[Default intensity]]
