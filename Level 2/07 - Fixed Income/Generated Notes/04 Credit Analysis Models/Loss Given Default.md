---
title: Loss Given Default
subject: Fixed Income
tags: [CFA-L2, fixed-income, loss-given-default, recovery-rate, expected-loss, cva, cds, credit-risk]
aliases: [loss given default, LGD, loss severity, loss given default (LGD)]
---

# Loss Given Default

## The Real-World Analogy

Imagine you lend someone $100.

They default.

But default does not necessarily mean you lose the full $100.

Maybe you recover $40 by selling collateral or receiving money through bankruptcy.

Then your actual loss is:

```text
Amount at risk: $100
Amount recovered: $40
Loss: $60
```

That $60 is the loss given default.

The key idea:

```text
Default answers: Did the borrower fail?
LGD answers: If they fail, how bad is the loss?
```

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] is the amount lost if default occurs.

In percentage terms, it is the part of the exposure that is not recovered after default.

If the recovery rate is 40%, the loss given default percentage is 60%.

```text
Recovery rate is what you get back.
LGD is what you lose.
```

## CFA Definition

The glossary definition:

```text
The amount that will be lost if a default occurs.
```

CFA often uses LGD together with:

| Concept | Meaning |
|---|---|
| [[Expected exposure]] | Amount at risk at the time of possible default |
| [[Recovery rate]] | Percentage recovered after default |
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Probability default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | Probability-weighted loss |
| [[Credit Valuation Adjustment]] | Present value of expected credit losses |

## Core Formula

In dollar terms:

$$
\text{LGD}
=
(1-\text{Recovery Rate})\times \text{Expected Exposure}
$$

In percentage terms:

$$
\text{LGD\%}
=
1-\text{Recovery Rate}
$$

Where:

| Term | Meaning |
|---|---|
| Recovery rate | Percentage of exposure recovered if default occurs |
| Expected exposure | Amount that could be lost at the default date |
| LGD | Dollar amount lost if default occurs |
| LGD% | Loss severity as a percentage of exposure |

## Why Expected Exposure Matters

LGD is not always calculated from par value.

It is calculated from the amount exposed to default at that point.

For a bond, expected exposure may include:

```text
principal
accrued interest
coupon due
market value of remaining promised cash flows
```

Example:

```text
One-year 4% bond priced at par.
At year-end, exposure is roughly 104, not 100,
because principal plus coupon is due.
```

That is why CFA writes:

$$
\text{LGD}=(1-\text{Recovery Rate})\times\text{Expected Exposure}
$$

not simply:

```text
LGD = 1 - recovery rate
```

The percentage version is $1-\text{RR}$.

The dollar version needs exposure.

## Worked Example: Basic LGD

Suppose:

| Input | Value |
|---|---:|
| Expected exposure | $104 |
| Recovery rate | 40% |

LGD percentage:

$$
1-0.40=0.60=60\%
$$

Dollar LGD:

$$
0.60\times \$104=\$62.40
$$

Interpretation:

```text
If default occurs, the expected loss conditional on default is $62.40.
```

That is not yet expected loss because we have not multiplied by default probability.

## LGD vs Expected Loss

This is one of the most important distinctions.

| Concept | Formula | Meaning |
|---|---|---|
| LGD | $(1-\text{RR})\times\text{Exposure}$ | Loss if default occurs |
| Expected loss | $\text{POD}\times\text{LGD}$ | Probability-weighted loss |

LGD is conditional on default.

Expected loss includes the chance that default may not happen.

## Worked Example: LGD to Expected Loss

Suppose:

| Input | Value |
|---|---:|
| Expected exposure | $1,000,000 |
| Recovery rate | 35% |
| POD | 2% |

LGD:

$$
(1-0.35)\times \$1{,}000{,}000
=0.65\times \$1{,}000{,}000
=\$650{,}000
$$

Expected loss:

$$
0.02\times \$650{,}000
=\$13{,}000
$$

Interpretation:

```text
If default happens, expected loss is $650,000.
Before knowing whether default happens, probability-weighted expected loss is $13,000.
```

