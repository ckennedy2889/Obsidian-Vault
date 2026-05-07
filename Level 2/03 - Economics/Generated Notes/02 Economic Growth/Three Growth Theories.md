---
title: Three Growth Theories
subject: Economics
tags: [CFA-L2, economics, economic-growth, growth-theory, solow-model, endogenous-growth]
aliases: [classical growth theory vs neoclassical growth theory vs endogenous growth theory, growth theories, classical growth theory, neoclassical growth theory, endogenous growth theory]
---

# Three Growth Theories

## The Real-World Analogy

Think of an economy like a farm.

The **classical** view says the farm has fixed land. If better tools raise food per person, families have more children, population rises, and the extra mouths eventually eat up the gain. The farm supports more people, but people are not richer in the long run.

The **neoclassical** view says the farm can accumulate more tractors and equipment, but each extra tractor helps less than the previous one. More saving and investment can make the farm richer, but only better technology can keep output per person growing forever.

The **endogenous** view says some investment does not just add another tractor. It creates knowledge, better seeds, better irrigation methods, and know-how that other farms can copy. Because knowledge spills over, investment can permanently raise the growth rate.

That is the whole contrast:

```text
Classical:    growth gets eaten by population
Neoclassical: growth lasts only if technology improves from outside the model
Endogenous:  growth can be created inside the model through knowledge investment
```

## The Big Idea

CFA compares the three theories because each one gives a different answer to the same question:

> What determines the long-run growth rate of real GDP per capita?

The answer matters because [[CFA_Glossary/Economic growth]] drives [[Potential GDP]], expected real income growth, long-run equity earnings, interest rates, and the ability of developing countries to catch up to developed countries.

| Theory | Long-run per-capita growth? | Why? |
|---|---|---|
| [[Classical growth theory]] | No sustained growth | Population growth drives income back to subsistence |
| [[Neoclassical growth theory]] / [[Solow Model (Neoclassical Growth Theory)]] | Yes, but only from exogenous technology | Capital deepening has diminishing returns |
| [[Endogenous growth theory]] | Yes, from investment in knowledge, R&D, and human capital | Knowledge spillovers can prevent diminishing returns at the economy-wide level |

## Classical Growth Theory

Classical growth theory is associated with Thomas Malthus. Its core idea is that the economy faces a fixed resource constraint, especially land.

The simple production story is:

$$
Y = F(L, \text{land})
$$

Land is fixed. Labor can grow. If population rises while land is fixed, each additional worker has less land to work with. That creates [[Diminishing marginal productivity]] of labor.

The mechanism is:

```text
Technology or capital improves
  |
  v
Real GDP per capita rises above subsistence
  |
  v
Population growth accelerates
  |
  v
More workers share fixed land/resources
  |
  v
Marginal product of labor falls
  |
  v
Real GDP per capita returns to subsistence
```

The key word is **subsistence**. Subsistence income is the minimum income needed to maintain life. In the classical model, if income rises above subsistence, population growth rises. If income falls below subsistence, population growth slows or reverses. So the economy is pulled back toward subsistence income.

This means technological progress creates a **larger population**, not a permanently richer population.

### Why Classical Theory Failed Empirically

The classical prediction did not hold in modern economies for two main reasons.

First, the assumed positive link between income and population growth broke down. In many economies, as income and education rise, birth rates fall. This is the demographic transition.

Second, technological progress became strong enough to more than offset diminishing returns to fixed resources. Better machines, energy use, transportation, medicine, education, and organization allowed output per worker to keep rising.

The exam implication: classical growth theory is historically important, but CFA says it is **not supported by empirical evidence** as a modern long-run growth model.

## Neoclassical Growth Theory

Neoclassical growth theory is the [[Solow Model (Neoclassical Growth Theory)]]. It shifts the focus from land and population traps to capital accumulation, labor growth, and technology.

The basic production function is:

$$
Y = AK^\alpha L^{1-\alpha}
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Output |
| $A$ | [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] |
| $K$ | [[Level 2/Generated Notes/03 - Economics/Capital Stock]] |
| $L$ | Labor |
| $\alpha$ | Capital's share of output |
| $1-\alpha$ | Labor's share of output |

