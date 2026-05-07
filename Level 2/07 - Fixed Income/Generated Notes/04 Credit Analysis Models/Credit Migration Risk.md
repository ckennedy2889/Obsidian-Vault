---
title: Credit Migration Risk
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-migration-risk, downgrade-risk, credit-ratings, transition-matrix, spread-risk]
aliases: [credit migration risk, downgrade risk, rating migration risk, credit rating migration, credit migration]
---

# Credit Migration Risk

## The Real-World Analogy

Imagine a student does not fail a class.

But halfway through the semester, the teacher changes the student's expected grade from A to C.

The student has not failed.

But the market's opinion of the student has deteriorated.

That is credit migration risk.

For a bond:

```text
Default risk = issuer fails to pay.
Migration risk = issuer becomes viewed as lower quality before default.
```

A downgrade can hurt bondholders even if every coupon is still paid.

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] is the risk that a bond issuer's credit quality deteriorates and its rating migrates lower.

It is also called [[Downgrade risk]].

In practical language:

```text
The issuer does not have to default for you to lose money.
If the market thinks default risk has increased,
the bond's spread widens and price falls.
```

## CFA Definition

The glossary definition:

```text
The risk that a bond issuer's creditworthiness deteriorates, or migrates lower,
leading investors to believe the risk of default is higher.
```

The key phrase is:

```text
leading investors to believe default risk is higher
```

That belief changes the required credit spread.

## Why Migration Risk Exists

Bond prices reflect expected future cash flows discounted at required yields.

For a risky bond, the required yield includes a credit spread.

If credit quality worsens:

```text
rating falls
market-implied default risk rises
credit spread widens
required yield rises
bond price falls
```

No missed coupon is required.

The loss comes from repricing.

## Default Risk vs Migration Risk

| Concept | Event | Price Impact |
|---|---|---|
| [[Default risk]] | Issuer fails to pay | Loss from missed payments/recovery value |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] | Issuer is upgraded or downgraded | Price changes because required spread changes |

Default is the endpoint.

Migration is the path.

Many issuers are downgraded several times before they eventually default.

This is why a model that treats default as a total surprise can miss an important real-world risk path.

## Credit Ratings Are Ordinal

[[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]] are ordinal rankings.

That means:

```text
AAA is better than AA.
AA is better than A.
A is better than BBB.
```

But ratings do not directly say:

```text
AA has exactly half the default probability of A.
```

To quantify migration risk, analysts use historical or model-based transition probabilities.

## Transition Matrix

A [[Transition matrix]] shows the probability that a bond migrates from one rating to another over a period, often one year.

Example layout:

| Current Rating | AAA | AA | A | BBB | BB | Default |
|---|---:|---:|---:|---:|---:|---:|
| A | 0.5% | 4.0% | 89.0% | 5.0% | 1.0% | 0.5% |

This row means:

```text
An A-rated issuer has an 89% chance of remaining A,
a 5% chance of moving to BBB,
a 1% chance of moving to BB,
and so on.
```

In some CFA problems, default is excluded because the question asks for expected return given migration but no default.

## Price Impact of Spread Migration

If a rating changes, the required credit spread changes.

The approximate price impact is:

$$
\%\Delta P
\approx
-\text{Duration}\times \Delta\text{Spread}
$$

For credit migration questions, CFA often uses modified duration or spread duration.

Use the duration specified in the vignette. If the problem says the bond "will have" a certain duration at the end of the year, use that horizon duration for the migration impact.

Where:

| Term | Meaning |
|---|---|
| Duration | Price sensitivity to yield/spread changes |
| $\Delta\text{Spread}$ | New rating spread minus current rating spread |

If a downgrade widens the spread:

```text
Delta spread is positive -> price change is negative.
```

If an upgrade tightens the spread:

```text
Delta spread is negative -> price change is positive.
```

## Worked Example: Downgrade Price Impact

A bond has:

| Input | Value |
|---|---:|
| Modified duration | 7.2 |
| Current spread | 150 bps |
| Spread after downgrade | 250 bps |

Spread change:

$$
250-150=100\text{ bps}=0.0100
$$

Price impact:

$$
\%\Delta P
\approx
-7.2(0.0100)
=-0.072
=-7.2\%
$$

Interpretation:

```text
The bond loses about 7.2% from spread widening,
even if it does not default.
```

## Expected Migration Adjustment

To estimate expected return with migration risk, calculate the probability-weighted price impact across possible ratings.

General logic:

$$
\text{Expected Migration Adjustment}
=
\sum_i
P_i
\times
\left(-D\times\Delta s_i\right)
$$

Then:

$$
\text{Expected Return}
\approx
\text{YTM}
+
\text{Expected Migration Price Impact}
$$

Because migration price impact is often negative, CFA may phrase this as:

$$
\text{Expected Return}
\approx
\text{YTM}
-
\text{Credit Migration Adjustment}
$$

## Worked Example: Expected Return Adjustment

Suppose a BBB bond has:

| Input | Value |
|---|---:|
| YTM | 5.50% |
| Modified duration | 7.5 |

Possible rating migrations over one year:

| Outcome | Probability | Spread Change | Price Impact |
|---|---:|---:|---:|
| Upgrade | 5% | -40 bps | $-7.5(-0.0040)=+3.00\%$ |
| No change | 90% | 0 bps | 0.00% |
| Downgrade | 5% | +120 bps | $-7.5(0.0120)=-9.00\%$ |