## LGD in CVA

[[Credit Valuation Adjustment]] is the present value of expected losses.

For each period:

$$
\text{Expected Loss}_t
=
\text{POD}_t\times\text{LGD}_t
$$

Then:

$$
\text{CVA}
=
\sum_t
\text{Expected Loss}_t\times\text{Discount Factor}_t
$$

So LGD is one of the main inputs that lowers risky-bond value.

The chain:

```text
Lower recovery rate
-> higher LGD
-> higher expected loss
-> higher CVA
-> lower risky bond value
-> wider required credit spread
```

## Worked Example: Mini CVA

Suppose a one-period risky bond has:

| Input | Value |
|---|---:|
| Expected exposure | $105 |
| Recovery rate | 60% |
| POD | 3% |
| Discount factor | 0.96 |

LGD:

$$
(1-0.60)\times105=42
$$

Expected loss:

$$
0.03\times42=1.26
$$

Present value of expected loss:

$$
1.26\times0.96=1.2096
$$

So this period contributes about $1.21 to CVA.

## Credit Spread Link

A simple credit spread approximation is:

$$
\text{Credit Spread}\approx\text{POD}\times\text{LGD\%}
$$

If POD is 2% and recovery rate is 60%:

$$
\text{LGD\%}=1-0.60=40\%
$$

$$
\text{Spread}\approx0.02\times0.40=0.008=80\text{ bps}
$$

If recovery falls from 60% to 30%:

$$
\text{LGD\%}=70\%
$$

$$
\text{Spread}\approx0.02\times0.70=0.014=140\text{ bps}
$$

Holding POD constant:

```text
Lower recovery -> higher LGD -> wider spread.
```

## CDS Pricing and Settlement

In a [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]], LGD determines the protection payment after a credit event.

Cash settlement:

$$
\text{Payout Amount}
=
\text{LGD\%}\times\text{Notional}
$$

Since:

$$
\text{LGD\%}=1-\text{Recovery Rate}
$$

Then:

$$
\text{Payout Amount}
=
(1-\text{Recovery Rate})\times\text{Notional}
$$

If notional is $10 million and recovery is 40%:

$$
\text{Payout}=0.60\times \$10{,}000{,}000=\$6{,}000{,}000
$$

## CDS Auction and Recovery

Actual recovery can take a long time in bankruptcy.

CDS settlement cannot wait years for final recovery.

So the market uses an auction process to estimate the recovery value of deliverable defaulted debt.

That auction value determines:

```text
Recovery rate for CDS settlement
LGD for the immediate payout
```

Exam implication:

```text
The CDS auction recovery can differ from the ultimate recovery realized later.
```

This matters if the protection buyer also owns the underlying bond.

## Seniority and Collateral

LGD depends heavily on where the debt sits in the capital structure.

| Debt Type | Expected Recovery | LGD |
|---|---:|---:|
| Senior secured | Higher | Lower |
| Senior unsecured | Moderate | Moderate |
| Subordinated debt | Lower | Higher |
| Equity | Residual claim | Highest loss risk |

Why?

In default, claims are paid according to priority.

Collateral and seniority increase the chance that the creditor recovers more value.

So:

```text
Better collateral / higher seniority -> higher recovery -> lower LGD.
```

## Business Cycle Effect

Recovery rates tend to be procyclical.

That means:

| Environment | Recovery Rate | LGD |
|---|---:|---:|
| Strong economy | Higher | Lower |
| Weak economy / recession | Lower | Higher |

Why?

In a strong economy, assets can often be sold at better prices, financing is available, and buyers are willing to purchase distressed assets.

In a recession, many firms may default at the same time, collateral values may be depressed, and buyers of distressed assets may demand steep discounts.

This creates a painful credit-risk interaction:

```text
When default probabilities rise,
recovery rates often fall,
so LGD rises too.
```

Exam implication:

```text
Credit losses can worsen from both sides at once:
higher POD and higher LGD.
```

## Real-World / Vignette Scenarios

### Scenario 1: Secured vs Unsecured Bond

