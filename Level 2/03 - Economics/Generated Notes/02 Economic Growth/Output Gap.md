---
title: Output Gap
subject: Economics
tags: [CFA-L2, economics, macroeconomics, output-gap, potential-gdp, inflation, monetary-policy, taylor-rule]
aliases: [output gap, positive output gap, negative output gap, GDP gap, slack in the economy]
---

# Output Gap

## The Real-World Analogy

Think of the economy as a marathon runner.

[[Potential GDP]] is the runner's sustainable pace. It is not the fastest sprint the runner can possibly do for 30 seconds. It is the pace the runner can maintain without overheating, collapsing, or damaging the body.

[[Actual GDP]] is the runner's current pace.

The [[Level 2/Generated Notes/03 - Economics/Output Gap]] asks:

```text
Is the economy running faster or slower than its sustainable pace?
```

If actual output is above potential output, the economy is sprinting too hard. Demand is stretching labor, factories, transportation networks, and materials beyond sustainable capacity. That usually creates [[Inflation]] pressure.

If actual output is below potential output, the economy is underusing its capacity. Workers are unemployed, factories have idle equipment, and firms have less pricing power. That usually creates disinflationary pressure and weaker growth.

## Core Definition

The [[Level 2/Generated Notes/03 - Economics/Output Gap]] is the difference between actual real GDP and potential GDP.

In level form:

$$
\text{Output gap} = Y - Y^*
$$

As a percentage of potential GDP:

$$
\text{Output gap \%} = \frac{Y - Y^*}{Y^*}
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | [[Actual GDP]] / actual real output |
| $Y^*$ | [[Potential GDP]] / sustainable real output |
| $Y - Y^*$ | Output gap |

In the [[Taylor Rule]], CFA often treats the output gap as the difference between the logarithmic levels of actual and potential real GDP:

$$
Y_t - Y_t^*
$$

This is essentially a percentage gap.

## Why Potential GDP Is The Anchor

[[Potential GDP]] is the maximum amount of output an economy can sustainably produce without inducing an increase in the [[Inflation rate]].

That wording matters. Potential GDP is not "the most output physically possible." An economy can temporarily produce above potential by using overtime, running machines harder, delaying maintenance, pulling marginal workers into employment, and bidding aggressively for scarce resources.

But that above-potential output is not sustainable because it strains capacity.

```text
Above potential = possible temporarily
Above potential forever = not sustainable
```

The mechanism is:

```text
Actual GDP rises above potential GDP
        ↓
Economy needs more labor and inputs than normal capacity allows
        ↓
Firms compete for workers, materials, shipping, energy, and equipment
        ↓
Wages and input costs rise
        ↓
Firms raise prices
        ↓
Inflation pressure increases
```

## Three Output Gap States

| State | Formula | Plain English | Typical Macro Signal |
|---|---:|---|---|
| Positive output gap | $Y > Y^*$ | Economy is producing above sustainable capacity | Overheating, inflation pressure |
| Zero output gap | $Y = Y^*$ | Economy is near sustainable capacity | Stable inflation, neutral-ish policy |
| Negative output gap | $Y < Y^*$ | Economy is producing below sustainable capacity | Slack, unemployment pressure |

## Positive Output Gap

A positive output gap means:

$$
Y > Y^*
$$

The economy is producing more than its sustainable capacity.

At first, this can look attractive: growth is strong, firms are busy, unemployment is low, and revenues are rising. But the problem is that the economy is using resources too intensely.

Real-world signs:

| Area | What You See |
|---|---|
| Labor market | Very low unemployment, labor shortages, overtime, wage pressure |
| Firms | High capacity utilization, backlogs, strong pricing power |
| Consumers | Strong demand, willingness to pay higher prices |
| Supply chains | Bottlenecks, delivery delays, input shortages |
| Inflation | High and/or rising inflation |
| Central bank | More likely to tighten [[Monetary Policy]] |

### Why Inflation Rises

Inflation rises because demand is pressing against a supply ceiling.

Suppose consumers want more cars than the economy can sustainably produce. Auto manufacturers need more steel, chips, workers, transport capacity, and factory time. If those resources are scarce, firms bid against each other. Workers demand higher wages, suppliers raise prices, and final goods prices rise.

This is demand-pull inflation.

```text
Too much demand relative to sustainable supply
        ↓
Resource scarcity
        ↓
Wages/input costs rise
        ↓
Firms raise prices
        ↓
Inflation accelerates
```

### Policy Implication

For the central bank, a positive output gap usually argues for higher policy rates.

