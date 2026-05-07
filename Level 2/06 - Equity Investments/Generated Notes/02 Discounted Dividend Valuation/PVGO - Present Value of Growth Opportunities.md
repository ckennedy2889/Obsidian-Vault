---
title: "CFA L2 - PVGO (Present Value of Growth Opportunities)"
subject: "Equity Investments"
tags: [CFA-L2, equity, PVGO, valuation, DDM, growth, ROE, cost-of-equity]
aliases: ["PVGO", "Present Value of Growth Opportunities", "Value of Growth"]
---

# PVGO — Present Value of Growth Opportunities

Imagine you're buying a lemonade stand. You're really paying for two things at the same time: the money the stand makes *right now* with its current setup — pitchers, lemons, the corner spot — and the potential for the owner to take some of that profit and open new stands in other neighbourhoods. The first part is what the business is worth today standing still. The second part is the value of future smart decisions.

That's PVGO in a nutshell. When you buy a stock, you're always buying both of those things: the value of what the company already has, and the "hope value" — the extra premium the market assigns because investors believe management will find great ways to grow.

---

## The Core Idea: Two Buckets of Value

Every stock price can be split into exactly two pieces:

$$V_0 = \frac{E_1}{r} + PVGO$$

| Symbol | Meaning |
|---|---|
| $V_0$ | Current stock price |
| $E_1$ | Expected earnings per share next year |
| $r$ | [[Cost of Equity]] — the return shareholders require |
| $\frac{E_1}{r}$ | The **no-growth value** — what the stock would be worth if the company never invested another dollar and just paid everything out forever |
| $PVGO$ | The **growth value** — the extra premium from future reinvestment opportunities |

**The no-growth value** $\frac{E_1}{r}$ is just a perpetuity (defined as: a stream of equal cash flows that lasts forever). If a company earned $4 per share forever and your required return is 10%, that stream is worth $4 / 0.10 = \$40$ today. Simple.

**PVGO** is everything above that $40. It's the market saying: "we believe this management team will take some of those earnings and invest them in projects that earn *more* than shareholders could earn elsewhere."

---

## The Real Question: What Happens to a Dollar of Profit?

This is where the intuition clicks. Every dollar a company earns faces a fork in the road:

```
Dollar of Profit
├── Pay it out as a dividend
│   └── Shareholders invest it themselves at rate r
│       → No extra value created (they could do this anyway)
│
└── Retain and reinvest
    ├── If ROE > r → Creates value → PVGO is POSITIVE
    ├── If ROE = r → Neutral → PVGO is ZERO
    └── If ROE < r → Destroys value → PVGO is NEGATIVE
```

The key insight: growth only creates value if the *return on that reinvestment* (measured by [[Return on Equity|ROE]]) beats the *cost of equity* ($r$). Bigger isn't always better — more profitable is better.

---

## Positive, Zero, and Negative PVGO

This is one of the most important distinctions in equity valuation:

| Scenario | Condition | What It Means | Real-World Analogy |
|---|---|---|---|
| **Positive PVGO** | $ROE > r$ | Management creates value — they take your dollar and turn it into more than you could yourself | Giving $10 to a friend who returns $15 |
| **Zero PVGO** | $ROE = r$ | Growth is value-neutral — reinvesting earns exactly what shareholders could get elsewhere | Giving $10 to a friend who returns exactly $10 |
| **Negative PVGO** | $ROE < r$ | Management destroys value — they take your dollar and earn less than you could in an index fund | Giving $10 to a friend who returns $8 |

The third scenario is the trap that catches people out. A company can be *growing its revenue* while simultaneously *destroying shareholder value*. If management is ploughing money into projects earning 6% when shareholders require 10%, the stock would actually be worth *more* if the company just stopped investing and paid everything out as dividends. More activity, less value.

---

## Derivation — Where the Formula Comes From

Start with the [[Gordon Growth Model|DDM (Gordon Growth Model)]]:

$$V_0 = \frac{D_1}{r - g}$$

A company that pays out all its earnings has no retained earnings, so no growth ($g = 0$) and $D_1 = E_1$:

$$\text{No-growth value} = \frac{E_1}{r}$$

