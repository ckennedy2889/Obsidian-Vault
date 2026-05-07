---
title: Expected Loss
subject: Fixed Income
tags: [CFA-L2, fixed-income, expected-loss, credit-risk, probability-of-default, loss-given-default, cva, cds]
aliases: [expected loss, expected credit loss, EL, present value of expected loss, PV of expected loss]
---

# Expected Loss

## The Real-World Analogy

Imagine you lend $1,000 to someone.

There are two questions:

```text
How likely are they to fail to repay?
If they fail, how much do I lose?
```

Expected loss combines those two questions.

If there is a 2% chance they default and you would lose $600 if they default:

$$
\text{Expected Loss}=2\%\times \$600=\$12
$$

That does not mean you will literally lose $12.

It means the probability-weighted average loss is $12.

The actual outcome is more like:

```text
Most of the time: lose $0 from default.
Sometimes: lose $600.
Average across many similar loans: $12.
```

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] is the average credit loss after weighting the loss in default by the probability that default occurs.

In simple language:

```text
Expected loss = how likely default is x how bad default would be.
```

It is the core bridge between:

```text
credit risk assumptions
and
bond/CDS valuation
```

## CFA Definition

The glossary definition:

```text
Expected loss = probability of default multiplied by loss given default.
```

Or:

```text
The full amount owed minus expected recovery, probability-weighted by default risk.
```

## Core Formula

The main formula is:

$$
\text{Expected Loss}
=
\text{Probability of Default}\times\text{Loss Given Default}
$$

Using abbreviations:

$$
\text{EL}=\text{POD}\times\text{LGD}
$$

Since:

$$
\text{LGD}=(1-\text{Recovery Rate})\times\text{Expected Exposure}
$$

We can expand expected loss:

$$
\text{EL}
=
\text{POD}
\times
(1-\text{Recovery Rate})
\times
\text{Expected Exposure}
$$

Where:

| Term | Meaning |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Chance default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Dollar loss if default occurs |
| [[Recovery rate]] | Percentage recovered after default |
| [[Expected exposure]] | Amount at risk at default date |

## Why Expected Loss Exists

A risky bond has promised cash flows.

But risky promised cash flows are not the same as expected cash flows.

Expected loss is how we translate default risk into a valuation adjustment.

The mechanism:

```text
Default might happen.
If default happens, the investor loses LGD.
The probability-weighted loss is expected loss.
Discount expected losses to today.
Subtract from default-free value.
```

That is the basic logic behind [[Credit Valuation Adjustment]].

## LGD Is Not Expected Loss

This is the first exam trap.

| Concept | Formula | Interpretation |
|---|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | $(1-\text{RR})\times EE$ | Loss if default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | $\text{POD}\times\text{LGD}$ | Average probability-weighted loss |

LGD is conditional on default.

Expected loss includes the probability of default.

If LGD is $600,000 and POD is 2%, expected loss is not $600,000.

It is:

$$
0.02\times \$600{,}000=\$12{,}000
$$

## Worked Example: Basic Expected Loss

Suppose:

| Input | Value |
|---|---:|
| Expected exposure | $1,000,000 |
| Recovery rate | 40% |
| POD | 3% |

Step 1: Calculate LGD.

$$
\text{LGD}
=
(1-0.40)\times \$1{,}000{,}000
$$

$$
\text{LGD}=0.60\times \$1{,}000{,}000=\$600{,}000
$$

Step 2: Calculate expected loss.

$$
\text{EL}
=
0.03\times \$600{,}000
=\$18{,}000
$$

Interpretation:

```text
The investor expects to lose $18,000 on average from credit risk for that period.
```

## Expected Exposure

Expected exposure is the amount at risk at the default date.

For a bond, expected exposure may include:

```text
principal
coupon due
accrued interest
market value of remaining promised cash flows
```

Example:

```text
A one-year 4% bond issued at par has exposure of about 104 at maturity,
because the investor is owed 100 principal + 4 coupon.
```

So if recovery is 40%:

$$
\text{LGD}=104\times(1-0.40)=62.40
$$

If POD is 1.25%:

$$
\text{Expected Loss}=0.0125\times62.40=0.7800
$$

The coupon matters because it is part of what the investor expects to receive.

## Present Value of Expected Loss

Expected loss occurs in the future, so valuation needs present value.

