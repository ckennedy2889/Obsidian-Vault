---
title: "Practice Q - Capital Deepening Outcome in a Low-GDP/Capita Economy"
subject: "Economics"
tags: [CFA-L2, practice-question, economics, capital-deepening, mpk, real-interest-rate, neoclassical-growth, solow-model]
aliases: [low GDP per capita capital deepening, MPK vs real interest rate practice]
source: "unknown"
date: 2026-04-29
---

# Capital Deepening — Outcome in a Low-GDP-per-Capita Economy

## Question

![[attachments/2026-04-29-capital-deepening-low-gdp-per-capita.png]]

> The *most likely* outcome from a planned increase in the capital stock for an economy with a low $\text{GDP}_r/\text{capita}$ ratio would be a:
>
> A. higher $y$ at a given $k$ if $K$ is currently earning the real interest rate.
> B. higher $y$ at a higher $k$ if $K$ is being paid less than the real interest rate.
> C. higher $y$ at a higher $k$ if $K$ is being paid more than the real interest rate.

---

## Correct Answer: C — Higher $y$ at a higher $k$ if $K$ is being paid more than the real interest rate.

### What is this testing?

Three connected ideas from the [[Solow Model (Neoclassical Growth Theory)]]:

1. **Capital deepening is a movement *along* the per-worker production function** — when $K/L$ rises, $Y/L$ rises with it. This is the difference between [[CFA_Glossary/Capital deepening]] (movement *along* $f(k)$) and [[CFA_Glossary/Total factor productivity (TFP)]] growth (an *upward shift* of $f(k)$).
2. **The investment decision rule** — capital should be added whenever the [[Marginal product of capital]] exceeds its rental cost (the [[Real interest rate]] in this simplified setting). If MPK > $r$, capital owners earn excess returns and the planned investment is profitable.
3. **Diminishing marginal returns linked to development level** — a country with low GDP per capita has low $k = K/L$, which by [[Diminishing marginal productivity]] means **high MPK**. The poorer the economy, the more productive its next unit of capital.

The exam writer wants you to chain those three together. Low GDP/capita → low $k$ → high MPK → MPK > $r$ → "K is paid more than $r$" → planned capital deepening is profitable → both $k$ and $y$ rise.

### The correct framework

The Cobb-Douglas per-worker production function:

$$
y = f(k) = A k^\alpha
$$

Where:

| Symbol | Meaning |
|---|---|
| $y = Y/L$ | Output per worker (or per capita, in CFA usage) |
| $k = K/L$ | [[CFA_Glossary/Capital stock]] per worker |
| $A$ | [[CFA_Glossary/Total factor productivity (TFP)]] |
| $\alpha$ | Elasticity / share of capital |

The marginal product of capital under Cobb-Douglas:

$$
MPK = \frac{\partial Y}{\partial K} = \alpha \cdot \frac{Y}{K}
$$

Because $\alpha < 1$ and the function is concave in $K$, **MPK falls as $K/L$ rises** ([[Diminishing marginal productivity]]).

The investment decision rule from [[CFA_Glossary/Rental price of capital]]:

$$
\text{Invest more capital if } MPK > r \quad (\text{equivalently, } K \text{ is "paid more than the real interest rate"})
$$

In long-run equilibrium, competition forces:

$$
MPK = r
$$

So "K is being paid more than r" is the language CFA uses to say "the economy is **below** its capital-equilibrium level" — there is room to add capital profitably.

### Step-by-step reasoning for Country with Low GDP/capita

**Step 1 — Map "low GDP/capita" onto the production function.**

Low $\text{GDP}_r/\text{capita}$ means low $y$. Under Cobb-Douglas, low $y$ on the curve $y = A k^\alpha$ implies **low $k$**.

```
y
│            ╱─────────  (high-GDP economy here, MPK low)
│         ╱
│      ╱  ●  ←── high-GDP economy: flat, MPK ≈ r
│   ╱
│ ●  ←── low-GDP economy: steep, MPK >> r
│╱
└──────────────────────── k
```

**Step 2 — Read off MPK at low $k$.**

The production function is steepest where $k$ is smallest. So at low $k$:

$$
MPK = \alpha \cdot \frac{Y}{K} \quad \text{is large}
$$

Crucially, MPK exceeds $r$:

$$
MPK > r \quad \Longleftrightarrow \quad K \text{ is being paid more than the real interest rate}
$$

**Step 3 — Evaluate the planned capital increase.**

A planned increase in $K$ raises $K/L$ (assuming $L$ is roughly constant in the short run), so $k$ rises. Because we are still on the production function, $y$ rises with $k$:

$$
\Delta K > 0 \;\Rightarrow\; \Delta k > 0 \;\Rightarrow\; \Delta y > 0
$$

The investment is profitable because each new unit of capital earns MPK, which currently exceeds $r$. As $k$ rises, MPK falls toward $r$, and the gap closes — but at the moment of the planned increase, the gap is positive, the investment goes ahead, and we end up at a **higher $k$ with higher $y$**.

**Conclusion: higher $y$ at a higher $k$, conditional on MPK > $r$ (i.e., K paid more than real interest rate). That is C.**

### The intuition — why the inequality direction matters

Here's the picture in plain English. The "real interest rate" is what capital owners can earn in the next-best alternative — lending it out. So when capital is "paid more than the real interest rate," it's earning excess returns relative to its alternative use. That excess is what attracts investment: capital owners say *"my capital is generating MPK > r — I should put more of it to work."* And since the firm sees the same logic, it builds more factories, buys more equipment, and the capital stock grows.

