---
title: Incremental VaR (IVaR)
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, VaR, position-sizing]
aliases: [IVaR, Incremental VaR, Incremental Value at Risk]
---

# Incremental VaR (IVaR)

## The Real-World Analogy

Picture a chef tasting a giant pot of stew. They want to know: *"If I add a whole jar of chili paste, how much hotter will the stew get?"* They can't just measure the chili's heat in isolation — once it's in the pot, it interacts with the broth, the cream, the other spices. The only way to know is to taste the stew **before** and **after** adding the jar, and report the **difference**.

That difference is **Incremental VaR**. The chili's "heat alone" = standalone VaR. The change in the *whole pot's* heat from adding it = IVaR. They are not the same number, because the pot's other ingredients dampen (or amplify) the chili's contribution.

## Plain-English Definition

> **Incremental VaR (IVaR) is the change in total portfolio VaR caused by a *discrete* change in a position — adding it, removing it, or significantly resizing it.**

It answers: *"If I make this specific trade, by how much will the portfolio's VaR move?"*

It is the only number that tells a portfolio manager the **true risk impact of a trade** in the context of the existing portfolio's correlations and concentrations.

## CFA Definition

> **Incremental VaR (IVaR)** measures the impact on a portfolio's VaR from a discrete change in a position (e.g., adding, removing, or resizing). It is calculated as:

$$
\boxed{\,IVaR \;=\; VaR_{\text{new portfolio}} \;-\; VaR_{\text{old portfolio}}\,}
$$

To compute it, the portfolio's full VaR must be re-calculated *after* the proposed trade — incorporating the new position's volatility **and** its covariance with every existing position.

See: [[Value at Risk (VaR)]] · [[Marginal VaR]] · [[Component VaR]] · [[Relative VaR]]

## Why It Matters

CFA tests IVaR because portfolio managers do not buy assets in isolation — they buy them *into a context*. The standalone risk of an asset (its solo VaR) routinely overstates or understates its risk impact on a real portfolio. IVaR is the bridge between **per-asset risk** and **whole-portfolio risk** when a discrete trade is on the table.

It is also the metric used to police a **risk budget**: before approving a trade, a CRO asks "what is the IVaR?" If it pushes the firm beyond its VaR limit, the trade is denied or downsized.

## Mechanism

| Step | What it says |
|---|---|
| **Rule** | $IVaR = VaR_{\text{new}} - VaR_{\text{old}}$ |
| **Why the rule exists** | Diversification / correlation means a position's *contribution* to portfolio risk is rarely equal to its standalone risk |
| **Mechanism** | Recompute the portfolio VaR end-to-end with the proposed position included; compare to the original VaR |
| **Assumption** | Underlying VaR methodology (parametric, historical, Monte Carlo) is internally consistent across both calculations |
| **Failure mode** | Volatilities and correlations shift between the two calculations (regime change); estimation error in tail |
| **Exam implication** | Use IVaR (not standalone VaR) to judge how a discrete trade changes total portfolio risk |

### Why a position's IVaR is rarely equal to its standalone VaR

Adding asset $i$ to a portfolio raises VaR by the new position's standalone risk *minus* the diversification benefit from its correlations with the existing book. If the new asset has low or negative correlation with the existing portfolio, IVaR can be a small fraction of standalone VaR — or even **negative** (the position is a net hedge).

## Formula / Framework

### Core formula

$$
IVaR \;=\; VaR_{\text{portfolio with the trade}} \;-\; VaR_{\text{portfolio without the trade}}
$$

**No partial-derivative shortcut applies** — IVaR is a *discrete-difference* concept. You must run the VaR engine twice.

### Sign interpretation

| IVaR | Interpretation |
|---|---|
| **> 0** | Trade adds risk to the portfolio |
| **= 0** | Trade is risk-neutral at the portfolio level |
| **< 0** | Trade is a **net hedge / diversifier** — total portfolio VaR drops |

### IVaR within the VaR-extension family

| Measure | What it answers | When to use |
|---|---|---|
| **Marginal VaR (MVaR)** | Rate of change in VaR for a *tiny* change in weight (a partial derivative, $\partial VaR / \partial w_i$) | Optimization / "what if I tweak weight by 1%?" |
| **Incremental VaR (IVaR)** | Change in VaR from a *discrete* trade (add / remove / resize) | "Should I do this specific trade?" |
| **Component VaR** | Contribution of position $i$ to *current* total portfolio VaR; **sums** to total VaR | Risk attribution / risk budgeting |

A useful identity: $\text{Component VaR}_i = MVaR_i \times \text{position value}_i$, and $\sum_i \text{Component VaR}_i = \text{Portfolio VaR}$. **IVaRs do not sum to portfolio VaR.**

## Worked Example

A portfolio manager runs a \$10,000,000 equity fund.

**Current state:**
- Portfolio 1-month 95% VaR = **\$500,000**

**Proposed trade:** add a \$2,000,000 allocation to an Emerging Markets (EM) fund.
- EM fund **standalone** 1-month 95% VaR = **\$200,000**
- EM fund has *low* correlation with the current portfolio.

After fully re-running the VaR engine including the EM fund and its correlation matrix:
- New portfolio 1-month 95% VaR = **\$560,000**

**Incremental VaR:**

$$
IVaR \;=\; \$560{,}000 \;-\; \$500{,}000 \;=\; \boxed{\$60{,}000}
$$

