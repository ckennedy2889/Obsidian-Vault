---
title: Potential GDP vs Real GDP and Interest Rate Implications
subject: Economics
tags: [CFA-L2, economics, macroeconomics, potential-gdp, real-gdp, output-gap, interest-rates, monetary-policy, fixed-income, equity]
aliases: [potential GDP vs real GDP, actual GDP vs potential GDP, real GDP and interest rates, potential GDP and interest rates, GDP gap and rates]
---

# Potential GDP vs Real GDP and Interest Rate Implications

## The Big Intuition

Think of an economy as a factory.

[[Potential GDP]] is the factory's sustainable production capacity. It is how much the factory can produce if workers, machines, technology, and infrastructure are used at a normal sustainable pace.

[[Real GDP]] is what the factory actually produced this period, measured in constant purchasing-power terms.

The interest-rate question is:

```text
Is actual production above, below, or equal to sustainable production?
```

That difference determines whether the economy has inflation pressure or slack.

```text
Actual real GDP above potential GDP
        ↓
Economy is overheating
        ↓
Inflation pressure rises
        ↓
Central bank more likely raises rates

Actual real GDP below potential GDP
        ↓
Economy has slack
        ↓
Inflation pressure weakens
        ↓
Central bank more likely cuts rates
```

## Definitions

### Real GDP

[[Real GDP]] is the value of goods and services produced, measured using base-year prices.

The reason economists use real GDP instead of nominal GDP is that nominal GDP mixes two things:

```text
Nominal GDP growth = real output growth + inflation effect
```

If nominal GDP rises because prices rose, the economy did not necessarily produce more real goods and services. [[Real GDP]] strips out inflation so we can focus on actual output.

### Potential GDP

[[Potential GDP]] is the maximum amount of output an economy can sustainably produce without inducing an increase in the [[Inflation rate]].

It is tied to:

| Driver | Why It Matters |
|---|---|
| [[Labor force]] | More workers increase sustainable production capacity |
| [[Level 2/Generated Notes/03 - Economics/Capital Stock]] | More machines, buildings, software, and infrastructure raise productive capacity |
| [[Human capital]] | Better education, skills, and health raise worker productivity |
| [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]] | Better technology and organization allow more output from the same inputs |
| Institutions | Property rights, financial markets, rule of law, and openness support long-run growth |

Potential GDP is not the absolute physical maximum output. An economy can temporarily produce above potential by forcing overtime, running machines harder, drawing marginal workers into employment, and bidding aggressively for scarce resources.

But that creates pressure.

```text
Above potential is possible temporarily.
Above potential is not sustainable without inflation pressure.
```

## The Key Relationship: Output Gap

The [[Level 2/Generated Notes/03 - Economics/Output Gap]] is the difference between actual real GDP and potential GDP.

$$
\text{Output gap} = Y - Y^*
$$

As a percentage:

$$
\text{Output gap \%} = \frac{Y - Y^*}{Y^*}
$$

Where:

| Symbol | Meaning |
|---|---|
| $Y$ | Actual [[Real GDP]] |
| $Y^*$ | [[Potential GDP]] |
| $Y - Y^*$ | [[Level 2/Generated Notes/03 - Economics/Output Gap]] |

The sign matters:

| Condition | Name | Meaning |
|---|---|---|
| $Y > Y^*$ | Positive output gap | Economy is above sustainable capacity |
| $Y = Y^*$ | Zero output gap | Economy is near sustainable capacity |
| $Y < Y^*$ | Negative output gap | Economy is below sustainable capacity |

## Two Different Interest Rate Channels

CFA wants you to separate two channels:

```text
Long-run channel:
Potential GDP growth affects equilibrium real interest rates.

Short-run channel:
Actual GDP relative to potential GDP affects inflation pressure and monetary policy.
```

This is the whole note.

## Channel 1: Potential GDP Growth And Real Interest Rates

