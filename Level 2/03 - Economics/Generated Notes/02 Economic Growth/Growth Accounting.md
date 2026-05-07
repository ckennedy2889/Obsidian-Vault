---
title: Growth Accounting
subject: Economics
tags: [CFA-L2, economics, economic-growth, growth-accounting, potential-gdp, solow-residual]
aliases: [growth accounting, growth accounting equation, Solow residual, sources of growth, potential GDP growth accounting]
---

# Growth Accounting

## The Real-World Analogy

Think of an economy as a factory that produced more this year than last year.

You want to know why output grew.

There are only a few broad possibilities:

```text
The factory had more workers.
The factory had more machines.
The factory used workers and machines better.
```

Growth accounting is the method for splitting GDP growth into those buckets.

It asks:

```text
How much growth came from labor?
How much came from capital?
How much came from productivity/technology?
```

That last leftover piece is [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]], also called the [[Solow residual]].

## The One-Minute Version

[[Growth Accounting]] is the [[Production function]] written in growth-rate form.

Starting from [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function|Cobb-Douglas]]:

$$
Y = A K^\alpha L^{1-\alpha}
$$

the growth accounting equation is:

$$
\boxed{
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
}
$$

Plain English:

```text
GDP growth
=
TFP growth
+
capital's weighted contribution
+
labor's weighted contribution
```

The equation is used to:

- explain past growth;
- estimate [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP growth]] as a residual;
- forecast [[Potential GDP]] growth;
- compare whether growth is coming from labor, capital, or productivity.

## Why Growth Accounting Exists

GDP growth alone is not enough.

Suppose Country A and Country B both grow 4%.

Country A grew because it added many workers.

Country B grew because it became more productive with the same workers and capital.

Those are very different stories.

Growth accounting separates the stories:

| Growth Source | What It Means | Sustainability Question |
|---|---|---|
| Labor growth | More workers or hours | Can the labor force keep growing? |
| Capital growth | More machines, buildings, equipment | Is capital deepening running into diminishing returns? |
| TFP growth | More output from the same measured inputs | Is technology/efficiency improving? |

For investors, this matters because [[Potential GDP]] growth affects long-run earnings, real interest rates, sovereign credit quality, and sustainable asset returns.

## Deriving The Equation

Start with:

$$
Y = A K^\alpha L^{1-\alpha}
$$

The growth-rate version of a product is approximately the sum of the growth rates of each part.

Because $K$ is raised to $\alpha$, capital growth is weighted by $\alpha$.

Because $L$ is raised to $1-\alpha$, labor growth is weighted by $1-\alpha$.

So:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
$$

Why the weights matter:

If $\alpha = 0.30$, a 1% increase in capital does not increase output by 1%. It increases output by about 0.30%, holding labor and TFP constant.

If $1-\alpha = 0.70$, a 1% increase in labor increases output by about 0.70%, holding capital and TFP constant.

## What Each Term Means

| Term | Name | Meaning |
|---|---|---|
| $\Delta Y/Y$ | Output growth | Growth in real GDP or potential GDP |
| $\Delta A/A$ | TFP growth | Growth from technology, efficiency, organization, and other unexplained productivity gains |
| $\alpha \Delta K/K$ | Capital contribution | Capital growth weighted by capital's output elasticity/income share |
| $(1-\alpha)\Delta L/L$ | Labor contribution | Labor growth weighted by labor's output elasticity/income share |

The compact memory version:

```text
Y growth = A growth + alpha K growth + labor-share L growth
```

## Why Alpha And One Minus Alpha Are The Weights

In Cobb-Douglas:

$$
Y = A K^\alpha L^{1-\alpha}
$$

$\alpha$ is capital's output elasticity.

That means:

```text
If capital rises 1%, output rises alpha%, holding A and L constant.
```

$1-\alpha$ is labor's output elasticity.

That means:

```text
If labor rises 1%, output rises (1-alpha)%, holding A and K constant.
```

Under competitive factor markets, these also correspond to factor income shares:

| Parameter | Output Elasticity | Income Share |
|---|---|---|
| $\alpha$ | Capital elasticity | Capital's share of national income |
| $1-\alpha$ | Labor elasticity | Labor's share of national income |

Exam shortcut:

If the question gives labor's share, compute:

$$
\alpha = 1 - \text{labor share}
$$

If labor's share is 65%, then capital's share is:

$$
\alpha = 1 - 0.65 = 0.35
$$

## TFP As The Solow Residual

TFP is not directly observed.

We can estimate:

- GDP growth;
- capital growth;
- labor growth;
- factor shares.

