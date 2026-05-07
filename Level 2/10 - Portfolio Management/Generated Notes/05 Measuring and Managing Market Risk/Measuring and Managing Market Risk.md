---
title: Measuring and Managing Market Risk
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, risk-management, VaR, sensitivity, scenario-analysis]
aliases: [Market Risk Measurement, VaR, Value at Risk, Risk Management, Greeks, Stress Testing]
---

# Measuring and Managing Market Risk

> [!abstract] The big idea
> Markets do not politely inform you *when* they will break your portfolio or *by how much*. So risk management becomes a portfolio of three complementary lenses. **Value at Risk (VaR)** answers "how bad is a typical bad day?" — a probabilistic statement about expected losses. **Sensitivity measures** (beta, duration, the Greeks) answer "how much does my P&L wiggle per unit of factor change?" — a local calculus statement. **Scenario analysis** answers "if Lehman 2008 happened tomorrow, would I survive?" — a discrete what-if statement with no probability attached. None of them is sufficient alone; risk managers run all three in parallel. Above all, the governance wrapper — risk budgets, position limits, stop-losses, RAROC — translates numbers into *decisions*.

![[risk-measurement-framework.png]]

---

## A real-world grounding: March 2020

Picture a balanced $100M portfolio the afternoon of **February 19, 2020**. Pre-COVID, its one-day 95% VaR — the worst loss you would expect on 19 out of 20 days — is around $1.2M. Comfortable. Three weeks later, the S&P drops 12% in a single session (March 16, 2020); the portfolio loses roughly $8M in a day. That single loss is ~**6.7× the VaR** on a day that "shouldn't" exceed VaR more than once a month.

What went wrong? Nothing about VaR was "wrong" — it told you what to expect on a normal bad day. It *never* promised to describe the tail. This is precisely why the curriculum insists that VaR is the *starting point*, and why sensitivity numbers (how much does a 1% vol spike cost me?) and scenarios (what does a repeat of 1987 do?) sit next to it on every risk dashboard. Market risk measurement is a **portfolio of measurements**, not a single number.

---

## LOS 1 — Explain use of Value at Risk (VaR)

**Value at Risk** is the answer to three simple questions packaged into one number:

$$\Pr\bigl[\,\text{Loss} \geq \text{VaR}\,\bigr] = p$$

A VaR statement *must* specify three elements:

| Element | Example | Why it matters |
|---|---|---|
| **Loss size (currency)** | \$6.5M | The "pain number" |
| **Probability** | 5% | The confidence level — 95% (p=5%), 99% (p=1%), 99.9% |
| **Time horizon** | 1 day | Daily for trading desks, 10-day under Basel, monthly for asset managers |

**Canonical reading**: *"The one-day 5% VaR is \$6.5 million"* = over the next trading day, there is a 5% probability of losing **at least** \$6.5M. It says **nothing** about how bad the loss could be once you breach it. That gap is exactly why CVaR exists (LOS 3).

> [!tip] Mental model
> VaR draws a line on the left tail of the return distribution and says "below this line lives the worst 5% of days." It does *not* describe what those days look like — only that there are enough of them to matter.

### Strengths & limitations (this is examinable)

| ✅ Why risk managers love VaR | ❌ Why they distrust it |
|---|---|
| Single, intuitive number ("\$X at p% over T days") | Silent on **tail magnitude** — says nothing past the cut-off |
| Compares across desks, asset classes, firms | Highly sensitive to **method** chosen (three answers below) |
| Aggregates all market risks into one metric | **Historical data dependency** — the past may not repeat |
| Widely accepted for **regulation** (Basel, SEC) | Often understates risk in crises (fat tails, correlation jumps) |
| Useful for **risk budgeting** & capital allocation | Can be **gamed** — push losses beyond the cutoff with options |

---

## LOS 2 — Compare the three VaR estimation methods

There is no single "VaR"; there are three recipes, each with its own assumptions. If the method isn't stated, the number isn't interpretable.

### Method 1 — Parametric (Variance-Covariance)

**Assumption**: Returns are **normally distributed** with known mean $\mu$ and std dev $\sigma$.

$$\text{VaR}_{\alpha} = \bigl(z_{\alpha}\,\sigma - \mu\bigr) \times V$$

