---
title: "CFA L2 - Leading P/E Ratio"
subject: "Equity Investments"
tags: [CFA-L2, equity-valuation, price-multiples, DDM, PVGO]
aliases: ["Forward P/E", "Leading P/E", "Justified Leading P/E"]
---

# Leading P/E Ratio

## The Rear-View Mirror vs. The Windshield

Imagine you're buying a rental property. Would you pay based on what it *earned last year*, or what you *expect it to earn going forward*? Obviously the future matters more — because the price you pay today is buying future cash flows, not past ones.

That's the core logic behind the **Leading P/E ratio** (also called the *forward P/E*). It prices a stock relative to *next year's* expected earnings, not the earnings that already happened.

|                | Trailing P/E                    | Leading P/E                           |
| -------------- | ------------------------------- | ------------------------------------- |
| Formula        | $P_0 / E_0$                     | $P_0 / E_1$                           |
| Earnings used  | Last 12 months (actual)         | Next 12 months (forecast)             |
| Strength       | Uses real data — no guesswork   | Forward-looking, relevant to price    |
| Weakness       | Stale — ignores what's changing | Relies on forecast accuracy           |
| Best used when | Stable, mature industries       | High-growth or recently changed firms |

The **trailing P/E** ($P_0 / E_0$) uses the earnings that already happened. It's safe and verifiable, but a stock price is a claim on *future* cash flows — so the trailing P/E is always looking in the rear-view mirror.

The **leading P/E** ($P_0 / E_1$) is forward-looking, which is why it's theoretically more appropriate for valuation — but it depends entirely on the quality of your earnings forecast.

---

## Deriving the Justified Leading P/E from the Gordon Growth Model

The **justified P/E** is the "fair" multiple implied by a company's fundamentals — what the P/E *should* be based on math, not just what the market is quoting.

We start with the [[Gordon Growth Model]] ([[GGM]]):

$$V_0 = \frac{D_1}{r - g}$$

Where:
- $V_0$ = intrinsic value of the stock today
- $D_1$ = expected dividend next period
- $r$ = [[required rate of return]] (cost of equity)
- $g$ = constant perpetual growth rate

**Step 1 — Replace dividends with earnings.**

A company pays out a fraction of its earnings as dividends. The **payout ratio** is $(1 - b)$, where $b$ is the **retention ratio** (the fraction reinvested back into the business). So:

$$D_1 = E_1 \times (1 - b)$$

**Step 2 — Substitute into GGM.**

$$V_0 = \frac{E_1(1-b)}{r - g}$$

**Step 3 — Divide both sides by $E_1$.**

$$\frac{V_0}{E_1} = \frac{1-b}{r-g}$$

This is the **justified leading P/E**:

$$\boxed{\frac{P_0}{E_1} = \frac{1-b}{r-g}}$$

Every variable has an intuitive effect:

| Variable         | Change | Effect on P/E | Why                                              |
| ---------------- | ------ | ------------- | ------------------------------------------------ |
| $g$ (growth)     | ↑      | ↑ P/E         | Denominator shrinks — future earnings worth more |
| $r$ (risk)       | ↑      | ↓ P/E         | Denominator grows — higher discount rate         |
| $b$ (retention)  | ↑      | ↓ P/E         | Less paid out as dividends (but see trap below)  |
| $(1-b)$ (payout) | ↑      | ↑ P/E         | More returned to shareholders                    |

> [!warning] Exam Trap: Payout and Growth Interact
> Increasing the payout ratio $(1-b)$ raises the numerator, but it also *reduces* $g$ because less is reinvested. You can't move one without affecting the other. The net effect depends on whether $ROE > r$. If $ROE = r$, payout ratio doesn't matter at all.

---

## The PVGO Decomposition of Leading P/E

There's a second, deeply insightful way to look at the leading P/E — by splitting the company into what it already has and what it might become.

A stock's total value is the sum of two components:

$$V_0 = \underbrace{\frac{E_1}{r}}_{\text{no-growth value}} + \underbrace{PVGO}_{\text{growth premium}}$$

- **$E_1/r$** — the [[no-growth value]]: what the company is worth if it pays out every dollar of earnings as dividends forever, never reinvests, never grows. A [[perpetuity]] of earnings. Think of a company on autopilot.
- **[[PVGO]]** (Present Value of Growth Opportunities) — the extra value created by reinvesting earnings into *profitable* projects (i.e., projects where $ROE > r$).

Divide both sides by $E_1$:

$$\frac{P_0}{E_1} = \frac{1}{r} + \frac{PVGO}{E_1}$$

This splits the leading P/E into two parts:

```
Leading P/E  =  No-Growth P/E  +  Growth Component
  P₀/E₁     =      1/r        +    PVGO/E₁
```

