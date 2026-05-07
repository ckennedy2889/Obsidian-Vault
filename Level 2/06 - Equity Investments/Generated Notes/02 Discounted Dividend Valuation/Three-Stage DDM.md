---
title: Three-Stage DDM
subject: Equity Investments
tags:
  - CFA-L2
  - equity
  - valuation
  - DDM
  - dividend-discount-model
  - three-stage
aliases:
  - Three Stage DDM
  - 3-Stage DDM
  - Three-Stage Dividend Discount Model
---

# Three-Stage DDM

## The Analogy: A Company's Full Lifecycle

Think of a company like a human career. In your twenties you're growing explosively — learning fast, earning more each year, taking risks. Through your thirties and forties, that growth rate gradually moderates as you hit natural ceilings in your profession. By your fifties and sixties you've settled into a stable, predictable pace that will continue until retirement.

The **three-stage DDM** models exactly this lifecycle for a firm:

- **Stage 1 (Growth):** The company enjoys a *constant, high* growth rate $g_S$ for $n_1$ years — think of a young tech firm with a genuine competitive moat
- **Stage 2 (Transition):** Growth *linearly declines* from $g_S$ down to $g_L$ over the next $n_2$ years — the moat is eroding as competitors enter
- **Stage 3 (Maturity):** Growth locks in at $g_L$ forever — the company is now a stable, mature enterprise

```
Growth rate
  gS |●━━━━━●
             ╲
              ╲  linear decline during Stage 2
               ╲
  gL |          ●━━━━━━━━━━━━━━━  (forever)
     |
     +──────────────────────────────  Time
     0   n1      n1+n2
          ↑       ↑
       Stage 1   Stage 3
       ends      begins
```

This is the most realistic of the DDM family. It recognizes that competitive advantages take time to build, take time to erode, and eventually reach equilibrium.

---

## Relationship to the H-Model

The [[Level 2/Generated Notes/06 - Equity Investments/H-Model]] is actually a special case of the three-stage DDM with Stage 1 removed — it assumes growth *starts* declining immediately from day one. The three-stage DDM adds the crucial insight that many companies sustain their high growth rate for several years before the fade begins.

| Model | Stage 1 | Stage 2 | Stage 3 |
|-------|---------|---------|---------|
| GGM | — | — | $g_L$ forever |
| Two-stage DDM | Constant $g_S$ for $n$ years | — | $g_L$ forever |
| H-model | — | Linear fade over 2H years | $g_L$ forever |
| **Three-stage DDM** | Constant $g_S$ for $n_1$ years | Linear fade over $n_2$ years | $g_L$ forever |

---

## The Formula: No Single Closed Form

Unlike the GGM or H-model, the three-stage DDM has **no elegant closed-form solution** you can plug numbers into directly. You must build it in three pieces and add them up:

$$V_0 = \underbrace{\sum_{t=1}^{n_1} \frac{D_t}{(1+r)^t}}_{\text{PV of Stage 1 dividends}} + \underbrace{\sum_{t=n_1+1}^{n_1+n_2} \frac{D_t}{(1+r)^t}}_{\text{PV of Stage 2 dividends}} + \underbrace{\frac{V_{n_1+n_2}}{(1+r)^{n_1+n_2}}}_{\text{PV of Stage 3 terminal value}}$$

Where the Stage 3 terminal value (calculated at the *end* of Stage 2) is just a Gordon Growth Model:

$$V_{n_1+n_2} = \frac{D_{n_1+n_2+1}}{r - g_L}$$

Each dividend must be projected explicitly. Here's how the growth rate behaves in each stage:

**Stage 1:** Growth is constant at $g_S$, so dividends compound cleanly:

$$D_t = D_0 \times (1 + g_S)^t \quad \text{for } t = 1, 2, \ldots, n_1$$

**Stage 2:** Growth declines linearly. At the start of Stage 2 (year $n_1 + 1$) growth is still $g_S$; at the end of Stage 2 (year $n_1 + n_2$) growth has reached $g_L$. The growth rate in year $t$ within Stage 2 is:

$$g_t = g_S - (g_S - g_L) \times \frac{t - n_1}{n_2} \quad \text{for } t = n_1+1, \ldots, n_1+n_2$$

