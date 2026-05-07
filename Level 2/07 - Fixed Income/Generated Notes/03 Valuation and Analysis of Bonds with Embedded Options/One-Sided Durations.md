---
title: One-Sided Durations
subject: Fixed Income
tags: [CFA-L2, fixed-income, one-sided-duration, effective-duration, embedded-options, callable-bonds, putable-bonds, interest-rate-risk]
aliases: [one-sided durations, one-sided duration, one-sided up-duration, one-sided down-duration, up-duration, down-duration]
---

# One-Sided Durations

## The Real-World Analogy

Imagine testing a car's suspension by pushing it down and pulling it up.

If the car responds the same way in both directions, one average number describes it pretty well.

But if the car has a mechanical stop that limits upward movement, then the average hides something important:

```text
It reacts one way when pushed down,
and a different way when pulled up.
```

That is the problem with using ordinary two-sided [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] for bonds with embedded options.

A callable bond may react mildly when rates fall but strongly when rates rise.

A putable bond may react strongly when rates fall but mildly when rates rise.

[[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]] separate those two directions.

## Plain-English Definition

One-sided durations are effective durations measured separately for upward and downward interest rate moves.

Instead of asking:

```text
On average, how sensitive is the bond to rates moving up or down?
```

They ask:

```text
How sensitive is the bond if rates rise?
How sensitive is the bond if rates fall?
```

That matters when the bond's price response is asymmetric.

## CFA Definition

For CFA Level II, one-sided durations are effective durations when interest rates go up or down, used to better capture the interest rate sensitivity of bonds with embedded options that do not react symmetrically to positive and negative rate changes of the same magnitude.

Key phrase:

```text
better for bonds with embedded options when rate-up and rate-down responses are asymmetric
```

## Why Two-Sided Effective Duration Can Hide Risk

The normal effective duration formula is:

$$
\text{EffDur}
=
\frac{PV_- - PV_+}
{2\times \Delta\text{Curve}\times PV_0}
$$

This uses both:

| Scenario | Meaning |
|---|---|
| $PV_-$ | Value when rates fall |
| $PV_+$ | Value when rates rise |

That is a two-sided average.

For option-free bonds and very small rate changes, that average is usually fine.

But for bonds with embedded options, the price response can be very different depending on direction.

Examples:

| Bond | Rates Fall | Rates Rise |
|---|---|---|
| [[Callable bond]] | Upside can be capped by call option | Downside remains exposed |
| [[Putable bond]] | Upside remains exposed | Downside can be floored by put option |

So the average may describe neither side very well.

## The Formulas

One-sided down-duration measures sensitivity when rates fall:

$$
\text{DownDur}
=
\frac{PV_- - PV_0}
{\Delta\text{Curve}\times PV_0}
$$

One-sided up-duration measures sensitivity when rates rise:

$$
\text{UpDur}
=
\frac{PV_0 - PV_+}
{\Delta\text{Curve}\times PV_0}
$$

Where:

| Term | Meaning |
|---|---|
| $PV_0$ | Current bond value |
| $PV_-$ | Bond value after rates fall |
| $PV_+$ | Bond value after rates rise |
| $\Delta\text{Curve}$ | Size of the rate shock, expressed as a decimal |

The signs are arranged so both one-sided durations are usually positive.

## Worked Example: Callable Bond

Suppose a callable bond has:

| Input | Value |
|---|---:|
| Current value, $PV_0$ | 100.00 |
| Value if rates fall 50 bps, $PV_-$ | 100.75 |
| Value if rates rise 50 bps, $PV_+$ | 97.50 |
| Rate shock, $\Delta\text{Curve}$ | 0.0050 |

Down-duration:

$$
\text{DownDur}
=
\frac{100.75-100.00}{0.0050(100.00)}
=
\frac{0.75}{0.50}
=1.50
$$

Up-duration:

$$
\text{UpDur}
=
\frac{100.00-97.50}{0.0050(100.00)}
=
\frac{2.50}{0.50}
=5.00
$$

Two-sided effective duration:

$$
\text{EffDur}
=
\frac{100.75-97.50}{2(0.0050)(100.00)}
=
\frac{3.25}{1.00}
=3.25
$$

The two-sided number, 3.25, hides the actual directional risk.

This callable bond is:

```text
Not very sensitive to falling rates because price upside is capped.
Very sensitive to rising rates because price downside is not capped.
```

## Callable Bond Behavior

A [[Callable bond]] gives the issuer the right to redeem the bond early.

The issuer wants to call when rates fall because refinancing becomes attractive.

So when rates fall:

```text
Bond price tries to rise.
Call option becomes more valuable to the issuer.
Price is capped near the call price.
Down-duration becomes lower.
```

When rates rise:

```text
Call option becomes less relevant.
Bond behaves more like a straight bond.
Price can fall more normally.
Up-duration is higher.
```

For a callable bond near the money:

$$
\text{DownDur} < \text{UpDur}
$$

Memory version:

```text
Callable = capped upside = lower down-duration.
```

## Putable Bond Behavior

A [[Putable bond]] gives the investor the right to sell the bond back to the issuer.

The investor wants to put when rates rise because the bond's market value would otherwise fall.

So when rates rise:

```text
Bond price tries to fall.
Put option becomes more valuable to the investor.
Price is floored near the put price.
Up-duration becomes lower.
```

When rates fall:

```text
Put option becomes less relevant.
Bond behaves more like a straight bond.
Price can rise more normally.
Down-duration is higher.
```

