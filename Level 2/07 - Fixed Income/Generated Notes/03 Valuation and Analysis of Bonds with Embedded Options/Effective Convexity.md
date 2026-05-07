---
title: Effective Convexity
subject: Fixed Income
tags: [CFA-L2, fixed-income, effective-convexity, convexity, embedded-options, callable-bonds, putable-bonds, interest-rate-risk]
aliases: [effective convexity, curve convexity, option-adjusted convexity, effective convexity of callable bond, effective convexity of putable bond]
---

# Effective Convexity

## The Real-World Analogy

[[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] tells you the bond's first reaction to an interest rate move.

Think of it like speed.

[[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] tells you how that reaction itself changes as rates move.

Think of it like acceleration.

If duration says:

```text
For a small rate move, price should move by about this much.
```

Then convexity says:

```text
For a bigger rate move, that straight-line estimate bends.
```

That bend matters a lot for bonds with embedded options, because the bond may stop behaving like a normal bond once the option moves closer to being exercised.

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] measures the curvature in a bond's price response to a change in the benchmark yield curve, allowing expected cash flows to change as interest rates change.

In simpler language:

```text
Effective convexity measures how much effective duration changes
when interest rates move.
```

This is why the glossary definition says effective convexity is the sensitivity of duration to changes in interest rates.

## Why Convexity Exists

Duration is a linear approximation.

It draws a straight line tangent to the bond's price-yield curve.

But actual bond prices do not move in a perfectly straight line when rates change.

For a normal option-free bond:

```text
Rates fall -> price rises more than duration alone predicts.
Rates rise -> price falls less than duration alone predicts.
```

That is positive convexity.

Positive convexity is good for the investor because it gives a better upside/downside tradeoff:

| Rate Move | Duration-Only Estimate | Effect of Positive Convexity |
|---|---|---|
| Rates fall | Price rises | Actual price rises more |
| Rates rise | Price falls | Actual price falls less |

But with embedded options, convexity can change dramatically because cash flows are not fixed.

## The Formula

The CFA formula for effective convexity is:

$$
\text{EffCon}
=\frac{PV_- + PV_+ - 2PV_0}{(\Delta\text{Curve})^2 \times PV_0}
$$

Where:

| Term | Meaning |
|---|---|
| $PV_-$ | Bond value after shifting the benchmark curve down |
| $PV_+$ | Bond value after shifting the benchmark curve up |
| $PV_0$ | Current bond value |
| $\Delta\text{Curve}$ | Size of the parallel curve shift, expressed as a decimal |

Notice the structure:

```text
PV_- + PV_+ - 2PV_0
```

That expression asks whether the average of the two shocked prices sits above or below the current price.

If the shocked prices average out above the current price, convexity is positive.

If the shocked prices average out below the current price, convexity is negative.

## The Big Formula Trap

Effective duration has a 2 in the denominator:

$$
\text{EffDur}=\frac{PV_- - PV_+}{2 \times \Delta\text{Curve} \times PV_0}
$$

Effective convexity does not have that same 2 in the denominator:

$$
\text{EffCon}
=\frac{PV_- + PV_+ - 2PV_0}{(\Delta\text{Curve})^2 \times PV_0}
$$

Exam trap:

```text
Do not put 2 x DeltaCurve^2 x PV0 in the effective convexity denominator.
```

The 2 is already doing its job in the numerator through the $-2PV_0$ term.

## Worked Example

Suppose a callable bond has:

| Input | Value |
|---|---:|
| Current value, $PV_0$ | 100.594 |
| Value if curve shifts down 30 bps, $PV_-$ | 101.194 |
| Value if curve shifts up 30 bps, $PV_+$ | 99.860 |
| Curve shift, $\Delta\text{Curve}$ | 0.0030 |

Then:

$$
\text{EffCon}
=\frac{101.194+99.860-2(100.594)}
{(0.0030)^2(100.594)}
$$

$$
\text{EffCon}
=\frac{-0.134}{0.000905346}
\approx -148.0
$$

The negative sign matters more than the raw scale.

It tells us:

```text
This bond has negative effective convexity over the tested rate range.
```

Why?

Because the price gain when rates fall is being capped more than the price loss when rates rise is being protected.

That is classic callable-bond behavior near the call boundary.

## How Convexity Improves a Price Estimate

The duration-only approximation is:

$$
\%\Delta P \approx -\text{EffDur}\times \Delta y
$$

The duration-plus-convexity approximation is:

$$
\%\Delta P
\approx
-\text{EffDur}\times \Delta y
+
\frac{1}{2}\times \text{EffCon}\times (\Delta y)^2
$$

The duration term is the first-order effect.

The convexity term is the second-order effect.

For small rate moves, duration may be enough.

For larger rate moves, convexity becomes more important because the price-yield relationship bends.

## Why Effective Convexity Is Used for Embedded Options

Standard convexity assumes fixed cash flows.

That assumption is acceptable for a straight option-free bond.

But it is not acceptable when a bond has an embedded option.

With an embedded option:

```text
Rates move -> option exercise probability changes -> expected cash flows change -> price response bends differently.
```

For a callable bond:

```text
Rates fall -> issuer is more likely to call -> price upside gets capped.
```

For a putable bond:

```text
Rates rise -> investor is more likely to put -> price downside gets floored.
```

For a mortgage-backed security:

```text
Rates fall -> prepayments speed up -> principal returns sooner.
```

Effective convexity is designed for this world because it revalues the bond after shifting the benchmark curve and allowing cash flows to change.

## The OAS Link

For risky bonds with embedded options, effective convexity is usually calculated through the same valuation machinery as [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]].