Two bonds are issued by the same distressed company.

One is senior secured.

The other is subordinated unsecured.

They may have similar POD because the issuer is the same.

But their LGDs are different.

Exam implication:

```text
Same issuer does not mean same loss severity.
Seniority and collateral affect LGD.
```

### Scenario 2: CDS Settlement

A protection buyer owns a $10 million CDS.

After default, deliverable debt trades at 25% of par.

Recovery rate is 25%.

LGD is 75%.

Payout:

$$
0.75\times \$10{,}000{,}000=\$7{,}500{,}000
$$

Exam implication:

```text
CDS payout is based on loss severity, not full notional unless recovery is zero.
```

### Scenario 3: Improving Collateral Value

A company owns valuable real estate securing its bonds.

Real estate values rise.

Expected recovery improves.

LGD falls.

Credit spreads can tighten even if POD is unchanged.

Exam implication:

```text
Spreads can change because loss severity changes, not only because default probability changes.
```

## Comparisons

| Concept | What It Means | Formula / Relationship |
|---|---|---|
| [[Recovery rate]] | Percentage recovered if default occurs | RR |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Percentage or amount lost if default occurs | $1-\text{RR}$ or $(1-\text{RR})\times EE$ |
| [[Expected exposure]] | Amount at risk at default date | EE |
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Chance default occurs | POD |
| [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]] | Probability-weighted loss | POD x LGD |
| [[Credit Valuation Adjustment]] | PV of expected losses | Sum of discounted expected losses |

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Confuse LGD with expected loss | LGD assumes default occurs | Expected loss = POD x LGD |
| Use par when expected exposure is given | Exposure may include coupon/accrued value | LGD uses expected exposure |
| Forget LGD is the complement of recovery | Higher recovery means lower LGD | LGD% = 1 - recovery rate |
| Treat recovery rate as payout | In CDS, seller pays the loss, not recovery | Payout = notional x LGD% |
| Assume all bonds of same issuer have same LGD | Seniority/collateral differ | Same POD can have different LGD |
| Think lower recovery narrows spreads | Lower recovery increases expected loss | Lower recovery widens spreads |
| Ignore auction recovery in CDS | CDS settlement uses market/auction recovery | Final bankruptcy recovery may differ |
| Mix percentage LGD and dollar LGD | LGD% is not the same as dollar loss | Use exposure to convert |
| Ignore the coupon in expected exposure | Exposure may include coupon due at the default date | Use expected exposure, not just par |
| Assume recovery is stable across the cycle | Recoveries often fall in recessions | Weak economy can mean higher POD and higher LGD |

## Memory Hooks

```text
Recovery is what comes back.
LGD is what does not.
```

```text
POD asks: will default happen?
LGD asks: if it happens, how bad?
```

```text
Expected loss = likelihood x severity.
```

## Exam-Day Checklist

When an LGD question appears, ask:

1. Is recovery rate given?
2. Is expected exposure or notional given?
3. Am I calculating LGD%, dollar LGD, expected loss, CVA, or CDS payout?
4. Does the bond's seniority or collateral affect recovery?
5. Is the question using CDS settlement recovery or ultimate bankruptcy recovery?
6. Am I accidentally using par instead of expected exposure?

Then use:

| Task | Formula |
|---|---|
| LGD% | $1-\text{Recovery Rate}$ |
| Dollar LGD | $(1-\text{Recovery Rate})\times\text{Expected Exposure}$ |
| Expected loss | $\text{POD}\times\text{LGD}$ |
| CDS payout | $\text{Notional}\times(1-\text{Recovery Rate})$ |
| CVA | $\sum \text{POD}_t\times\text{LGD}_t\times DF_t$ |
| Simple spread | $\text{POD}\times\text{LGD\%}$ |

## Related Concepts

- [[Recovery rate]]
- [[Expected exposure]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Credit Valuation Adjustment]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS spread]]
- [[Credit event]]
- [[Physical settlement]]
- [[Cheapest-to-deliver]]
- [[Credit spread risk]]
- [[Seniority ranking]]
