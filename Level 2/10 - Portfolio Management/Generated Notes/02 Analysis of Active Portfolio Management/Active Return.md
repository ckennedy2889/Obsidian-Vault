---
title: Active Return
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, active-management, performance-evaluation]
aliases: [Active Return, R_A, Benchmark-Relative Return, Value Added]
---

# Active Return

## The Real-World Analogy

Imagine you and a friend each invest in two near-identical mutual funds tracking the S&P 500. At year-end, your fund returned 13.2%, your friend's returned 10.6%. The 2.6 percentage points by which you beat the index is your **active return** — the value your manager added (or subtracted) versus a passive alternative. It is *not* your total return, and it is *not* your return over cash. It is purely the gap between you and the benchmark you implicitly competed against.

The catch: that gap can come from skill, from luck, from style drift, or from quietly taking on more risk. Active return tells you the score of the game; it does not tell you whether the game was fair.

## Plain-English Definition

**Active return is how much a portfolio outperformed (or underperformed) its benchmark over a period.** It is the raw, unadjusted scoreboard number for an active manager, computed before considering how much risk was taken to earn it.

## CFA Definition

Active return ($R_A$) is the difference between a portfolio's return and the return on its designated benchmark:

$$
R_A = R_P - R_B
$$

It is the **numerator of the [[Information Ratio]]**, the foundational input to active-management attribution, and the quantity the [[Fundamental Law of Active Management]] tries to explain.

## Why It Matters

Every active manager charges fees for one promise: outperformance versus a passive alternative. Active return is the *direct measure of that promise being kept*. Without it:

- You cannot compute the [[Information Ratio]].
- You cannot do performance attribution (factor vs. selection).
- You cannot apply the [[Fundamental Law of Active Management]].
- You cannot judge whether a manager's fee is justified.

CFA tests it because students routinely confuse it with **alpha** (risk-adjusted) and **excess return** (over the risk-free rate). Getting these three straight is a near-guaranteed vignette point.

## Mechanism

**Rule.** $R_A = R_P - R_B$.

**Why the rule exists.** A manager who simply buys the benchmark earns $R_B$ by definition. So any return *above* $R_B$ is, by construction, the manager's contribution from active decisions — overweighting some securities, underweighting others, tilting toward factors, or rotating between sectors.

**Mechanism — where active return comes from.** Because portfolio weights and benchmark weights both sum to 100%, the difference in weights ($\Delta w_i = w_{P,i} - w_{B,i}$) must sum to zero. Every overweight is funded by an underweight. Active return is the dot product of those active weights with security returns:

$$
R_A = \sum_{i=1}^{N} \Delta w_i \cdot R_i
$$

This identity is powerful: it says active return depends only on **which securities you tilted toward and how those securities performed relative to the rest of the benchmark**. If you overweight winners and underweight losers, $R_A > 0$.

**Assumptions that make it meaningful.**

1. The benchmark is **investable, replicable, and representative** of the manager's opportunity set (a "valid benchmark").
2. The benchmark is **specified ex ante** (before performance is measured), not chosen retroactively to make the manager look good.
3. Returns are measured **consistently** (same currency, same fee treatment, same frequency).

**Failure modes.**

- *Wrong benchmark.* If a small-cap value manager is benchmarked to the S&P 500, observed $R_A$ will be polluted by **misfit return** — return earned simply because their style universe drifted relative to the broad market. Sound active return uses the manager's "normal portfolio" (true style benchmark), not a generic index.
- *Beta tilt masquerading as skill.* A manager who runs $\beta_P = 1.3$ during a bull market generates positive $R_A$ without picking a single good stock. Active return does not adjust for this; **alpha** does.
- *Compounding distortion.* Single-period $R_A$ values do **not** sum to multi-period $R_A$ because of compounding. Use geometric attribution to avoid the smoothing problem.

**Exam implication.** When a vignette gives you $R_P$ and a benchmark, the active return is mechanical — but the *interpretation* is where points are won. Always ask: is the benchmark valid? Is beta the same? Is this skill or style?

## Formula / Framework

### 1. Core formula

