---
title: Spread Duration
subject: Fixed Income
tags: [CFA-L2, fixed-income, spread-duration, credit-spread-risk, credit-risk, portfolio-risk, bonds]
aliases: [spread duration, credit spread duration, spread DV01, CS01, credit spread sensitivity]
---

# Spread Duration

## The Real-World Analogy

A risky bond's yield has two big pieces:

```text
benchmark interest rate + credit spread
```

The benchmark rate is the market's compensation for time value and risk-free rate movements.

The credit spread is extra compensation for bearing issuer-specific risks like default risk, downgrade risk, and liquidity risk.

So if you own a corporate bond, you have two different sources of yield risk:

| Risk Driver | Question |
|---|---|
| Benchmark rates | What if Treasury/swap rates move? |
| Credit spreads | What if investors demand more or less compensation for this issuer's credit risk? |

[[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] and [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] focus on benchmark yield curve risk.

[[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] focuses on credit spread risk.

## Plain-English Definition

Spread duration measures how sensitive a bond or portfolio's price is to a change in credit spreads, holding benchmark interest rates constant.

In practical language:

```text
If the issuer's spread widens by 1%,
about how much does the bond price fall?
```

If a bond has a spread duration of 6.0, then a 100 bps widening in its credit spread should reduce its price by roughly 6%, before convexity and other changes.

## CFA Definition

The glossary definition is concise:

```text
A measure used in determining a portfolio's sensitivity to changes in credit spreads.
```

The key CFA idea is separation:

```text
Spread duration isolates spread risk,
while effective/key rate duration isolates benchmark rate risk.
```

## The Core Formula Logic

The approximate price impact is:

$$
\%\Delta P \approx -\text{Spread Duration}\times \Delta \text{Spread}
$$

Where $\Delta \text{Spread}$ is expressed as a decimal.

So:

$$
50\text{ bps}=0.50\%=0.0050
$$

If spreads widen:

```text
Delta spread is positive -> price change is negative.
```

If spreads tighten:

```text
Delta spread is negative -> price change is positive.
```

## Worked Example

Suppose a corporate bond has:

| Input | Value |
|---|---:|
| Market value | $10,000,000 |
| Spread duration | 5.25 |
| Spread change | +40 bps |

Convert the spread change:

$$
40\text{ bps}=0.0040
$$

Estimate percentage price change:

$$
\%\Delta P
\approx
-5.25(0.0040)
=-0.0210
=-2.10\%
$$

Estimate dollar price change:

$$
\Delta P
\approx
-2.10\%\times \$10{,}000{,}000
=-\$210{,}000
$$

Interpretation:

```text
A 40 bps spread widening costs about $210,000.
```

## CS01 / Spread DV01

Spread duration is often converted into the dollar impact of a 1 bp spread change.

This is commonly called [[CS01]] or spread DV01:

$$
\text{CS01}
=
\text{Market Value}\times \text{Spread Duration}\times 0.0001
$$

Using the same bond:

$$
\text{CS01}
=
\$10{,}000{,}000\times 5.25 \times 0.0001
=\$5{,}250
$$

So each 1 bp widening in the credit spread costs approximately $5,250.

A 40 bp widening:

$$
40\times \$5{,}250=\$210{,}000
$$

Same answer, just expressed in basis-point units.

## Why Spread Duration Exists

For a default-free government bond, most of the yield movement is benchmark rate movement.

For a corporate bond, emerging market bond, securitized credit instrument, or risky sovereign, yield changes can come from:

```text
benchmark rate changes + spread changes
```

If you only look at duration, you may miss the credit story.

Example:

```text
Treasury rates unchanged.
Issuer credit spreads widen by 150 bps.
Corporate bond price falls.
```

Effective duration would not explain that loss because the benchmark curve did not move.

Spread duration explains it.

## Spread Duration vs Effective Duration vs Key Rate Duration

| Measure | Risk Factor Moved | What Is Held Constant? | Best Question |
|---|---|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] | Entire benchmark curve | Spread/OAS | What if rates move in parallel? |
| [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] | One benchmark maturity | Other benchmark rates and spread | What if one part of the curve moves? |
| [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] | Credit spread | Benchmark curve | What if credit spreads widen or tighten? |

Exam shortcut:

```text
Rates move -> duration.
Curve shape moves -> key rate duration.
Credit spreads move -> spread duration.
```

For a plain fixed-rate corporate bond with no embedded option, spread duration and effective duration may be numerically similar because both are discount-rate sensitivities.

But conceptually they are not the same:

```text
Effective duration asks what happens when benchmark rates move.
Spread duration asks what happens when the credit spread moves.
```

For a default-risk-free government bond in its own currency, credit spread duration is effectively zero because there is no meaningful credit spread to shock.

## Connection to Z-Spread and OAS

For an option-free risky bond, spread risk is often discussed using spreads such as [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]].

For a risky bond with embedded options, the relevant spread measure may be [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]].

The same intuition applies:

```text
If the required spread goes up,
the discount rates used to value risky cash flows go up,
so the bond price falls.
```

For option-embedded bonds, the valuation model may need to revalue cash flows and option exercise behavior as spreads change.

## Why Risky Bonds Have Spread Duration

Credit spreads compensate investors for risks such as:

| Risk | Why It Raises Spread |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Higher chance the issuer fails to pay |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Lower expected recovery if default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] | Downgrade risk can reduce market price |
| Liquidity risk | Investors demand compensation for harder-to-trade bonds |
| Business cycle risk | Credit losses rise in weak economies |

