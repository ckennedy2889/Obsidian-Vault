---
title: "Practice Q - Canada Short-term and Long-term Growth Forecasts"
subject: "Economics"
tags: [CFA-L2, practice-question, economics, growth-accounting, steady-state-growth, solow-model, equity-valuation, capital-market-expectations]
aliases: [Canada gS gL forecast, growth accounting vs steady state Canada, two-stage equity valuation growth inputs]
source: "unknown"
date: 2026-04-29
---

# Canada — Short-term ($g_S$) and Long-term ($g_L$) Growth Forecasts

## Question

![[attachments/2026-04-29-canada-short-term-long-term-growth.png]]

> Canada plans to invest a considerable amount of government funds in national high-speed internet infrastructure and basic research programs in STEM fields in hopes of increasing its long-term real GDP growth rate from the current 2.8%. Alongside this, the country also plans to increase its immigration rate but limit the increase to those applicants with advanced degrees in the STEM fields.
>
> In order to develop a forecast for the Canadian equity market, a valuation model will be used to capture the changes in policy that will unfold over the next 5 years. This model requires forecasts of both short-term ($g_S$) and long-term ($g_L$) growth rates.
>
> What values of $g_S$ and $g_L$ will be used?

| Country | Period | $\Delta A/A$ (%) | $\alpha$ | $\Delta K/K$ (%) | $\Delta L/L$ (%) |
|---|---|---:|---:|---:|---:|
| **Canada** | **2018–2022** | **1.1** | **0.72** | **3.6** | **0.4** |
| **Canada** | **long-term** | **1.3** | **0.66** | **3** | **1.2** |
| Mexico | 2018–2022 | 0.9 | 0.65 | 5.5 | 2.2 |
| Mexico | long-term | 0.9 | 0.70 | 4.3 | 2.2 |
| United States | 2018–2022 | 1.4 | 0.70 | 3.8 | 0.5 |
| United States | long-term | 1.2 | 0.64 | 4.6 | 0 |

---

## Correct Answer: $g_S \approx 3.80\%$ and $g_L \approx 5.02\%$

### What is this testing?

This is the canonical two-formula question in CFA L2 economic-growth forecasting. The exam writer wants you to recognise that **short-term and long-term growth use different formulas**, even when the inputs come from the same Cobb-Douglas / Solow framework:

1. **Short-term ($g_S$)** is forecast with the [[Growth Accounting]] equation, which decomposes *realised* (or near-term projected) growth into TFP, capital, and labor contributions.
2. **Long-term ($g_L$)** is forecast with the [[Steady-State Growth Rate]] formula from the [[Solow Model (Neoclassical Growth Theory)]], which captures the *balanced growth path* that holds after the economy adjusts to its new policy regime.

The trick is that the table gives you both rows for Canada — the 2018–2022 row (use for $g_S$) and the long-term row (use for $g_L$). Students who reach for the same formula twice get the second piece wrong. Students who mix rows across formulas get both pieces wrong.

### The correct framework

**Short-term — Growth Accounting equation:**

$$
\boxed{g_S = \frac{\Delta A}{A} + \alpha \frac{\Delta K}{K} + (1-\alpha) \frac{\Delta L}{L}}
$$

This is a *current-period* identity: it sums the actual contributions of TFP growth, capital growth (weighted by capital's share), and labor growth (weighted by labor's share). Use it whenever the question asks for realised, projected, or transitional output growth — i.e., growth *not* on the long-run balanced path.

**Long-term — Solow steady-state:**

$$
\boxed{g_L = \frac{\theta}{1-\alpha} + n}
$$

Where $\theta = \Delta A/A$ is long-run TFP growth and $n$ is the long-run [[Labor force]] growth rate. Use this whenever the question says "long-term," "long-run," "steady state," or "balanced growth path."

The two formulas look different because in steady state, capital growth is **endogenous** — it is whatever it has to be to keep the capital-output ratio constant. So $\Delta K/K$ does not appear directly; it has been substituted out using the steady-state condition $\Delta K/K = \Delta Y/Y$.

### Step-by-step computation

**Step 1 — Identify the right row for each forecast.**

| Forecast | Row | Why |
|---|---|---|
| $g_S$ (next 5 years) | Canada **2018–2022** | Captures the actual / near-term contributions during the transition phase, before the policy fully matures |
| $g_L$ (long-run) | Canada **long-term** | Captures the post-policy steady-state TFP, capital share, and labor force growth |

**Step 2 — Compute $g_S$ via Growth Accounting (Canada 2018–2022).**

