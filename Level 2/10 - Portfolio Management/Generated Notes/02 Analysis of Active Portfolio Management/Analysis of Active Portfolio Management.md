---
title: Analysis of Active Portfolio Management
subject: Portfolio Management
tags: [CFA-L2, PortfolioManagement, ActiveManagement, InformationRatio, SharpeRatio, FundamentalLaw, TransferCoefficient, InformationCoefficient, Breadth, ActiveRisk, MarketTiming, SecuritySelection]
aliases: [Fundamental Law of Active Management, Active Management, Information Ratio Reading, L2 PM Module 2]
---

# Analysis of Active Portfolio Management

> [!abstract] The One-Sentence Version
> Active management succeeds when **skill × the number of independent bets × how cleanly those bets get into the portfolio** overcomes the cost of tracking error — and the whole system is summarized by one formula: **IR = TC × IC × √BR**.

The reading is really just Grinold and Kahn's elegant claim that you can decompose a manager's whole edge into four numbers — skill (IC), opportunity (BR), implementation purity (TC), and aggressiveness (σ_A). Everything in the LOS list is an application of those four.

---

## 1. What "Value Added" Actually Means

### 1.1 Active Return, the Building Block

**Active return** is just how much better (or worse) a portfolio did than its benchmark:

$$
\boxed{\,R_A \;=\; R_P \;-\; R_B\,}
$$

Two useful re-expressions:

1. **Weight × return** form — active return is the sum of active weights times asset returns:

$$
R_A \;=\; \sum_{i=1}^{N} (w_{P,i} - w_{B,i})\,R_i \;=\; \sum_{i=1}^{N} \Delta w_i \,R_i
$$

2. **Alpha** ($\alpha$) — active return *after* scrubbing off the return that just came from taking more market risk ($\beta$). When $\beta_P \approx 1$, alpha ≈ active return.

$$
\alpha \;=\; R_P \;-\; \bigl[R_F + \beta_P(R_M - R_F)\bigr]
$$

### 1.2 Decomposing Where Value Came From

$$
R_A \;=\; \underbrace{\sum_j (w_{P,j} - w_{B,j})\,R_{B,j}}_{\text{Asset allocation effect}} \;+\; \underbrace{\sum_j w_{P,j}(R_{P,j} - R_{B,j})}_{\text{Security selection effect}}
$$

| Source | Question answered | How measured |
|---|---|---|
| **Asset allocation** | Did the manager get *which buckets* (equities vs. bonds vs. cash, sectors, regions) right? | Active weight × benchmark return of bucket |
| **Security selection** | Within each bucket, did the manager pick the right names? | Portfolio weight × (portfolio return − benchmark return) inside the bucket |

> [!tip] Memory Hook — **"Buckets vs. Names"**
> Asset allocation = **bucket picking**. Security selection = **name picking**. Value added is the sum.

See: [[Active Return]] · [[Alpha]] · [[Brinson Fachler Attribution]]

---

## 2. The Information Ratio — Report Card for Active Managers

### 2.1 Definition

$$
\boxed{\,IR \;=\; \frac{\bar{R}_A}{\sigma_A}\,}
$$

where $\sigma_A$ is the standard deviation of active returns (a.k.a. **tracking error** or **active risk**).

IR tells you how **consistently** a manager generates benchmark-relative return per unit of benchmark-relative risk. It's the "batting average" of active management.

### 2.2 Ex Ante vs. Ex Post

| Flavor | Inputs | Use for |
|---|---|---|
| **Ex ante IR** | *Expected* active return and *forecast* active risk | Manager hiring, risk budgeting, portfolio construction |
| **Ex post IR** | *Realized* average active return and *sample* standard deviation | Performance evaluation, reporting |

Both use the same formula, just different inputs.

### 2.3 Sharpe Ratio vs. Information Ratio — Cousins, Not Twins

| | **Sharpe ratio ($SR$)** | **Information ratio ($IR$)** |
|---|---|---|
| **Numerator** | $R_P - R_F$ (excess over cash) | $R_P - R_B$ (excess over benchmark) |
| **Denominator** | $\sigma_P$ (total risk) | $\sigma_A$ (active / tracking risk) |
| **Answers** | "Is this portfolio good *in absolute terms*?" | "Is this manager adding value *vs. the benchmark*?" |
| **Effect of cash / leverage** | **Unchanged** — adding cash or leverage doesn't move SR | **Changes** — adding cash lowers IR; leverage *within* active weights keeps IR constant under no constraints |
| **Effect of more active aggressiveness** | Affects SR (through total risk) | **Invariant** to scale when unconstrained |