Higher expected [[Potential GDP]] growth tends to imply higher equilibrium [[Real interest rate|real interest rates]].

Why?

If an economy is expected to grow faster over the long run, households and firms expect future income to be higher. If people expect to be richer tomorrow, they are less eager to save today. To persuade them to defer consumption, the economy needs a higher real return.

From an investment perspective, faster sustainable growth also creates more attractive capital investment opportunities. Firms want funds to build factories, buy equipment, develop technology, and expand capacity. Stronger investment demand also pushes real rates higher.

Mechanism:

```text
Higher potential GDP growth
        ↓
Higher expected future real income
        ↓
Less desire to save today / more desire to invest today
        ↓
Higher equilibrium real interest rate
        ↓
Higher required real returns on assets
```

So in CFA language:

```text
Faster potential GDP growth → higher real rates and higher expected real asset returns.
Slower potential GDP growth → lower real rates and lower expected real asset returns.
```

This is a long-run relationship. It is not about whether the central bank hikes next meeting. It is about the sustainable real rate environment.

## Channel 2: Actual GDP vs Potential GDP And Policy Rates

Short-run rate moves depend heavily on the [[Level 2/Generated Notes/03 - Economics/Output Gap]].

If actual GDP is above potential GDP, the economy is using resources beyond sustainable capacity. That usually creates inflation pressure.

```text
Y > Y^*
        ↓
Positive output gap
        ↓
Inflation pressure rises
        ↓
Central bank tightens
        ↓
Short-term nominal rates rise
```

If actual GDP is below potential GDP, the economy has slack.

```text
Y < Y^*
        ↓
Negative output gap
        ↓
Inflation pressure weakens
        ↓
Central bank eases
        ↓
Short-term nominal rates fall
```

## Positive Output Gap: Rate Implications

A positive output gap means:

$$
Y > Y^*
$$

The economy is producing above sustainable capacity.

Real-world signs:

| Area | What You See |
|---|---|
| Labor market | Low unemployment, labor shortages, wage pressure |
| Firms | High capacity utilization, backlogs, pricing power |
| Consumers | Strong demand and willingness to absorb higher prices |
| Inflation | High or rising inflation |
| Central bank | Bias toward tighter policy |

Interest-rate implications:

| Rate / Market | Likely Direction | Why |
|---|---|---|
| Short-term policy rate | Up | Central bank tightens to cool inflation |
| Short-term nominal yields | Up | Closely tied to expected policy path |
| Long-term nominal yields | Often up, but depends on growth/inflation expectations | Higher inflation expectations and term premia can lift long yields |
| Real rates | Can rise | Tighter monetary policy raises real borrowing costs |
| Bond prices | Down | Bond prices move inversely to yields |

Exam phrase:

```text
Positive output gap = overheating = inflation pressure = tighter policy = upward pressure on rates.
```

## Negative Output Gap: Rate Implications

A negative output gap means:

$$
Y < Y^*
$$

The economy is producing below sustainable capacity.

Real-world signs:

| Area | What You See |
|---|---|
| Labor market | Higher unemployment, weak wage growth |
| Firms | Idle capacity, lower investment, discounting |
| Consumers | Weak demand, cautious spending |
| Inflation | Low or falling inflation pressure |
| Central bank | Bias toward easier policy |

Interest-rate implications:

| Rate / Market | Likely Direction | Why |
|---|---|---|
| Short-term policy rate | Down | Central bank eases to stimulate demand |
| Short-term nominal yields | Down | Expected policy path falls |
| Long-term nominal yields | Often down | Lower expected inflation and weaker growth |
| Real rates | Can fall | Easier policy reduces real borrowing costs |
| Bond prices | Up | Falling yields raise bond prices |

Exam phrase:

```text
Negative output gap = slack = unemployment pressure = easier policy = downward pressure on rates.
```

## Taylor Rule Link

The [[Taylor Rule]] formalizes how central banks may respond to inflation and output gaps.

One CFA-style version is:

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

Read it mechanically:

| Gap | Effect on Taylor Rule Rate |
|---|---|
| Inflation above target | Raises policy rate |
| Inflation below target | Lowers policy rate |
| Positive output gap | Raises policy rate |
| Negative output gap | Lowers policy rate |

So the output gap directly enters the policy-rate decision.

## Worked Example 1: Output Gap And Rates

Suppose:

- Actual real GDP: $22.0$ trillion
- Potential GDP: $21.5$ trillion

$$
\text{Output gap \%} = \frac{22.0 - 21.5}{21.5}
$$

$$
= \frac{0.5}{21.5}
$$

$$
= 0.0233 = 2.33\%
$$

The economy has a positive output gap of about 2.3%.

Interpretation:

```text
Actual output is above sustainable output.
The economy is overheating.
Inflation pressure is likely rising.
The central bank is more likely to raise rates.
Bond prices face downward pressure.
```

## Worked Example 2: Taylor Rule

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

Why so high?

The central bank is responding to both:

1. Inflation above target.
2. Actual GDP above potential GDP.

Both signals point toward tighter policy.

## Worked Example 3: Potential Growth And Real Rates

Suppose Country A has expected potential GDP growth of 1%, while Country B has expected potential GDP growth of 4%.

All else equal, Country B should tend to have a higher equilibrium real interest rate.

Why?

```text
Higher sustainable growth
        ↓
Higher expected future income
        ↓
Greater investment demand and less need to save today
        ↓
Higher real rate needed to balance saving and investment
```

This does not mean Country B's bonds always have higher realized returns. Higher rates can mean lower current bond prices, different inflation expectations, different currency risk, and different credit risk. The CFA point is narrower:

```text
Potential GDP growth is a long-run determinant of real interest rates.
```

## Bond Market Implications

For [[Fixed Income]], separate the level of rates from price movement.

| Macro Signal | Rate Implication | Bond Price Implication |
|---|---|---|
| Higher potential GDP growth | Higher long-run real rates | Lower bond valuations, all else equal |
| Lower potential GDP growth | Lower long-run real rates | Higher bond valuations, all else equal |
| Positive output gap | Higher expected policy rates | Bond prices pressured lower |
| Negative output gap | Lower expected policy rates | Bond prices supported higher |
| Actual GDP growth below potential growth | Slack likely increasing | Lower inflation pressure, easier policy, bonds may rise |
| Actual GDP growth above potential growth | Inflation pressure likely increasing | Tighter policy, bonds may fall |

Important nuance:

```text
Bond prices respond to surprises relative to expectations.
```

If markets already expected a central bank hike, the hike may not move bond prices much. The price moves when the actual or expected path of rates changes relative to what was priced.

## Equity Market Implications

For [[Equity]], GDP affects both expected cash flows and discount rates.

Potential GDP matters because long-run earnings growth cannot sustainably exceed potential GDP growth forever. If corporate earnings grew faster than the economy forever, corporate profits would eventually become an impossible share of GDP.

Actual GDP matters because it affects the cycle.

| Scenario | Cash Flow Effect | Discount Rate Effect | Equity Implication |
|---|---|---|---|
| Higher potential GDP growth | Better long-run earnings capacity | Higher real rates may raise discount rates | Usually supportive, but valuation impact is mixed |
| Positive output gap | Strong near-term sales | Higher rates and inflation pressure | Earnings up, multiples may compress |
| Negative output gap | Weak near-term earnings | Lower rates may support valuations | Defensive sectors may outperform |
| Negative gap closing | Earnings recovery | Rates may remain supportive early | Cyclicals may perform well |

The core equity tension:

```text
Good growth helps cash flows.
But if growth is too strong relative to potential, it can raise rates and hurt valuation multiples.
```

That is why a strong GDP report can sometimes cause stocks to fall: investors may infer more inflation and tighter policy.

## Real GDP Growth vs Potential GDP Growth

Do not confuse the level gap with the growth-rate comparison.

