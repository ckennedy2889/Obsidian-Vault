---
title: Capital Deepening and TFP Relationship
subject: Economics
tags: [CFA-L2, economics, economic-growth, capital-deepening, tfp, labor-productivity, solow-model, growth-accounting]
aliases: [capital deepening vs TFP, capital deepening and total factor productivity, capital deepening versus technological progress, capital deepening and TFP]
---

# Capital Deepening and TFP Relationship

## The Big Intuition

Think of an economy as a kitchen.

Workers are the cooks. Capital is the ovens, knives, refrigerators, counters, delivery systems, and software. [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] is the recipe, workflow, timing, training, layout, and organization that determine how well the cooks and tools are used.

There are two ways to make each cook produce more meals:

```text
1. Give each cook more/better tools.
   This is capital deepening.

2. Make the same cooks and tools work better together.
   This is TFP growth.
```

That is the entire relationship.

```text
Capital deepening = more tools per worker.
TFP = better use of workers and tools.
```

## The Core Formula

Start with the [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Divide by labor to get output per worker:

$$
y = A k^\alpha
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Total output / [[Real GDP]] or [[Potential GDP]] |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $K$ | [[Level 2/Generated Notes/03 - Economics/Capital Stock]] |
| $L$ | Labor |
| $y = Y/L$ | Output per worker / [[Labor productivity]] |
| $k = K/L$ | Capital per worker |
| $\alpha$ | Capital's output elasticity / capital share |

This formula says:

```text
Labor productivity depends on:
1. capital per worker, k;
2. TFP, A.
```

So output per worker can rise because:

```text
k rises → capital deepening
A rises → TFP growth / technological progress
```

## Capital Deepening: The k Route

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means an increase in the capital-to-labor ratio:

$$
k = \frac{K}{L}
$$

Capital deepening happens when capital grows faster than labor:

$$
\frac{\Delta K}{K} > \frac{\Delta L}{L}
$$

Or:

$$
\frac{\Delta k}{k} \approx \frac{\Delta K}{K} - \frac{\Delta L}{L} > 0
$$

Plain English:

```text
Each worker has more capital to work with.
```

Examples:

| Example | Why It Is Capital Deepening |
|---|---|
| More machines per factory worker | Each worker can produce more units |
| More computers per analyst | Each worker can process more information |
| Better logistics equipment per warehouse worker | Each worker can move more goods |
| More infrastructure per worker | Transportation and production become easier |

In the formula:

$$
y = A k^\alpha
$$

capital deepening raises $y$ by raising $k$, holding $A$ constant.

## TFP: The A Route

[[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] means the efficiency with which labor and capital are transformed into output.

In the formula:

$$
y = A k^\alpha
$$

TFP growth raises $y$ by raising $A$, even if $k$ is unchanged.

Plain English:

```text
The same workers and same capital produce more output.
```

Examples:

| Example | Why It Is TFP |
|---|---|
| Better production process | Same inputs create more output |
| Improved management system | Workers and machines are coordinated better |
| New software that reduces downtime | Existing capital is used more efficiently |
| Better legal/property-rights environment | Resources are allocated more productively |
| Knowledge spillovers | Firms learn better methods from each other |

TFP is often measured as the [[Solow residual]] because we cannot observe it directly:

$$
\frac{\Delta A}{A}
\approx
\frac{\Delta Y}{Y}
-
\alpha\frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
$$

It is the growth left over after accounting for measured capital and labor growth.

## The Visual Difference

Capital deepening is a movement along the same production function.

```text
Output per worker, y
  |
  |                         B
  |                    .
  |               .
  |          A
  |     .
  |  .
  +-------------------------------- Capital per worker, k
          k rises → move along curve
```

TFP growth shifts the entire production function upward.

```text
Output per worker, y
  |
  |                         new curve after TFP growth
  |                    . . . . . . . . .
  |               .
  |          old curve
  |     .
  |  .
  +-------------------------------- Capital per worker, k
          same k, higher y
```

Memory hook:

```text
Capital deepening moves right.
TFP shifts up.
```

## Labor Productivity Growth Equation

The relationship is clearest in the labor productivity growth equation:

$$
\boxed{
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha\frac{\Delta k}{k}
}
$$

Plain English:

```text
Labor productivity growth
=
TFP growth
+
capital deepening contribution
```

This equation is the bridge between the concepts.

| Component | Meaning |
|---|---|
| $\Delta y/y$ | Growth in output per worker |
| $\Delta A/A$ | TFP growth |
| $\alpha \Delta k/k$ | Capital deepening contribution |

The capital deepening contribution is multiplied by $\alpha$ because capital has diminishing marginal returns. If $\alpha = 0.30$, a 1% increase in capital per worker raises output per worker by only about 0.30%, holding TFP constant.

## Worked Example: Separating Capital Deepening From TFP

Suppose:

- Output per worker grows by $4.0\%$.
- Capital per worker grows by $3.0\%$.
- Capital's share is $\alpha = 0.30$.

Use:

$$
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha\frac{\Delta k}{k}
$$

Step 1: Calculate the capital deepening contribution:

$$
\alpha\frac{\Delta k}{k}
=
0.30(3.0\%)
=
0.90\%
$$

Step 2: Solve for TFP growth:

$$
4.0\%
=
\frac{\Delta A}{A}
+
0.90\%
$$

$$
\frac{\Delta A}{A}
=
4.0\% - 0.90\%
$$

$$
\boxed{\frac{\Delta A}{A} = 3.10\%}
$$

Interpretation:

```text
Output per worker grew 4.0%.
Capital deepening explains 0.9 percentage points.
TFP explains 3.1 percentage points.
```

Most of the productivity gain came from better efficiency/technology, not just more capital per worker.

## Why Capital Deepening Has Diminishing Returns

Capital deepening raises labor productivity, but its effect gets weaker as capital per worker rises.

Why?

The first machine for a worker is transformative. The tenth machine is useful. The hundredth machine may sit idle because the worker cannot operate all of them at once.

In Cobb-Douglas, $\alpha < 1$, so:

$$
y = A k^\alpha
$$

is concave in $k$.

The [[Marginal product of capital]] is:

$$
MPK = \alpha \frac{Y}{K}
$$

As $K/L$ rises, the extra output from one more unit of capital tends to fall.

```text
More capital per worker
        ↓
Output per worker rises
        ↓
But each extra unit of capital adds less than the prior unit
        ↓
Capital deepening cannot sustain growth forever
```

## Why TFP Can Sustain Long-Run Growth

TFP is different because it does not merely add another tool to the same worker.

TFP makes the whole production system more effective.

```text
Better technology
Better organization
Better institutions
Better processes
Better know-how
        ↓
Same capital and labor produce more output
        ↓
Production function shifts upward
```

In the [[Solow Model (Neoclassical Growth Theory)]], pure capital deepening can raise the level of output per worker, but sustained long-run growth in output per worker requires TFP growth.

The steady-state per-worker growth rate is:

$$
g^* = \frac{\theta}{1-\alpha}
$$

Where:

| Symbol | Meaning |
|---|---|
| $\theta$ | TFP growth rate |
| $1-\alpha$ | Labor's share |

If:

$$
\theta = 0
$$

then:

$$
g^* = 0
$$

That means no sustained growth in output per worker in steady state.

## Developing vs Developed Economies

Capital deepening matters differently depending on how capital-rich an economy already is.

| Economy Type | Capital Per Worker | MPK | Capital Deepening Effect | TFP Role |
|---|---:|---:|---|---|
| Developing economy | Low | High | Large catch-up gains | Adoption of existing technology can be powerful |
| Developed economy | High | Low | Smaller gains | Innovation/TFP is essential |

Why developing economies can grow fast:

```text
Low K/L
        ↓
Capital is scarce
        ↓
MPK is high
        ↓
New investment is very productive
        ↓
Capital deepening creates rapid catch-up growth
```

Why developed economies depend more on TFP:

```text
High K/L
        ↓
Capital is abundant
        ↓
MPK is lower
        ↓
More capital adds less output
        ↓
Long-run gains require TFP growth
```

## ICT Investment: The Blurry Edge Case

CFA sometimes separates [[ICT vs Non-ICT Capital]] because information, computer, and telecommunications investment can do two things at once.

It can increase measured capital per worker:

```text
More computers, servers, software systems
        ↓
Higher K/L
        ↓
Capital deepening
```

But it can also change how the whole economy works:

```text
Better communication
Better data processing
Better coordination
Network effects
New business models
        ↓
Higher TFP
```

So ICT can be both:

```text
capital deepening + TFP improvement
```

Exam implication:

If the question says firms simply buy more equipment per worker, classify it as capital deepening. If the question says the same inputs produce more because of better technology, organization, or knowledge spillovers, classify it as TFP growth.

## Rule -> Mechanism -> Exam Implication

| Rule | Why | Mechanism | Exam Implication |
|---|---|---|---|
| Capital deepening raises labor productivity | Workers have more tools | $k = K/L$ rises in $y = Ak^\alpha$ | Use $\alpha \Delta k/k$ as contribution |
| TFP raises labor productivity | Inputs are used more efficiently | $A$ rises in $y = Ak^\alpha$ | TFP is the residual after K and L |
| Capital deepening has diminishing returns | Capital becomes less scarce | $MPK$ falls as $K/L$ rises | Cannot sustain per-capita growth forever in Solow |
| TFP can sustain growth | The whole production function improves | Production curve shifts upward | Long-run per-worker growth depends on TFP |

## Common CFA Traps

| Trap | Correct Thinking |
|---|---|
| Labor productivity and TFP are the same | Labor productivity is $Y/L$; TFP is $A$ |
| More output per worker always means TFP rose | Output per worker can rise from capital deepening alone |
| More machines always means TFP rose | More machines per worker is capital deepening unless output rises beyond measured input effects |
| Capital deepening permanently raises Solow growth | It raises the level of output per worker; long-run growth requires TFP |
| Total capital growth means capital deepening | Capital deepening requires $K$ to grow faster than $L$ |
| ICT is always just capital deepening | ICT can also raise TFP if it changes processes, networks, and organization |

## Memory Hooks

```text
Capital deepening = more tools per worker.
TFP = better recipe for using workers and tools.
```

```text
k moves you along the curve.
A shifts the curve up.
```

```text
Capital gives workers more.
TFP makes everything work better.
```

## Exam-Day Checklist

When a vignette describes a growth driver, ask:

1. Did capital per worker increase?
2. Did the same measured capital and labor produce more output?
3. Is the question about labor productivity growth or total GDP growth?
4. Are you being asked for the capital deepening contribution, $\alpha \Delta k/k$?
5. Are you being asked for TFP as the residual?
6. Is the economy below steady state, where capital deepening can create catch-up growth?
7. Is the economy near steady state, where TFP matters more for long-run per-worker growth?

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Growth Accounting]]
- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Steady-State Growth Rate]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Labor productivity]]
- [[Marginal product of capital]]
- [[Diminishing marginal productivity]]
- [[ICT vs Non-ICT Capital]]