Higher rates cool the economy by making borrowing more expensive, reducing interest-sensitive spending, slowing credit creation, and weakening demand.

```text
Positive output gap
        ↓
Inflation pressure
        ↓
Central bank tightens
        ↓
Short-term rates rise
        ↓
Bond prices face pressure
```

## Negative Output Gap

A negative output gap means:

$$
Y < Y^*
$$

The economy is producing less than it sustainably could.

This is economic slack.

Real-world signs:

| Area | What You See |
|---|---|
| Labor market | High unemployment, weak wage growth, discouraged workers |
| Firms | Idle factories, fewer shifts, weak order books |
| Consumers | Weak spending, higher saving, cautious behavior |
| Businesses | Lower investment, discounting, margin pressure |
| Inflation | Low, falling, or subdued inflation pressure |
| Central bank | More likely to ease [[Monetary Policy]] |

### Why Inflation Falls

Inflation pressure falls because firms have unused capacity and weak demand.

If restaurants have empty tables, hotels have vacant rooms, factories have idle machines, and unemployed workers are looking for jobs, firms do not have much pricing power. They may discount to attract demand. Workers have less bargaining power, so wage pressure weakens.

```text
Demand below sustainable supply
        ↓
Idle labor and capital
        ↓
Weak wage and pricing power
        ↓
Lower inflation pressure
        ↓
Central bank may cut rates
```

## Zero Output Gap

A zero output gap means:

$$
Y = Y^*
$$

The economy is producing near sustainable capacity.

This does not mean unemployment is zero. It means unemployment is around its natural or equilibrium level, with normal job search, normal labor turnover, and some structural mismatch.

| Misinterpretation | Correct Interpretation |
|---|---|
| Zero output gap means no unemployment | False. It means unemployment is near its natural rate |
| Zero output gap means no inflation | False. It means inflation is not accelerating because of excess demand |
| Potential GDP is fixed | False. Potential GDP changes with labor, capital, technology, and productivity |

## Worked Example 1: Positive Output Gap

Suppose:

- Actual real GDP: $22.0$ trillion
- Potential GDP: $21.5$ trillion

Use:

$$
\text{Output gap \%} = \frac{Y - Y^*}{Y^*}
$$

Substitute:

$$
\text{Output gap \%} = \frac{22.0 - 21.5}{21.5}
$$

Calculate:

$$
= \frac{0.5}{21.5}
$$

$$
= 0.0233 = 2.33\%
$$

Conclusion:

$$
\boxed{\text{Output gap} \approx +2.3\%}
$$

Interpretation:

```text
Actual GDP is 2.3% above sustainable output.
The economy is likely overheating.
Inflation pressure is likely rising.
Central bank policy is more likely to tighten.
```

## Worked Example 2: Negative Output Gap

Suppose:

- Actual real GDP: $20.8$ trillion
- Potential GDP: $21.5$ trillion

$$
\text{Output gap \%} = \frac{20.8 - 21.5}{21.5}
$$

$$
= \frac{-0.7}{21.5}
$$

$$
= -0.0326 = -3.26\%
$$

Conclusion:

$$
\boxed{\text{Output gap} \approx -3.3\%}
$$

Interpretation:

```text
Actual GDP is 3.3% below sustainable output.
The economy has slack.
Unemployment is likely elevated.
Inflation pressure is likely weak.
Central bank policy is more likely to ease.
```

## Real-World Scenarios

| Scenario | Output Gap | What Is Happening | Likely Implication |
|---|---:|---|---|
| Deep recession | Negative and wide | Demand collapses, unemployment rises, factories idle | Rate cuts, fiscal stimulus, weaker earnings |
| Early recovery | Negative but closing | Growth improves from a depressed base | Cyclical assets may recover; disinflation pressure fades |
| Mid-cycle expansion | Near zero | Economy grows around potential | Stable inflation, neutral policy |
| Late-cycle boom | Positive and widening | Demand exceeds sustainable capacity | Inflation pressure, rate hikes, valuation risk |
| Supply shock | Mixed; potential GDP may fall | Energy, labor, or supply constraints reduce capacity | Inflation can rise even with weak growth |
| Productivity boom | Gap may shrink even with strong growth | Potential GDP rises because economy can produce more | Stronger growth with less inflation pressure |
| Immigration/labor force increase | Potential GDP rises | More workers increase capacity | Can worsen unemployment if demand does not rise too |

## Scenario 1: Recession

In a recession, actual GDP falls below potential GDP.