where $V$ is portfolio value and $z_{\alpha}$ is the standard-normal critical value:
- 95% VaR → $z = 1.645$
- 99% VaR → $z = 2.326$
- 99.9% VaR → $z = 3.090$

> [!example] Worked example — Parametric VaR
> Portfolio value $V = \$10M$; daily $\mu = 0.05\%$, $\sigma = 1.2\%$; 1-day 95% VaR.
>
> $\text{VaR} = (1.645 \times 0.012 - 0.0005) \times \$10M = (0.01974 - 0.0005) \times \$10M = \$192{,}400$
>
> *"There is a 5% chance of losing at least \$192,400 tomorrow."*

| Pros | Cons |
|---|---|
| Fast — closed-form | **Normality fails** in crises (fat tails) |
| Needs only $\mu$, $\sigma$, $\rho$ | Poor for **options** (non-linear payoffs) |
| Clean for simple portfolios | Ignores skew, kurtosis |

### Method 2 — Historical Simulation

Take the last $N$ daily returns (e.g., 500 days = ~2 years), apply each to today's positions, sort losses worst-to-best, and pick the $p$-th percentile.

> [!example] Worked example — Historical VaR
> Using 250 trading days of portfolio P&L, sorted from worst to best. For 99% VaR, you take the 3rd worst day (since 1% × 250 = 2.5, round up). If the 3rd worst day was a $450K loss, **1-day 99% VaR = \$450K**.

| Pros | Cons |
|---|---|
| **No distributional assumption** | Assumes past distribution will repeat |
| Captures fat tails / skew naturally | Highly dependent on **window length** |
| Simple to explain | Misses shocks not in the window (e.g., pre-2008 samples had no GFC) |

### Method 3 — Monte Carlo Simulation

Specify a statistical process for risk factors (need not be normal), generate 10,000+ random paths, revalue the portfolio in each path, rank the losses, and read off the $p$-th percentile.

| Pros | Cons |
|---|---|
| **Most flexible** — any distribution, any payoff | Computationally expensive |
| Handles options & exotic derivatives | "Garbage in, garbage out" — needs good inputs |
| Captures non-linear, path-dependent risk | Black box — harder to audit |

### Side-by-side

| Method | Distribution | Best for | Worst for |
|---|---|---|---|
| Parametric | Assumed normal | Linear, large portfolios | Options, fat-tail regimes |
| Historical | Empirical (past data) | Whatever happened last year | Truly novel shocks |
| Monte Carlo | Any chosen model | Options, path-dependent | When you can't trust the inputs |

> [!tip] Mnemonic — "PHM" (Parametric, Historical, Monte Carlo)
> **P**arametric = "trust the **formula**." **H**istorical = "trust the **past**." **M**onte Carlo = "trust the **model**." Each one delegates trust somewhere different — and each can fail.

---

## LOS 3 — Advantages, limitations, extensions of VaR

### Extensions you must know

| Measure | What it answers | Key insight |
|---|---|---|
| **CVaR** (Conditional VaR, a.k.a. **Expected Shortfall**) | "Given we exceed VaR, what's the *average* loss?" | Captures tail *magnitude*; always ≥ VaR |
| **IVaR** (Incremental VaR) | "How does total VaR change if I add this position?" | Discrete before/after difference — used in portfolio construction |
| **MVaR** (Marginal VaR) | "How does VaR change per \$1 added to this position?" | Calculus derivative — used for **risk budgeting** |
| **Relative VaR** | "How much could my portfolio underperform the benchmark?" | Also called **TE-VaR** — dispersion of $R_P - R_B$ |

> [!tip] Mnemonic for VaR family
> **"Classic → Beyond → Before → Besides"**:
> **V**aR (classic), **C**VaR (beyond it), **I**ncremental (before/after), **M**arginal (besides — derivative), Relative (versus benchmark).

### Why CVaR is rising in popularity

VaR is *blind* to what happens past the cutoff — doubling the worst 5% of losses doesn't change 95% VaR one dollar. CVaR (Expected Shortfall) averages across the tail, so it *does* move. Basel moved to **Expected Shortfall** for market risk capital post-2019 precisely because Lehman taught regulators that knowing the cutoff was not enough — you need the **expected tail**.

---

## LOS 4 — Sensitivity risk measures