The process is:

1. Use the current market price to solve for the bond's [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]].
2. Hold that OAS constant.
3. Shift the benchmark curve down and revalue the bond to get $PV_-$.
4. Shift the benchmark curve up and revalue the bond to get $PV_+$.
5. Plug the values into the effective convexity formula.

Holding OAS constant keeps the analysis focused on interest rate curvature, not credit spread changes.

## Callable Bond Convexity

A [[Callable bond]] gives the issuer the right to redeem the bond early.

That option hurts the investor because the issuer will tend to call the bond when it is favorable to the issuer, not when it is favorable to the investor.

When rates are high:

```text
The call option is out of the money.
The issuer is unlikely to call.
The callable bond behaves more like a straight bond.
Convexity can be positive.
```

When rates fall and the call becomes near the money:

```text
The issuer is likely to call.
The bond's upside is capped near the call price.
The bondholder does not fully benefit from falling rates.
Effective convexity can turn negative.
```

This is the core negative convexity story.

| Rate Level | Call Option Status | Callable Bond Convexity |
|---|---|---|
| High rates | Call out of the money | Usually positive, like a straight bond |
| Low rates / near call price | Call near or in the money | Can become negative |

## Why Negative Convexity Is Bad

For an option-free bond with positive convexity:

```text
Rates down 100 bps -> price gain is relatively large.
Rates up 100 bps -> price loss is relatively smaller.
```

For a callable bond with negative convexity:

```text
Rates down 100 bps -> price gain is limited by the call.
Rates up 100 bps -> price loss is not similarly limited.
```

That means the investor has an unattractive asymmetry:

```text
Less upside when rates fall.
Still meaningful downside when rates rise.
```

The issuer owns the valuable option. The investor is short that option.

That is why callable bonds usually offer extra yield compensation.

## Putable Bond Convexity

A [[Putable bond]] gives the investor the right to sell the bond back to the issuer.

That option helps the investor.

When rates rise:

```text
Straight bond prices fall.
But the put option becomes more valuable.
The investor can put the bond back at the exercise price.
The bond's downside is floored.
```

When rates fall:

```text
The put option is less relevant.
The bond can still enjoy price appreciation.
```

So the investor has a favorable asymmetry:

```text
More upside when rates fall.
Less downside when rates rise.
```

That is positive convexity.

For CFA purposes:

```text
Putable bonds exhibit positive convexity.
```

## Straight vs Callable vs Putable

| Bond Type | Typical Effective Convexity | Why |
|---|---|---|
| Straight option-free bond | Positive | Price-yield curve is normally bowed in the investor's favor |
| Callable bond | Positive when call is far out of the money; negative when call is near the money | Investor's upside is capped by issuer's call |
| Putable bond | Positive | Investor's downside is protected by put option |

Memory version:

```text
Straight: good bend.
Callable near the money: bad bend.
Putable: investor-friendly bend.
```

## Connection to Effective Duration

Effective duration and effective convexity are partners.

| Measure | What It Captures | Order of Effect |
|---|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] | Slope of price-rate relationship | First-order |
| [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] | Curvature of price-rate relationship | Second-order |

Duration answers:

```text
How steep is the price response right now?
```