But we cannot directly count "technology" or "efficiency" in a clean way.

So growth accounting solves for TFP as the leftover:

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

Why residual?

```text
Observed GDP growth
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

What can be hidden in TFP:

- true technological progress;
- better management;
- better institutions;
- improved worker quality not captured in labor quantity;
- improved capital quality not captured in capital quantity;
- natural resources or omitted inputs;
- capacity utilization changes;
- measurement error.

## Forecasting Potential GDP

CFA uses growth accounting to forecast [[Potential GDP]] growth.

Potential GDP is the economy's sustainable output level: the output it can produce without creating inflation pressure.

To forecast potential GDP growth, use trend estimates:

$$
g_{Y^*}
=
g_A
+
\alpha g_K
+
(1-\alpha)g_L
$$

Where:

| Term | Forecasting Input |
|---|---|
| $g_A$ | Expected trend TFP growth |
| $g_K$ | Expected trend capital stock growth |
| $g_L$ | Expected trend labor input growth |
| $\alpha$ | Capital share |
| $1-\alpha$ | Labor share |

Why trend estimates?

Because potential GDP is a long-run sustainable concept. Short-run actual GDP can be above or below potential due to the business cycle.

## Worked Example 1: Forecast Potential GDP

Suppose:

- Expected TFP growth: $2.0\%$
- Capital growth: $3.0\%$
- Labor growth: $1.5\%$
- Labor share: $60\%$

Step 1: Compute capital share.

$$
\alpha = 1 - 0.60 = 0.40
$$

Step 2: Use the growth accounting equation.

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
2.0\%
+
0.40(3.0\%)
+
0.60(1.5\%)
$$

Capital contribution:

$$
0.40 \times 3.0\% = 1.2\%
$$

Labor contribution:

$$
0.60 \times 1.5\% = 0.9\%
$$

Potential GDP growth:

$$
2.0\% + 1.2\% + 0.9\% = 4.1\%
$$

Conclusion:

$$
\boxed{\text{Potential GDP growth} = 4.1\%}
$$

## Worked Example 2: Solve For TFP

Suppose:

- Real GDP growth: $4.5\%$
- Capital growth: $5.0\%$
- Labor growth: $1.0\%$
- Capital share: $\alpha = 0.35$

Step 1: Capital contribution.

$$
0.35 \times 5.0\% = 1.75\%
$$

Step 2: Labor share.

$$
1-\alpha = 1 - 0.35 = 0.65
$$

Step 3: Labor contribution.

$$
0.65 \times 1.0\% = 0.65\%
$$

Step 4: Total explained by inputs.

$$
1.75\% + 0.65\% = 2.40\%
$$

Step 5: TFP residual.

$$
\frac{\Delta A}{A}
=
4.5\% - 2.40\%
=
2.10\%
$$

Conclusion:

$$
\boxed{\text{TFP growth} = 2.10\%}
$$

## Labor Productivity Version

Sometimes CFA focuses on output per worker:

$$
y = \frac{Y}{L}
$$

and capital per worker:

$$
k = \frac{K}{L}
$$

From:

$$
y = A k^\alpha
$$

the labor productivity growth equation is:

$$
\boxed{
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta k}{k}
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

This version is useful when the question is about standard of living or GDP per worker rather than total GDP.

## Worked Example 3: Labor Productivity Growth

Suppose:

- TFP growth: $1.2\%$
- Capital per worker growth: $4.0\%$
- Capital share: $\alpha = 0.30$

Use:

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
1.2\%
+
0.30(4.0\%)
$$

Capital deepening contribution:

$$
0.30 \times 4.0\% = 1.2\%
$$

Labor productivity growth:

$$
1.2\% + 1.2\% = 2.4\%
$$

Conclusion:

$$
\boxed{\text{Labor productivity growth} = 2.4\%}
$$

## Capital Deepening And Growth Accounting

Capital deepening appears most clearly in the labor productivity version:

$$
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta k}{k}
$$

Where:

$$
k = \frac{K}{L}
$$

If capital per worker rises, then $\Delta k/k$ is positive.

But the contribution to productivity growth is weighted by $\alpha$ because capital has diminishing marginal returns.

```text
Capital deepening
  |
  v
k rises
  |
  v
Labor productivity rises
  |
  v
But only by alpha times k growth, holding TFP constant
```

## Decision Tree: Which Formula Do I Use?

```text
Step 1: Is the question asking about total GDP or potential GDP?
  |
  +-- Yes
  |     |
  |     +-- Decision: use total growth accounting.
  |     |
  |     +-- Why: total GDP growth depends on TFP growth, capital growth, and labor growth.
  |
  +-- No, it asks about output per worker or labor productivity
        |
        +-- Decision: use the labor productivity equation.
        |
        +-- Why: output per worker removes total labor size and focuses on TFP plus capital per worker.