Per worker:

$$
y = Ak^\alpha
$$

Where:

$$
y = \frac{Y}{L}
$$

and:

$$
k = \frac{K}{L}
$$

This says output per worker depends on [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)|TFP]] and capital per worker.

### The Mechanism

If an economy saves more, it invests more:

```text
Higher saving/investment
  |
  v
More capital per worker
  |
  v
Higher output per worker
  |
  v
Diminishing returns to capital eventually appear
  |
  v
Growth rate returns to steady-state rate
```

The subtle but critical point: in Solow, a higher saving rate can permanently raise the **level** of output per worker, but it cannot permanently raise the **growth rate** of output per worker.

Why? Because capital has diminishing marginal returns. The first machines added to a low-capital economy are very powerful. The hundredth extra machine in an already capital-rich economy adds much less.

### Steady-State Growth Formula

CFA gives the neoclassical steady-state growth rate of output per capita as:

$$
g^*_{\text{per capita}} = \frac{\theta}{1-\alpha}
$$

Where:

| Term | Meaning |
|---|---|
| $\theta$ | Growth rate of TFP |
| $\alpha$ | Capital's share of output |
| $1-\alpha$ | Labor's share of output |

Total output growth adds labor force growth:

$$
G^* = \frac{\theta}{1-\alpha}+n
$$

Where:

$$
n = \text{labor force growth}
$$

This is the exam-famous result: once the economy is at the steady state, **capital deepening is still occurring but does not affect the long-run growth rate**. Long-run per-capita growth depends on TFP growth and labor's share.

### Worked Numerical Example

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

Per-capita sustainable growth is:

$$
g^*_{\text{per capita}}=\frac{\theta}{1-\alpha}
$$

$$
g^*_{\text{per capita}}=\frac{1.4\%}{1-0.30}
$$

$$
g^*_{\text{per capita}}=\frac{1.4\%}{0.70}=2.0\%
$$

Total sustainable output growth is:

$$
G^*=2.0\%+0.8\%=2.8\%
$$

Interpretation: if saving rises, the country may grow faster for a while as capital per worker rises. But in the long run, unless $\theta$ or $n$ changes, the sustainable total growth rate remains 2.8%.

## Endogenous Growth Theory

Endogenous growth theory was developed to fix the main weakness of the Solow model: Solow says technology drives long-run growth, but then treats technology as coming from outside the model.

Endogenous growth says technological progress is created **inside** the economy through:

- [[Human capital]];
- research and development;
- education;
- innovation;
- knowledge capital;
- learning by doing;
- ICT and network spillovers.

The simplest version is often called the AK model:

$$
Y = AK
$$

Here, $K$ is interpreted broadly. It includes not only physical capital but also human capital and knowledge capital.

The key assumption is **constant returns to capital at the economy-wide level**. A single firm may face diminishing returns to its own R&D, but the economy may not because knowledge spills over.

```text
Firm invests in R&D or human capital
  |
  v
New knowledge is created
  |
  v
Other firms learn, imitate, adapt, or hire trained workers
  |
  v
Economy-wide productivity rises
  |
  v
Social return exceeds private return
```

This is why endogenous growth theory gives a stronger role to public policy. If firms cannot capture all the benefits of innovation, they may underinvest from society's perspective. That creates a rationale for patents, R&D subsidies, education spending, public research, and infrastructure that supports knowledge diffusion.

### The Key Difference From Solow

In the Solow model:

$$
\text{Higher saving} \Rightarrow \text{higher level of } Y/L, \text{ not permanently higher growth}
$$

In endogenous growth theory:

$$
\text{Higher investment in knowledge capital} \Rightarrow \text{potentially permanently higher growth}
$$

That difference is testable because CFA loves asking whether a policy changes the **level** of output or the **growth rate** of output.

## Master Comparison Table

