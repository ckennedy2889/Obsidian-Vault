---
title: Sharpe Ratio
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, performance-evaluation, risk-adjusted-return]
aliases: [Sharpe Ratio, SR, Reward-to-Variability Ratio, Sharpe Measure]
---

# Sharpe Ratio

## The Real-World Analogy

Imagine two trips to a casino. You play roulette at table A and walk away with +$100. Your friend plays roulette at table B and also walks away with +$100. Same profit. But at table A you bet $50 per spin and at table B you bet $500 per spin. **Per dollar of risk taken, you did far better.** That "return per unit of risk" is the Sharpe ratio's core idea.

In investing, "risk" is **total volatility** ($\sigma_P$) and "return" is the **excess over what you could have earned with no risk at all** ($R_P - R_F$). Sharpe is the cleanest single number for comparing how efficiently any portfolio — active or passive, equity or balanced — converts risk into reward.

## Plain-English Definition

**The Sharpe ratio is the excess return earned per unit of total volatility.** Higher is better. A Sharpe of 0.5 means you earned 0.5% of excess return for every 1% of standard deviation. It is the dominant *total-risk* performance measure and the benchmark against which all other risk-adjusted measures are compared.

## CFA Definition

$$
SR_P \;=\; \frac{\bar{R}_P - \bar{R}_F}{\sigma_P}
$$

| Symbol | Meaning |
|---|---|
| $\bar{R}_P$ | Mean (or expected) portfolio return |
| $\bar{R}_F$ | Mean risk-free rate |
| $\sigma_P$ | Standard deviation of portfolio returns (total risk) |

This is the **reward-to-variability ratio** introduced by William Sharpe (1966). It assumes the investor cares about *total* portfolio risk — appropriate when the portfolio in question represents the investor's entire risky position.

## Why It Matters

Sharpe is the **default scoreboard** for risk-adjusted performance. CFA tests it because:

1. It is the **bridge** between active management and total-portfolio efficiency: $SR_P^2 = SR_B^2 + IR^2$ (the cornerstone of the [[Fundamental Law of Active Management]] reading).
2. It feeds the **optimal active risk** formula: $\sigma_A^* = (IR/SR_B) \cdot \sigma_B$.
3. It is the test case for **multi-period annualization traps** (the $\sqrt{T}$ rule and its failure under autocorrelation).
4. It is the most-used and most-misused single number in the industry — vignettes love to test when it lies (skewed/leptokurtic returns, leverage, stale prices).

## Mechanism

**Rule.** Sharpe = (excess return) / (total volatility).

**Why total risk?** Because it answers the question: "If this portfolio is *all* I own, how good is it per unit of nervous-stomach volatility?" When the portfolio is your whole risk budget, both systematic and idiosyncratic risk hurt you — so total $\sigma$ is the right denominator. (If you hold the portfolio alongside a well-diversified market portfolio, idiosyncratic risk diversifies away and you should use **beta** instead → [[Treynor Ratio]].)

**Mechanism — what raises Sharpe.** Three levers, in order of cleanliness:
1. **Higher expected return** at the same volatility (true alpha).
2. **Lower volatility** at the same return (better diversification).
3. **Leverage along the capital allocation line** — does *not* change Sharpe because both numerator and denominator scale linearly.

**Assumptions that make it meaningful.**

1. **Returns are approximately normally distributed.** The Sharpe ratio uses only the first two moments (mean, variance). It is blind to skewness and kurtosis.
2. **Risk-free rate is well-defined and constant** (or you use a matched-maturity proxy like the 3-month T-bill).
3. **Returns are i.i.d.** (independent and identically distributed) — needed for the $\sqrt{T}$ annualization to be valid.
4. The portfolio is the investor's **total risky holding**.

**Failure modes.**

- *Negatively skewed strategies (option-selling, merger arb, credit, illiquid alts)* show artificially high Sharpe ratios because they hide tail risk in moments 3 and 4. Use [[Sortino Ratio]] or [[Conditional VaR (CVaR) and Expected Shortfall]] instead.
- *Stale prices* (illiquid funds, real estate, private credit) understate $\sigma_P$ and inflate Sharpe. Unsmooth the returns first.
- *Autocorrelated returns* break the $\sqrt{T}$ annualization. Positive autocorrelation overstates annualized Sharpe.
- *Negative excess return* makes Sharpe ambiguous: a more-volatile losing portfolio looks "better" because its negative numerator is divided by a bigger denominator.
- *Different risk-free rates* across studies make cross-comparisons unreliable.

