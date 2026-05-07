---
title: Yield Curve Factor Exposures
subject: Fixed Income
tags: [CFA-L2, FixedIncome, YieldCurve, Duration, RiskManagement]
aliases: [yield curve factors, level steepness curvature, yield curve risk factors, maturity structure of yield volatilities]
---

# Yield Curve Factor Exposures

## The Real-World Analogy

A yield curve is like a flexible ruler.

It can move up or down, twist steeper or flatter, and bend in the middle. A bond portfolio can be sensitive to each kind of movement.

## Yield Curve Risk

Yield curve risk is the risk that unexpected changes in the benchmark yield curve change the value of a bond or bond portfolio.

The broad tools are:

| Tool | Best For |
|---|---|
| [[Effective Duration]] | Parallel yield curve shifts |
| [[Key Rate Duration]] | Nonparallel shifts at specific maturities |
| Three-factor model | Level, steepness, and curvature movements |

## Level, Steepness, And Curvature

| Factor | Meaning | Curve Movement |
|---|---|---|
| Level | Parallel move | All yields rise or fall together |
| Steepness | Slope change | Long rates rise while short rates fall, or the reverse |
| Curvature | Bend change | Short and long rates move differently from intermediate rates |

Increasing curvature often means short- and long-term rates rise while intermediate rates change less.

## Three-Factor Exposure Model

The portfolio's percentage value change can be modeled as:

$$
\%\Delta PV \approx -D_L \Delta x_L - D_S \Delta x_S - D_C \Delta x_C
$$

where:

| Term | Meaning |
|---|---|
| $D_L$ | Sensitivity to level movement |
| $D_S$ | Sensitivity to steepness movement |
| $D_C$ | Sensitivity to curvature movement |
| $\Delta x_L$ | Change in level factor |
| $\Delta x_S$ | Change in steepness factor |
| $\Delta x_C$ | Change in curvature factor |

## Key Rate Duration Link

[[Key Rate Duration]] measures sensitivity to a change in one maturity point on the par curve, holding other key rates constant.

It is useful because real yield curves rarely move in perfectly parallel shifts.

```text
Effective duration:
What if the whole curve shifts?

Key rate duration:
What if the 5-year point shifts?

Factor exposure:
What if the curve level, slope, or curvature changes?
```

## Maturity Structure Of Yield Volatilities

The term structure of yield volatility plots yield volatility by maturity.

CFA's typical pattern:

```text
Short-term rates are more volatile than long-term rates.
```

Why?

| Maturity Area | Main Uncertainty |
|---|---|
| Short rates | Monetary policy uncertainty |
| Long rates | Real economy and inflation uncertainty |

Interest rate volatility matters because it drives price volatility.

It matters even more for bonds with embedded options because option values increase when rate volatility increases.

## Price Volatility

Price volatility depends on both:

```text
Yield volatility
and
Duration/convexity exposure
```

Longer-duration bonds may have high price volatility even if long-term yield volatility is lower than short-term yield volatility.

## Economic Factor Views

Managers form views on benchmark rates, spreads, and curve shape using macro factors.

| Economic Factor | Typical Fixed-Income Link |
|---|---|
| Monetary policy | Dominates short and intermediate benchmark yields |
| Inflation expectations | Major driver of long-term yields |
| GDP growth | Affects real rates, credit spreads, and curve shape |
| Flight to quality | Lowers government yields and widens risky spreads |
| Expansion with inflation pressure | Can create bearish flattening |
| Recession/easing | Can create bullish steepening |

## Exam Traps

| Trap | Correction |
|---|---|
| Using effective duration for nonparallel shifts | Use key rate duration or factor exposures. |
| Thinking short-rate volatility means short bonds always have highest price volatility | Price volatility also depends on duration. |
| Ignoring embedded options | Callable and putable bonds are especially volatility-sensitive. |
| Confusing steepness and curvature | Steepness is slope; curvature is bending. |
| Assuming one duration number captures all yield curve risk | It misses shaping risk. |

## Memory Hook

```text
Level = elevator.
Steepness = seesaw.
Curvature = bow.
```

## Related Concepts

- [[Effective Duration]]
- [[Key Rate Duration]]
- [[Effective Convexity]]
- [[One-Sided Durations]]
- [[Option-Adjusted Spread]]
- [[Yield curve]]
- [[Term Structure Theories]]