When investors demand more compensation for these risks, spreads widen.

When spreads widen, risky bonds fall in price.

Spread duration measures how much.

## Business Cycle Implications

Credit spreads are cyclical.

| Environment | Typical Spread Behavior | Bond Price Effect |
|---|---|---|
| Expansion, improving credit quality | Spreads tighten | Risky bonds outperform |
| Recession, rising default concerns | Spreads widen | Risky bonds underperform |
| Flight to quality | Lower-quality spreads widen more | High yield suffers more than high grade |

So two bonds with similar benchmark duration can perform very differently in a recession if one has much larger spread duration and lower credit quality.

## Portfolio Implications

A portfolio manager needs to know:

```text
How much money do I lose if spreads widen?
Which issuers, sectors, or ratings drive that exposure?
Can I hedge the spread risk without removing all interest rate exposure?
```

Spread duration can be aggregated across holdings:

| Portfolio Segment | Market Value | Spread Duration | Approx. CS01 |
|---|---:|---:|---:|
| Investment grade financials | $50m | 6.0 | $30,000 |
| High yield industrials | $20m | 3.5 | $7,000 |
| EM sovereigns | $30m | 7.0 | $21,000 |

This lets the manager identify where spread widening would hurt most in dollar terms.

For portfolios with long and short credit positions, the manager cares about net spread duration.

Example:

```text
Long corporate bonds: positive spread duration.
Bought CDS protection: offsetting negative spread exposure.
Net spread duration: the actual remaining credit spread risk.
```

## Hedging Implications

Spread risk can be hedged or adjusted using:

| Tool | Logic |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] protection | Gains when credit risk/spreads widen |
| Corporate bond sales | Reduce direct spread exposure |
| Index CDS | Hedge broad spread widening |
| Rating/sector rotation | Reduce exposure to spread-sensitive sectors |
| Treasury futures plus credit instruments | Separate rate exposure from spread exposure |

Important distinction:

```text
Shorting Treasury futures hedges rate duration.
It does not directly hedge credit spread widening.
```

To hedge spread risk, you need an instrument tied to credit spreads.

## Spread Duration and Credit Migration

If a bond is downgraded, its required spread often widens.

The approximate price effect is:

$$
\%\Delta P \approx -\text{Spread Duration}\times \Delta \text{Spread}
$$

Example:

```text
Spread duration = 7.2
Spread widens by 90 bps after a downgrade
Estimated price change = -7.2 x 0.0090 = -6.48%
```

This is why downgrade risk matters even if the issuer does not default.

The bond can lose value because the market reprices its spread.

## Limitations

Spread duration is useful, but it is not a complete risk measure.

| Limitation | Why It Matters |
|---|---|
| Linear approximation | Less accurate for large spread moves |
| Spread curve shape | Different maturities may widen by different amounts |
| Liquidity shocks | Market prices can move more than model spreads imply |
| Default jump risk | Spread duration does not fully capture sudden default losses |
| Correlation with rates | In crises, spreads and rates may move together |
| Embedded options | Spread changes can interact with option value and exercise behavior |

For severe credit scenarios, use full revaluation or stress testing rather than relying only on spread duration.

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Use effective duration for spread widening | Effective duration measures benchmark rate sensitivity | Use spread duration |
| Forget the negative sign | Wider spreads mean lower prices | $\%\Delta P \approx -SD\times\Delta s$ |
| Use bps directly | 75 bps is not 75 | 75 bps = 0.0075 |
| Think Treasury futures hedge credit spread risk | Treasury futures hedge rates | Use credit instruments for spread exposure |
| Ignore market value | Portfolio dollar loss depends on size | Use CS01 for dollar exposure |
| Treat all spread moves as parallel | Credit curves can steepen or flatten | Segment spread exposure by maturity/issuer/sector |
| Confuse OAS level with spread duration | OAS is a spread; spread duration is sensitivity to spread changes | One is a level, one is a risk measure |
| Assume sensitivity equals loss potential | High-yield spreads can move more violently than IG spreads | Combine sensitivity with volatility/stress analysis |
| Assign credit spread duration to default-free government bonds | They do not have meaningful credit spread risk in their own currency | Spread duration is effectively zero |
| Ignore short credit hedges | Long and short spread exposures can offset | Use net spread duration |

## Memory Hooks

```text
Spread duration is duration for credit spreads.
```

```text
Rates up hurts duration.
Spreads wider hurts spread duration.
```

```text
CS01 = dollar pain per 1 bp of spread widening.
```

```text
Treasury hedge fixes rate risk, not credit spread risk.
```

## Exam Decision Checklist

When a question mentions spread risk, ask:

1. Are benchmark rates moving, or are credit spreads moving?
2. Is the spread change expressed in bps or decimal form?
3. Is the question asking for percentage price impact or dollar impact?
4. Do I need spread duration or CS01?
5. Is the spread move issuer-specific, sector-wide, or market-wide?
6. Is this a normal sensitivity question or a severe stress/default scenario?

Then choose:

| Situation | Tool |
|---|---|
| Benchmark rates move in parallel | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
| Specific benchmark maturity moves | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
| Credit spreads move | [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] |
| 1 bp spread dollar impact | [[CS01]] |
| Extreme spread/default scenario | Full revaluation or stress test |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]]
- [[Credit spread risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[CS01]]
