---
title: Rental Price of Capital
subject: Economics
tags: [CFA-L2, economics, economic-growth, capital, marginal-product-of-capital, cobb-douglas]
aliases: [rental price of capital, cost to rent capital, r, real rental price of capital, rental rate of capital]
---

# Rental Price of Capital

## The Real-World Analogy

Imagine a construction company deciding whether to rent one more crane.

The crane has a rental cost. Maybe it costs $1,000 per day to use.

The company asks:

```text
If I rent this crane, how much extra output/revenue can I produce?
```

If the extra output is worth $1,500 per day, renting the crane is profitable.

If the extra output is worth $700 per day, renting the crane is not profitable.

The [[Level 2/Generated Notes/03 - Economics/Rental Price of Capital]] is the cost of using one more unit of capital for a period of time.

The [[Marginal product of capital]] is the extra output from using one more unit of capital.

The firm compares them:

```text
Benefit of one more machine = MPK
Cost of one more machine = rental price of capital
```

## The One-Minute Version

The rental price of capital is:

> the cost per unit of time to rent or use one unit of capital.

In CFA Economics, it is usually represented by:

$$
r
$$

The profit-maximizing condition is:

$$
\boxed{MPK = r}
$$

Meaning:

```text
Firms add capital until the extra output from the last unit of capital equals the cost of using it.
```

If:

$$
MPK > r
$$

the firm should add capital.

If:

$$
MPK < r
$$

the firm has too much capital.

## What The Rental Price Of Capital Is

Capital includes productive assets such as:

- machines;
- equipment;
- buildings;
- vehicles;
- computers;
- structures;
- productive infrastructure.

The rental price of capital is the cost of using that capital for a period.

It can be thought of as the real cost of capital services.

```text
Owning a machine gives you capital services over time.
Renting a machine means paying for those services directly.
The rental price is the price of those services.
```

The idea is broader than literal renting. Even if a firm owns a machine, using it has an opportunity cost. The firm could have rented it out, sold it, or invested the funds elsewhere.

So $r$ is the economic cost of using capital, not merely the invoice price on a rental agreement.

## Why Profit-Maximizing Firms Set MPK = r

A firm adds capital as long as the next unit of capital produces more value than it costs.

Decision rule:

| Condition | Firm Action | Why |
|---|---|---|
| $MPK > r$ | Add capital | Extra output exceeds cost |
| $MPK = r$ | Stop adding capital | Extra output exactly equals cost |
| $MPK < r$ | Reduce/avoid capital | Extra output is less than cost |

The mechanism:

```text
One more machine
  |
  v
Creates extra output = MPK
  |
  v
Costs rental price = r
  |
  v
Compare MPK with r
```

Why equality is the stopping point:

If $MPK > r$, there is still profit left from adding capital.

If $MPK < r$, the last unit of capital costs more than it produces.

At $MPK = r$, the firm has no incentive to add or remove capital at the margin.

## Cobb-Douglas Link

The [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]] is:

$$
Y = A K^\alpha L^{1-\alpha}
$$

The marginal product of capital is:

$$
MPK = \alpha A K^{\alpha-1}L^{1-\alpha}
$$

This simplifies to:

$$
\boxed{MPK = \alpha \frac{Y}{K}}
$$

Why?

Because:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Divide by $K$:

$$
\frac{Y}{K} = A K^{\alpha-1}L^{1-\alpha}
$$

So:

$$
MPK = \alpha A K^{\alpha-1}L^{1-\alpha}
=
\alpha \frac{Y}{K}
$$

Then profit maximization sets:

$$
\alpha \frac{Y}{K} = r
$$

## Why Alpha Becomes Capital's Income Share

Start with:

$$
MPK = r
$$

In Cobb-Douglas:

$$
MPK = \alpha \frac{Y}{K}
$$

So:

$$
\alpha \frac{Y}{K} = r
$$

Multiply both sides by $K$:

$$
\alpha Y = rK
$$

Divide by $Y$:

$$
\boxed{\alpha = \frac{rK}{Y}}
$$

Now interpret the terms:

| Term | Meaning |
|---|---|
| $r$ | Rental price per unit of capital |
| $K$ | Total capital stock |
| $rK$ | Total income paid to capital |
| $Y$ | Total output/income |
| $rK/Y$ | Capital's share of total income |

Therefore:

