---
title: Credit Valuation Adjustment
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-valuation-adjustment, cva, expected-loss, risky-bond-valuation, credit-risk]
aliases: [credit valuation adjustment, CVA, present value of expected loss, present value of expected losses, value assuming no default, VND]
---

# Credit Valuation Adjustment

## The Real-World Analogy

Imagine two versions of the same bond.

Version A is magic: it cannot default.

Version B is real: the issuer might default.

The promised coupons and principal are the same, but Version B is worth less because some promised cash flows may not arrive.

The difference between the two values is the cost of credit risk.

That cost is [[Credit Valuation Adjustment]].

```text
Default-free value
- present value of expected credit losses
= risky bond value
```

CVA is the deduction for credit risk.

## Plain-English Definition

Credit valuation adjustment, or CVA, is the present value of expected credit losses.

In plain English:

```text
CVA is the amount you subtract from a default-free value
to account for the possibility of default.
```

If a bond would be worth 100 with no default risk, and the present value of expected credit losses is 4, then the risky bond is worth about 96.

## CFA Definition

CFA frames CVA as the present value of expected loss from default risk.

The related glossary concept, [[Present value of the expected loss]], says it is conceptually the most one would pay a third party, such as an insurer, to entirely remove the credit risk of purchasing and holding the bond.

That sentence is important.

It means:

```text
CVA is like the fair value of default insurance.
```

That is why CVA connects naturally to [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] pricing.

## Core Formulas

For each period:

$$
\text{Expected Loss}_t
=
\text{POD}_t\times\text{LGD}_t
$$

Present value of that expected loss:

$$
\text{PV(Expected Loss)}_t
=
\text{POD}_t\times\text{LGD}_t\times DF_t
$$

CVA:

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

CFA often calls the default-free value:

```text
VND = value assuming no default
```

So:

$$
V_{\text{risky}}=\text{VND}-\text{CVA}
$$

## What Each Input Means

| Input | Meaning | What Raises CVA? |
|---|---|---|
| [[Expected exposure]] | Amount at risk at the default date | Higher exposure |
| [[Recovery rate]] | Percentage recovered after default | Lower recovery |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Dollar loss if default occurs | Higher LGD |
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Probability default occurs in that period | Higher POD |
| [[Discount factor]] | Present value weight | Higher discount factor |

Because:

$$
\text{LGD}_t=(1-\text{Recovery Rate})\times \text{Expected Exposure}_t
$$

CVA can also be viewed as:

$$
\text{CVA}
=
\sum_t
\text{POD}_t
\times
(1-\text{Recovery Rate}_t)
\times
\text{Expected Exposure}_t
\times
DF_t
$$

## Why CVA Exists

The clean default-free bond formula discounts promised cash flows.

But risky bonds have promised cash flows that might not be paid.

There are two broad valuation approaches:

1. Increase the discount rate by adding a credit spread.
2. Explicitly model expected default losses and subtract them from the default-free value.

CVA is the second approach.

It says:

```text
Start with the value if there were no default.
Estimate expected default losses by date.
Discount those expected losses.
Subtract them.
```

This is useful because it shows exactly what drives credit risk:

```text
exposure, recovery, default probability, and timing.
```

## Mechanism Ladder

Rule:

```text
Risky value = VND - CVA.
```

Why:

```text
A risky bond is worth less than the same bond without default risk.
```

Mechanism:

```text
Default can occur in different periods.
Each period has a probability of default.
If default occurs, the investor loses LGD.
That probability-weighted loss is expected loss.
Discount each expected loss.
Sum them into CVA.
Subtract from default-free value.
```

Assumptions:

```text
POD, recovery, exposure, and discount factors are estimated correctly.
Credit losses are modeled separately from liquidity/tax effects.
The discount factors are appropriate for present valuing expected losses.
```

Failure mode:

```text
If recovery is wrong, POD is wrong, or liquidity effects are mixed into spreads,
CVA may not match observed market prices.
```

Exam implication:

```text
If POD or LGD rises, CVA rises and risky fair value falls.
```

## Worked Example: Simple CVA Table

Suppose a three-year risky bond has:

| Year | Expected Exposure | Recovery Rate | POD | Discount Factor |
|---:|---:|---:|---:|---:|
| 1 | 104.00 | 40% | 1.25% | 0.9709 |
| 2 | 102.00 | 40% | 1.23% | 0.9426 |
| 3 | 100.00 | 40% | 1.22% | 0.9151 |

Step 1: Calculate LGD.

$$
\text{LGD}=(1-\text{RR})\times EE
$$

| Year | LGD |
|---:|---:|
| 1 | $0.60(104.00)=62.40$ |
| 2 | $0.60(102.00)=61.20$ |
| 3 | $0.60(100.00)=60.00$ |

Step 2: Calculate expected loss.

$$
\text{EL}=\text{POD}\times\text{LGD}
$$

| Year | Expected Loss |
|---:|---:|
| 1 | $0.0125(62.40)=0.7800$ |
| 2 | $0.0123(61.20)=0.7528$ |
| 3 | $0.0122(60.00)=0.7320$ |

Step 3: Discount expected loss.

$$
\text{PV(EL)}=\text{EL}\times DF
$$

| Year | PV Expected Loss |
|---:|---:|
| 1 | $0.7800(0.9709)=0.7573$ |
| 2 | $0.7528(0.9426)=0.7096$ |
| 3 | $0.7320(0.9151)=0.6699$ |

Step 4: Sum PV expected losses.

$$
\text{CVA}=0.7573+0.7096+0.6699=2.1368
$$