```text
Weak demand
        ↓
Lower production
        ↓
Layoffs and idle capacity
        ↓
Negative output gap
        ↓
Lower inflation pressure
        ↓
Central bank cuts rates
```

For [[Fixed Income]], this can be favorable for high-quality bonds because policy rates may fall and bond prices may rise.

For [[Equity]], the picture is mixed. Lower rates help valuations, but falling earnings hurt cash flows. Early in recessions, the earnings hit often dominates. Later, equities may recover if investors anticipate policy easing and future growth.

## Scenario 2: Early Recovery

In an early recovery, the output gap is often still negative, but it is narrowing.

This distinction is important.

High GDP growth does not automatically mean a positive output gap. If the economy fell far below potential, it can grow quickly while still operating below capacity.

```text
Actual GDP growth is strong
        ↓
But actual GDP remains below potential GDP
        ↓
Negative output gap is closing
        ↓
Inflation pressure may remain contained at first
```

Exam trap:

```text
High growth rate does not always mean overheating.
Ask whether the level of GDP is above or below potential GDP.
```

## Scenario 3: Late-Cycle Overheating

Late in an expansion, the output gap may become positive.

Firms are busy, unemployment is low, wages rise, and input costs rise. This can support revenues at first, but it also puts pressure on margins and pushes central banks toward tightening.

For equities:

```text
Strong revenues
        ↓
But rising wages, input costs, and discount rates
        ↓
Margins and valuation multiples face pressure
```

For bonds:

```text
Positive output gap
        ↓
Higher expected inflation and policy rates
        ↓
Yields rise
        ↓
Bond prices fall
```

## Scenario 4: Supply Shock

Supply shocks are tricky because inflation can rise even if demand is not strong.

Suppose oil prices spike or supply chains break. The economy's sustainable capacity may fall because production becomes more expensive or physically harder to complete.

```text
Supply capacity falls
        ↓
Potential GDP falls
        ↓
Inflation rises
        ↓
Actual GDP may also weaken
```

This is why inflation is not always caused by a positive demand-driven output gap. CFA questions may try to make you over-apply the simple rule.

The clean rule is:

```text
Positive demand gap → inflation pressure from excess demand.
Negative demand gap → disinflation pressure from slack.
Supply shock → inflation may rise even with weak output.
```

## Output Gap And The Taylor Rule

The [[Taylor Rule]] links the policy rate to the inflation gap and the output gap.

A common CFA version is:

$$
pr_t = l_t + \pi_t + 0.5(\pi_t - \pi_t^*) + 0.5(Y_t - Y_t^*)
$$

Where:

| Term | Meaning |
|---|---|
| $pr_t$ | Policy rate |
| $l_t$ | Neutral real short-term rate |
| $\pi_t$ | Current inflation |
| $\pi_t^*$ | Target inflation |
| $\pi_t - \pi_t^*$ | Inflation gap |
| $Y_t - Y_t^*$ | Output gap |

Decision rule:

| Situation | Taylor Rule Effect | Policy Meaning |
|---|---|---|
| Inflation above target | Raises policy rate | Tighten |
| Inflation below target | Lowers policy rate | Ease |
| Positive output gap | Raises policy rate | Cool overheating |
| Negative output gap | Lowers policy rate | Stimulate slack economy |

### Worked Example 3: Taylor Rule

Suppose:

- Neutral real rate: $l_t = 2.0\%$
- Current inflation: $\pi_t = 3.0\%$
- Target inflation: $\pi_t^* = 2.0\%$
- Output gap: $Y_t - Y_t^* = 2.0\%$

Use:

$$
pr_t = l_t + \pi_t + 0.5(\pi_t - \pi_t^*) + 0.5(Y_t - Y_t^*)
$$

Substitute:

$$
pr_t = 2.0 + 3.0 + 0.5(3.0 - 2.0) + 0.5(2.0)
$$

Calculate:

$$
pr_t = 2.0 + 3.0 + 0.5 + 1.0
$$

$$
\boxed{pr_t = 6.5\%}
$$

Interpretation:

The economy has both above-target inflation and a positive output gap, so the Taylor Rule recommends a policy rate above the neutral nominal rate.

## Investor Implications

### Fixed Income

The output gap helps investors forecast [[Inflation]], [[Monetary Policy]], and [[Bond]] prices.

