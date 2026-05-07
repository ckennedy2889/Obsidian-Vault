---
title: Cobb-Douglas Production Function
subject: Economics
tags: [CFA-L2, economics, economic-growth, production-function, growth-accounting, total-factor-productivity]
aliases: [Cobb-Douglas, Cobb Douglas, Cobb-Douglas function, Cobb-Douglas production function, Cobb–Douglas production function, Cobb-Douglas model]
---

## The Real-World Analogy

Imagine an economy as a bakery.

The bakery produces bread. Its output depends on:

- the ovens, mixers, counters, and delivery trucks it owns;
- the workers who operate them;
- the recipe, workflow, management quality, and technology that make the whole operation efficient.

If the bakery buys more ovens but hires no more workers, production rises, but not forever at the same pace. At some point, workers are waiting on each other, ovens sit partly unused, floor space gets crowded, and each additional oven adds less output than the previous oven.

If the bakery hires more workers but buys no more ovens, production also rises at first, but eventually workers crowd around the same machines and each extra worker adds less.

But if the bakery improves the recipe, redesigns the production line, trains workers better, or adopts better technology, every oven and every worker becomes more productive.

That is the spirit of the [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]:

```text
Output comes from:

Capital
  +
Labor
  +
Efficiency/technology that makes capital and labor productive
```

The model is trying to answer:

```text
How much output can an economy produce from its capital, labor, and technology?
```

## The Big Formula

The CFA version of the [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]] is:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Where:

| Symbol | Meaning | Plain-English Version |
|---|---|---|
| $Y$ | [[Aggregate output]], usually real GDP | Total goods and services produced |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] | The economy's efficiency, technology, organization, and know-how |
| $K$ | [[Level 2/Generated Notes/03 - Economics/Capital Stock]] | Machines, buildings, equipment, infrastructure, software, productive assets |
| $L$ | [[Labor]] | Workers or hours worked |
| $\alpha$ | Capital's output elasticity and income share | How much output responds to capital; often around 0.3 |
| $1-\alpha$ | Labor's output elasticity and income share | How much output responds to labor; often around 0.7 |

The model says output is not just:

```text
capital + labor
```

It is:

```text
technology/efficiency × capital contribution × labor contribution
```

That matters because two countries can have similar amounts of workers and machines but very different output if one country has better institutions, technology, education, supply chains, legal systems, management methods, infrastructure quality, or production organization. Those differences are captured mostly in $A$, [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]].

## Why The Formula Is Multiplicative

The function is multiplicative:

$$
Y = A K^\alpha L^{1-\alpha}
$$

not additive:

$$
Y \ne A + K + L
$$

Why?

Because capital and labor are complements. A machine without a worker produces little. A worker without tools produces little. Technology without inputs has nothing to improve.

Multiplication captures the idea that each input makes the other input more useful.

```text
More capital makes labor more productive.
More labor makes capital more useful.
Better technology makes both capital and labor more productive.
```

If $A$ rises, output rises proportionately for any combination of $K$ and $L$. That is why $A$ is called a scale factor.

## What $A$ Really Means

$A$ is [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]. It is the part of output not directly explained by measured capital and labor.

In plain English, $A$ asks:

```text
Given the same machines and workers, how good is this economy at turning inputs into output?
```

$A$ includes things like:

- technology;
- management techniques;
- scientific knowledge;
- worker organization;
- legal and institutional quality;
- logistics and supply-chain efficiency;
- production know-how;
- quality of infrastructure;
- anything that makes measured inputs more productive.

The CFA source makes an important distinction:

| Concept | What It Means |
|---|---|
| Production function shape $F(K,L)$ | How capital and labor combine with each other |
| TFP scale factor $A$ | A broad productivity multiplier that raises output for any input combination |

Most of the time in CFA Economics, when you see "technology," interpret it as TFP unless the question says otherwise.

Why is TFP so important?

Because capital deepening eventually runs into diminishing returns. TFP can shift the whole production function upward.

