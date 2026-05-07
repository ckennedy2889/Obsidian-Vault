---
title: Steady-State Growth Rate
subject: Economics
tags: [CFA-L2, economics, economic-growth, steady-state-growth, solow-model, neoclassical-growth, tfp, capital-deepening]
aliases: [steady-state growth rate, steady state growth rate, balanced growth rate, sustainable growth rate in Solow, Solow steady state growth]
---

# Steady-State Growth Rate

## The Real-World Analogy

Imagine a delivery company.

At first, the company has 10 drivers and only 2 trucks. Buying more trucks is incredibly powerful. The drivers stop waiting around. Deliveries increase quickly. Output per worker jumps.

But now imagine the company already has 10 drivers and 100 trucks. Buying the 101st truck barely helps. Most trucks sit idle. The company needs better routing software, better logistics, better fuel efficiency, or more workers. Just adding more trucks no longer creates explosive growth.

That is the intuition behind the [[Steady state rate of growth]] in the [[Solow Model (Neoclassical Growth Theory)]].

```text
Early capital deepening: powerful.
Later capital deepening: diminishing returns.
Steady state: capital deepening no longer raises the long-run growth rate.
```

## One-Sentence Definition

The steady-state growth rate is the long-run sustainable growth rate an economy reaches when key ratios, especially the capital-to-output ratio, are constant and [[Level 2/Generated Notes/03 - Economics/Capital Deepening]] no longer changes the growth rate.

In the neoclassical/Solow model, this is also called the balanced growth path.

## The Core CFA Formula

For total output:

$$
\boxed{\frac{\Delta Y}{Y} = \frac{\theta}{1-\alpha} + n}
$$

For output per worker or output per capita:

$$
\boxed{\frac{\Delta y}{y} = \frac{\theta}{1-\alpha}}
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Total output / [[Potential GDP]] |
| $y = Y/L$ | Output per worker / [[Labor productivity]] |
| $\theta$ | Growth rate of [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $\alpha$ | Capital's share of output |
| $1-\alpha$ | Labor's share of output |
| $n$ | Growth rate of the [[Labor force]] |

Memory hook:

```text
Per-worker growth = theta over labor share.
Total growth = per-worker growth plus labor growth.
```

## Why Labor's Share Is In The Denominator

Start with the Cobb-Douglas production function:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Per worker:

$$
y = \frac{Y}{L} = A k^\alpha
$$

where:

$$
k = \frac{K}{L}
$$

Taking growth rates:

$$
\frac{\Delta y}{y} = \frac{\Delta A}{A} + \alpha \frac{\Delta k}{k}
$$

Since:

$$
\frac{\Delta A}{A} = \theta
$$

we have:

$$
\frac{\Delta y}{y} = \theta + \alpha \frac{\Delta k}{k}
$$

In steady state, growth is balanced. That means capital per worker and output per worker grow at the same rate:

$$
\frac{\Delta y}{y} = \frac{\Delta k}{k}
$$

Let that common steady-state per-worker growth rate be $g^*$:

$$
g^* = \theta + \alpha g^*
$$

Move the $\alpha g^*$ term to the left:

$$
g^* - \alpha g^* = \theta
$$

Factor:

$$
g^*(1-\alpha) = \theta
$$

Solve:

$$
\boxed{g^* = \frac{\theta}{1-\alpha}}
$$

That is the steady-state growth rate of output per worker and capital per worker.

Total output adds labor force growth:

$$
\boxed{G^* = \frac{\theta}{1-\alpha} + n}
$$

## What Is Balanced In The Steady State?

In steady state, the economy is not frozen. It can still grow.

What becomes stable is the relationship among the moving parts.

| Variable | Steady-State Growth Rate |
|---|---:|
| [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] $A$ | $\theta$ |
| Labor $L$ | $n$ |
| Output per worker $y = Y/L$ | $\theta/(1-\alpha)$ |
| Capital per worker $k = K/L$ | $\theta/(1-\alpha)$ |
| Total output $Y$ | $\theta/(1-\alpha)+n$ |
| Total capital $K$ | $\theta/(1-\alpha)+n$ |
| Output-to-capital ratio $Y/K$ | Constant |
| Marginal product of capital | Constant |

This is why CFA calls it balanced growth.

```text
Capital per worker and output per worker grow together.
Total capital and total output grow together.
Key ratios stop drifting.
```

## Why Capital Deepening Stops Driving Long-Run Growth

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means increasing capital per worker:

$$
k = \frac{K}{L}
$$

When a country has very little capital per worker, adding capital is extremely productive. A worker with no machine benefits enormously from the first machine.

But as capital per worker rises, each additional unit of capital adds less output. This is [[Diminishing marginal productivity]].

```text
Low capital per worker
        ↓
High marginal product of capital
        ↓
Capital deepening raises growth strongly

High capital per worker
        ↓
Low marginal product of capital
        ↓
Extra capital adds less and less output
```

At the steady state, actual investment is just enough to:

1. Replace depreciated capital.
2. Equip new workers.
3. Keep capital per worker growing at the rate required by TFP progress.

The economy can keep adding capital, but that capital deepening no longer increases the steady-state growth rate.

This is the central CFA insight:

```text
Capital deepening can raise the level of output per worker.
TFP growth is what sustains growth in output per worker.
```

## The Steady-State Investment Condition

The steady-state condition can be written as:

$$
s f(k^*) = \left(\delta + n + g^*\right)k^*
$$

Where:

| Term | Meaning |
|---|---|
| $s$ | Saving rate |
| $f(k^*)$ | Output per worker at steady-state capital per worker |
| $\delta$ | Depreciation rate |
| $n$ | Labor force growth |
| $g^*$ | Steady-state growth in output per worker and capital per worker |
| $k^*$ | Steady-state capital per worker |

The left side is actual saving/investment per worker.

The right side is break-even investment per worker: the amount needed to replace depreciation, equip new workers, and keep up with technology-driven growth.

```text
Actual investment = break-even investment
        ↓
Steady state
```

## Worked Example 1: Per-Worker And Total Growth

Suppose:

$$
\theta = 1.4\%
$$

$$
\alpha = 0.30
$$

$$
n = 0.8\%
$$

Step 1: Compute labor's share:

$$
1-\alpha = 1 - 0.30 = 0.70
$$

Step 2: Compute steady-state growth of output per worker:

$$
g^* = \frac{\theta}{1-\alpha}
$$

$$
g^* = \frac{1.4\%}{0.70}
$$

$$
\boxed{g^* = 2.0\%}
$$

Step 3: Add labor force growth to get total output growth:

$$
G^* = g^* + n
$$

$$
G^* = 2.0\% + 0.8\%
$$

$$
\boxed{G^* = 2.8\%}
$$

Interpretation:

```text
Output per worker grows 2.0%.
Total output grows 2.8%.
The extra 0.8% comes from labor force growth.
```

## Worked Example 2: CFA-Style Country Calculation

Suppose a country has:

- TFP growth: $2.9\%$
- Labor's share of output: $56.1\%$
- Labor force growth: $1.2\%$

The total steady-state growth rate is:

$$
G^* = \frac{\theta}{1-\alpha} + n
$$

Here CFA gives labor's share directly:

$$
1-\alpha = 0.561
$$

Substitute:

$$
G^* = \frac{2.9\%}{0.561} + 1.2\%
$$

$$
G^* = 5.17\% + 1.2\%
$$

$$
\boxed{G^* = 6.37\%}
$$

Interpretation:

The economy's steady-state total output growth is 6.37%. If actual or potential GDP growth is above that for a while, the country may be below its steady state and still benefiting from catch-up capital deepening.

## What Happens If The Saving Rate Rises?

This is one of the biggest CFA traps.

A higher saving rate raises investment. More investment raises capital per worker. That can make the economy grow faster for a while.

But in the Solow model, it does not permanently raise the steady-state growth rate.

```text
Saving rate rises
        ↓
Investment rises
        ↓
Capital per worker rises
        ↓
Output per worker rises
        ↓
Economy reaches a higher level of y
        ↓
Growth rate returns to θ/(1−α)
```

So:

| Effect of Higher Saving Rate | Result |
|---|---|
| Level of output per worker | Permanently higher |
| Transition growth rate | Temporarily higher |
| Long-run steady-state growth rate | Unchanged |

Exam sentence:

```text
Saving can raise the level, but TFP raises the long-run growth rate.
```

## Why TFP Is The Star

If an economy only adds more capital, diminishing returns eventually weaken the impact.

But if [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] improves, the economy becomes better at turning capital and labor into output.

TFP growth shifts the production function upward.

```text
Capital deepening = move along the production function.
TFP growth = shift the production function upward.
```

That is why sustained per-capita growth in the neoclassical model requires TFP growth.

If:

$$
\theta = 0
$$

then:

$$
g^* = \frac{0}{1-\alpha} = 0
$$

Output per worker does not grow in steady state.

Total output can still grow if labor grows:

$$
G^* = 0 + n = n
$$

But average living standards are not rising from productivity growth.

## Real Interest Rate Implication

In the steady state, the [[Marginal product of capital]] is constant.

In the neoclassical model, the marginal product of capital is linked to the [[Real interest rate]] because firms invest until the extra output from one more unit of capital equals the cost of using capital.

In Cobb-Douglas:

$$
MPK = \alpha \frac{Y}{K}
$$

Since the output-to-capital ratio is constant in the steady state:

$$
\frac{Y}{K} = \text{constant}
$$

then:

$$
MPK = \text{constant}
$$

So real interest rates are stable along the steady-state growth path.

Interpretation:

```text
Before steady state:
Capital deepening lowers MPK as capital becomes less scarce.

At steady state:
Y/K is constant, MPK is constant, and real rates stabilize.
```

## China vs Japan-Style Intuition

A developing economy below its steady state can grow faster than its steady-state rate for a while.

Why?

It has low capital per worker, so the marginal product of capital is high. New investment is very productive. Capital deepening contributes strongly to growth.

```text
Below steady state
        ↓
Low capital per worker
        ↓
High MPK
        ↓
Capital deepening boosts growth
        ↓
Growth can exceed steady-state growth temporarily
```

A developed economy near steady state cannot rely much on more capital per worker.

```text
Near steady state
        ↓
Capital deepening no longer adds much to growth
        ↓
Growth depends mainly on TFP and labor force growth
```

## Exam Traps

| Trap | Correct Thinking |
|---|---|
| Higher saving permanently raises growth | It raises the level of output per worker; long-run growth returns to $\theta/(1-\alpha)$ |
| Capital deepening stops completely in steady state | It may continue, but it no longer raises the growth rate |
| Labor force growth raises per-capita growth | Labor force growth raises total output growth, not output per worker growth |
| The formula uses capital's share in the denominator | The denominator is labor's share, $1-\alpha$ |
| TFP growth equals output per worker growth | Output per worker growth equals $\theta/(1-\alpha)$ in steady state |
| A country growing faster than steady state must be overheating | Not necessarily; it may be below steady state and converging |
| Steady state means no growth | False. It means balanced sustainable growth |
| More capital always raises growth | Diminishing returns mean capital deepening cannot sustain growth forever |

## Decision Tree

```text
Question asks for output per worker / per-capita growth?
        ↓
Use θ/(1−α)

Question asks for total output / total GDP growth?
        ↓
Use θ/(1−α) + n

Question asks what happens when saving rises?
        ↓
Level of output per worker rises, but long-run growth rate unchanged

Question asks what drives sustained per-capita growth?
        ↓
TFP growth

Question says economy is below steady state?
        ↓
Capital deepening can temporarily raise growth above steady-state rate
```

## Memory Hooks

```text
Theta over labor share = per-worker steady-state growth.
Add n = total steady-state GDP growth.
```

```text
Saving lifts the level.
TFP lifts the long-run growth rate.
Labor growth lifts total GDP, not GDP per worker.
```

## Related Concepts

- [[Solow Model (Neoclassical Growth Theory)]]
- [[Three Growth Theories]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Labor productivity]]
- [[Labor force]]
- [[Potential GDP]]
- [[Growth Accounting]]
- [[Real interest rate]]
- [[Marginal product of capital]]
- [[Diminishing marginal productivity]]
