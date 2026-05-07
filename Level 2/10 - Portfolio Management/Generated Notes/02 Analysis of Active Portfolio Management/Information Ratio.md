---
title: Information Ratio
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, active-management, performance, risk-adjusted-return]
aliases: [IR, Information Ratio, Appraisal Ratio (related)]
---

# Information Ratio

## The Real-World Analogy

Imagine you hire two basketball coaches. Both promise to beat the average team in the league. Coach A wins by 2 points per game, but his game-to-game scoring swings are wild — sometimes +30, sometimes -25. Coach B also wins by 2 points per game, but his swings are tiny — every game is a +1 to +4 nudge above the league average.

If you have to bet your career on one coach next season, which is more *skillful*? Coach B. Same edge over the benchmark, far less noise around the edge. That ratio — *edge per unit of noise around the edge* — is exactly what the **Information Ratio** is.

A manager who beats the index by 2% with 1% tracking error is **vastly more skilled** than one who beats it by 4% with 8% tracking error, even though the second has a bigger raw outperformance.

## Plain-English Definition

> **Information Ratio = (active return) / (active risk).**

Active return is how much you beat the benchmark by. Active risk (a.k.a. tracking error) is how much your active return *bounces around* over time. The IR tells you how much "value-added per unit of bet placed against the benchmark" the manager is delivering.

It is the **single most important number** for ranking active managers measured against the *same* benchmark. Higher IR = better skill, period.

## CFA Definition

The Information Ratio is the mean active return divided by the standard deviation of active return:

$$
IR \;=\; \frac{R_P - R_B}{\sigma_{(R_P - R_B)}} \;=\; \frac{\bar{R}_A}{\sigma_{R_A}}
$$

where $R_P$ is portfolio return, $R_B$ is benchmark return, $R_A = R_P - R_B$ is active return, and $\sigma_{R_A}$ is **tracking error** (the standard deviation of $R_A$, also called active risk or tracking risk).

See: [[Active Return]] · [[Active Risk]] · [[Tracking Error]] · [[Sharpe Ratio]] · [[Fundamental Law of Active Management]]

## Why It Matters

CFA tests IR everywhere because it is the **central ranking statistic** in active management:

1. It removes the "lucky / aggressive" bias of just looking at active return — a manager can goose active return by tilting harder; IR doesn't reward that (see Section 5 below).
2. It plugs directly into the **Fundamental Law of Active Management**: $IR^* = IC \times \sqrt{BR}$, decomposing skill into *signal quality* and *number of independent bets*.
3. It tells the investor exactly how to size the active position to maximize the **total portfolio Sharpe ratio**: $SR_P^2 = SR_B^2 + IR^2$.

If you understand IR deeply, you understand 70% of Module 2 (Analysis of Active Portfolio Management).

## Mechanism

**Rule:** Rank managers by IR, not by raw active return.

**Why the rule exists:** Two managers can both produce 3% active return per year. One does it with 2% tracking error (IR = 1.5 — exceptional), the other with 8% tracking error (IR = 0.375 — mediocre). The first has *real signal*; the second is just throwing darts and got a couple to land.

**Mechanism:** Active return $R_A$ is a noisy realization of a manager's true expected edge plus random luck. The variance of $R_A$ across periods, $\sigma_{R_A}^2$, is a proxy for how much of the realized return is luck-driven. Dividing by $\sigma_{R_A}$ standardizes the active return per unit of "bet size against the benchmark," which is the only fair way to compare managers using the same benchmark.

**Assumptions that make IR meaningful:**

- Active returns are roughly **stationary** (the skill and the noise process are stable).
- Managers are evaluated against the **same benchmark** — IRs are not comparable across different benchmarks (a small-cap manager and a global-bond manager cannot be ranked by IR head-to-head).
- Active returns are approximately normally distributed (so $\sigma_{R_A}$ captures most of the relevant risk).

**Failure modes:**

- **Benchmark mismatch:** if the benchmark is poor (high tracking error baked in just from style drift), IR misleads.
- **Short history:** with only 12–24 monthly returns, IR estimates are extremely noisy.
- **Non-normal active returns:** if the strategy has fat-tail blow-ups (e.g., short-volatility), the standard deviation understates risk and IR overstates skill.

**Exam implication:** When a vignette says "Manager A had higher active return; Manager B had higher IR — who do you recommend?" — pick **B**, every time, *provided* the benchmark is appropriate.

## Formula / Framework

### Core Formula

$$
\boxed{\,IR \;=\; \frac{\bar{R}_A}{\sigma_{R_A}} \;=\; \frac{\bar{R}_P - \bar{R}_B}{\sigma_{(R_P - R_B)}}\,}
$$

