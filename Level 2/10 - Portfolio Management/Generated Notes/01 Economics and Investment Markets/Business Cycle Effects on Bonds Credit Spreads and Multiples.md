---
title: Business Cycle Effects on Bonds Credit Spreads and Multiples
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, economics, business-cycle, yield-curve, credit-spreads, valuation-multiples]
aliases: [Business Cycle Effects, Yield Curve and Business Cycle, Credit Spreads and Business Cycle, Valuation Multiples and Business Cycle]
---

# Business Cycle Effects on Bonds Credit Spreads and Multiples

## Intuition

The business cycle changes asset values through three channels:

1. expected cash flows,
2. default-free rates,
3. risk premiums.

That is why the same macro phase can affect bonds, credit spreads, earnings, and valuation multiples at the same time.

See: [[Economics and Investment Markets Framework]] · [[Consumption Hedging and Equity Risk Premium]] · [[Credit spreads]]

## Phase-by-Phase Map

| Phase | Policy rates | Yield curve | Credit spreads | Equities / earnings | Multiples |
|---|---|---|---|---|---|
| **Initial recovery** | Low or bottoming | Steep | Wide but narrowing | Earnings begin recovering | Multiples often rise early |
| **Expansion** | Rising as central bank removes stimulus | Flattening | Narrow | Cyclical earnings strong | Multiples supported by growth and lower risk premiums |
| **Late expansion / peak** | High or still rising | Flat or inverted | Start widening | Earnings growth slows | Multiples vulnerable |
| **Contraction / recession** | Falling as policy eases | Steepening | Wide | Earnings fall, especially cyclicals | Multiples pressured by risk premiums |

The most tested timing issue:

> The curve often **flattens or inverts near the peak**, then **steepens in recession** as short-term rates are cut.

## Policy Rates and the Yield Curve

Central banks affect the short end of the yield curve through policy rates.

Long-term rates reflect:

- expected future short-term rates,
- expected inflation,
- real growth expectations,
- term premiums,
- inflation uncertainty premiums.

### Recovery

In early recovery, policy rates are often still low after recession-fighting cuts. Long-term yields may rise as investors anticipate stronger growth and future inflation.

Result:

$$
\text{Yield curve: steep}
$$

### Expansion

As growth improves and inflation pressure builds, central banks raise short-term rates.

Result:

$$
\text{Short rates rise faster than long rates}
$$

The curve flattens.

### Peak / slowdown

Short rates may be high because the central bank has tightened policy. Long-term rates may stop rising or fall if markets expect slower future growth.

Result:

$$
\text{Yield curve: flat or inverted}
$$

### Recession

Central banks cut policy rates aggressively. Short-term rates fall. Long-term yields may also fall, but often less than short rates.

Result:

$$
\text{Yield curve: steepening}
$$

## Bond Maturity Performance

Bond prices move inversely with yields. Longer maturity bonds have higher duration, so they are more sensitive to yield changes.

| Rate environment | Relative bond effect |
|---|---|
| Yields rising | Long-maturity bonds underperform short-maturity bonds |
| Yields falling | Long-maturity bonds outperform short-maturity bonds |
| Curve flattening from short-rate hikes | Short maturities are hit by policy-rate increases |
| Curve steepening from short-rate cuts | Short rates fall more; curve steepens |

Exam trap:

> "Recession" does not automatically mean bad for high-quality bonds. If rates fall, high-quality bonds can perform well.

## Credit Spreads

[[Credit spreads]] compensate investors for expected default losses, downgrade risk, liquidity risk, and other credit risks.

Credit spreads are countercyclical:

| Phase | Credit spread behavior | Reason |
|---|---|---|
| Expansion | Narrow | Defaults expected to be low; recovery rates stronger |
| Slowdown | Widen | Credit risk begins rising |
| Recession | Wide | Defaults increase and recovery rates decline |
| Recovery | Narrow from wide levels | Credit outlook improves |

When spreads narrow, credit-sensitive bonds outperform default-free bonds. When spreads widen, they underperform.

## Rating Sensitivity

Lower-rated bonds are more sensitive to credit-spread changes.

| Spread movement | Lower-rated bonds | Higher-rated bonds |
|---|---|---|
| Spreads narrow | Benefit more | Benefit less |
| Spreads widen | Suffer more | Suffer less |

Reason: lower-rated bonds have more credit risk exposure, so the spread component of their yield is larger and more volatile.

## Cyclical vs Defensive Credit Quality

