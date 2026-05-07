---
title: Conditional VaR (CVaR) and Expected Shortfall
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, VaR, tail-risk, risk-measures]
aliases: [CVaR, Conditional Value at Risk, Expected Shortfall, ES, Expected Tail Loss, ETL]
---

# Conditional VaR (CVaR) / Expected Shortfall

## The Real-World Analogy

Picture two flood-warning systems for a town near a river.

- **System A (VaR):** "There's a 1% chance the river rises above 10 feet this year." That's it. Above 10 feet, it could be 11, or 50, or it could swallow the town. The warning doesn't say.
- **System B (CVaR):** "If the river *does* go above 10 feet, the average flood depth — based on every catastrophic flood in history — is 18 feet."

System B is the one you actually want before deciding how high to build the levees. **VaR tells you the threshold; CVaR tells you what the average disaster looks like *past* that threshold.** That's the entire intuition for moving from VaR to Expected Shortfall.

## Plain-English Definition

> **CVaR (= Expected Shortfall = Expected Tail Loss) is the *average* loss you should expect on the days when losses are bad enough to break through the VaR threshold.**

It is *conditional*: assume the bad event happens, then ask "how bad on average?"

If a portfolio's 1-day 99% VaR is \$1,000,000, CVaR might be \$1,800,000 — meaning when the worst-1% day actually shows up, the *typical* such day costs you \$1.8M, not the \$1M cutoff number.

## CFA Definition

> **Conditional VaR (CVaR)** — also called **Expected Shortfall (ES)** or **Expected Tail Loss (ETL)** — is the expected (average) loss over a specified horizon, **conditional on the loss being worse than the VaR loss** at a given confidence level.

Formally, for confidence level $X$ (e.g., 99%) and horizon $h$:

$$
\text{CVaR}_X \;=\; E\bigl[\,L \;\big|\; L > \text{VaR}_X\,\bigr]
$$

where $L$ is the (positive-signed) loss random variable.

See: [[Value at Risk (VaR)]] · [[Tail Risk]] · [[Coherent Risk Measure]] · [[Expected Shortfall]]

## Why It Matters

CFA tests CVaR for three big reasons:

1. **VaR has a fatal blind spot** — it ignores everything past the cutoff. Two portfolios with identical VaR can have radically different tail catastrophes. CVaR fixes this.
2. **CVaR is a *coherent* risk measure**; VaR is not. Coherence is the academic gold standard for risk metrics — it requires that diversification can never *increase* risk (subadditivity). VaR can violate this; CVaR cannot.
3. **Regulators are migrating away from VaR.** The Basel Committee replaced VaR with Expected Shortfall in market-risk capital rules (FRTB). Knowing why is fair game for the exam.

In any real risk-management or vignette context, CVaR is the more defensible number.

## Mechanism

Walk the explanation ladder:

| Step | What it says |
|---|---|
| **Rule** | CVaR = the mean of losses that exceed the VaR cutoff |
| **Why the rule exists** | Because a single quantile (VaR) collapses the entire tail to one number, ignoring how *catastrophic* that tail is |
| **Mechanism** | Build a loss distribution → identify the VaR cutoff at confidence $X$ → average everything in the tail beyond that cutoff |
| **Assumptions** | Loss distribution is reliable; sample size in the tail is meaningful; method-specific (normality for parametric, representativeness for historical, model accuracy for Monte Carlo) |
| **Failure mode** | Few tail observations → unstable CVaR estimate; non-stationary regimes → historical CVaR underestimates the *next* crisis |
| **Exam implication** | When a vignette gives ranked losses, **average the tail observations**, don't pick the cutoff |

### Why VaR fails the "coherent" test

A risk measure $\rho$ is **coherent** if it satisfies four properties: monotonicity, positive homogeneity, translation invariance, and **subadditivity**:

$$
\rho(A + B) \le \rho(A) + \rho(B)
$$

Subadditivity says combining two portfolios should never *increase* risk — diversification can only help. **VaR can violate this**, especially with discrete or fat-tailed distributions. **Expected Shortfall always satisfies it.** That single property is why theoretical and regulatory winds blow toward CVaR.