| Symbol | Meaning |
|---|---|
| $\bar{R}_P$ | Mean portfolio return over the evaluation period |
| $\bar{R}_B$ | Mean benchmark return over the same period |
| $\bar{R}_A = \bar{R}_P - \bar{R}_B$ | **Active return** (a.k.a. value added) |
| $\sigma_{R_A}$ | **Active risk** = standard deviation of period-by-period active returns ($\equiv$ tracking error) |

### Ex Ante vs Ex Post

| Form | Numerator | Denominator | Use |
|---|---|---|---|
| **Ex ante** (forward-looking) | $E(R_A)$ — manager's *expected* active return | $\sigma_A$ — *expected* tracking error | Portfolio construction; sizing the active bet |
| **Ex post** (realized) | Mean of *realized* $R_A$ | Sample standard deviation of realized $R_A$ | Performance evaluation after the fact |

### Connection to Sharpe — The Optimal Sizing Result

For an **unconstrained** portfolio combining benchmark exposure plus the active portfolio:

$$
\boxed{\,SR_P^{\,2} \;=\; SR_B^{\,2} + IR^{\,2}\,}
$$

This says: total portfolio Sharpe squared = benchmark Sharpe squared **plus** information ratio squared. The active portfolio with the **highest IR** delivers the **highest combined Sharpe ratio**, regardless of the benchmark. That is why IR is *the* objective function in active management.

The **optimal active risk** (level of tracking error to take) is:

$$
\sigma_{R_A}^{*} \;=\; \frac{IR}{SR_B}\,\sigma_{R_B}
$$

For **constrained** portfolios (no shorting, sector caps, leverage limits), multiply by the **Transfer Coefficient** $TC \in [0,1]$:

$$
SR_P^{\,2} \;=\; SR_B^{\,2} + (TC)^2 (IR^*)^2
$$

### Connection to the Fundamental Law

$$
IR^{*} \;=\; IC \times \sqrt{BR} \quad\text{(unconstrained)}
$$
$$
IR \;=\; TC \times IC \times \sqrt{BR} \quad\text{(constrained — full law)}
$$

| Symbol | Meaning |
|---|---|
| $IC$ | **Information Coefficient** — risk-weighted correlation between forecasted and realized active returns. Skill of the signal. |
| $BR$ | **Breadth** — number of *independent* investment decisions per year |
| $TC$ | **Transfer Coefficient** — fidelity with which forecasts get translated into actual active weights (1.0 if unconstrained) |

See: [[Fundamental Law of Active Management]] · [[Information Coefficient]] · [[Breadth]] · [[Transfer Coefficient]]

## Worked Example

A pension consultant is evaluating an active US large-cap manager benchmarked to the S&P 500.

**Inputs:**
- Benchmark Sharpe ratio $SR_B = 0.46$
- Benchmark volatility $\sigma_{R_B} = 10.8\%$
- The combined optimal portfolio (benchmark + active) achieves $SR_P = 0.61$.

**Step 1 — Back out IR from the Sharpe relation.**

$$
SR_P^2 = SR_B^2 + IR^2
$$
$$
(0.61)^2 = (0.46)^2 + IR^2
$$
$$
0.3721 = 0.2116 + IR^2 \;\Rightarrow\; IR^2 = 0.1605
$$
$$
\boxed{IR = \sqrt{0.1605} \approx 0.40}
$$

An IR of 0.40 is "good" by industry rule-of-thumb (>0.50 is "very good"; >0.75 is "exceptional"; 1.0+ is rare).

**Step 2 — Optimal active risk to take.**

$$
\sigma_{R_A}^{*} = \frac{IR}{SR_B}\,\sigma_{R_B} = \frac{0.40}{0.46}\times 10.8\% \approx 9.39\%
$$

**Step 3 — Implied expected active return.**

$$
E(R_A) = IR \times \sigma_{R_A}^{*} = 0.40 \times 9.39\% \approx 3.76\%
$$

**Step 4 — Cross-check via the Fundamental Law.**

If the manager's $IC = 0.20$ and they make $BR = 4$ independent decisions per year:

$$
IR^* = IC \times \sqrt{BR} = 0.20 \times \sqrt{4} = 0.40 \;\checkmark
$$

The numbers tie out — the manager's signal quality and breadth justify exactly the IR observed.

## Comparisons

### IR vs Sharpe Ratio

| Property | Sharpe Ratio | Information Ratio |
|---|---|---|
| Numerator | $R_P - R_F$ (excess over **risk-free**) | $R_P - R_B$ (excess over **benchmark**) |
| Denominator | Total volatility $\sigma_P$ | Active risk $\sigma_{R_A}$ |
| Affected by **adding cash / leverage**? | **No** | **Yes** |
| Affected by **aggressiveness of active weights**? | Yes | **No** |
| What it measures | Absolute reward per total risk | Relative reward per active risk |
| When to use | Comparing portfolios with different risk levels overall | Comparing active managers vs the **same** benchmark |

The asymmetry on the last two rows is tested constantly. **Memorize it.**

### IR vs Treynor & Jensen's Alpha

