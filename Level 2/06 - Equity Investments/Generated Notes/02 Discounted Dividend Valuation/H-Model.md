---
title: "CFA L2 - H-Model"
subject: "Equity Investments"
tags: [CFA-L2, equity-valuation, DDM, multistage, H-model]
aliases: ["H Model", "H-Model DDM", "Half-Life DDM"]
---

# The H-Model

## The Problem: Growth Doesn't Fall Off a Cliff

Imagine a hot startup that's growing at 20% a year. Eventually, competitors enter, margins compress, and growth slows — but that process takes *years*, not one day. It's a gradual fade, not a hard stop.

The standard **[[two-stage DDM]]** handles growth clumsily: it assumes the company grows fast for exactly $n$ years, then *instantly* switches to a slow stable rate forever. That's a light switch — click, growth is gone. In reality, competitive advantages erode gradually. The **H-Model** replaces the light switch with a dimmer switch: growth starts high and declines in a straight line until it reaches its long-run level.

```
Growth Rate
  gS |●
     | ╲
     |  ╲   Linear decline
     |   ╲
  gL |    ●━━━━━━━━━━━━━━━━  (stable forever)
     |
     0    2H          Time
```

---

## The Formula

$$\boxed{V_0 = \frac{D_0(1+g_L) + D_0 \cdot H(g_S - g_L)}{r - g_L}}$$

**Every variable:**

| Symbol | Meaning |
|--------|---------|
| $V_0$ | Intrinsic value of the stock today |
| $D_0$ | Dividend just paid (current dividend) — **not** $D_1$ |
| $g_S$ | Short-term (initial) high growth rate |
| $g_L$ | Long-term stable growth rate (the destination) |
| $r$ | Required rate of return on equity |
| $H$ | **Half-life** of the high-growth period = (total transition years) ÷ 2 |

> [!warning] H Is Half the Period
> If growth declines over **10 years**, $H = 5$. If over **8 years**, $H = 4$. Exam questions commonly give you the *total* period — always divide by 2 to get $H$.

---

## The Intuition Behind "H"

$H$ is the **half-life** of the transition. It captures the *average* extra growth the company gets during the fade from $g_S$ to $g_L$.

Because growth declines *linearly*, the average growth rate during the transition period is the midpoint between $g_S$ and $g_L$. The variable $H$ is mathematically placed to represent that average excess, so the formula neatly compresses the entire transition into a single term — without requiring you to discount each year's dividend individually.

This is what makes the H-Model an *approximation*: it trades exactness for elegance. For short transitions or modest growth differentials, it's highly accurate. For 30-year transitions with extreme growth differences, a full spreadsheet model is better.

---

## Two Economic Buckets

The formula separates neatly into two pieces:

$$V_0 = \underbrace{\frac{D_0(1+g_L)}{r-g_L}}_{\text{Bucket 1: Stable-growth value}} + \underbrace{\frac{D_0 \cdot H(g_S - g_L)}{r-g_L}}_{\text{Bucket 2: Supernormal growth bonus}}$$

**Bucket 1 — Stable-growth value:** What the stock would be worth *right now* if the company were already a mature, slow-growing business growing at $g_L$ forever. This is just a [[Gordon Growth Model]] calculation using $D_1 = D_0(1+g_L)$.

**Bucket 2 — Supernormal growth bonus:** The *extra* value from the fact that the company currently grows faster than $g_L$. The term $H(g_S - g_L)$ captures the total excess growth over the transition, and dividing by $(r - g_L)$ converts it to present value. This term shrinks as:
- The transition period shortens ($H$ gets smaller)
- The growth gap narrows ($g_S - g_L$ gets smaller)
- The company gets closer to maturity

> [!tip] Conceptual Check
> If $g_S = g_L$ (no high-growth phase at all), Bucket 2 = 0 and the H-Model collapses to the [[Gordon Growth Model]]. That's a good sanity check.

---

## When to Use Which DDM

| Model | Best used when |
|-------|---------------|
| [[Gordon Growth Model]] | Mature company, already at stable growth, $g$ near nominal GDP |
| [[Two-Stage DDM]] | Clean, discrete high-growth period with an abrupt end (e.g., patent expiry) |
| **H-Model** | Company in transition — competitive advantages fading *gradually* over time |
| Three-Stage DDM | Complex lifecycle with a distinct growth, transition, and maturity phase each |

---

## Solving for the Implied Required Return

