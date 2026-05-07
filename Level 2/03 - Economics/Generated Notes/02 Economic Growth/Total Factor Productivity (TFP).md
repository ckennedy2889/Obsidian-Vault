---
title: Total Factor Productivity (TFP)
subject: Economics
tags: [CFA-L2, economics, economic-growth, total-factor-productivity, growth-accounting, solow-model]
aliases: [TFP, Total factor productivity, total factor productivity, technological progress, technology growth, Solow residual]
---

# Total Factor Productivity (TFP)

## The Real-World Analogy

Think of an economy as a restaurant kitchen.

The kitchen has:

- cooks, which are [[Labor]];
- ovens, knives, refrigerators, and counters, which are [[Level 2/Generated Notes/03 - Economics/Capital Stock|capital]];
- recipes, workflow, management, timing, training, software, and organization, which are [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP]].

If the restaurant hires more cooks, output can rise.

If it buys more ovens, output can rise.

But if the restaurant redesigns the kitchen layout, improves the recipe, trains workers better, installs better ordering software, and reduces wasted motion, output can rise even with the same cooks and ovens.

That last part is TFP.

TFP is not more ingredients. It is a better recipe for using the ingredients.

```text
Labor = people doing work
Capital = tools used by people
TFP = how effectively people and tools are combined
```

## The One-Minute Version

[[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] is the efficiency with which an economy turns [[Labor]] and [[Level 2/Generated Notes/03 - Economics/Capital Stock|capital]] into output.

In the production function:

$$
Y = A F(K,L)
$$

or in [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function|Cobb-Douglas]] form:

$$
Y = A K^\alpha L^{1-\alpha}
$$

$A$ is TFP.

If $A$ rises, output rises even if capital and labor do not change.

That is why TFP is so powerful:

```text
More capital:
More tools for workers

More labor:
More workers using tools

More TFP:
Every worker and every tool becomes more productive
```

For CFA, the most important idea is:

> TFP growth shifts the production function upward and is the key driver of sustained long-run growth in output per worker.

## What TFP Means In The Production Function

Start with the general production function:

$$
Y = A F(K,L)
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Total output, usually real GDP |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $K$ | Capital input |
| $L$ | Labor input |
| $F(K,L)$ | The way capital and labor combine to produce output |

$A$ sits outside the function as a multiplier.

That means if $A$ increases by 10%, then output increases by 10% for the same $K$ and $L$.

Example:

Suppose:

$$
F(K,L) = 500
$$

and:

$$
A = 2
$$

Then:

$$
Y = 2 \times 500 = 1{,}000
$$

If $A$ rises to 2.2, with capital and labor unchanged:

$$
Y = 2.2 \times 500 = 1{,}100
$$

Output rises by:

$$
\frac{1{,}100 - 1{,}000}{1{,}000} = 10\%
$$

Why?

Because TFP is a scale factor. It scales up the productivity of the whole economy.

## TFP In Cobb-Douglas

The Cobb-Douglas production function is:

$$
Y = A K^\alpha L^{1-\alpha}
$$

In this formula, $A$ is TFP.

The meaning:

```text
K and L tell us how many inputs the economy has.
A tells us how effectively those inputs are used.
```

If two countries have the same $K$ and $L$ but different $A$, the country with higher $A$ produces more output.

That can happen because it has:

- better technology;
- better management;
- better logistics;
- better institutions;
- better legal systems;
- more efficient firms;
- better education and know-how;
- better infrastructure;
- less corruption or waste;
- better matching of workers to jobs;
- stronger knowledge spillovers.

The key is that TFP is broad. It is not just "robots" or "new machines." New machines are often capital. TFP is the economy-wide efficiency with which measured inputs become output.

## TFP vs Labor Productivity

This is a major CFA distinction.

[[Labor productivity]] is:

$$
y = \frac{Y}{L}
$$

It measures output per worker.

TFP is:

$$
A
$$

It measures the efficiency multiplier in the production function.

They are related but not the same.

| Concept | Formula | What It Measures | What Can Raise It |
|---|---|---|---|
| Labor productivity | $Y/L$ | Output per worker | More capital per worker or higher TFP |
| TFP | $A$ | Efficiency of all inputs together | Better technology, organization, institutions, methods |

A worker can become more productive for two different reasons:

```text
Reason 1: More capital per worker
  |
  v
Same worker has better tools
  |
  v
Labor productivity rises
  |
  v
But TFP may be unchanged
```

```text
Reason 2: Higher TFP
  |
  v
Same worker and same tools are used more effectively
  |
  v
Labor productivity rises
  |
  v
TFP has improved
```