Each dividend in Stage 2 must be grown from the prior year's dividend using that year's $g_t$.

**Stage 3:** At year $n_1 + n_2 + 1$, the company is a Gordon-growth-model firm. Apply the GGM to get the terminal value at the end of Stage 2, then discount it back to today.

---

## Step-by-Step Worked Example

**Setup:** Apex Innovations just paid $D_0 = \$1.00$.

| Parameter | Value |
|-----------|-------|
| $g_S$ (Stage 1 growth) | 20% |
| $n_1$ (Stage 1 length) | 3 years |
| $n_2$ (Stage 2 length) | 4 years |
| $g_L$ (Stage 3 growth) | 5% |
| $r$ (required return) | 12% |

The growth rate transitions linearly from 20% to 5% across Stage 2 (years 4–7). The step-down per year is $(20\% - 5\%) / 4 = 3.75\%$ per year.

### Stage 1 Dividends (Years 1–3, constant 20% growth)

| Year | Growth Rate | Dividend | PV Factor at 12% | PV |
|------|------------|----------|-----------------|-----|
| 1 | 20% | $1.00 × 1.20 = $1.200 | 1/1.12¹ = 0.8929 | $1.071 |
| 2 | 20% | $1.20 × 1.20 = $1.440 | 1/1.12² = 0.7972 | $1.148 |
| 3 | 20% | $1.44 × 1.20 = $1.728 | 1/1.12³ = 0.7118 | $1.230 |

**Sum of Stage 1 PVs = $3.449**

### Stage 2 Dividends (Years 4–7, linearly declining growth)

Growth rates:

| Year | Decline Step | Growth Rate |
|------|-------------|------------|
| 4 | 0 steps from $g_S$ | $20\% - 1×3.75\% = 16.25\%$ |
| 5 | | $20\% - 2×3.75\% = 12.50\%$ |
| 6 | | $20\% - 3×3.75\% = 8.75\%$ |
| 7 | | $20\% - 4×3.75\% = 5.00\%$ ← now at $g_L$ |

Dividends (growing from $D_3 = \$1.728$):

| Year | Growth Rate | Dividend | PV Factor at 12% | PV |
|------|------------|----------|-----------------|-----|
| 4 | 16.25% | $1.728 × 1.1625 = $2.009 | 1/1.12⁴ = 0.6355 | $1.277 |
| 5 | 12.50% | $2.009 × 1.1250 = $2.260 | 1/1.12⁵ = 0.5674 | $1.282 |
| 6 | 8.75% | $2.260 × 1.0875 = $2.458 | 1/1.12⁶ = 0.5066 | $1.245 |
| 7 | 5.00% | $2.458 × 1.0500 = $2.581 | 1/1.12⁷ = 0.4523 | $1.168 |

**Sum of Stage 2 PVs = $4.972**

### Stage 3 Terminal Value (end of Year 7)

At the end of year 7, the company enters perpetual 5% growth. The next dividend (year 8):

$$D_8 = D_7 \times (1 + g_L) = 2.581 \times 1.05 = \$2.710$$

Terminal value at end of year 7:

$$V_7 = \frac{D_8}{r - g_L} = \frac{2.710}{0.12 - 0.05} = \frac{2.710}{0.07} = \$38.71$$

Discount back to today:

$$PV(V_7) = \frac{38.71}{1.12^7} = 38.71 \times 0.4523 = \$17.51$$

### Total Intrinsic Value

$$V_0 = 3.449 + 4.972 + 17.51 = \mathbf{\$25.93}$$

> [!tip] Where the Value Comes From
> - Stage 1: $3.45 (13%)
> - Stage 2: $4.97 (19%)
> - Stage 3 terminal value: $17.51 (68%)
>
> As always with DDMs, the terminal value dominates. This is why the assumed long-run growth rate $g_L$ has an outsized effect on the answer — small changes to $g_L$ move the terminal value dramatically.

---

## The Linear Decline in Detail

The Stage 2 growth rate schedule deserves careful attention. Given:
- Start of Stage 2: growth = $g_S$
- End of Stage 2: growth = $g_L$
- Duration: $n_2$ years

The annual step-down is:

$$\Delta g = \frac{g_S - g_L}{n_2}$$

The growth rate applied to the dividend in year $t$ (where $t$ is measured from the start of Stage 2, so $t = 1$ through $n_2$) is:

$$g_t = g_S - t \times \Delta g$$

So in year 1 of Stage 2, growth is $g_S - \Delta g$. In the final year of Stage 2, growth is exactly $g_L$.

> [!warning] The Growth Rate Applied vs. the Dividend Paid
> The growth rate $g_t$ is applied to grow the *prior year's* dividend into the *current year's* dividend. Don't confuse the growth rate labeled for year $t$ with the dividend labeled for year $t$ — the year-$t$ growth rate determines how year $t$'s dividend differs from year $t-1$'s.

---

## Three-Stage DDM vs. H-Model: When to Use Which

The three-stage DDM is more flexible but requires more inputs and more computation. Use it when:

- The company has a **clearly identifiable high-growth period** (e.g., 5 years of patent protection remaining)
- The high-growth phase is **long enough that assuming immediate erosion (H-model) would understate value**
- You have **detailed analyst forecasts** for Stage 1 dividends

Use the H-model instead when:
- You want a **quick, back-of-envelope** estimate
- The company is **already in transition** (no distinct Stage 1 to preserve)
- The growth differential $(g_S - g_L)$ is **modest** (H-model approximation error is small)

---

## Sensitivity of Value to Key Inputs

Using the Apex example above ($V_0 = \$25.93$):

**Effect of changing $g_L$ (Stage 3 growth):**

| $g_L$ | Terminal Value $V_7$ | Total $V_0$ |
|-------|--------------------|-----------:|
| 3% | $2.581×1.03/(0.12−0.03) = $29.55 → PV = $13.36 | $21.78 |
| 5% | $38.71 → PV = $17.51 | $25.93 |
| 7% | $2.581×1.07/(0.12−0.07) = $55.23 → PV = $24.98 | $33.40 |

A 2 percentage point change in $g_L$ swings $V_0$ by $7–8. The terminal value is the lever that matters most.

**Effect of changing $n_1$ (Stage 1 length):**

| $n_1$ | Interpretation | Effect on $V_0$ |
|-------|---------------|----------------|
| 1 year | Almost no competitive advantage | Lower — less high-growth compounding |
| 3 years | Base case | $25.93 |
| 5 years | Durable moat | Higher — more years of 20% dividend growth |

---

## Practical Notes for the CFA Exam

> [!example] What the Exam Tests
> 1. **Building the dividend table** — you'll usually be asked to project dividends for a 2–3 year Stage 1 and 2–3 year Stage 2 and then calculate the terminal value
> 2. **Correctly computing the linear growth step-down** — $\Delta g = (g_S - g_L)/n_2$
> 3. **Terminal value timing** — $V_{n_1+n_2}$ uses $D_{n_1+n_2+1}$, i.e., the *next* dividend after Stage 2 ends
> 4. **Discounting the terminal value** — it must be discounted for the full $n_1 + n_2$ periods back to today
> 5. **Recognizing when the H-model is an approximation** of this model

> [!danger] Most Common Mistakes
> - Using $D_{n_1+n_2}$ instead of $D_{n_1+n_2+1}$ in the terminal value formula (off-by-one error)
> - Discounting the terminal value by $n_1$ periods instead of $n_1 + n_2$
> - Applying the step-down to $g_L$ instead of starting from $g_S$ (getting the direction of decline backwards)
> - Forgetting that the first Stage 2 growth rate is $g_S - \Delta g$, not $g_S$ itself

---

## Related Notes

- [[Level 2/Generated Notes/06 - Equity Investments/H-Model]] — closed-form approximation; Stage 1 omitted, growth fades immediately
- [[Two-Stage DDM]] — abrupt transition, no gradual fade
- [[Gordon Growth Model]] — maturity phase formula used as terminal value
- [[Discounted Dividend Valuation]] — the parent DDM framework
- [[PVGO]] — separating value into assets-in-place vs. growth opportunities
- [[Sustainable Growth Rate]] — anchor for setting a realistic $g_L$
- [[Required Return on Equity]] — how to derive $r$ (CAPM, build-up)
