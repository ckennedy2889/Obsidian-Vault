---
title: "Practice Q - Solow Steady-State Output Growth (Country D)"
subject: "Economics"
tags: [CFA-L2, practice-question, economics, solow-model, steady-state-growth, neoclassical-growth, growth-accounting]
aliases: [steady state growth Country D, solow steady state practice, neoclassical growth practice]
source: "unknown"
date: 2026-04-29
---

# Solow Steady-State Output Growth — Country D

## Question

![[attachments/2026-04-29-solow-steady-state-country-d.png]]

> With reference to the table below, what would be the steady state growth rate of output for Country D?

| Country | Elasticity of Capital ($\alpha$) | Rate of Technological Change ($\theta$) | Growth Rate of Capital | Growth Rate of Labor | Long-Term Growth Rate of the Labor Force ($n$) |
|---|---:|---:|---:|---:|---:|
| A | 0.3 | 3.20% | -1% | 1.10% | — |
| B | 0.1 | 0.80% | 0.80% | 0.80% | — |
| C | 0.1 | 0.80% | 0.40% | — | 0.40% |
| **D** | **0.3** | **1.40%** | 0.60% | — | **2.10%** |

---

## Correct Answer: 4.10%

### What is this testing?

This is a [[Solow Model (Neoclassical Growth Theory)]] question, specifically the [[Steady-State Growth Rate]] formula. The exam writers want to confirm you can do three things:

1. Recognise that "steady state" means use the Solow balanced-growth formula, **not** the [[Growth Accounting]] equation.
2. Pick the *long-term* labor force growth rate, not the current period labor growth.
3. Divide TFP growth by **labor's share** ($1-\alpha$), not capital's share.

The table is constructed as a trap. Country D has the "Growth Rate of Labor" cell deliberately blank — there is no current-period labor growth number. That blank is a tell: growth accounting is unavailable, so the only formula left standing is steady-state Solow.

### The correct framework

The neoclassical / Solow steady-state growth rate of total output is:

$$
\boxed{\frac{\Delta Y}{Y} = \frac{\theta}{1-\alpha} + n}
$$

Where:

| Symbol | Meaning |
|---|---|
| $\theta$ | Growth rate of [[CFA_Glossary/Total factor productivity (TFP)]] (the "rate of technological change" column) |
| $\alpha$ | Elasticity of capital (capital's share of income) |
| $1-\alpha$ | Labor's share of income |
| $n$ | **Long-run** [[Labor force]] growth rate |

Two pieces are crucial and easy to get wrong:

- The denominator under $\theta$ is **labor's share**, not capital's share.
- $n$ must be the **long-term** labor force growth rate, not the current observed rate. In steady state we are looking down the long-run growth path, not at a transitional snapshot.

### Step-by-step computation

For Country D, pull the right cells:

- $\alpha = 0.3$, so $1-\alpha = 0.7$
- $\theta = 1.40\%$
- $n = 2.10\%$ (the **Long-Term Growth Rate of the Labor Force** column)

Ignore the "Growth Rate of Capital" (0.60%) and "Growth Rate of Labor" (blank). Capital's growth in steady state is endogenous — it's whatever it has to be to keep the capital-output ratio stable. The current labor growth rate is a transitional number, not a steady-state input.

Step 1 — compute steady-state growth of output **per worker**:

$$
g^* = \frac{\theta}{1-\alpha} = \frac{1.40\%}{0.70} = 2.00\%
$$

Step 2 — add long-run labor force growth to get steady-state growth of **total** output:

$$
G^* = g^* + n = 2.00\% + 2.10\%
$$

$$
\boxed{G^* = 4.10\%}
$$

### The intuition — why this works

Here is the picture. In the long run, the [[Solow Model (Neoclassical Growth Theory)]] says an economy reaches a **balanced growth path**. On that path, capital per worker stops drifting, the marginal product of capital is constant, and the only thing pushing output per worker upward is improvements in [[CFA_Glossary/Total factor productivity (TFP)]].

Why does $\theta$ get scaled up by $1/(1-\alpha)$? Because TFP growth makes each existing unit of capital more productive, and firms respond by investing more capital, which raises output further, which calls for still more capital, and so on. The geometric series of those reinforcing rounds collapses to the multiplier $1/(1-\alpha)$. Capital's share $\alpha$ measures how much of each round of extra output gets reinvested as capital, and the smaller labor's share is, the bigger the loop. That is why the denominator is labor's share — it is what's *left over* after the capital-deepening feedback loop has done its work.

Once you have output per worker growth, $g^* = \theta/(1-\alpha)$, total output grows faster than per-worker output by exactly the labor force growth rate, because more workers mean more output even if each one is no more productive than before. Hence the $+\,n$ tag.

For Country D the per-worker piece is 2.0% (driven by 1.4% TFP scaled by labor's 0.7 share), and the labor-force tag adds another 2.1%. The economy expands at 4.10% in the long run.

---

## The Trap — Most Common Mistake

There are three classic wrong paths on this kind of question. The single most tempting trap is **#1**.

### Trap #1 — Forgetting to scale $\theta$ by labor's share (most common)

A candidate who half-remembers the formula writes:

$$
G^* \stackrel{?}{=} \theta + n = 1.40\% + 2.10\% = 3.50\%
$$

This is the [[Growth Accounting]] equation collapsed wrong. It looks plausible — TFP growth plus labor growth — and it produces a clean number. But it skips the capital-deepening feedback loop entirely.

**The fix:** any time the question says "steady state," reach for $\theta/(1-\alpha) + n$. The denominator $(1-\alpha)$ must be there.

### Trap #2 — Using "Growth Rate of Capital" instead of long-term labor growth

A candidate who scans the row left-to-right grabs the first non-blank number after $\theta$:

$$
G^* \stackrel{?}{=} \frac{\theta}{1-\alpha} + \text{growth rate of capital} = 2.00\% + 0.60\% = 2.60\%
$$

Capital growth is **not** an input to the steady-state formula. In steady state, capital grows endogenously at the same rate as output. The exam table is structured precisely to test whether you reach for the correct column — the "Long-Term Growth Rate of the Labor Force" column, not "Growth Rate of Capital."

### Trap #3 — Trying to use Growth Accounting

A candidate ignores the words "steady state" and applies the [[Growth Accounting]] decomposition:

$$
\frac{\Delta Y}{Y} = \theta + \alpha \frac{\Delta K}{K} + (1-\alpha)\frac{\Delta L}{L}
$$

For Country D, $\Delta L/L$ is blank in the table — this is the deliberate signal that growth accounting is unavailable and you must use steady state. A candidate who ignores the blank and substitutes the long-term labor force growth into $\Delta L/L$ gets:

$$
\stackrel{?}{=} 1.40\% + 0.3 \times 0.60\% + 0.7 \times 2.10\% = 1.40\% + 0.18\% + 1.47\% = 3.05\%
$$

Wrong on two levels: it treats long-term labor force growth as current-period labor growth, and it ignores the steady-state setup entirely.

### How to avoid all three on exam day

Run this two-step check on any "steady-state output growth" question:

1. **Read the question stem.** If it says "steady state" or "balanced growth path" or "long-run growth rate," ignore current-period growth columns and reach for $\theta/(1-\alpha) + n$.
2. **Find $n$ in the row marked "long-term" or "long-run."** Never use a column labelled "current growth rate" for $n$ in steady state.

Then verify the denominator under $\theta$ is **labor's** share by recalling: capital deepens, but labor's share is what *cushions* the deepening — so labor's share goes underneath.

---

## Key Takeaway

> [!tip] Memory Hook
> **Theta over labor share, plus long-run labor.** $G^* = \theta/(1-\alpha) + n$. If the question says "steady state" and labor growth is blank, the answer always uses long-term labor force growth — never the current-period labor or capital growth columns.

For Country D: $1.40\%/0.70 + 2.10\% = 2.00\% + 2.10\% = 4.10\%$.

---

## Why This Question Matters

The CFA L2 economics LOS this question discharges:

- *Forecast potential GDP based on growth accounting relations.*
- *Explain the steady state rate of growth in the neoclassical (Solow) model and demonstrate the effects of changes in saving rate, labor force growth, and total factor productivity.*

The skill being checked is **picking the right framework**. Growth accounting and steady-state Solow share inputs but apply in different regimes. Growth accounting measures realised growth in any given period; the steady-state formula projects long-run sustainable growth. The blank cells in the table are how the exam writer enforces the choice.

---

## Related Concepts

- [[Steady-State Growth Rate]] — full derivation of $G^* = \theta/(1-\alpha) + n$
- [[Solow Model (Neoclassical Growth Theory)]] — the model behind the formula
- [[Three Growth Theories]] — classical, neoclassical, endogenous; how Solow fits
- [[Growth Accounting]] — the *current-period* decomposition; the alternative this question rejects
- [[CFA_Glossary/Total factor productivity (TFP)]] — what $\theta$ measures
- [[CFA_Glossary/Cobb-Douglas production function]] — the production technology underlying the model
- [[CFA_Glossary/Capital deepening]] — why TFP, not capital, drives long-run per-worker growth
- [[Convergence Hypotheses]] — what happens to economies below their steady state
- [[Labor force]] — the source of $n$
- [[Potential GDP]] — what total output growth describes in the long run