> [!important] Invariance to Aggressiveness
> For an **unconstrained** active manager, doubling every active weight doubles $R_A$ *and* doubles $\sigma_A$ — the ratio stays the same. IR measures skill, not boldness.

### 2.4 Typical Industry Values

| Type | "Good" ex post IR |
|---|---|
| Typical active mutual fund | –0.30 to +0.30 |
| Top-quartile active manager | 0.40 – 0.60 |
| Quantitative equity strategies (unconstrained) | 0.40 – 0.60 "quite good" |
| Elite hedge funds / market-neutral | > 1.0 (rare, often decays) |

See: [[Information Ratio]] · [[Sharpe Ratio]] · [[Tracking Error]]

---

## 3. The Fundamental Law of Active Management

The **Fundamental Law of Active Management** (Grinold, 1989; Clarke, de Silva, Thorley 2002) decomposes the information ratio into its building blocks.

![[fundamental-law-active-mgmt.png]]

### 3.1 Basic Form

$$
\boxed{\,IR \;=\; IC \times \sqrt{BR}\,}
$$

### 3.2 Full (Constrained) Form

$$
\boxed{\,IR \;=\; TC \times IC \times \sqrt{BR}\,}
$$

Expected active return:

$$
\boxed{\,E[R_A] \;=\; TC \times IC \times \sqrt{BR}\times \sigma_A\,}
$$

### 3.3 Each Component, Plainly

#### IC — Information Coefficient (Skill)

The correlation between the manager's forecasts and realized active returns.

$$
IC \;=\; \text{Corr}(\text{forecast}_i,\; R_{A,i})
$$

- $IC = 0$ → a coin flip.
- $IC = 0.05$ → slightly skilled (typical for stock pickers).
- $IC = 0.10–0.15$ → very skilled.
- $IC = 1.0$ → perfect foresight (fictional).

Because it's a correlation, it's bounded in $[-1, +1]$. In practice, sustained IC above 0.10 is rare.

#### BR — Breadth (Shots on Goal)

The number of **independent** decisions per year. The key word is *independent* — this is where most real-world violations happen.

| Strategy | BR calculation |
|---|---|
| Annual asset-allocation tilt (stocks vs. bonds) | 1 |
| Quarterly tactical moves across 5 sectors | 5 × 4 = 20 |
| 400 stocks rebalanced quarterly (if independent) | 400 × 4 = 1600 |
| 400 stocks rebalanced daily (if independent) | 400 × 252 = 100,800 ← rarely true in practice |

> The **√BR** factor is the law of large numbers. Active return scales with **BR**, but active risk scales only with **√BR** (independent bets diversify). Their ratio, the IR, grows with **√BR**.

#### TC — Transfer Coefficient (Implementation Purity)

How well forecasts translate into *actual* active weights.

$$
TC \;=\; \text{Corr}(\text{forecast},\; \text{realized active weights})
$$