$$
R_A = R_P - R_B
$$

| Symbol | Meaning |
|---|---|
| $R_A$ | Active return over the period |
| $R_P$ | Portfolio total return |
| $R_B$ | Benchmark total return |

### 2. Active-weight decomposition

$$
R_A = \sum_{i=1}^{N} (w_{P,i} - w_{B,i}) \cdot R_i = \sum_{i=1}^{N} \Delta w_i \cdot R_i
$$

| Symbol | Meaning |
|---|---|
| $w_{P,i}$ | Portfolio weight in security $i$ |
| $w_{B,i}$ | Benchmark weight in security $i$ |
| $\Delta w_i$ | Active weight (overweight if positive) |
| $R_i$ | Return on security $i$ |

### 3. Geometric (compounding-safe) version

$$
G = \frac{1 + R_P}{1 + R_B} - 1
$$

This is the version to use when chaining multiple sub-periods, because geometric active returns multiply (compound) cleanly to the multi-period figure, while arithmetic active returns require Cariño/Menchero smoothing to reconcile.

### 4. Factor-model decomposition (Fundamental Factor Model)

$$
R_A \;=\; \underbrace{\sum_{k=1}^{K} (\beta_{P,k} - \beta_{B,k}) \cdot F_k}_{\text{Active Factor Return}} \;+\; \underbrace{\text{Active Specific Return}}_{\text{Security Selection}}
$$

| Symbol | Meaning |
|---|---|
| $\beta_{P,k}$ | Portfolio sensitivity to factor $k$ |
| $\beta_{B,k}$ | Benchmark sensitivity to factor $k$ |
| $F_k$ | Realized return on factor $k$ |
| Active Specific Return | Idiosyncratic, security-specific return not explained by factors |

This decomposition tells you **whether the manager added value through factor tilts (top-down) or stock picking (bottom-up)** — the two engines of active management. See [[Using Multifactor Models]].

### 5. Misfit decomposition (true vs. misfit return)

$$
R_A^{\text{vs broad index}} \;=\; \underbrace{(R_P - R_{\text{normal}})}_{\text{True active return}} \;+\; \underbrace{(R_{\text{normal}} - R_B)}_{\text{Misfit active return}}
$$

The "normal portfolio" is the manager's true style benchmark. Misfit return is style drift relative to the broad index, not skill.

## Worked Example

A balanced manager is benchmarked to a 60/40 stock-bond mix.

**Benchmark:**
- 60% stocks @ 15% return
- 40% bonds @ 4% return
- $R_B = 0.6(15\%) + 0.4(4\%) = 9.0\% + 1.6\% = 10.6\%$

**Portfolio (active manager):**
- 70% stocks @ 17% (better stocks + overweight equity)
- 30% bonds @ 4.2%
- $R_P = 0.7(17\%) + 0.3(4.2\%) = 11.9\% + 1.26\% = 13.16\%$

**Active return:**
$$
R_A = 13.16\% - 10.6\% = \mathbf{2.56\%}
$$

**Decompose using active weights ($\Delta w_{\text{stocks}} = +10\%$, $\Delta w_{\text{bonds}} = -10\%$):**

| Source | Calculation | Contribution |
|---|---|---|
| Allocation effect (stocks) | $+10\% \times (15\% - 10.6\%) = +10\% \times 4.4\%$ | $+0.44\%$ |
| Allocation effect (bonds) | $-10\% \times (4\% - 10.6\%) = -10\% \times (-6.6\%)$ | $+0.66\%$ |
| Selection (stocks) | $70\% \times (17\% - 15\%)$ | $+1.40\%$ |
| Selection (bonds) | $30\% \times (4.2\% - 4\%)$ | $+0.06\%$ |
| **Total** | | **+2.56%** |

The Brinson-style attribution sums to the same +2.56% — confirming the identity and showing that **70% of value-added came from stock picking, 30% from asset allocation.**

## Comparisons

