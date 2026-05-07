---
title: Capital Stock
subject: Economics
tags: [CFA-L2, economics, economic-growth, capital-stock, capital-deepening, solow-model]
aliases: [capital stock, physical capital stock, K, stock of capital, productive capital]
---

# Capital Stock

## The Real-World Analogy

Think of an economy as a workshop.

The workshop has workers, but workers need tools:

- machines;
- buildings;
- computers;
- delivery vehicles;
- warehouses;
- roads and infrastructure;
- production equipment.

The total accumulated pile of productive tools is the economy's [[Level 2/Generated Notes/03 - Economics/Capital Stock]].

If workers are the hands of the economy, capital stock is the toolbox.

```text
Labor = who works
Capital stock = what they work with
TFP = how well the people and tools are organized
```

A worker with no tools can produce something, but not much. A worker with a machine, software, electricity, roads, and a factory can produce far more.

That is why capital stock matters for [[CFA_Glossary/Economic growth]] and [[Labor productivity]].

## The One-Minute Version

[[Level 2/Generated Notes/03 - Economics/Capital Stock]] is the accumulated amount of buildings, machinery, equipment, structures, infrastructure, and other productive assets used to produce goods and services.

In the production function:

$$
Y = A F(K,L)
$$

and in [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function|Cobb-Douglas]]:

$$
Y = A K^\alpha L^{1-\alpha}
$$

$K$ is the capital stock.

The key distinction:

```text
Capital stock = accumulated productive assets at a point in time.
Investment = spending flow that adds to capital stock over time.
Depreciation = wearing-out flow that subtracts from capital stock over time.
```

Memory hook:

```text
Capital stock is the bathtub water level.
Investment is the faucet.
Depreciation is the drain.
```

## What Counts As Capital Stock

Capital stock means productive physical assets, not just "money."

Examples:

| Counts As Capital Stock | Why |
|---|---|
| Factories | Used to produce goods |
| Machinery | Directly helps transform inputs into output |
| Equipment | Enables workers to produce more |
| Buildings and structures | Provide productive space |
| Trucks and logistics assets | Move goods through the production chain |
| Computers and software systems | Help organize, automate, and process production |
| Infrastructure | Roads, ports, utilities, communications networks support production |

The common thread:

```text
Capital stock is durable.
Capital stock is productive.
Capital stock helps labor create output over multiple periods.
```

## Physical Capital vs Human Capital vs Financial Capital

CFA can use "capital" in multiple ways, so keep them separate.

| Type | Meaning | Production Function Role |
|---|---|---|
| [[Physical capital]] / capital stock | Machines, buildings, equipment, infrastructure | The $K$ in $Y = A K^\alpha L^{1-\alpha}$ |
| [[Human capital]] | Worker education, skill, training, health | Can raise effective labor quality or show up partly in TFP |
| Financial capital | Money, securities, funding | Finances physical capital but is not itself a machine producing goods |

Why financial capital is different:

Money helps buy machines, but money sitting in a bank account does not directly produce output. The factory, machine, software, or infrastructure purchased with the money becomes productive capital.

## Stock vs Flow

This is the most important beginner distinction.

A stock is measured at a point in time.

A flow is measured over a period of time.

| Concept | Stock or Flow? | Example |
|---|---|---|
| Capital stock | Stock | The economy has $10 trillion of productive capital on December 31 |
| Gross investment | Flow | Firms spend $700 billion on new capital during the year |
| Depreciation | Flow | $300 billion of capital wears out during the year |
| Net investment | Flow | Capital stock increases by $400 billion during the year |

The bathtub picture:

```text
Capital stock = water already in the bathtub
Gross investment = water flowing in through faucet
Depreciation = water draining out
Net investment = faucet minus drain
```

## How Capital Stock Changes

Capital stock increases when new investment exceeds depreciation.

The basic formula:

$$
K_t = K_{t-1} + I_t - D_t
$$

Where:

| Symbol | Meaning |
|---|---|
| $K_t$ | Capital stock at the end of period $t$ |
| $K_{t-1}$ | Capital stock at the beginning of the period |
| $I_t$ | Gross investment during the period |
| $D_t$ | Depreciation during the period |

Net investment is:

$$
\text{Net investment} = I_t - D_t
$$

So:

$$
K_t = K_{t-1} + \text{Net investment}
$$

Decision rule:

| Condition | Capital Stock Effect | Why |
|---|---|---|
| Gross investment > depreciation | Capital stock rises | New capital added exceeds capital wearing out |
| Gross investment = depreciation | Capital stock unchanged | New capital only replaces worn-out capital |
| Gross investment < depreciation | Capital stock falls | The economy is not replacing capital fast enough |

## Worked Example 1: Updating Capital Stock

Suppose an economy begins the year with:

- Beginning capital stock: $K_{t-1} = 1{,}000$
- Gross investment: $I_t = 120$
- Depreciation: $D_t = 50$

Use:

$$
K_t = K_{t-1} + I_t - D_t
$$

Substitute:

$$
K_t = 1{,}000 + 120 - 50
$$

Calculate net investment:

$$
120 - 50 = 70
$$

