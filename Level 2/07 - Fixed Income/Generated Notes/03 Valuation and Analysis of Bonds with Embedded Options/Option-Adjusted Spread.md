---
title: Option-Adjusted Spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, oas, option-adjusted-spread, embedded-options, callable-bonds, putable-bonds, arbitrage-free-valuation]
aliases: [option-adjusted spread, OAS, option adjusted spread, option-adjusted spread (OAS)]
---

# Option-Adjusted Spread

## The Real-World Analogy

Imagine two apartments have the same rent, but one has a landlord who can kick you out early if market rents fall.

You would not compare the two rents directly because one contract has an embedded disadvantage.

You would ask:

```text
After adjusting for the landlord's option,
how much compensation am I really receiving for the apartment's location/quality risk?
```

That is what [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]] does for bonds.

A callable bond's observed spread includes compensation for:

```text
credit risk + liquidity risk + the issuer's call option
```

OAS tries to strip out the option part so we can compare the bond's pure compensation for credit and liquidity risk.

## Plain-English Definition

The option-adjusted spread, or OAS, is the spread over benchmark interest rates after adjusting for the value of an embedded option.

It answers:

```text
After accounting for the bond's call or put option,
what spread is the investor earning for credit/liquidity risk?
```

## CFA Definition

CFA defines OAS as the constant spread that, when added to all the one-period forward rates on an interest rate tree, makes the arbitrage-free value of the bond equal to its market price.

Key phrase:

```text
constant spread added to every node / one-period forward rate in the tree
```

## Why OAS Exists

For an option-free risky bond, [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]] works well because promised cash flows are fixed.

But for bonds with embedded options, cash flows depend on future interest rate paths.

Examples:

| Bond Type | Embedded Option | Who Owns It? | Why Cash Flows Change |
|---|---|---|---|
| [[Callable bond]] | Call option | Issuer | Issuer may redeem when rates fall |
| [[Putable bond]] | Put option | Bondholder | Investor may put bond back when rates rise |
| [[Convertible bond]] | Conversion option | Bondholder | Investor may convert into shares |

Because future cash flows are path-dependent, a static spot-curve spread is not enough. We need an interest rate tree and backward induction.

## OAS Calculation Logic

OAS is found by trial and error in an arbitrage-free framework.

The workflow:

```text
1. Build a benchmark interest rate tree.
2. Project the bond's cash flows through the tree.
3. Apply the embedded option rule at each node.
   - callable: issuer chooses min(value, call price)
   - putable: investor chooses max(value, put price)
4. Add a trial spread to every one-period forward rate.
5. Use backward induction to value the bond.
6. Adjust the spread until model value equals market price.
7. That spread is the OAS.
```

In formula form, the OAS is the spread such that:

$$
\text{Model value using benchmark tree + OAS + option exercise rules}
=
\text{Market price}
$$

There is usually no simple closed-form formula. The spread is estimated iteratively.

## Why The Spread Is Added After Option Adjustment

This point is very testable.

The tree valuation first handles the embedded option by applying the correct exercise rule at each node.

Then OAS is the spread left after that option effect is incorporated.

```text
Step 1: Value the option behavior in the tree.
Step 2: Add a spread so risky model value equals market price.
Step 3: Interpret that spread as credit/liquidity compensation after option adjustment.
```

That is why it is called option-adjusted.

## OAS vs Z-Spread

The [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]] adds a constant spread to the spot curve.

The OAS adds a constant spread to the one-period forward rates in an interest rate tree.

| Feature | Z-Spread | OAS |
|---|---|---|
| Framework | Spot curve | Binomial/interest rate tree |
| Handles path-dependent options? | No | Yes |
| Best for | Option-free risky bonds | Bonds with embedded options |
| Spread added to | Spot rates | One-period forward rates / tree nodes |
| Adjusts for option value? | No | Yes |

For an option-free bond:

$$
OAS \approx ZS
$$

because there is no embedded option to adjust for.

## Formula Relationship With Option Value

For a callable bond:

$$
OAS = ZS - \text{call option cost}
$$

Why?

The issuer owns the call option. That hurts the investor. The observed Z-spread includes compensation for giving the issuer that option. OAS removes that option compensation to isolate credit/liquidity spread.

So:

```text
Callable bond: Z-spread > OAS
```

For a putable bond:

$$
OAS = ZS + \text{put option value}
$$

Why?

The investor owns the put option. That benefits the investor. Because the investor is receiving an option, the bond can offer a lower observed Z-spread. OAS adds back the value of that investor-owned option to identify the comparable credit/liquidity spread.

So:

```text
Putable bond: OAS > Z-spread
```

## Worked Example 1: Callable Bond Spread Decomposition

Suppose:

- Callable bond Z-spread: $180$ bps
- Estimated call option cost: $40$ bps

Use:

$$
OAS = ZS - \text{call option cost}
$$

Substitute:

$$
OAS = 180 - 40
$$

$$
\boxed{OAS = 140 \text{ bps}}
$$

Interpretation:

```text
The total observed spread is 180 bps.
40 bps compensates the investor for the issuer's call option.
140 bps is the option-adjusted spread for credit/liquidity risk.
```

## Worked Example 2: Putable Bond Spread Decomposition

Suppose:

- Putable bond Z-spread: $100$ bps
- Estimated put option value: $25$ bps

Use:

$$
OAS = ZS + \text{put option value}
$$

Substitute:

$$
OAS = 100 + 25
$$

$$
\boxed{OAS = 125 \text{ bps}}
$$

Interpretation:

```text
The investor-owned put makes the bond more valuable.
The observed Z-spread is lower because the investor receives option value.
OAS adds back the option value to get a comparable credit/liquidity spread.
```

## Worked Example 3: Iterating To Find OAS

Suppose a risky callable bond trades at:

$$
P_{\text{market}} = 101.000
$$

An analyst values the bond in a benchmark interest rate tree using the call rule.

Try adding 30 bps to every node:

$$
\text{Model value} = 100.973
$$

This is below the market price.

Why?

The discount rates are too high. The spread is too high.

Try adding 28 bps:

$$
\text{Model value} = 101.010
$$

This is slightly above the market price.

So the correct OAS is between 28 and 30 bps.

Further iteration gives:

$$
\boxed{OAS = 28.55 \text{ bps}}
$$

## Interpreting OAS For Relative Value

OAS is used for relative value analysis.

If two bonds have similar:

- credit quality;
- maturity;
- coupon structure;
- embedded option features;
- benchmark curve;
- liquidity;
- model assumptions;

then they should have similar OAS.

Decision rule:

| OAS Relative To Comparable Bonds | Interpretation |
|---|---|
| Higher OAS | Bond may be cheap / underpriced |
| Lower OAS | Bond may be rich / overpriced |
| Similar OAS | Bond may be fairly priced |

But the comparison only works if the bonds are genuinely comparable.

A CCC bond with a higher OAS than a B-rated bond is not automatically cheap. The higher OAS may simply compensate for worse credit risk.

## Volatility Effect On OAS

This is one of the highest-yield exam traps.

Options become more valuable when interest rate volatility rises.

But the direction of OAS depends on who owns the option.

| Bond Type | Higher Assumed Interest Rate Volatility | Effect On Embedded Option | Effect On Computed OAS |
|---|---|---|---|
| Callable bond | Volatility rises | Issuer's call option becomes more valuable | OAS decreases |
| Putable bond | Volatility rises | Investor's put option becomes more valuable | OAS increases |
| Option-free bond | Volatility rises | No embedded option | OAS unchanged |

## Why Higher Volatility Lowers OAS For Callable Bonds

A callable bond can be viewed as:

$$
\text{Callable bond}
=
\text{Straight bond}
-
\text{Call option owned by issuer}
$$

When interest rate volatility rises:

```text
Call option value rises
        ↓
Callable bond model value falls
        ↓
Model value moves closer to a lower market price
        ↓
Less extra spread is needed to force model value down
        ↓
Computed OAS decreases
```

Important:

```text
This does not mean the bond became less risky.
It means more of the observed spread is being attributed to the embedded call option.
```

## Why Higher Volatility Raises OAS For Putable Bonds

A putable bond can be viewed as:

$$
\text{Putable bond}
=
\text{Straight bond}
+
\text{Put option owned by investor}
$$

When interest rate volatility rises:

```text
Put option value rises
        ↓
Putable bond model value rises
        ↓
Model value moves farther above a given market price
        ↓
More extra spread is needed to force model value down
        ↓
Computed OAS increases
```

## Assumptions And Limitations

OAS is powerful, but it is model-dependent.

Its quality depends on:

| Assumption | Why It Matters |
|---|---|
| Benchmark curve | Different benchmark curves can produce different OAS |
| Interest rate volatility | OAS changes with volatility assumptions |
| Interest rate model | Different trees/models can produce different option values |
| Exercise behavior | Assumes rational exercise at model nodes |
| Liquidity and taxes | These may still be mixed into the residual spread |
| Credit migration/default | Basic OAS may not fully model changing credit states |

Exam implication:

```text
OAS is not a pure truth number.
It is a model-implied spread.
```

## Common CFA Traps

| Trap | Correct Thinking |
|---|---|
| OAS is just the Z-spread | Only for option-free bonds or zero volatility |
| OAS is added to spot rates | Z-spread uses spot rates; OAS is added to one-period forward rates in the tree |
| Higher OAS always means better bond | Only compare OAS among similar bonds with similar credit/liquidity/model assumptions |
| Higher volatility raises OAS for all bonds | Callable OAS decreases; putable OAS increases |
| A lower OAS means lower risk | Not necessarily; it may reflect model assumptions or option value |
| OAS removes all risks except credit | It adjusts for options, but liquidity, tax, and model risk may remain |
| Callable bond OAS is greater than Z-spread | Usually false. Callable: Z-spread > OAS |
| Putable bond OAS is less than Z-spread | Usually false. Putable: OAS > Z-spread |

## Memory Hooks

```text
OAS = Option effect stripped away.
```

```text
Callable: issuer owns option -> ZS > OAS.
Putable: investor owns option -> OAS > ZS.
```

```text
Vol up:
Callable OAS down.
Putable OAS up.
```

## Exam-Day Checklist

When a vignette mentions OAS, ask:

1. Is the bond callable, putable, convertible, or option-free?
2. Who owns the embedded option?
3. Is the spread being added to a spot curve or to one-period forward rates in a tree?
4. Are you comparing OAS only among similar bonds?
5. Did the volatility assumption change?
6. For callable bonds, did higher volatility lower computed OAS?
7. For putable bonds, did higher volatility raise computed OAS?
8. Is the question asking about pure spread, option value, or relative cheapness?

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]]
- [[G-spread]]
- [[I-spread]]
- [[Callable bond]]
- [[Putable bond]]
- [[Embedded option]]
- [[Binomial Interest Rate Tree]]
- [[Backward Induction]]
- [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]]
- [[Credit risk]]
- [[Liquidity risk]]
