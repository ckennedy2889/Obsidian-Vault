---
title: "Practice Q - Par/Spot/Forward Rate Triangle (Solve for 2-Year Par and Spot)"
subject: "Fixed Income"
tags: [CFA-L2, practice-question, term-structure, par-spot-forward]
source: "unknown"
date: 2026-05-03
---

# Par/Spot/Forward Rate Triangle — Solve for 2-Year Par (X) and 2-Year Spot (Y)

## Question

You are given the following par rates, spot rates, and forward rates. *Calculate* the value of X and Y.

|         | Par   | Spot  | Forward |
|---------|-------|-------|---------|
| 1-year  | 2.20% | 2.20% | 2.20%   |
| 2-year  | **X** | **Y** | 3.30%   |

The 2-year forward rate listed (3.30%) is the **1-year rate, 1 year forward** — i.e., $f_{1,1}$.

---

## Correct Answer: X ≈ 2.74%, Y ≈ 2.75%

### What is this testing?

The exam writers are checking whether you understand that par, spot, and forward rates are three different *views* of the same underlying discount-factor curve. Give them any one curve completely, and the other two are forced — there is no extra information needed. The economic content is identical; only the framing differs. This question hands you the 1-year point in all three frames (which trivially must agree, since over a single period par = spot = forward by definition) and the 2-year forward, and asks you to push that forward back into the spot frame, then push the spot frame into the par frame.

The relationships are anchored by [[Bootstrapping Spot Rates]], the [[Forward curve]], the [[Spot curve]], and the [[Par curve]]. See [[Par vs Spot vs Forward Rates]] for the conceptual map.

### The correct approach

**Step A — Convert forwards to spots (no-arbitrage chain rule).**

A 2-year zero must produce the same terminal wealth as rolling a 1-year spot into a 1-year forward:

$$
(1 + S_2)^2 \;=\; (1 + S_1)\,(1 + f_{1,1})
$$

**Step B — Convert spots to the par rate.**

A par bond is a coupon bond priced at 100 with coupon equal to the par rate. Discount each cash flow at its own spot rate and set the sum to 100:

$$
100 \;=\; \frac{C}{1+S_1} \;+\; \frac{100+C}{(1+S_2)^2}, \qquad \text{Par}_2 = \frac{C}{100}
$$

Equivalently (dividing through by 100, with $X = C/100$):

$$
1 \;=\; \frac{X}{1+S_1} \;+\; \frac{1+X}{(1+S_2)^2}
$$

Solve for $X$.

### Step-by-step computation

**Y — the 2-year spot:**

$$
(1+Y)^2 = (1.0220)(1.0330) = 1.055726
$$

$$
1 + Y = \sqrt{1.055726} = 1.0274853
$$

$$
\boxed{Y \approx 2.7485\% \;\approx\; 2.75\%}
$$

**X — the 2-year par rate:**

Compute the two discount factors first:

$$
DF_1 = \frac{1}{1.0220} = 0.9784736
$$

$$
DF_2 = \frac{1}{1.055726} = 0.9472063
$$

Plug into the par equation:

$$
1 = X(DF_1) + (1+X)(DF_2) \;=\; X(DF_1 + DF_2) + DF_2
$$

$$
X = \frac{1 - DF_2}{DF_1 + DF_2} = \frac{1 - 0.9472063}{0.9784736 + 0.9472063} = \frac{0.0527937}{1.9256799}
$$

$$
\boxed{X \approx 0.027415 \;=\; 2.7415\% \;\approx\; 2.74\%}
$$

### The intuition

Why is the par rate (2.74%) *less* than the spot rate (2.75%), which is itself less than the long forward (3.30%)? Because the curve is **upward-sloping**, and each rate frame averages the underlying one-period forwards in a different way:

- The **forward** $f_{1,1} = 3.30\%$ is the *marginal* one-period rate covering year 2 alone.
- The **spot** $S_2 = 2.75\%$ is the *geometric average* of the year-1 and year-2 forwards: $\sqrt{(1.0220)(1.0330)} - 1$. It blends a low front rate with a high back rate, so it sits between them.
- The **par** rate $X = 2.74\%$ is a *cash-flow-weighted* average of the spots. Because the par bond has a coupon at year 1 (discounted at the low $S_1$) as well as principal+coupon at year 2 (discounted at the higher $S_2$), the front-loaded cash flow drags the par rate slightly *below* the 2-year spot.

This produces the canonical ordering for an upward-sloping curve:

$$
\text{Par} \;<\; \text{Spot} \;<\; \text{Forward}
$$

Check: $2.74\% < 2.75\% < 3.30\%$. ✓ For a downward-sloping curve the inequality flips. For a flat curve all three coincide — exactly as you see in the 1-year row of this table.

### Mechanical check via the par-rate shortcut

There is an algebraic shortcut worth memorizing. Since $1 = \sum X \cdot DF_t + DF_T$ (the principal discount), the par rate equals:

$$
\text{Par}_T = \frac{1 - DF_T}{\sum_{t=1}^{T} DF_t}
$$

Here: $\frac{1 - 0.9472063}{0.9784736 + 0.9472063} = 2.7415\%$. Same answer, fewer keystrokes — useful when the question gives you discount factors directly instead of spot rates. This formulation also makes it obvious why par rates are a weighted average of spots: the denominator is the annuity factor.

---

## The Trap — Most Tempting Wrong Answer

**The seductive mistake: setting Y = average of 2.20% and 3.30% = 2.75%, then setting X = Y.**

Two errors get bundled here:

1. **Arithmetic vs geometric averaging for Y.** The arithmetic mean $(2.20 + 3.30)/2 = 2.75\%$ happens to land *very* close to the correct geometric answer (2.7485%) because the rates are small and close together — this is a coincidence of low rates, not a justification. On the exam, with bigger rates or longer horizons, the gap balloons. Always compound: $(1+S_2)^2 = (1+S_1)(1+f_{1,1})$, then take the square root.

2. **Assuming par = spot.** This collapses two distinct concepts. Par equals spot **only** when the curve is flat — that's why row 1 has all three columns identical. Whenever the curve slopes, the par bond's intermediate coupon is discounted at a different rate than the terminal cash flow, and the par rate diverges from the terminal spot. A test-taker who shortcuts X = Y is silently assuming flatness, which contradicts the very data the question hands them ($f_{1,1} \neq S_1$).

**How to avoid it on exam day.** Whenever you see the par/spot/forward triangle, write the ordering rule in the margin first:

> Upward curve → Par < Spot < Forward.
> Downward curve → Par > Spot > Forward.
> Flat curve → Par = Spot = Forward.

Then sanity-check your answer obeys it. If you get X = Y = 2.75%, you've violated the rule and need to redo the par calculation.

---

## Key Takeaway

> [!tip] Memory Hook
> **"Forwards build spots; spots build par."** On an upward-sloping curve, **Par < Spot < Forward** — par sags below spot because the early coupon gets discounted at the cheaper short rate.

---

## Related Concepts

- [[Par vs Spot vs Forward Rates]] — primary conceptual map for this question
- [[Bootstrapping Spot Rates]] — the (1+S₂)² = (1+S₁)(1+f₁,₁) chain
- [[Forward curve]] — definition of $f_{1,1}$
- [[Spot curve]] — geometric-average interpretation
- [[Par curve]] — coupon-weighted-average interpretation
- [[Discount factor]] — DF shortcut for the par rate formula
- [[Yield to Maturity]] — par rate equals YTM of a par-priced coupon bond
