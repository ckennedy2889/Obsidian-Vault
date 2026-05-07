---
title: Fundamental Law of Active Management
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, active-management, fundamental-law, IC, breadth, transfer-coefficient]
aliases: [FLAM, Fundamental Law, Grinold's Law, IR = IC sqrt(BR)]
---

# Fundamental Law of Active Management

## The Real-World Analogy

Picture a professional poker player. Their long-run winnings depend on **two** things, not one:

1. **How accurate is their read on each hand?** (signal quality)
2. **How many hands do they get to play per night?** (number of independent bets)

A genius who reads opponents 80% correctly but only plays 5 hands per night will *lose* to a competent player who reads opponents 53% correctly across 1,000 hands. The math of edges-times-frequency is brutal: small skill, multiplied across many independent decisions, compounds into real performance.

That is the entire intuition behind the **Fundamental Law of Active Management** (FLAM, sometimes called **Grinold's Law**). A manager's risk-adjusted skill (Information Ratio) is the product of *signal quality* (IC) and *the square root of how many independent bets* they take per year (BR). And if constraints prevent them from translating their bets into actual portfolio weights cleanly, that gets penalized too (TC).

## Plain-English Definition

> **The Fundamental Law says a manager's risk-adjusted active skill = (their forecasting accuracy) × (how many independent decisions they make) × (how cleanly those decisions become real positions).**

Mathematically:

$$
IR \;=\; TC \cdot IC \cdot \sqrt{BR}
$$

If the manager has no constraints (no shorting limits, no sector caps, no max position sizes), $TC = 1$ and the law collapses to the **basic form**:

$$
IR^{*} \;=\; IC \cdot \sqrt{BR}
$$

## CFA Definition

The Fundamental Law of Active Management decomposes a manager's expected risk-adjusted active performance into three multiplicative components:

$$
\boxed{\,IR \;=\; TC \cdot IC \cdot \sqrt{BR}\,}
\qquad\text{(full law)}
$$

$$
E(R_A) \;=\; TC \cdot IC \cdot \sqrt{BR} \cdot \sigma_A
\qquad\text{(expected active return form)}
$$

| Symbol | Meaning |
|---|---|
| $IR$ | **Information Ratio** — active return per unit of active risk |
| $IC$ | **Information Coefficient** — risk-weighted correlation between forecasted and *realized* active returns (signal quality, between −1 and 1; usually ~0.02–0.10 for skilled managers) |
| $BR$ | **Breadth** — number of **independent** investment decisions per year |
| $TC$ | **Transfer Coefficient** — risk-weighted correlation between forecasted active returns and *actual* active weights (between 0 and 1; = 1 if unconstrained) |
| $\sigma_A$ | **Active risk** (tracking error) — std. dev. of active returns |
| $E(R_A)$ | **Expected active return** |

See: [[Information Ratio]] · [[Information Coefficient]] · [[Breadth]] · [[Transfer Coefficient]] · [[Active Risk]] · [[Tracking Error]]

## Why It Matters

CFA tests the FLAM because it is the **single most important framework in active management**. It:

1. **Decomposes alpha into causes.** A poor IR is either bad signal (low IC), too few independent bets (low BR), or implementation friction (low TC). The law tells you which.
2. **Quantifies the cost of constraints.** Long-only mandates, sector limits, and turnover caps all reduce TC below 1. The law shows exactly how many basis points of IR a constraint costs.
3. **Connects to the Sharpe ratio.** Because $SR_P^2 = SR_B^2 + IR^2$, maximizing IR maximizes total portfolio Sharpe — and the law tells you how to maximize IR.
4. **Disciplines breadth claims.** Managers love to claim "we cover 1,000 stocks." Breadth requires *independent* decisions; sector rotation across 10 sectors gives BR = 10, not 1,000. The law forces honesty.

## Mechanism

Walk the explanation ladder for each component:

| Step | What it says |
|---|---|
| **Rule** | $IR = TC \cdot IC \cdot \sqrt{BR}$ |
| **Why the rule exists** | Skill alone doesn't generate IR — it must be applied many times *independently*, and translated into real weights without being blocked by constraints |
| **Mechanism** | IC measures the per-bet edge; $\sqrt{BR}$ scales it by the number of independent bets (Central Limit Theorem); TC scales by implementation efficiency |
| **Assumptions** | Bets are truly independent; IC is stable; the active risk $\sigma_A$ is taken at the optimal level; manager isn't gaming forecasts |
| **Failure modes** | Bets that look independent are correlated (e.g., 50 oil stocks → BR = 1); IC drifts down over time; constraints tighten and TC collapses |
| **Exam implication** | If a vignette describes constraints, use the **full** law; otherwise the basic form. If breadth is overstated, recompute |

### Why $\sqrt{BR}$ and not $BR$?

Because the **standard error** of an average shrinks with $\sqrt{n}$, not $n$. Adding more independent bets *averages out* idiosyncratic noise faster than it adds expected return — but only at $\sqrt{BR}$ rate. Doubling breadth multiplies IR by ≈1.41, not by 2.

### What makes a "decision" independent?

Two decisions are independent if knowing the outcome of one tells you *nothing* about the outcome of the other. Examples:

- Picking 50 oil stocks → essentially **one** macro bet on oil, repeated. BR ≈ 1.
- Rotating across 10 sectors based on macro views → BR = 10.
- 50 single-stock alpha forecasts each driven by a *separate* idiosyncratic catalyst → BR = 50.
- Picking 200 stocks where forecasts are based on a single common factor → BR ≈ 1.

The CFA exam tests this trap directly.

## Formula / Framework

### The full family of FLAM equations

| Concept | Unconstrained ($TC = 1$) | Constrained ($TC < 1$) |
|---|---|---|
| Information Ratio | $IR^{*} = IC \sqrt{BR}$ | $IR = TC \cdot IC \sqrt{BR}$ |
| Expected active return | $E(R_A) = IC \sqrt{BR} \cdot \sigma_A$ | $E(R_A) = TC \cdot IC \sqrt{BR} \cdot \sigma_A$ |
| Total portfolio Sharpe² | $SR_P^2 = SR_B^2 + (IR^*)^2$ | $SR_C^2 = SR_B^2 + TC^2 (IR^*)^2$ |
| Optimal active risk | $\sigma_A^{*} = \dfrac{IR^*}{SR_B}\sigma_B$ | $\sigma_A = TC \cdot \dfrac{IR^*}{SR_B}\sigma_B$ |

### Key identities to memorize

$$
\boxed{\,SR_P^{\,2} = SR_B^{\,2} + IR^{\,2}\,}
\qquad
\boxed{\,\sigma_A^{*} = \frac{IR}{SR_B}\sigma_B\,}
$$

The first says **squared Sharpe ratios add**; the second tells you the **right amount of active risk** to take.

## Worked Example

A long-only equity manager:

- Information Coefficient $IC = 0.05$ (typical "good" forecaster)
- Breadth $BR = 144$ independent decisions per year
- Portfolio is **unconstrained** (assume long-short, no sector caps) → $TC = 1$
- Benchmark Sharpe ratio $SR_B = 0.40$
- Benchmark volatility $\sigma_B = 12\%$

**Step 1 — Compute the basic IR.**

$$
IR^{*} = IC \cdot \sqrt{BR} = 0.05 \times \sqrt{144} = 0.05 \times 12 = \boxed{0.60}
$$

**Step 2 — Compute the optimal active risk.**

$$
\sigma_A^{*} = \frac{IR^*}{SR_B}\,\sigma_B = \frac{0.60}{0.40}\times 12\% = 1.5 \times 12\% = \boxed{18\%}
$$

**Step 3 — Compute the expected active return at that optimal risk.**

$$
E(R_A) = IR^{*} \times \sigma_A^{*} = 0.60 \times 18\% = \boxed{10.8\%}
$$

**Step 4 — Combined portfolio Sharpe.**

$$
SR_P^{\,2} = SR_B^{\,2} + (IR^*)^2 = 0.40^2 + 0.60^2 = 0.16 + 0.36 = 0.52
$$

$$
SR_P = \sqrt{0.52} \approx \boxed{0.721}
$$

Combining a benchmark with $SR_B = 0.40$ and an active overlay with $IR = 0.60$ produces a total portfolio with Sharpe ≈ 0.72.

### Now add a constraint

Suppose a no-shorting rule and sector limits drop $TC$ to 0.5:

$$
IR_\text{constrained} = TC \cdot IC \cdot \sqrt{BR} = 0.5 \times 0.05 \times 12 = 0.30
$$

The constraint **halves** the IR. Expected active return at the constrained-optimal risk ($\sigma_A = TC \cdot 18\% = 9\%$) drops to $0.30 \times 9\% = 2.7\%$. The combined Sharpe falls to $\sqrt{0.16 + 0.09} = 0.50$. **Constraints are expensive.**

### Breadth-trap variant

The same manager claims "I cover 500 stocks." But all 500 forecasts are driven by a single macro signal (interest-rate direction). True breadth is **1**. Then $IR = 0.5 \times 0.05 \times \sqrt{1} = 0.025$ — essentially no skill. The exam will test recognition of this collapse.

## Comparisons

### Basic vs Full Law

| Aspect | **Basic ($IR^* = IC\sqrt{BR}$)** | **Full ($IR = TC \cdot IC \sqrt{BR}$)** |
|---|---|---|
| Assumption | No constraints on positions | Constraints exist (long-only, sector caps, etc.) |
| TC | Implicitly 1 | Less than 1 |
| Use when | Hedge fund, market-neutral, unconstrained | Long-only mutual funds, constrained mandates |

### Components — what changes IR

| Driver | Effect on IR | How to improve |
|---|---|---|
| Higher IC (better signal) | Linear improvement | Better research, better data, better models |
| Higher BR (more independent bets) | Square-root improvement | Cover more independent themes, not more correlated names |
| Higher TC (less constraint friction) | Linear improvement | Loosen mandate restrictions, allow shorts/derivatives |
| Wrong active risk level | None (IR is risk-adjusted) | Use $\sigma_A^* = (IR/SR_B)\sigma_B$ to maximize portfolio Sharpe |

### IR vs Sharpe — the tested asymmetry

| Question | Answer |
|---|---|
| Does adding cash change IR? | **Yes** |
| Does adding cash change Sharpe? | **No** |
| Does scaling up active weights (aggressiveness) change IR? | **No** |
| Does scaling up aggressiveness change Sharpe? | **Yes** |

## Real-World / Vignette Scenarios

**Scenario 1 — Constraint cost.** A vignette compares a long-short hedge fund ($TC = 1$, $IC = 0.04$, $BR = 100$) to a long-only fund ($TC = 0.5$, same IC and BR). Compute IRs:
- Hedge fund: $0.04 \times 10 = 0.40$
- Long-only: $0.5 \times 0.04 \times 10 = 0.20$

Long-only delivers half the IR — the constraint cost is 20 bps of IR per unit risk.

**Scenario 2 — False breadth.** A PM claims to make 500 independent stock decisions per year. The vignette reveals all 500 are based on one macro top-down view of energy prices. Recompute breadth → BR = 1. The IR collapses from claimed $0.05\sqrt{500} = 1.12$ to actual $0.05$. The vignette tests recognition of this gap.

**Scenario 3 — Rank managers.** A table gives three managers' (IC, BR, TC). Compute IR for each; rank them. The highest IR will (per $SR_P^2 = SR_B^2 + IR^2$) deliver the highest combined portfolio Sharpe.

**Scenario 4 — Right-size active risk.** A vignette gives the manager's IR and benchmark stats and asks how much tracking error to take. Use $\sigma_A^* = (IR/SR_B)\sigma_B$.

## Exam Traps

| Trap | Reality |
|---|---|
| Use basic law when constraints exist | Use **full** law: $IR = TC \cdot IC \sqrt{BR}$ |
| Set $BR$ = number of stocks in coverage | $BR$ = number of **independent** decisions; correlated stocks share a single decision |
| Multiply by $BR$ instead of $\sqrt{BR}$ | The law uses **square root**, courtesy of the CLT |
| Treat IR as additive across portfolios | $SR_P^2 = SR_B^2 + IR^2$ — square them, then sum |
| Confuse IC with IR | IC is **per-bet skill** (correlation); IR is **portfolio-level risk-adjusted return** |
| Ignore TC when long-only mandate is mentioned | Long-only ⇒ $TC < 1$ — *use the penalty* |
| Forget cash/leverage affects IR but not Sharpe | And aggressiveness affects Sharpe but not IR |
| Use forecast IC when realized IC is asked (or vice versa) | IC is realized *correlation* between past forecasts and outcomes — usually ex-post |
| Believe doubling breadth doubles IR | Doubling BR multiplies IR by $\sqrt{2} \approx 1.41$ |

## Memory Hook

> **"Skill × Reps × Reach → Risk-adjusted Win"**
>
> $$IR = \underbrace{TC}_{\text{reach}} \cdot \underbrace{IC}_{\text{skill}} \cdot \underbrace{\sqrt{BR}}_{\text{reps}}$$

Or:

> **"Smart, Often, Cleanly."** — IC says you're smart, $\sqrt{BR}$ says you do it often, TC says you do it cleanly.

Bridging mnemonic to Sharpe: **"Squares add."** — $SR_P^2 = SR_B^2 + IR^2$.

## Exam-Day Checklist

When a vignette involves the Fundamental Law:

1. Are there **constraints** (long-only, sector caps, leverage limits)? → Use the **full** law with $TC < 1$.
2. Is the breadth claim plausible? Are the decisions **truly independent** or driven by a common factor? Recompute BR if not.
3. Is the question asking for **expected active return**? Use $E(R_A) = IR \times \sigma_A$ at the optimal risk level.
4. Is the question asking for **optimal active risk**? Use $\sigma_A^* = (IR/SR_B)\sigma_B$ (or with $TC$ for constrained).
5. Is the question asking for **combined Sharpe**? Use $SR_P^2 = SR_B^2 + IR^2$ (or $TC^2 \cdot IR^{*\,2}$ for constrained).
6. Is it the **cash/leverage vs aggressiveness** asymmetry? IR is changed by cash/leverage; Sharpe is changed by aggressiveness.
7. Are the inputs **ex ante** (forecasts) or **ex post** (realized)? Match the question's frame.
8. Are returns/risks **annualized**? Required for the formulas.

## Related Concepts

- [[Information Ratio]]
- [[Information Coefficient]]
- [[Breadth]]
- [[Transfer Coefficient]]
- [[Active Return]]
- [[Active Risk]]
- [[Tracking Error]]
- [[Sharpe Ratio]]
- [[Active Factor Risk]]
- [[Active Specific Risk]]
- [[Analysis of Active Portfolio Management]]
- [[Using Multifactor Models]]
