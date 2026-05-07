# Taylor rule

**Program:** CFA® Program
**Level:** Level II / Level III

## Definition

A rule linking a central bank's target short-term [[Policy rate]] to the economy's inflation gap and output gap.

In plain English, the Taylor rule is a central bank's thermostat. If the economy is running too hot, because [[Inflation]] is above target or actual output is above [[Potential GDP]], the rule recommends a higher policy rate. If the economy is running too cold, because inflation is below target or output is below potential, the rule recommends a lower policy rate.

## Formula

The CFA-style version is:

$$
\boxed{
pr_t = r_t + \pi_t + 0.5(\pi_t - \pi_t^*) + 0.5(Y_t - Y_t^*)
}
$$

| Term | Meaning |
|---|---|
| $pr_t$ | Recommended nominal [[Policy rate]] |
| $r_t$ | [[Neutral rate of interest]], stated as a real rate |
| $\pi_t$ | Current inflation |
| $\pi_t^*$ | Target inflation |
| $\pi_t - \pi_t^*$ | Inflation gap |
| $Y_t - Y_t^*$ | [[Output gap]]: actual output minus potential output |

The first two terms, $r_t + \pi_t$, give the neutral nominal policy rate. That is the rate that should be neither stimulative nor restrictive if inflation is on target and output is at potential.

The final two terms adjust that neutral rate:

| Condition | Taylor rule effect | Policy meaning |
|---|---|---|
| Inflation above target | Raises the policy rate | Tighten |
| Inflation below target | Lowers the policy rate | Ease |
| Positive output gap | Raises the policy rate | Cool overheating |
| Negative output gap | Lowers the policy rate | Stimulate weak demand |

## Intuition

The Taylor rule exists because central banks need a disciplined way to translate macroeconomic conditions into an interest-rate decision.

If inflation is above target, money is losing purchasing power too quickly. Raising the policy rate makes borrowing more expensive, slows credit growth, cools demand, and reduces inflation pressure.

If actual output is above potential output, the economy is operating beyond sustainable capacity. Firms face capacity constraints, labor markets tighten, wages rise, and inflation pressure tends to build. A higher policy rate leans against that overheating.

If the gaps are negative, the logic reverses. Below-target inflation or a negative output gap suggests slack in the economy, so the Taylor rule recommends a lower policy rate.

## Worked Example

Suppose:

| Input | Value |
|---|---:|
| Neutral real rate, $r_t$ | 2% |
| Current inflation, $\pi_t$ | 3% |
| Target inflation, $\pi_t^*$ | 2% |
| Output gap, $Y_t - Y_t^*$ | +2% |

Then:

$$
pr_t = 2 + 3 + 0.5(3 - 2) + 0.5(2)
$$

$$
pr_t = 2 + 3 + 0.5 + 1 = 6.5\%
$$

The Taylor rule recommends a 6.5% nominal policy rate.

The neutral nominal rate is $2\% + 3\% = 5\%$, but inflation is above target and the economy has a positive output gap, so the rule adds another 1.5 percentage points.

## Exam Traps

| Trap | Correction |
|---|---|
| Treating the Taylor rule output as a real rate | The rule recommends a nominal policy rate. |
| Forgetting the neutral rate already includes the real-rate base | Start with $r_t + \pi_t$, then adjust for the gaps. |
| Misreading the output gap | If actual output is below potential output, the gap is negative and lowers the recommended rate. |
| Assuming high GDP growth always means a positive output gap | Fast growth can still occur while the economy remains below potential after a recession. |
| Treating the rule as mechanical truth | The neutral real rate and potential GDP are estimated, not directly observable. |

## Memory Hook

Taylor = target rate = thermostat.

Inflation too hot or output too hot? Raise the rate. Economy too cold? Lower the rate.

**Tags:** #CFA #glossary
