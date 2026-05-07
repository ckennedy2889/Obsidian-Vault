---
title: ICT vs Non-ICT Capital
subject: Economics
tags: [CFA-L2, economics, economic-growth, growth-accounting, capital-deepening, productivity]
aliases: [ICT capital, non-ICT capital, information computer and telecommunications capital, information and communication technology capital, physical capital types]
---

# ICT vs Non-ICT Capital

## The Real-World Analogy

Imagine two firms each spend $10 million on capital.

The first firm buys more delivery trucks and warehouse space. Workers can now move more boxes per day. That is useful, but the effect is mostly local: the firm has more equipment per worker.

The second firm builds a digital ordering platform, connects suppliers, installs inventory software, and gives workers handheld scanners. Each worker is better equipped, but something bigger also happens: the whole system coordinates faster. Suppliers see demand sooner, inventory errors fall, customers order more easily, and the platform becomes more valuable as more people use it.

That difference is the heart of **ICT vs non-ICT capital**. Both are forms of [[Physical capital]]. Both can raise output. But **ICT capital** can also create spillovers and network effects that look closer to [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|technological progress]], while **non-ICT capital** is usually closer to ordinary [[Level 2/Generated Notes/03 - Economics/Capital Deepening]].

## The Big Idea

In the CFA Economics reading on [[CFA_Glossary/Economic growth]], the production function is expanded beyond basic capital and labor:

$$
Y = AF(N, L, H, K_{IT}, K_{NT}, K_P)
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Output |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] / technological knowledge |
| $N$ | Natural resources |
| $L$ | Quantity of labor |
| $H$ | [[Human capital]] |
| $K_{IT}$ | ICT capital |
| $K_{NT}$ | Non-ICT capital |
| $K_P$ | Public capital |

The key distinction:

| Capital type | What it includes | CFA intuition |
|---|---|---|
| **ICT capital** | Computer hardware, software, and communications equipment | Can raise productivity through both capital deepening and technology/network effects |
| **Non-ICT capital** | Transport equipment, metal products, plant machinery excluding computer/communications equipment, non-residential buildings, and other structures | Mostly raises productivity through traditional capital deepening |

## Why CFA Tests This

CFA is trying to make you separate three related but different ideas:

1. **More capital per worker** raises [[Labor productivity]].
2. **Diminishing marginal returns** mean ordinary capital deepening cannot sustain high growth forever.
3. Some capital, especially ICT capital, can embody or spread new technology, making the effect bigger than a simple machine-per-worker story.

That third point is the nuance. If a question says "investment in physical capital," you should not automatically assume it is only boring capital deepening. If the capital is ICT, software, communications infrastructure, or a network, it may also support [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP]] growth through spillovers.

## ICT Capital

**ICT capital** means information, computer, and telecommunications capital. CFA examples include:

- computer hardware;
- software;
- communication equipment;
- IT networks.

Mechanically, ICT capital raises output in two ways.

First, it gives each worker better tools:

```text
More ICT capital
  |
  v
More useful capital per worker
  |
  v
Higher labor productivity
```

That is still [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]. A worker with better software, faster systems, and better communication tools can produce more output per hour.

Second, ICT may improve the way the whole economy organizes production:

```text
More ICT adoption
  |
  v
More connections among firms, workers, suppliers, and customers
  |
  v
Better matching, lower search costs, faster information flow
  |
  v
Higher economy-wide efficiency / TFP
```

This is why CFA emphasizes **network externalities**. A network becomes more valuable as more people connect to it. One firm using email or cloud inventory software helps that firm. But when suppliers, customers, logistics providers, and employees are all digitally connected, the whole network becomes more productive.

The exam implication: ICT investment can be classified as physical capital, but its growth effect may include a technological-progress channel.

## Non-ICT Capital

**Non-ICT capital** includes physical assets that are not computer hardware, software, or communications equipment. CFA examples include:

- transportation equipment;
- metal products;
- plant machinery other than computer hardware and communications equipment;
- non-residential buildings;
- other structures.

Non-ICT capital usually works through the classic capital-deepening mechanism:

```text
More non-ICT capital
  |
  v
Higher K/L
  |
  v
Each worker has more equipment or structure to work with
  |
  v
Labor productivity rises
  |
  v
But marginal product of capital eventually falls
```

If a factory buys more machines, output per worker may rise. But if it keeps adding machines without improving technology, worker skill, demand, or organization, each additional machine eventually adds less incremental output. That is [[Diminishing marginal productivity]].

The exam implication: non-ICT capital is usually the cleanest example of **capital deepening**, not technological progress.

## The Deep Mechanism

Start with the simple labor productivity equation:

$$
y = \frac{Y}{L}
$$

Labor productivity rises when output per worker rises.

In a basic Cobb-Douglas style setup:

$$
Y = AK^\alpha L^{1-\alpha}
$$

Divide by labor:

$$
y = Ak^\alpha
$$

Where:

$$
k = \frac{K}{L}
$$

This says labor productivity depends on:

1. $A$, or TFP; and
2. $k$, or capital per worker.

So when non-ICT capital rises faster than labor, $k$ rises:

$$
\frac{K}{L}\uparrow \Rightarrow y\uparrow
$$

That is capital deepening.

But ICT capital can affect both sides:

$$
K_{IT}\uparrow \Rightarrow k\uparrow
$$

and potentially:

$$
K_{IT}\uparrow \Rightarrow A\uparrow
$$

That second arrow is the important CFA nuance. ICT can make the entire production process more efficient, not merely give workers more equipment.

## Comparison Table

| Feature | ICT capital | Non-ICT capital |
|---|---|---|
| CFA examples | Hardware, software, communications equipment | Transportation equipment, plant machinery, buildings, structures |
| Type of capital | Physical capital with technology/network qualities | Traditional physical capital |
| Main channel | Capital deepening plus possible TFP spillovers | Capital deepening |
| Effect on labor productivity | Raises output per worker | Raises output per worker |
| Diminishing returns? | Still possible, but network effects can offset or delay the simple diminishing-return story | More directly subject to diminishing marginal returns |
| Spillovers | Often meaningful because networks become more valuable as adoption grows | Usually more limited and local |
| Exam phrase to notice | "network externalities," "IT networks," "software," "communications" | "machinery," "transportation," "non-residential structures" |

## Worked Numerical Example

Suppose an economy has:

- TFP growth = 1.0%;
- labor growth = 1.5%;
- capital share, $\alpha = 0.30$;
- non-ICT capital per worker growth = 3.0%;
- ICT capital per worker growth = 4.0%.

To keep the example simple, assume the capital share is split:

| Capital type | Weight |
|---|---:|
| Non-ICT capital | 0.20 |
| ICT capital | 0.10 |
| Total capital share | 0.30 |

Labor productivity growth is:

$$
\frac{\Delta y}{y}
=
\frac{\Delta A}{A}
+0.20\left(\frac{\Delta k_{NT}}{k_{NT}}\right)
+0.10\left(\frac{\Delta k_{IT}}{k_{IT}}\right)
$$

Substitute:

$$
\frac{\Delta y}{y}
=
1.0\%
+0.20(3.0\%)
+0.10(4.0\%)
$$

Calculate each capital contribution:

$$
0.20(3.0\%)=0.6\%
$$

$$
0.10(4.0\%)=0.4\%
$$

So:

$$
\frac{\Delta y}{y}
=
1.0\%+0.6\%+0.4\%=2.0\%
$$

If labor grows 1.5%, then potential GDP growth is approximately:

$$
\text{Potential GDP growth}
=
\text{labor growth}
+
\text{labor productivity growth}
$$

$$
=1.5\%+2.0\%=3.5\%
$$

Now suppose ICT investment also creates network externalities that raise TFP by an additional 0.3%. Then TFP growth becomes 1.3%:

$$
\frac{\Delta y}{y}
=
1.3\%+0.6\%+0.4\%=2.3\%
$$

Potential GDP growth becomes:

$$
1.5\%+2.3\%=3.8\%
$$

The lesson is not that ICT always magically raises TFP. The lesson is that ICT can have a direct capital-deepening effect and an indirect technology/spillover effect.

## Exam Traps

| Trap | Correct exam move |
|---|---|
| Thinking ICT capital is not physical capital | ICT is a form of physical capital in the expanded production function |
| Treating ICT and non-ICT as identical | ICT often has network externalities and may support TFP growth |
| Assuming all capital deepening creates sustained long-run growth | Pure capital deepening runs into diminishing marginal returns |
| Forgetting the per-worker logic | Capital deepening requires capital per worker to rise, not merely total capital |
| Calling every productivity improvement TFP | If output rises because workers have more capital, that is capital deepening; TFP is output growth beyond measured input growth |
| Ignoring developing vs developed economy context | Capital deepening has larger effects when capital per worker is initially low |

## Decision Rule

Use this on exam day:

```text
Is the investment hardware, software, communications, or IT networks?
  |
  +-- Yes -> ICT capital.
  |          Think: capital deepening + possible network externalities / TFP spillovers.
  |
  +-- No -> Is it machinery, transport equipment, buildings, structures?
             |
             +-- Yes -> Non-ICT capital.
                       Think: classic capital deepening, subject to diminishing returns.
```

## Memory Hooks

**Non-ICT capital** is the "more machines and buildings" story.

**ICT capital** is the "more connected and coordinated economy" story.

For the CFA exam:

> Non-ICT mostly gives workers more tools. ICT can give workers more tools and make the whole system smarter.

## Related Concepts

- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Capital deepening investment]]
- [[Labor productivity]]
- [[Labor productivity growth accounting equation]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Growth Accounting]]
- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Potential GDP]]
- [[Human capital]]
- [[CFA_Glossary/Economic growth]]