| Component | What it represents |
|-----------|-------------------|
| $1/r$ | The multiple you'd pay for a zero-growth perpetuity — the "floor" |
| $PVGO/E_1$ | The premium for future profitable reinvestment opportunities |

**Why this matters:** A high P/E stock like a tech company might have 70% of its P/E in $PVGO/E_1$ — meaning most of what you're paying for is *hope about future projects*. A utility might have PVGO near zero — you're paying almost entirely for the existing asset base.

> [!tip] Memory Hook: Hope vs. Assets
> Split any P/E into **"What's there now"** ($1/r$) and **"What might happen"** ($PVGO/E_1$). The more a stock relies on the second piece, the more sensitive it is to changing growth expectations.

---

## When Growth Doesn't Add Value

This is one of the most important conceptual insights in equity valuation:

**Growth only adds value when $ROE > r$.**

- If $ROE > r$: reinvesting creates positive-[[NPV]] projects → $PVGO > 0$ → P/E premium
- If $ROE = r$: reinvesting earns exactly the cost of capital → $PVGO = 0$ → no P/E premium
- If $ROE < r$: reinvesting destroys value → $PVGO < 0$ → P/E *discount*

A company that grows fast but earns below its cost of capital is actively destroying shareholder wealth by reinvesting. Investors should *want* it to pay everything out as dividends instead.

---

## Worked Numerical Example

**Setup:** FutureTech Corp. Expected earnings next year: **$5.00/share** ($E_1$). Payout ratio: **40%** (so $b = 0.60$). Required return: **$r = 10\%$**. Perpetual growth rate: **$g = 6\%$**.

**Step 1 — Justified Leading P/E (GGM method)**

$$\frac{P_0}{E_1} = \frac{1-b}{r-g} = \frac{0.40}{0.10 - 0.06} = \frac{0.40}{0.04} = 10.0\times$$

**Step 2 — Intrinsic Value**

$$V_0 = 10.0 \times \$5.00 = \$50.00$$

**Step 3 — PVGO Decomposition**

No-growth value:

$$\frac{E_1}{r} = \frac{5.00}{0.10} = \$50.00$$

PVGO:

$$PVGO = V_0 - \frac{E_1}{r} = 50 - 50 = \$0$$

**Interpretation:** Even though the company grows at 6%, its PVGO is zero. Why? Because it earns exactly its [[cost of capital]] on new investments ($ROE = r$). The growth looks busy on the income statement but isn't creating any new shareholder wealth.

**P/E decomposition:**

$$\frac{P_0}{E_1} = \frac{1}{r} + \frac{PVGO}{E_1} = \frac{1}{0.10} + \frac{0}{5} = 10.0 + 0 = 10.0\times$$

100% of the P/E reflects existing assets; 0% is a growth premium.

---

## Leading vs. Trailing P/E: The Conversion

The two multiples are always linked. Starting from the trailing P/E formula:

$$\frac{P_0}{E_0} = \frac{(1-b)(1+g)}{r-g}$$

And the leading:

$$\frac{P_0}{E_1} = \frac{1-b}{r-g}$$

The relationship is simply:

$$\text{Trailing P/E} = \text{Leading P/E} \times (1+g)$$

Because $E_1 = E_0 \times (1+g)$, trailing P/E is always slightly *higher* than leading P/E for a growing firm.

---

## Exam Traps Summary

> [!danger] Watch Out For These
> - **$D_0$ vs. $D_1$**: If the exam gives "last year's dividend" ($D_0$), you must grow it: $D_1 = D_0(1+g)$ before using the GGM.
> - **Sensitivity to $r - g$**: When $g$ is close to $r$, tiny input changes cause massive P/E swings. The exam may test whether you recognize this instability.
> - **Negative earnings**: P/E is undefined when $E < 0$. Use **earnings yield** ($E/P$) instead — it's just the reciprocal and works with negatives.
> - **PVGO < 0**: Possible and meaningful — signals value destruction via overinvestment.
> - **$ROE = r$ trap**: Growth with $ROE = r$ adds zero value. Don't confuse "growing earnings" with "growing intrinsic value."

---

## Related Concepts

- [[Gordon Growth Model]] — the foundation for the justified P/E derivation
- [[PVGO]] — decomposes P/E into no-growth and growth components
- [[Trailing P/E]] — the historical counterpart
- [[Required Rate of Return]] — drives the no-growth P/E floor ($1/r$)
- [[Retention Ratio]] / [[Payout Ratio]] — the $b$ and $(1-b)$ in the formula
- [[NPV]] — the link between PVGO and project profitability
- [[Sustainable Growth Rate]] — connects $g$ to $ROE \times b$