Probability-weighted migration impact:

$$
(0.05)(3.00\%)+(0.90)(0)+(0.05)(-9.00\%)
$$

$$
=0.15\%-0.45\%=-0.30\%
$$

Expected return:

$$
5.50\%-0.30\%=5.20\%
$$

The downgrade and upgrade probabilities are equal, but the downgrade hurts more because spread widening is larger.

## Why Migration Usually Reduces Expected Return

CFA emphasizes two reasons credit migration often reduces expected return:

| Reason | Explanation |
|---|---|
| Probabilities may be skewed toward downgrade | Lower migration outcomes may be more likely than upgrades |
| Downgrade spread widening is often larger | Moving down in credit quality can widen spreads more than an upgrade tightens them |

So even if the bond does not default, the expected migration adjustment can be negative.

This is the key intuition:

```text
Downgrades usually hurt more than upgrades help.
```

## Fallen Angels

A [[Fallen angel]] is a bond downgraded from investment grade to high yield.

This can create forced selling.

Why?

Many institutional mandates restrict holdings to investment-grade bonds.

When a bond falls below investment grade:

```text
rating downgrade
-> forced selling by restricted investors
-> price pressure
-> spread widens more than fundamentals alone might imply
```

Exam implication:

```text
Downgrades can create technical pressure, not just fundamental repricing.
```

## Link to Spread Duration

[[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] measures the price sensitivity to spread changes.

Credit migration risk is one reason spreads change.

The chain:

```text
Downgrade risk
-> spread widening
-> price decline
-> negative migration adjustment
```

Formula:

$$
\%\Delta P
\approx
-\text{Spread Duration}\times\Delta\text{Spread}
$$

This is why spread duration is useful even when no default occurs.

## Link to Credit Spreads

Credit spreads compensate investors for more than actual default.

They also compensate for:

```text
downgrade risk,
spread volatility,
liquidity risk,
and uncertainty about future credit quality.
```

If investors fear migration lower, they demand a wider spread today.

## Real-World / Vignette Scenarios

### Scenario 1: BBB Bond Near High Yield

A BBB-minus bond sits one notch above high yield.

The issuer's leverage rises.

The bond has not defaulted, but the market fears a downgrade to BB.

Spreads widen before any rating agency action.

Exam implication:

```text
Migration risk can be priced before official migration occurs.
```

### Scenario 2: Upgrade Candidate

An issuer improves margins, pays down debt, and receives a positive outlook.

The market expects an upgrade.

Spreads tighten.

Bond price rises.

Exam implication:

```text
Credit migration can help returns when credit quality improves.
```

### Scenario 3: Fallen Angel Forced Selling

A pension fund can hold only investment-grade bonds.

A bond is downgraded to high yield.

The fund sells even if it believes the bond is cheap.

Exam implication:

```text
Mandate-driven selling can depress prices after downgrade.
```

## Comparisons

| Concept | What It Means | Main Price Channel |
|---|---|---|
| [[Default risk]] | Issuer fails to pay | Recovery / loss given default |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] | Rating or credit quality changes | Spread widening/tightening |
| [[Spread risk]] | Spread changes for any credit/liquidity reason | Spread duration |
| [[Liquidity risk]] | Harder to trade | Wider liquidity premium |
| [[Credit spread risk]] | Required credit spread changes | Price changes through spread duration |

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Treat migration risk as default risk | Migration can hurt price without default | Downgrade widens spreads |
| Ignore duration | Spread changes affect price through duration | Use $-\text{Duration}\times\Delta s$ |
| Use today's duration when the vignette gives horizon duration | Migration impact is measured over the stated horizon | Use the duration specified for the end of the period |
| Use bps directly | 100 bps is not 100 | 100 bps = 0.0100 |
| Assume upgrades and downgrades offset symmetrically | Downgrades often widen spreads more than upgrades tighten them | Probability-weight each spread impact |
| Forget no-default assumption | Some migration questions exclude default | Use transition probabilities specified |
| Think ratings are cardinal | Ratings are ordinal | Need transition matrix/spreads to quantify |
| Ignore fallen-angel effects | Mandates can force selling | Downgrade can create technical spread pressure |
| Add migration adjustment to YTM when it is negative | Migration often reduces expected return | Expected return = YTM + expected price impact |

## Memory Hooks

```text
Default risk: did they pay?
Migration risk: did their credit grade move?
```

```text
Downgrade widens spread; wider spread lowers price.
```

```text
Migration risk is spread risk before default.
```

## Exam-Day Checklist

When a migration-risk question appears, ask:

1. Is the question about default or rating migration with no default?
2. Is there a transition matrix?
3. What spread applies to each possible rating?
4. What is the spread change from the current rating?
5. What duration should be used?
6. Do I need a probability-weighted migration adjustment?
7. Is expected return equal to YTM plus or minus the migration impact?

Then use:

| Task | Formula |
|---|---|
| Price impact from migration | $\%\Delta P\approx-D\times\Delta s$ |
| Expected migration impact | $\sum P_i(-D\times\Delta s_i)$ |
| Expected return | $\text{YTM}+\text{Expected migration impact}$ |

## Related Concepts

- [[Downgrade risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]]
- [[Transition matrix]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
- [[Spread risk]]
- [[Credit spread risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Default risk]]
- [[Fallen angels]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
