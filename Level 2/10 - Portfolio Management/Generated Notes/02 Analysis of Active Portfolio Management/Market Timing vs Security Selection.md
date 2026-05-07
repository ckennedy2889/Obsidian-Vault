---
title: Market Timing vs Security Selection
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, active-management, market-timing, security-selection, fundamental-law]
aliases: [Market Timing, Security Selection, Sector Rotation, Active Management Strategy Changes]
---

# Market Timing vs Security Selection

## Intuition

An active manager can try to win in two very different ways.

One manager says, "I know **when** the market, a sector, or an asset class will do better." That is **market timing**. Another manager says, "I know **which securities** inside the market are mispriced." That is **security selection**.

The [[Fundamental Law of Active Management]] makes the comparison precise. It asks:

> How good is each forecast, how many truly independent forecasts does the manager make, and how cleanly do those forecasts become actual active weights?

That is the bridge from strategy description to exam calculation:

$$
IR = TC \times IC \times \sqrt{BR}
$$

and

$$
E(R_A) = TC \times IC \times \sqrt{BR} \times \sigma_A
$$

See: [[Information Ratio]] · [[Information Coefficient]] · [[Breadth]] · [[Transfer Coefficient]] · [[Active Risk and Tracking Error]]

## Plain-English Definitions

| Strategy | What the manager forecasts | Typical bet | Main FLAM issue |
|---|---|---|---|
| **Market timing** | Direction of a market, asset class, sector, style, or factor over time | Overweight equities versus cash; rotate into cyclicals; raise duration | Usually high potential IC per call, but low [[Breadth]] |
| **Security selection** | Relative performance of securities inside a benchmark | Overweight stock A, underweight stock B | Usually lower IC per name, but much higher potential breadth |
| **Sector rotation** | Relative performance of sectors over time | Overweight technology, underweight utilities | A market-timing subtype; breadth depends on independent sector calls |

The exam usually wants you to notice that **market timing is time-series skill** and **security selection is cross-sectional skill**.

## Why the Distinction Matters

The two strategies may have the same goal, positive [[Active Return]], but the mechanics are different.

### Market timing

A market timer makes a directional call:

- Stocks will outperform cash.
- Bonds will outperform stocks.
- Growth will outperform value.
- Consumer staples will outperform consumer discretionary.

For a simple up-or-down call, CFA often measures skill as:

$$
IC = 2(\%\text{ correct}) - 1
$$

If the manager is correct 50% of the time:

$$
IC = 2(0.50) - 1 = 0
$$

No edge. The manager is guessing.

If the manager is correct 55% of the time:

$$
IC = 2(0.55) - 1 = 0.10
$$

That sounds like a small edge, but it can matter if it is repeated across enough truly independent timing decisions.

### Security selection

A security selector ranks securities by expected active return:

- Overweight securities with positive expected active return.
- Underweight or short securities with negative expected active return.
- Keep active weights proportional to expected reward per unit of active risk when unconstrained.

Here, the [[Information Coefficient]] is usually interpreted as the correlation between forecasted active returns and realized active returns. If the manager's rankings line up well with later outcomes, IC is positive.

## The Fundamental Law Lens

The full law is:

$$
IR = TC \cdot IC \cdot \sqrt{BR}
$$

Each strategy changes a different part of the equation.

| FLAM input | Market timing | Security selection | Exam implication |
|---|---|---|---|
| $IC$ | Can be based on percentage of correct directional calls: $IC = 2p - 1$ | Correlation between forecasts and realized active returns | Do not use the market-timing shortcut for ordinary stock-selection ranking unless the vignette frames forecasts as binary calls |
| $BR$ | Number of independent timing decisions per year | Number of independent security-selection decisions per year | Security selection often has more possible breadth, but only if forecasts are independent |
| $TC$ | Reduced by limits on asset allocation, sector weights, cash, derivatives, leverage, or tracking error | Reduced by long-only constraints, position limits, turnover limits, sector caps | Constraints lower IR linearly |
| $\sigma_A$ | Size of timing bet | Size of active weights versus benchmark | Aggressiveness scales expected active return, but does not improve unconstrained IR |