Sensitivity measures are **derivatives** — they tell you how portfolio value moves per *unit change* in a risk factor. Local and linear (first-order) or local and quadratic (second-order). Fast, transparent, but they break down for large moves or non-linear payoffs.

### Equity: Beta

$$\beta_i = \frac{\text{Cov}(R_i, R_M)}{\text{Var}(R_M)}$$

Beta tells you how a stock moves per 1% market move. $\beta = 1.3$ → stock moves 1.3% for every 1% market move, on average.

### Fixed Income: Duration, Convexity, PVBP

- **Modified Duration** (1st-order) — %-change in price per 1% change in yield
- **Convexity** (2nd-order correction) — captures curvature; adds precision for large rate moves

$$\%\Delta P \approx -\text{ModDur} \times \Delta y + \tfrac{1}{2} \times \text{Convexity} \times (\Delta y)^2$$

- **PVBP / Money Duration** — \$-change per 1 bp move (PV01): $\text{PVBP} = \text{ModDur} \times P \times 0.0001$

### Options: The Greeks

| Greek | Symbol | What it measures | Intuition |
|---|---|---|---|
| **Delta** | $\Delta$ | Option price change per \$1 change in underlying | Directional exposure |
| **Gamma** | $\Gamma$ | Delta change per \$1 change in underlying | Second-order — delta's speed |
| **Vega** | $\nu$ | Price change per 1% change in implied vol | Vol exposure |
| **Theta** | $\Theta$ | Price change per 1 day passage of time | Time decay (usually negative for long options) |
| **Rho** | $\rho$ | Price change per 1% change in interest rate | Rate exposure |

> [!tip] Delta-gamma approximation
> For options, a first-order delta estimate misses curvature. The delta-gamma approximation adds the convexity term:
>
> $$\Delta V \approx \Delta \cdot \Delta S + \tfrac{1}{2}\Gamma (\Delta S)^2$$
>
> This is the option-world twin of duration + convexity in fixed income.

### Strengths & limitations (symmetric with VaR)

| ✅ Why sensitivity measures matter | ❌ Why they aren't enough |
|---|---|
| **Transparent** — no distributional assumption | **Local** — linearization fails far from current price |
| **Fast** — closed-form derivatives | Assumes risk factors move *independently* — correlation breakdowns not captured |
| **Per-factor** decomposition (hedge each one) | No probability attached — doesn't tell you *how likely* a 5% move is |
| Great for **hedging** (e.g., delta-neutral) | Breaks for **non-linear** payoffs (e.g., digital options) |

---

## LOS 5 — Advantages & limitations of sensitivity measures

Same trade-off as above, more formally:

**Advantages**
- Easier to compute than VaR — no simulation required
- Easier to **interpret** — "my \$50M bond portfolio has \$25k PV01"
- Per-factor: lets you **hedge each risk separately** (delta-hedge, duration-match)
- No distributional assumption

**Limitations**
- **Local only** — valid for small moves
- **Non-probabilistic** — doesn't tell you *how likely* a given move is
- **Incomplete** — captures one factor at a time, ignores joint moves
- **Model-dependent** — Greeks depend on your options model (Black-Scholes, etc.)

> [!example] Fixed-income PVBP in action
> A \$100M portfolio with mod duration 6.5 has PVBP:
>
> $\text{PVBP} = 6.5 \times \$100M \times 0.0001 = \$65{,}000$
>
> *"A 1-bp move in yields costs me \$65k."* Clean. No probability, no scenario — just the local slope.

---

## LOS 6 — Scenario Analysis (historical & hypothetical)

**Scenario analysis** revalues the entire portfolio under a large, *joint* shock to many factors at once. Unlike VaR, it has **no probability** attached — it's a discrete "what-if," not a statistical distribution. Unlike sensitivity measures, it handles large, *joint*, non-linear moves.

### Historical scenarios

Replay a real past crisis at today's positions.

| Scenario | What happened | Why it still matters |
|---|---|---|
| **Black Monday 1987** | S&P −22% in a single day | Tests portfolio against severe one-day equity crash |
| **Asia crisis 1997** | Thai baht devaluation → EM contagion | Tests EM FX & sovereign exposure |
| **Dot-com crash 2000** | Nasdaq −78% over 2 years | Tests growth/tech concentration |
| **GFC 2008** | Lehman, credit freeze, 60% S&P drawdown | Multi-asset, liquidity-correlation regime shift |
| **COVID March 2020** | S&P −34% in 5 weeks; oil futures negative | Fat-tail, policy-response scenario |