$$
\boxed{\alpha = \text{capital's share of income}}
$$

And:

$$
\boxed{1-\alpha = \text{labor's share of income}}
$$

The why ladder:

```text
Rule:
Alpha equals capital's income share.

Why:
Firms pay capital according to its marginal product.

Mechanism:
Profit maximization makes MPK = r.

Algebra:
alpha Y/K = r -> alpha = rK/Y.

Meaning:
rK is total capital income, and Y is total income.

Exam implication:
If capital earns 30% of GDP, alpha = 0.30 in growth accounting.
```

## Relation To Real Interest Rates

The rental price of capital is often linked to the real interest rate.

Why?

Because using capital has an opportunity cost.

A firm can:

```text
Use money to buy/rent capital
```

or:

```text
Invest/lend the money elsewhere and earn a real return
```

In equilibrium, the return from physical capital should line up with the real cost of using capital.

So CFA notes often write:

$$
MPK = r
$$

where $r$ can be interpreted as the real rental price of capital or real required return on capital services.

Be careful:

This is an Economics growth-model concept. It is related to cost of capital, but it is not the same as corporate finance [[Weighted average cost of capital|WACC]].

## Rental Price vs Depreciation vs WACC

These are easy to mix up.

| Concept | Meaning | CFA Context |
|---|---|---|
| Rental price of capital, $r$ | Cost per period to use one unit of capital | Production functions, MPK, capital deepening |
| [[Depreciation]], $\delta$ | Rate at which capital wears out or becomes obsolete | Solow break-even investment |
| [[Weighted average cost of capital|WACC]] | Company's financing cost from debt/equity | Corporate Issuers / valuation |

Rental price asks:

```text
What does it cost to use capital this period?
```

Depreciation asks:

```text
How much of the capital stock wears out this period?
```

WACC asks:

```text
What return do providers of financial capital require?
```

They are related economically, but they are not interchangeable exam terms.

## Capital Deepening Link

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means:

$$
\frac{K}{L} \uparrow
$$

As capital per worker rises, the marginal product of capital tends to fall.

```text
More capital per worker
  |
  v
Capital becomes less scarce
  |
  v
Each extra unit of capital adds less output
  |
  v
MPK falls
```

Firms keep adding capital while:

$$
MPK > r
$$

They stop when:

$$
MPK = r
$$

That is why the rental price of capital marks the stopping point for pure capital deepening.

## Solow Steady State Link

In the [[Solow Model (Neoclassical Growth Theory)]], capital deepening cannot continue forever as a source of per-worker growth.

Why?

Because as $K/L$ rises, $MPK$ falls.

Eventually:

$$
MPK = r
$$

At that point, firms have no incentive to increase $K/L$ further beyond what is needed to maintain equilibrium.

With no [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP]] growth, pure capital deepening eventually runs out.

With TFP growth, the production function shifts upward, which can raise MPK and make additional capital investment profitable again.

## Worked Example 1: Implied Rental Price

Suppose:

- Output: $Y = 5{,}000$
- Capital stock: $K = 10{,}000$
- Capital share: $\alpha = 0.30$

Use:

$$
r = \alpha \frac{Y}{K}
$$

Substitute:

$$
r = 0.30 \times \frac{5{,}000}{10{,}000}
$$

Compute:

$$
\frac{5{,}000}{10{,}000} = 0.50
$$

$$
r = 0.30 \times 0.50 = 0.15
$$

Conclusion:

$$
\boxed{r = 15\%}
$$

Interpretation:

The implied rental price or required real return on capital is 15% per period.

## Worked Example 2: Should The Firm Add Capital?

Suppose a new machine costs $1,000 to use for the year and produces $120 of additional output value.

The marginal product/return from the machine is:

$$
MPK = \frac{120}{1{,}000} = 0.12 = 12\%
$$

Suppose the rental price of capital is:

$$
r = 10\%
$$

Compare:

$$
MPK = 12\% > r = 10\%
$$

Decision:

The firm should add the machine.

Why:

The machine produces more value than it costs to use.

## Worked Example 3: Capital's Income Share

Suppose:

- Rental price of capital: $r = 8\%$
- Capital stock: $K = 2{,}000$
- Output: $Y = 5{,}000$

Capital income:

$$
rK = 0.08 \times 2{,}000 = 160
$$

Capital's income share:

$$
\frac{rK}{Y} = \frac{160}{5{,}000} = 0.032 = 3.2\%
$$

So:

$$
\alpha = 3.2\%
$$

Interpretation:

In this simplified setup, capital receives 3.2% of total output. If this seems low versus typical macro capital shares, that is a clue that either $r$, $K$, or $Y$ may be scaled differently in the problem. Always follow the units CFA gives you.

## Decision Tree: Add More Capital?

```text
Step 1: Compare MPK with rental price r.
  |
  +-- MPK > r
  |     |
  |     +-- Decision: add capital.
  |     |
  |     +-- Why: the extra unit of capital produces more output than it costs to use.
  |
  +-- MPK = r
  |     |
  |     +-- Decision: stop adding capital at the margin.
  |     |
  |     +-- Why: the extra unit just covers its cost; no extra marginal profit remains.
  |
  +-- MPK < r
        |
        +-- Decision: do not add capital; reduce if possible.
        |
        +-- Why: the extra unit costs more than the output it produces.
```

## Decision Tree: What Happens As K/L Rises?

```text
Step 1: Is capital per worker rising?
  |
  +-- Yes
  |     |
  |     +-- Decision: expect MPK to fall over time, holding TFP constant.
  |     |
  |     +-- Why: capital becomes less scarce relative to labor, so each extra unit adds less output.
  |
  +-- No
        |
        +-- Decision: do not assume MPK is falling because of capital deepening.
        |
        +-- Why: diminishing MPK from capital deepening requires more capital per worker.

Step 2: Does TFP rise?
  |
  +-- Yes
  |     |
  |     +-- Decision: MPK may rise or capital investment may become profitable again.
  |     |
  |     +-- Why: higher TFP makes each unit of capital more productive.
  |
  +-- No
        |
        +-- Decision: pure capital deepening eventually hits MPK = r.
        |
        +-- Why: diminishing marginal productivity lowers MPK as K/L rises.
```

## Common CFA Traps

### Trap 1: Confusing Rental Price With Depreciation

Depreciation is capital wearing out.

Rental price is the cost of using capital for a period.

### Trap 2: Forgetting The Firm Stops At MPK = r

The stopping point is not when MPK is zero.

The stopping point is when:

$$
MPK = r
$$

Because capital is costly.

### Trap 3: Mixing This With WACC

In Economics growth models, $r$ is the rental price or real required return on capital services.

In Corporate Issuers, WACC is the firm's weighted average financing cost.

Related idea, different context.

### Trap 4: Forgetting Alpha's Dual Role

$\alpha$ is:

- capital's output elasticity;
- capital's income share;
- capital's weight in growth accounting.

The bridge is:

$$
\alpha = \frac{rK}{Y}
$$

### Trap 5: Thinking Capital Deepening Can Continue Forever

As capital per worker rises, MPK falls. Eventually MPK equals the rental price of capital, and pure deepening stops being profitable.

## Minimum Memorization

Memorize:

$$
\boxed{MPK = r}
$$

$$
\boxed{MPK = \alpha \frac{Y}{K}}
$$

$$
\boxed{\alpha = \frac{rK}{Y}}
$$

And the intuition:

```text
r = cost of using capital.
MPK = benefit of using one more unit of capital.

Add capital while MPK > r.
Stop when MPK = r.

As K/L rises, MPK falls.
TFP can raise MPK by making capital more productive.
```

## Can I Solve This?

1. If $Y = 4{,}000$, $K = 8{,}000$, and $\alpha = 0.25$, what is $r$?

$$
r = \alpha \frac{Y}{K}
= 0.25 \times \frac{4{,}000}{8{,}000}
= 0.25 \times 0.50
= 0.125
$$

Answer: $r = 12.5\%$.

2. If $MPK = 9\%$ and $r = 11\%$, should the firm add capital?

Answer: No. The extra capital produces less than it costs.

3. If capital per worker rises and TFP is unchanged, what happens to MPK?

Answer: MPK tends to fall because of diminishing marginal productivity of capital.

4. Why does TFP growth make more capital investment attractive?

Answer: TFP raises the productivity of capital, increasing MPK relative to the rental price.

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Marginal product of capital]]
- [[Marginal product]]
- [[Diminishing marginal productivity]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Cost of capital]]
- [[Weighted average cost of capital]]
- [[Depreciation]]
- [[Growth accounting equation]]
