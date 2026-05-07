---
title: Backtesting and Simulation
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, backtesting, simulation, Monte-Carlo, historical-simulation, sensitivity-analysis]
aliases: [Backtesting, Monte Carlo Simulation, Historical Simulation, Walk-Forward, Strategy Testing]
---

# Backtesting and Simulation

> [!abstract] The big idea
> Before you commit real money to a new investment strategy, you need to know the answer to a simple but loaded question: *"If I had run this yesterday, would I have made or lost money — and how confident am I that tomorrow looks like yesterday?"* The industry's answer is a four-part testing toolkit. **Backtesting** replays history in order — "what would have happened?" **Historical simulation** shuffles that same history — "what else could have happened with the same underlying returns?" **Monte Carlo simulation** invents synthetic histories from a chosen probability model — "what could happen under never-seen conditions?" **Sensitivity analysis** asks the meta-question — "what if my assumptions are wrong?" Each answers a different question; the mature risk process runs all four, each with eyes open to its own biases.

![[backtesting-workflow.png]]

---

## A real-world grounding: the 1986-2019 Value backtest

Imagine an analyst in late 2019 proposing a classic **Value** strategy to an investment committee: *"Buy the 20% of US stocks with the highest trailing earnings yield (1 ÷ P/E), short the 20% with the lowest, rebalance monthly."* The committee doesn't want a hunch — they want evidence. So the analyst runs a backtest from **January 1986 to December 2019** on the Russell 3000 universe. Here's what they discover:

| Statistic | Value |
|---|---|
| Annualized return | **9.24%** |
| Annualized volatility | 12.36% |
| Sharpe ratio | **0.75** |
| Maximum drawdown | **−41.04%** (dot-com bust & GFC) |
| Return distribution | **Negatively skewed** — rare but severe losses |

On paper, 0.75 Sharpe is solid. But the equity curve reveals a stomach-churning 41% drawdown, and the distribution has a nasty left tail. Would the committee approve the strategy? Maybe — but only after they've run **historical simulation** (to stress the returns), **Monte Carlo** (to explore tail risk), **sensitivity analysis** (to see if the Sharpe survives a fat-tail assumption), and checked the backtest for **pitfalls** like survivorship bias and look-ahead errors. That's the workflow this module teaches.

---

## LOS 1 — Objectives of backtesting

**Backtesting** is a simulation of an investment strategy applied to historical data, designed to estimate how it *would have* performed. Its core objectives:

| Objective | What it means in practice |
|---|---|
| **Risk-return discovery** | Estimate the historical Sharpe, drawdown, volatility — before risking capital |
| **Filter bad ideas out** | If it fails in the past, investors won't fund it for the future |
| **Find an "information edge"** | Does adding P/E, momentum, or ESG filters actually produce alpha? |
| **Set decision rules** | Evidence-based accept/reject thresholds rather than hunches |
| **Communicate with clients** | Defensible, quantitative story when pitching a mandate |
| **Debug the model** | Often reveals coding errors, logic flaws, or data issues |

> [!tip] Mental model
> A backtest is a **time machine for hypotheses**. You travel back to 1986, follow your proposed rules for 33 years, and come home with a transcript of what you would have earned. The question is not *"did it work?"* — it's *"did it work for reasons that will persist?"*

**What a backtest is NOT**:
- Not a guarantee of future returns
- Not a substitute for economic intuition — a "pattern that works historically" without a causal story is data-mined noise
- Not complete risk management — it tells you only what happened, not what *could* happen

---

## LOS 2 — Steps and procedures in backtesting

The process has **three distinct stages**, each with specific decisions:

### Step 1 — Strategy Design

Before any code is written, decide:

| Decision | Example |
|---|---|
| **Investment objective** | Beat the Russell 3000 by ≥ 2% annualized |
| **Hypothesis** | "Cheap stocks (high earnings yield) outperform expensive ones" |
| **Universe** | Russell 3000 (point-in-time, not today's constituents) |
| **Rebalance frequency** | Monthly (trade-off: more often = more signal, more costs) |
| **Sample period** | 1986-01 to 2019-12 (include recessions AND bull markets) |
| **Entry/exit rules** | Buy top-quintile earnings yield, short bottom quintile |
| **Transaction cost model** | E.g., 10 bps per side + market-impact adjustment |
| **Risk constraints** | Max position size, sector neutrality, leverage limits |

> [!warning] Trap
> It is tempting to tune these choices *after* seeing results (e.g., "let me use quarterly rebalancing because monthly had too much turnover"). That's **overfitting**. Freeze the design BEFORE looking at results.

### Step 2 — Historical Investment Simulation

Now the code runs. This is where **window approach** decisions matter.

#### Rolling-window walk-forward (the standard)

At each date $t$:
1. Use data from $t - T$ to $t$ (the **in-sample** block) to build the portfolio
2. Hold that portfolio over $[t, t + h]$ — the **out-of-sample** period
3. Record the realized return
4. Slide the window forward by $h$ and repeat

This *mimics real-life decision-making* — you can only use data that was available at the time.

#### Expanding window

Same idea, but the in-sample block *grows* — so you always use *all* data up to $t$. Preferred when more data helps; less effective if the market regime has shifted.

#### Cross-validation

Build the strategy on market A (e.g., US), validate on market B (e.g., Europe). Like the two strategies are siblings rather than twins — if results survive the transplant, they're more likely to be real.

### Step 3 — Analysis of Output

Aggregate the rolling-window returns and compute statistics (covered in LOS 3).

| Step | Output |
|---|---|
| Strategy design | Rules, universe, dates |
| Simulation | Time series of portfolio returns |
| Analysis | Summary statistics and visuals |

> [!example] Worked example — rolling window
> Say $T=60$ months (5 years), $h=1$ month, test period 1986-01 to 2019-12.
>
> - First window: data Jan-1981 to Dec-1985 → hold portfolio Jan-1986 → record return
> - Slide: Feb-1981 to Jan-1986 → hold Feb-1986 → record return
> - ... and so on for ~408 months
> - Result: 408 out-of-sample monthly returns to analyze
>
> Each test month used **only data that existed BEFORE that month** — no cheating with future information.

---

## LOS 3 — Metrics and visuals reported in a backtest

### Core metrics

| Metric | Formula | What it measures |
|---|---|---|
| **Annualized return** | $(\prod(1+r_t))^{12/N} - 1$ | Geometric mean, yearly |
| **Annualized volatility** | $\sigma_{\text{monthly}} \times \sqrt{12}$ | Spread of returns |
| **Sharpe ratio** | $\dfrac{R_P - R_f}{\sigma_P}$ | Reward per unit of total risk |
| **Sortino ratio** | $\dfrac{R_P - R_{MAR}}{\sigma_{\text{downside}}}$ | Reward per unit of *downside* risk |
| **Information ratio** | $\dfrac{R_P - R_B}{\text{TE}}$ | Reward per unit of active risk (vs benchmark) |
| **Maximum drawdown** | $\max_\tau \left[\dfrac{P_\tau^{\max} - P_\tau}{P_\tau^{\max}}\right]$ | Worst peak-to-trough fall |
| **Hit rate / IC** | $\text{corr}(\hat{r}, r_{actual})$ | How often the model is right |
| **Turnover** | $\tfrac{1}{2}\sum|w_{i,t+1} - w_{i,t}|$ | How much of the book trades |
| **Net-of-cost return** | Return after trading costs | The number you can actually earn |

### Key visuals

- **Equity curve (log scale)** — cumulative wealth over time. Log scale is essential: a 10% gain at \$100 looks the same as a 10% gain at \$10,000
- **Drawdown chart** — negative-area chart showing % below prior peak
- **Return histogram** — visualizes **skewness** (asymmetry) and **kurtosis** (fat tails)
- **Rolling Sharpe / rolling drawdown** — shows how performance evolves (consistent vs. regime-dependent)
- **Scatter plot: predicted vs. actual return** — diagnoses the IC

### Worked example — interpreting Value strategy output

| Metric | Value | Interpretation |
|---|---|---|
| Annualized return | 9.24% | Decent |
| Volatility | 12.36% | Moderate |
| Sharpe | 0.75 | Strong — typical long-only equity ~0.4 |
| Max drawdown | −41.04% | **Brutal** — in 2000 and 2008 the strategy lost 40%+ |
| Skewness | Negative | Occasional big losses disproportionate to typical losses |
| Turnover | ~80%/year | Moderate — transaction cost matters |

> [!example] Sharpe example
> Monthly portfolio return: 0.77%, risk-free: 0.17%, monthly σ: 3.57%.
>
> Monthly Sharpe = $(0.0077 - 0.0017)/0.0357 = 0.168$.
>
> Annualized Sharpe = $0.168 \times \sqrt{12} = 0.582$.

---

## LOS 4 — Problems in backtesting (the "pitfalls")

A backtest that doesn't address these is worse than useless — it's **misleading**. The mnemonic: **"S-L-D-O-C-S"** — Survivorship, Look-ahead, Data snooping, Overfitting, Costs, Sample/Stationarity.

### 1. Survivorship bias

Testing on **only today's surviving firms** ignores all companies that went bankrupt or were delisted. If Enron isn't in your data, you never "buy" Enron — which never blows up — and your strategy looks artificially safe.

- **Fix**: Use **point-in-time** data with delisted/bankrupt firms included. CRSP and Compustat both provide this; free sources often do not.

### 2. Look-ahead bias

Your test "knows" information that was not yet public at the time. Classic example: a company's FY2023 earnings are released in February 2024, but your test uses them as-of December 31, 2023.

- **Fix**: **Lag fundamentals** by 1–3 months behind the fiscal period-end to account for reporting lag. For daily data, use intraday timestamps.

### 3. Data snooping (p-hacking)

You test 50 strategies, one produces a 0.8 Sharpe by chance, you publish only that one. With 50 independent tests, getting a nominally "significant" result at the 5% level is essentially guaranteed.

- **Fix**: Use a **higher t-statistic threshold** (e.g., require $|t| > 3$ rather than 2), **Bonferroni correction** ($\alpha/N$), or **cross-validate** on a different market.

### 4. Overfitting

The model is so complex it **memorizes** past noise rather than learning real patterns. A great in-sample Sharpe that collapses out-of-sample is the hallmark.

- **Fix**: **Occam's razor** (simpler models win), **regularization** (penalty for complexity, e.g., LASSO or Ridge), **holdout sample** (never touch last 20% of data until the end).

### 5. Ignored transaction costs

A strategy with 500%/year turnover can easily lose 2–3% per year to bid-ask spreads and commissions. Most "market anomalies" that survive academic publication fail once realistic costs are applied.

- **Fix**: Subtract realistic costs at each trade (bid-ask + commissions + market-impact for large portfolios).

### 6. Sample period / non-stationarity

Financial data is **non-stationary** — the relationships between variables change with regimes (inflation, rates, policy). A strategy that worked in the 1990s low-inflation era may fail now.

- **Fix**: Use **long samples** that span multiple regimes, and **test performance separately** in each regime (bull, bear, hike, cut).

### Summary pitfall-fix table

| Pitfall | Symptom | Fix |
|---|---|---|
| Survivorship | Lean portfolio, no blowups | Point-in-time data |
| Look-ahead | Near-perfect Sharpe | Lag data 1–3 months |
| Data snooping | Only the winner reported | Higher t-threshold, cross-validate |
| Overfitting | Great IS, awful OOS | Simpler model, regularization |
| Ignored costs | Trades-hungry strategy "works" | Model realistic bid-ask + commissions |
| Non-stationarity | Works 1990s, fails 2020s | Long sample, regime-by-regime testing |

> [!tip] Mnemonic — **"S-L-D-O-C-S"**
> **S**urvivorship, **L**ook-ahead, **D**ata snooping, **O**verfitting, **C**osts, **S**tationarity. Six bears waiting in the woods of every backtest.

---

## LOS 5 — Historical scenario analysis

### What it is

Instead of asking *"what happened on average over 30 years?"* (backtest), **historical scenario analysis** asks *"what would happen to my portfolio today if a specific past episode repeated?"* It zooms in on discrete, named crises:

| Scenario | What happened | Lens |
|---|---|---|
| **Black Monday 1987** | S&P −22% in one day | Acute crash |
| **Dot-com crash 2000-02** | Nasdaq −78% over 2.5 years | Slow-motion bear |
| **Global Financial Crisis 2008** | Lehman, credit freeze, −55% S&P drawdown | Multi-asset liquidity shock |
| **Euro crisis 2011-12** | Sovereign stress, EM contagion | Regional / credit |
| **COVID-19 March 2020** | S&P −34% in 5 weeks | Pandemic, vol-spike |

### How it differs from a backtest

| Backtest | Historical scenario analysis |
|---|---|
| Continuous time series, months/years | **Discrete regime** — a named episode |
| "Average" performance metrics | "Worst-case" performance in the stress |
| Long horizon for significance | Specific crisis |
| Summary: Sharpe, drawdown | Summary: drawdown **during X** only |

### How to interpret

The value is in **structural breaks** — moments when normal correlations fall apart. A strategy can have a great 30-year Sharpe but a terrible GFC outcome; scenario analysis exposes that.

### Worked example — Benchmark vs. Risk Parity in recessions

Compare two strategies over NBER-defined US recessions (Dec-2007 to Jun-2009, Feb-2020 to Apr-2020):

| Strategy | Full-sample Sharpe | Recession Sharpe |
|---|---|---|
| Benchmark (60/40) | 0.60 | **0.05** |
| Risk Parity | 0.55 | **0.40** |

*Interpretation*: Benchmark has a *marginally* better full-sample Sharpe but **collapses** during recessions; Risk Parity is slightly weaker overall but **stable** in stress. If your client needs liquidity during downturns, Risk Parity is the better choice — something the backtest averages would have hidden.

---

## LOS 6 — Monte Carlo vs. historical simulation

Both are *simulation* methods — they don't just replay the past; they generate many synthetic outcomes. The difference is where the synthetic data comes from.

### Historical simulation

**Recipe**: Take the past N monthly returns. Put each on an index card. **Shuffle** the deck. Deal K random cards → one synthetic "history." Repeat 10,000 times. Compute statistics across all synthetic histories.

$$r_t^{\text{sim}} \sim \text{Uniform}(\{r_1, r_2, \ldots, r_N\}) \text{ with replacement}$$

This is **bootstrapping**. No distributional assumption — you're resampling the actual empirical distribution.

| ✅ Strengths | ❌ Weaknesses |
|---|---|
| No distribution assumption | Capped by what's in the deck |
| Real returns only — fat tails / skew captured naturally | Misses never-seen events ("100-year pandemic" if not in sample) |
| Simple, explainable | Breaks time-series dependence (sequence matters for some strategies) |

### Monte Carlo simulation

**Recipe**: Specify a distribution — e.g., multivariate Normal with $\mu$, $\Sigma$ (or something fatter-tailed like Student-t, GARCH, regime-switching). **Generate** thousands of random paths from that distribution. Compute statistics.

$$r_t^{\text{sim}} \sim F(\theta)$$

where $F$ is your chosen distribution and $\theta$ its parameters.

| ✅ Strengths | ❌ Weaknesses |
|---|---|
| Flexible — any distribution, any correlation | **Model risk** — if $F$ is wrong, all results are wrong |
| Models fat tails, regime shifts, options | Computationally heavy |
| Handles path-dependent payoffs | "Black box" — hard to audit |

### Side-by-side

| Property | Historical | Monte Carlo |
|---|---|---|
| Data source | Past returns | Chosen distribution |
| Distributional assumption | None | Required |
| Novel shocks | ❌ Only what happened | ✅ Can model |
| Correlation structure | Empirical | Modeled |
| Best for | Linear portfolios, quick VaR checks | Options, tail risk, projections |

> [!tip] One-line distinction
> **Historical**: "trust the *data*." **Monte Carlo**: "trust the *model*." Each delegates trust somewhere different — and each can fail there.

---

## LOS 7 — Inputs and decisions in running a simulation

A simulation is only as good as its inputs. The key decisions:

### 1. Target and decision variables

- **Target variable** — what you want to learn about (portfolio return, end-of-horizon wealth, tail VaR)
- **Decision variables** — the risk factors that drive the target (individual stock returns, rate curves, FX)

### 2. Number of trials

- Rule of thumb: **1,000 trials** for broad summary; **10,000+** for tail statistics (VaR, CVaR)
- More trials → smoother, more stable output
- Trade-off: computational cost scales linearly

### 3. Distributional assumption (Monte Carlo)

The single biggest decision. Options include:

| Distribution | When to use |
|---|---|
| **Multivariate Normal** | Simple, fast; assumes no fat tails (default starting point) |
| **Multivariate Student-t** | Fat tails; one extra parameter (degrees of freedom) |
| **Multivariate Skewed-t** | Fat tails + asymmetry (realistic for equity markets) |
| **GARCH** | Time-varying volatility (captures clustering) |
| **Regime-switching** | Different params in bull vs. bear markets |

### 4. Sampling choice (historical sim)

- **With replacement (bootstrap)** — same return can appear multiple times in one path; needed when N simulations > N data points
- **Without replacement** — permutation only; limited to max of N paths

### 5. Correlation structure

You can't simulate assets independently — when the market falls, *most* assets fall together. Use a **multivariate distribution** so co-movements are preserved. This is why individual-asset simulation fails: it misses the "everything correlates to 1 in a crisis" phenomenon.

### 6. Horizon and path length

- 1-day simulations for daily VaR
- Multi-year simulations for retirement / liability projections
- Longer horizons amplify path dependence and model uncertainty

### 7. Random seed

Fix the seed for **reproducibility**. Without a fixed seed, the same code produces slightly different numbers every run.

### Interpreting the output

Typical simulation report card:

| Statistic | What it tells you |
|---|---|
| Mean return | Central tendency |
| Standard deviation | Spread |
| **Sharpe ratio** | Reward-per-risk |
| **5% VaR** | Loss at 5th percentile |
| **5% CVaR (ES)** | Average loss in worst 5% of paths |
| Max drawdown across paths | Worst trajectory |
| % of paths with negative return | Loss probability |

---

## LOS 8 — Sensitivity analysis

**Sensitivity analysis** changes an input and re-runs to see how much the output moves. It's the meta-test that asks *"is my model fragile?"*

### How it differs from simulation

| Simulation | Sensitivity analysis |
|---|---|
| Varies the **random** component (within a fixed model) | Varies the **assumptions** of the model itself |
| Gives one distribution of outcomes | Gives multiple distributions, one per assumption set |
| Tells you "how uncertain is the answer under these rules?" | Tells you "how much do the rules themselves matter?" |

### Core workflow

1. Run baseline simulation
2. Identify key assumptions (distribution, correlation, horizon, vol estimate, risk aversion)
3. Re-run the simulation with each assumption flexed (e.g., ±20%, or swap distribution)
4. Compare outputs side-by-side
5. Flag assumptions where the output changes **materially**

### Worked example — distributional sensitivity

A risk officer runs a **Monte Carlo** on a Benchmark strategy:

**Baseline — Multivariate Normal distribution**
- 95% CVaR = **−3.7%**
- Interpretation: "In the worst 5% of outcomes, average loss is 3.7%"

**Sensitivity test — swap to Multivariate Skewed Student-t (fat tails, negative skew)**
- 95% CVaR = **−8.4%**

**Conclusion**: The baseline *more than doubled* when the distribution was changed. The model is **highly sensitive** to the fat-tail assumption. The original Normal model was hiding the true danger of a crash. Risk committee decision: re-underwrite capital using the skewed-t.

### When to use it

- **Always** when the output feeds a binding decision (capital, leverage, hedge ratio)
- Before reporting risk numbers to a board / regulator
- After any modeling choice that feels "soft" or convenient

> [!tip] Three-question sensitivity test
> Before shipping any simulation result, ask:
> 1. *What distribution did I assume?* — and how much does 95% CVaR change under a fatter-tailed one?
> 2. *What correlation structure?* — and what if correlations jump to 1 (crisis mode)?
> 3. *What horizon?* — and how does the answer change if I double it?
>
> If any of the three meaningfully changes the answer, state that range in the report — don't just report the baseline.

---

## Formula cheat-sheet

$$\boxed{\;\text{Sharpe} = \frac{R_P - R_f}{\sigma_P}\;}$$

$$\boxed{\;\text{Sortino} = \frac{R_P - R_{MAR}}{\sigma_{\text{downside}}}\;}$$

$$\boxed{\;\text{Information Ratio} = \frac{R_P - R_B}{\text{TE}}\;}$$

$$\boxed{\;\text{Max Drawdown} = \max_{\tau}\left[\frac{P_\tau^{\max} - P_\tau}{P_\tau^{\max}}\right]\;}$$

$$\boxed{\;\text{Turnover} = \tfrac{1}{2}\sum_i |w_{i,t+1} - w_{i,t}|\;}$$

$$\boxed{\;r_t^{\text{hist-sim}} \sim \text{Uniform}(\{r_1,\ldots,r_N\}) \text{ w/ replacement}\;}$$

$$\boxed{\;r_t^{\text{MC}} \sim F(\theta) \quad \text{for chosen } F, \theta\;}$$

---

## Quick mnemonics

| Mnemonic | What it remembers |
|---|---|
| **"S-L-D-O-C-S"** | Six backtest pitfalls: Survivorship, Look-ahead, Data snooping, Overfitting, Costs, Stationarity |
| **"Three lenses"** | Backtest (what was), Historical sim (what else), Monte Carlo (what could be), Sensitivity (what if wrong) |
| **"Trust the data vs. trust the model"** | Historical sim vs. Monte Carlo, in seven words |
| **"Walk forward, freeze the design"** | Don't re-tune after seeing results |
| **"Normal is nice, skewed-t is honest"** | Watch out for thin-tail assumption; always sensitivity-check |

---

## Related notes

- [[Measuring and Managing Market Risk]] — VaR/CVaR via the three methods (parametric, historical, Monte Carlo) — simulation is the engine
- [[Analysis of Active Portfolio Management]] — IR, Fundamental Law — backtest inputs for active strategies
- [[Using Multifactor Models]] — factor backtests need point-in-time data & look-ahead control
- [[Economics and Investment Markets]] — regime-sensitive strategies demand scenario analysis

---

## Final frame

Every investment strategy is really a **hypothesis about the future dressed up as a portfolio**. Backtesting tests that hypothesis on *actual* history, in order. Historical simulation tests it on *reshuffled* history to add robustness. Monte Carlo tests it on *invented* history to stress assumptions the past never recorded. Sensitivity analysis tests *the assumptions themselves* to reveal fragility. Using only one of the four is naive; using all four with discipline — and with eyes open to the six pitfalls — is the difference between *investing* and *gambling with a spreadsheet*.