Inputs from the 2018–2022 row:

- $\Delta A/A = 1.1\%$
- $\alpha = 0.72$, so $1-\alpha = 0.28$
- $\Delta K/K = 3.6\%$
- $\Delta L/L = 0.4\%$

Plug in:

$$
g_S = 1.1\% + (0.72)(3.6\%) + (0.28)(0.4\%)
$$

$$
g_S = 1.1\% + 2.592\% + 0.112\%
$$

$$
\boxed{g_S = 3.804\% \approx 3.80\%}
$$

**Step 3 — Compute $g_L$ via Solow steady-state (Canada long-term row).**

Inputs from the long-term row:

- $\theta = 1.3\%$
- $\alpha = 0.66$, so $1-\alpha = 0.34$
- $n = \Delta L/L = 1.2\%$

Plug in:

$$
g_L = \frac{1.3\%}{0.34} + 1.2\%
$$

$$
g_L = 3.8235\% + 1.2\%
$$

$$
\boxed{g_L = 5.0235\% \approx 5.02\%}
$$

### Why the two rows look the way they do — the policy story

The structure of the long-term row tells you the policy story Canada is trying to engineer:

| Variable | 2018–2022 | Long-term | Direction | Policy reason |
|---|---:|---:|---|---|
| $\Delta A/A$ | 1.1% | 1.3% | Up | National high-speed internet + STEM research raise [[CFA_Glossary/Total factor productivity (TFP)]] |
| $\alpha$ | 0.72 | 0.66 | Down | Skilled-labor immigration tilts factor shares toward labor; capital's share falls |
| $\Delta K/K$ | 3.6% | 3% | Down | In steady state, capital growth slows to match output growth; no more catch-up [[CFA_Glossary/Capital deepening]] |
| $\Delta L/L$ | 0.4% | 1.2% | Up | New immigration policy (advanced STEM degrees) raises long-run [[Labor force]] growth |

So Canada's long-term growth rate is being lifted from a current 2.8% to roughly 5.02% via three levers: faster TFP growth, faster labor force growth, and a structural shift in factor shares. The short-term forecast (3.80%) reflects the transition — capital is still growing fast (3.6%) as new infrastructure gets built, but labor and TFP have not fully adjusted yet.

### The intuition — why two formulas, not one

Here is the picture. **Growth accounting** is just an arithmetic decomposition of whatever growth happens to occur. If you tell me how fast TFP, capital, and labor grew, I can tell you how fast output grew — but I have to take all three numbers as given. There is no economic theory in the equation; it is an identity.

The **Solow steady-state formula** adds a piece of theory: in the long run, the capital-to-output ratio is constant. That single assumption eliminates one of the three free variables. Capital growth is no longer something you read off a table — it is forced to equal output growth. So the formula collapses to depend only on TFP growth, labor's share, and labor force growth.

Why is this important for forecasting? Because over a 5-year horizon, the economy is *adjusting* — capital is growing faster or slower than its steady-state rate, the capital-to-output ratio is drifting. So you need the full growth-accounting equation, with all three free variables. But over the long run, that drift dies out and capital settles into its balanced rate. Then the Solow simplification kicks in, and you forecast with $\theta/(1-\alpha) + n$.

A two-stage equity valuation model — exactly the kind described in the question — needs both: a transition-period number for the explicit forecast horizon, and a steady-state number for the terminal value.

---

## The Trap — Most Tempting Wrong Answer

There are several wrong paths. The single most dangerous one is **using the same formula for both forecasts**.

### Trap #1 — Using Growth Accounting for both (most tempting)

A candidate sees a table with $\Delta K/K$ and $\Delta L/L$ in every row and assumes growth accounting is the formula for the entire question. Applying it to the long-term row:

$$
g_L \stackrel{?}{=} 1.3\% + (0.66)(3\%) + (0.34)(1.2\%)
$$

$$
\stackrel{?}{=} 1.3\% + 1.98\% + 0.408\% = 3.688\%
$$

This is wrong. The "long-term" row is intended for the **steady-state** formula. Treating it as another current-period growth-accounting calculation throws away the Solow theory and produces a long-run forecast (3.69%) that is *lower* than the short-run forecast (3.80%) — which is economically backwards given that Canada's policy is meant to *raise* long-run growth.

### Trap #2 — Using Steady-state for both

A candidate who half-remembers that "long-term equals steady state" might apply the Solow formula to the 2018–2022 row as well:

