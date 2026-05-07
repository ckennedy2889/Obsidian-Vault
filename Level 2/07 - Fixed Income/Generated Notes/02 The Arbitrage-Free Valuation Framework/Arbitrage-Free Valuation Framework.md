---
title: Arbitrage-Free Valuation Framework
subject: Fixed Income
tags: [CFA-L2, FixedIncome, ArbitrageFreeValuation]
aliases: [arbitrage-free valuation, arbitrage-free fixed income valuation, no-arbitrage bond valuation]
---

# Arbitrage-Free Valuation Framework

## The Real-World Analogy

Arbitrage-free valuation is like making sure every grocery bundle costs the same whether you buy the bundle or buy each item separately.

If a bond's cash flows can be replicated with zero-coupon bonds, the bond must equal the cost of those zero-coupon pieces. If it does not, traders can buy the cheap version and sell the expensive version.

## Definition

[[Arbitrage-free valuation]] prices a fixed-income instrument so there is no riskless profit from replicating its cash flows with other securities.

Two no-arbitrage principles sit underneath the framework:

| Principle | Meaning |
|---|---|
| Value additivity | The value of the whole must equal the sum of the values of the parts |
| Dominance | If two risk-free assets have the same future payoff, the cheaper one dominates and creates arbitrage |

For an option-free fixed-rate bond:

$$
V_0 = \sum_{t=1}^{T} \frac{CF_t}{(1+z_t)^t}
$$

where:

| Term | Meaning |
|---|---|
| $V_0$ | Arbitrage-free value today |
| $CF_t$ | Cash flow at time $t$ |
| $z_t$ | Spot rate for maturity $t$ |

## Why Spot Rates Matter

Each cash flow has its own maturity, so each cash flow should be discounted at the spot rate for that maturity.

```text
1-year coupon -> 1-year spot rate
2-year coupon -> 2-year spot rate
Final principal -> maturity spot rate
```

Using one YTM for every cash flow is a summary measure, not the true cash-flow-by-cash-flow arbitrage-free engine unless the spot curve is flat.

## Option-Free Bond Pricing

For a 3-year annual-pay bond:

$$
V_0 = \frac{C}{1+z_1} + \frac{C}{(1+z_2)^2} + \frac{C+FV}{(1+z_3)^3}
$$

This is equivalent to pricing the bond as a portfolio of zero-coupon bonds.

## Why A Tree Is Needed

Spot-rate discounting works cleanly for option-free bonds because cash flows are fixed.

For bonds with embedded options, cash flows depend on future rates.

```text
Future rates fall
  |
  v
Callable bond may be called
  |
  v
Cash flows change
```

So we need a model of future rate paths, usually a calibrated [[Binomial Interest Rate Tree]] or simulation.

## Zero-Curve Pricing vs Lattice Pricing

| Method | Best For | Core Idea |
|---|---|---|
| Spot curve / zero curve | Option-free bonds | Discount each fixed cash flow at its maturity spot rate |
| Binomial lattice | Callable, putable, path-contingent rates | Model future rates and value by backward induction |
| Monte Carlo | Path-dependent securities | Simulate many rate paths and average discounted values |

For option-free bonds, spot-rate pricing and a calibrated arbitrage-free tree should give the same value.

## Exam Traps

| Trap | Correction |
|---|---|
| Discounting all cash flows at YTM | Arbitrage-free valuation uses spot rates. |
| Thinking spot rates and tree values differ for option-free bonds | If the tree is calibrated, they should match. |
| Thinking volatility changes option-free bond value in a calibrated tree | For option-free bonds, higher rate volatility changes the tree shape but not the calibrated arbitrage-free value. |
| Using spot curve for callable bond optionality | Embedded options require rate paths and exercise decisions. |
| Forgetting replication logic | Bond value equals the value of its replicating zero-coupon cash flows. |

## Memory Hook

```text
No arbitrage = no free lunch.
Option-free = discount fixed cash flows with spot rates.
Options = model rate paths.
```

## Related Concepts

- [[Par vs Spot vs Forward Rates]]
- [[Binomial Interest Rate Tree]]
- [[Backward Induction]]
- [[Pathwise Valuation]]
- [[Monte Carlo Forward-Rate Simulation]]
- [[Term Structure Models]]
- [[Option-Adjusted Spread]]