## Formula / Framework

### Method 1 — Historical Simulation (the most common exam setup)

1. Take the last $N$ daily returns/PnL outcomes.
2. Rank them from worst to best.
3. The number of tail observations at confidence $X$ is $N \times (1 - X)$.
4. **VaR** = the loss at the cutoff (e.g., the $N(1-X)$-th worst loss).
5. **CVaR** = the **average** of all losses *at and beyond* the cutoff (or strictly beyond, depending on convention; CFA averages the tail including the cutoff).

### Method 2 — Parametric (Variance-Covariance, normal assumption)

If losses are normal with mean $m$ and standard deviation $s$, then for confidence $X$ (e.g., 0.99):

$$
\boxed{\;ES \;=\; m \;+\; s \cdot \frac{e^{-Y^2/2}}{\sqrt{2\pi}\,(1-X)}\;}
$$

| Symbol | Meaning |
|---|---|
| $m$ | Mean loss (often assumed 0 over short horizons) |
| $s$ | Standard deviation of loss |
| $X$ | Confidence level (e.g., 0.99 for 99%) |
| $Y$ | Standard-normal $X$-th percentile (e.g., 2.326 at 99%, 1.645 at 95%) |
| $\dfrac{e^{-Y^2/2}}{\sqrt{2\pi}}$ | Standard-normal density at $Y$ |

Compare to parametric VaR: $VaR = m + s \cdot Y$. CVaR replaces the multiplier $Y$ with $\phi(Y)/(1-X)$, which is **always larger**.

### Method 3 — Monte Carlo Simulation

1. Specify a stochastic model for risk factors (drifts, vols, correlations).
2. Generate $T$ trials of the portfolio's PnL (e.g., $T = 5{,}000$).
3. Rank losses; the cutoff is at trial $T(1-X)$ (the 50th worst at 99% with 5,000 trials).
4. **CVaR** = average of the $T(1-X)$ worst trials.

## Worked Example

A risk manager runs **historical simulation** with the last 500 trading days. The 99% 1-day VaR uses the worst $500 \times 1\% = 5$ loss days. The five worst daily losses (ranked, in dollars) are:

| Rank | Loss ($) |
|---|---|
| 1 (worst) | 922,484 |
| 2 | 858,423 |
| 3 | 653,541 |
| 4 | 490,215 |
| 5 (cutoff) | 422,291 |

**99% 1-day VaR** = the 5th-worst loss = **\$422,291**.

> Interpretation: We are 99% confident the 1-day loss will not exceed \$422,291.

**99% 1-day CVaR (Expected Shortfall)** = average of those 5 tail losses:

$$
CVaR \;=\; \frac{922{,}484 + 858{,}423 + 653{,}541 + 490{,}215 + 422{,}291}{5} \;=\; \frac{3{,}346{,}954}{5} \;\approx\; \$669{,}391
$$

> Interpretation: **If** the 1% tail event occurs, the *expected* loss is about \$669,391 — about **58% larger** than the VaR cutoff would suggest.

That gap — \$669k vs \$422k — is the entire point of CVaR.

## Comparisons

### VaR vs CVaR — the tested table

| Property | **VaR** | **CVaR (Expected Shortfall)** |
|---|---|---|
| Question answered | "How bad **can** things get at a confidence level?" (cutoff only) | "**If** they get bad, how bad on average?" |
| Sensitive to tail magnitude beyond cutoff? | **No** | **Yes** |
| Coherent risk measure (subadditive)? | **Not always** | **Always** |
| Captures fat tails? | Poorly | Better |
| Regulator preference (post-Basel III/FRTB) | Being phased out | **Preferred** |
| Computationally simpler | Yes | Slightly heavier (need full tail) |
| Reported as a positive loss? | Yes | Yes |

### Three estimation methods compared

| Method | Pros | Cons | CVaR-specific note |
|---|---|---|---|
| **Historical simulation** | No distribution assumption; uses real fat tails | Assumes future ≈ past; few tail observations | Best for CVaR — empirical tail data |
| **Parametric (variance–covariance)** | Closed-form, fast | Normality assumption usually wrong in tails | Use the $\phi(Y)/(1-X)$ formula |
| **Monte Carlo** | Flexible, handles non-linear positions, options | Model risk; computationally heavy | Average the simulated tail losses |