In a poor economy, this gap is wide. Each new factory in a country that barely has any factories is enormously productive — MPK is big, way above what bonds or savings accounts pay. So capital deepening is the natural thing for that economy to do. As capital accumulates, MPK falls (diminishing returns), the gap narrows, and eventually MPK = $r$ at the steady-state $k^*$.

In a rich economy, MPK has already fallen to roughly equal $r$ — there is no excess return to attract more capital, and capital deepening has run out of road. That is why low-GDP economies have so much room to grow through investment, while high-GDP economies must rely on TFP growth.

---

## The Trap — Most Tempting Wrong Answer

**Answer B: higher $y$ at a higher $k$ if $K$ is being paid less than the real interest rate.**

### Why it looks right

B is dangerous because it gets the **mechanical outcome correct**: a planned capital increase does push the economy to a *higher $k$ with higher $y$*. So a candidate who pattern-matches on the visible result ("K↑ ⇒ k↑ ⇒ y↑") and skims past the inequality direction will land on B.

It also has a misleading semantic appeal: "K is paid less than the real interest rate" can be misread as "capital is cheap," and "cheap capital → easy to invest" feels like a justification for deepening. That intuition is wrong, but it is plausible enough to lure candidates who aren't careful with the equilibrium framework.

### The specific mistake

Two errors compound:

1. **Inequality flipped.** "K paid less than $r$" means MPK < $r$. That is the condition for an **over-capitalised** economy — capital is earning *less* than its alternative use, so capital owners would shift their wealth into bonds and the capital stock would naturally **shrink**, not grow. This is the opposite of the situation in a low-GDP/capita economy.

2. **Mismatch with "low GDP/capita."** Low GDP/capita maps to **low $k$**, which means **high MPK** (steep part of the production function). High MPK > $r$, not less than. So even if you ignore the equilibrium logic and just trust diminishing returns, the inequality in B is the wrong way around for the country described.

### How to avoid it on exam day

Run this two-step check whenever you see a question linking capital deepening to MPK and $r$:

1. **Where on the production function is the country?** Low GDP/capita → low $k$ → steep slope → MPK is *high*.
2. **Compare MPK to $r$.** High MPK → MPK > $r$ → "K paid more than $r$" → adding capital is profitable.

Then check the answer's *inequality direction* before you check the *outcome*. The outcome (higher $y$ at higher $k$) is the same in B and C — only the inequality differs, and that is the part the exam writer is testing.

### Why A is also wrong

**Answer A: higher $y$ at a given $k$ if $K$ is currently earning the real interest rate.**

A confuses [[CFA_Glossary/Capital deepening]] with [[CFA_Glossary/Total factor productivity (TFP)]] growth. "Higher $y$ at a *given* $k$" describes an **upward shift** of the production function — exactly the signature of a TFP improvement. But the question stipulates a planned increase in the capital stock, which is movement *along* the curve, not a shift of the curve itself. Increasing $K$ raises $k$ (assuming $L$ does not also rise as fast); it does not leave $k$ unchanged.

Layered on top, A's inequality is the equilibrium condition $MPK = r$. If the economy were already in equilibrium, additional capital would push MPK *below* $r$ and would not be profitable. So A picks the wrong mechanism *and* the wrong starting condition simultaneously.

---

## Key Takeaway

> [!tip] Memory Hook
> **Low GDP/capita → low $k$ → high MPK → K paid more than $r$ → invest, both $k$ and $y$ rise.** Capital deepening is a movement *along* the production function ($k$↑, $y$↑) — not a shift. The inequality "K paid more than $r$" is what tells you the investment is profitable.

Decision shortcut for any "should this country deepen capital?" question:

```
Where is country on f(k)?
        │
        ▼
Low GDP/capita?  ──Yes──▶ Low k → MPK > r → invest → k↑, y↑     (Answer C-pattern)
        │
        No
        ▼
Already at steady state?
        │
        ▼
MPK = r → no excess returns → no further deepening profitable    (Answer A-pattern wrong, since needs "given k")
```

---

## Why This Question Matters

The CFA L2 LOS this question discharges:

- *Describe the impact of capital deepening on output and growth.*
- *Explain how growth in TFP, capital, and labor each contribute to long-run economic growth.*
- *Describe the relationship between the marginal product of capital and the real interest rate.*

The skill being tested is not arithmetic — it is **mapping a verbal economic state ("low GDP/capita") onto the right region of the production function**, and reading off the right inequality between MPK and $r$ from that location. The exam writer dresses the same question in many ways: "country below steady state," "developing economy with abundant labor," "country where MPK exceeds the cost of capital." All of them are pointing at the same place on the curve.

---

## Related Concepts

- [[CFA_Glossary/Capital deepening]] — the core mechanism: $K/L$ rises, $y$ rises along $f(k)$
- [[Capital Deepening and TFP Relationship]] — why TFP growth makes capital deepening more attractive
- [[Solow Model (Neoclassical Growth Theory)]] — the framework behind diminishing returns and steady state
- [[Steady-State Growth Rate]] — what happens when MPK has fallen to $r$
- [[Convergence Hypotheses]] — why low-GDP countries can grow faster than high-GDP ones
- [[CFA_Glossary/Rental price of capital]] — the formal CFA treatment of MPK vs $r$
- [[CFA_Glossary/Total factor productivity (TFP)]] — the alternative engine of growth, which *shifts* $f(k)$ upward
- [[CFA_Glossary/Cobb-Douglas production function]] — where $MPK = \alpha Y/K$ comes from
- [[CFA_Glossary/Capital stock]] — what $K$ in the formulas refers to
- [[Real interest rate]] — the cost of capital benchmark
- [[Marginal product of capital]] — the return that "K is being paid"
- [[Diminishing marginal productivity]] — why MPK falls as $k$ rises
