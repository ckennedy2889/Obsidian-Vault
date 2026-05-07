---
title: "Practice Q - Grinold-Kroner Equity Appreciation and PE Expansion"
subject: "Equity Investments"
tags: [CFA-L2, practice-question, equity-investments, grinold-kroner, equity-risk-premium, capital-market-expectations]
aliases: [analyst forecast vs economist forecast, long-run equity appreciation consistency]
source: "unknown"
date: 2026-04-29
---

# Grinold-Kroner — What Bridges the Analyst's Equity Appreciation and the Economist's Macro?

## Question

![[attachments/2026-04-29-grinold-kroner-equity-appreciation-pe-expansion.png]]

> Analyst forecasts of long-run equity appreciation are **9.40%** and a **2% dividend yield**. Economists' forecasts of long-run growth in real potential GDP are **2.8%**. Long-run forecasts of inflation are **1.8%**.
>
> To be consistent with the economists, analysts are *most likely* assuming:
>
> A. PE ratios will expand 4.8%.
> B. Inflation will actually be higher at 2.8%.
> C. Corporate profits as a share of GDP are expected to grow 6.8%.

---

## Correct Answer: A — PE ratios will expand 4.8%

### What is this testing?

This is a [[Grinold-Kroner Model]] decomposition question — a staple of CFA capital market expectations material. The exam writers are checking whether you can take a real-world set of inputs (an analyst's equity number plus an economist's macro number) and ask the right question: *what implicit assumption must the analyst be making for both forecasts to be internally consistent?*

The skill being tested is not plugging into a formula. It is recognising that any equity-appreciation forecast can be decomposed into macro-grounded pieces, and that whichever piece is **left over** after you account for the economists' macro inputs is the implicit assumption hiding inside the analyst's number.

### The correct framework

The full [[Grinold-Kroner Model]] for expected equity total return is:

$$
E(R_e) = DY + \Delta(P/E) + i + g - \Delta S
$$

Where:

| Symbol | Meaning |
|---|---|
| $DY$ | [[Dividend yield]] |
| $\Delta(P/E)$ | Expected change in market P/E multiple (repricing) |
| $i$ | Expected [[Inflation]] |
| $g$ | Real earnings growth, typically proxied by [[Real GDP]] growth |
| $\Delta S$ | Expected change in shares outstanding (positive = dilution; negative = buybacks) |

The question splits **total return** into **price appreciation** and **dividend yield** explicitly. The 2% dividend yield is the $DY$ piece. The 9.40% "equity appreciation" is everything *except* dividend yield:

$$
\text{Equity appreciation} = \Delta(P/E) + i + g - \Delta S
$$

### Step-by-step computation

To be **consistent with the economists**, the analyst must use:

- $i = 1.8\%$ (economist's inflation forecast)
- $g = 2.8\%$ (economist's real potential GDP growth — the long-run proxy for real earnings growth)

The standard long-run Grinold-Kroner assumptions also require:

- $\Delta S = 0$ — no net buybacks or issuance over the long run
- **Corporate profits are a constant share of GDP** — so aggregate corporate earnings grow at nominal GDP growth, meaning the $i + g$ proxy is exactly right

Plug in:

$$
9.40\% = \Delta(P/E) + 1.8\% + 2.8\% - 0
$$

$$
9.40\% = \Delta(P/E) + 4.6\%
$$

$$
\Delta(P/E) = 9.40\% - 4.6\% = 4.80\%
$$

The analyst's implicit assumption is that **the market P/E expands by 4.8% per year**.

### The intuition — why this is the answer

Here is the picture. The economists give you the *real economy*: things grow 2.8% in real terms, prices rise 1.8% per year. That is **nominal GDP growth of 4.6%**. If corporate profits hold their slice of that economic pie, aggregate corporate earnings also grow 4.6% per year. With no net share issuance, **earnings per share also grow 4.6%**.

If the P/E multiple stayed flat, equity prices would grow exactly with EPS: **4.6% appreciation**. Add the 2% dividend yield, and you get a 6.6% total return.

But the analyst is forecasting **9.40% appreciation** — almost 5 percentage points higher than what the macro picture supports. That gap has to come from somewhere. The Grinold-Kroner formula gives you exactly four levers:

1. **Higher inflation** — but the economists already pinned inflation at 1.8%, so changing $i$ violates "consistent with the economists."
2. **Higher real growth** — same problem; $g = 2.8\%$ is the economist input.
3. **Negative $\Delta S$ (buybacks)** — possible, but this lever is not in any of the answer choices.
4. **P/E expansion** — the only macro-consistent way to bridge the gap.

So the analyst must be implicitly assuming the market **re-rates higher** by 4.8% per year. That is the answer.

This is also why the long-run version of [[Grinold-Kroner Model]] usually assumes $\Delta(P/E) \approx 0$: because P/E expansion at 4.8% per year is **not sustainable** — investors cannot keep paying ever-higher multiples for each dollar of earnings forever. The CFA point is that whenever an analyst's equity forecast exceeds the macro-grounded number, it is implicitly relying on multiple expansion or margin expansion, neither of which can run indefinitely.

---

## The Trap — Most Tempting Wrong Answer

**Answer C: "Corporate profits as a share of GDP are expected to grow 6.8%."**

### Why it looks right

This answer is structurally the right *kind* of answer — it identifies a real Grinold-Kroner lever (relaxing the "constant profit share of GDP" assumption) and converts it into a numerical claim. A candidate who half-remembers the model thinks: "The economists give me nominal GDP of 4.6%, the analyst wants 9.40%, so corporate profits must be growing faster than GDP — answer C captures that idea."

Even better as a trap: **the *direction* of C is correct** (profits growing as a share of GDP would indeed close part of the gap), so candidates pattern-match on the concept and stop checking the arithmetic.

### The specific mistake

Two errors compound:

1. **Wrong arithmetic.** If you allowed corporate profits' share of GDP to grow at rate $x$, then nominal earnings growth would be $i + g + x = 1.8\% + 2.8\% + x$. Setting this equal to 9.40% gives $x = 4.8\%$, **not 6.8%**. The answer's number (6.8%) just does not solve the equation. The candidate who is sloppy with arithmetic might compute $9.40\% - 2.8\% = 6.6\%$ or $9.40\% - 2\% \text{ (dividend yield)} - 0.6\% = 6.8\%$ and never check that this satisfies the Grinold-Kroner identity.

2. **Wrong attribution.** Even if the math worked, attributing the bridge to "profit share of GDP" rather than "P/E expansion" picks the wrong Grinold-Kroner lever. The standard CFA convention is that the long-run macro proxy ($i + g$) bakes in a **constant** profit share of GDP, and any residual is repricing — i.e., $\Delta(P/E)$. The exam writer wants you to default to that convention.

### How to avoid it on exam day

Run this two-step check whenever an equity-return question gives you analyst and economist numbers separately:

1. **Compute nominal GDP from economist inputs:** $i + g$. That is the macro-grounded earnings growth assuming constant profit share.
2. **Subtract that from the analyst's appreciation:** the residual *must* be $\Delta(P/E)$ if you take the economists at face value and assume zero share issuance and constant profit share.

In this question: $9.40\% - 4.6\% = 4.8\%$. That number must appear in the right answer. **Answer A has 4.8%. Answer C has 6.8%. Done.**

### Why B is also wrong

**Answer B: "Inflation will actually be higher at 2.8%."**

The phrase "consistent with the economists" forbids overriding any of the economists' inputs. The economists explicitly forecast 1.8% inflation — using 2.8% inflation contradicts that. Notice the trap inside the trap: the 2.8% in answer B is the economists' **real GDP growth** number, not their inflation number. The question is dangling a familiar figure and hoping you grab it without thinking.

---

## Key Takeaway

> [!tip] Memory Hook
> **Analyst minus economist = P/E expansion.** Strip dividend yield, then subtract the economists' nominal GDP ($i + g$) from the analyst's price appreciation. Whatever's left is the implicit P/E re-rating the analyst is assuming.

For this question: $9.40\% - (1.8\% + 2.8\%) = 4.80\%$ — the answer.

---

## Related Concepts

- [[Grinold-Kroner Model]] — full model derivation, ERP estimation, and assumption table
- [[Equity risk premium]] — what Grinold-Kroner is most often used to estimate
- [[Dividend yield]] — the income-return component
- [[Real GDP]] — the standard proxy for $g$
- [[Potential GDP]] — long-run real growth ceiling that limits sustainable real earnings growth
- [[Inflation]] — how nominal earnings growth is decomposed
- [[Repurchase yield]] — the $-\Delta S$ term when shares are net retired
- [[Cost of Capital]] — Grinold-Kroner's home in the Corporate Issuers cost-of-capital reading
