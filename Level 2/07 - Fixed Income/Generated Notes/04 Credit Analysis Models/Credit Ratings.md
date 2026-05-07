---
title: Credit Ratings
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-analysis, credit-ratings, credit-migration]
aliases: [credit rating, ratings, bond ratings, issuer rating, issue rating, rating migration]
---

# Credit Ratings

## The Real-World Analogy

A credit rating is like a lender saying:

> "This borrower belongs in this risk bucket."

It is not the same as saying:

> "This borrower has exactly a 1.37% probability of default next year."

Think about restaurant health grades.

An A-rated restaurant is safer than a C-rated restaurant, but the grade itself does not tell you the exact probability that a customer gets sick.

Likewise, a AAA bond is safer than a BB bond, but the rating itself is an ordinal rank, not a precise probability.

```text
AAA > AA > A > BBB > BB > B > CCC

Higher rating = lower credit risk
Lower rating = higher credit risk
```

The rating gives the order.

Default data, transition matrices, spreads, and credit models give the numbers.

## The Big Idea

[[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]] are ordinal rankings of the credit risk of an issuer or a specific debt issue.

Ordinal means the ratings create an order:

$$
AAA \text{ is better than } AA
$$

and:

$$
AA \text{ is better than } A
$$

But ordinal does not mean cardinal.

Cardinal would mean the rating scale has exact numerical distances.

That is not true.

An A-rated bond is not "twice as risky" as an AA-rated bond just because it is one broad category lower.

A BBB bond is not exactly one unit riskier than an A bond in a way that lets you do arithmetic directly on the letters.

The rating is a rank.

The numerical default probability must come from default history, market prices, spreads, transition matrices, or credit models.

## Why CFA Tests This

CFA tests ratings because they sit between qualitative credit analysis and quantitative bond valuation.

Ratings affect:

- required [[Credit spread]]
- portfolio eligibility
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- expected return adjustments
- [[Fallen angels]]
- issue-specific notching
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- market segmentation

Ratings also create a very common exam trap:

> Ratings are ordinal rankings, not exact default probabilities.

If a vignette gives you ratings and asks for numerical expected return or default risk, you usually need more data:

- default probability table
- [[Transition matrix]]
- credit spread by rating
- recovery assumptions
- duration
- market-implied spread data

The letter grade alone is not enough for precise math.

## Who Assigns Credit Ratings

The three major global credit rating agencies are:

| Agency | Common name |
|---|---|
| Moody's Investors Service | Moody's |
| Standard & Poor's | S&P |
| Fitch Ratings | Fitch |

They assign ratings to:

- corporations
- sovereign governments
- quasi-government issuers
- structured products
- asset-backed securities
- specific bond issues

Ratings are used primarily in wholesale bond markets, not retail consumer lending.

## Credit Scores Versus Credit Ratings

The local source notes make this distinction explicit.

| Feature | [[Credit scores]] | [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]] |
|---|---|---|
| Primary market | Retail lending | Wholesale bond markets |
| Typical borrowers | Individuals and small businesses | Corporations, sovereigns, ABS issuers |
| Format | Numerical score | Letter grade |
| Examples | FICO-style consumer scores | AAA, AA, A, BBB, BB |
| Used by | Consumer lenders, credit-card issuers, mortgage lenders | Bond investors, rating agencies, portfolio managers |
| Meaning | Ordinal creditworthiness rank | Ordinal credit-risk rank |

Both are ordinal.

Neither is automatically cardinal.

Exam trap:

A credit score of 750 is not "twice as creditworthy" as 375.

Likewise, an A rating does not mean "half the default risk" of BBB.

## Typical Rating Scale

The broad S&P/Fitch-style scale is:

| Rating bucket | General interpretation |
|---|---|
| AAA | Highest credit quality |
| AA | Very high credit quality |
| A | Strong credit quality |
| BBB | Adequate credit quality; lowest broad investment-grade bucket |
| BB | Speculative; highest broad high-yield bucket |
| B | More speculative |
| CCC/C/C | Very high default risk |
| D | Default |

Moody's uses a different naming convention, such as Aaa, Aa, A, Baa, Ba, B, and Caa.

The economic idea is the same:

```text
Higher rating
   -> lower expected default risk
   -> lower required spread
   -> higher bond price, all else equal
```

and:

```text
Lower rating
   -> higher expected default risk
   -> higher required spread
   -> lower bond price, all else equal
```

## Investment Grade Versus High Yield

A major dividing line is investment grade versus high yield.