Step 2: Are you solving for TFP?
  |
  +-- Yes
  |     |
  |     +-- Decision: subtract weighted capital and labor growth from GDP growth.
  |     |
  |     +-- Why: TFP is the residual after measured input growth is removed.
  |
  +-- No, forecasting GDP growth
        |
        +-- Decision: add TFP growth plus weighted input growth.
        |
        +-- Why: growth accounting decomposes total growth into additive contributions.
```

## Decision Tree: What Is Driving Growth?

```text
Step 1: Is labor contribution the largest?
  |
  +-- Yes
  |     |
  |     +-- Decision: growth depends heavily on labor-force or hours growth.
  |     |
  |     +-- Why: the weighted labor term explains the largest share of GDP growth.
  |
  +-- No
        |
        +-- Decision: compare capital and TFP contributions.
        |
        +-- Why: growth may be coming from investment or productivity instead.

Step 2: Is capital contribution large?
  |
  +-- Yes
  |     |
  |     +-- Decision: capital accumulation/deepening is important.
  |     |
  |     +-- Why: capital stock growth, weighted by alpha, explains a meaningful part of growth.
  |
  +-- No
        |
        +-- Decision: capital is not the main driver.
        |
        +-- Why: either K is growing slowly or alpha is small.

Step 3: Is TFP contribution large?
  |
  +-- Yes
  |     |
  |     +-- Decision: productivity/technology is the main growth source.
  |     |
  |     +-- Why: output grew more than measured capital and labor can explain.
  |
  +-- No
        |
        +-- Decision: growth is mostly input-driven.
        |
        +-- Why: measured labor and capital explain most of the growth.
```

## Common CFA Traps

### Trap 1: Forgetting To Weight Inputs

Wrong:

```text
GDP growth = TFP growth + K growth + L growth
```

Correct:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
$$

Capital and labor growth must be weighted by their output elasticities/income shares.

### Trap 2: Confusing Capital Share With Labor Share

If labor's share is 70%, then:

$$
1-\alpha = 0.70
$$

so:

$$
\alpha = 0.30
$$

Do not multiply capital growth by labor's share.

### Trap 3: Treating TFP As Directly Observed

TFP is usually estimated as a residual:

```text
TFP = observed growth - measured input contributions
```

### Trap 4: Mixing Total GDP Growth With Per-Worker Growth

Total GDP growth:

$$
\frac{\Delta Y}{Y}
$$

Labor productivity growth:

$$
\frac{\Delta y}{y}
$$

The second removes labor quantity and focuses on output per worker.

### Trap 5: Forgetting Potential GDP Uses Trend Inputs

Potential GDP is long-run sustainable output. Use trend estimates of labor, capital, and TFP, not one-year cyclical noise.

## Minimum Memorization

Memorize:

$$
\boxed{
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta K}{K}
+
(1-\alpha)\frac{\Delta L}{L}
}
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

$$
\boxed{
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+
\alpha \frac{\Delta k}{k}
}
$$

And the intuition:

```text
Growth accounting is GDP growth split into:
1. TFP growth
2. capital contribution
3. labor contribution

TFP is the leftover after measured inputs are counted.
```

## Can I Solve This?

1. GDP grows 6%, capital grows 4%, labor grows 2%, and $\alpha = 0.25$. What is TFP growth?

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
6.0\% - 1.0\% - 1.5\% = 3.5\%
$$

2. Labor's share is 65%, capital grows 3%, labor grows 1%, and TFP grows 2%. What is potential GDP growth?

Capital share:

$$
\alpha = 1 - 0.65 = 0.35
$$

Potential GDP growth:

$$
2.0\% + 0.35(3.0\%) + 0.65(1.0\%)
$$

$$
2.0\% + 1.05\% + 0.65\% = 3.70\%
$$

3. TFP growth is 1%, capital per worker grows 5%, and $\alpha = 0.30$. What is labor productivity growth?

$$
\frac{\Delta y}{y}
=
1.0\% + 0.30(5.0\%)
=
1.0\% + 1.5\%
=
2.5\%
$$

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Solow residual]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Labor productivity]]
- [[Potential GDP]]
- [[CFA_Glossary/Economic growth]]
- [[Production function]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Labor productivity growth accounting equation]]
- [[Diminishing marginal productivity]]
