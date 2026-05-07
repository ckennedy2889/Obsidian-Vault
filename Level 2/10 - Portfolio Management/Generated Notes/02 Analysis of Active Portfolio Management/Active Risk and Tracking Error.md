---
title: Active Risk and Tracking Error
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, active-management, risk]
aliases: [Active Risk, Tracking Error, Tracking Risk, σ_RA, sigma_A]
---

# Active Risk and Tracking Error

## The Real-World Analogy

Picture a marathon runner who is paid to stay within sight of the lead pacer at every mile. Their **average gap** to the pacer over the race is their *active return*. But the **mile-by-mile variability** of that gap — sometimes 50 metres ahead, sometimes 80 metres behind — is their *active risk*.

A runner who finishes 30 seconds ahead by sprinting and stalling unpredictably is *not* the same as one who finishes 30 seconds ahead while never drifting more than 5 metres from the pacer. Same active return, very different active risk. The second runner has the higher **Information Ratio** — better skill per unit of deviation.

## Plain-English Definition

**Active risk (a.k.a. tracking error or tracking risk) is the volatility of a portfolio's returns relative to its benchmark.** It is the standard deviation of the period-by-period [[Active Return|active returns]]. It tells you how *consistently* a manager hugs or strays from the benchmark — high values mean wide swings around the benchmark, low values mean tight tracking.

## CFA Definition

Active risk is the standard deviation of active returns:

$$
\sigma_{R_A} \;=\; \sqrt{\operatorname{Var}(R_P - R_B)}
$$

In CFA texts, "tracking error," "tracking risk," and "active risk" are used interchangeably to mean this quantity. (Older sloppy usage sometimes called the single-period $R_P - R_B$ a "tracking error" — beware.)

It is the **denominator of the [[Information Ratio]]** and the **scaling lever** in the [[Fundamental Law of Active Management]].

## Why It Matters

Active return without active risk is like a casino payout without the bet size — meaningless. CFA tests active risk because it is the bridge between three pillars of active management:

1. **Performance evaluation** — Information Ratio = active return / active risk.
2. **Portfolio construction** — risk budgeting allocates active risk across managers/strategies.
3. **The Fundamental Law** — $E(R_A) = TC \times IC \times \sqrt{BR} \times \sigma_A$. Active risk is the *throttle* on expected active return.

It also appears in the most-tested risk-management trap on the exam: **adding a "safe" asset (cash) to an equity portfolio reduces total risk but increases active risk against an equity benchmark.**

## Mechanism

**Rule.** Active risk is the standard deviation of $R_A = R_P - R_B$ over time.

**Why the rule exists.** Once you measure active *return* (the gap), you also need to measure how *stable* that gap is. A manager who beats by +5% one year and loses -3% the next has a different risk profile than one who steadily beats by +1% every year, even if the average return is similar. Investors and IPS mandates pay for *consistent* outperformance, not lottery-ticket outperformance.

**Mechanism — variance additivity.** Using a fundamental factor model, the **active variance** (active risk squared) decomposes cleanly:

$$
\sigma_{R_A}^2 \;=\; \underbrace{\text{Active Factor Variance}}_{\text{from factor tilts}} \;+\; \underbrace{\text{Active Specific Variance}}_{\text{from security selection}}
$$

This works because the residual (specific) returns are, by construction, uncorrelated with the factors. So a manager who knows their factor tilts can calculate exactly how much of their tracking error comes from the value/size/momentum bets versus their stock-picking.

**Assumptions.**

1. Active returns are **stationary** enough that a sample standard deviation is meaningful.
2. The benchmark is **valid** (investable, replicable, ex-ante). A bad benchmark inflates active risk via misfit return.
3. For ex-ante measures, you need reliable **forward-looking** covariances.

**Failure modes.**

- *Non-stationary active returns* (manager changed style mid-period) → historical $\sigma_{R_A}$ misleads.
- *Wrong benchmark* → measured tracking error reflects style misfit, not true active bets.
- *Cash drag against an equity benchmark* → low-volatility cash *increases* tracking error because cash returns are uncorrelated with the equity benchmark.
- *Concentration* → a single oversized active bet inflates active risk far more than the same total active weight spread across diversified names (uncorrelated bets diversify).

**Exam implication.** Vignettes love to show you a "low-risk" portfolio change and ask whether tracking error rises or falls. The answer hinges on **what the benchmark is**, not on the asset's standalone volatility.

## Formula / Framework

### 1. Core formula

