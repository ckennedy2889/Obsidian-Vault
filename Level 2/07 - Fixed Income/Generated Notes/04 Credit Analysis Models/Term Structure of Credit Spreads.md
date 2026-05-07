---
title: Term Structure of Credit Spreads
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-spreads, credit-curve, spread-curve, cds, credit-risk]
aliases: [term structure of credit spreads, credit curve, spread curve, credit spread term structure, credit spread curve]
---

# Term Structure of Credit Spreads

## The Real-World Analogy

Imagine lending to the same company for 1 year, 5 years, and 10 years.

You would not demand the same extra compensation at every maturity if the company's risk changes over time.

If the company looks safe this year but uncertain over the next decade, you might demand:

```text
small 1-year spread
larger 5-year spread
even larger 10-year spread
```

That creates an upward-sloping credit curve.

If the company is in immediate distress but might survive after a restructuring, you might demand:

```text
huge 1-year spread
lower 5-year spread
lower 10-year spread
```

That creates a downward-sloping or inverted credit curve.

The term structure of credit spreads is the market's timeline of credit fear.

## Plain-English Definition

The [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]] shows how a borrower's credit spreads vary across maturities.

It answers:

```text
How much extra yield do investors demand
for lending to this borrower at different time horizons?
```

A closely related term is [[Credit curve]].

For a company, the credit curve is the set of credit spreads on that company's debt across maturities.

## CFA Definition

The glossary definition:

```text
The relationship between spreads over risk-free or benchmark rates and times to maturity.
```

For Level II, the credit curve applies to non-government borrowers and incorporates credit risk into each maturity's spread.

## Credit Spread Refresher

A credit spread is the yield premium over a benchmark rate:

$$
\text{Credit Spread}
=
\text{Risky Bond Yield}
-
\text{Benchmark Yield}
$$

The spread compensates investors for risks such as:

| Risk | Why It Affects Spread |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] | Greater chance promised payments are missed |
| [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] | Lower recovery if default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] | Downgrade risk can reduce price |
| Liquidity risk | Harder-to-trade bonds require compensation |
| Business cycle risk | Defaults rise in weak economies |
| Supply/demand | Heavy issuance or scarce demand can widen spreads |

The rough credit-risk relationship is:

$$
\text{Credit Spread} \approx \text{Probability of Default}\times \text{Loss Given Default}
$$

More precisely, the spread reflects expected losses, risk premia, liquidity, taxes, and market technicals.

But for CFA intuition:

```text
Higher default probability or higher loss severity -> wider credit spread.
```

## Hazard Rate Link

The [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] is the conditional probability of default in a period, given that default has not already occurred.

That conditional wording matters.

If a company has a 3% hazard rate in Year 2, that means:

```text
Probability of defaulting in Year 2,
conditional on surviving Year 1.
```

Credit curve shape is heavily influenced by the term structure of hazard rates.

| Hazard Rate Pattern | Credit Curve Implication |
|---|---|
| Rising hazard rates over time | Upward-sloping credit curve |
| Roughly constant hazard rates | Flatter credit curve |
| High near-term hazard rates | Downward-sloping / inverted credit curve |

The curriculum nuance:

```text
A constant hazard rate tends to flatten the credit curve,
but discounting can keep it from being perfectly flat.
```

## Common Credit Curve Shapes

| Shape | What It Looks Like | Interpretation |
|---|---|---|
| Upward sloping | Long spreads > short spreads | More concern about longer-term default risk |
| Flat | Similar spreads across maturities | Similar credit risk compensation across horizons |
| Downward sloping / inverted | Short spreads > long spreads | Severe near-term stress or high near-term default risk |
| Steepening | Long spreads widen relative to short spreads | Long-term credit outlook worsens relative to near-term |
| Flattening | Short spreads widen or long spreads tighten relative to the other | Near-term risk rises relative to long-term risk, or long-term outlook improves |

## Upward-Sloping Credit Curve

An upward-sloping credit curve is common for investment-grade issuers.

Why?