For a putable bond near the money:

$$
\text{DownDur} > \text{UpDur}
$$

Memory version:

```text
Putable = floored downside = lower up-duration.
```

## Worked Example: Putable Bond

Suppose a putable bond has:

| Input | Value |
|---|---:|
| Current value, $PV_0$ | 100.00 |
| Value if rates fall 50 bps, $PV_-$ | 103.00 |
| Value if rates rise 50 bps, $PV_+$ | 99.20 |
| Rate shock, $\Delta\text{Curve}$ | 0.0050 |

Down-duration:

$$
\text{DownDur}
=
\frac{103.00-100.00}{0.0050(100.00)}
=6.00
$$

Up-duration:

$$
\text{UpDur}
=
\frac{100.00-99.20}{0.0050(100.00)}
=1.60
$$

This putable bond is much more sensitive to falling rates than rising rates.

Why?

```text
When rates rise, the put option protects the investor.
When rates fall, the bond can still appreciate.
```

## Relationship to Effective Convexity

The two-sided [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] is the average of the two one-sided durations:

$$
\text{EffDur}
=
\frac{\text{UpDur}+\text{DownDur}}{2}
$$

That is useful for remembering the mechanics, but it is also the weakness.

If the two sides are very different, the average may be mathematically correct but economically incomplete.

One-sided duration and [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] are different tools, but they are telling related stories.

One-sided duration says:

```text
The slope is different depending on direction.
```

Effective convexity says:

```text
The slope changes as rates move.
```

For callable bonds near the call price:

| Measure | What It Reveals |
|---|---|
| One-sided duration | Down-duration is lower than up-duration |
| Effective convexity | Convexity may be negative |

Both are symptoms of the same mechanism:

```text
The issuer's call option caps the investor's upside.
```

## When One-Sided Durations Matter Most

One-sided durations are most useful when:

| Situation | Why One-Sided Duration Helps |
|---|---|
| Embedded option is near the money | Option exercise likelihood changes sharply |
| Callable bond near call price | Falling-rate upside is capped |
| Putable bond near put price | Rising-rate downside is floored |
| Mortgage-backed security during refi risk | Falling rates can trigger prepayments |
| Risk manager cares about directional rate shock | Up and down shocks have different impact |

They are less important when:

```text
The bond is option-free,
the option is far out of the money,
or the rate shock is tiny.
```

Like effective duration, one-sided duration still assumes a parallel curve move. If the question is about steepening, flattening, or twist risk, use [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] instead.

## Real-World Scenarios

### Scenario 1: Callable Bond in a Falling-Rate Market

A manager owns a callable corporate bond trading near its call price.

Rates fall 50 bps.

The manager expects a large price gain, but the bond barely rises because investors expect the issuer to call.

Implication:

```text
Down-duration is low.
```

The manager faces reinvestment risk because principal may come back when yields are lower.

### Scenario 2: Callable Bond in a Rising-Rate Market

The same callable bond faces a 50 bps rate increase.

Now the call option becomes less valuable to the issuer.

The bond is no longer protected by a call-price ceiling because the problem is downside, not upside.

Implication:

```text
Up-duration is higher than down-duration.
```

### Scenario 3: Putable Bond During a Rate Shock

An investor owns a putable bond before rates rise.

Straight bond prices fall, but this bond does not fall as much because the investor can put it back to the issuer.

Implication:

```text
Up-duration is low.
```

The investor paid for that protection through a lower yield.

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Use only two-sided effective duration near an embedded option boundary | It averages away asymmetry | Use one-sided durations |
| Think callable bonds are protected when rates rise | The call belongs to the issuer and caps upside when rates fall | Callable up-duration can be higher |
| Think putable bonds are most exposed when rates rise | The put belongs to the investor and floors downside | Putable up-duration can be lower |
| Reverse $PV_-$ and $PV_+$ | Rates down usually means price up | $PV_-$ is the down-rate value |
| Forget to convert bps to decimals | 50 bps is 0.0050 | Use decimal rate shocks |
| Treat one-sided durations as necessary for all bonds | Option-free bonds are usually more symmetric | One-sided is most valuable for embedded options |
| Ignore whether the option is near the money | Far out-of-the-money options may not affect price much | Asymmetry is strongest near the exercise boundary |
| Use one-sided duration for curve-shape risk | One-sided duration is directional but still assumes a parallel shift | Use [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] for shaping risk |

## Memory Hooks

```text
One-sided duration asks: which way did rates move?
```

```text
Callable: rates down, call caps upside, down-duration drops.
```

```text
Putable: rates up, put floors downside, up-duration drops.
```

```text
Two-sided duration is an average; one-sided duration shows the asymmetry.
```

## Exam Decision Checklist

When you see a duration question with embedded options, ask:

1. Is the bond callable, putable, or mortgage-backed?
2. Is the option near the money?
3. Does the question compare equal rate increases and decreases?
4. Is the price response asymmetric?
5. Which side is capped or floored?
6. Are you being asked for directional interest rate risk?

Then choose:

| Situation | Measure |
|---|---|
| Option-free bond, small moves | [[Modified duration]] or [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
| Embedded option, average parallel sensitivity | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
| Embedded option, asymmetric up/down response | [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]] |
| Nonparallel yield curve shift | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
| Curvature in price response | [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]]
- [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]]
- [[Callable bond]]
- [[Putable bond]]
- [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]]
- [[Embedded option]]
- [[Mortgage-backed security]]
- [[Reinvestment risk]]
