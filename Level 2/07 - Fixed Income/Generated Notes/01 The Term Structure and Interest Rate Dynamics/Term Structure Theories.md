---
title: Term Structure Theories
subject: Fixed Income
tags: [CFA-L2, FixedIncome, TermStructure, YieldCurve]
aliases: [traditional term structure theories, pure expectations theory, unbiased expectations theory, local expectations theory, liquidity preference theory, segmented markets theory, preferred habitat theory]
---

# Term Structure Theories

## The Real-World Analogy

The yield curve is a set of prices for lending money at different maturities.

Term structure theories answer:

```text
Why are those maturity prices shaped this way?
```

Some theories say the curve is mostly expectations. Others say it is mostly risk premiums or maturity-specific supply and demand.

## Summary Table

| Theory | Forward Rates Mean | Risk Premium? | Yield Curve Implication |
|---|---|---|---|
| Pure expectations | Expected future spot rates | No | Curve shape reflects expected future rates |
| Local expectations | Short-horizon expected returns equal risk-free rate | Only beyond short horizon | Short holding-period returns should be equal |
| Liquidity preference | Expected future spot rates plus liquidity premium | Yes, increasing with maturity | Upward slope may reflect premium, not rising rate expectations |
| Segmented markets | Supply/demand in each maturity segment | Not central | Maturities are independent markets |
| Preferred habitat | Expected future spot rates plus maturity-specific premium | Yes, varies by segment | Almost any shape possible |

## Pure Expectations Theory

Pure expectations theory says forward rates are unbiased forecasts of future spot rates.

```text
Forward rate = expected future spot rate
```

Implications:

| Yield Curve Shape | Interpretation |
|---|---|
| Upward sloping | Short-term rates expected to rise |
| Downward sloping | Short-term rates expected to fall |
| Flat | Short-term rates expected to stay constant |

The theory assumes risk neutrality. Investors do not demand extra compensation for choosing a maturity that differs from their investment horizon.

## Local Expectations Theory

Local expectations theory keeps the risk-neutral assumption only for very short holding periods.

The idea:

```text
Over a short horizon, all default-free bonds should earn the risk-free rate.
```

It is "local" because it applies over a short horizon, not necessarily over long horizons.

## Liquidity Preference Theory

Liquidity preference theory says forward rates include:

```text
Expected future spot rate + liquidity premium
```

The liquidity premium compensates investors for interest-rate risk and is positively related to maturity.

Implication:

```text
Observed forward rates are upward-biased estimates of expected future spot rates.
```

An upward-sloping curve does not necessarily mean future short rates are expected to rise. It could mean rates are expected to stay flat or even fall slightly, but the liquidity premium creates the upward slope.

A downward-sloping curve is stronger evidence that short-term rates are expected to fall, because the curve slopes downward despite positive liquidity premiums.

## Segmented Markets Theory

Segmented markets theory says each maturity segment is its own market.

```text
Short maturity supply/demand determines short yields.
Long maturity supply/demand determines long yields.
```

Investors and borrowers have maturity constraints or strong preferences. Pension funds and insurers may prefer long maturities for asset-liability matching, while money market investors may prefer short maturities.

Forward rates are not necessarily expectations of future spot rates.

## Preferred Habitat Theory

Preferred habitat theory is a more flexible version of segmented markets.

Investors and borrowers prefer certain maturity habitats but will leave them if adequately compensated.

```text
Preferred maturity
  |
  v
Will shift if premium is attractive enough
```

Premiums depend on supply and demand in each maturity segment. Unlike liquidity preference theory, the premium does not have to rise steadily with maturity.

## Exam Traps

| Trap | Correction |
|---|---|
| Saying liquidity preference requires an upward-sloping curve | It adds positive premiums, but expected rate declines can still create a downward curve. |
| Treating preferred habitat as identical to segmented markets | Preferred habitat allows investors to leave their preferred segment if compensated. |
| Saying segmented markets uses forward rates as expectations | It focuses on supply/demand by maturity segment. |
| Forgetting risk neutrality in pure expectations | Pure expectations assumes no maturity risk premium. |
| Assuming all upward curves imply rising rates | Under liquidity preference, upward slope may be a liquidity premium. |

## Memory Hook

```text
Pure expectations = forwards are forecasts.
Liquidity preference = forwards are forecasts plus upward premium.
Segmented markets = each maturity has its own crowd.
Preferred habitat = crowds can move if paid.
```

## Related Concepts

- [[Par vs Spot vs Forward Rates]]
- [[Rolling Down the Yield Curve]]
- [[Yield Curve Factor Exposures]]
- [[Spot rate]]
- [[Forward rate]]
- [[Yield curve]]
