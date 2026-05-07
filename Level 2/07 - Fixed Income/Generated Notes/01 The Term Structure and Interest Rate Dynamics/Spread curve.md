---
title: Spread curve
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-spreads, spread-curve, credit-risk, liquidity-risk]
aliases: [Spread curve, Credit spread curve, Credit curve, Term structure of credit spreads]
---

# Spread curve

## The Real-World Analogy

A single credit spread is like a weather reading at one hour of the day. A [[Spread curve]] is the full weather forecast across time.

It shows whether the market is more worried about near-term default risk, long-term uncertainty, or both.

```text
Credit spread by maturity
        =
market's timeline of credit concern
```

## Plain-English Definition

A spread curve, or credit spread curve, shows the relationship between credit spreads and maturity.

It can be built from:

| Curve type | What it compares |
|---|---|
| Issuer spread curve | Bonds from the same issuer across maturities |
| Sector spread curve | Bonds from similar issuers in the same rating/sector bucket |

The curve is useful only if the bonds used are comparable.

## Why CFA Tests This

CFA tests spread curves because credit risk is not always the same at every maturity.

For example:

```text
Near-term refinancing pressure
  -> short spreads may be high

Long-term business uncertainty
  -> long spreads may be high
```

The spread curve helps analysts price new issues, compare existing bonds, and interpret the market's expectations about future default probabilities and recovery rates.

## Construction Discipline

To create a meaningful spread curve, the bonds should have similar credit characteristics.

Avoid mixing bonds that differ materially in:

| Distortion | Why it matters |
|---|---|
| Seniority | Senior and subordinated debt have different recovery expectations |
| Collateral / lien status | Secured debt and unsecured debt have different risk |
| Embedded options | Callable/putable bonds include option value in quoted spreads |
| Liquidity | Less liquid bonds may show wider spreads unrelated to credit |
| Currency or tax status | Different markets can distort spread comparisons |

If these features differ, the fitted spread curve may not reflect the true term structure of credit risk.

## Shape And Interpretation

| Spread curve shape | Interpretation |
|---|---|
| Upward sloping | Longer-term credit risk or uncertainty is higher |
| Flat | Credit and recovery expectations are relatively stable across maturities |
| Downward sloping / inverted | Near-term credit stress is high, or longer bonds are relatively better supported |

Key determinants include:

| Driver | Effect |
|---|---|
| Credit quality | Higher-rated curves tend to be flat or slightly upward sloping; lower-rated curves tend to be steeper and more cyclical |
| Financial conditions | Spreads narrow in expansions and widen in downturns |
| Market demand and supply | New issue liquidity and investor demand can distort the curve |
| Equity volatility | Higher equity volatility tends to widen spreads in structural credit models |
| Expected default probabilities | Higher future default risk steepens the curve |
| Expected recovery rates | Lower expected recovery rates widen spreads |

## Worked Example

Suppose a BBB issuer has these option-free senior unsecured bonds:

| Maturity | Bond spread |
|---|---:|
| 2 years | 90 bps |
| 5 years | 135 bps |
| 10 years | 190 bps |

The spread curve is upward sloping.

Interpretation:

```text
The market demands more compensation for longer exposure to this issuer.
```

That may reflect greater uncertainty about the issuer's long-term credit quality, higher long-run default probability, lower expected recovery, or weaker long-term liquidity.

Now suppose spreads are:

| Maturity | Bond spread |
|---|---:|
| 2 years | 300 bps |
| 5 years | 220 bps |
| 10 years | 180 bps |

This spread curve is inverted.

Interpretation:

```text
The market is more worried about near-term credit stress than long-term survival.
```

This can happen when refinancing risk or a near-term downgrade/default concern dominates.

## Link To The Credit Cycle

Spread curves move with financial conditions.

| Environment | Typical spread behavior |
|---|---|
| Expansion | Spreads tend to narrow; curves may steepen because near-term default risk looks especially low |
| Downturn / recession | Spreads tend to widen; curves may flatten as near-term default risk rises |
| Distress | Curves may invert steeply when near-term default or restructuring dominates |
| Flight to quality | Risky spreads widen as investors prefer safer assets |

Lower-rated sectors usually have steeper or more volatile spread curves because their default probabilities are more sensitive to the business cycle.

## Spread Curve vs Term Structure Of Interest Rates

Do not confuse these:

| Curve | What is on the y-axis |
|---|---|
| [[Yield curve]] | Government or benchmark yield by maturity |
| [[Spot curve]] | Zero-coupon spot rate by maturity |
| [[Forward curve]] | Implied future rate by maturity |
| [[Spread curve]] | Credit spread by maturity |

The spread curve is about compensation over a benchmark, not the benchmark rate itself.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Mixing non-comparable bonds | Use similar seniority, security, currency, liquidity, and option features |
| Ignoring embedded options | Options distort quoted spreads |
| Calling every upward curve a rate expectation | Spread curves reflect credit/liquidity/recovery expectations |
| Forgetting credit quality | Lower-rated curves are typically steeper and more cyclical |
| Treating liquidity effects as default risk | Liquidity can widen spreads even if default risk is unchanged |

## Memory Hook

```text
Yield curve = time value by maturity.
Spread curve = credit fear by maturity.
```

## Related Concepts

- [[Term Structure of Credit Spreads]]
- [[Credit spread]]
- [[G-spread]]
- [[I-spread]]
- [[Z-Spread]]
- [[Option-Adjusted Spread]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Recovery rate]]
- [[Probability of Default]]
- [[Structural Models]]