**Exam implication.** When a vignette says "the portfolio earned 12% with 15% volatility and the risk-free rate is 3%" — Sharpe is a one-line plug. The points come from knowing **when not to trust it** (skewed returns, leverage, multi-period annualization, comparing across asset classes with different distributions).

## Formula / Framework

### 1. Core formula

$$
SR \;=\; \frac{R_P - R_F}{\sigma_P}
$$

### 2. Multi-period annualization (the $\sqrt{T}$ rule)

If monthly returns are i.i.d. with monthly Sharpe $SR_m$:

$$
SR_{\text{annual}} \;=\; SR_m \cdot \sqrt{12}
$$

More generally, if you have a Sharpe based on returns of frequency $f$, annualize by multiplying by $\sqrt{f}$ where $f$ is observations-per-year (12 monthly, 52 weekly, 252 daily).

**Trap:** this rule **only works if returns are i.i.d.** With positive autocorrelation (common in illiquid funds), $\sqrt{T}$ overstates annualized Sharpe — the real annualization needs a serial-correlation correction.

### 3. Sharpe decomposition (active management identity)

For an actively managed portfolio relative to a benchmark, when active and benchmark returns are uncorrelated:

$$
\boxed{\,SR_P^{\,2} \;=\; SR_B^{\,2} \;+\; IR^{\,2}\,}
$$

This is the **single most important active-management identity**. It says that adding an active overlay with information ratio $IR$ to a passive benchmark with Sharpe $SR_B$ raises total portfolio Sharpe by an amount that depends only on the IR — not on the benchmark. Therefore: **pick the manager with the highest IR**.

### 4. Optimal active risk

$$
\sigma_A^{*} \;=\; \frac{IR}{SR_B} \cdot \sigma_B
$$

Take *exactly* this much active risk to fully realize the Sharpe boost from your IR.

### 5. Ex-ante vs ex-post

| Type | Inputs | Use |
|---|---|---|
| **Ex-ante (expected) Sharpe** | $E[R_P]$, $E[R_F]$, forecast $\sigma_P$ | Portfolio construction, manager selection |
| **Ex-post (realized) Sharpe** | Sample mean, sample SD over historical period | Performance evaluation |

## Worked Example

**Setup.** Over the past year, a balanced fund returned $\bar{R}_P = 11.0\%$ with $\sigma_P = 12.0\%$. The average risk-free rate was 3.0%.

**Sharpe:**
$$
SR_P = \frac{11.0\% - 3.0\%}{12.0\%} = \frac{8.0\%}{12.0\%} = \mathbf{0.667}
$$

**Sharpe boost from active management.** The benchmark Sharpe is $SR_B = 0.50$. The manager has $IR = 0.40$.

$$
SR_P^2 = 0.50^2 + 0.40^2 = 0.25 + 0.16 = 0.41
$$
$$
SR_P = \sqrt{0.41} = \mathbf{0.640}
$$

The investor moves from a 0.50-Sharpe passive portfolio to a 0.64-Sharpe active portfolio — a 28% improvement, driven entirely by the IR.

**Optimal active risk** if benchmark $\sigma_B = 16\%$:
$$
\sigma_A^{*} = \frac{0.40}{0.50} \cdot 16\% = 0.80 \cdot 16\% = \mathbf{12.8\%}
$$

**Annualization sanity check.** If this fund's monthly Sharpe is 0.18 and returns are approximately i.i.d.:
$$
SR_{\text{annual}} \approx 0.18 \cdot \sqrt{12} \approx 0.18 \cdot 3.464 \approx \mathbf{0.62}
$$

If the fund is illiquid with monthly autocorrelation $\rho = 0.3$, the true annualized Sharpe is meaningfully lower than 0.62 — the smoothed-return $\sqrt{12}$ rule lies upward.

## Comparisons

| Measure | Numerator | Denominator | When to use | Adjusts for |
|---|---|---|---|---|
| **Sharpe** | $R_P - R_F$ | Total $\sigma_P$ | Portfolio is total risky position | Total risk |
| **[[Treynor Ratio]]** | $R_P - R_F$ | Beta $\beta_P$ | Portfolio is one slice of a diversified whole | Systematic risk only |
| **[[Information Ratio]]** | $R_P - R_B$ | Tracking error $\sigma_{R_A}$ | Active management vs benchmark | Benchmark-relative risk |
| **Jensen's alpha** | $R_P - [R_F + \beta(R_M - R_F)]$ | — | Skill measurement | Beta-explained return |
| **M-squared** | Sharpe rescaled to benchmark $\sigma$ | — | Easier-to-interpret % return | Total risk |
| **[[Sortino Ratio]]** | $R_P - MAR$ | Downside $\sigma_D$ | Asymmetric / non-normal returns | Downside risk only |