For a given period:

$$
\text{PV(Expected Loss)}_t
=
\text{EL}_t\times \text{Discount Factor}_t
$$

And:

$$
\text{EL}_t
=
\text{POD}_t\times\text{LGD}_t
$$

So:

$$
\text{PV(Expected Loss)}_t
=
\text{POD}_t\times\text{LGD}_t\times DF_t
$$

This is the building block of CVA.

## Credit Valuation Adjustment

[[Credit Valuation Adjustment]] is the sum of the present values of expected losses.

$$
\text{CVA}
=
\sum_{t=1}^{T}
\text{PV(Expected Loss)}_t
$$

Expanded:

$$
\text{CVA}
=
\sum_{t=1}^{T}
\text{POD}_t\times\text{LGD}_t\times DF_t
$$

Risky bond value:

$$
V_{\text{risky}}
=
V_{\text{default-free}}
-
\text{CVA}
$$

The intuition:

```text
Start with what the bond would be worth if it could not default.
Subtract the present value of expected credit losses.
What remains is the risky bond value.
```

## Worked Example: Mini CVA Table

Suppose a risky bond has:

| Year | Expected Exposure | Recovery Rate | POD | Discount Factor |
|---:|---:|---:|---:|---:|
| 1 | 104 | 40% | 1.25% | 0.9709 |
| 2 | 102 | 40% | 1.23% | 0.9426 |
| 3 | 100 | 40% | 1.22% | 0.9151 |

Step 1: Calculate LGD each year.

| Year | LGD |
|---:|---:|
| 1 | $104(0.60)=62.40$ |
| 2 | $102(0.60)=61.20$ |
| 3 | $100(0.60)=60.00$ |

Step 2: Calculate expected loss.

| Year | Expected Loss |
|---:|---:|
| 1 | $0.0125(62.40)=0.7800$ |
| 2 | $0.0123(61.20)=0.7528$ |
| 3 | $0.0122(60.00)=0.7320$ |

Step 3: Discount expected losses.

| Year | PV Expected Loss |
|---:|---:|
| 1 | $0.7800(0.9709)=0.7573$ |
| 2 | $0.7528(0.9426)=0.7096$ |
| 3 | $0.7320(0.9151)=0.6699$ |

CVA:

$$
0.7573+0.7096+0.6699=2.1368
$$

If the default-free value is 98.50:

$$
V_{\text{risky}}
=
98.50-2.1368
=96.3632
$$

## Credit Spread Link

Expected loss helps explain credit spreads.

In a simplified one-period model:

$$
\text{Credit Spread}
\approx
\text{POD}\times\text{LGD\%}
$$

This is expected loss as a percentage of exposure.

Example:

| Input | Value |
|---|---:|
| POD | 2% |
| Recovery rate | 60% |
| LGD% | 40% |

$$
\text{Spread}
\approx0.02\times0.40=0.008=80\text{ bps}
$$

But in real markets, credit spreads also include:

```text
risk premium
liquidity premium
tax effects
supply/demand
uncertainty about default timing
```

So expected loss is the foundation, not the entire observed spread.

## CDS Link

In a [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]], the protection leg is the present value of expected default payments.

That is basically the present value of expected losses.

Fair CDS pricing sets:

$$
\text{PV(Premium leg)}=\text{PV(Protection leg)}
$$

And the protection leg depends on:

```text
POD / hazard rate
LGD / recovery rate
timing of default
discount factors
```

So:

```text
Higher expected loss -> higher fair CDS spread.
```

## What Changes Expected Loss?

Expected loss rises when:

| Driver | Effect |
|---|---|
| POD increases | Default is more likely |
| Recovery rate decreases | Loss if default occurs is larger |
| Expected exposure increases | More money is at risk |
| Discount factor increases | Future expected loss has higher PV |

Expected loss falls when:

```text
default probability falls,
recovery improves,
exposure declines,
or losses occur farther in the future at lower present value.
```

## Limitations and Model Risk

Expected loss is clean in a formula, but messy in the real world.

| Limitation | Why It Matters |
|---|---|
| POD and recovery are not independent | In recessions, default probabilities often rise while recovery rates fall |
| Historical POD may not equal pricing POD | Valuation uses risk-neutral probabilities implied by market prices |
| Recovery is uncertain | Final bankruptcy recovery may differ from assumed recovery |
| Exposure can change | Floating-rate bonds, amortizing debt, derivatives, and callable structures can change exposure |
| Spreads include more than expected loss | Liquidity, taxes, and risk premia also affect observed spreads |

