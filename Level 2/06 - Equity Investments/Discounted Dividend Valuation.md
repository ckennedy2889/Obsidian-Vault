---
title: "Discounted Dividend Valuation"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments]
aliases: []
---

# Module 2: Discounted Dividend Valuation

---
Inke
## Table of Contents

1. [[#1 — Choosing Your Cash Flow Input Dividends vs FCF vs Residual Income]]
2. [[#2 — The dividend discount model (DDM) Single and Multiple Holding Periods]]
3. [[#3 — The Gordon growth model (GGM)]]
4. [[#4 — Valuing Perpetual Preferred Stock]]
5. [[#5 — Implied Growth Rate from the GGM]]
6. [[#6 — Present Value of Growth Opportunitiesowth]] Opportunities (PVGO)]]
7. [[#7 — Justified Leading and Trailing P/E Ratios]]
8. [[#8 — Estimating Required Return from Any DDM]]
9. [[#9 — Overvalued, Fairly Valued, or Undervalued]]
10. [[#10 — Business Lifecycle Growth Phase Transition Phase Maturity Phase]]
11. [[#11 — Multistage DDMs Two-Stage, H-Model, Three-Stage]]
12. [[#12 — Terminal Value]]
13. [[#13 — Spreadsheet Modeling]]
14. [[#14 — sustainable growth rate and DuPont Analysis]]
15. [[#Formula Cheat Sheet]]

---

## 1 — Choosing Your Cash Flow Input: Dividends vs FCF vs Residual Income

Before you can value a stock, you have to decide *what* cash flows to discount. Think of it like choosing which thermometer to use — they all measure temperature, but some are better for certain situations.

### The Three Cash Flow Inputs

**[[Dividends]]** — The actual cash payments the company sends to shareholders. This is the most direct measure of what an investor physically receives.

**[[Free cash flow]] (FCF)** — The cash a company generates *after* paying for everything it needs to run and grow the business. Think of it as the company's "leftover cash" that could theoretically be paid out.
- **[[FCFF]] ([[Free cash flow|Free Cash Flow]]ow to the firm|[[Free cash flow|Free Cash Flow]] to the Firm]])** — Cash available to *all* capital providers (both debt holders and equity holders).
- **[[FCFE]] ([[Free cash flow to equity|Free Cash Flow to Equity]])** — Cash available specifically to *equity holders* after the company has paid its debts.

**[[Residual income]]** — The profit left over *after* subtracting the cost of the capital used to generate it. It's like saying "after we account for what investors *deserve* to earn, how much extra did we create?"

### When to Use Each

| Situation                                                                  | Best Model                      | Why                                                  |
| -------------------------------------------------------------------------- | ------------------------------- | ---------------------------------------------------- |
| Company pays steady, predictable [[dividends]] that track [[earnings]]     | **[[Dividend discount model]]** | Dividends are observable and reliable                |
| You are a **minority shareholder** (you can't control [[Dividend policy|dividend policy]])     | **[[DDM]]**                     | You can only receive what's paid out to you          |
| Company doesn't pay [[dividends]], or dividends differ a lot from [[FCFE]] | **[[FCF]] approach**            | Dividends don't reflect what the company *could* pay |
| You're a **controlling shareholder** (you can change [[Dividend policy]])  | **[[FCF]] approach**            | You could redirect all [[Free cash flow|free cash flow]] to yourself    |
| Company doesn't pay [[dividends]] AND has negative [[Free cash flow]]      | **[[Residual income]]**         | Neither dividends nor FCF exist to discount          |
| Company has high-quality, transparent [[financial reporting]]              | **[[Residual income]]**         | Model relies heavily on accounting data              |

> **Real-World Example:** Imagine you're valuing **Coca-Cola**. Coke has paid dividends for over 100 years, and its [[Dividend payout ratio|dividend payout ratio]]io|payout ratio]] is stable around 70-75%. The [[DDM]] is perfect here — dividends are predictable and clearly tied to earnings. Now imagine valuing **Tesla** in 2018 — no dividends, negative [[Free cash flow|free cash flow]], massive reinvestment. You'd reach for [[Residual income]] instead.

---

## 2 — The Dividend Discount Model (DDM): Single and Multiple Holding Periods

![[DDM-Cash-Flow-Timeline.excalidraw]]

### The Core Idea

The value of any financial asset is the [[present value]] of its future cash flows. For a stock, those cash flows are [[dividends]] (and eventually a sale price when you sell).

Think of buying a stock like buying an apple tree. The tree's value to you is the present value of all the apples it will produce (dividends) plus what you could sell the tree for later (terminal price).

### Single Holding Period DDM

If you plan to hold a stock for **one year**, you'll receive one dividend ($D_1$) plus the price you sell it for ($P_1$):

$$V_0 = \frac{D_1}{(1+r)^1} + \frac{P_1}{(1+r)^1} = \frac{D_1 + P_1}{(1+r)}$$

**What each variable means:**
- $V_0$ = the [[Intrinsic value]] of the stock today (what it *should* be worth)
- $D_1$ = the [[Dividend]] you expect to receive at the end of Year 1
- $P_1$ = the price you expect to sell the stock for at the end of Year 1
- $r$ = your [[Required rate of return]] (the minimum return you demand for the risk you're taking)

**Why each variable is there:** You're getting two things — cash from dividends and cash from selling. Both arrive in the future, so you discount them back to today using $r$.

### Expected Holding Period Return

If you rearrange the formula and assume the stock is fairly priced ($V_0 = P_0$):

$$r = \frac{D_1 + P_1}{P_0} - 1 = \underbrace{\frac{D_1}{P_0}}_{\text{Dividend Yield}} + \underbrace{\frac{P_1 - P_0}{P_0}}_{\text{Capital Gains Yield}}$$

This says: **[[Total return]] = [[Dividend yield]] + [[Capital Gains Yield]]**. You earn returns from two sources — cash income and price appreciation.

### Multiple Holding Period DDM

If you hold the stock for $n$ periods:

$$V_0 = \sum_{t=1}^{n} \frac{D_t}{(1+r)^t} + \frac{P_n}{(1+r)^n}$$

**In plain English:** Add up the present value of every dividend you'll receive during your holding period, then add the present value of the price you'll sell at.

### General (Infinite) DDM

If you hold the stock *forever* (or equivalently, if you keep passing it to the next investor, who also values it by its future dividends):

$$V_0 = \sum_{t=1}^{\infty} \frac{D_t}{(1+r)^t}$$

**Why the sale price disappears:** As $n \to \infty$, the present value of $P_n$ shrinks to zero. All that's left is the infinite stream of dividends. This is the key insight — **even if you plan to sell the stock, the buyer is paying for future dividends too**. So ultimately, a stock's value is always about dividends.

### Worked Example: Three-Period DDM

> **Problem:** Reliable Motors shares are expected to pay dividends of $1.50, $1.60, and $1.75 at the end of each of the next three years. The investor expects the price at the end of Year 3 to be $54.00. The [[required return]] is 15%.

**Timeline:**

```
Today        Year 1       Year 2       Year 3
 |            |            |            |
 V₀ ←——— $1.50 ←——— $1.60 ←——— $1.75 + $54.00
         ÷(1.15)¹   ÷(1.15)²    ÷(1.15)³
```

**Step 1:** Discount each cash flow back to today.

$$V_0 = \frac{1.50}{(1.15)^1} + \frac{1.60}{(1.15)^2} + \frac{1.75 + 54.00}{(1.15)^3}$$

**Step 2:** Calculate each term.

$$V_0 = \frac{1.50}{1.15} + \frac{1.60}{1.3225} + \frac{55.75}{1.5209}$$

$$V_0 = 1.3043 + 1.2098 + 36.6559$$

**Step 3:** Sum them up.

$$V_0 = \$39.17$$

The stock is worth approximately **$39.17** today based on these expected cash flows.

---

## 3 — The Gordon Growth Model (GGM)

### The Big Idea

The [[General DDM]] requires you to forecast dividends individually forever — an impossible task. The **[[Gordon Growth Model]]** (GGM) solves this by making one powerful simplifying assumption: **dividends grow at a constant rate ($g$) forever**.

Think of it like a savings account that grows at a fixed interest rate — once you know the starting balance and the rate, you know every future balance automatically.
22
### The Formula

$$V_0 = \frac{D_1}{r - g} = \frac{D_0(1 + g)}{r - g}$$

**What each variable means:**
- $V_0$ = [[Intrinsic value]] of the stock today
- $D_1$ = expected [[Dividend]] next year. This is $D_0 \times (1 + g)$, where $D_0$ is the dividend *just paid*
- $D_0$ = the most recent dividend (already paid — this is historical)
- $r$ = [[Required rate of return]] on the stock (your minimum demanded return)
- $g$ = the constant [[growth rate]] of dividends, forever

**Why each variable is there:**
- $D_1$ is in the numerator because the model values the *next* dividend and all dividends after it
- $r$ is what you demand as compensation for risk — a higher $r$ means you discount future cash flows more aggressively, so the stock is worth less
- $g$ offsets $r$ in the denominator because growth makes future dividends larger, partially counteracting the discounting. The net "discount" is only $r - g$
- **$r$ must be greater than $g$**: If dividends grow as fast as or faster than the discount rate, the present value of future dividends would be infinite — which doesn't make sense

### Key Assumptions

1. [[Dividends]] grow at a **constant rate** $g$ indefinitely
2. $r > g$ (required return exceeds the growth rate)
3. Both $r$ and $g$ should reflect **long-term** expectations
4. If $g$ exceeds [[GDP]] growth, the assumption of perpetual growth at that rate is unrealistic — use a [[multistage DDM]] instead

> **Rule of Thumb:** A perpetual [[dividend growth rate]] forecast above about 5% is suspect. Why? Because no single company can grow faster than the entire economy forever.

### Where the Formula Comes From (Intuition)

When you write out the DDM with constant growth:

$$V_0 = \frac{D_0(1+g)}{(1+r)} + \frac{D_0(1+g)^2}{(1+r)^2} + \frac{D_0(1+g)^3}{(1+r)^3} + \cdots$$

This is a [[geometric series]] where each term is the previous term multiplied by $\frac{(1+g)}{(1+r)}$. As long as this ratio is less than 1 (i.e., $r > g$), the infinite sum converges to:

$$V_0 = \frac{D_0(1+g)}{r - g}$$

### Worked Example

> **Problem:** DownUnder Financial recently paid a dividend of A\$1.80. Dividends are expected to grow at 3.5% indefinitely. DownUnder's [[Beta]] is 1.5, the [[risk-free rate]] is 4%, and the expected [[market return]] is 8%.

**Step 1: Find the [[required return]] using [[CAPM]].**

$$r = R_f + \beta \times (R_m - R_f)$$

- $R_f$ = 4% (the [[risk-free rate]] — what you'd earn on a government bond with no risk)
- $\beta$ = 1.5 (measures how much the stock moves relative to the market — a beta of 1.5 means the stock is 50% more volatile than the market)
- $(R_m - R_f)$ = 8% - 4% = 4% (the [[Equity risk premium]] — the extra return the market earns above risk-free investments)

$$r = 0.04 + 1.5(0.04) = 0.04 + 0.06 = 0.10 = 10\%$$

**Step 2: Calculate $D_1$.**

$$D_1 = D_0 \times (1 + g) = 1.80 \times 1.035 = \text{A\$}1.863$$

**Step 3: Apply the [[GGM]].**

$$V_0 = \frac{1.863}{0.10 - 0.035} = \frac{1.863}{0.065} = \text{A\$}28.66$$

> **Common Mistake:** Using $D_0$ instead of $D_1$ in the numerator. The GGM values dividends starting *next period*, not the dividend that was just paid.

### Strengths and Limitations of the GGM

**Strengths:**
- Very applicable to stable, mature [[Dividend]]-paying firms (think utilities, consumer staples)
- Easily applied to broad market [[indexes]]
- Simple to communicate and explain
- Useful for backing out [[implied growth rates]], [[required returns]], and [[PVGO]]
- Can be embedded as the final stage of more complex models

**Limitations:**
- Very sensitive to estimates of $g$ and $r$ — small changes in either cause large swings in value
- Cannot easily be applied to [[non-dividend-paying stocks]]
- Assumes constant growth forever — unrealistic for many companies

> **Real-World Example:** The GGM works well for valuing something like **Procter & Gamble** or the **S&P 500 index** as a whole — both have relatively stable, predictable growth. It would be a poor choice for valuing a fast-growing tech startup whose growth rate will clearly change over time.

---

## 4 — Valuing Perpetual Preferred Stock

[[Preferred stock]] that is non-callable, fixed-rate, and perpetual pays the same dividend forever. It's the simplest case — no growth at all ($g = 0$).

### The Formula

$$V_0 = \frac{D}{r}$$

**What each variable means:**
- $V_0$ = value of the [[Preferred stock]]
- $D$ = the fixed annual [[Dividend]] (constant, never changes)
- $r$ = [[Required rate of return]] (often called the [[Capitalization rate]] for a perpetuity)

**Why it works:** This is just the [[GGM]] with $g = 0$. If dividends never grow, the formula simplifies from $D_1/(r - g)$ to $D/r$.

**Analogy:** Think of [[Preferred stock]] as a bond that never matures. You receive the same coupon payment forever, and the value is just that payment divided by the rate investors demand.

### Worked Example

> **Problem:** Main Company's preferred stock has a par value of \$50 and pays a 5.5% dividend. The required return is 6%. What is the value?

**Step 1:** Calculate the annual dividend.

$$D = \$50 \times 0.055 = \$2.75$$

**Step 2:** Apply the [[Perpetuity]] formula.

$$V_0 = \frac{\$2.75}{0.06} = \$45.83$$

If the stock is trading at \$42, it's **[[undervalued]]** — you'd be buying a stream of cash flows worth \$45.83 for only \$42.

---

## 5 — Implied Growth Rate from the GGM

### The Concept

The [[GGM]] has four variables: $V_0$, $D_0$ (or $D_1$), $r$, and $g$. If you know any three, you can solve for the fourth. Since we can observe a stock's market price ($P_0$) and its current dividend, and if we have an estimate of $r$, we can back out the **[[implied growth rate]]** — the growth rate the market is "baking into" the current stock price.

### The Formula

Start with the GGM, set $V_0 = P_0$ (assume the stock is fairly priced):

$$P_0 = \frac{D_0(1 + g)}{r - g}$$

Rearrange to solve for $g$:

$$P_0(r - g) = D_0(1 + g)$$
$$P_0 \cdot r - P_0 \cdot g = D_0 + D_0 \cdot g$$
$$P_0 \cdot r - D_0 = g(P_0 + D_0)$$
$$g = \frac{P_0 \cdot r - D_0}{P_0 + D_0}$$

### Worked Example

> **Problem:** A stock has a [[Beta]] of 1.1, [[risk-free rate]] = 5.6%, [[Equity risk premium]] = 6%, current dividend $D_0$ = \$2.00. The stock price is \$40. What growth rate is implied by the market price?

**Step 1:** Find $r$ using [[CAPM]].

$$r = 5.6\% + 1.1(6\%) = 5.6\% + 6.6\% = 12.2\%$$

**Step 2:** Plug into the [[GGM]] and solve for $g$.

$$40 = \frac{2.00(1 + g)}{0.122 - g}$$

**Step 3:** Cross-multiply and solve.

$$40(0.122 - g) = 2.00(1 + g)$$
$$4.88 - 40g = 2 + 2g$$
$$4.88 - 2 = 40g + 2g$$
$$2.88 = 42g$$
$$g = \frac{2.88}{42} = 0.0686 = 6.86\%$$

**Interpretation:** The market is pricing in a 6.86% perpetual [[dividend growth rate]]. The analyst can then ask: "Is 6.86% growth realistic for this company forever?" If not, the stock may be [[overvalued]].

---

## 6 — Present Value of Growth Opportunities (PVGO)

### The Concept

A stock's value has two components:
1. **[[No-growth value]]** ($E_1/r$) — What the company would be worth if it just paid out all earnings as dividends forever, with no reinvestment and no growth. Think of a company on autopilot.
2. **[[PVGO]]** — The extra value created by the company's ability to reinvest earnings into *profitable* projects (projects that earn more than the [[Cost of capital]]).

### The Formula

$$V_0 = P_0 = \frac{E_1}{r} + PVGO$$

**What each variable means:**
- $V_0$ or $P_0$ = current stock price (assuming fair pricing)
- $E_1$ = expected [[Earnings per share]] next year
- $r$ = [[Required rate of return]]
- $E_1/r$ = value of a [[Perpetuity]] of earnings — this is what the stock would be worth with *zero* growth
- $PVGO$ = the additional value created by reinvesting in positive-[[NPV]] projects

**Why it matters:** [[PVGO]] tells you what fraction of a stock's price is driven by *expectations of future growth* versus *existing assets*. A company like **Alphabet (Google)** might have 53% of its value in PVGO — meaning over half the stock price is a bet on future innovations. A mature utility might have PVGO near zero.

### Key Insight: When Does Growth Add Value?

Growth only creates value when the company reinvests at a rate **above** its [[Cost of capital]] ($ROE > r$). If a company earns exactly its cost of capital on new investments, the [[NPV]] of those investments is zero — growth exists but adds nothing to shareholder wealth. If $ROE < r$, the company is *destroying* value by growing.

### Leading P/E and PVGO

Dividing both sides of the PVGO equation by $E_1$:

$$\frac{P}{E_1} = \frac{1}{r} + \frac{PVGO}{E_1}$$

**In plain English:** A stock's [[leading P/E]] ratio is the sum of the [[no-growth P/E]] ($1/r$) and the [[growth component]] ($PVGO/E_1$).

### Worked Example

> **Problem:** Reliable, Inc. trades at Sf 60.00, with expected [[earnings]] of Sf 5.00/share and $r$ = 10%.

**Step 1:** Calculate the [[no-growth value]].

$$\frac{E_1}{r} = \frac{5.00}{0.10} = \text{Sf }50.00$$

**Step 2:** Solve for [[PVGO]].

$$PVGO = P_0 - \frac{E_1}{r} = 60.00 - 50.00 = \text{Sf }10.00$$

**Step 3:** Find the growth component of the [[P/E]].

$$\frac{P_0}{E_1} = \frac{60}{5} = 12.0\times$$

$$\text{No-growth P/E} = \frac{1}{r} = \frac{1}{0.10} = 10.0\times$$

$$\text{Growth component} = \frac{PVGO}{E_1} = \frac{10}{5} = 2.0\times$$

So 2/12 = **16.7%** of the P/E is attributable to growth opportunities.

---

## 7 — Justified Leading and Trailing P/E Ratios

### The Concept

A **[[justified P/E]]** is the [[Price-to-earnings ratio|P/E ratio]] that a stock *deserves* based on its fundamentals (growth, risk, payout policy). It's derived from the [[GGM]], so it assumes constant growth.

> **Important note:** The "price" in the numerator of a justified P/E is actually the *[[Intrinsic value]]* from the GGM ($V_0$), not necessarily the market price. The convention is to call it P/E, but it's really $V_0/E$.

### Justified Leading (Forward) P/E

Start with the [[GGM]]: $P_0 = D_1 / (r - g)$.

Since $D_1 = E_1 \times (1 - b)$, where $b$ = [[retention rate]] and $(1-b)$ = [[Dividend payout ratio]]:

$$\frac{P_0}{E_1} = \frac{1 - b}{r - g}$$

**What each variable means:**
- $P_0/E_1$ = [[justified leading P/E]] (price today ÷ *next year's* earnings)
- $(1 - b)$ = [[Dividend payout ratio]] — the fraction of earnings paid out as dividends
- $b$ = [[retention rate]] — the fraction of earnings kept and reinvested (= 1 − payout ratio)
- $r$ = [[Required rate of return]]
- $g$ = constant [[dividend growth rate]]

**In plain English:** A stock's justified P/E is *higher* when the payout ratio is higher, when the growth rate is higher, or when the required return is lower.

### Justified Trailing P/E

$$\frac{P_0}{E_0} = \frac{(1 - b)(1 + g)}{r - g}$$

The trailing version is just the leading version multiplied by $(1 + g)$ because $E_0$ is one period behind $E_1$, so $E_1 = E_0(1+g)$, meaning dividing by the smaller $E_0$ gives a larger ratio.

### Worked Example

> **Problem:** Alliance, Inc. sells at \$16.00, current earnings \$3.00, current dividend \$1.50. Dividend growth = 3.5%. Risk-free rate = 4%, market risk premium = 6%, beta = 1.1.

**Step 1:** Find $r$.

$$r = 4\% + 1.1(6\%) = 10.6\%$$

**Step 2:** Find the [[Payout ratio]].

$$1 - b = \frac{D_0}{E_0} = \frac{1.50}{3.00} = 0.50 \quad \Rightarrow \quad b = 0.50$$

**Step 3:** Calculate justified [[leading P/E]].

$$\frac{P_0}{E_1} = \frac{1 - b}{r - g} = \frac{0.50}{0.106 - 0.035} = \frac{0.50}{0.071} = 7.04\times$$

**Step 4:** Calculate justified [[trailing P/E]].

$$\frac{P_0}{E_0} = \frac{(1 - b)(1 + g)}{r - g} = \frac{0.50 \times 1.035}{0.071} = \frac{0.5175}{0.071} = 7.29\times$$

> **Key Relationship:** Justified trailing P/E = Justified leading P/E × $(1 + g)$. Always. This is because you're dividing by a smaller number ($E_0 < E_1$), so the ratio is bigger by exactly the growth factor.

---

## 8 — Estimating Required Return from Any DDM

### GGM Required Return

If you assume the stock is fairly priced ($P_0 = V_0$), rearrange the [[GGM]]:

$$r = \frac{D_1}{P_0} + g = \frac{D_0(1+g)}{P_0} + g$$

**In plain English:** [[Total return]] = [[Dividend yield]] + [[Capital Gains Yield]]. The capital gains yield equals the growth rate $g$ in a constant-growth world.

### H-Model Required Return

The [[CFA_Glossary/H-model]] (covered later) can also be rearranged:

$$r = \frac{D_0}{P_0}\Big[(1 + g_L) + H(g_S - g_L)\Big] + g_L$$

**What the extra variables mean:**
- $g_S$ = initial high [[growth rate]]
- $g_L$ = long-run sustainable [[growth rate]]
- $H$ = half-life of the high-growth period (in years)

### Two-Stage and Complex Models

For more complex DDMs, there is no neat closed-form solution for $r$. You must use **trial and error** (or a financial calculator/spreadsheet): plug in different values of $r$ until the present value of the dividend stream equals the current market price. This is essentially solving for the [[IRR]] of the dividend stream.

### Worked Example: GGM Required Return

> **Problem:** S&W's stock is expected to pay $D_1$ = \$1.60, current price \$40.00, projected growth 9%.

$$r = \frac{1.60}{40.00} + 0.09 = 0.04 + 0.09 = 13\%$$

---

## 9 — Overvalued, Fairly Valued, or Undervalued

### The Decision Rule

After computing [[Intrinsic value]] ($V_0$) using any DDM, compare it to the [[market price]] ($P_0$):

| Comparison | Verdict | Action |
|-----------|---------|--------|
| $V_0 > P_0$ | **[[Undervalued]]** | Buy (the market is charging less than the stock is worth) |
| $V_0 < P_0$ | **[[Overvalued]]** | Sell/Avoid (the market is charging more than the stock is worth) |
| $V_0 = P_0$ | **[[Fairly valued]]** | The expected return equals the required return |

**Analogy:** Imagine you calculated that a used car is worth \$15,000 based on its condition, mileage, and comparable sales. If the dealer is asking \$12,000, it's undervalued — grab it. If they want \$18,000, it's overvalued — walk away.

### Using the Implied Growth Rate

Alternatively, you can compare the [[implied growth rate]] (the $g$ baked into the market price) against the company's [[Sustainable growth rate]]:

- If implied $g$ > sustainable $g$ → the market is too optimistic → stock is **[[overvalued]]**
- If implied $g$ < sustainable $g$ → the market is too pessimistic → stock is **[[undervalued]]**

### Worked Example

> **Problem:** JZY stock has a sustainable growth rate of 4.9% (= retention ratio × ROE = 0.60 × 8.17%). But the growth rate implied by the current stock price is 5.3%.

**Analysis:** The implied growth rate (5.3%) exceeds the sustainable growth rate (4.9%). The market is pricing in more growth than the company can sustain with internal resources. Therefore, the stock is **[[overvalued]]**.

Verify by computing intrinsic value:

$$V_0 = \frac{D_0(1 + g)}{r - g} = \frac{0.84(1.0490)}{0.08 - 0.0490} = \frac{0.8812}{0.031} = \$28.42$$

Since the stock trades at \$32.76, and $V_0$ = \$28.42 < \$32.76, the stock is confirmed [[overvalued]].

---

## 10 — Business Lifecycle: Growth Phase, Transition Phase, Maturity Phase

![[Business-Lifecycle-Dividend-Models.excalidraw]]

Most companies don't grow at a constant rate forever. They follow a **lifecycle** — just like people grow rapidly as children, slow down as teenagers, and reach a stable height as adults.

### The Three Phases

**[[Growth Phase]]**
- Rapidly expanding markets, high [[profit margins]]
- Abnormally high [[earnings growth]] ("[[Supernormal growth]]")
- Often **negative** [[Free cash flow]] because the company is investing heavily
- Low or no [[dividends]] (cash is reinvested)
- *Example:* A tech startup that's doubling revenue every year but burning cash to expand

**[[Transition Phase]]**
- Growth begins to slow as competitors enter and markets mature
- [[Profit margins]] may start to compress
- [[Free cash flow]] turns positive as investment needs decrease
- [[Dividends]] may begin or increase
- *Example:* A company like Amazon in the mid-2010s — still growing fast but starting to generate enormous cash flows

**[[Maturity Phase]]**
- Growth stabilizes at a rate comparable to the overall economy
- [[Earnings growth]], [[ROE]], and [[payout ratios]] reach sustainable long-term levels
- Dividends are stable and predictable
- *Example:* Procter & Gamble, Coca-Cola, major utilities

### Why This Matters for Valuation

The [[GGM]] assumes you're *always* in the maturity phase. But most interesting companies to value aren't there yet. That's why we need [[multistage DDMs]] — they let us model each phase separately.

---

## 11 — Multistage DDMs: Two-Stage, H-Model, Three-Stage

### Overview: Choosing the Right Model

| Model | Growth Pattern | Best For |
|-------|---------------|----------|
| [[Gordon Growth Model]] | Constant growth forever | Mature, stable companies; market indexes |
| [[Two-Stage DDM]] | High growth for $n$ years, then abrupt switch to low growth | Companies with a temporary competitive advantage (patent, first-mover) |
| [[CFA_Glossary/H-model]] | Growth starts high, declines *linearly* to mature rate | Companies where growth fades gradually (more realistic transition) |
| [[Three-Stage DDM]] | Three distinct phases: high → transition → mature | Companies clearly in the growth phase with a long runway |
| [[Spreadsheet Model]] | Any pattern you want | When you have detailed company-specific forecasts |

---

### Two-Stage DDM

**Assumption:** Dividends grow at a high rate $g_S$ for $n$ years, then immediately drop to a lower rate $g_L$ forever.

**The Formula:**

$$V_0 = \sum_{t=1}^{n} \frac{D_0(1+g_S)^t}{(1+r)^t} + \frac{D_0(1+g_S)^n(1+g_L)}{(1+r)^n(r - g_L)}$$

**What each piece means:**
- **First term:** Present value of all dividends during the high-growth period (Stage 1). Each dividend is $D_0$ grown at rate $g_S$ for $t$ periods, then discounted back.
- **Second term:** The [[Terminal value]] — the value at time $n$ of all dividends from year $n+1$ onward, growing at $g_L$ forever. This is a [[GGM]] applied at time $n$, then discounted back to today.

**Variable definitions:**
- $g_S$ = short-term [[supernormal growth rate]]
- $g_L$ = long-term sustainable [[growth rate]]
- $n$ = number of years of high growth
- $r$ = [[Required rate of return]]

### Worked Example: Two-Stage DDM

> **Problem:** Sea Island Recreation pays $D_0$ = \$1.00. Growth is 10% for 3 years, then 4% forever. Required return = 12%.

**Timeline:**

```
Today    Year 1    Year 2    Year 3    Year 4    Year 5 ...
 |         |         |         |         |         |
$1.00    $1.10     $1.21     $1.331    $1.3842   $1.4396 ...
         (×1.10)   (×1.10)   (×1.10)   (×1.04)   (×1.04)
         ←——— Stage 1 (10%) ———→ ←——— Stage 2 (4%) ———→
```

**Step 1:** Calculate Stage 1 dividends and their present values.

| Year | Dividend | PV at 12% |
|------|----------|-----------|
| 1 | $1.00 × 1.10 = $1.10 | $1.10/1.12 = $0.9821 |
| 2 | $1.00 × 1.10² = $1.21 | $1.21/1.12² = $0.9643 |
| 3 | $1.00 × 1.10³ = $1.331 | $1.331/1.12³ = $0.9474 |

Sum of Stage 1 PVs = $2.8938

**Step 2:** Calculate the [[Terminal value]] at the end of Year 3.

$$V_3 = \frac{D_4}{r - g_L} = \frac{1.331 \times 1.04}{0.12 - 0.04} = \frac{1.3842}{0.08} = \$17.3028$$

**Step 3:** Discount the [[Terminal value|terminal value]] back to today.

$$PV(V_3) = \frac{17.3028}{(1.12)^3} = \frac{17.3028}{1.4049} = \$12.3158$$

**Step 4:** Sum everything.

$$V_0 = 2.8938 + 12.3158 = \$15.21$$

> **Notice:** The [[Terminal value|terminal value]] ($12.32) represents about 81% of the total value ($15.21). This is typical — and it's why getting the terminal assumptions right is so critical.

---

### The H-Model

**Assumption:** Growth doesn't drop abruptly. Instead, it starts at a high rate $g_S$ and **declines linearly** over $2H$ years until it reaches $g_L$.

Think of it as turning a dimmer switch slowly rather than flipping a light switch.

**The Formula:**

$$V_0 = \frac{D_0(1 + g_L)}{r - g_L} + \frac{D_0 \cdot H(g_S - g_L)}{r - g_L}$$

Or combined:

$$V_0 = \frac{D_0(1 + g_L) + D_0 \cdot H(g_S - g_L)}{r - g_L}$$

**What each piece means:**
- **First term:** What the stock would be worth if it grew at $g_L$ forever starting now (this is just the [[GGM]])
- **Second term:** The *extra* value from the period of above-normal growth. The longer the high-growth period ($H$) and the bigger the gap between $g_S$ and $g_L$, the more extra value

**Variable definitions:**
- $H$ = **half-life** of the high-growth period (if high growth lasts 10 years, $H$ = 5)
- $g_S$ = initial high [[growth rate]]
- $g_L$ = long-term [[growth rate]]

### Worked Example: H-Model

> **Problem:** Omega Foods pays $D_0$ = €2.00. Growth is currently 20%, expected to decline linearly over 10 years to 5%. Required return = 12%.

**Step 1:** Identify the variables.
- $H$ = 10/2 = 5 (half-life of the 10-year high-growth period)
- $g_S$ = 20%, $g_L$ = 5%, $r$ = 12%

**Step 2:** Apply the [[CFA_Glossary/H-model]] formula.

$$V_0 = \frac{2.00(1.05)}{0.12 - 0.05} + \frac{2.00(5)(0.20 - 0.05)}{0.12 - 0.05}$$

$$V_0 = \frac{2.10}{0.07} + \frac{2.00(5)(0.15)}{0.07}$$

$$V_0 = 30.00 + \frac{1.50}{0.07}$$

$$V_0 = 30.00 + 21.43 = €51.43$$

**Interpretation:** Without the high-growth period, the stock would be worth €30.00. The declining high-growth period adds €21.43 of extra value.

---

### Three-Stage DDM

The **[[Three-Stage DDM]]** combines elements from above. There are two popular versions:

**Version 1 — Three distinct constant rates:** Growth at $g_S$ for $m$ years → Growth at $g_t$ (transition rate) for the next $n - m$ years → Growth at $g_L$ forever.

**Version 2 — Linear decline in middle stage:** Growth at $g_S$ for Stage 1 → Growth declines linearly in Stage 2 (like the [[CFA_Glossary/H-model]]) → Growth at $g_L$ forever in Stage 3.

### Three-Stage DDM Formula (Version 1)

$$V_0 = \underbrace{\sum_{a=1}^{m} \frac{D_0(1+g_S)^a}{(1+r)^a}}_{\text{Stage 1: High growth}} + \underbrace{\sum_{b=m+1}^{n} \frac{D_0(1+g_S)^m(1+g_t)^{b-m}}{(1+r)^b}}_{\text{Stage 2: Transition}} + \underbrace{\frac{D_0(1+g_S)^m(1+g_t)^{n-m}(1+g_L)}{(1+r)^n(r-g_L)}}_{\text{Stage 3: Terminal value}}$$

**Variable definitions (from the Mark Meldrum formula sheet):**
- $D$ = [[Dividends]]
- $P$ = Price
- $V$ = [[Intrinsic value]]
- $g$ = [[Growth Rate]]
- $g_S$ = short-term [[growth rate]] (high-growth period)
- $g_t$ = mid-term [[growth rate]] (transition period)
- $g_L$ = long-term [[growth rate]] (mature/low-growth period)
- $b$ = (1 − [[Dividend payout ratio]]) = [[retention ratio]]
- $H$ = half-life in years of the high-growth period
- $RR$ = [[Retention Ratio]]
- $r$ = [[Required rate of return]]

### Worked Example: Three-Stage DDM

> **Problem:** A [[Technology|technology]] company pays $D_0$ = \$3.30. Required return = 9%. Growth: 14% for 2 years, 12% for 5 years, 6.75% thereafter. Stock trades at \$194.98.

| Time | Calculation | Dividend ($D_t$) | PV at 9% |
|------|------------|----------|----------|
| 1 | 3.30 × 1.14 | $3.762 | $3.451 |
| 2 | 3.30 × 1.14² | $4.289 | $3.610 |
| 3 | 3.30 × 1.14² × 1.12 | $4.803 | $3.709 |
| 4 | 3.30 × 1.14² × 1.12² | $5.380 | $3.811 |
| 5 | 3.30 × 1.14² × 1.12³ | $6.025 | $3.916 |
| 6 | 3.30 × 1.14² × 1.12⁴ | $6.748 | $4.024 |
| 7 | 3.30 × 1.14² × 1.12⁵ | $7.558 | $4.135 |
| **7** | **Terminal: $V_7 = 7.558 × 1.0675 / (0.09 − 0.0675)$** | **$358.59** | **$196.16** |
| | | **Total** | **$222.82** |

The model gives $V_0$ = \$222.82, which is about 14% above the market price of \$194.98. The stock appears **[[undervalued]]**.

> **Key Observation:** The [[Terminal value|terminal value]] (\$196.16) represents about **88%** of total value. This is typical for multistage models and shows why the mature-stage assumptions (especially $g_L$) are so important.

---

## 12 — Terminal Value

### What Is Terminal Value?

**[[Terminal value]]** (also called **[[Continuing value]]**) is the estimated value of all dividends *beyond* the explicit forecast period. Since you can't forecast dividends individually forever, at some point you switch to a simplified model.

### Two Approaches

**Approach 1: [[Gordon Growth Model]]**

This is the most common method. At the end of your forecast period (time $n$), assume dividends will grow at a constant rate $g_L$ forever:

$$V_n = \frac{D_{n+1}}{r - g_L}$$

**Approach 2: [[Market Multiple]]**

Apply a [[P/E ratio]] (or other multiple) to forecasted earnings at the terminal date:

$$V_n = P/E \times E_n$$

### Worked Example: Both Approaches

> **Problem:** Level Partners is expected to have [[EPS]] of \$12 in 10 years, [[Payout ratio]] = 50%, $r$ = 11%, long-term $g$ = 4%, forecasted [[trailing P/E]] = 8×.

**GGM Approach:**

$D_{10}$ = \$12 × 50% = \$6.00
$D_{11}$ = \$6.00 × 1.04 = \$6.24

$$V_{10} = \frac{6.24}{0.11 - 0.04} = \frac{6.24}{0.07} = \$89.14$$

**P/E Multiple Approach:**

$$V_{10} = 8 \times \$12 = \$96.00$$

The two methods give different answers (\$89.14 vs \$96.00), which highlights that [[Terminal value|terminal value]] estimates are always uncertain and sensitive to assumptions.

---

## 13 — Spreadsheet Modeling

### When to Use It

[[Spreadsheet modeling]] is the most flexible approach. Use it when:
- You have detailed company-specific information (e.g., a defense contractor with known contracts)
- Dividends don't follow any neat pattern
- You want to test different scenarios ([[Sensitivity analysis|sensitivity analysis]])

### The Process

1. **Establish the base level** of dividends or cash flows
2. **Forecast dividends** for each individual year during the explicit forecast period (typically 3–10 years)
3. **Estimate a [[Terminal value]]** at the end of the forecast horizon using the [[GGM]] or a market multiple
4. **Discount everything** back to today at the [[Required rate of return]]

### Worked Example: Irregular Dividend Pattern

> **Problem:** Yang Co. expects $D_1$ = \$21.00. Dividends decline by 10% annually for 3 years. Year 5 dividend = \$60 (includes asset sale proceeds). Year 6 and 7 dividends = \$40. After Year 7, dividends grow at 5% forever. $r$ = 12%.

| Year | Dividend | PV at 12% | Explanation |
|------|----------|-----------|-------------|
| 1 | $21.00 | $18.75 | Set at $21 |
| 2 | $18.90 | $15.07 | Previous × 0.90 |
| 3 | $17.01 | $12.11 | Previous × 0.90 |
| 4 | $15.31 | $9.73 | Previous × 0.90 |
| 5 | $60.00 | $34.05 | [[Special dividend|Special dividend]] (asset sale) |
| 6 | $40.00 | $20.27 | Set at $40 |
| 7 | $40.00 | $18.09 | Set at $40 |
| **7** | **$V_7$ = $40 × 1.05 / (0.12 − 0.05) = $600** | **$271.41** | **GGM terminal value** |
| | **Total** | **$399.48** | |

This pattern — declining dividends, a one-time spike, then stabilization — can't be captured by any stylized model. Only a [[spreadsheet model]] can handle it.

---

## 14 — Sustainable Growth Rate and DuPont Analysis

### Sustainable Growth Rate (SGR)

The **[[Sustainable growth rate]]** is the rate at which [[earnings]] (and [[dividends]]) can grow indefinitely, assuming:
- The [[Capital structure]] ([[Debt-to-equity ratio|debt-to-equity ratio]]) stays constant
- No new equity is issued
- Growth is funded entirely by [[retained earnings]]

### The Formula

$$g = b \times ROE$$

**What each variable means:**
- $g$ = [[Sustainable growth rate]] of dividends and earnings
- $b$ = [[retention rate]] = $\frac{\text{Net Income} - \text{Dividends}}{\text{Net Income}} = 1 - \text{Dividend Payout Ratio}$
- $ROE$ = [[return on equity]] = [[Net income|Net Income]] / Shareholders' Equity

**Why it works (the intuition):** If a company earns 15% on its equity and keeps 60% of earnings, it's adding $0.60 × 15\% = 9\%$ to its equity base each year. Since earnings are proportional to equity (via ROE), earnings also grow at 9%.

### DuPont Analysis

[[DuPont analysis]] breaks [[ROE]] into three components to understand *what's driving it*:

$$ROE = \underbrace{\frac{\text{Net Income}}{\text{Sales}}}_{\text{Profit Margin}} \times \underbrace{\frac{\text{Sales}}{\text{Total Assets}}}_{\text{Asset Turnover}} \times \underbrace{\frac{\text{Total Assets}}{\text{Shareholders' Equity}}}_{\text{Equity Multiplier (Leverage)}}$$

**What each piece tells you:**
- **[[Profit margin]]:** How much profit the company squeezes out of each dollar of sales. Higher margin → higher ROE.
- **[[Asset Turnover]]:** How efficiently the company uses assets to generate sales. Higher turnover → higher ROE.
- **[[Equity Multiplier]]:** How much leverage (debt) the company uses. More leverage → higher ROE (but also more risk).

### The PRAT Model

Combining [[DuPont analysis]] with the [[Sustainable growth rate]]:

$$g = \underbrace{\frac{\text{Net Income} - \text{Dividends}}{\text{Net Income}}}_{\text{Retention Rate (R)}} \times \underbrace{\frac{\text{Net Income}}{\text{Sales}}}_{\text{Profit Margin (P)}} \times \underbrace{\frac{\text{Sales}}{\text{Total Assets}}}_{\text{Asset Turnover (A)}} \times \underbrace{\frac{\text{Total Assets}}{\text{Shareholders' Equity}}}_{\text{Financial Leverage (T)}}$$

This is called the **[[PRAT model]]**: Growth = f([[Profit margin|Profit margin]], Retention rate, Asset turnover, [[Financial leverage|financial leverage]] T).

Two of these factors are **performance-driven** (P and A → together they form [[ROA]]), and two are **financial policy decisions** (R and T).

> **Important:** Use **beginning-of-period** [[Balance sheet|balance sheet]] values for mixed ratios (e.g., total asset turnover) unless told otherwise.

### Worked Example

> **Problem:** Halo Construction has averaged: [[Profit margin]] = 10%, [[asset turnover]] = 1.8, [[leverage ratio]] = 1.25, [[Payout ratio]] = 40%.

**Step 1:** Calculate [[ROE]] using DuPont.

$$ROE = 0.10 \times 1.8 \times 1.25 = 0.225 = 22.5\%$$

**Step 2:** Calculate the [[retention rate]].

$$b = 1 - 0.40 = 0.60$$

**Step 3:** Calculate the [[Sustainable growth rate]].

$$g = b \times ROE = 0.60 \times 22.5\% = 13.5\%$$

**Interpretation:** If Halo maintains these financial characteristics and doesn't issue new equity, it can sustain dividend and earnings growth of 13.5% per year.

### Real-World Caution

If a company's actual growth exceeds its SGR, something has to give — it must either issue new equity, increase leverage, improve margins, or increase asset efficiency. Conversely, an SGR much higher than actual growth suggests the company is building [[Excess capital|excess capital]] or paying out more than it needs to.

> **IBM Example:** IBM's ROE in 2018 was 52%, and its retention rate averaged 62%. Naively, $g = 0.62 \times 52\% = 32\%$ — an absurd perpetual growth rate for a company whose sales were *declining*. The culprit? Extreme [[Financial leverage|financial leverage]] (equity multiplier of 7.35). [[DuPont analysis|DuPont analysis]] revealed that IBM's high ROE was driven almost entirely by leverage, not operating performance. Its [[Profit margin|profit margin]] and asset turnover were only modestly above [[Benchmark|benchmark]].

---

## Formula Cheat Sheet

### Core DDM

$$V_0 = \sum_{t=1}^{\infty} \frac{D_t}{(1+r)^t} = \sum_{t=1}^{n} \frac{D_t}{(1+r)^t} + \frac{P_n}{(1+r)^n}$$

### Gordon Growth Model

$$V_0 = \frac{D_1}{r - g} = \frac{D_0(1+g)}{r - g}$$

$$r = \frac{D_1}{P_0} + g$$

### Perpetuity (Preferred Stock)

$$V_0 = \frac{D}{r}$$

### PVGO

$$V_0 = \frac{E_1}{r} + PVGO$$

$$\frac{P}{E_1} = \frac{1}{r} + \frac{PVGO}{E_1}$$

### Justified P/E

$$\frac{P_0}{E_0} = \frac{(1-b)(1+g)}{r - g} \quad \text{(trailing)}$$

$$\frac{P_0}{E_1} = \frac{1-b}{r - g} \quad \text{(leading)}$$

### Two-Stage DDM

$$V_0 = \sum_{t=1}^{n} \frac{D_0(1+g_S)^t}{(1+r)^t} + \frac{D_0(1+g_S)^n(1+g_L)}{(1+r)^n(r - g_L)}$$

### H-Model

$$V_0 = \frac{D_0(1+g_L) + D_0 H(g_S - g_L)}{r - g_L}$$

### Three-Stage DDM

$$V_0 = \sum_{a=1}^{m} \frac{D_0(1+g_S)^a}{(1+r)^a} + \sum_{b=m+1}^{n} \frac{D_0(1+g_S)^m(1+g_t)^{b-m}}{(1+r)^b} + \frac{D_0(1+g_S)^m(1+g_t)^{n-m}(1+g_L)}{(1+r)^n(r-g_L)}$$

### Sustainable Growth Rate

$$g = b \times ROE = RR \times ROE$$

### DuPont (PRAT Model)

$$g = \frac{\text{NI} - \text{Div}}{\text{NI}} \times \frac{\text{NI}}{\text{Sales}} \times \frac{\text{Sales}}{\text{Total Assets}} \times \frac{\text{Total Assets}}{\text{Equity}}$$

---