| Comparison | Question Answered |
|---|---|
| $Y$ versus $Y^*$ | Is the economy above or below sustainable capacity? |
| Growth in $Y$ versus growth in $Y^*$ | Is the output gap likely widening or closing? |

Example:

Suppose actual GDP is below potential GDP, so the economy has a negative output gap. If actual GDP grows 4% while potential GDP grows 2%, the output gap is closing.

That does not necessarily mean the economy is overheating.

```text
High actual GDP growth can simply mean recovery from a depressed level.
```

Exam trap:

```text
Actual growth above potential growth means the gap is closing or becoming more positive.
It does not automatically mean actual GDP is already above potential GDP.
```

## Scenario Table

| Scenario | Actual GDP vs Potential GDP | Interest Rate Implication | Asset Implication |
|---|---|---|---|
| Economy below potential and weakening | $Y < Y^*$, gap widening negative | Rates likely down | High-quality bonds supported; equities pressured by earnings |
| Economy below potential but recovering | $Y < Y^*$, gap narrowing | Rates may stay low then rise later | Cyclicals may improve |
| Economy at potential | $Y \approx Y^*$ | Policy near neutral, all else equal | Valuations depend on earnings, inflation, and risk premia |
| Economy above potential | $Y > Y^*$ | Rates likely up | Bonds pressured; equities face multiple compression risk |
| Potential GDP growth rises | $Y^*$ growth higher | Long-run real rates higher | Better earnings capacity but higher discount rates |
| Potential GDP growth falls | $Y^*$ growth lower | Long-run real rates lower | Lower long-run earnings growth, lower real discount rates |

## Common CFA Traps

| Trap | Correct Thinking |
|---|---|
| Real GDP and potential GDP are the same | Real GDP is actual output; potential GDP is sustainable capacity |
| Potential GDP is maximum possible output | It is maximum sustainable output without accelerating inflation |
| High real GDP growth always means higher rates | Only if it creates inflation pressure or changes policy expectations |
| Actual GDP growth above potential growth means positive output gap | Not necessarily. The gap may just be closing from negative |
| Higher potential GDP growth always means bond prices rise | Higher potential growth tends to raise real rates, which can pressure bond prices |
| Lower rates are always good for equities | Lower rates may reflect weak growth and falling earnings |
| Positive output gap is good for equities | It can boost revenues, but rates and inflation can compress multiples |
| Potential GDP is observable | It is estimated using labor, capital, productivity, and trend methods |

## Memory Hooks

```text
Potential GDP = sustainable speed limit.
Real GDP = current speed.
Output gap = speeding or crawling.
```

For rates:

```text
Long run:
Higher potential growth → higher real rates.

Short run:
Real GDP above potential → inflation pressure → policy rates up.
Real GDP below potential → slack → policy rates down.
```

## Exam-Day Checklist

When a vignette gives GDP and rates, ask:

1. Is the question about actual [[Real GDP]] or [[Potential GDP]]?
2. Is it asking about the level of GDP or the growth rate?
3. Is actual GDP above or below potential GDP?
4. Is the output gap widening or closing?
5. Does the scenario imply rising or falling inflation pressure?
6. What should the central bank do to the [[Policy rate]]?
7. What happens to bond prices if yields move?
8. For equities, is the main effect on cash flows, discount rates, or both?

## Related Concepts

- [[Potential GDP]]
- [[Real GDP]]
- [[Level 2/Generated Notes/03 - Economics/Output Gap]]
- [[Inflation]]
- [[Real interest rate]]
- [[Nominal interest rate]]
- [[Policy rate]]
- [[Taylor Rule]]
- [[Monetary Policy]]
- [[Fixed Income]]
- [[Equity]]
- [[Growth Accounting]]
- [[Level 2/Generated Notes/03 - Economics/Total Factor Productivity (TFP)]]
- [[Level 2/Generated Notes/03 - Economics/Capital Stock]]
- [[Labor force]]