The big exam intuition:

```text
Expected loss is the foundation of credit valuation,
but market spreads usually compensate investors for more than average expected loss.
```

## Real-World / Vignette Scenarios

### Scenario 1: Same POD, Different LGD

Two bonds are issued by the same company.

One is senior secured.

The other is subordinated unsecured.

They may have similar POD because the issuer is the same, but different LGD because recoveries differ.

Exam implication:

```text
Expected loss can differ even when default probability is the same.
```

### Scenario 2: Same LGD, Different POD

Two bonds have similar seniority and collateral, but one issuer is much more leveraged.

LGD may be similar.

POD is higher for the weaker issuer.

Exam implication:

```text
Expected loss rises through the probability channel.
```

### Scenario 3: Recession Shock

During a recession:

```text
POD rises because borrowers are weaker.
Recovery falls because collateral values fall.
Expected exposure may rise for some instruments.
```

Expected loss can jump because multiple inputs worsen at once.

Exam implication:

```text
Credit spreads can widen sharply when both POD and LGD deteriorate.
```

## Comparisons

| Concept | Meaning | Formula |
|---|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Chance default occurs | POD |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Loss if default occurs | $(1-\text{RR})\times EE$ |
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | Probability-weighted default loss | POD x LGD |
| [[Present value of the expected loss]] | Expected loss discounted to today | EL x DF |
| [[Credit Valuation Adjustment]] | Sum of PV expected losses | $\sum POD_t\times LGD_t\times DF_t$ |
| [[Credit spread]] | Yield compensation for credit risk and other premia | roughly POD x LGD% |

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Confuse LGD with expected loss | LGD assumes default occurs | Expected loss = POD x LGD |
| Forget expected exposure | LGD depends on amount at risk | Include coupon/principal/exposure as relevant |
| Use recovery rate instead of loss severity | Recovery is what comes back | LGD% = 1 - recovery rate |
| Forget to discount expected loss for valuation | Future losses need present value | PV EL = EL x DF |
| Treat CVA as one-period EL | CVA sums PV expected losses across periods | CVA = sum of PV EL |
| Add CVA to default-free value | Credit risk reduces value | Risky value = default-free value - CVA |
| Assume observed spread equals expected loss exactly | Market spreads include risk/liquidity premia | POD x LGD is a simplified approximation |
| Ignore timing of default | Earlier expected losses have greater PV impact | Use period PODs and discount factors |
| Use historical POD for valuation without adjustment | Historical POD lacks the market risk premium | Valuation generally uses risk-neutral POD |
| Assume POD and recovery move separately | They can worsen together in stress | Recession can mean higher POD and higher LGD |

## Memory Hooks

```text
Expected loss = likelihood x severity.
```

```text
LGD is the hit if default happens.
Expected loss is the average hit before you know.
```

```text
CVA is expected losses brought back to today.
```

## Exam-Day Checklist

When an expected-loss question appears, ask:

1. Is the question asking for dollar EL, percentage EL, PV of EL, or CVA?
2. Do I have POD?
3. Do I have recovery rate and expected exposure to calculate LGD?
4. Do I need to discount the expected loss?
5. Is this one period or multiple periods?
6. Am I valuing a risky bond, a CDS, or just calculating credit loss?
7. Are spreads being approximated from expected loss, or are market premia also relevant?

Then use:

| Task | Formula |
|---|---|
| LGD | $(1-\text{Recovery Rate})\times\text{Expected Exposure}$ |
| Expected loss | $\text{POD}\times\text{LGD}$ |
| PV expected loss | $\text{Expected Loss}\times DF$ |
| CVA | $\sum \text{POD}_t\times\text{LGD}_t\times DF_t$ |
| Risky bond value | $V_{\text{default-free}}-\text{CVA}$ |
| Simple spread | $\text{POD}\times\text{LGD\%}$ |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Recovery rate]]
- [[Expected exposure]]
- [[Present value of the expected loss]]
- [[Credit Valuation Adjustment]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS spread]]
- [[Credit spread risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Default risk]]