$$
\sigma_{R_A} \;=\; \sqrt{\operatorname{Var}(R_P - R_B)} \;=\; \sqrt{\frac{\sum_{t=1}^{T}(R_{A,t} - \bar{R}_A)^2}{T - 1}}
$$

For active returns with mean ≈ 0 (often the case in evaluation):

$$
\sigma_{R_A} \;\approx\; \sqrt{\frac{\sum_{t=1}^{T} R_{A,t}^2}{T - 1}}
$$

| Symbol | Meaning |
|---|---|
| $\sigma_{R_A}$ | Active risk (a.k.a. tracking error) |
| $R_{A,t}$ | Active return in period $t$ |
| $\bar{R}_A$ | Mean active return |
| $T$ | Number of observations |

### 2. Variance decomposition (factor model)

$$
\sigma_{R_A}^2 \;=\; \sigma_{\text{Active Factor}}^2 \;+\; \sigma_{\text{Active Specific}}^2
$$

| Term | What it captures |
|---|---|
| Active factor variance | Risk from intentional tilts to rewarded factors |
| Active specific variance | Idiosyncratic risk from individual security bets |

### 3. Uncorrelated active bets — independent securities

When active bets across $N$ securities are uncorrelated:

$$
\sigma_{R_A}^2 \;=\; \sum_{i=1}^{N} (\Delta w_i)^2 \cdot \sigma_i^2
$$

This is the formula that drives the worked example below — it makes vivid how concentration (large $\Delta w$ on few names) explodes active risk.

### 4. Ex-ante vs ex-post

| Type | What it uses | When | Strength | Weakness |
|---|---|---|---|---|
| **Ex-ante (predicted)** | Forward-looking factor variances/covariances | Portfolio construction, risk budgeting | Forward-looking, control-relevant | Requires good covariance estimates |
| **Ex-post (realized)** | Historical $R_{A,t}$ series | Performance evaluation | Easy, observable | Backward-looking, may not predict future |

### 5. Optimal active risk (when combining with benchmark)

To maximize the total portfolio Sharpe ratio when active and benchmark returns are uncorrelated:

$$
\sigma_{R_A}^* \;=\; \frac{IR}{SR_B} \cdot \sigma_{R_B}
$$

| Symbol | Meaning |
|---|---|
| $IR$ | Manager's information ratio |
| $SR_B$ | Sharpe ratio of the benchmark |
| $\sigma_{R_B}$ | Volatility of the benchmark |

### 6. Link to the Fundamental Law

$$
E(R_A) \;=\; TC \times IC \times \sqrt{BR} \times \sigma_{R_A}
$$

Active risk is the **scaling lever**. Doubling $\sigma_{R_A}$ doubles expected active return *for a given IR* — but it also doubles the downside.

## Worked Example

A manager places **four uncorrelated active bets** with active weights and forecast volatilities:

| Security | $\Delta w_i$ | $\sigma_i$ | $(\Delta w_i)^2 \cdot \sigma_i^2$ |
|---|---|---|---|
| 1 | +0.18 | 0.25 | $0.0324 \times 0.0625 = 0.002025$ |
| 2 | +0.09 | 0.50 | $0.0081 \times 0.2500 = 0.002025$ |
| 3 | −0.18 | 0.25 | $0.0324 \times 0.0625 = 0.002025$ |
| 4 | −0.09 | 0.50 | $0.0081 \times 0.2500 = 0.002025$ |
| **Sum** | | | **0.0081** |

Because the bets are uncorrelated:

$$
\sigma_{R_A}^2 = 0.0081 \quad\Rightarrow\quad \sigma_{R_A} = \sqrt{0.0081} = 0.09 \;=\; \mathbf{9.0\%}
$$

**What if the manager doubled the active weight on Security 1 and dropped Security 3?**

- New term: $(0.36)^2 \times (0.25)^2 = 0.1296 \times 0.0625 = 0.0081$
- Old terms 2 & 4 unchanged: $0.002025 + 0.002025 = 0.00405$
- New $\sigma_{R_A}^2 = 0.0081 + 0.00405 = 0.01215$
- New $\sigma_{R_A} = \sqrt{0.01215} \approx 0.110 = \mathbf{11.0\%}$

**Same gross active exposure, much higher tracking error** — this is the diversification penalty for concentration.

## Comparisons