So labor productivity tells you what happened to output per worker. TFP helps explain why it happened after accounting for capital and labor.

## Per-Worker Form

Start with Cobb-Douglas:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Divide by $L$:

$$
\frac{Y}{L} = A \left(\frac{K}{L}\right)^\alpha
$$

Define:

$$
y = \frac{Y}{L}
$$

and:

$$
k = \frac{K}{L}
$$

Then:

$$
\boxed{y = A k^\alpha}
$$

This says output per worker depends on:

1. capital per worker, $k$;
2. TFP, $A$.

The deep intuition:

```text
Capital deepening raises y by increasing k.
TFP raises y by increasing A.
```

That distinction is the whole game.

## Capital Deepening vs TFP Growth

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means giving each worker more capital:

$$
k = \frac{K}{L}
$$

TFP growth means making the same capital and labor more productive:

$$
A \uparrow
$$

| Feature | Capital Deepening | TFP Growth |
|---|---|---|
| What changes? | $K/L$ rises | $A$ rises |
| Visual effect | Movement along the production curve | Upward shift of the production curve |
| Why output per worker rises | Each worker has more capital | Each worker and each unit of capital is used more efficiently |
| Limitation | Diminishing marginal returns | Can sustain long-run growth |
| CFA phrase | More capital per worker | Technological progress / Solow residual |

ASCII visual:

```text
Capital deepening:

Output per worker
  |
  |           .
  |        .
  |     .
  |  .
  +---------------- Capital per worker
     A -> B along same curve

TFP growth:

Output per worker
  |
  |              new higher curve
  |           . . . . .
  |        .
  |     old curve
  +---------------- Capital per worker
     whole curve shifts upward
```

Why does this matter?

Capital deepening eventually loses power because of [[Diminishing marginal productivity|diminishing marginal productivity]]. TFP growth can keep raising output per worker because it makes the entire productive system better.

## Why TFP Shifts The Production Function Upward

Use the per-worker function:

$$
y = A k^\alpha
$$

Suppose $k$ is fixed.

If $A$ rises, then $y$ rises.

Example:

- $k = 100$
- $\alpha = 0.30$
- Initial $A = 1.0$
- New $A = 1.2$

Initial output per worker:

$$
y_0 = 1.0(100)^{0.30}
$$

$$
100^{0.30} \approx 3.981
$$

$$
y_0 \approx 3.981
$$

New output per worker:

$$
y_1 = 1.2(100)^{0.30}
$$

$$
y_1 = 1.2 \times 3.981
$$

$$
y_1 \approx 4.777
$$

Percentage increase:

$$
\frac{4.777 - 3.981}{3.981} \approx 20\%
$$

Output per worker rises by the same percentage as TFP.

Why?

Because $A$ multiplies the entire production function.

## Measuring TFP: The Solow Residual

TFP is not directly observed.

You can count workers.

You can estimate machines, structures, and capital stock.

You can measure GDP.

But you cannot directly count "efficiency" in the same clean way.

So economists estimate TFP using [[Growth accounting equation|growth accounting]].

Start with:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Convert to growth rates:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
$$

Solve for TFP growth:

$$
\boxed{
\frac{\Delta A}{A}
=
\frac{\Delta Y}{Y}
-
\alpha \frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
}
$$

This is the [[Solow residual]].

The word residual means leftover.

```text
Observed output growth
  |
  v
Subtract capital's weighted contribution
  |
  v
Subtract labor's weighted contribution
  |
  v
Leftover = TFP growth
```

So TFP is measured as:

```text
Growth we cannot explain with measured capital and measured labor.
```

## Worked Example 1: Calculate TFP Growth

Suppose:

- Real GDP growth: $4.0\%$
- Capital growth: $3.0\%$
- Labor growth: $1.0\%$
- Capital share: $\alpha = 0.30$
- Labor share: $1-\alpha = 0.70$

Use:

$$
\frac{\Delta A}{A}
=
\frac{\Delta Y}{Y}
-
\alpha \frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
$$

Step 1: Calculate capital's contribution.

$$
\alpha \frac{\Delta K}{K}
=
0.30 \times 3.0\%
=
0.9\%
$$

Step 2: Calculate labor's contribution.

$$
(1-\alpha)\frac{\Delta L}{L}
=
0.70 \times 1.0\%
=
0.7\%
$$

Step 3: Add measured input contributions.

$$
0.9\% + 0.7\% = 1.6\%
$$

Step 4: Subtract from observed GDP growth.

$$
\frac{\Delta A}{A}
=
4.0\% - 1.6\%
=
2.4\%
$$

Conclusion:

$$
\boxed{\text{TFP growth} = 2.4\%}
$$

