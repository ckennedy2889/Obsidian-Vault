---
title: Stress Testing and Scenario Analysis
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, stress-test, scenario-analysis, tail-risk]
aliases: [Stress Testing, Stress Tests, Scenario Analysis, Reverse Stress Testing, Factor Push, Maximum Loss Optimization, Stylized Scenario, Historical Scenario, Hypothetical Scenario]
---

# Stress Testing and Scenario Analysis

## The Real-World Analogy

Imagine you are an architect designing a bridge. **VaR** is like saying *"on a typical breezy day, with 99% confidence, the bridge will sway no more than 4 inches."* Useful, but it tells you nothing about what happens in a hurricane.

**Stress testing** is the engineer dragging in a wind machine and blasting the bridge at 150 mph to see what breaks. **Scenario analysis** is asking *"what if a 7.0 earthquake hits during rush-hour traffic with a fully loaded oil tanker passing underneath?"* And **reverse stress testing** is asking *"what is the smallest combination of forces that would actually collapse this bridge?"* — then checking how plausible each ingredient is.

Each method is designed to answer the question that VaR cannot: *what does the world look like when things actually go wrong?*

## Plain-English Definition

> **Scenario analysis** computes the gain or loss on a portfolio under a *specific assumed* set of market conditions — without attaching a probability to that condition.
>
> **Stress testing** is scenario analysis with **extreme, adverse** assumptions — designed to expose the portfolio's tail vulnerabilities.
>
> **Reverse stress testing** flips the question: instead of *"what would happen if X occurs?"* it asks *"what set of events would have to occur to bankrupt us?"* and then evaluates how plausible those events are.

None of these techniques produce a probability. They produce a **conditional dollar loss**: *if* this scenario occurs, *this* is the impact.

## CFA Definition

| Concept | CFA-Style Definition |
|---|---|
| **Scenario analysis** | Calculation of portfolio gain/loss under a variety of assumed market conditions (severity not specified). |
| **Stress test** | A scenario analysis applying *extreme* shocks to the portfolio's risk factors. |
| **Reverse stress test** | A test that begins with a defined adverse outcome (e.g., bankruptcy, capital breach, covenant violation) and works backward to identify the combination of market shocks that would cause it. |
| **Factor push** | A stress technique that shocks **every** key risk factor simultaneously in its **worst** direction for the portfolio. |
| **Maximum loss optimization** | An algorithmic search across the joint distribution of risk factors to find the precise combination producing the **largest possible** loss. |

See: [[Value at Risk (VaR)]] · [[Conditional VaR (CVaR) and Expected Shortfall]] · [[Tail Risk]]

## Why It Matters

VaR and Expected Shortfall are *statistical* measures — they are only as good as the historical distributions they depend on. In a true crisis (1987, 1998, 2008, 2020), volatilities spike, correlations jump to 1, and the assumptions behind VaR break down. **Humans anchor on normal scenarios**, and statistical models inherit that anchoring.

CFA tests stress and scenario analysis because they are the **complement** to VaR — designed to uncover what VaR systematically hides:

- non-linear payoffs (options, structured products),
- regime shifts (crises with novel correlations),
- liquidity collapses,
- multi-factor catastrophes that no single VaR run will surface.

Risk management is incomplete without both.

## Mechanism

Walk the explanation ladder:

| Step | What it says |
|---|---|
| **Rule** | Always run stress tests / scenarios alongside VaR; treat them as complements, not substitutes |
| **Why the rule exists** | VaR ignores the magnitude of tail losses, assumes stable distributions, and uses normal-period correlations |
| **Mechanism** | Specify a stressed value for each risk factor → revalue the portfolio → report the dollar P&L |
| **Assumptions** | The chosen scenario reflects a meaningful threat; risk-factor mappings to portfolio value are accurate (especially for non-linear instruments) |
| **Failure modes** | Scenarios are subjective; missing scenarios = missing risks; over-reliance on past crises misses *next* crisis |
| **Exam implication** | Stress tests **do not give probabilities**; they give conditional dollar impacts. Use them to set scenario limits and stop-loss limits. |

## Types of Scenarios