```text
The further into the future we lend,
the more time there is for leverage, competition, regulation, or macro conditions to deteriorate.
```

So investors often require more spread for longer maturities.

Example:

| Maturity | Credit Spread |
|---|---:|
| 1-year | 45 bps |
| 5-year | 95 bps |
| 10-year | 145 bps |

Interpretation:

```text
The market sees more credit uncertainty over longer horizons.
```

## Downward-Sloping Credit Curve

A downward-sloping credit curve is less common and often signals severe near-term stress.

Example:

| Maturity | Credit Spread |
|---|---:|
| 1-year | 1,700 bps |
| 5-year | 900 bps |
| 10-year | 660 bps |

Interpretation:

```text
The market is worried about near-term default.
If the firm survives the next year or two,
its longer-term outlook may be less bad.
```

This can happen for distressed issuers.

When default is very likely soon, bonds across maturities may trade closer to expected recovery value, and the credit curve can become less informative.

This is the distressed-debt trap:

```text
The bond may be priced more like a claim on recovery value
than like a normal yield-to-maturity instrument.
```

In that situation, quoted spreads can look extreme or oddly shaped because the market is focused on recovery and timing of default.

## Business Cycle Interpretation

Credit spread curves move with the business cycle.

| Environment | Spread Level | Curve Shape Tendency | Intuition |
|---|---|---|---|
| Strong economy | Spreads narrow | Curve may flatten | Default risk is lower and investors are comfortable taking credit risk |
| Weak economy | Spreads widen | Curve may steepen for many issuers | Longer-term credit uncertainty rises |
| Severe near-term stress | Short spreads spike | Curve may invert | Market fears imminent default |
| Improving issuer balance sheet | Spreads tighten | Curve may flatten | Leverage and long-term risk decline |

The exam will often ask you to infer the market's view from the curve shape.

## Relationship to CDS

The CDS market is closely tied to the credit curve.

A [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] spread is the cost of buying credit protection for a given maturity.

So the CDS curve is often used to infer the issuer's credit curve:

```text
2-year CDS spread
5-year CDS spread
10-year CDS spread
```

In practice, CDS spreads can strongly influence the observed credit curve because CDS markets are often liquid and directly trade credit risk.

The bond market and CDS market do not always imply the exact same spread.

The difference is called the [[CDS-bond basis]]:

```text
Basis = CDS spread - bond spread
```

Basis trades try to exploit the difference between credit risk priced in bonds and credit risk priced in CDS.

## CDS Curve Trades

Investors can express views on the shape of the credit curve using CDS.

### Steepening View

If an investor expects the credit curve to steepen:

```text
Long-term credit risk will rise relative to short-term credit risk.
```

A common trade:

| Leg | Action | Why |
|---|---|---|
| Long-term CDS | Buy protection | Benefits if long-term spreads widen |
| Short-term CDS | Sell protection | Offsets cost and expresses relative view |

This is effectively bearish on long-term credit risk relative to short-term credit risk.

### Flattening View

If an investor expects the credit curve to flatten because near-term stress will rise:

```text
Short-term spreads will widen relative to long-term spreads.
```

A common trade:

| Leg | Action | Why |
|---|---|---|
| Short-term CDS | Buy protection | Benefits if short-term spreads widen |
| Long-term CDS | Sell protection | Offsets cost and expresses relative view |

This is common when the investor believes the issuer faces near-term problems.

## Bond Portfolio Implications

Credit curve shape affects bond selection.

| View | Possible Positioning |
|---|---|
| Spreads will tighten broadly | Increase credit exposure / spread duration |
| Spreads will widen broadly | Reduce credit exposure / buy CDS protection |
| Curve will steepen | Favor shorter credit exposure or buy long-term protection |
| Curve will flatten from short-end stress | Reduce short-maturity risky exposure or buy short-term protection |
| Issuer's long-term outlook improves | Longer bonds may outperform if long spreads tighten |

This connects directly to [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]].

Longer credit instruments often have more spread duration, so their prices are more sensitive to spread moves.