| Category | S&P/Fitch-style ratings | Moody's-style ratings | Common implication |
|---|---|---|---|
| Investment grade | BBB- and above | Baa3 and above | Many institutional mandates allow |
| High yield / speculative grade | BB+ and below | Ba1 and below | Higher spreads, more restrictions |

This boundary matters because many portfolios are restricted from holding high-yield bonds.

If a bond is downgraded from investment grade to high yield, it becomes a [[Fallen angels|fallen angel]].

That downgrade can trigger forced or mandate-driven selling.

The price impact can be larger than the change in default probability alone would suggest because market segmentation and selling pressure also matter.

```text
Investment grade bond downgraded to high yield
        |
        v
Some investors forced to sell
        |
        v
Extra price pressure
        |
        v
Yield may become unusually attractive
```

## Issuer Ratings Versus Issue Ratings

A rating can apply to the issuer or to a specific debt issue.

| Rating type | What it evaluates |
|---|---|
| Issuer rating | Overall creditworthiness of the borrower |
| Issue rating | Credit risk of a specific bond or debt instrument |

Why can issue ratings differ from issuer ratings?

Because different debt issues can have different recovery prospects.

A senior secured bond and a subordinated unsecured bond from the same issuer do not have the same priority.

If the issuer defaults:

```text
Senior secured debt
   paid before
Senior unsecured debt
   paid before
Subordinated debt
   paid before
Equity
```

Rating agencies use notching to adjust issue ratings for priority, collateral, subordination, and expected recovery.

This is why CFA notes say they are called credit ratings, not merely default ratings.

The rating can reflect not only [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] but also expected [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]].

## Ratings, POD, and Expected Loss

Ratings focus on credit risk.

Default probability is a major component, but issue ratings can also reflect expected loss severity.

The expected-loss framework is:

$$
EL = POD \times LGD \times \text{Exposure}
$$

where:

| Term | Meaning |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Likelihood the issuer defaults |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Percentage loss if default occurs |
| Exposure | Amount at risk |

Two bonds from the same issuer may have the same issuer default probability but different issue ratings because recovery differs.

Example:

| Bond | Priority | POD | Recovery | LGD | Issue rating intuition |
|---|---|---:|---:|---:|---|
| Senior secured | First claim, collateral | Same issuer POD | High | Low | Higher issue rating |
| Subordinated unsecured | Lower claim | Same issuer POD | Low | High | Lower issue rating |

Exam implication:

If the question distinguishes issuer rating and issue rating, look for priority, collateral, and subordination.

## Rating Outlooks and Watch Lists

Rating agencies may also provide:

| Signal | Meaning |
|---|---|
| Positive outlook | Rating may improve over time |
| Stable outlook | Rating expected to remain broadly unchanged |
| Negative outlook | Rating may deteriorate |
| Positive watch | Upgrade may be more imminent |
| Negative watch | Downgrade may be more imminent |

These are not the same as a rating change.

They are warnings about possible future migration.

Exam trap:

If an analyst believes an issuer is undervalued because her default probability and recovery assumptions are more optimistic than the agencies' assumptions, the likely rating-agency action may be positive watch or upgrade direction, not downgrade.

Rating changes are usually incremental, not dramatic jumps from BBB to AAA.

## Rating Migration

Ratings change over time.

A company can move:

- from A to BBB
- from BBB to BB
- from BB to B
- from BBB to A
- from CCC to default

That movement is [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]].

The bond does not need to default for rating migration to matter.

A downgrade can hurt price because the required spread widens.

```text
Downgrade
   -> higher perceived credit risk
   -> wider required spread
   -> lower bond price
```

An upgrade can help price because the required spread narrows.

```text
Upgrade
   -> lower perceived credit risk
   -> tighter required spread
   -> higher bond price
```

## Transition Matrix

A [[Transition matrix]] shows probabilities of moving from one rating to another over a period, often one year.

Example structure:

| From / To | AAA | AA | A | BBB | BB | B | CCC | D |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| AA | 1.50% | 88.00% | 9.50% | 0.75% | 0.15% | 0.05% | 0.03% | 0.02% |

Read across the row.

If the bond starts AA:

- 1.50% probability of upgrade to AAA
- 88.00% probability of staying AA
- 9.50% probability of downgrade to A
- and so on

The row probabilities should sum to approximately 100%.

The diagonal entries show the probability that the rating stays the same.

In most transition matrices, the diagonal is usually large because ratings tend to be sticky over short horizons.

```text
From AA to AA = stay AA
From A to A   = stay A
From BBB to BBB = stay BBB
```

Exam use:

The transition matrix lets you probability-weight the price impact of rating changes.

## Rating Migration and Expected Return

The standard price-change approximation:

$$
\Delta P \approx -D_{\text{mod}} \times \Delta \text{Spread}
$$

where:

| Term | Meaning |
|---|---|
| $D_{\text{mod}}$ | Modified duration |
| $\Delta \text{Spread}$ | New spread after migration minus current spread |

If spread widens, $\Delta \text{Spread} > 0$, so price change is negative.

If spread tightens, $\Delta \text{Spread} < 0$, so price change is positive.

Workflow:

1. Start with the current rating.
2. Use the transition matrix row for that rating.
3. For each possible rating outcome, find the new spread.
4. Compute $\Delta \text{Spread}$.
5. Compute price impact using duration.
6. Multiply each price impact by transition probability.
7. Sum the weighted effects.
8. Adjust expected return.

## Worked Numerical Example: Rating Migration

Suppose a bond is rated AA.

| Input | Value |
|---|---:|
| Modified duration at horizon | 2.75 |
| Current AA spread | 0.90% |

Partial transition outcomes:

| Transition | New spread | Spread change | Probability |
|---|---:|---:|---:|
| AA to AAA | 0.60% | -0.30% | 1.50% |
| AA to AA | 0.90% | 0.00% | 88.00% |
| AA to A | 1.10% | +0.20% | 9.50% |
| AA to BBB | 1.50% | +0.60% | 0.75% |

Price impact for AA to AAA:

$$
\Delta P \approx -2.75(-0.0030)
$$

$$
= +0.00825 = +0.825\%
$$

Weighted impact:

$$
0.0150 \times 0.825\% = 0.0124\%
$$

Price impact for AA to A:

$$
\Delta P \approx -2.75(0.0020)
$$

$$
= -0.0055 = -0.55\%
$$

Weighted impact:

$$
0.0950 \times (-0.55\%) = -0.0523\%
$$

Price impact for AA to BBB:

$$
\Delta P \approx -2.75(0.0060)
$$

$$
= -0.0165 = -1.65\%
$$

Weighted impact:

$$
0.0075 \times (-1.65\%) = -0.0124\%
$$

Even in this partial table, the downgrade outcomes more than offset the upgrade benefit.

That is the key CFA intuition:

> Credit spread migration often reduces expected return because downgrades tend to be more likely and more damaging than upgrades are beneficial.

## Why Downgrades Often Hurt More Than Upgrades Help

There are two reasons.

First, transition probabilities are often skewed toward downgrade rather than upgrade.

Second, spread widening from downgrades can be much larger than spread tightening from upgrades.

```text
Upgrade:
   spread tightens a little
   price rises a little

Downgrade:
   spread widens a lot
   price falls a lot
```

This asymmetry is especially important for lower-quality bonds.

It is also why high-quality bonds with already tiny spreads may have limited spread-tightening upside.

Credit spreads cannot go far below zero, so the upside from further rating improvement can be capped, while downgrade risk remains.

## Ratings and Credit Spreads

All else equal:

| Rating direction | Spread effect | Price effect |
|---|---|---|
| Upgrade | Spread tightens | Price rises |
| Downgrade | Spread widens | Price falls |

But the rating itself is not the spread.

Market spreads can change before ratings change because investors update faster than rating committees.

A bond can trade like a weaker credit before it is officially downgraded.

This matters because ratings can be sticky.

They may stay unchanged for a long time and then adjust after deterioration has already become obvious in the market.

## Ratings and Credit Models

Ratings are not a substitute for credit modeling.

They can be used alongside:

- [[Level 2/Generated Notes/07 - Fixed Income/Structural Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Credit Valuation Adjustment]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]

Structural models may estimate default probability from asset values, volatility, and debt barriers.

Reduced-form models may estimate default intensity from observable variables.

Ratings summarize credit quality, but they do not show every assumption underneath.

## Fallen Angels

A [[Fallen angels|fallen angel]] is a bond downgraded from investment grade to high yield.

This matters because many institutional investors are restricted to investment-grade holdings.

When the downgrade happens:

```text
Bond crosses IG/HY boundary
        |
        v
Mandate-restricted investors sell
        |
        v
Price pressure
        |
        v
Yield may become elevated
```

This is not purely a default-risk story.

It is also a market-segmentation story.

Exam trap:

If fallen angel yields look unusually high relative to otherwise similar bonds, the answer may involve forced selling or market segmentation, not just higher expected default loss.

## Limitations of Credit Ratings

Ratings are useful, but they are not perfect.

