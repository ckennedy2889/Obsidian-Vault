---
title: Callable and Putable Bond Value Relationships
subject: Fixed Income
tags: [CFA-L2, FixedIncome, EmbeddedOptions, CallableBonds, PutableBonds]
aliases: [callable bond value relationship, putable bond value relationship, embedded option value relationships]
---

# Callable and Putable Bond Value Relationships

## Core Formulas

Callable bond:

$$
\boxed{
V_{\text{callable}} = V_{\text{straight}} - V_{\text{call option}}
}
$$

Putable bond:

$$
\boxed{
V_{\text{putable}} = V_{\text{straight}} + V_{\text{put option}}
}
$$

## Ownership Of The Option

| Bond Type | Option Owner | Investor Position | Value Effect |
|---|---|---|---|
| Callable bond | Issuer | Investor is short the call | Worth less than straight bond |
| Putable bond | Investor | Investor is long the put | Worth more than straight bond |

## Mechanism

Callable bond:

```text
Rates fall
  |
  v
Straight bond price would rise
  |
  v
Issuer calls/refinances
  |
  v
Investor's upside is capped
```

Putable bond:

```text
Rates rise
  |
  v
Straight bond price would fall
  |
  v
Investor puts bond back
  |
  v
Investor's downside is floored
```

## Volatility Effect

Higher interest rate volatility increases the value of options.

| Volatility Rises | Option Value | Bond Value |
|---|---|---|
| Callable bond | Call option value rises | Callable bond value falls |
| Putable bond | Put option value rises | Putable bond value rises |

## Tree Valuation Rule

At each exercise node:

| Bond Type | Node Rule |
|---|---|
| Callable | $\min(\text{continuation value}, \text{call price})$ |
| Putable | $\max(\text{continuation value}, \text{put price})$ |

## OAS And Volatility

When assumed interest rate volatility rises:

| Bond Type | Model Option Effect | OAS Effect |
|---|---|---|
| Callable | Call value rises, model bond value falls | OAS decreases |
| Putable | Put value rises, model bond value rises | OAS increases |
| Option-free | No embedded option | OAS unchanged |

The total market spread did not necessarily change. The model is changing how much of the spread is attributed to optionality versus credit/liquidity compensation.

A common shorthand is:

$$
\text{OAS} = \text{Z-spread} - \text{Option cost}
$$

where the option cost is positive for callable bonds from the investor's perspective because the investor is short the issuer's call.

## Exam Traps

| Trap | Correction |
|---|---|
| Adding the call option to a callable bond | The issuer owns the call, so subtract it from investor value. |
| Subtracting the put option from a putable bond | The investor owns the put, so add it. |
| Thinking higher volatility helps all bonds | It helps long-option positions and hurts short-option positions. |
| Reversing tree min/max rules | Callable uses min; putable uses max from investor perspective. |
| Thinking lower OAS means less risk for callable bonds after volatility increases | It may just mean more spread is assigned to option cost. |
| Forgetting what option-adjusted means | OAS is the spread after removing the embedded option's modeled effect. |

## Related Concepts

- [[Callable bond]]
- [[Putable bond]]
- [[Backward Induction]]
- [[Option-Adjusted Spread]]
- [[Effective Duration]]
- [[Effective Convexity]]
- [[One-Sided Durations]]