### Hypothetical scenarios

Construct a shock that *hasn't happened* but is plausible.

Examples:
- "Fed hikes 300 bps overnight"
- "Equities −30% + credit spreads +300 bps + USD strengthens 10%"
- "Oil +\$50/bbl on supply disruption"
- "China devalues RMB 15%"

### Reverse stress testing

Turn the question upside-down: *"What combination of shocks would cause us to lose \$X?"* Instead of starting with a scenario and computing the loss, you start with an intolerable loss and back out the scenario. Used to find **hidden vulnerabilities** — the scenario you didn't think to run.

### Advantages vs VaR

| Scenario wins when... | VaR wins when... |
|---|---|
| Factors correlate in ways VaR's covariance matrix misses | Day-to-day risk budgeting across many desks |
| Non-linear payoffs (options, structured products) | You need a single summary number for regulators |
| Capital adequacy and survival testing | You need probability attached |
| Testing events with no historical analog | Broad market risk reporting |

> [!tip] Reverse stress test mantra
> Regular stress test: *"Here's a scenario — what's the loss?"*
> Reverse stress test: *"Here's the loss we can't survive — what's the scenario?"*

---

## LOS 7 — Sensitivity, scenario & VaR used together

No single measure is adequate. A good risk dashboard uses all three, and each addresses a weakness in the others.

| Lens | Strength | Weakness covered by... |
|---|---|---|
| **VaR** | Probabilistic; single number; aggregates risks | Tail silence → **CVaR / scenario** |
| **Sensitivity** | Transparent; per-factor hedging | No probability → **VaR**; no big moves → **scenario** |
| **Scenario** | Handles large joint shocks, tail events | No probability; subjective → **VaR / sensitivity** |

> [!example] Why you need all three
> Pre-GFC, a bank's 1-day 99% VaR might say "worst expected loss is \$20M." Sensitivity says "a 100 bp credit spread widening costs us \$8M." Scenario says "replay Lehman → \$150M loss." VaR *alone* would have lulled management to sleep; scenario alone would have been dismissed as "never happens"; sensitivity alone wouldn't have combined the shocks. **Together** they force a discussion about capital adequacy.

### Constraints — the governance wrapper

Measurement is useless without *rules* that shape decisions. The curriculum identifies four classical constraint types:

| Constraint | What it limits |
|---|---|
| **Risk budgeting** | Total risk (VaR, vol, TE) allocated across units |
| **Position limits** | Maximum \$ or % in any single position or sector |
| **Scenario limits** | Maximum loss under specified stress scenarios |
| **Stop-loss limits** | Automatic position closure once a loss threshold is hit |

### Capital-allocation measures

| Measure | Formula / concept |
|---|---|
| **Economic Capital** | Capital needed to absorb losses at chosen confidence (e.g., 99.9% over 1 yr) |
| **RAROC** | $\text{RAROC} = \dfrac{\text{Risk-adjusted return}}{\text{Economic capital}}$ — compares returns on a *per-unit-of-risk* basis |
| **Risk-weighted position sizing** | Allocate more capital to positions with higher risk-adjusted return |

> [!tip] Mnemonic for constraints — **"R-P-S-S"**
> **R**isk budget, **P**osition limit, **S**cenario limit, **S**top-loss. In rough order from top-down strategic (R) to bottom-up tactical (S).

---

## LOS 8 — Backtesting & benchmarking

### Backtesting

Check your VaR model by comparing **predicted** vs **actual** tail breaches.

- Over 250 trading days, a 99% VaR should be exceeded ~2.5 days.
- If your 99% VaR is breached 15 times in a year → model **understates risk**.
- If breached 0 times → model may be **too conservative** (wasting capital).

**Basel backtesting zones** (for a 99% 1-day VaR over 250 days):

| Zone | # Breaches | Interpretation |
|---|---|---|
| **Green** | 0-4 | Model is accurate |
| **Yellow** | 5-9 | Warning; increase capital multiplier |
| **Red** | 10+ | Model unreliable; regulatory escalation |

### Benchmarking

