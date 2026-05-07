---
title: Capital Deepening
subject: Economics
tags: [CFA-L2, economics, economic-growth, capital-deepening, labor-productivity, solow-model]
aliases: [capital deepening, capital deepening investment, capital-to-labor ratio, capital per worker, K/L, k]
---

# Capital Deepening

## The Real-World Analogy

Imagine a construction crew.

If 10 workers share one crane, one bulldozer, and a few tools, each worker can only do so much.

Now give the same 10 workers more cranes, better tools, more vehicles, and better equipment. Each worker can produce more per hour because each worker has more capital to work with.

That is [[Level 2/Generated Notes/03 - Economics/Capital Deepening]].

```text
Same worker
  +
More tools per worker
  =
More output per worker
```

Capital deepening does not mean the economy merely has more machines in total. It means the economy has more machines, structures, and productive capital relative to its labor force.

## The One-Minute Version

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] is an increase in the capital-to-labor ratio:

$$
k = \frac{K}{L}
$$

Where:

| Symbol | Meaning |
|---|---|
| $K$ | [[Level 2/Generated Notes/03 - Economics/Capital Stock]] |
| $L$ | [[Labor]] |
| $k = K/L$ | Capital per worker |

Capital deepening happens when:

$$
\text{Growth in } K > \text{Growth in } L
$$

or:

$$
\Delta k > 0
$$

The intuition:

```text
Capital stock grows faster than labor
  |
  v
Each worker has more capital
  |
  v
Output per worker rises
  |
  v
Labor productivity rises
```

But the exam catch is:

> Capital deepening raises the level of output per worker, but because of diminishing marginal returns, it cannot by itself generate sustained long-run per-capita growth in the neoclassical/Solow model.

## The Exact Definition

The CFA glossary definition:

> Capital deepening is an increase in the capital-to-labor ratio.

That means:

$$
\frac{K}{L} \uparrow
$$

This is why "more capital" is not always enough.

If $K$ rises but $L$ rises just as fast, then $K/L$ does not rise.

If $K$ rises but $L$ rises faster, then $K/L$ falls.

Capital deepening is not about total capital alone. It is about capital per worker.

## Stock vs Ratio

Capital deepening depends on the ratio:

$$
k = \frac{K}{L}
$$

not just the level:

$$
K
$$

| Scenario | Capital Stock $K$ | Labor $L$ | Capital Per Worker $K/L$ | Capital Deepening? |
|---|---:|---:|---:|---|
| Capital grows faster than labor | Up 6% | Up 2% | Rises | Yes |
| Capital and labor grow equally | Up 4% | Up 4% | Same | No |
| Capital grows slower than labor | Up 2% | Up 5% | Falls | No, capital shallowing |

Why this matters:

Labor productivity depends on the amount of capital each worker has, not just the total amount of capital in the economy.

## Cobb-Douglas Per-Worker Form