## Real-World / Vignette Scenarios

**Scenario 1 — Two portfolios, same VaR.** A vignette shows Portfolio A has a 99% VaR of \$1M with worst-case loss capped at \$1.1M. Portfolio B has a 99% VaR of \$1M but tail losses extending to \$10M. **VaR cannot tell them apart; CVaR will.** A is much safer.

**Scenario 2 — The ranked-losses table.** A vignette gives you the 10 worst simulated losses out of 1,000 trials and asks for 99% CVaR. The cutoff is at trial 10 (= 1,000 × 1%). **VaR** = the 10th worst. **CVaR** = average of all 10 listed losses, *not* just the cutoff number.

**Scenario 3 — Regulator question.** A vignette mentions a bank moving its capital framework from VaR to Expected Shortfall under Basel III. The reasoning hinges on coherence (subadditivity) and tail sensitivity.

**Scenario 4 — Diversification check.** A risk officer combines two desks each with VaR \$5M. Combined VaR is reported as \$11M (subadditivity violated). Expected Shortfall combination would always be ≤ \$10M. Vignette tests recognition of the coherence flaw.

## Exam Traps

| Trap | Reality |
|---|---|
| Pick the VaR cutoff observation as CVaR | CVaR = **average** of all tail losses (cutoff and beyond) |
| Treat CVaR and VaR as interchangeable | They answer different questions; CVaR ≥ VaR by construction |
| Assume VaR is "coherent" because it's standard | VaR can violate **subadditivity**; ES does not |
| Use parametric formula with non-normal returns and trust the answer | Parametric CVaR understates tail loss when returns are fat-tailed |
| Confuse Expected Shortfall with Maximum Drawdown | Drawdown is path-dependent; ES is a single-period tail expectation |
| Forget to set $Y$ correctly when computing parametric ES | $Y = 2.326$ for 99%, $1.645$ for 95% — same Y as VaR |
| Use the wrong tail count: at 99% with 250 obs, tail = ? | $250 \times 0.01 = 2.5$ — round up to **3** worst observations |
| Report ES as a "probability" | ES is a **dollar (or %) loss**, not a probability |

## Memory Hook

> **"VaR is the doorstep; CVaR is the average size of the monsters that walk in past it."**

Or formulaic:

> **"VaR cuts; CVaR averages the tail."**

For the parametric formula, remember the multiplier swap:

$$
VaR \to s\cdot Y \qquad CVaR \to s\cdot\frac{\phi(Y)}{1-X}
$$

The latter is always bigger because it captures *the whole tail*, not just the doorstep.

## Exam-Day Checklist

When you see CVaR / Expected Shortfall in a vignette:

1. Identify the **confidence level** (95% / 99%) and **horizon** (1-day / 10-day).
2. Identify the **method** (historical, parametric, Monte Carlo).
3. If a **ranked-loss table** is given: compute tail size = $N(1-X)$, then **average** those losses.
4. If **parametric** with normality: use $ES = m + s \cdot \phi(Y)/(1-X)$.
5. Check whether the question wants **VaR**, **CVaR**, or **both** — they're often presented side-by-side.
6. For conceptual Qs: ES is **coherent**, captures **tail magnitude**, preferred by **regulators** (Basel III/FRTB).
7. Watch for the **two-portfolios-same-VaR** trick — answer is always "use ES to distinguish them."
8. Remember CVaR ≥ VaR. If your computed CVaR < VaR, you made an arithmetic mistake.

## Related Concepts

- [[Value at Risk (VaR)]]
- [[Parametric Method]]
- [[Historical Simulation]]
- [[Monte Carlo Simulation]]
- [[Tail Risk]]
- [[Coherent Risk Measure]]
- [[Subadditivity]]
- [[Stress Testing]]
- [[Incremental VaR]]
- [[Marginal VaR]]
- [[Relative VaR]]
- [[Drawdown]]
- [[Measuring and Managing Market Risk]]