| Measure | Numerator | Denominator | Notes |
|---|---|---|---|
| Sharpe | $R_P - R_F$ | $\sigma_P$ | Total risk |
| Treynor | $R_P - R_F$ | $\beta_P$ | Systematic risk only |
| Jensen's $\alpha$ | $R_P - [R_F + \beta_P(R_M - R_F)]$ | — (raw return number) | CAPM-adjusted excess |
| **Information Ratio** | $R_P - R_B$ | $\sigma_{R_A}$ | **Benchmark-relative**, not CAPM-relative |

Jensen's alpha and IR can both be called "appraisal" measures, but IR uses *benchmark* deviation, not *CAPM* deviation.

## Real-World / Vignette Scenarios

**Scenario 1 — Manager Beauty Contest.** Three small-cap managers benchmarked to the Russell 2000:

| Manager | Active return | Tracking error | IR |
|---|---|---|---|
| A | 4.0% | 8.0% | 0.50 |
| B | 2.5% | 4.0% | 0.625 |
| C | 6.0% | 15.0% | 0.40 |

Pick **B**. Highest IR ⇒ best added Sharpe to the total portfolio. C looks tempting (highest active return) but is a low-skill, high-aggressiveness story.

**Scenario 2 — Constraint Bites.** A manager with $IC = 0.05$, $BR = 100$, and a no-shorting constraint that gives $TC = 0.6$:

$$
IR = 0.6 \times 0.05 \times \sqrt{100} = 0.30
$$

Without the short-selling constraint ($TC=1$), $IR^* = 0.50$. The constraint costs the client 0.20 of IR — a vignette may ask you to quantify this.

**Scenario 3 — Wrong Use of Cash.** A manager with strong stock-picking IR of 0.7 holds 30% in cash to "reduce risk." Cash dilutes both active return and active risk *non-proportionally* (cash has zero benchmark-relative tracking) — IR falls. Sharpe is unchanged. Vignette will test which ratio moves.

## Exam Traps

| Trap | Reality |
|---|---|
| Pick the manager with highest active return | Pick highest **IR** — same edge per unit of risk |
| Use IR to compare a small-cap fund vs an EM debt fund | IR is only comparable across managers with the **same benchmark** |
| Add Sharpe and IR linearly to get total Sharpe | Square them: $SR_P^2 = SR_B^2 + IR^2$ |
| Claim cash/leverage doesn't affect IR (it doesn't affect Sharpe) | Cash/leverage **does** affect IR; it does **not** affect Sharpe |
| Claim aggressiveness changes IR | Scaling all active weights by a constant leaves IR **unchanged** (numerator and denominator scale together) |
| Use $IR = IC \sqrt{BR}$ when constraints exist | Use the **full law** $IR = TC \cdot IC \cdot \sqrt{BR}$ |
| Treat 500 stocks in the universe as $BR = 500$ | $BR$ = number of **independent** decisions; sector rotation across 10 sectors gives $BR = 10$ |
| Expect IR to stay stable with a 12-month sample | IR estimates are noisy — need 5+ years of monthly data for reliable estimates |

## Memory Hook

> **"IR = active return ÷ active risk = skill per unit of bet."**

And the chain to remember the law and the Sharpe link:

> **"IR squared adds to Sharpe squared. IR equals IC times root breadth. Cash kills IR but not Sharpe; aggressiveness kills Sharpe but not IR."**

Mnemonic for the asymmetry: **CASH-IR / AGG-SR** — *the one you'd expect doesn't matter; the other one does.*

## Exam-Day Checklist

When you see a vignette involving IR, ask yourself:

1. Is the benchmark **appropriate**? (If not, IR is meaningless.)
2. Is this **ex ante** or **ex post**?
3. Is the portfolio **constrained**? (If yes, use $TC \cdot IC \cdot \sqrt{BR}$.)
4. Are you being asked to **rank managers** (use IR) or evaluate a **standalone portfolio** (use Sharpe)?
5. Is the question testing the **cash / leverage** asymmetry vs Sharpe?
6. Is breadth the number of **stocks** (wrong) or **independent decisions** (right)?
7. If asked for the **optimal active risk**, use $\sigma_{R_A}^* = (IR / SR_B)\,\sigma_{R_B}$.
8. If asked for the **maximum combined Sharpe**, use $SR_P^2 = SR_B^2 + IR^2$ (or $(TC \cdot IR^*)^2$).

## Related Concepts

- [[Active Return]]
- [[Active Risk]]
- [[Tracking Error]]
- [[Sharpe Ratio]]
- [[Fundamental Law of Active Management]]
- [[Information Coefficient]]
- [[Breadth]]
- [[Transfer Coefficient]]
- [[Active Factor Risk]]
- [[Active Specific Risk]]
- [[Jensen's Alpha]]
- [[Treynor Ratio]]
- [[Sortino Ratio]]
- [[Analysis of Active Portfolio Management]]