| Concept | Formula | Measures | Benchmark involved? |
|---|---|---|---|
| **Active risk / tracking error** | $\operatorname{SD}(R_P - R_B)$ | Volatility of benchmark-relative return | Yes |
| **Total portfolio risk** | $\operatorname{SD}(R_P)$ | Absolute volatility | No |
| **Systematic risk (beta)** | $\beta_P$ | Sensitivity to market factor | Market |
| **Idiosyncratic risk** | Residual SD | Firm-specific risk | No |
| **Downside risk** | $\operatorname{SD}$ of returns below MAR | One-sided risk | No |
| **VaR** | Quantile of loss distribution | Worst-case loss at confidence level | No |

## Real-World / Vignette Scenarios

**Scenario 1 — The cash-drag trap.** A manager benchmarked to the S&P 500 reduces equity weight from 100% to 90% and holds 10% T-bills. Total volatility falls. **Tracking error rises** because cash has near-zero correlation with the S&P 500, widening the active-return swings. CFA vignettes test exactly this distinction.

**Scenario 2 — Same IR, different active risk.** Manager A: $E(R_A) = 2\%$, $\sigma_{R_A} = 4\%$, IR = 0.50. Manager B: $E(R_A) = 4\%$, $\sigma_{R_A} = 8\%$, IR = 0.50. Same skill, but Manager B is using twice the active risk budget. To pick between them, you need to know your **risk budget**, not just IR.

**Scenario 3 — Concentration vs. diversification.** A long-only US large-cap manager runs 40 active bets averaging 1% active weight. Equivalent gross active weight concentrated into 4 names would generate roughly $\sqrt{40/4} \approx 3.2\times$ the tracking error per dollar of bet — even with the same conviction.

**Scenario 4 — Risk budgeting.** A multi-manager equity portfolio targets total $\sigma_{R_A} = 3\%$. Each sub-manager is given an active-risk budget such that their squared contributions sum to $9\% \times 9\%$ in basis points (assuming uncorrelated active returns).

## Exam Traps

| Trap | Why it's wrong | Correct view |
|---|---|---|
| Lower total risk → lower tracking error | Cash lowers total risk but increases TE vs an equity benchmark | TE depends on deviation from benchmark, not absolute volatility |
| Tracking error always rises with concentration | Only if bets are uncorrelated; correlated bets behave differently | Use full covariance, not just sum of variances |
| Active risk is a single-period figure | TE is a *standard deviation* — needs a return series or a covariance model | Single-period $R_A$ is just the gap, not the risk |
| Ex-post TE predicts ex-ante TE | Markets and styles drift | Use forward-looking factor models for portfolio construction |
| TE and total risk add | They live in different spaces; only $\sigma_P^2 = \sigma_B^2 + 2\beta\sigma_B \sigma_{R_A}\rho + \sigma_{R_A}^2$ when uncorrelated does it simplify | Decompose carefully |
| Higher active risk = better skill | Skill is IR, not σ_A; high σ_A with low IR = wasted risk | Always pair σ_A with a return measure |
| Tracking error == single-period $R_A$ | Sloppy older usage | In CFA, TE ≡ standard deviation of $R_A$ |

## Memory Hook

> **"σ_A is the *throttle*, not the *engine*."**

The Fundamental Law: $E(R_A) = TC \cdot IC \cdot \sqrt{BR} \cdot \sigma_A$. Active risk *scales* the engine (skill × breadth × implementation). If your engine is broken (low IR), pressing the throttle harder just burns cash faster.

A second hook: **"Cash is risky if your benchmark is stocks."** Burn this into long-term memory — it is the single most-tested counterintuitive idea in PM.

## Exam-Day Checklist

When a vignette mentions tracking error or active risk:

1. **What is the benchmark?** TE only makes sense relative to a benchmark.
2. **Is this ex-ante or ex-post?** Construction uses ex-ante; evaluation uses ex-post.
3. **Are active bets correlated?** If the question says "uncorrelated," variance is additive: $\sigma_{R_A}^2 = \sum (\Delta w_i \sigma_i)^2$.
4. **Did total risk and active risk move in the same direction?** They often don't — check the cash-drag trap.
5. **What is the IR?** TE alone is meaningless; pair it with $E(R_A)$.
6. **Is the question about decomposition?** Identify factor variance vs specific variance.
7. **Risk budget?** TE is the unit of measurement for risk-budgeted multi-manager portfolios.

## Related Concepts

- [[Active Return]]
- [[Information Ratio]]
- [[Fundamental Law of Active Management]]
- [[Analysis of Active Portfolio Management]]
- [[Using Multifactor Models]]
- [[Sharpe Ratio]]
- [[Treynor Ratio]]