| Type | What it is | Example |
|---|---|---|
| **Historical scenario** | Replay an actual past crisis on the *current* portfolio | 1987 Black Monday, 2008 GFC, March 2020 COVID shock, 2022 rates spike |
| **Hypothetical scenario** | Construct a plausible event that hasn't occurred | A simultaneous large EM sovereign default + cyberattack on settlement systems |
| **Stylized scenario** | Apply a uniform standardized shock | Parallel +100bp yield curve shift; −10% global equities; +50% USD |
| **Factor push** | Push *every* risk factor simultaneously in its **worst** direction for the portfolio | Equities −25%, credit spreads +200bp, vol +15 vol points, all together |
| **Maximum loss optimization** | An *algorithm* searches the joint factor space for the combination producing the **largest** loss | Find the (Δ rates, Δ equity, Δ FX, Δ vol) corner that maximizes loss subject to factor bounds |

The first three are **manager-specified**; the last two are **systematic / algorithmic**.

### Reverse Stress Testing

Standard stress test: *"Given shock X, what is our loss?"*

Reverse stress test: *"Given an unacceptable outcome (insolvency, breach), what shock X would have caused it? And how plausible is X?"*

Reverse testing forces the firm to articulate its *failure points* explicitly — covenants, regulatory triggers, liquidity floors — and then quantify how close the world is to producing them.

## Formula / Framework

There is no single formula. The framework is procedural:

```text
1. Define risk factors (equity indices, rates, spreads, FX, vol, etc.).
2. Choose scenario type (historical / hypothetical / stylized / factor push / max-loss / reverse).
3. Specify shock magnitudes for each factor in the scenario.
4. Revalue every position at the new factor levels (full revaluation
   for non-linear instruments — do NOT use linear delta approximations).
5. Aggregate to portfolio P&L = Σ (new value − old value).
6. Report dollar impact and compare to risk limits / capital.
```

For **reverse stress testing**, the procedure is:

```text
1. Define the failure outcome (e.g., loss = capital, equity ratio < limit).
2. Search backward across scenarios for combinations that hit it.
3. Assess plausibility of each combination → which deserve hedging?
```

## Worked Example

A bank holds a portfolio of FX options dependent on the **USD/EUR exchange rate**. The two key risk factors are the spot rate and the implied volatility. The risk team runs a **stylized scenario** matrix over a 2-week horizon.

**Shock grid:**

| Δ Spot \ Δ IV | −2% vol | flat | +2% vol |
|---|---|---|---|
| **−0.06** | −\$1.1M | −\$0.7M | −\$0.4M |
| **−0.04** | −\$0.6M | −\$0.3M | −\$0.1M |
| **−0.02** | −\$0.2M | +\$0.1M | +\$0.4M |
| **0** | +\$0.1M | +\$0.2M | +\$0.5M |
| **+0.02** | +\$0.1M | +\$0.4M | +\$0.7M |
| **+0.04** | −\$0.3M | +\$0.6M | +\$1.4M |
| **+0.06** | −\$0.9M | +\$0.5M | **−\$2.6M** |

**Reading the matrix:** the **maximum loss** in this stylized stress grid is **−\$2.6M**, occurring when the spot rises by 0.06 *and* implied volatility rises by 2 vol points simultaneously. That is the corner of pain.

**Action:** management can now decide whether to (a) hedge the specific gamma/vega exposure in that corner, (b) set a scenario limit prohibiting losses above some threshold in any cell, or (c) accept the exposure and reserve capital against it.

**Reverse-stress version:** suppose the firm cannot tolerate losses worse than −\$2M without breaching a regulatory capital ratio. The reverse test identifies that **only the (+0.06 spot, +2% vol) combination** crosses that line. The firm then asks: *how plausible is this co-movement?* If it is highly plausible (e.g., during ECB intervention episodes), the position must be hedged. If implausible, it can be tolerated.

## Comparisons

### Stress / Scenario vs VaR / CVaR

| Property | **VaR / CVaR** | **Stress / Scenario** |
|---|---|---|
| Output | Probability-weighted (loss at confidence X%) | Conditional dollar loss given the scenario |
| Probability attached? | **Yes** | **No** |
| Captures non-linear payoffs? | Limited (parametric/historical) | **Yes**, via full revaluation |
| Captures regime shifts / new crises? | Poorly (anchored on history) | **Yes** (with hypothetical scenarios) |
| Suited for senior-management communication? | Moderate | **Excellent** ("if X happens we lose \$Y") |
| Subject to model error? | Yes | Yes (subjective scenario design) |

**Key takeaway:** VaR/CVaR answer "how bad with what probability?" Stress tests answer "**if** this happens, how bad?"

### Factor Push vs Maximum Loss Optimization