Final capital stock:

$$
K_t = 1{,}070
$$

Conclusion:

$$
\boxed{K_t = 1{,}070}
$$

The capital stock grew because gross investment exceeded depreciation.

## Capital Stock In The Production Function

Capital stock is a main input into output.

General form:

$$
Y = A F(K,L)
$$

Cobb-Douglas form:

$$
Y = A K^\alpha L^{1-\alpha}
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Real output / GDP |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $K$ | Capital stock |
| $L$ | Labor |
| $\alpha$ | Capital's output elasticity and income share |

If $K$ rises, output rises, holding $A$ and $L$ constant.

But because $\alpha < 1$, output rises less than proportionately.

Example:

If $\alpha = 0.30$, then a 1% increase in capital stock increases output by about 0.30%, holding labor and TFP constant.

Why?

Because $\alpha$ is the output elasticity of capital.

## Capital Per Worker

For living standards, CFA often cares about capital per worker:

$$
k = \frac{K}{L}
$$

This tells you how much capital the average worker has available.

In per-worker Cobb-Douglas:

$$
y = A k^\alpha
$$

Where:

| Symbol | Meaning |
|---|---|
| $y = Y/L$ | Output per worker, or labor productivity |
| $k = K/L$ | Capital per worker |
| $A$ | TFP |

Why $K/L$ matters:

```text
More capital stock alone does not guarantee higher living standards.
The capital stock must grow relative to labor.
```

If capital grows 5% but labor grows 5%, capital per worker is roughly unchanged.

If capital grows 5% and labor grows 2%, capital per worker rises.

If capital grows 2% and labor grows 5%, capital per worker falls.

## Capital Deepening

[[Level 2/Generated Notes/03 - Economics/Capital Deepening]] means the capital-to-labor ratio rises:

$$
\frac{K}{L} \uparrow
$$

That means each worker has more capital to work with.

The chain:

```text
Capital stock grows faster than labor
  |
  v
K/L rises
  |
  v
Workers have more tools
  |
  v
Output per worker rises
  |
  v
Labor productivity rises
```

But the effect weakens as capital becomes abundant because of [[Diminishing marginal productivity]].

## Diminishing Marginal Product Of Capital

The [[Marginal product of capital]] is the additional output produced by one more unit of capital, holding other inputs constant.

In Cobb-Douglas:

$$
MPK = \alpha \frac{Y}{K}
$$

The intuition:

```text
When capital is scarce:
One more machine is very valuable.

When capital is abundant:
One more machine adds less.
```

This is why developing economies can grow quickly from capital accumulation, while developed economies usually need [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP]] growth for sustained gains.

## Worked Example 2: Capital Per Worker

Suppose:

- Capital stock: $K = 500$
- Labor: $L = 100$

Capital per worker:

$$
k = \frac{K}{L}
$$

$$
k = \frac{500}{100} = 5
$$

Now suppose investment raises capital stock to $600$, while labor rises to $120$.

New capital per worker:

$$
k = \frac{600}{120} = 5
$$

Capital stock rose, but capital per worker did not.

Conclusion:

```text
Total K increased, but K/L did not increase.
So there is no capital deepening.
```

Why this matters:

Labor productivity depends on capital per worker, not just total capital stock.

## Worked Example 3: Growth Accounting Contribution

Suppose:

- Capital stock growth: $5.0\%$
- Labor growth: $2.0\%$
- Capital share: $\alpha = 0.40$
- Labor share: $1-\alpha = 0.60$
- Total GDP growth: $6.0\%$

Capital's growth contribution:

$$
\alpha \frac{\Delta K}{K}
=
0.40 \times 5.0\%
=
2.0\%
$$

Labor's growth contribution:

$$
(1-\alpha)\frac{\Delta L}{L}
=
0.60 \times 2.0\%
=
1.2\%
$$

Input contribution:

$$
2.0\% + 1.2\% = 3.2\%
$$

TFP growth:

$$
6.0\% - 3.2\% = 2.8\%
$$

Conclusion:

Capital stock growth contributed 2.0 percentage points to GDP growth. TFP contributed 2.8 percentage points.

## Solow Model: Capital Accumulation

In the [[Solow Model (Neoclassical Growth Theory)]], capital per worker changes according to:

$$
\Delta k = s \cdot y - (\delta + n)k
$$

Where:

| Term | Meaning |
|---|---|
| $s \cdot y$ | Actual investment per worker |
| $\delta k$ | Capital per worker lost to depreciation |
| $n k$ | Capital dilution from population growth |
| $(\delta+n)k$ | Break-even investment needed to keep $k$ unchanged |

The logic:

```text
Actual investment > break-even investment
  |
  v
k rises
  |
  v
capital deepening occurs
```

```text
Actual investment = break-even investment
  |
  v
k is stable
  |
  v
steady state
```

```text
Actual investment < break-even investment
  |
  v
k falls
  |
  v
capital shallowing occurs
```

## Break-Even Investment

Break-even investment is the investment needed just to keep capital per worker from falling.

It has two parts:

| Component | Why It Matters |
|---|---|
| Depreciation, $\delta k$ | Machines wear out and must be replaced |
| Population growth, $nk$ | New workers need capital just to keep $K/L$ constant |

If technology growth is included, the full break-even term may also include the investment needed to keep capital per effective worker constant, but the basic CFA intuition is:

```text
Break-even investment replaces worn-out capital and equips new workers.
```

## Decision Tree: Is Capital Deepening Happening?

```text
Step 1: Did total capital stock rise?
  |
  +-- No
  |     |
  |     +-- Decision: no capital deepening.
  |     |
  |     +-- Why: K cannot rise relative to L if K itself did not rise.
  |
  +-- Yes
        |
        +-- Decision: check whether K rose faster than L.
        |
        +-- Why: capital deepening depends on K/L, not K alone.

Step 2: Did K grow faster than L?
  |
  +-- Yes
  |     |
  |     +-- Decision: capital deepening is occurring.
  |     |
  |     +-- Why: each worker has more capital because K/L increased.
  |
  +-- No
        |
        +-- Decision: no capital deepening; possibly capital shallowing if K grew slower than L.
        |
        +-- Why: total capital may rise while capital per worker stays flat or falls.
```

## Decision Tree: What Happens To Capital Stock?

```text
Step 1: Compare gross investment with depreciation.
  |
  +-- Investment > depreciation
  |     |
  |     +-- Decision: capital stock rises.
  |     |
  |     +-- Why: the economy adds more new capital than it loses to wear and obsolescence.
  |
  +-- Investment = depreciation
  |     |
  |     +-- Decision: capital stock is unchanged.
  |     |
  |     +-- Why: new investment only replaces worn-out capital.
  |
  +-- Investment < depreciation
        |
        +-- Decision: capital stock falls.
        |
        +-- Why: the economy is not replacing capital as fast as it wears out.
```

## Developed vs Developing Economies

Capital stock has different growth implications depending on how much capital an economy already has.

| Economy Type | Typical Capital Per Worker | MPK | Growth Implication |
|---|---:|---:|---|
| Developing economy | Low | High | Capital accumulation can raise growth significantly |
| Developed economy | High | Low | More capital has smaller effect; TFP matters more |

Why:

```text
Low K/L
  |
  v
Capital is scarce
  |
  v
MPK is high
  |
  v
New investment adds a lot of output
```

```text
High K/L
  |
  v
Capital is abundant
  |
  v
MPK is low
  |
  v
New investment adds little output
```

## Common CFA Traps

### Trap 1: Confusing Capital Stock With Investment

Capital stock is the accumulated level of productive assets.

Investment is the flow that adds to the capital stock.

### Trap 2: Forgetting Depreciation

Gross investment alone does not tell you whether capital stock increased.

You need net investment:

$$
\text{Net investment} = \text{Gross investment} - \text{Depreciation}
$$

### Trap 3: Confusing Total Capital With Capital Per Worker

Total capital can rise while capital per worker stays flat or falls.

Example:

```text
K grows 3%
L grows 5%
K/L falls
```

That is not capital deepening.

### Trap 4: Thinking Capital Accumulation Permanently Raises Growth

In the neoclassical/Solow model, capital accumulation can raise the level of output per worker but cannot permanently raise the growth rate of output per worker because of diminishing marginal returns.

Sustained per-capita growth requires [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP growth]].

### Trap 5: Treating Financial Capital As Physical Capital

Financial capital funds production, but the production function's $K$ is productive capital: buildings, machines, structures, and equipment.

## Minimum Memorization

Memorize:

$$
\boxed{K_t = K_{t-1} + I_t - D_t}
$$

$$
\boxed{k = \frac{K}{L}}
$$

$$
\boxed{Y = A K^\alpha L^{1-\alpha}}
$$

$$
\boxed{MPK = \alpha \frac{Y}{K}}
$$

And the core intuition:

```text
Capital stock is a stock.
Investment and depreciation are flows.

Capital deepening means K/L rises, not just K rises.

More capital helps, but diminishing returns mean TFP is needed for sustained long-run growth.
```

## Can I Solve This?

1. Beginning capital stock is 800, gross investment is 100, and depreciation is 40. What is ending capital stock?

$$
K_t = 800 + 100 - 40 = 860
$$

Answer: Ending capital stock is 860.

2. Capital stock grows 4% and labor grows 6%. Is there capital deepening?

Answer: No. Capital per worker falls because capital grows slower than labor.

3. Capital stock grows 7% and labor grows 2%. Is there capital deepening?

Answer: Yes. Capital grows faster than labor, so $K/L$ rises.

4. Why does capital accumulation eventually slow as a growth source?

Answer: Because the marginal product of capital falls as capital becomes more abundant. Each additional unit of capital adds less output.

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Production function]]
- [[CFA_Glossary/Economic growth]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Capital deepening investment]]
- [[Physical capital]]
- [[Human capital]]
- [[Labor productivity]]
- [[Diminishing marginal productivity]]
- [[Marginal product of capital]]
- [[Depreciation]]
- [[Capital consumption allowance]]
- [[Gross investment]]
- [[Net investment]]
- [[Steady State]]