Start with the [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Divide by $L$ to get output per worker:

$$
y = A k^\alpha
$$

Where:

| Symbol | Meaning |
|---|---|
| $y = Y/L$ | Output per worker / [[Labor productivity]] |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $k = K/L$ | Capital per worker |
| $\alpha$ | Capital's output elasticity |

This equation says labor productivity can rise in two ways:

```text
1. k rises -> capital deepening
2. A rises -> TFP / technological progress
```

Capital deepening is the $k$ route.

TFP growth is the $A$ route.

## Why Capital Deepening Raises Labor Productivity

Use:

$$
y = A k^\alpha
$$

If $A$ is constant and $k$ rises, then $y$ rises.

Why?

Because workers with more capital can produce more output.

```text
More capital per worker
  |
  v
Workers can operate more/better equipment
  |
  v
Each worker produces more output
  |
  v
Labor productivity rises
```

But the exponent $\alpha$ is less than 1, so the increase in $y$ is less than proportional to the increase in $k$.

If $\alpha = 0.30$, then a 1% increase in capital per worker raises output per worker by about 0.30%, holding TFP constant.

## Movement Along The Curve

Capital deepening is a movement along the per-worker production function.

```text
Output per worker y
  |
  |                         .
  |                    .
  |               .
  |          .
  |     .
  |  .
  +-------------------------------- Capital per worker k
     low k                    high k
```

When $k$ rises, the economy moves to the right along the curve.

Why the curve bends:

```text
At low k:
capital is scarce -> each extra unit of capital is very useful.

At high k:
capital is abundant -> each extra unit of capital adds less output.
```

That bend is [[Diminishing marginal productivity]].

## Contrast With TFP

The big CFA contrast:

| Feature | Capital Deepening | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] / Technological Progress |
|---|---|---|
| Variable | $k = K/L$ | $A$ |
| What changes? | More capital per worker | More output from the same capital and labor |
| Visual effect | Move along the production curve | Shift the whole curve upward |
| Growth effect | Raises labor productivity but with diminishing returns | Can sustain long-run growth |
| CFA phrase | Capital-to-labor ratio rises | Production function shifts upward |

Visual:

```text
Capital deepening:
Point A -> Point B along same curve

TFP growth:
Whole curve shifts upward
```

Why this distinction matters:

Capital deepening can make workers richer by giving them more tools. TFP makes every existing tool and worker more productive.

## Diminishing Marginal Product Of Capital

The [[Marginal product of capital]] is:

$$
MPK = \alpha \frac{Y}{K}
$$

It measures extra output from one more unit of capital.

As $K$ rises relative to labor, $MPK$ tends to fall.

Why?

```text
First machine:
huge improvement

Tenth machine:
still helpful

Hundredth machine:
maybe idle, duplicative, or bottlenecked by labor
```

This is why capital deepening has diminishing returns.

The why ladder:

```text
Rule:
Capital deepening eventually has smaller effects on labor productivity.

Why:
Each worker already has a lot of capital.

Mechanism:
The marginal product of capital declines as K/L rises.

Assumption:
Labor and TFP are not rising enough to make every new unit of capital equally productive.

Failure mode:
If the new capital embodies major technology improvements, then it may raise TFP too, not just deepen capital.

Exam implication:
Pure capital deepening cannot sustain long-run per-capita growth in the Solow model.
```

## MPK vs Marginal Cost

Firms keep adding capital as long as:

$$
MPK > r
$$

where $r$ is the rental price or cost of capital.

They stop deepening capital when:

$$
MPK = r
$$

Why?

Because if an extra machine produces more value than it costs, buying it is profitable. If it produces less value than it costs, buying it destroys value.

```text
MPK > r
  |
  v
Add capital
  |
  v
K/L rises
  |
  v
Capital deepening
```

```text
MPK = r
  |
  v
No extra profit from more capital
  |
  v
Capital deepening stops
```

## Solow Model: Why Deepening Stops

In the [[Solow Model (Neoclassical Growth Theory)]], capital per worker changes based on actual investment versus break-even investment.

Basic form:

$$
\Delta k = s y - (\delta+n)k
$$

Where:

| Term | Meaning |
|---|---|
| $s y$ | Actual investment per worker |
| $\delta k$ | Capital per worker lost to depreciation |
| $n k$ | Capital dilution from population growth |
| $(\delta+n)k$ | Break-even investment |

Capital deepening happens when:

$$
s y > (\delta+n)k
$$

Capital per worker is stable when:

$$
s y = (\delta+n)k
$$

That stable point is the steady state.

Why deepening stops:

```text
k rises
  |
  v
Output per worker rises
  |
  v
Investment per worker rises
  |
  v
But due to diminishing returns, output/investment rise more slowly
  |
  v
Break-even investment keeps rising with k
  |
  v
Eventually investment only maintains existing k
  |
  v
Steady state
```