## Worked Example 1: Market Timer vs Security Selector

Two managers are unconstrained, so $TC = 1$.

**Manager A: market timer**

- Makes quarterly market calls.
- Correct 55% of the time.
- $BR = 4$ timing calls per year.

Compute IC:

$$
IC = 2(0.55) - 1 = 0.10
$$

Compute IR:

$$
IR = 1.0 \times 0.10 \times \sqrt{4}
$$

$$
IR = 0.10 \times 2 = 0.20
$$

**Manager B: security selector**

- Makes 50 independent stock-selection decisions per year.
- $IC = 0.04$.
- $BR = 50$.

Compute IR:

$$
IR = 1.0 \times 0.04 \times \sqrt{50}
$$

$$
IR = 0.04 \times 7.071 = 0.283
$$

**Interpretation:** the security selector has lower per-decision skill, but higher breadth. The Fundamental Law says Manager B has the better expected risk-adjusted active performance:

$$
0.283 > 0.200
$$

This is the core exam lesson: **small skill applied many independent times can beat larger skill applied rarely.**

## Worked Example 2: Expected Active Return

A constrained active equity manager has:

- $IC = 0.05$
- $BR = 100$
- $TC = 0.60$
- Active risk $\sigma_A = 6\%$

First compute IR:

$$
IR = 0.60 \times 0.05 \times \sqrt{100}
$$

$$
IR = 0.60 \times 0.05 \times 10 = 0.30
$$

Now compute expected active return:

$$
E(R_A) = IR \times \sigma_A = 0.30 \times 6\% = 1.8\%
$$

The manager is expected to add 1.8% per year over the benchmark, given the active risk taken.

If the same manager were unconstrained, $TC = 1$:

$$
IR^* = 1.0 \times 0.05 \times 10 = 0.50
$$

$$
E(R_A)^* = 0.50 \times 6\% = 3.0\%
$$

The constraint cost is:

$$
3.0\% - 1.8\% = 1.2\%
$$

## Sector Rotation as Market Timing

Sector rotation is market timing inside the equity market. Instead of deciding "stocks versus cash," the manager decides which sector should outperform.

Example:

- Overweight consumer staples if the manager expects a defensive phase.
- Overweight consumer discretionary if the manager expects a cyclical upswing.

The active risk of a two-sector timing strategy comes from the volatility of the return difference between the two sectors:

$$
\sigma(R_X - R_Y) =
\sqrt{\sigma_X^2 + \sigma_Y^2 - 2\rho_{XY}\sigma_X\sigma_Y}
$$

If the manager makes $n$ independent timing bets per year, annualized active risk scales as:

$$
\sigma_{A,\text{annual}} = \sigma(R_X - R_Y)\sqrt{n}
$$

The trap is that **monthly sector calls are not automatically 12 independent bets**. If every call is driven by the same recession forecast, true breadth is closer to 1 than 12.

## Strategy Changes Under the Fundamental Law

CFA can describe a strategy change and ask whether expected active performance improves. Translate the change into $IC$, $BR$, $TC$, and $\sigma_A$.

| Strategy change | Likely FLAM effect | Good only if... |
|---|---|---|
| Add more securities to the research universe | Higher possible $BR$ | New forecasts are truly independent |
| Increase rebalance frequency | Higher nominal $BR$ | New timing decisions are not serially dependent |
| Move from quarterly timing to monthly timing | $BR$ may rise from 4 to 12 | The monthly calls use fresh independent information |
| Relax long-only or sector constraints | Higher $TC$ | The manager has skill worth implementing |
| Add derivatives to express views | Higher $TC$ or more efficient $\sigma_A$ | Derivatives are used to express existing skill, not to manufacture fake breadth |
| Increase active risk/aggressiveness | Higher expected active return if IR unchanged | Constraints do not reduce TC as active risk rises |
| Expand from market timing to stock selection | Potentially higher $BR$ | The manager actually has stock-level IC |

## Aggressiveness and Active Risk

Active risk, $\sigma_A$, is the size of the active bet. It appears in:

$$
E(R_A) = IR \times \sigma_A
$$

That creates a subtle exam distinction.

### Unconstrained portfolio