```text
Capital deepening:
Move along the curve

TFP growth:
Shift the whole curve upward
```

## Why The Exponents Matter

The exponents are the most important part of the formula:

$$
Y = A K^\alpha L^{1-\alpha}
$$

They do three jobs at once.

| Exponent | Job 1: Output Elasticity | Job 2: Income Share | Job 3: Growth Weight |
|---|---|---|---|
| $\alpha$ | % change in output from 1% more capital | Capital's share of income | Weight on capital growth |
| $1-\alpha$ | % change in output from 1% more labor | Labor's share of income | Weight on labor growth |

If $\alpha = 0.30$, then a 1% increase in capital, holding labor and TFP constant, increases output by about 0.30%.

If $1-\alpha = 0.70$, then a 1% increase in labor, holding capital and TFP constant, increases output by about 0.70%.

That is why labor growth often has a larger direct weight in GDP growth than capital growth when labor's share is larger than capital's share.

## Why $\alpha$ Is Capital's Share of Income

This is one of the deepest parts of the model, and it is worth slowing down.

Start with the production function:

$$
Y = A K^\alpha L^{1-\alpha}
$$

The [[Marginal product|marginal product]] of capital is the extra output produced by adding a little more capital while holding labor and technology constant.

Take the derivative with respect to $K$:

$$
MPK = \frac{\partial Y}{\partial K}
$$

Since:

$$
Y = A K^\alpha L^{1-\alpha}
$$

the derivative is:

$$
MPK = \alpha A K^{\alpha-1} L^{1-\alpha}
$$

Now notice that:

$$
Y = A K^\alpha L^{1-\alpha}
$$

If we divide $Y$ by $K$:

$$
\frac{Y}{K} = \frac{A K^\alpha L^{1-\alpha}}{K}
$$

Because dividing by $K$ is the same as subtracting 1 from the exponent on $K$:

$$
\frac{Y}{K} = A K^{\alpha-1} L^{1-\alpha}
$$

So:

$$
MPK = \alpha \frac{Y}{K}
$$

That is the key marginal-product formula:

$$
\boxed{MPK = \alpha \frac{Y}{K}}
$$

In a competitive economy, firms hire capital until:

$$
MPK = r
$$

where $r$ is the [[Level 2/Generated Notes/03 - Economics/Rental Price of Capital|rental price of capital]] or real return required by capital providers.

So:

$$
\alpha \frac{Y}{K} = r
$$

Multiply both sides by $K$:

$$
\alpha Y = rK
$$

Now divide both sides by $Y$:

$$
\alpha = \frac{rK}{Y}
$$

What is $rK$?

It is the total income paid to capital:

```text
return per unit of capital × amount of capital = capital income
```

So:

$$
\alpha = \frac{\text{capital income}}{\text{total output/income}}
$$

That means:

$$
\boxed{\alpha = \text{capital's share of national income}}
$$

and:

$$
\boxed{1-\alpha = \text{labor's share of national income}}
$$

The why ladder:

```text
Rule:
Alpha is capital's share of income.

Why:
In competitive markets, factors are paid their marginal products.

Mechanism:
MPK = alpha Y/K, and profit maximization sets MPK = r.

Algebra:
alpha Y/K = r -> alpha = rK/Y.

Meaning:
rK is capital income, Y is total income, so alpha is capital's income share.

Exam implication:
If labor receives 70% of national income, then alpha = 30%, and capital growth gets a 0.30 weight in growth accounting.
```

## Constant Returns To Scale

Cobb-Douglas has [[Constant returns to scale|constant returns to scale]] when the exponents sum to 1.

Here they do:

$$
\alpha + (1-\alpha) = 1
$$

Constant returns to scale means:

```text
If all inputs rise by x%, output rises by x%.
```

Example:

If capital doubles and labor doubles, output doubles.

Proof:

Start with:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Now double both inputs:

$$
Y_{new} = A(2K)^\alpha(2L)^{1-\alpha}
$$

Break apart the powers:

$$
Y_{new} = A \cdot 2^\alpha K^\alpha \cdot 2^{1-\alpha}L^{1-\alpha}
$$

Combine the powers of 2:

$$
Y_{new} = A \cdot 2^{\alpha + 1-\alpha} K^\alpha L^{1-\alpha}
$$

Since $\alpha + 1-\alpha = 1$:

$$
Y_{new} = 2 \cdot A K^\alpha L^{1-\alpha}
$$

Therefore:

$$
Y_{new} = 2Y
$$

That is constant returns to scale.

## Diminishing Marginal Productivity

Cobb-Douglas also has [[Diminishing marginal productivity|diminishing marginal productivity]] for each individual input when the other input is held constant.

This sounds contradictory at first:

```text
Constant returns to scale:
Double capital and labor together -> double output.

Diminishing marginal productivity:
Increase only capital while labor is fixed -> each extra unit of capital adds less output.
```

Both can be true because they are asking different questions.

| Concept | What Changes? | What Is Held Fixed? | Result |
|---|---|---|---|
| Constant returns to scale | All inputs rise together | Input proportions stay the same | Output rises proportionately |
| Diminishing marginal productivity | One input rises | The other input is fixed | Extra output from the rising input declines |

Why does diminishing marginal productivity happen?

Because an input becomes less useful when its complementary input does not also rise.

Example:

```text
More machines with same workers:
At first, workers become much more productive.
Eventually, extra machines sit idle or duplicate capacity.

More workers with same machines:
At first, machines are used more fully.
Eventually, workers crowd around the same capital.
```

For capital:

$$
MPK = \alpha A K^{\alpha-1} L^{1-\alpha}
$$

Since $\alpha$ is between 0 and 1, $\alpha - 1$ is negative.

So:

$$
K^{\alpha-1} = K^{-(1-\alpha)}
$$

As $K$ rises, $K^{\alpha-1}$ falls.

That is the math behind diminishing marginal productivity of capital:

```text
More K
  |
  v
K has a negative exponent inside MPK
  |
  v
MPK falls
  |
  v
Each extra unit of capital adds less output
```

## The Role Of Alpha In Diminishing Returns

The value of $\alpha$ controls how quickly diminishing returns to capital appear.

| Alpha Value | Meaning | Diminishing Returns To Capital |
|---|---|---|
| $\alpha$ close to 0 | Capital has a small output weight | Extra capital adds much less output quickly |
| $\alpha$ around 0.3 | Typical capital share | Capital deepening helps, but with clear diminishing returns |
| $\alpha$ close to 1 | Capital has a large output weight | Diminishing returns exist but are weaker |

Why?

Because the marginal product of capital is:

$$
MPK = \alpha A K^{\alpha-1} L^{1-\alpha}
$$

If $\alpha$ is low, then $\alpha - 1$ is very negative. MPK falls quickly as $K$ rises.

If $\alpha$ is high, then $\alpha - 1$ is closer to zero. MPK still falls, but more slowly.

## Per-Worker Form

CFA uses the per-worker form because it connects directly to [[Labor productivity]] and living standards.

Start with:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Divide both sides by $L$:

$$
\frac{Y}{L} = \frac{A K^\alpha L^{1-\alpha}}{L}
$$

Since:

$$
L^{1-\alpha} / L = L^{1-\alpha-1} = L^{-\alpha}
$$

we get:

$$
\frac{Y}{L} = A K^\alpha L^{-\alpha}
$$

Rewrite:

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

So:

$$
\boxed{y = A k^\alpha}
$$

This is the per-worker Cobb-Douglas function.

| Symbol | Meaning |
|---|---|
| $y$ | Output per worker, or [[Labor productivity]] |
| $k$ | Capital per worker, or capital-to-labor ratio |
| $A$ | Total factor productivity |
| $\alpha$ | Capital's output elasticity/income share |

The meaning:

```text
Labor productivity depends on:

1. How much capital each worker has
2. How productive/technologically advanced the economy is
```

## Capital Deepening vs Technological Progress

The per-worker form is:

$$
y = A k^\alpha
$$

There are only two ways to raise output per worker:

```text
Raise k:
Give each worker more capital.

Raise A:
Make each worker and each unit of capital more productive.
```

### Capital Deepening

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means an increase in capital per worker:

$$
k = \frac{K}{L}
$$

If $K$ rises faster than $L$, then $k$ rises.

That raises output per worker:

$$
y = A k^\alpha
$$

But because $\alpha < 1$, the gains shrink as $k$ gets larger.

```text
Capital deepening
  |
  v
More capital per worker
  |
  v
Move along the production curve
  |
  v
Output per worker rises
  |
  v
But at a decreasing rate
```

### Technological Progress

[[Technological progress]] means an increase in $A$, [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]].

If $A$ rises, the whole production function shifts upward.

```text
Technological progress
  |
  v
Higher A
  |
  v
Same k produces more y
  |
  v
Production curve shifts upward
  |
  v
Output per worker rises at every level of capital per worker
```

This is why CFA says capital deepening and technological progress are different:

| Feature | Capital Deepening | Technological Progress / TFP Growth |
|---|---|---|
| Variable changed | $k = K/L$ | $A$ |
| Visual effect | Movement along the production curve | Upward shift of the production curve |
| Main result | More output per worker because each worker has more capital | More output per worker because every input is more productive |
| Limitation | Diminishing marginal returns | Can support sustained growth |
| More important for | Developing economies with low capital per worker | Developed economies with high capital per worker |

## Decision Tree: What Is Driving Growth?

Use this when a CFA question asks whether growth is coming from capital deepening or technological progress.

```text
Step 1: Did capital per worker rise?
  |
  +-- Yes
  |     |
  |     +-- Decision: capital deepening is contributing to labor productivity growth.
  |     |
  |     +-- Why: each worker has more tools, machines, structures, or productive capital.
  |
  +-- No
        |
        +-- Decision: capital deepening is not the source of higher labor productivity.
        |
        +-- Why: labor productivity cannot rise from more capital per worker if K/L did not increase.

Step 2: Did output per worker rise even at the same K/L?
  |
  +-- Yes
  |     |
  |     +-- Decision: TFP/technological progress is contributing.
  |     |
  |     +-- Why: the same capital per worker now produces more output, so the whole production function shifted upward.
  |
  +-- No
        |
        +-- Decision: there is no evidence of technological progress from the production function alone.
        |
        +-- Why: if A is unchanged, the same K/L produces the same y.
```

## Growth Accounting

The [[Growth accounting equation]] is the Cobb-Douglas production function written in growth-rate form.

Start with:

$$
Y = A K^\alpha L^{1-\alpha}
$$

The growth-rate version is:

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
Output growth
=
TFP growth
+
capital's weighted contribution
+
labor's weighted contribution
```

If $\alpha = 0.30$, then:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
0.30\frac{\Delta K}{K}
+
0.70\frac{\Delta L}{L}
$$

Why are the growth rates weighted?

Because not every 1% increase in an input creates a 1% increase in output. The exponent tells you the output elasticity.

If capital has an elasticity of 0.30, then 1% more capital increases output by only 0.30%, holding everything else constant.

## TFP As The Solow Residual

TFP growth is not directly observed. We measure output, capital, and labor more easily than we measure "technology" or "efficiency."

So we solve for TFP growth as the residual:

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

This is called the [[Solow residual]].

Why residual?

Because it is what is left over after accounting for measured input growth.

```text
Observed output growth
  |
  v
Subtract growth explained by capital
  |
  v
Subtract growth explained by labor
  |
  v
Leftover = TFP growth
```

The deep interpretation:

TFP is not just "technology" in a narrow gadget sense. It includes any improvement in the economy's ability to convert measured inputs into output.

That is powerful, but also dangerous. Because it is a residual, TFP can include:

- real technological progress;
- better management;
- better worker skills not captured in labor quantity;
- better capital quality not captured in capital quantity;
- measurement error;
- omitted inputs;
- changes in capacity utilization;
- institutional improvements.

So TFP is economically important, but it is not perfectly clean.

## Worked Example 1: Compute Output

Suppose an economy has:

- $A = 2$
- $K = 100$
- $L = 400$
- $\alpha = 0.30$

The production function is:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Substitute:

$$
Y = 2(100)^{0.30}(400)^{0.70}
$$

Step 1: Compute $100^{0.30}$.

$$
100^{0.30} \approx 3.981
$$

Step 2: Compute $400^{0.70}$.

$$
400^{0.70} \approx 66.289
$$

Step 3: Multiply.

$$
Y = 2 \times 3.981 \times 66.289
$$

$$
Y \approx 527.8
$$

Conclusion:

$$
\boxed{Y \approx 527.8}
$$

## Worked Example 2: Per-Worker Output

Using the same economy:

- $Y \approx 527.8$
- $K = 100$
- $L = 400$
- $A = 2$
- $\alpha = 0.30$

Compute output per worker directly:

$$
y = \frac{Y}{L}
$$

$$
y = \frac{527.8}{400}
$$

$$
y \approx 1.3195
$$

Now use the per-worker form:

$$
y = A k^\alpha
$$

First compute $k$:

$$
k = \frac{K}{L} = \frac{100}{400} = 0.25
$$

Then:

$$
y = 2(0.25)^{0.30}
$$

$$
(0.25)^{0.30} \approx 0.660
$$

$$
y \approx 2 \times 0.660 = 1.320
$$

The two methods match, with small rounding differences.

Why does this matter?

Because the per-worker form lets you analyze living standards without being distracted by the size of the labor force. Bigger countries can have higher total GDP simply because they have more workers. Per-worker output asks how productive each worker is.

## Worked Example 3: Growth Accounting

Suppose:

- Real GDP growth: $3.5\%$
- Capital growth: $4.0\%$
- Labor growth: $1.0\%$
- Capital share: $\alpha = 0.30$
- Labor share: $1-\alpha = 0.70$

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
3.5\%
=
\frac{\Delta A}{A}
+
0.30(4.0\%)
+
0.70(1.0\%)
$$

Step 1: Capital contribution.

$$
0.30 \times 4.0\% = 1.2\%
$$

Step 2: Labor contribution.

$$
0.70 \times 1.0\% = 0.7\%
$$

Step 3: Add explained input contributions.

$$
1.2\% + 0.7\% = 1.9\%
$$

Step 4: Solve for TFP growth.

$$
\frac{\Delta A}{A}
=
3.5\% - 1.9\%
=
1.6\%
$$

Conclusion:

$$
\boxed{\frac{\Delta A}{A} = 1.6\%}
$$

Interpretation:

Output grew by 3.5%. Capital and labor explain 1.9 percentage points. The remaining 1.6 percentage points are attributed to TFP growth.

## Worked Example 4: Constant Returns To Scale

Suppose:

$$
Y = A K^{0.30}L^{0.70}
$$

Now both capital and labor rise by 10%, while $A$ is unchanged.

Because the exponents sum to 1:

$$
0.30 + 0.70 = 1
$$

output rises by 10%.

Proof:

$$
Y_{new} = A(1.10K)^{0.30}(1.10L)^{0.70}
$$

$$
Y_{new} = A(1.10)^{0.30}K^{0.30}(1.10)^{0.70}L^{0.70}
$$

$$
Y_{new} = (1.10)^{1.00}AK^{0.30}L^{0.70}
$$

$$
Y_{new} = 1.10Y
$$

Conclusion:

$$
\boxed{\text{Output rises by 10%}}
$$

## Worked Example 5: Diminishing Marginal Product Of Capital

Suppose:

- $Y = 500$
- $K = 100$
- $\alpha = 0.30$

Compute MPK:

$$
MPK = \alpha \frac{Y}{K}
$$

$$
MPK = 0.30 \times \frac{500}{100}
$$

$$
MPK = 0.30 \times 5
$$

$$
MPK = 1.5
$$

Interpretation:

One additional unit of capital adds about 1.5 units of output at the margin.

Now suppose the economy becomes more capital intensive:

- $Y = 700$
- $K = 200$
- $\alpha = 0.30$

$$
MPK = 0.30 \times \frac{700}{200}
$$

$$
MPK = 0.30 \times 3.5
$$

$$
MPK = 1.05
$$

Output is higher, but the marginal product of capital is lower.

Why?

Because capital has become less scarce relative to the rest of the economy. Each extra unit of capital adds less incremental output.

## Developed vs Developing Economies

Cobb-Douglas helps explain why developing economies can grow quickly from capital deepening, while developed economies usually need TFP growth for sustained gains.

| Economy Type | Typical $k = K/L$ | MPK | Growth Source | Why |
|---|---:|---:|---|---|
| Developing economy | Low | High | Capital deepening can help a lot | Capital is scarce, so each new unit of capital has high marginal product |
| Developed economy | High | Low | TFP is more important | Capital is already abundant, so additional capital has lower marginal product |

The mechanism:

```text
Low capital per worker
  |
  v
Capital is scarce
  |
  v
MPK is high
  |
  v
Investment adds a lot of output
  |
  v
Capital deepening can drive catch-up growth
```

```text
High capital per worker
  |
  v
Capital is abundant
  |
  v
MPK is low
  |
  v
More capital adds less output
  |
  v
Sustained growth depends more on TFP
```

## Decision Tree: Solving Cobb-Douglas Questions

Use this when you see a CFA question involving Cobb-Douglas.

```text
Step 1: Is the question asking for total output or output growth?
  |
  +-- Total output
  |     |
  |     +-- Decision: use Y = A K^alpha L^(1-alpha).
  |     |
  |     +-- Why: the level equation converts input levels into output level.
  |
  +-- Output growth
        |
        +-- Decision: use growth accounting.
        |
        +-- Why: the growth equation decomposes GDP growth into TFP, capital, and labor contributions.

Step 2: Is the question asking about living standards or labor productivity?
  |
  +-- Yes
  |     |
  |     +-- Decision: use y = A k^alpha.
  |     |
  |     +-- Why: living standards depend on output per worker, not just total output.
  |
  +-- No
        |
        +-- Decision: stay with the aggregate equation.
        |
        +-- Why: total GDP questions care about total K and total L, not per-worker values.

Step 3: Are all inputs increasing by the same percentage?
  |
  +-- Yes
  |     |
  |     +-- Decision: output rises by that same percentage.
  |     |
  |     +-- Why: alpha + (1-alpha) = 1, so Cobb-Douglas has constant returns to scale.
  |
  +-- No
        |
        +-- Decision: weight each input's growth by its exponent.
        |
        +-- Why: alpha and 1-alpha are output elasticities, so inputs do not contribute one-for-one unless their exponent is 1.

Step 4: Is the question asking why growth slows as capital rises?
  |
  +-- Yes
  |     |
  |     +-- Decision: discuss diminishing marginal productivity of capital.
  |     |
  |     +-- Why: alpha < 1, so each additional unit of capital adds less output when labor is fixed.
  |
  +-- No
        |
        +-- Decision: identify whether the question is about TFP, factor shares, or growth accounting.
        |
        +-- Why: Cobb-Douglas questions usually test one of those three mechanics.
```

## Common CFA Traps

### Trap 1: Confusing Total GDP With Labor Productivity

Total GDP:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Labor productivity:

$$
y = \frac{Y}{L} = A k^\alpha
$$

A country can have high total GDP because it has many workers, but that does not mean each worker is highly productive.

### Trap 2: Thinking More Capital Permanently Raises Growth

Capital deepening can raise output per worker, especially when capital is scarce.

But because of diminishing marginal productivity, capital deepening alone cannot generate sustained per-worker growth forever in the neoclassical framework.

Sustained growth in living standards requires TFP growth.

### Trap 3: Forgetting Alpha Has Multiple Meanings

$\alpha$ is:

- capital's output elasticity;
- capital's share of national income;
- capital's weight in the growth accounting equation.

Those are not three unrelated facts. They are connected by the math of Cobb-Douglas and the economic assumption that factors are paid their marginal products.

### Trap 4: Misreading Constant Returns To Scale

Constant returns to scale does not mean every input has constant marginal returns.

Correct:

```text
Increase K and L together -> output rises proportionately.
Increase only K while L is fixed -> MPK falls.
```

### Trap 5: Treating TFP As Directly Observed

TFP growth is usually estimated as a residual:

$$
\frac{\Delta A}{A}
=
\frac{\Delta Y}{Y}
-
\alpha \frac{\Delta K}{K}
-
(1-\alpha)\frac{\Delta L}{L}
$$

That means TFP can include true technology, better organization, omitted inputs, and measurement error.

### Trap 6: Forgetting Labor's Share

If the question gives labor's share instead of capital's share:

$$
\alpha = 1 - \text{labor share}
$$

Example:

If labor receives 65% of income:

$$
1-\alpha = 0.65
$$

$$
\alpha = 0.35
$$

Then the growth accounting equation is:

$$
\frac{\Delta Y}{Y}
=
\frac{\Delta A}{A}
+
0.35\frac{\Delta K}{K}
+
0.65\frac{\Delta L}{L}
$$

## Minimum Memorization

Memorize these:

$$
\boxed{Y = A K^\alpha L^{1-\alpha}}
$$

$$
\boxed{y = A k^\alpha}
$$

$$
\boxed{MPK = \alpha \frac{Y}{K}}
$$

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

And the core intuition:

```text
Capital deepening moves along the curve.
TFP growth shifts the curve upward.

Capital deepening eventually slows because of diminishing returns.
TFP growth is the long-run engine of labor productivity growth.
```

## Can I Solve This?

1. If capital's share is 0.35, what is labor's share?

Answer:

$$
1-\alpha = 1 - 0.35 = 0.65
$$

Labor's share is 65%.

2. If capital and labor both rise by 6%, and TFP is unchanged, what happens to output?

Answer:

Output rises by 6% because Cobb-Douglas has constant returns to scale when the exponents sum to 1.

3. If GDP grows 4%, capital grows 5%, labor grows 2%, and $\alpha = 0.30$, what is TFP growth?

Answer:

Capital contribution:

$$
0.30 \times 5\% = 1.5\%
$$

Labor contribution:

$$
0.70 \times 2\% = 1.4\%
$$

Input contribution:

$$
1.5\% + 1.4\% = 2.9\%
$$

TFP growth:

$$
4.0\% - 2.9\% = 1.1\%
$$

4. Why does capital deepening eventually become less powerful?

Answer:

Because $\alpha < 1$, the production function is concave in capital. As capital per worker rises, the marginal product of capital falls. Each additional unit of capital adds less output than the previous unit.

5. Why can TFP raise output per worker even if capital per worker does not change?

Answer:

Because $A$ multiplies the entire production function. A higher $A$ means the same capital per worker produces more output per worker.

## Related Concepts

- [[Production function]]
- [[CFA_Glossary/Economic growth]]
- [[Potential GDP]]
- [[Growth accounting equation]]
- [[Solow residual]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Labor productivity]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Technological progress]]
- [[Diminishing marginal productivity]]
- [[Constant returns to scale]]
- [[Marginal product]]
- [[Marginal product of capital]]
- [[Level 2/Generated Notes/03 - Economics/Rental Price of Capital]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Labor]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Conditional convergence]]