If you know the market price ($P_0$), you can rearrange the H-Model to back out what return the market is implying:

$$r = \frac{D_0}{P_0}\left[(1+g_L) + H(g_S - g_L)\right] + g_L$$

This is the H-Model equivalent of the GGM's implied return formula ($r = D_1/P_0 + g$). Use this when the question gives you a price and asks for the "implied required return" or "expected return" — it's the same as asking: "If this price is fair, what return are investors demanding?"

---

## Worked Example 1 — Finding Intrinsic Value

**Trendify Inc.** just paid a dividend of $D_0 = \$2.00$. Its current growth rate is $g_S = 12\%$, expected to decline *linearly* over **10 years** to a permanent rate of $g_L = 5\%$. Required return: $r = 10\%$.

**Step 1 — Find H.**

$$H = \frac{10}{2} = 5$$

**Step 2 — Bucket 1 (stable-growth value).**

$$\frac{D_0(1+g_L)}{r-g_L} = \frac{2.00 \times 1.05}{0.10-0.05} = \frac{2.10}{0.05} = \$42.00$$

**Step 3 — Bucket 2 (supernormal bonus).**

$$\frac{D_0 \cdot H(g_S - g_L)}{r-g_L} = \frac{2.00 \times 5 \times (0.12-0.05)}{0.10-0.05} = \frac{2.00 \times 5 \times 0.07}{0.05} = \frac{0.70}{0.05} = \$14.00$$

**Step 4 — Total intrinsic value.**

$$V_0 = \$42.00 + \$14.00 = \mathbf{\$56.00}$$

If Trendify trades at $60, it's overvalued ($60 > $56). If it trades at $50, it's undervalued.

---

## Worked Example 2 — Finding Implied Required Return

**Fast-Track Corp.** trades at $P_0 = \$50.00$. It just paid $D_0 = \$1.50$. Growth is $g_S = 10\%$ declining linearly over **8 years** to $g_L = 4\%$.

**Step 1 — Find H.**

$$H = \frac{8}{2} = 4$$

**Step 2 — Plug into implied return formula.**

$$r = \frac{1.50}{50.00}\left[(1+0.04) + 4(0.10-0.04)\right] + 0.04$$

$$r = 0.03 \times \left[1.04 + 4(0.06)\right] + 0.04$$

$$r = 0.03 \times \left[1.04 + 0.24\right] + 0.04$$

$$r = 0.03 \times 1.28 + 0.04 = 0.0384 + 0.04 = \mathbf{7.84\%}$$

**Interpretation:** If Fast-Track is fairly priced at $50, the market is implying a 7.84% required return. If your required return is higher (say, 9%), the stock looks overvalued to you.

---

## Assumptions and Limitations

| Assumption | Reality check |
|------------|--------------|
| Growth declines *linearly* | Real fades are rarely perfectly straight-line |
| Single transition period | Some companies have complex, multi-phase trajectories |
| Approximation only | Exact when discounting each year individually; H-Model is a shortcut |
| Best for short transitions | Accuracy degrades for very long transition periods (>15–20 years) |

The H-Model is practical for exam purposes and real-world quick estimates. When precision matters — or the transition is very long — build a full spreadsheet with year-by-year dividend discounting.

---

## Exam Traps Summary

> [!danger] Common Mistakes
> - **$H$ = total years ÷ 2**: Always halve the transition period. $H$ is not the total length.
> - **Uses $D_0$, not $D_1$**: The H-Model formula starts with the *just-paid* dividend. If given $D_1$, back-calculate $D_0 = D_1 / (1+g_S)$.
> - **Bucket 2 can be zero**: If $g_S = g_L$, no growth bonus — collapses to GGM.
> - **$r > g_L$ required**: The denominator $(r - g_L)$ must be positive or the model breaks.
> - **Linear decline is an assumption**: The model doesn't work if growth jumps around — only appropriate when transition is gradual.

---

## Related Concepts

- [[Discounted Dividend Valuation]] — the broader DDM framework this sits within
- [[Gordon Growth Model]] — the stable-growth special case (when $H = 0$ or $g_S = g_L$)
- [[Two-Stage DDM]] — the "light switch" alternative
- [[PVGO]] — growth premium framework that complements H-Model intuition
- [[Justified Leading and Trailing PE]] — multiples implied by the same GGM foundation
- [[Sustainable Growth Rate]] — determines whether $g_L$ is realistic
