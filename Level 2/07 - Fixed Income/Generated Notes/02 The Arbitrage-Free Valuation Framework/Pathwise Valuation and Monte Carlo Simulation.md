---
title: Pathwise Valuation and Monte Carlo Simulation
subject: Fixed Income
tags: [CFA-L2, FixedIncome, MonteCarlo, PathwiseValuation, ArbitrageFreeValuation]
aliases: [pathwise valuation, Monte Carlo forward-rate simulation, Monte Carlo fixed income valuation, path dependent fixed income valuation]
---

# Pathwise Valuation and Monte Carlo Simulation

## The Real-World Analogy

Backward induction solves a tree from the end backward.

Pathwise valuation drives each possible route from start to finish, values the cash flows along that route, and averages the routes.

Monte Carlo does the same thing, but with thousands of randomly generated routes.

## Pathwise Valuation

[[Pathwise valuation]] values a security by:

```text
1. List each possible interest-rate path.
2. Discount cash flows along each path.
3. Compute each path's present value.
4. Average the path values using path probabilities.
```

For simple option-free bonds, pathwise valuation should match backward induction and spot-rate valuation.

## When Pathwise Works Best

Pathwise valuation is useful when cash flows depend on the path rates take.

Examples:

| Security | Why Path Matters |
|---|---|
| Mortgage-backed security | Prepayments depend on rate history |
| Structured products | Cash flows may depend on cumulative events |
| Callable structures with history-dependent rules | Exercise may depend on prior paths |

For ordinary callable or putable bonds with node-based exercise, backward induction is usually more natural because the exercise decision depends on the value at each node.

## Monte Carlo Forward-Rate Simulation

[[Monte Carlo simulation]] generates many random interest-rate paths from a term structure model.

Process:

```text
Step 1: Choose a term structure model.
Step 2: Calibrate model drift to today's yield curve.
Step 3: Simulate many future rate paths.
Step 4: Project security cash flows along each path.
Step 5: Discount cash flows along each path.
Step 6: Average path values.
```

As the number of simulations increases, the average value converges toward the model value.

## Calibration

Monte Carlo must be calibrated to be arbitrage-free.

```text
Binomial tree calibration:
Adjust node rates so benchmark bonds price correctly.

Monte Carlo calibration:
Adjust drift terms so average simulated benchmark values match market prices.
```

Without calibration, the simulation may generate plausible paths but wrong prices.

## Binomial Tree vs Monte Carlo

| Feature | Binomial Tree | Monte Carlo |
|---|---|---|
| Path count | Small, structured, recombining | Large random sample |
| Early exercise | Natural with backward induction | More difficult |
| Path dependence | Limited because tree recombines | Strong because each path history is preserved |
| Accuracy | Exact within tree assumptions | Sampling error falls with more paths |
| Main use | Callable/putable bonds | MBS and path-dependent securities |

For MBS and similar securities, recombining binomial trees lose important path history. Monte Carlo is usually preferred because prepayments depend on the sequence of past rates, not just the current node.

## Exam Traps

| Trap | Correction |
|---|---|
| Thinking Monte Carlo is automatically arbitrage-free | It must be calibrated with drift adjustments. |
| Using Monte Carlo for simple callable exercise by default | Backward induction is usually cleaner for node-based early exercise. |
| Forgetting sampling error | Monte Carlo values vary unless many paths are used. |
| Ignoring path dependence | Monte Carlo is valuable because it preserves full path history. |
| Treating pathwise and backward induction as inconsistent | For simple option-free bonds, they should agree. |
| Using a recombining tree for MBS prepayment modeling | Prepayments are path-dependent, so Monte Carlo is typically the better tool. |

## Memory Hook

```text
Pathwise = value every route.
Monte Carlo = value many random routes.
Calibration = make routes price today's market correctly.
```

## Related Concepts

- [[Arbitrage-Free Valuation Framework]]
- [[Binomial Interest Rate Tree]]
- [[Backward Induction]]
- [[Term Structure Models]]
- [[Mortgage-backed securities]]
- [[Option-Adjusted Spread]]
