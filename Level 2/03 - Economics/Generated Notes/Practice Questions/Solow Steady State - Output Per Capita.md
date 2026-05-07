---
title: "Practice Q - Solow Steady-State Output per Capita Growth"
subject: "Economics"
tags: [CFA-L2, practice-question, economics, solow-model, steady-state-growth, output-per-capita, neoclassical-growth]
aliases: [steady state output per capita, per worker steady state growth, theta over labor share]
source: "unknown"
date: 2026-04-30
---

# Solow Steady-State — Growth Rate of Output **Per Capita**

## Question

![[attachments/2026-04-30-solow-steady-state-output-per-capita.png]]

> The elasticity of capital is **0.32**, TFP growth is **3.1%**, and the labor force is growing at **1.1%**.
>
> *Calculate* the growth rate of output **per capita** in the steady state.

---

## Correct Answer: $\approx 4.56\%$

### What is this testing?

A single, very precise distinction from the [[Solow Model (Neoclassical Growth Theory)]]: **per-capita** (or per-worker) steady-state growth versus **total** output steady-state growth. The two formulas share most of their inputs but differ by exactly the labor-force growth term:

| Quantity | Steady-state formula |
|---|---|
| Output per worker / per capita, $y = Y/L$ | $g^* = \dfrac{\theta}{1-\alpha}$ |
| Total output, $Y$ | $G^* = \dfrac{\theta}{1-\alpha} + n$ |

The exam writer dangles the labor-force growth rate (1.1%) precisely because the per-capita formula does **not** use it. Reaching for it is the whole trap.

### The correct framework

For per-capita / per-worker output in steady state:

$$
\boxed{g^* = \frac{\theta}{1-\alpha}}
$$

Where $\theta$ is [[CFA_Glossary/Total factor productivity (TFP)]] growth and $\alpha$ is the [[CFA_Glossary/Cobb-Douglas production function]] elasticity of capital. The denominator $1-\alpha$ is **labor's** share — never capital's share.

The labor-force growth rate $n$ raises *total* output growth (more workers, more output) but does **not** raise output *per worker*: the new workers each receive their own share of capital and produce at the same per-worker rate as the existing workers.

### Step-by-step computation

Inputs:

- $\theta = 3.1\%$
- $\alpha = 0.32$, so $1-\alpha = 0.68$
- $n = 1.1\%$ (**not used** for per-capita)

Plug in:

$$
g^* = \frac{3.1\%}{0.68}
$$

$$
\boxed{g^* = 4.5588\% \approx 4.56\%}
$$

### The intuition — why $n$ does not appear

Here is the picture. In steady state, the [[CFA_Glossary/Capital deepening]] feedback loop has settled: capital per worker, $k = K/L$, grows at exactly the same rate as output per worker, $y = Y/L$. That common per-worker growth rate is $\theta/(1-\alpha)$ — TFP improvements scaled up by the multiplier $1/(1-\alpha)$ that captures how each TFP gain encourages additional capital, which feeds back to more output, which encourages still more capital.

Now add a wave of new workers. Each new worker arrives with the same per-worker capital and the same TFP as everybody else. Total output goes up by exactly $n$ percent because there are $n$ percent more workers — but average output per worker is unchanged. So $n$ shows up in *total* output growth and disappears from *per worker* output growth. That is why the per-capita formula has only $\theta/(1-\alpha)$, while the total-output formula has $\theta/(1-\alpha) + n$.

For this question, $\theta = 3.1\%$ scaled by $1/0.68 = 1.47$ gives 4.56%. The 1.1% labor-force growth is a distractor.

---

## The Trap — Most Tempting Wrong Answer

**$\approx 5.66\%$ — adding labor-force growth.**

A candidate who half-remembers the steady-state formula reaches for the *total* output version:

$$
\stackrel{?}{=} \frac{3.1\%}{0.68} + 1.1\% = 4.56\% + 1.1\% = 5.66\%
$$

This is the steady-state growth rate of **total GDP**, not per capita. The CFA writers love this trap because both formulas live in the same reading and look almost identical on the page. The single word in the question stem — "**per capita**" — is what flips you from one to the other.

**How to avoid it on exam day:** circle the words "per capita," "per worker," or "per person" *before* you start computing. If you see them, $n$ does not enter the formula. If the question says "GDP growth," "total output growth," or "output growth" without "per worker," then $n$ does enter.

### Other arithmetic slips to avoid

| Slip | What it gives | Why it's wrong |
|---|---|---|
| Dividing $\theta$ by $\alpha$ instead of $1-\alpha$ | $3.1\%/0.32 = 9.69\%$ | Denominator must be **labor's** share, not capital's |
| Just using $\theta$ on its own | $3.1\%$ | Misses the capital-deepening multiplier from the feedback loop |
| Subtracting $n$ from the per-capita answer | $4.56\% - 1.1\% = 3.46\%$ | Confuses the relationship — $n$ doesn't subtract from per-capita; it adds to total |
| Multiplying $\theta$ by $\alpha$ | $3.1\% \times 0.32 = 0.99\%$ | Reverses the role of $\alpha$ entirely |

---

## Key Takeaway

> [!tip] Memory Hook
> **Per-capita growth = $\theta/(1-\alpha)$.** Total growth adds $n$. The labor-force growth rate raises *total* output (more workers, more output) but never raises *per-worker* output. Read the question stem for "per capita" or "per worker" before computing.

For this question:

$$
g^* = \frac{3.1\%}{0.68} = 4.56\%
$$

---

## Why This Question Matters

The CFA L2 LOS this question discharges:

- *Explain the steady state rate of growth in the neoclassical (Solow) model.*
- *Explain the differences between the steady-state growth rates of total output and output per worker.*

Per-capita growth is the right number for measuring **living-standard improvement** — it is what determines how rich the average person becomes. Total output growth is the right number for **macro forecasting**, fiscal capacity, and aggregate equity-market sizing. The two-stage equity valuation models seen elsewhere in the curriculum use total output growth (which adds $n$); welfare and convergence comparisons across countries use per-capita growth (which does not).

The exam will dress this distinction up many ways: "growth in the standard of living," "growth in average labor productivity," "growth in output per worker." All of them point at the same formula: $\theta/(1-\alpha)$, no $n$.

---

## Related Concepts

- [[Steady-State Growth Rate]] — full derivation of both per-worker and total formulas
- [[Solow Model (Neoclassical Growth Theory)]] — the framework
- [[CFA_Glossary/Total factor productivity (TFP)]] — what $\theta$ measures and why it's the engine of per-capita growth
- [[CFA_Glossary/Cobb-Douglas production function]] — where the $1/(1-\alpha)$ multiplier originates
- [[CFA_Glossary/Capital deepening]] — the per-worker mechanism that drives transitional growth above steady state
- [[Labor productivity]] — output per worker, the quantity this question asks about
- [[Labor force]] — the source of $n$, which only enters the *total* formula
- [[Three Growth Theories]] — classical, neoclassical, endogenous; how Solow's per-capita result fits
- [[Convergence Hypotheses]] — why per-capita growth is the right metric for catch-up analysis