Interpretation:

The economy grew 4.0%. Capital and labor explain 1.6 percentage points. The remaining 2.4 percentage points are attributed to TFP growth.

## Worked Example 2: Forecast Potential GDP Growth

Suppose an analyst expects:

- TFP growth: $1.5\%$
- Capital growth: $4.0\%$
- Labor growth: $1.2\%$
- Capital share: $\alpha = 0.35$
- Labor share: $1-\alpha = 0.65$

Use:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
$$

Substitute:

$$
\frac{\Delta Y}{Y}
=
1.5\%
+
0.35(4.0\%)
+
0.65(1.2\%)
$$

Capital contribution:

$$
0.35 \times 4.0\% = 1.4\%
$$

Labor contribution:

$$
0.65 \times 1.2\% = 0.78\%
$$

Potential GDP growth:

$$
1.5\% + 1.4\% + 0.78\% = 3.68\%
$$

Conclusion:

$$
\boxed{\text{Potential GDP growth} = 3.68\%}
$$

## What Is Hidden Inside The Residual?

TFP is useful, but it is not a perfectly clean measurement.

Because TFP is the leftover, it can include:

| Hidden Inside TFP | Why It Gets Captured There |
|---|---|
| True technological progress | New methods let the same inputs produce more output |
| Better management | Same workers and machines are organized more effectively |
| Better institutions | Less friction, better contracts, better property rights, lower corruption |
| Better infrastructure quality | Existing capital and labor become more productive |
| Worker skill quality | If labor is measured only by hours, quality improvements may show up as TFP |
| Capital quality | If capital is measured only by quantity, better capital may show up as TFP |
| Natural resources | Unmodeled inputs may be folded into TFP |
| Capacity utilization | Using existing capital harder can look like higher productivity |
| Measurement error | Bad data can end up in the residual |

This is why TFP is sometimes called a residual measure. It is powerful, but it requires humility.

The exam implication:

```text
TFP is not directly observed.
It is estimated as what remains after accounting for measured inputs.
```

## Why Only TFP Drives Sustained Long-Run Per-Capita Growth

In the [[Solow Model (Neoclassical Growth Theory)]], capital deepening cannot permanently raise the growth rate of output per worker by itself.

Why?

Because of diminishing marginal returns to capital.

```text
More capital per worker
  |
  v
Output per worker rises
  |
  v
But each new unit of capital adds less output
  |
  v
Eventually investment just covers depreciation and capital needs of new workers
  |
  v
Economy reaches steady state
```

At that point, simply saving more can raise the level of output per worker, but not its permanent growth rate.

TFP is different.

```text
TFP growth
  |
  v
Same capital and labor become more productive
  |
  v
Production function shifts upward
  |
  v
Output per worker can keep rising
```

Memory hook:

```text
Capital gives workers more tools.
TFP makes every tool and worker better.
```

## Developed vs Developing Economies

TFP also helps explain different growth patterns across economies.

| Economy Type | Typical Situation | Growth From Capital Deepening | Growth From TFP |
|---|---|---|---|
| Developing economy | Low capital per worker | Often powerful because capital is scarce | Can come from adopting existing foreign technology |
| Developed economy | High capital per worker | Weaker because marginal product of capital is lower | Essential because innovation is needed to keep living standards rising |

The why:

```text
Developing country
  |
  v
Low K/L
  |
  v
High marginal product of capital
  |
  v
Capital deepening can produce rapid catch-up growth
```

```text
Developed country
  |
  v
High K/L
  |
  v
Low marginal product of additional capital
  |
  v
Needs TFP growth for sustained gains
```

## Decision Tree: Is It TFP?

Use this when an exam question describes a growth driver.

```text
Step 1: Did the economy simply add more workers?
  |
  +-- Yes
  |     |
  |     +-- Decision: classify as labor input growth, not TFP.
  |     |
  |     +-- Why: more workers increase L, while TFP means better output from the same measured inputs.
  |
  +-- No
        |
        +-- Decision: move to the capital/efficiency question.
        |
        +-- Why: if L did not rise, growth may come from K, A, or measurement effects.

Step 2: Did the economy simply give workers more capital?
  |
  +-- Yes
  |     |
  |     +-- Decision: classify as capital deepening.
  |     |
  |     +-- Why: more capital per worker raises k = K/L and moves the economy along the production curve.
  |
  +-- No
        |
        +-- Decision: look for a productivity/technology improvement.
        |
        +-- Why: if output rises without more K or L, the explanation is likely higher A.

Step 3: Did the same measured capital and labor produce more output?
  |
  +-- Yes
  |     |
  |     +-- Decision: classify as TFP growth.
  |     |
  |     +-- Why: higher A means more output from the same measured inputs.
  |
  +-- No
        |
        +-- Decision: no evidence of TFP growth from the information given.
        |
        +-- Why: TFP is inferred from unexplained output growth after accounting for K and L.
```

