---
title: "CFA L2 - Justified Leading and Trailing P/E Ratios"
subject: "Equity Investments"
tags: [CFA-L2, equity-valuation, price-multiples, DDM, GGM, PVGO]
aliases: ["Justified P/E", "Forward P/E Derivation", "Trailing P/E Derivation"]
---

# Justified Leading and Trailing P/E Ratios

## What Does "Justified" Even Mean?

Think of buying a used car. The sticker price is what the dealer is *asking* — but the "justified" price is what the car is actually *worth* based on its condition, mileage, and comparable sales. If the sticker is higher than the justified price, you're overpaying.

The same logic applies to stocks. The **market P/E** is what you observe: just divide the current stock price by earnings and you get a number. But that number tells you nothing about whether it's *fair*. The **justified P/E** is the multiple that the stock *should* trade at given its fundamentals — its growth rate, risk, and dividend policy. It's the answer to: "What P/E is actually warranted here?"

When justified P/E ≠ market P/E, there's a mispricing signal.

| | Market P/E | Justified P/E |
|---|---|---|
| What it is | Observed multiple ($P_0 / E$) | Calculated "fair" multiple from fundamentals |
| Source | Market price ÷ earnings | [[Gordon Growth Model]] derivation |
| Use | Describes what investors are paying | Benchmark to detect over/undervaluation |

---

## The Two Formulas at a Glance

$$\boxed{\text{Justified Leading P/E} = \frac{P_0}{E_1} = \frac{1-b}{r-g}}$$

$$\boxed{\text{Justified Trailing P/E} = \frac{P_0}{E_0} = \frac{(1-b)(1+g)}{r-g}}$$

Where:
- $b$ = **[[retention ratio]]** — the fraction of earnings *kept* and reinvested
- $(1-b)$ = **[[payout ratio]]** — the fraction paid out as dividends
- $r$ = **[[required rate of return]]** on equity (cost of equity)
- $g$ = **constant perpetual growth rate**
- $E_1$ = expected earnings per share *next* year (leading)
- $E_0$ = earnings per share *this* year, just reported (trailing)

---

## Deriving the Justified Leading P/E

**Start with the [[Gordon Growth Model]]:**

$$V_0 = \frac{D_1}{r - g}$$

**Step 1 — Express dividends in terms of earnings.**

A company pays out only a fraction of its earnings as dividends. That fraction is the payout ratio $(1-b)$. So:

$$D_1 = E_1 \times (1-b)$$

**Step 2 — Substitute into GGM.**

$$V_0 = \frac{E_1(1-b)}{r-g}$$

**Step 3 — Divide both sides by $E_1$.**

$$\frac{V_0}{E_1} = \frac{1-b}{r-g}$$

Assuming the stock is fairly priced ($P_0 = V_0$):

$$\frac{P_0}{E_1} = \frac{1-b}{r-g}$$

That's it. The justified leading P/E is entirely determined by three inputs: how much the company pays out, how risky it is, and how fast it grows.

---

## Deriving the Justified Trailing P/E

The trailing P/E uses *current* (already reported) earnings $E_0$, not next year's forecast.

**Start with the GGM expressed using $D_0$:**

$$V_0 = \frac{D_0(1+g)}{r-g}$$

(Because $D_1 = D_0 \times (1+g)$ — dividends grow at rate $g$.)

**Step 1 — Express current dividend in terms of current earnings.**

$$D_0 = E_0 \times (1-b)$$

**Step 2 — Substitute.**

$$V_0 = \frac{E_0(1-b)(1+g)}{r-g}$$

**Step 3 — Divide both sides by $E_0$.**

$$\frac{P_0}{E_0} = \frac{(1-b)(1+g)}{r-g}$$

---

## The Relationship Between the Two

Leading and trailing P/E are not independent — they're linked by the growth rate.

Since $E_1 = E_0 \times (1+g)$:

$$\text{Trailing P/E} = \text{Leading P/E} \times (1+g)$$

```
Trailing P/E  >  Leading P/E   (always, for g > 0)
```