If value assuming no default is 98.50:

$$
V_{\text{risky}}
=
98.50-2.1368
=96.3632
$$

Interpretation:

```text
The bond loses 2.1368 of value because of expected credit losses.
```

## Full Exam Workflow

When CFA gives a CVA table, the steps are usually:

1. Calculate value assuming no default, or VND.
2. Calculate expected exposure for each date.
3. Calculate LGD for each date.
4. Calculate POD for each date.
5. Multiply LGD by POD to get expected loss.
6. Multiply expected loss by the discount factor to get PV expected loss.
7. Sum PV expected losses to get CVA.
8. Subtract CVA from VND to get risky fair value.

In table form:

| Step | Formula |
|---|---|
| LGD | $(1-\text{RR})\times EE$ |
| Expected loss | $POD\times LGD$ |
| PV expected loss | $POD\times LGD\times DF$ |
| CVA | $\sum PV(\text{Expected Loss})$ |
| Risky fair value | $VND-CVA$ |

## Relationship to Credit Spreads

CVA and credit spreads are two ways to express credit compensation.

| Measure | Form |
|---|---|
| CVA | Present value dollar deduction from default-free value |
| Credit spread | Annualized yield premium over benchmark |

The curriculum point:

```text
The same credit risk can be expressed as a CVA amount or as a credit spread.
```

Example:

```text
CVA = 3.1549 per 100 of par
Equivalent credit spread may be about 77 bps over the benchmark
```

The spread is not always exactly POD x LGD because market spreads can include liquidity, taxes, and risk premia.

But the intuition is:

```text
Higher CVA -> lower risky price -> higher credit spread.
```

## Relationship to CDS

CVA is closely related to [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] pricing.

The protection leg of a CDS is the present value of expected default payments.

That is conceptually similar to CVA:

```text
CVA is the PV of expected credit loss.
CDS protection is insurance against that credit loss.
```

At fair CDS pricing:

$$
\text{PV(Premium leg)}=\text{PV(Protection leg)}
$$

The protection leg depends on:

```text
POD, LGD, recovery, exposure, default timing, and discount factors.
```

So the CVA framework helps explain the fair CDS spread.

## What Raises and Lowers CVA

| Change | CVA Effect | Why |
|---|---:|---|
| POD increases | Rises | Default is more likely |
| Recovery rate decreases | Rises | Loss severity is larger |
| Expected exposure increases | Rises | More is at risk |
| Discount factor increases | Rises | Future losses have higher present value |
| Default expected earlier | Rises | Earlier losses are discounted less |
| Credit quality improves | Falls | Lower expected default loss |

## Real-World / Vignette Scenarios

### Scenario 1: Bond Looks Cheap vs Analyst CVA

A corporate bond trades below the analyst's fair value.

The analyst's CVA is lower than the market-implied credit loss.

Interpretation:

```text
The market may be overestimating POD or LGD.
The bond may be undervalued if the analyst is correct.
```

### Scenario 2: Recovery Assumption Changes

An issuer pledges high-quality collateral.

Expected recovery rises.

LGD falls.

CVA falls.

Risky fair value rises.

### Scenario 3: Default Probability Shock

A company issues a profit warning and violates debt covenants.

POD rises.

CVA rises.

Risky bond value falls and spreads widen.

## Comparisons

| Concept | What It Answers |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | What is the probability-weighted loss in a period? |
| [[Present value of the expected loss]] | What is that expected loss worth today? |
| [[Credit Valuation Adjustment]] | What is the total PV credit-risk deduction across periods? |
| [[Credit spread]] | What annual yield premium compensates for credit risk? |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] | What derivative transfers that credit risk? |

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Add CVA to VND | Credit risk lowers value | Risky value = VND - CVA |
| Treat CVA as one-period expected loss | CVA is sum of PV expected losses | Calculate across all relevant periods |
| Forget to discount expected losses | Future losses must be present valued | PV EL = EL x DF |
| Use recovery rate instead of LGD | Recovery is what comes back | LGD = (1 - RR) x exposure |
| Ignore expected exposure | Exposure can change by date | Use date-specific exposure |
| Think changing POD changes VND | VND is no-default value | POD affects CVA, not VND |
| Treat observed spread as pure CVA | Spreads include liquidity/tax/risk premia | CVA isolates expected credit loss under assumptions |
| Confuse CVA with CDS premium leg | CVA is PV expected loss; CDS premium leg pays for protection | Link through protection-leg valuation |

## Memory Hooks

```text
CVA is the credit-risk haircut.
```

```text
VND is the clean no-default value.
CVA is what credit risk takes away.
```

```text
CVA = expected losses brought back to today.
```

## Exam-Day Checklist

When a CVA question appears, ask:

1. Do I have VND or do I need to calculate it?
2. Do I have expected exposure for each date?
3. Do I need to compute LGD from recovery rate?
4. Are PODs conditional/period probabilities or cumulative?
5. Do I have discount factors?
6. Am I being asked for CVA, risky value, fair value, spread, or CDS interpretation?
7. Did I subtract CVA from VND?

Then use:

| Task | Formula |
|---|---|
| LGD | $(1-\text{RR})\times EE$ |
| Expected loss | $POD\times LGD$ |
| PV expected loss | $POD\times LGD\times DF$ |
| CVA | $\sum POD_t\times LGD_t\times DF_t$ |
| Risky fair value | $VND-CVA$ |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Present value of the expected loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Recovery rate]]
- [[Expected exposure]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS spread]]
- [[Credit spread]]
- [[Credit spread risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Value assuming no default]]