$$
g_S \stackrel{?}{=} \frac{1.1\%}{0.28} + 0.4\% = 3.929\% + 0.4\% = 4.33\%
$$

This is also wrong. The 2018–2022 period is explicitly the **next 5 years** of the policy transition — the economy is not yet in steady state. Solow's balanced-growth assumption is invalid for this horizon. Use the full growth-accounting equation, which doesn't require the economy to be on the balanced path.

### Trap #3 — Mixing $\alpha$ and $1-\alpha$

The most arithmetic-level error. In growth accounting, $\alpha$ multiplies $\Delta K/K$ and $1-\alpha$ multiplies $\Delta L/L$. In the steady-state formula, $\theta$ is divided by $1-\alpha$ (labor's share, **not** capital's share).

Common slip: dividing $\theta$ by $\alpha$ in the steady-state piece:

$$
g_L \stackrel{?}{=} \frac{1.3\%}{0.66} + 1.2\% = 1.97\% + 1.2\% = 3.17\%
$$

This number is wrong by about 1.85 percentage points. The mnemonic from [[Steady-State Growth Rate]]: **theta over labor's share**, never capital's share.

### Trap #4 — Crossing the rows

Pulling $\theta$ from the long-term row but $\alpha$ from the 2018–2022 row, or vice versa. Each row is internally consistent — its $\alpha$ reflects the factor shares for that period — and crossing rows produces a Frankenstein formula that means nothing economically.

### How to avoid all four on exam day

Run this checklist when a question asks for both $g_S$ and $g_L$:

1. **For $g_S$ → growth accounting**, full equation, all three terms.
2. **For $g_L$ → Solow steady-state**, $\theta/(1-\alpha) + n$, capital growth not used.
3. **Match each row to its formula**. The "near-term" or "20XX–20XX" row goes with growth accounting; the "long-term" row goes with steady state.
4. **Always divide $\theta$ by labor's share** ($1-\alpha$), never by capital's share.

---

## Key Takeaway

> [!tip] Memory Hook
> **Two horizons, two formulas.** Short-term: growth accounting, all three terms — $\theta + \alpha\,\Delta K/K + (1-\alpha)\,\Delta L/L$. Long-term: Solow steady state, capital growth drops out — $\theta/(1-\alpha) + n$. Match each formula to its row, never cross them.

For Canada:

$$
g_S = 1.1\% + 0.72(3.6\%) + 0.28(0.4\%) = 3.80\%
$$

$$
g_L = \frac{1.3\%}{0.34} + 1.2\% = 5.02\%
$$

---

## Why This Question Matters

The CFA L2 LOS this question discharges:

- *Demonstrate forecasting potential GDP based on growth accounting relations.*
- *Explain the steady state rate of growth in the neoclassical (Solow) model.*
- *Forecast economic growth using inputs to support a multi-stage equity valuation model.*

This is also the **bridge between Economics and Equity Investments**. The two-stage growth dichotomy ($g_S$ for the explicit forecast horizon, $g_L$ for the terminal stage) is exactly the structure used in the [[Three-Stage DDM]] and similar valuation models. The economics reading gives you the macro plumbing; the equity reading uses it to value an aggregate market or index.

The exam-writer's policy narrative also matters. The question deliberately frames a story (STEM research, internet infrastructure, skilled immigration) that maps onto specific table cells: TFP up, labor up, factor shares shifting. A complete answer recognises that the long-term row reflects the *post-policy steady state*, and that Canada's 2.8% current rate is meant to climb toward roughly 5.0% as the policy beds in.

---

## Related Concepts

- [[Growth Accounting]] — the short-term formula and its role as a decomposition identity
- [[Steady-State Growth Rate]] — the long-term formula and the balanced-growth derivation
- [[Solow Model (Neoclassical Growth Theory)]] — the framework that justifies dropping $\Delta K/K$ in the long run
- [[CFA_Glossary/Total factor productivity (TFP)]] — what $\theta = \Delta A/A$ measures
- [[CFA_Glossary/Cobb-Douglas production function]] — the production technology that produces both formulas
- [[CFA_Glossary/Capital deepening]] — the transitional engine; runs out in steady state
- [[ICT vs Non-ICT Capital]] — relevant to Canada's high-speed internet investment
- [[Three-Stage DDM]] — the equity-valuation use case for both $g_S$ and $g_L$
- [[Grinold-Kroner Model]] — alternative top-down equity-return forecast with similar inputs
- [[Potential GDP]] — what these growth forecasts ultimately describe
- [[Convergence Hypotheses]] — why Mexico's row in the table looks structurally different