| Feature | Classical | Neoclassical / Solow | Endogenous |
|---|---|---|---|
| Main thinker | Malthus | Solow | Romer / Lucas style models |
| Core constraint | Fixed land/resources | Diminishing returns to capital | Knowledge spillovers can offset diminishing returns |
| Technology | Helps temporarily, but population absorbs gains | Exogenous; drives long-run growth but is unexplained | Endogenous; created by investment, R&D, human capital |
| Population | Rises when income rises above subsistence | Independent driver of total output growth | Can matter, but knowledge and human capital dominate |
| Capital deepening | Not central; fixed resources dominate | Raises level, not long-run growth rate | Can raise growth if capital includes knowledge/human capital |
| Long-run per-capita growth | Returns to zero / subsistence | $\theta/(1-\alpha)$ | Can be permanently increased by investment and policy |
| Effect of higher saving | Population eventually absorbs gains | Higher level of $Y/L$, temporary growth boost | Permanently higher growth possible |
| Policy role | Very limited | Limited for long-run growth unless policy affects TFP | Strong role for education, R&D, patents, innovation policy |
| Convergence implication | Not the central prediction | Conditional convergence | No automatic convergence |
| CFA exam phrase | Subsistence trap | Steady state; capital deepening has diminishing returns | Knowledge spillovers; constant returns to capital |

## Convergence Link

The three models also imply different views about whether poor countries catch up to rich countries.

| Theory | Convergence implication |
|---|---|
| Classical | Poor and rich alike are pulled toward subsistence in the long run |
| Neoclassical | Poor countries can grow faster because they have lower capital per worker and higher marginal product of capital, but convergence is usually conditional |
| Endogenous | No automatic convergence; countries with more human capital, R&D, institutions, and knowledge networks may keep pulling ahead |

The most important CFA nuance is that Solow supports **conditional convergence**, not guaranteed absolute convergence.

[[Conditional convergence]] means countries converge if they have similar:

- saving rates;
- population growth rates;
- production functions;
- institutions and policy environments.

If those conditions are not similar, countries can converge to different steady states.

## Exam Traps

| Trap | Correct exam move |
|---|---|
| Saying Solow predicts saving permanently raises growth | Saving raises the level of output per worker; long-run growth returns to steady state |
| Forgetting the Solow formula uses labor's share in the denominator | $g^*_{\text{per capita}}=\theta/(1-\alpha)$ |
| Treating technology the same in all models | Classical: absorbed by population; Solow: exogenous; endogenous: explained inside the model |
| Saying capital deepening always sustains growth | Pure capital deepening runs into diminishing returns |
| Saying endogenous growth predicts convergence | Endogenous theory does not imply automatic convergence |
| Thinking classical theory is empirically supported today | CFA says its prediction failed because population growth slowed as income rose and technology offset diminishing returns |
| Confusing level and rate | Solow policy/saving effects often change the level; endogenous policies can change the growth rate |

## Decision Rule

Use this when a question describes a policy or growth pattern:

```text
Does the story say population absorbs income gains and income returns to subsistence?
  |
  +-- Yes -> Classical growth theory
  |
  +-- No
       |
       +-- Does capital deepening raise the level but not the long-run growth rate?
       |     |
       |     +-- Yes -> Neoclassical / Solow
       |
       +-- Does investment in R&D, human capital, or knowledge create permanent growth?
             |
             +-- Yes -> Endogenous growth theory
```

## Memory Hooks

**Classical:** more output creates more people.

**Neoclassical:** more capital creates a higher level.

**Endogenous:** more knowledge creates a higher growth rate.

Or use:

```text
C = Children consume the gains
N = New steady-state level, not new long-run rate
E = Education, externalities, and endogenous technology
```

## Related Concepts

- [[CFA_Glossary/Economic growth]]
- [[Solow Model (Neoclassical Growth Theory)]]
- [[Level 2/Generated Notes/03 - Economics/Cobb-Douglas Production Function]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Level 2/Generated Notes/03 - Economics/Capital Deepening]]
- [[Labor productivity]]
- [[Potential GDP]]
- [[Human capital]]
- [[Conditional convergence]]
- [[Absolute convergence]]
- [[Club convergence]]