- **Unconstrained mean-variance optimizer** → TC ≈ 1.
- **Long-only constraint** (can't short losers) → TC ≈ 0.3 – 0.6.
- **Long-only + turnover limits + position caps** → TC can drop below 0.3.

TC is the silent killer. Many quantitative strategies look brilliant on paper (high IC, high BR) but deliver mediocre IR because real-world constraints cap TC.

#### σ_A — Active Risk (Aggressiveness)

Target tracking error. Does **not** affect the IR (by invariance), but directly scales expected active return:
$$E[R_A] = IR \times \sigma_A$$

### 3.4 Worked Example — Full Calculation

> A quantitative equity manager:
>
> | Input | Value |
> |---|---|
> | Information coefficient (IC) | 0.05 |
> | Breadth (400 stocks × 4 quarterly rebal.) | 1,600 |
> | Transfer coefficient (long-only) | 0.60 |
> | Target active risk (σ_A) | 4% |
>
> **Step 1 — IR**
> $$IR = 0.60 \times 0.05 \times \sqrt{1{,}600} = 0.60 \times 0.05 \times 40 = \mathbf{1.20}$$
>
> **Step 2 — Expected active return**
> $$E[R_A] = 1.20 \times 4\% = \mathbf{4.80\%}$$
>
> **Step 3 — Sanity check**
> A tiny skill (0.05) produces a premium IR because of the vast breadth and the square-root leverage. This is the quant edge: thousands of small bets combined.

### 3.5 Why Square Root?

The intuition is diversification. With $N$ independent bets, each with expected excess return $\mu$ and volatility $\sigma$:

- Portfolio *expected* active return = $N \times \mu$ (scales linearly)
- Portfolio *standard deviation* = $\sqrt{N} \times \sigma$ (scales by √N, since variance adds but stddev is the sqrt)
- Ratio = $\sqrt{N} \times \mu/\sigma$

The IR grows with √N, not N — more bets help, but with diminishing returns.

> [!tip] Memory Hook — **"SITE"**
> **S**kill × **I**mplementation × (square root of) **T**ries × **E**xposure (aggressiveness).
> That's IC × TC × √BR × σ_A.

See: [[Fundamental Law of Active Management]] · [[Information Coefficient]] · [[Breadth]] · [[Transfer Coefficient]]

---

## 4. Using IR to Pick Managers & Set Risk

### 4.1 Highest IR Wins — Always

Among available active managers, the one with the **highest ex ante IR** lets the investor build the portfolio with the **highest possible Sharpe ratio**. This is arguably the most important practical result in the reading.

$$
\boxed{\,SR_P^{\,2} \;=\; SR_B^{\,2} \;+\; IR^{\,2}\,}
$$

The added Sharpe² is just the squared IR — *regardless of the benchmark*. So if you can pick, you pick the highest IR.

### 4.2 Optimal Active Risk σ_A*

Once you've chosen a manager, how *much* active risk should you take? Enough that the Sharpe boost is fully exploited:

$$
\boxed{\,\sigma_A^{\,*} \;=\; \frac{IR}{SR_B}\,\sigma_B\,}
$$

If a manager's existing active risk is **below** σ_A*, the investor can lever up (or short some benchmark to buy more of the active fund) to hit the optimum. Above it, scale back.

### 4.3 Worked Example — Sharpe Improvement

> Benchmark: $SR_B = 0.40$, $\sigma_B = 16\%$. Manager: $IR = 0.30$.
>
> **Optimal active risk**
> $$\sigma_A^* = (0.30/0.40) \times 16\% = \mathbf{12\%}$$
>
> **New total portfolio Sharpe**
> $$SR_P = \sqrt{0.40^2 + 0.30^2} = \sqrt{0.16 + 0.09} = \sqrt{0.25} = \mathbf{0.50}$$
>
> The investor moved from a 0.40-Sharpe passive portfolio to a 0.50-Sharpe managed portfolio — a 25% improvement, captured entirely through the IR.

> [!warning] Real-World Caveat
> σ_A* assumes **unconstrained** access to the manager and leverage. If the client's mandate caps tracking error at, say, 4% while σ_A* = 12%, the investor can't fully exploit the IR.

See: [[Risk Budgeting]] · [[Optimal Active Risk]]

---

## 5. Comparing Active Strategies

### 5.1 Market Timing vs. Security Selection — The Core Contrast

| | **Market Timer** | **Stock Picker** |
|---|---|---|
| Decisions per year (BR) | Few (e.g., 4 quarterly asset-allocation calls) | Many (e.g., 100+ stocks, rebalanced monthly) |
| Required IC | **Must be high** (each call matters) | Can be low (law of averages works) |
| Character | "Home run hitter" | "Base hitter" |
| Typical real-world IR at IC=0.05 | Very low — 0.05×√4 = 0.10 | Moderate — 0.05×√100 = 0.50 |

#### Worked Example — Same Skill, Different BR

> **Manager A (Market Timer):** IC = 0.10, BR = 4 (quarterly)
> $$IR_A = 0.10 \times \sqrt{4} = \mathbf{0.20}$$
>
> **Manager B (Stock Picker):** IC = 0.05, BR = 100
> $$IR_B = 0.05 \times \sqrt{100} = \mathbf{0.50}$$
>
> **Takeaway:** B has *half* the per-decision skill but 2.5× the IR because of breadth. This is why quant equity shops exist.

### 5.2 Common Strategy Changes — Fundamental-Law Analysis

Apply the law to evaluate any proposed change:

| Proposed change | Effect on which term? | Net IR effect |
|---|---|---|
| Rebalance monthly instead of quarterly | BR potentially ×3 — *but only if signals are truly independent each month* | IR × √3 ≈ ×1.7 *at best* |
| Expand universe from 100 → 500 stocks | BR × 5 | IR × √5 ≈ ×2.24 |
| Lift long-only constraint (allow shorting) | TC rises (e.g., 0.6 → 0.9) | IR × 1.5 |
| Add turnover limit of 50%/year | TC falls | IR shrinks proportionally |
| Hire a second, correlated signal | BR unchanged (not independent!) | IR unchanged — **common trap** |
| Switch from ranking 10 sectors to 500 stocks | BR × 50 | IR × √50 ≈ ×7 (if IC holds) |

#### Worked Example — Adding a Constraint

> A manager runs an unconstrained strategy with $IR = 0.50$ and $\sigma_A = 3\%$.
>
> $$E[R_A] = 0.50 \times 3\% = 1.50\%$$
>
> The client insists on long-only plus a monthly turnover cap, dropping TC from 1.0 → 0.60.
>
> $$IR_{\text{new}} = 0.60 \times 0.50 = 0.30$$
> $$E[R_A]_{\text{new}} = 0.30 \times 3\% = 0.90\%$$
>
> A 40% cut in active return purely from implementation friction — the forecasts didn't change.

> [!tip] Mnemonic — **"Independence is Everything"**
> The single biggest overstatement in the fundamental law is pretending correlated bets are independent. 50 tech stocks in 2000 were **one** bet, not 50.

See: [[Market Timing]] · [[Security Selection]] · [[Long Only Constraint]]

---

## 6. Practical Strengths and Limitations

### 6.1 Strengths — Why Everyone Teaches This Framework

| Strength | What it gives you |
|---|---|
| **Unified decomposition** | Turns "is this manager skilled?" into four measurable components |
| **Evaluates strategy changes** | Quantifies the incremental value of more stocks, faster rebalancing, lifting constraints |
| **Comparable across strategies** | Same IR lens compares a market-timer to a quant equity shop |
| **Bridges to total Sharpe** | Connects active management back to total-portfolio efficiency (SR_P² = SR_B² + IR²) |
| **Highlights implementation** | TC reminds PMs that frictions and constraints are a hidden alpha tax |

### 6.2 Limitations — Where the Math Lies to You

| Limitation | Consequence |
|---|---|
| **Overstated breadth** | Correlated bets count as one bet. Real-world BR is often 10–50× smaller than naive counting suggests. |
| **Non-stationary IC** | True skill drifts over time; markets regime-shift. Ex ante IC estimates may not hold. |
| **Ex post noise** | Realized ex post IR can be 45–91% *below* the theoretical ex ante IR — the gap is **strategy risk**. |
| **TC is hard to estimate** | Requires Monte Carlo simulation of constrained optimizer output vs. unconstrained signals. |
| **Assumes mean-variance world** | Ignores higher moments — the 2008 experience of many "market-neutral" funds. |
| **Signal decay** | Signals lose power as they become crowded or as markets adapt. |
| **Transaction costs ignored** | Real trading costs eat into active return; the law models frictionless rebalancing. |
| **Manager selection bias** | Past IR doesn't cleanly predict future IR; survivorship bias inflates industry averages. |

### 6.3 Two Biggest Pitfalls To Memorize

> [!warning] Pitfall #1 — Breadth inflation
> If you're picking tech stocks after reading the same tech research newsletter, your BR is 1, not 50. Counting correlated signals as independent is the classic error that makes bad quant strategies look great on paper.

> [!warning] Pitfall #2 — Ignoring strategy risk
> The theoretical ex ante IR assumes IC is perfectly estimated and stable. In reality, your estimate of IC is itself noisy — the strategy as a whole has risk, on top of its component risks. Expect realized IR to be substantially below theoretical.

See: [[Strategy Risk]] · [[Signal Decay]] · [[Transaction Costs]]

---

## 7. Putting It All Together

### 7.1 Decision Framework for the Exam / The Analyst

Given any active-management scenario, walk through:

1. **Identify the active return source** — allocation, selection, timing, factor?
2. **Estimate the four pillars** — IC, BR, TC, σ_A.
3. **Compute the ex ante IR** via IR = TC × IC × √BR.
4. **Gut-check against real-world limits** — Are the bets really independent? Are constraints hidden?
5. **Compare to σ_A\*** — Is the manager running at the right aggressiveness?
6. **Estimate Sharpe boost** — SR_P² = SR_B² + IR².
7. **Apply the discount** — expect realized IR to underperform theoretical by 50%+ in practice.

### 7.2 Master Summary Table

| LOS | Core formula / idea |
|---|---|
| Value added | $R_A = R_P - R_B = \sum \Delta w_i R_i$ |
| Information ratio | $IR = \bar{R}_A / \sigma_A$ |
| Sharpe vs IR | $SR_P^2 = SR_B^2 + IR^2$ |
| Fundamental law (basic) | $IR = IC \sqrt{BR}$ |
| Fundamental law (full) | $IR = TC \cdot IC \cdot \sqrt{BR}$ |
| Expected active return | $E[R_A] = TC \cdot IC \cdot \sqrt{BR} \cdot \sigma_A$ |
| Optimal active risk | $\sigma_A^* = (IR / SR_B) \sigma_B$ |
| Breadth intuition | Independent bets, risk scales √N, return scales N |
| TC intuition | Constraints < 1 shave IR proportionally |
| Manager selection | Highest ex ante IR |

### 7.3 Exam Danger Zones

| Trap | Antidote |
|---|---|
| Counting correlated bets as independent | Always ask "is each signal genuinely new information?" |
| Confusing ex ante with ex post IR | Ex ante uses forecasts; ex post uses realizations |
| Forgetting TC when a constraint is added | Any long-only, turnover, or cap is a TC haircut |
| Treating IR as dependent on σ_A | Invariance: IR is scale-free under no constraints |
| Adding cash to boost Sharpe (it doesn't boost IR) | SR unchanged by cash; IR shrinks because σ_A unchanged while R_A scales |
| Terminal-value IR above 2.0 | Implausible long-run — revisit breadth/IC assumptions |

---

## 8. Formula Cheat Sheet

| Formula | Gives |
|---|---|
| $R_A = R_P - R_B$ | Active return |
| $R_A = \sum \Delta w_i R_i$ | Active return from active weights |
| $IR = \bar{R}_A / \sigma_A$ | Information ratio |
| $SR = (R_P - R_F)/\sigma_P$ | Sharpe ratio |
| $IR = IC\sqrt{BR}$ | Basic fundamental law |
| $IR = TC \cdot IC \sqrt{BR}$ | Full fundamental law |
| $E[R_A] = TC \cdot IC \sqrt{BR} \cdot \sigma_A$ | Expected active return |
| $SR_P^2 = SR_B^2 + IR^2$ | Manager's impact on total Sharpe |
| $\sigma_A^* = (IR/SR_B)\sigma_B$ | Optimal active risk |
| $TC = \text{Corr}(\text{forecast}, \text{active weight})$ | Transfer coefficient |
| $IC = \text{Corr}(\text{forecast}, R_A)$ | Information coefficient |

---

## 9. Related Notes

- [[Information Ratio]] · [[Sharpe Ratio]] · [[Tracking Error]]
- [[Active Return]] · [[Alpha]] · [[Brinson Fachler Attribution]]
- [[Fundamental Law of Active Management]] · [[Information Coefficient]] · [[Breadth]] · [[Transfer Coefficient]]
- [[Market Timing]] · [[Security Selection]] · [[Long Only Constraint]]
- [[Optimal Active Risk]] · [[Risk Budgeting]]
- [[Strategy Risk]] · [[Signal Decay]]
- Practice: `Practice Questions/10 - Portfolio Management/Analysis of Active Portfolio Management/`

---

> [!quote] Final Frame
> The fundamental law says a manager's edge = **skill** × **opportunity** × **implementation** × **aggressiveness**. Three of those four — skill (IC), opportunity (BR), and implementation (TC) — determine the information ratio. Aggressiveness just scales it. Get these four right, and you've got the whole reading.