Compare the model's numbers against simpler reference models or peer banks to sanity-check. If your VaR is systematically half the peer-bank average for the same portfolio, *someone* is mis-measuring.

---

## LOS 9 — Institutional risk measures (banks)

Banks worry about **market risk on trading books, liquidity risk, credit risk, and regulatory capital**. Primary measures:

| Measure | What it does |
|---|---|
| **VaR** (trading book) | Daily risk budgeting across trading desks |
| **Stressed VaR** | VaR calibrated to a historical stress period (Basel III) |
| **Expected Shortfall** | Replacing VaR in Basel's market-risk capital calc post-2019 |
| **Economic Capital** | Tail-loss capital across all risk types |
| **Liquidity Coverage Ratio (LCR)** | High-quality liquid assets vs 30-day stressed outflows |
| **Leverage Ratio** | Tier 1 capital / total (un-risk-weighted) exposures |
| **Sensitivities (DV01, CS01)** | Dollar change per 1-bp move in rates / credit spreads |

Banks run **daily** VaR, **weekly** stress tests, and **monthly-to-quarterly** Economic Capital calculations. Regulators (Fed, ECB, PRA) require **Comprehensive Capital Analysis & Review (CCAR)** — severe hypothetical scenarios over multi-year horizons.

---

## LOS 10 — Institutional risk measures (asset managers, pensions, insurers)

### Traditional asset managers

- **Tracking Error (TE)** — dispersion of $R_P - R_B$; primary active-risk metric
- **Active share** — fraction of holdings different from benchmark
- **Sensitivity measures** for style drift (beta, duration)
- **Relative VaR / TE-VaR** — VaR of active return

### Hedge funds

- **VaR**, **Expected Shortfall**
- **Sensitivity / Greeks** (for derivatives-heavy books)
- **Leverage ratio** — gross exposure / NAV
- **Scenario analysis** for tail events
- **Drawdown** — peak-to-trough decline

### Pension funds — Surplus at Risk

Pensions care about **assets vs liabilities**, not assets alone.

$$\text{Surplus} = \text{Assets} - \text{PV(Liabilities)}$$

- **Surplus at Risk (SaR)** — VaR-style measure on the *surplus*
- **Liability-driven investing (LDI)** — match duration/convexity of assets to liabilities
- Cares about **real** returns (inflation-linked liabilities)

### Insurers

Two flavors with different liability profiles:

| Life insurers | P&C insurers |
|---|---|
| Long-dated, predictable liabilities | Short-dated, catastrophe-driven |
| ALM — match asset & liability duration | Capital for tail events (hurricanes, etc.) |
| Minimum guaranteed returns on policies | Combined ratio (losses + expenses) / premiums |

Both use:
- **Economic Capital** (often 99.5% or 99.9%)
- **ALM** — asset-liability matching
- **Scenario analysis** (stress-testing policy reserves)
- **VaR** (on investment portfolio)

### Summary table

| Institution | Primary market-risk measures | Secondary focus |
|---|---|---|
| **Banks** | VaR, Stressed VaR, ES, Economic Capital | LCR, Leverage, Sensitivities |
| **Asset managers** | Tracking Error, Active Share | Sensitivities, Relative VaR |
| **Hedge funds** | VaR, ES, Greeks, Leverage | Drawdown, Scenario |
| **Pension funds** | Surplus at Risk, ALM | Duration match, inflation hedging |
| **Insurers** | Economic Capital, ALM | VaR on invested assets |

---

## LOS 11 — Risk budgeting, position limits, and other constraints

Already introduced above; here's the deeper layer.

### Risk budgeting

Allocate total risk (measured as vol, VaR, or TE) across units (traders, strategies, asset classes). The sum of individual budgets should equal or be less than total tolerance, after accounting for diversification.

$$\text{Total VaR} \leq \sum_i w_i \cdot \text{VaR}_i \quad \text{(ignoring correlation)}$$

In practice, use **Marginal VaR** to allocate because risk is *not* additive — diversification reduces total VaR below the sum of parts.

### Position limits

Hard caps on:
- Max \$ exposure to any issuer
- Max % of portfolio in any sector/country
- Max % of average daily volume (liquidity limit)
- Max notional in any single derivative

**Why?** Concentration risk — VaR can miss idiosyncratic risk if one position is huge.

### Scenario limits