Convexity answers:

```text
How does that steepness change as rates move?
```

If the bond has embedded options, both measures need to be effective measures because the cash flows can change.

## Real-World Scenarios

### Scenario 1: Callable Corporate Bond After a Rate Rally

A portfolio manager owns a high-coupon callable corporate bond.

Rates fall.

The bond price rises at first, but then approaches the call price. At that point, further rate declines do not help much because the issuer is increasingly likely to redeem the bond.

Implication:

```text
The bond may show negative effective convexity.
```

The manager faces reinvestment risk: principal may come back exactly when reinvestment yields are lower.

### Scenario 2: Mortgage Portfolio During Refinancing Wave

A mortgage-backed security portfolio benefits less than expected from falling rates.

Why?

Borrowers refinance, prepayments accelerate, and the expected life of the security shortens.

Implication:

```text
The portfolio can display negative convexity,
similar to callable bonds.
```

The investor is effectively short the borrower's prepayment option.

### Scenario 3: Putable Bond in a Rate Shock

An investor owns a putable bond before rates rise sharply.

The straight-bond value would fall, but the investor's put option becomes valuable and floors the bond's price.

Implication:

```text
The putable bond keeps positive convexity.
```

The investor paid for this protection by accepting a lower yield than an otherwise similar non-putable bond.

## Limits of the Measure

Effective convexity is better than duration alone, but it is still an approximation.

It assumes:

| Assumption | Why It Matters |
|---|---|
| Parallel curve shift | It does not directly capture yield curve twists or steepening |
| Model-based option exercise | Output depends on the interest rate tree and volatility assumption |
| OAS held constant | It isolates interest rate curvature, not spread widening or tightening |
| Moderate rate shock | Very large shocks may require full scenario analysis or stress testing |

This is especially important for option-embedded bonds.

For a severe scenario, the analyst should usually revalue the bond under the full scenario instead of trusting a duration-plus-convexity shortcut.

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Put a 2 in the effective convexity denominator | CFA's effective convexity formula does not use $2(\Delta\text{Curve})^2PV_0$ | Denominator is $(\Delta\text{Curve})^2PV_0$ |
| Use standard convexity for callable or putable bonds | Standard convexity assumes fixed cash flows | Use effective convexity |
| Think all bonds have positive convexity | Callable bonds can have negative convexity when the call is near the money | Check the embedded option |
| Think negative convexity means price always falls | It means the curvature is unfavorable | Price can still rise when rates fall, but by less than a straight bond |
| Forget to convert bps to decimal | 30 bps is not 30 or 0.30 | 30 bps = 0.0030 |
| Ignore OAS | Spread changes contaminate the interest rate sensitivity measure | Hold OAS constant |
| Treat convexity as more important for tiny moves | Convexity is second-order | It matters more as rate moves get larger |
| Confuse putable and callable convexity | Put option belongs to investor; call option belongs to issuer | Putable is investor-friendly, callable is investor-unfriendly near the money |
| Assume callable bonds always have negative convexity | The call must be economically relevant | Callable bonds can have positive convexity when rates are high and the call is out of the money |
| Use duration plus convexity for an extreme stress scenario | Sensitivities are approximations | Revalue the bond under the scenario |

## Memory Hooks

```text
Duration is slope. Convexity is bend.
```

```text
Callable near the call price = capped upside = negative convexity risk.
```

```text
Putable = investor owns the protection = positive convexity.
```

```text
Effective convexity lets the cash flows re-decide.
```

## Exam Decision Checklist

When you see an effective convexity question, ask:

1. Does the bond have an embedded option?
2. Is the formula using $PV_-$, $PV_+$, and $PV_0$?
3. Is the curve shift in decimal form?
4. Did the denominator avoid the extra 2?
5. Is OAS being held constant?
6. Is the callable bond near the call price?
7. Is the investor long or short the embedded option?

Then choose:

| Situation | Likely Answer |
|---|---|
| Option-free bond | Positive convexity |
| Callable bond, high rates | Positive or similar to straight bond |
| Callable bond, low rates / near call | Negative convexity possible |
| Putable bond | Positive convexity |
| Larger rate shock | Convexity adjustment matters more |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]]
- [[Modified duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]]
- [[Callable bond]]
- [[Putable bond]]
- [[Embedded option]]
- [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]]
- [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]]
- [[Mortgage-backed security]]
- [[Convexity adjustment]]