At steady state, more capital deepening no longer drives sustained growth in output per worker.

## Worked Example 1: Is Capital Deepening Happening?

Suppose:

- Capital stock grows by 6%
- Labor grows by 2%

Approximate growth in capital per worker:

$$
\Delta k \approx \Delta K - \Delta L
$$

Substitute:

$$
\Delta k \approx 6\% - 2\% = 4\%
$$

Conclusion:

Capital per worker increased by about 4%, so capital deepening occurred.

## Worked Example 2: Capital Deepening Contribution

Suppose:

- Capital per worker growth: $\Delta k/k = 4\%$
- Capital's output elasticity: $\alpha = 0.30$
- TFP growth: $0\%$

Use:

$$
y = A k^\alpha
$$

In growth-rate form:

$$
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta k}{k}
$$

Substitute:

$$
\frac{\Delta y}{y}
=
0\%
+
0.30(4\%)
$$

Calculate:

$$
0.30 \times 4\% = 1.2\%
$$

Conclusion:

Output per worker rises by 1.2%.

Why not 4%?

Because $\alpha = 0.30$, so capital per worker has diminishing returns. A 1% increase in capital per worker only raises output per worker by 0.30%, holding TFP constant.

## Worked Example 3: TFP vs Capital Deepening

Suppose:

- Total GDP growth: $5.0\%$
- Labor growth: $1.0\%$
- Capital growth: $3.0\%$
- Capital share: $\alpha = 0.40$

Step 1: Compute output per worker growth.

$$
\Delta y \approx \Delta Y - \Delta L
$$

$$
\Delta y \approx 5.0\% - 1.0\% = 4.0\%
$$

Step 2: Compute capital per worker growth.

$$
\Delta k \approx \Delta K - \Delta L
$$

$$
\Delta k \approx 3.0\% - 1.0\% = 2.0\%
$$

Step 3: Compute capital deepening contribution.

$$
\alpha \Delta k = 0.40 \times 2.0\% = 0.80\%
$$

Step 4: Solve for TFP contribution.

$$
\Delta A/A = 4.0\% - 0.80\% = 3.20\%
$$

Conclusion:

Output per worker grew 4.0%. Capital deepening explains 0.80 percentage points. TFP explains 3.20 percentage points.

## Developed vs Developing Economies

Capital deepening has the biggest effect where capital is scarce.

| Economy Type | Capital Per Worker | MPK | Capital Deepening Effect |
|---|---:|---:|---|
| Developing economy | Low | High | Large effect on labor productivity |
| Developed economy | High | Low | Smaller effect; TFP matters more |

Why:

```text
Developing economy
  |
  v
Low K/L
  |
  v
Capital is scarce
  |
  v
MPK is high
  |
  v
Investment can raise productivity sharply
```

```text
Developed economy
  |
  v
High K/L
  |
  v
Capital is abundant
  |
  v
MPK is low
  |
  v
Additional capital adds little
```

## Foreign Investment

Foreign investment can create capital deepening in developing countries.

```text
Foreign direct investment enters
  |
  v
Capital stock rises
  |
  v
If K grows faster than L, K/L rises
  |
  v
Capital deepening
  |
  v
Labor productivity rises
```

This is especially powerful when the country starts with low capital per worker.

But if foreign investment brings new technology, processes, and know-how, it may also raise [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]. Then it is not just pure capital deepening; it is capital deepening plus technological progress.

## Decision Tree: Is This Capital Deepening?

```text
Step 1: Did capital stock increase?
  |
  +-- No
  |     |
  |     +-- Decision: no capital deepening.
  |     |
  |     +-- Why: K/L cannot rise from a falling or unchanged K unless labor falls even more, and the usual CFA case requires more capital per worker.
  |
  +-- Yes
        |
        +-- Decision: compare capital growth with labor growth.
        |
        +-- Why: capital deepening depends on capital per worker, not total capital alone.

Step 2: Did capital grow faster than labor?
  |
  +-- Yes
  |     |
  |     +-- Decision: capital deepening occurred.
  |     |
  |     +-- Why: K/L increased, so each worker has more capital.
  |
  +-- No
        |
        +-- Decision: no capital deepening.
        |
        +-- Why: if labor grows as fast as or faster than capital, the amount of capital per worker does not rise.
```