| Limitation | Why it matters |
|---|---|
| Ordinal, not cardinal | Cannot do exact risk arithmetic from letters alone |
| May lag markets | Spreads may move before ratings |
| Can be sticky | Ratings may remain unchanged through gradual deterioration |
| Agency methodology may differ | Ratings may not fully match your assumptions |
| Issue ratings require recovery judgment | Priority and collateral matter |
| Not enough for expected return | Need spreads, duration, transition probabilities, and default assumptions |
| Issuer-pay model can create conflicts | Agencies may face incentives that affect rating quality |

The correct attitude:

> Use ratings as a structured credit-quality input, not as a full valuation model.

### Ratings Can Lag Market Signals

NotebookLM emphasized that market prices can detect credit deterioration faster than formal ratings.

Equity prices, CDS spreads, and bond spreads may move before the rating agency acts.

```text
Operating weakness appears
   |
   v
Equity falls / CDS widens / bond spread widens
   |
   v
Rating agency later downgrades or puts issuer on watch
```

Exam implication:

Do not assume the current rating fully captures all current market information.

If the vignette says spreads have widened sharply but the rating is unchanged, that can mean the market is pricing a downgrade or higher default risk before the agency has formally moved.

## Mini Vignette Scenarios

### Scenario 1: Same Issuer, Different Bond Ratings

A company has senior secured debt and subordinated unsecured debt.

The issuer default probability is the same for both issues.

But recovery is different.

The subordinated issue may be notched lower.

Exam implication:

Do not assume all bonds from the same issuer have the same issue rating.

### Scenario 2: BBB Bond Put on Negative Watch

A BBB issuer has weakening profitability and rising leverage.

The agency places the rating on negative watch.

Interpretation:

The rating has not changed yet, but downgrade risk has increased.

The bond's spread may widen before the downgrade officially occurs.

### Scenario 3: Analyst More Optimistic Than Agencies

An analyst believes the market and agencies overstate default probability and understate recovery.

The bond may be undervalued from the analyst's perspective.

If agencies later agree, likely direction is positive watch or upgrade, not downgrade.

### Scenario 4: Forced Selling After Downgrade

A BBB- bond is downgraded to BB+.

Many investment-grade funds must sell.

The bond price drops sharply.

The yield may become attractive because selling pressure pushed the price below fundamental value.

That is a fallen angel setup.

## Common Exam Traps

| Trap | Why it is wrong | Better exam response |
|---|---|---|
| Treat ratings as exact PODs | Ratings are ordinal | Use default data or model outputs for numerical POD |
| Think A is twice as risky as AA | Letter grades are not cardinal | They only rank relative credit quality |
| Ignore issue-specific notching | Issue priority affects expected recovery | Seniority and collateral can change issue ratings |
| Assume different bonds from the same issuer have different PODs | Default is an issuer event | Issue ratings can differ because LGD/recovery differs |
| Assume downgrade means default | Downgrade is migration, not default | Price can fall even if coupons are paid |
| Forget forced selling | Mandates can magnify fallen angel price pressure | Market segmentation matters |
| Use current duration blindly in migration examples | Vignettes may give horizon/end-of-year duration | Use the duration specified |
| Assume upgrades and downgrades are symmetric | Downgrades can be more likely and more damaging | Probability-weight each outcome |
| Treat rating outlook as rating change | Outlook/watch is a signal, not a migration event itself | Separate watch/outlook from actual rating |
| Treat credit spread as pure default compensation | Spreads can include liquidity, taxes, and risk premia | Default risk is central but not the only component |

## Exam-Day Checklist

When you see a credit-ratings question, ask:

1. Is the rating issuer-level or issue-level?
2. Is the question asking for ordinal ranking or numerical POD?
3. Do I need a transition matrix?
4. Do I need spread changes by rating?
5. Do I need duration to estimate price impact?
6. Is the bond crossing the investment-grade/high-yield boundary?
7. Is there possible forced selling or market segmentation?
8. Are priority, collateral, and subordination relevant?
9. Is the rating agency action an outlook/watch or an actual rating change?

## Memory Hooks

Credit ratings:

```text
Ratings rank.
They do not measure exact distance.
```

Migration:

```text
Downgrade widens spread.
Spread widening lowers price.
```

Fallen angel:

```text
IG to HY = forced-selling risk.
```

Issue versus issuer:

```text
Issuer = borrower.
Issue = specific bond.
```

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]]
- [[Credit scores]]
- [[Credit analysis]]
- [[Credit risk]]
- [[Default risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- [[Transition matrix]]
- [[Downgrade risk]]
- [[Fallen angels]]
- [[Credit spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Structural Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[High yield]]
- [[Investment grade]]
- [[Subordinated debt]]
- [[Senior unsecured debt]]