| Output Gap Condition | Inflation Pressure | Policy Rate Bias | Bond Price Bias |
|---|---|---|---|
| Positive gap | Upward | Higher rates | Downward pressure |
| Negative gap | Downward | Lower rates | Upward pressure |
| Gap closing from negative | Less disinflationary | Less easing / eventual tightening | Depends on expectations |
| Gap widening positive | More inflationary | More tightening | Strong downward pressure |

CFA Economics explicitly connects sluggish actual GDP growth relative to [[Potential GDP]] growth with a growing output gap, lower inflation pressure, easier policy, and potentially higher fixed-income prices.

### Equity

For equities, the output gap affects both cash flows and discount rates.

| Scenario | Cash Flow Effect | Discount Rate Effect | Equity Interpretation |
|---|---|---|---|
| Negative gap widening | Earnings weaken | Rates may fall | Defensive sectors may hold up better |
| Negative gap closing | Earnings recover | Rates may remain supportive | Cyclicals can benefit |
| Positive gap | Revenues strong | Rates rise | Earnings strong but multiples may compress |
| Overheating | Margins pressured by wages/input costs | Rates rise further | Late-cycle risk increases |

The subtle point:

```text
Output gap affects equities through both numerator and denominator.
Numerator = expected cash flows.
Denominator = discount rates and risk premiums.
```

That is why a strong economy can sometimes hurt equities if the market expects aggressive central bank tightening.

## Fiscal Policy Implications

The output gap also affects government budgets.

During recessions, government deficits often increase because tax revenue falls and spending on unemployment support rises.

During expansions, deficits often shrink because incomes, profits, and tax receipts rise.

This is why analysts distinguish between:

| Fiscal Measure | Meaning |
|---|---|
| Actual budget deficit | Deficit observed at current actual GDP |
| Structural / cyclically adjusted deficit | Deficit estimated as if the economy were operating at potential GDP |

Exam implication:

```text
A large actual deficit during a recession may partly reflect a negative output gap,
not only loose discretionary fiscal policy.
```

## Decision Tree

```text
Start: Compare actual GDP to potential GDP.

If actual GDP > potential GDP:
    Output gap is positive.
    Economy is above sustainable capacity.
    Inflation pressure likely rises.
    Central bank more likely tightens.
    Short rates likely rise.

If actual GDP < potential GDP:
    Output gap is negative.
    Economy has slack.
    Unemployment likely elevated.
    Inflation pressure likely falls.
    Central bank more likely eases.
    Short rates likely fall.

If actual GDP = potential GDP:
    Output gap is near zero.
    Economy is near sustainable capacity.
    Inflation pressure from demand is stable.
    Policy rate may be near neutral.
```

## Common CFA Traps

| Trap | Correct Thinking |
|---|---|
| Positive output gap is always good | It may signal strong demand, but it also signals overheating and inflation pressure |
| Negative output gap means potential GDP fell | Not necessarily. Actual GDP may have fallen below potential |
| High GDP growth means positive gap | False. A depressed economy can grow quickly while still below potential |
| Zero output gap means zero unemployment | False. It means unemployment is near the natural/equilibrium rate |
| Potential GDP is directly observed | False. It is estimated from labor, capital, productivity, and capacity |
| Potential GDP means maximum possible output | More precisely, maximum sustainable output without accelerating inflation |
| Inflation only rises with positive gaps | Usually for demand-driven inflation, but supply shocks can raise inflation too |
| Output gap determines all asset returns | It matters, but expectations, risk premiums, and starting valuations matter too |

## Memory Hooks

```text
Gap up = too hot = inflation up = rates up.
Gap down = too cold = unemployment up = rates down.
```

Another version:

```text
Positive gap: factories sweating.
Negative gap: factories sleeping.
Zero gap: factories operating sustainably.
```

## Exam-Day Checklist

When a vignette mentions actual GDP, potential GDP, inflation, unemployment, or central bank policy, ask:

1. Is actual GDP above or below potential GDP?
2. Is the gap positive, negative, or near zero?
3. Is the gap widening or closing?
4. What does that imply for inflation pressure?
5. What does that imply for unemployment?
6. What does that imply for the central bank's policy rate?
7. What does that imply for [[Fixed Income]] prices, [[Equity]] cash flows, and valuation multiples?

## Related Concepts

- [[Potential GDP]]
- [[Actual GDP]]
- [[Inflation]]
- [[Monetary Policy]]
- [[Fiscal Policy]]
- [[Taylor Rule]]
- [[Policy rate]]
- [[Neutral Real Rate]]
- [[Business Cycle]]
- [[CFA_Glossary/Economic growth]]
- [[Growth Accounting]]
- [[Fixed Income]]
- [[Equity]]
