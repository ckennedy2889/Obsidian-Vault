---
title: Backward Induction
subject: Fixed Income
tags: [CFA-L2, FixedIncome, BackwardInduction, ArbitrageFreeValuation]
aliases: [backward induction valuation, fixed income backward induction, node valuation]
---

# Backward Induction

## The Real-World Analogy

Backward induction is solving a maze from the exit backward.

At maturity, you know exactly what the bond pays. Then you step backward one node at a time, discounting expected future values until you reach today.

## Definition

[[Backward Induction]] is a valuation method that works from maturity back to the present through an interest rate tree.

At each node:

$$
V_{\text{node}} = \frac{CF_{\text{next}} + 0.5V_{up} + 0.5V_{down}}{1+r_{\text{node}}}
$$

where:

| Term | Meaning |
|---|---|
| $V_{\text{node}}$ | Value at the current node |
| $CF_{\text{next}}$ | Cash flow over the next period |
| $V_{up}$ | Value at the next up node |
| $V_{down}$ | Value at the next down node |
| $r_{\text{node}}$ | One-period rate at the current node |

## Process

```text
Step 1: Start at maturity values.
Step 2: Move one period backward.
Step 3: Average next-node values using risk-neutral probabilities.
Step 4: Add any coupon cash flow.
Step 5: Discount at the node's one-period rate.
Step 6: Repeat until time 0.
```

## Option-Free Bonds

For an option-free bond, backward induction should match spot-rate pricing if the tree is calibrated.

```text
Spot curve method = direct discounting of fixed cash flows
Tree method = expected discounted values through calibrated paths
```

Both are arbitrage-free representations of the same term structure.

## Callable And Putable Bonds

Backward induction is especially useful for embedded options.

### Callable Bond

The issuer owns the call option. The investor receives the lower of:

```text
Continuation value
Call price
```

So:

$$
V_{\text{callable node}} = \min(\text{continuation value}, \text{call price})
$$

### Putable Bond

The investor owns the put option. The investor receives the higher of:

```text
Continuation value
Put price
```

So:

$$
V_{\text{putable node}} = \max(\text{continuation value}, \text{put price})
$$

## Exam Traps

| Trap | Correction |
|---|---|
| Working forward instead of backward | Values are known at maturity, so work backward. |
| Using YTM at each node | Use the node's one-period rate. |
| Forgetting coupon timing | Add cash flows at the correct node/period. |
| Reversing callable and putable logic | Callable uses min; putable uses max from investor perspective. |
| Thinking tree and spot method disagree for option-free bonds | Calibrated trees should match spot-rate valuation. |

## Memory Hook

```text
Callable: issuer chooses -> investor gets min.
Putable: investor chooses -> investor gets max.
```

## Related Concepts

- [[Binomial Interest Rate Tree]]
- [[Arbitrage-Free Valuation Framework]]
- [[Option-Adjusted Spread]]
- [[Effective Duration]]
- [[Pathwise Valuation]]