## Worked Example: Interpreting a Steepening

Suppose a company's credit spreads change as follows:

| Maturity | Old Spread | New Spread | Change |
|---|---:|---:|---:|
| 2-year | 90 bps | 90 bps | 0 bps |
| 10-year | 150 bps | 250 bps | +100 bps |

The curve steepened.

Interpretation:

```text
The market is not more worried about near-term default,
but it is much more worried about long-term credit risk.
```

Likely implication:

```text
Longer-maturity bonds underperform shorter-maturity bonds.
Long-term CDS protection becomes more valuable.
```

## Worked Example: Interpreting a Flattening/Inversion

Suppose:

| Maturity | Old Spread | New Spread | Change |
|---|---:|---:|---:|
| 2-year | 150 bps | 650 bps | +500 bps |
| 10-year | 300 bps | 300 bps | 0 bps |

The curve flattened or moved toward inversion because the short end widened sharply.

Interpretation:

```text
The market sees severe near-term stress.
```

This is not a normal "longer maturity = more risk" situation.

It is a "can this company survive the next few years?" situation.

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Treat the credit curve like the Treasury yield curve | It is about credit compensation, not default-free rates | Interpret default/liquidity/risk premium across maturities |
| Assume upward sloping always means near-term trouble | Upward sloping often means long-term uncertainty is greater | Near-term trouble often creates inversion |
| Assume flat curve means zero credit risk | Flat means similar spread compensation across maturities | Spread level can still be high |
| Forget the hazard rate is conditional | It is default probability given survival so far | Do not treat it as unconditional default probability |
| Think constant hazard rate guarantees perfectly flat spreads | Discounting and pricing mechanics can prevent a perfectly flat curve | Constant hazard tends to flatten |
| Confuse spread widening with spread tightening | Wider spreads lower risky bond prices | Tighter spreads raise risky bond prices |
| Choose the wrong CDS leg | Buying protection benefits from spread widening | Sell protection benefits from spread tightening |
| Ignore maturity | Long-term CDS/bonds usually react more to long-end spread changes | Match the trade to the curve view |
| Ignore CDS-bond basis | Bonds and CDS can imply different credit spreads | Basis is the difference between CDS and bond spread |
| Treat distressed spreads as clean signals | Distressed bonds may trade near recovery value | Be cautious interpreting YTM-based spreads |
| Ignore benchmark selection | Spreads depend on the reference curve | Government, swap, or other benchmarks can change the measured spread |
| Confuse actual and risk-neutral default probabilities | Market spreads include risk premia | Risk-neutral PODs are often higher than historical PODs |

## Memory Hooks

```text
Credit curve = market's timeline of credit fear.
```

```text
Upward slope: later risk.
Inverted curve: near-term stress.
Flat curve: similar compensation across time.
```

```text
Buy CDS protection when you want to benefit from widening spreads.
Sell CDS protection when you want to benefit from tightening spreads.
```

## Exam Decision Checklist

When a question gives credit spreads by maturity, ask:

1. Are short spreads or long spreads higher?
2. Did the level of the curve change, or did the shape change?
3. Is the issuer investment grade, high yield, or distressed?
4. Is the question about bonds or CDS?
5. Would the investor profit from spread widening or tightening?
6. Is the view about near-term risk or long-term risk?
7. Which maturity should the hedge or trade target?

Then choose:

| Situation | Interpretation / Action |
|---|---|
| Long spreads > short spreads | Upward-sloping curve; more long-term credit uncertainty |
| Short spreads > long spreads | Inverted curve; severe near-term stress |
| All spreads widen | Credit quality/risk appetite worsens |
| All spreads tighten | Credit quality/risk appetite improves |
| Long spreads widen more | Curve steepens; long-term risk increases |
| Short spreads widen more | Curve flattens/inverts; near-term risk increases |

## Related Concepts

- [[Credit curve]]
- [[Spread curve]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS-bond basis]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- [[Credit spread risk]]
- [[Term structure]]
- [[Business cycle]]