| Concept | Formula | Numerator measures | Denominator | Adjusts for |
|---|---|---|---|---|
| **Active return** | $R_P - R_B$ | Excess over benchmark | — | Nothing |
| **Excess return** | $R_P - R_F$ | Excess over risk-free | — | Nothing |
| **Alpha (Jensen)** | $R_P - [R_F + \beta(R_M - R_F)]$ | Risk-adjusted skill | — | Beta (systematic risk) |
| **[[Information Ratio]]** | $(R_P - R_B)/\sigma_{R_A}$ | Active return per unit active risk | [[Active Risk and Tracking Error\|Tracking error]] | Benchmark-relative risk |
| **[[Sharpe Ratio]]** | $(R_P - R_F)/\sigma_P$ | Total return per unit total risk | Total volatility | Total risk |

Mnemonic: **AR vs B, ER vs F, IR scales AR, Sharpe scales ER.**

## Real-World / Vignette Scenarios

**Scenario 1 — Style misfit.** A small-cap value manager returns 8% while the Russell 2000 Value index returns 6% and the S&P 500 returns 12%. Versus the *correct* benchmark, $R_A = +2\%$ (skill). Versus the S&P 500, $R_A = -4\%$ (misleading — captures style headwind, not poor management). CFA loves this.

**Scenario 2 — Hidden beta bet.** A long-only US equity manager returns 18% vs. the S&P 500's 14% in a strong-up year. $R_A = +4\%$. Sounds great — until you learn $\beta_P = 1.3$. Expected return given that beta = $14\% \times 1.3 = 18.2\%$. **Alpha is essentially zero.** Active return overstated skill by ignoring systematic risk.

**Scenario 3 — Attribution.** A vignette gives you portfolio weights, benchmark weights, sector returns, and asks you to split $R_A$ into allocation, selection, and interaction. Use the active-weight identity above.

## Exam Traps

| Trap | Why it's wrong | Correct view |
|---|---|---|
| Active return = alpha | Active return ignores beta; alpha adjusts for it | A positive $R_A$ from a high-beta tilt has $\alpha = 0$ |
| Active return = excess return | Excess return is over $R_F$, not the benchmark | $R_A$ uses $R_B$; ER uses $R_F$ |
| Sub-period $R_A$ values sum to total | Compounding breaks the sum | Use geometric attribution or apply Cariño/Menchero smoothing |
| Any positive $R_A$ proves skill | Could be factor tilts, style drift, or pure luck | Decompose into factor return + selection; check IR and t-stat |
| Use any convenient benchmark | Wrong benchmark creates misfit return | Use the manager's normal portfolio (style-matched, ex-ante, investable) |
| $R_A$ is risk-adjusted | It is not; only [[Information Ratio]] / alpha adjust | Always pair $R_A$ with a risk measure |

## Memory Hook

> **"AR = P minus B. Skill needs more."**

Active return is the *raw scoreboard*. To prove **skill** you must add a risk lens — either divide by tracking error to get IR, or subtract the beta-explained part to get alpha.

A second hook: **"Same letters, different denominator."** Active return is the numerator shared by both attribution analysis and the Information Ratio. Whenever you compute $R_P - R_B$, ask yourself "where does this go next — into IR, into Brinson, or into alpha?"

## Exam-Day Checklist

When a vignette mentions portfolio and benchmark returns, ask:

1. **Is this $R_A$ or excess return?** Confirm whether the comparison is to a benchmark or to $R_F$.
2. **Is the benchmark valid?** Investable, replicable, ex-ante, style-appropriate? If not, suspect misfit return.
3. **What is the portfolio's beta?** A high-beta tilt can manufacture $R_A$ without skill.
4. **Are you being asked for arithmetic or geometric $R_A$?** Multi-period questions usually want geometric.
5. **Does the question want decomposition?** Identify whether allocation, selection, factor, or specific return is the target.
6. **Is the next step IR or alpha?** Active return rarely stands alone on the exam.

## Related Concepts

- [[Active Risk and Tracking Error]]
- [[Information Ratio]]
- [[Fundamental Law of Active Management]]
- [[Analysis of Active Portfolio Management]]
- [[Using Multifactor Models]]
- [[Fama-French Model]]
- [[Sharpe Ratio]]
- [[Treynor Ratio]]