| Aspect | **Factor Push** | **Max Loss Optimization** |
|---|---|---|
| Method | Push every factor to its individual worst | Algorithmic search over the joint factor space |
| Computation | Simple; deterministic | Heavier; constrained optimization |
| Realism | Often unrealistic (rarely do all factors max-out at once in the worst direction) | More realistic — finds the *plausible* worst combination given joint constraints |
| Result | Pessimistic upper-bound shock | Tighter, more credible worst-case |

### Standard vs Reverse Stress Test — directional flow

```text
Standard:  shock → loss
Reverse:   loss (failure threshold) → shock combinations that cause it
```

## Real-World / Vignette Scenarios

**Scenario 1 — Hedge fund vignette.** A CRO is debating with a PM who says "VaR is fine — we're at \$3M against a \$5M limit." The CRO insists on running 2008 historical and a hypothetical "EM contagion" scenario. The historical scenario shows a \$22M loss. The exam tests: which technique is the CRO using, and why is it appropriate? (Stress testing; because VaR misses regime-shift losses.)

**Scenario 2 — Reverse stress test.** A pension fund has a covenant requiring assets ≥ 105% of liabilities. The CRO works backward and identifies that a simultaneous −20% equity / +150bp credit spread / −50bp rates move would breach the floor. Vignette asks the candidate to identify the technique (reverse stress test) and recommend an action (hedge the specific combination, e.g., via tail-risk overlay).

**Scenario 3 — Factor push at a bank desk.** Risk committee runs a factor-push test where equities −30%, credit spreads +400bp, vol +20 vol pts, USD +10% all simultaneously. Loss is \$110M. Vignette asks whether the test is realistic. Answer: factor push is conservative and unrealistic for joint behavior; **max loss optimization** would generate a more credible (smaller) but well-justified worst case.

**Scenario 4 — Stylized rate shock.** Treasury portfolio is shocked with a parallel +100bp curve move; the report shows a \$45M loss. The question tests recognition of "stylized scenario" and asks for the limitation (uniform shifts ignore curve-shape changes that often accompany rate moves).

## Exam Traps

| Trap | Reality |
|---|---|
| Treat stress test outputs as having a probability | They are **conditional** losses — no probability is attached |
| Conflate factor push with max-loss optimization | Push = each factor at its individual worst; max-loss = algorithm searches joint space |
| Assume VaR and stress test are substitutes | They are **complements** — each catches what the other misses |
| Apply only historical scenarios | Misses *next* crisis; pair with hypothetical and reverse tests |
| Use linear (delta) approximation for option/structured-product stress | **Always full revalue** for non-linear instruments — that's the whole point |
| Confuse standard vs reverse stress test direction | Standard: shock → loss. Reverse: loss → shock |
| Believe stress tests should "replace" VaR | Regulators require **both** — VaR/ES for capital, stress tests for tail vulnerability |
| Treat stylized scenarios as realistic | They are *standardized* shocks for comparability, not necessarily realistic |

## Memory Hook

> **"VaR tells you the weather forecast. Stress tests tell you what happens when the storm actually hits. Reverse stress tests ask: what storm would actually sink us?"**

Mnemonic for the five test types:

> **"H**istorical, **H**ypothetical, **S**tylized, **F**actor push, **M**ax loss" → "**HHSFM** — Headline, Hypothetical, Stylized, Force-all, Maximize."

Direction of reverse: **Outcome first, shock second.**

## Exam-Day Checklist

When a vignette describes risk-management techniques:

1. Does the measure attach a **probability**? → VaR / CVaR. No probability? → stress test / scenario.
2. Is the scenario **a real past crisis**? → historical. **Plausible but unprecedented**? → hypothetical. **A standardized shock**? → stylized.
3. Are **all factors** pushed to their worst simultaneously? → **factor push**.
4. Is an **algorithm finding the worst combination**? → **maximum loss optimization**.
5. Did the analyst **start from a failure outcome** and work backward? → **reverse stress test**.
6. Are **non-linear instruments** present? Confirm full revaluation, not delta approximation.
7. Does the question ask about **limitations**? Mention subjectivity, no probability attached, dependence on past data, sensitivity to scenario design.
8. Does the question ask about **complementarity with VaR**? Stress tests catch what VaR ignores: tail magnitude, regime shifts, non-linearities.

## Related Concepts

- [[Value at Risk (VaR)]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
- [[Incremental VaR]]
- [[Marginal VaR]]
- [[Tail Risk]]
- [[Coherent Risk Measure]]
- [[Sensitivity Analysis]]
- [[Drawdown]]
- [[Risk Budgeting]]
- [[Liquidity Risk]]
- [[Measuring and Managing Market Risk]]