**Interpretation:**

- Adding \$200k of standalone risk only increased portfolio VaR by \$60k.
- The other **\$140k of standalone risk got diversified away** — the EM fund moves out of phase with the existing portfolio.
- Compare to a hypothetical second candidate (a US large-cap ETF) with standalone VaR of only \$120k but IVaR of \$110k (high correlation). The EM fund — *with bigger standalone risk* — is the **lower** marginal contribution. IVaR is the only metric that surfaces this.

If the firm's risk budget allows only \$50k of additional VaR, the trade must be **downsized** (e.g., to \$1.6M instead of \$2M).

### A negative-IVaR variant

Suppose the same PM, instead of EM equities, considers adding \$2M of long-duration Treasuries that move *opposite* the equity portfolio in stress. After recalculation:

- New portfolio VaR = \$470,000
- $IVaR = \$470{,}000 - \$500{,}000 = -\$30{,}000$

The Treasury position is a **net hedge**: its standalone risk is more than offset by its negative correlation. Vignettes test recognition of this.

## Comparisons

### IVaR vs Standalone VaR

| Aspect | **Standalone VaR** | **IVaR** |
|---|---|---|
| Context | Position in isolation | Position *inside* the actual portfolio |
| Captures correlation? | No | Yes |
| Used for trade approval? | No (misleading) | **Yes** |
| Can be negative? | No | **Yes** (if position is a hedge) |

### IVaR vs Marginal VaR vs Component VaR

| Property | **MVaR** | **IVaR** | **Component VaR** |
|---|---|---|---|
| Change size | Infinitesimal | Discrete | (Current contribution) |
| Math | Partial derivative | Difference of two VaR calculations | $MVaR_i \times w_i \cdot V$ |
| Sums to portfolio VaR? | (No — dimensional) | **No** | **Yes** |
| Best for | Optimization | Trade decisions | Risk attribution |

## Real-World / Vignette Scenarios

**Scenario 1 — Trade approval.** A vignette gives a CRO three proposed trades with their IVaRs (\$80k, \$30k, \$120k) and a remaining VaR budget of \$100k. **Trade B (\$30k IVaR)** is approved; trade C is denied; trade A may be downsized.

**Scenario 2 — Diversifier vs adder.** A table shows two assets: Asset X has standalone VaR \$500k and IVaR \$400k; Asset Y has standalone VaR \$300k but IVaR \$350k (correlation amplifies it). **Asset Y is the larger risk contributor**, despite the smaller solo number. Pick Y as "adds the most risk."

**Scenario 3 — Hedging.** A vignette describes adding a put-option overlay; IVaR is reported as **negative**. Recognize this means the overlay reduces total portfolio VaR and may justify a higher risk budget elsewhere.

**Scenario 4 — MVaR vs IVaR.** The vignette specifies "increase exposure to position A by 1%." The right metric is **MVaR**. If it says "add a brand-new \$5M allocation," the right metric is **IVaR**. The exam tests this distinction directly.

## Exam Traps

| Trap | Reality |
|---|---|
| Treat IVaR = standalone VaR of the position | Standalone VaR ignores correlation; IVaR captures it |
| Sum the IVaRs of all positions and expect portfolio VaR | **Component VaRs** sum to portfolio VaR; IVaRs do **not** |
| Use IVaR for a 1% weight tweak | That's **MVaR** — partial derivative, not discrete |
| Assume IVaR is always positive | It can be **negative** when the new position hedges the existing book |
| Use the same VaR figure for "before" and just add asset's solo VaR | Must **fully re-compute** portfolio VaR including new covariances |
| Confuse IVaR with **CVaR (Conditional VaR)** | CVaR = expected loss in the tail; IVaR = change in VaR from a trade. **Completely different concepts** that share the letter "C/I" near "VaR" |
| Assume the bigger standalone VaR position adds more portfolio risk | The **correlation profile** can flip the ranking; compare IVaRs |

## Memory Hook

> **"IVaR = VaR_after − VaR_before. Period."**

To keep the trio straight:

> **"Marginal = nudge. Incremental = trade. Component = share."**

Or visualize: the chef tastes the stew before and after the chili — that's IVaR. Asking "how much hotter per pinch?" is MVaR. Asking "how much of the stew's current heat comes from the chili?" is Component VaR.

## Exam-Day Checklist

When a vignette presents a portfolio risk decision:

1. Is the change **discrete** (full add / remove / resize)? → **IVaR**.
2. Is the change **infinitesimal** (1% tweak, optimization)? → **MVaR**.
3. Is the question about each position's **contribution to current VaR** that sums to total? → **Component VaR**.
4. Does the question ask which trade adds the most risk? Compare **IVaRs**, not standalone VaRs.
5. Is the IVaR negative? Recognize it as a **hedge / diversifier**.
6. Is the firm's **VaR budget** breached after the trade? Resize until $VaR_{\text{old}} + IVaR \le \text{limit}$.
7. Watch for trap: candidates conflating **IVaR** (incremental) with **CVaR** (conditional/tail).

## Related Concepts

- [[Value at Risk (VaR)]]
- [[Marginal VaR]]
- [[Component VaR]]
- [[Relative VaR]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
- [[Risk Budgeting]]
- [[Correlation]]
- [[Diversification]]
- [[Stress Testing]]
- [[Measuring and Managing Market Risk]]