Product-market characteristics affect credit quality.

| Sector type | Revenue behavior | Credit implication |
|---|---|---|
| **Cyclical** | Revenues and earnings rise/fall with GDP | Spreads widen more in downturns |
| **Defensive / non-cyclical** | Demand is more stable | Spreads are more stable |

Examples:

- Cyclical: autos, durable goods, consumer discretionary, industrials.
- Defensive: consumer staples, utilities, healthcare.

Financial leverage amplifies the effect. A highly levered cyclical company has the worst credit profile in a downturn because cash flows fall when debt capacity is most valuable.

## Earnings Expectations

Cyclical earnings are highly sensitive to the business cycle.

| Company type | Expansion | Recession |
|---|---|---|
| Cyclical | Earnings rise sharply | Earnings fall sharply |
| Defensive | Earnings more stable | Earnings more stable |

Short-term earnings expectations react strongly to the current phase. Long-term earnings expectations can be less volatile, but still decline if investors believe the downturn damages long-run profitability.

## Valuation Multiples

Valuation multiples such as P/E and P/B depend on growth and required return.

A simple justified P/E intuition:

$$
P/E \approx \frac{\text{Payout ratio}}{r - g}
$$

Multiples rise when:

- expected growth $g$ rises,
- required return $r$ falls,
- real rates fall,
- inflation uncertainty premiums fall,
- equity risk premiums fall.

Multiples fall when:

- expected growth falls,
- required return rises,
- risk premiums rise,
- uncertainty increases.

## Business Cycle and Multiples

| Phase | Growth expectations | Risk premiums | Multiple effect |
|---|---|---|---|
| Recovery | Improve from depressed levels | Begin falling | Multiples can rise strongly |
| Expansion | Strong | Lower | Multiples often supported |
| Slowdown | Deteriorate | Rising | Multiples compress |
| Recession | Weak | High | Multiples pressured, though markets may anticipate recovery before earnings bottom |

Exam nuance:

> Equity markets are forward-looking. Multiples may start rising before reported earnings recover if investors expect the recovery ahead.

## Style Rotation Trap

The source material often links style performance to the cycle:

| Cycle point | Style tendency |
|---|---|
| Immediate aftermath of recession | Value and cyclical assets can rebound strongly |
| Active expansion | Growth can outperform as earnings momentum is rewarded |
| Slowdown / recession | Defensive and quality stocks often outperform |

Do not apply this mechanically without reading the vignette. The exam usually gives clues about growth expectations, risk premiums, or credit conditions.

## Worked Example: Credit Spreads

Two bonds have equal duration but different credit ratings:

| Bond | Rating | Current spread |
|---|---|---:|
| Bond A | AA | 80 bps |
| Bond B | B | 500 bps |

In recovery, spreads narrow:

- AA spread narrows by 20 bps.
- B spread narrows by 150 bps.

With the same duration, Bond B gains more from spread narrowing because its yield falls more.

In recession, the reverse is true. If spreads widen, Bond B suffers more.

## Exam Traps

| Trap | Correct response |
|---|---|
| Say yield curve inversion happens at the deepest recession point | Inversion is more typical near slowdown/peak; recession cuts can steepen the curve |
| Assume all corporate bonds behave similarly | Lower-rated and cyclical bonds have more spread sensitivity |
| Assume high-quality bonds always underperform in recession | Falling rates can support high-quality bonds |
| Treat expected news as new information | Prices react to surprises, not already expected conditions |
| Say multiples are high only because market is overvalued | Higher multiples can be justified by higher growth or lower required returns |
| Say defensive companies have no credit risk | They usually have more stable cash flows, not zero risk |

## Memory Hook

> **Peak flattens. Recession steepens. Credit widens in weakness and narrows in recovery. Multiples follow growth up and risk premiums down.**

## Exam-Day Checklist

1. Identify the business-cycle phase.
2. Decide whether short rates are rising or falling.
3. Decide whether the curve is steepening, flattening, or inverted.
4. For bonds, link yield changes to maturity/duration.
5. For credit, decide whether spreads are widening or narrowing.
6. Separate lower-rated from higher-rated credit.
7. Separate cyclical from defensive earnings and credit quality.
8. For multiples, identify whether $g$ or $r$ changed.

## Related Concepts

- [[Economics and Investment Markets Framework]]
- [[Consumption Hedging and Equity Risk Premium]]
- [[Credit spreads]]
- [[Business Cycle]]
- [[Risk Premium]]
- [[Yield Curve]]
