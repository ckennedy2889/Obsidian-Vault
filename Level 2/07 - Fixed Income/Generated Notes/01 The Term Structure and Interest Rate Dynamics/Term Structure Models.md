---
title: Term Structure Models
subject: Fixed Income
tags: [CFA-L2, FixedIncome, TermStructureModels, InterestRates]
aliases: [fixed income term structure models, equilibrium term structure models, arbitrage-free term structure models, Vasicek model, CIR model, Ho-Lee model, KWF model]
---

# Term Structure Models

## The Real-World Analogy

A term structure model is the engine under an interest-rate tree or simulation.

It tells the model how rates are allowed to move over time.

## Two Model Families

| Model Family | Starting Point | Best Use |
|---|---|---|
| Equilibrium models | Economic assumptions about rate behavior | Explaining rate dynamics |
| Arbitrage-free models | Today's observed yield curve | Pricing securities to match market prices |

## Equilibrium Models

Equilibrium models derive the term structure from assumptions about the economy and interest-rate behavior.

Examples include:

| Model | Feature |
|---|---|
| Vasicek | Mean reversion, normally distributed rates, can produce negative rates |
| Cox-Ingersoll-Ross (CIR) | Mean reversion with volatility related to rate level, nonnegative rates |

Equilibrium models are useful for intuition but may not exactly fit today's observed yield curve.

## Arbitrage-Free Models

Arbitrage-free models are calibrated to today's yield curve.

```text
Observed market curve
  |
  v
Calibrate model drift
  |
  v
Model prices benchmark bonds correctly
  |
  v
Use model for valuation
```

Examples include:

| Model | Feature |
|---|---|
| Ho-Lee | Normally distributed rates, time-dependent drift, can produce negative rates |
| Kalotay-Williams-Fabozzi (KWF) | Lognormal rates, rates stay nonnegative, foundation for lognormal binomial trees |

## Why Arbitrage-Free Models Matter For Valuation

For pricing bonds with embedded options, the model must match current market prices before valuing the option.

If the model does not fit today's curve, the option value may reflect model error rather than actual optionality.

```text
Wrong starting curve
  |
  v
Wrong future rate paths
  |
  v
Wrong option exercise values
  |
  v
Wrong bond value
```

## Exam Traps

| Trap | Correction |
|---|---|
| Thinking equilibrium models exactly match today's curve | They are driven by economic assumptions and may not fit observed prices. |
| Thinking arbitrage-free models explain why rates are where they are | They fit the current curve; they are primarily valuation tools. |
| Forgetting negative-rate possibility | Normal models can produce negative rates; lognormal models do not. |
| Confusing CIR and Vasicek | CIR keeps rates nonnegative; Vasicek can go negative. |
| Ignoring calibration | Arbitrage-free valuation requires calibration to market prices. |

## Memory Hook

```text
Equilibrium models explain.
Arbitrage-free models price.
Normal can go negative.
Lognormal stays positive.
```

## Related Concepts

- [[Arbitrage-Free Valuation Framework]]
- [[Binomial Interest Rate Tree]]
- [[Pathwise Valuation and Monte Carlo Simulation]]
- [[Backward Induction]]
- [[Option-Adjusted Spread]]