Now, a growing company pays out only a fraction of earnings (the **dividend payout ratio**) and retains the rest to reinvest. The growth that retained reinvestment creates has a present value — that's PVGO. So:

$$V_0 = \underbrace{\frac{E_1}{r}}_{\text{no-growth value}} + \underbrace{PVGO}_{\text{value of future investments}}$$

Rearranging to solve for PVGO:

$$PVGO = V_0 - \frac{E_1}{r}$$

You can calculate it directly from a stock's market price and expected earnings.

---

## Worked Numerical Example — Tech-Grow Inc.

**Given:**

| Item | Value |
|---|---|
| Expected EPS next year ($E_1$) | $4.00 |
| Required return / cost of equity ($r$) | 10% |
| Current market price ($V_0$) | $65.00 |

**Step 1 — No-growth value:**

$$\frac{E_1}{r} = \frac{\$4.00}{0.10} = \$40.00$$

This is what Tech-Grow would be worth if it declared "no more investing — we're paying out everything forever."

**Step 2 — Solve for PVGO:**

$$PVGO = V_0 - \frac{E_1}{r} = \$65.00 - \$40.00 = \$25.00$$

**Step 3 — Interpret:**

$$\frac{PVGO}{V_0} = \frac{\$25}{\$65} = 38.5\%$$

So **38.5% of Tech-Grow's stock price is pure hope** — the market's belief that management will find great projects in the future. If management disappoints and growth opportunities dry up, the stock could fall toward $40.

This is also a risk. High-PVGO companies are fragile — their price is built on expectations. One bad earnings report or a signal that growth is slowing can wipe out a large portion of the stock price very quickly.

---

## The Link to ROE and Cost of Equity

PVGO is essentially a scorecard on management quality:

$$PVGO > 0 \iff ROE > r_e$$

Where [[Return on Equity|ROE]] is the return management earns on reinvested capital, and $r_e$ is the [[Cost of Equity]] (what shareholders require).

**Mnemonic — "ROE vs. r is the game":**
- ROE **beats** the cost of equity → growth **adds** to price → **buy** the growth
- ROE **trails** the cost of equity → growth **subtracts** from price → **prefer** dividends

This is directly linked to [[WACC]] thinking: the cost of equity in PVGO is the same hurdle rate concept from WACC. If a company can't beat its own cost of capital on new investments, it should stop investing and return cash to shareholders instead.

---

## Connecting to DDM and Interest Rates

**Link to [[Discounted Dividend Valuation|DDM]]:**

PVGO and the Gordon Growth Model are two lenses on the same thing. DDM gives you total value by discounting all future dividends. PVGO splits that total into "what we have now" vs "what we hope to build." They should give the same answer.

**Link to interest rates:**

When interest rates rise, $r$ (the cost of equity) rises. This does two things simultaneously:
1. The no-growth value $\frac{E_1}{r}$ shrinks — the same earnings stream is worth less at a higher discount rate
2. The PVGO shrinks — future growth projects are discounted more heavily

This is why growth stocks (high PVGO companies) are hit hardest when interest rates rise. A company where 60% of its value is PVGO loses far more than a boring utility where PVGO is near zero. See [[Equity Valuation - Applications and Processes]].

---

## Side-by-Side: High PVGO vs. Low PVGO Companies

| | **High PVGO** | **Low PVGO** |
|---|---|---|
| **Example** | Tech company, biotech | Utility, mature retailer |
| **Where value comes from** | Future growth opportunities | Current assets and earnings |
| **P/E ratio** | High | Low |
| **Sensitivity to rates** | Very high | Low |
| **Risk** | High — priced on expectations | Low — priced on what already exists |
| **Management matters** | Enormously — they decide how to deploy capital | Less so — business runs on existing infrastructure |

---

## Related Notes

- [[Equity Valuation - Applications and Processes]]
- [[Discounted Dividend Valuation]]
- [[Gordon Growth Model]]
- [[Return on Equity]]
- [[Cost of Equity]]
- [[CAPM]]
- [[Weighted Average Cost of Capital (WACC)]]
- [[DuPont Analysis & ROE]]
- [[Free Cash Flow Valuation]]

---