If the portfolio is unconstrained and the manager doubles active risk, expected active return doubles, but the [[Information Ratio]] is unchanged:

$$
IR = \frac{E(R_A)}{\sigma_A}
$$

Both numerator and denominator scale together.

### Constrained portfolio

If the portfolio is constrained, increasing active risk can make constraints bind harder. The manager may be forced into positions that are less aligned with optimal active weights, so $TC$ falls.

Then:

$$
IR = TC \times IC \times \sqrt{BR}
$$

If $TC$ falls, IR falls. This is why "more aggressive" is not automatically better.

## Manager Selection

When comparing active managers for the same benchmark, the best manager is generally the one with the highest expected [[Information Ratio]], not necessarily the highest expected active return.

Reason:

$$
SR_P^2 = SR_B^2 + IR^2
$$

For a given benchmark, the active manager with the highest IR creates the highest combined portfolio Sharpe ratio. The investor can then choose how much active risk to take.

If a constraint applies:

$$
SR_P^2 = SR_B^2 + TC^2(IR^*)^2
$$

So a brilliant but heavily constrained manager may rank below a slightly less skilled manager whose ideas can be implemented cleanly.

## Practical Limitations

The Fundamental Law is powerful because it forces every active strategy into a small number of drivers. Its weakness is that the inputs are easy to overstate.

| Limitation | Mechanism | Exam clue |
|---|---|---|
| Overestimated $IC$ | Managers confuse backtested signal quality with repeatable forecasting skill | "Proprietary model showed strong historical performance" |
| False breadth | Many decisions share the same underlying driver | All stock picks depend on one macro view |
| Cross-sectional dependence | Similar securities move together | Many stocks in one industry or many bonds with the same credit spread exposure |
| Time-series dependence | Sequential decisions are correlated | Monthly timing calls based on the same business-cycle forecast |
| Constraint drag | Active weights cannot match optimal active weights | Long-only, sector caps, turnover limits, tracking-error caps |
| Unstable skill | IC changes across regimes | Model works in expansion but fails in recession |

The shortest version: **garbage in, garbage out**. Bad IC and breadth estimates produce a precise but wrong IR.

## Exam Traps

| Trap | Correct response |
|---|---|
| Treat a 50% market-timing hit rate as positive skill | $IC = 2(0.50)-1 = 0$ |
| Count all monthly market calls as independent | Check for serial dependence; same macro view means lower true $BR$ |
| Count all securities as independent decisions | Check for common factors, industry clustering, and shared signals |
| Choose the manager with the highest active return | Compare [[Information Ratio]] if risk differs |
| Assume increasing active risk improves IR | It improves expected active return only if IR stays unchanged |
| Ignore $TC$ in long-only or constrained mandates | Constraints reduce implementation efficiency and IR |
| Use $BR$ instead of $\sqrt{BR}$ | Breadth enters as square root |
| Add Sharpe and IR directly | Use $SR_P^2 = SR_B^2 + IR^2$ |

## Memory Hook

> **Market timing asks "when?" Security selection asks "which?" FLAM asks "how good, how often, and how cleanly?"**

Or:

> **Timing = few big calls. Selection = many small calls. Breadth decides how skill scales.**

## Exam-Day Checklist

1. Identify the active strategy: timing, selection, sector rotation, or combination.
2. Compute $IC$ correctly. For binary timing calls, use $IC = 2p - 1$.
3. Estimate true $BR$, not headline count. Look for common drivers and serial dependence.
4. Check for constraints. If constrained, include $TC$.
5. If expected active return is requested, multiply $IR$ by $\sigma_A$.
6. If manager selection is requested, compare expected IR first.
7. If strategy change is described, map it to $IC$, $BR$, $TC$, and $\sigma_A$ before judging.

## Related Concepts

- [[Fundamental Law of Active Management]]
- [[Information Ratio]]
- [[Information Coefficient]]
- [[Breadth]]
- [[Transfer Coefficient]]
- [[Active Return]]
- [[Active Risk and Tracking Error]]
- [[Sharpe Ratio]]
- [[Analysis of Active Portfolio Management]]
- [[Using Multifactor Models]]