The trailing P/E is always *higher* than the leading P/E for a growing company. This makes intuitive sense: the trailing ratio uses a *smaller* denominator (last year's earnings), so the multiple looks bigger.

> [!tip] Memory Hook: Which Is Bigger?
> Trailing = Leading × (1+g). Since (1+g) > 1, trailing is always the larger number. If you mix them up on the exam, your valuation conclusion will flip.

---

## How to Use Them: Detecting Mispricing

The comparison is always between the *justified* multiple (what the stock is worth) and the *actual market* multiple (what you're being asked to pay).

```
Justified P/E  >  Actual Market P/E  →  Undervalued  (buy signal)
Justified P/E  <  Actual Market P/E  →  Overvalued   (avoid/sell)
Justified P/E  =  Actual Market P/E  →  Fairly valued
```

Equivalently, you can just compute the intrinsic value directly:

$$V_0 = \text{Justified P/E} \times E$$

Then compare $V_0$ to $P_0$. Same answer, different path.

---

## What Drives the P/E Higher or Lower

From $\frac{1-b}{r-g}$, three levers control the multiple:

| Driver | Direction | Effect on P/E | Intuition |
|--------|-----------|---------------|-----------|
| Growth $g$ ↑ | Denominator shrinks | P/E ↑ | Future earnings worth more |
| Risk $r$ ↑ | Denominator grows | P/E ↓ | Higher discount rate lowers present value |
| Payout $(1-b)$ ↑ | Numerator grows | P/E ↑ (if $ROE > r$) | More returned to shareholders |
| Retention $b$ ↑ | Numerator shrinks | P/E ↓ (if $ROE < r$) | Reinvesting at below-cost-of-capital destroys value |

> [!warning] The Payout-Growth Trap
> You cannot increase the payout ratio $(1-b)$ in isolation. More payout means less retained ($b$ falls), which typically *reduces* $g = ROE \times b$. The two variables are linked through the [[sustainable growth rate]]. Whether raising payout increases or decreases P/E depends entirely on whether $ROE > r$ or $ROE < r$.

### The Special Case: $ROE = r$

When a company earns exactly its cost of capital on new investments, growth adds zero value. In this case, the justified leading P/E collapses to:

$$\frac{P_0}{E_1} = \frac{1}{r}$$

The payout ratio and growth rate cancel out entirely — the P/E is just the reciprocal of the required return. This is the "no-growth" benchmark from the [[PVGO]] framework.

---

## Worked Examples

### Example 1 — Justified Leading P/E

**TechFast Corp.** Expected EPS next year: **$5.00** ($E_1$). Payout ratio: **40%** (so $1-b = 0.40$, $b = 0.60$). Required return: **$r = 10\%$**. Growth rate: **$g = 6\%$**.

$$\text{Justified Leading P/E} = \frac{1-b}{r-g} = \frac{0.40}{0.10-0.06} = \frac{0.40}{0.04} = \mathbf{10.0\times}$$

Intrinsic value: $10.0 \times \$5.00 = \$50.00$

If TechFast trades at $55, the market P/E = $55/$5 = 11.0×. Since 11.0× > 10.0×, the stock is **overvalued**.

---

### Example 2 — Justified Trailing P/E

**SteadyCorp.** Current EPS just reported: **$4.00** ($E_0$). Payout ratio: **50%** ($1-b = 0.50$). Required return: **$r = 12\%$**. Growth rate: **$g = 5\%$**.

$$\text{Justified Trailing P/E} = \frac{(1-b)(1+g)}{r-g} = \frac{0.50 \times 1.05}{0.12-0.05} = \frac{0.525}{0.07} = \mathbf{7.5\times}$$

Intrinsic value: $7.5 \times \$4.00 = \$30.00$

If SteadyCorp trades at $28, the market P/E = $28/$4 = 7.0×. Since 7.0× < 7.5×, the stock is **undervalued**.

---

### Verify the Leading–Trailing Relationship

Using SteadyCorp above:

$$\text{Justified Leading P/E} = \frac{1-b}{r-g} = \frac{0.50}{0.07} = 7.14\times$$

$$\text{Trailing} = \text{Leading} \times (1+g) = 7.14 \times 1.05 = 7.5\times \checkmark$$

---

## Exam Traps Summary

> [!danger] Don't Get Caught By These
> - **$D_0$ given, need $D_1$**: Always grow it — $D_1 = D_0(1+g)$ — before plugging into GGM.
> - **Trailing > Leading**: Trailing P/E is always the larger number for $g > 0$. Mixing them up flips your valuation conclusion.
> - **Payout raises P/E… or does it?** Only if $ROE > r$. If not, higher payout just signals the company is rationally giving up on bad projects.
> - **Sensitivity**: When $r - g$ is small (say, 1–2%), tiny changes in inputs cause massive P/E swings. The exam may ask you to recognize this instability.
> - **Justified ≠ Intrinsic value directly**: Justified P/E is a *ratio* — multiply by the relevant earnings figure to get dollars.
> - **Which earnings to use**: Leading P/E multiplies by $E_1$; trailing P/E multiplies by $E_0$. Don't swap them.

---

## Related Concepts

- [[Gordon Growth Model]] — the foundation of both derivations
- [[PVGO]] — leading P/E decomposes into $1/r + PVGO/E_1$
- [[Leading PE Ratio]] — full treatment of the leading P/E
- [[Sustainable Growth Rate]] — ties $g$, $ROE$, and $b$ together
- [[Required Rate of Return]] — the $r$ in all formulas
- [[Payout Ratio]] / [[Retention Ratio]] — the $(1-b)$ and $b$ terms
- [[Discounted Dividend Valuation]] — the broader DDM framework