## Decision Tree: Will It Sustain Long-Run Growth?

```text
Step 1: Is the growth from pure capital deepening?
  |
  +-- Yes
  |     |
  |     +-- Decision: it can raise output per worker temporarily or raise the level of output.
  |     |
  |     +-- Why: more capital per worker raises labor productivity.
  |
  +-- No, it includes TFP growth
        |
        +-- Decision: sustained long-run growth is possible.
        |
        +-- Why: TFP shifts the production function upward and offsets diminishing returns.

Step 2: Is the economy already capital-rich?
  |
  +-- Yes
  |     |
  |     +-- Decision: expect smaller gains from capital deepening.
  |     |
  |     +-- Why: MPK is low when K/L is already high.
  |
  +-- No
        |
        +-- Decision: capital deepening can have a large effect.
        |
        +-- Why: MPK is high when capital is scarce.
```

## Common CFA Traps

### Trap 1: Thinking More Capital Always Means Capital Deepening

Wrong:

```text
K rose, so capital deepening occurred.
```

Correct:

```text
K/L must rise.
```

Capital must grow faster than labor.

### Trap 2: Confusing Capital Deepening With TFP

Capital deepening:

```text
More capital per worker -> move along the curve.
```

TFP:

```text
More output from same inputs -> shift the curve upward.
```

### Trap 3: Thinking Capital Deepening Permanently Raises Growth

In the Solow model, capital deepening can raise the level of output per worker, but it cannot permanently raise the growth rate of output per worker without TFP growth.

### Trap 4: Ignoring Population Growth

Population growth can dilute capital.

```text
K rises 4%
L rises 6%
K/L falls
```

That is capital shallowing, not capital deepening.

### Trap 5: Treating All Investment As Pure Deepening

Some investment only replaces depreciation. Some investment equips new workers. Only investment that raises $K/L$ is capital deepening.

Some investment also embodies new technology. That may raise TFP too.

## Minimum Memorization

Memorize:

$$
\boxed{k = \frac{K}{L}}
$$

$$
\boxed{\text{Capital deepening occurs when } K/L \text{ rises}}
$$

$$
\boxed{y = A k^\alpha}
$$

And the core intuition:

```text
Capital deepening = more tools per worker.

It moves the economy along the production function.

It raises labor productivity, but diminishing returns limit it.

Sustained long-run per-worker growth requires TFP.
```

## Can I Solve This?

1. Capital grows 8% and labor grows 3%. Is there capital deepening?

Answer: Yes. Capital grows faster than labor, so $K/L$ rises by about 5%.

2. Capital grows 4% and labor grows 4%. Is there capital deepening?

Answer: No. $K/L$ is unchanged.

3. Capital grows 3% and labor grows 5%. What happened?

Answer: Capital per worker fell. This is capital shallowing.

4. If $k$ rises 6% and $\alpha = 0.30$, with no TFP growth, how much does output per worker rise?

$$
\Delta y/y = 0.30 \times 6\% = 1.8\%
$$

5. Why does capital deepening have a bigger effect in developing economies?

Answer: Developing economies usually have low capital per worker, so capital is scarce and MPK is high. Each additional unit of capital adds more output.

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Labor productivity]]
- [[Production function]]
- [[CFA_Glossary/Economic growth]]
- [[Potential GDP]]
- [[Marginal product of capital]]
- [[Diminishing marginal productivity]]
- [[Physical capital]]
- [[Foreign direct investment]]
- [[Technological progress]]
- [[Steady State]]