"Loss under Scenario X must not exceed \$Y." Forces the desk to **hedge** or **reduce** positions that would break under the specified stress. Different from VaR limits because scenarios are **discrete and extreme**.

### Stop-loss limits

Automatic: if a position loses \$X, close it. Trade-off:
- ✅ Limits bleeding
- ❌ Can lock in losses during temporary drawdowns; may be gamed in low-liquidity markets

### Capital allocation

- **Economic capital** — allocate capital to each business unit based on its contribution to tail risk
- **RAROC** — rank businesses by *risk-adjusted* return; reallocate capital toward high-RAROC units

---

## LOS 12 — Applications of risk measures

Risk measurement is only useful if it drives **decisions**. Three main application areas:

### 1. Portfolio construction

- Use **Marginal VaR** to decide which positions add the most risk per \$
- Use **IVaR** to evaluate a proposed new position before adding it
- Use **tracking error** to keep active exposures within mandate
- Use **stress testing** to check tail exposures during optimization

### 2. Capital allocation

- Allocate economic capital across businesses using **RAROC**
- Replace intuition-based allocation with *risk-adjusted* allocation
- Ensure regulators, rating agencies, and shareholders see sufficient buffer

### 3. Performance attribution & compensation

- Base trader compensation on **risk-adjusted return**, not raw return
- Use **Sharpe**, **Information Ratio**, **RAROC** rather than P&L alone
- Discourages high-leverage, high-risk strategies that produce lucky wins

### Tying it together — the governance cycle

```
Measure risk → Set limits → Monitor daily →
Breach? → Force hedge / unwind / capital increase →
Post-mortem & model update → Measure risk (repeat)
```

Risk measurement without action is useless; risk action without measurement is reckless.

---

## Formula cheat-sheet

$$\boxed{\;\Pr[\text{Loss} \geq \text{VaR}] = p\;}$$

$$\boxed{\;\text{VaR}_{\alpha} = (z_{\alpha}\sigma - \mu) \cdot V\;}$$

$$\boxed{\;\text{CVaR} = E[\text{Loss} \mid \text{Loss} \geq \text{VaR}]\;}$$

$$\boxed{\;\beta_i = \frac{\text{Cov}(R_i, R_M)}{\text{Var}(R_M)}\;}$$

$$\boxed{\;\%\Delta P \approx -\text{ModDur}\cdot\Delta y + \tfrac{1}{2}\text{Conv}\cdot(\Delta y)^2\;}$$

$$\boxed{\;\text{PVBP} = \text{ModDur} \cdot P \cdot 0.0001\;}$$

$$\boxed{\;\Delta V \approx \Delta\cdot\Delta S + \tfrac{1}{2}\Gamma(\Delta S)^2\;}$$

$$\boxed{\;\text{RAROC} = \frac{\text{Risk-adjusted return}}{\text{Economic capital}}\;}$$

---

## Quick mnemonics

| Mnemonic | What it remembers |
|---|---|
| **"PHM"** | Parametric, Historical, Monte Carlo — the three VaR methods |
| **"CVaR = C for Cruel"** | CVaR averages the *cruel* (bad) tail that VaR ignores |
| **"R-P-S-S"** | Risk budget, Position limit, Scenario limit, Stop-loss |
| **"Δ Γ ν Θ ρ"** | Greeks: Delta, Gamma, Vega, Theta, Rho — directional, curvature, vol, time, rates |
| **"Reverse test = reverse question"** | "What breaks us?" not "what happens if X?" |

---

## Related notes

- [[Analysis of Active Portfolio Management]] — Information Ratio, TE, active risk (relative VaR family)
- [[Using Multifactor Models]] — factor exposures are the inputs to scenario analysis
- [[Economics and Investment Markets]] — business-cycle scenarios drive hypothetical stress tests

---

## Final frame

Market risk measurement is a **triangulation problem**. No single number captures what a portfolio can lose — VaR gives you the *typical bad day*, sensitivity gives you the *local slope*, scenarios give you the *tail survivor test*. The sophisticated practitioner runs **all three** every day, cross-checks them against **backtesting**, wraps them in **risk budgets / position limits / stop-losses**, and ultimately uses them to drive **capital allocation and compensation**. Numbers without decisions are scorekeeping; decisions without numbers are gambling. Good risk management is neither.