## Decision Tree: Growth Accounting

Use this when the question gives GDP, capital, labor, and factor shares.

```text
Step 1: Do you need GDP growth or TFP growth?
  |
  +-- GDP growth
  |     |
  |     +-- Decision: add TFP growth plus weighted input growth.
  |     |
  |     +-- Why: output growth equals TFP growth plus capital and labor contributions.
  |
  +-- TFP growth
        |
        +-- Decision: subtract weighted input growth from GDP growth.
        |
        +-- Why: TFP is the residual left after measured input growth is removed.

Step 2: Did the question give labor's share instead of capital's share?
  |
  +-- Yes
  |     |
  |     +-- Decision: calculate alpha = 1 - labor share.
  |     |
  |     +-- Why: alpha is capital's share and 1-alpha is labor's share.
  |
  +-- No
        |
        +-- Decision: use the given capital share as alpha.
        |
        +-- Why: the capital growth contribution is alpha times capital growth.

Step 3: Are inputs measured in growth rates?
  |
  +-- Yes
  |     |
  |     +-- Decision: apply the growth accounting formula directly.
  |     |
  |     +-- Why: the formula decomposes growth rates, not levels.
  |
  +-- No
        |
        +-- Decision: convert levels into growth rates first.
        |
        +-- Why: mixing levels and growth rates gives meaningless results.
```

## Common CFA Traps

### Trap 1: TFP Is Not Labor Productivity

Labor productivity is output per worker:

$$
\frac{Y}{L}
$$

TFP is the efficiency multiplier:

$$
A
$$

Labor productivity can rise because workers have more capital, even if TFP is unchanged.

### Trap 2: TFP Is Not Directly Measured

TFP is estimated as a residual:

$$
\frac{\Delta A}{A}
=
\frac{\Delta Y}{Y}
-
\alpha \frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
$$

If the exam asks what TFP growth represents, say it is output growth not explained by measured capital and labor growth.

### Trap 3: Capital Deepening Is Not The Same As TFP

Capital deepening:

```text
More K per worker -> move along the curve
```

TFP growth:

```text
Higher A -> shift the curve upward
```

### Trap 4: Higher Saving Does Not Permanently Raise Growth In Solow

A higher saving rate can raise the level of output per worker by increasing capital per worker.

But in the neoclassical model, it does not permanently raise the long-run growth rate of output per worker.

Only TFP growth does that.

### Trap 5: TFP Can Hide Measurement Problems

Because TFP is a residual, a positive TFP estimate does not always mean pure technological progress. It may reflect omitted variables or measurement error.

## Minimum Memorization

Memorize:

$$
\boxed{Y = A K^\alpha L^{1-\alpha}}
$$

$$
\boxed{y = A k^\alpha}
$$

$$
\boxed{
\frac{\Delta A}{A}
=
\frac{\Delta Y}{Y}
-
\alpha \frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
}
$$

And memorize the intuition:

```text
TFP = more output from the same measured inputs.

Capital deepening moves along the production curve.
TFP growth shifts the production curve upward.

TFP is the Solow residual:
what is left after accounting for capital and labor.
```

## Can I Solve This?

1. If GDP grows 5%, capital grows 4%, labor grows 2%, and $\alpha = 0.25$, what is TFP growth?

Capital contribution:

$$
0.25 \times 4\% = 1.0\%
$$

Labor contribution:

$$
0.75 \times 2\% = 1.5\%
$$

TFP growth:

$$
5.0\% - 1.0\% - 1.5\% = 2.5\%
$$

2. If output per worker rises because each worker gets more machines, is that TFP?

Answer: Not necessarily. That is capital deepening. TFP rises only if output increases beyond what the additional capital and labor explain.

3. If the same workers and same capital produce more output after a management/process improvement, is that TFP?

Answer: Yes. Same measured inputs, more output, so the improvement is captured as higher TFP.

4. Why does CFA say TFP is central to long-run growth?

Answer: Capital deepening faces diminishing marginal returns. TFP shifts the production function upward and allows sustained increases in output per worker.

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Growth accounting equation]]
- [[Solow residual]]
- [[Labor productivity]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Technological progress]]
- [[Production function]]
- [[CFA_Glossary/Economic growth]]
- [[Potential GDP]]
- [[Diminishing marginal productivity]]
- [[Human capital]]
- [[Physical capital]]
- [[Conditional convergence]]