Mnemonic: **Sharpe-Total, Treynor-Beta, IR-Active.**

## Real-World / Vignette Scenarios

**Scenario 1 — Sharpe vs. Treynor disagreement.** A portfolio's Sharpe ranks 8th of 10 but its Treynor ranks 1st. Implication: high *idiosyncratic* risk but low *systematic* risk. If the portfolio is the investor's only holding → trust Sharpe (it ranks low). If it's one of many → trust Treynor (it adds well to a diversified pot).

**Scenario 2 — Negatively skewed strategy.** A merger-arbitrage fund shows monthly Sharpe of 1.8 over five years. Looks elite. But returns are negatively skewed with fat left tails (deal breaks). True risk-adjusted performance is much worse than Sharpe says — use [[Sortino Ratio]] and [[Maximum Drawdown]] for a fairer picture.

**Scenario 3 — Leverage doesn't help.** Doubling leverage doubles both excess return and volatility, leaving Sharpe unchanged (along the CAL). To raise Sharpe you need *true alpha*, not gearing.

**Scenario 4 — Active boost.** Pension uses passive S&P 500 with $SR_B = 0.45$. Two active managers offer overlays: A has IR = 0.30, B has IR = 0.20. New Sharpes: $\sqrt{0.45^2 + 0.30^2} = 0.541$ vs $\sqrt{0.45^2 + 0.20^2} = 0.492$. Pick A.

**Scenario 5 — Annualization trap.** A hedge fund reports a monthly Sharpe of 0.5 → "annual Sharpe of 1.73 ($0.5\sqrt{12}$)." Vignette later reveals returns have monthly autocorrelation of 0.4. The $\sqrt{12}$ rule fails — the *true* annualized Sharpe is meaningfully lower because volatility was understated by smoothing.

## Exam Traps

| Trap | Why it's wrong | Correct view |
|---|---|---|
| Higher Sharpe always = better | Negative-skew strategies fake high Sharpe by hiding tail risk | Pair with Sortino, max drawdown, CVaR |
| Leverage raises Sharpe | Both numerator and denominator scale | Sharpe is leverage-invariant on the CAL |
| Sharpe and Treynor must agree | They use different risk measures | Disagreement signals high firm-specific risk |
| $\sqrt{T}$ annualization always works | Requires i.i.d. returns | Adjust for autocorrelation in illiquid strategies |
| Comparing Sharpes across asset classes is fair | Different higher moments distort comparison | Compare within asset class or unsmooth first |
| Negative-Sharpe rankings are meaningful | More-volatile losers look "better" | Use a different measure when excess returns are negative |
| Sharpe = excess over benchmark | Excess is over $R_F$, not $R_B$ | Excess-over-benchmark = numerator of IR, not Sharpe |

## Memory Hook

> **"Excess over cash, divided by all the bumps."**

The numerator: how much you beat *cash* (not the benchmark). The denominator: *every* bump in the road (total volatility), not just the market-beta bumps.

A second hook: **"$SR^2$ adds for orthogonal sources."** Sharpe-squared is additive for uncorrelated return sources, which is exactly why $SR_P^2 = SR_B^2 + IR^2$ holds.

## Exam-Day Checklist

When a vignette mentions Sharpe, ask:

1. **Is total risk the right denominator?** If the portfolio is one slice, switch to Treynor. If benchmark-relative, switch to IR.
2. **Are returns approximately normal?** If they're skewed/fat-tailed, Sharpe overstates true performance.
3. **Are prices stale or smoothed?** Unsmooth before annualizing.
4. **Multi-period?** Verify i.i.d. before applying $\sqrt{T}$.
5. **Active overlay?** Use $SR_P^2 = SR_B^2 + IR^2$ to compute the boost.
6. **Optimal active risk?** $\sigma_A^* = (IR/SR_B)\sigma_B$.
7. **Negative numerator?** Sharpe rankings are unreliable; switch metric.
8. **Leverage involved?** Sharpe should be unchanged — if it isn't, find the alpha source.

## Related Concepts

- [[Information Ratio]]
- [[Treynor Ratio]]
- [[Sortino Ratio]]
- [[Maximum Drawdown]]
- [[Active Return]]
- [[Active Risk and Tracking Error]]
- [[Fundamental Law of Active Management]]
- [[Analysis of Active Portfolio Management]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
