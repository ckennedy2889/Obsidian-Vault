---
title: Key Rate Duration
subject: Fixed Income
tags: [CFA-L2, fixed-income, key-rate-duration, partial-duration, yield-curve-risk, shaping-risk, duration]
aliases: [key rate duration, key rate durations, partial duration, partial durations, KRD, key-rate duration]
---

# Key Rate Duration

## The Real-World Analogy

[[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] asks:

```text
What happens if the entire yield curve moves up or down together?
```

That is like asking how a bridge handles the whole ground rising or falling evenly.

But real yield curves do not move that neatly.

Sometimes:

```text
Short rates rise.
Intermediate rates barely move.
Long rates fall.
```

That is like different parts of the bridge being pushed in different directions.

[[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] breaks the bond's interest rate risk into maturity buckets so we can ask:

```text
Which part of the yield curve is this bond or portfolio most exposed to?
```

## Plain-English Definition

Key rate duration measures how sensitive a bond or bond portfolio is to a change in one specific maturity point on the benchmark yield curve, holding the other maturity points constant.

It is also called [[Partial duration]] because it measures only one part of the curve at a time.

Examples:

| Key Rate | Question |
|---|---|
| 2-year key rate duration | What happens if only the 2-year rate changes? |
| 5-year key rate duration | What happens if only the 5-year rate changes? |
| 10-year key rate duration | What happens if only the 10-year rate changes? |
| 30-year key rate duration | What happens if only the 30-year rate changes? |

## CFA Definition

For CFA Level II, key rate duration is the sensitivity of the value of a security or portfolio to a change in a single par rate, holding all other par rates constant.

That means:

```text
Shift one point on the benchmark curve.
Keep the other points unchanged.
Revalue the bond or portfolio.
Measure the price sensitivity.
```

This is why key rate duration is used to measure [[Shaping risk]].

## What Shaping Risk Means

[[Shaping risk]] is the risk that a bond or portfolio loses value because the yield curve changes shape.

Examples of shape changes:

| Curve Movement | What Happens |
|---|---|
| Steepening | Long-term rates rise relative to short-term rates |
| Flattening | Long-term rates fall relative to short-term rates, or short-term rates rise relative to long-term rates |
| Twist | Rates at different maturities move in opposite directions |
| Curvature change | Short and long rates move differently from intermediate rates |

[[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] is not enough for this because it assumes a parallel shift.

Key rate duration is built for the messier real world where each maturity can move differently.

## Measurement Logic

The calculation is similar to effective duration.

The difference is that only one key rate is shifted.

For the $i$th key rate:

$$
\text{KeyDur}_i
=
\frac{PV_{i,-}-PV_{i,+}}
{2\times \Delta r_i \times PV_0}
$$

Where:

| Term | Meaning |
|---|---|
| $PV_{i,-}$ | Bond value when key rate $i$ is shifted down |
| $PV_{i,+}$ | Bond value when key rate $i$ is shifted up |
| $PV_0$ | Current bond value |
| $\Delta r_i$ | Size of the shift in key rate $i$, expressed as a decimal |

The words matter more than the notation:

```text
Effective duration shifts the whole curve.
Key rate duration shifts one maturity point at a time.
```

## Price Change Model

If a portfolio has several key rate durations, its approximate percentage price change is:

$$
\frac{\Delta V}{V}
\approx
-\sum_i \text{KeyDur}_i \Delta r_i
$$

This is just duration logic applied by curve segment.

If the 2-year rate rises, the 2-year key rate duration matters.

If the 10-year rate falls, the 10-year key rate duration matters.

If every key rate changes by the same amount, the key rate duration model collapses back into effective duration.

## Sum of Key Rate Durations

For a set of key rates that fully represents the curve exposure:

$$
\sum_i \text{KeyDur}_i \approx \text{Effective Duration}
$$

Why?

If all key rates move by the same amount, the yield curve has made a parallel shift.

So the total price response from all key-rate buckets should match the effective-duration response.

In plain English:

```text
Key rate duration decomposes effective duration.
```

## Worked Example: Three Key Rates

Suppose a portfolio has exposure to three key rates:

| Key Rate | Key Rate Duration |
|---|---:|
| 1-year | 0.3333 |
| 5-year | 1.6667 |
| 10-year | 3.3333 |

The sum is:

$$
0.3333+1.6667+3.3333=5.3333
$$

So the portfolio's effective duration is approximately 5.3333.

### Parallel Shift

If all three key rates fall by 50 bps:

$$
\Delta r=-0.0050
$$

Then:

$$
\frac{\Delta V}{V}
\approx
-5.3333(-0.0050)
=0.0267
=2.67\%
$$

The portfolio gains value because rates fell.

### Nonparallel Shift

Now suppose:

| Key Rate | Rate Change |
|---|---:|
| 1-year | +25 bps |
| 5-year | 0 bps |
| 10-year | -40 bps |

Then:

$$
\frac{\Delta V}{V}
\approx
-[(0.3333)(0.0025)+(1.6667)(0)+(3.3333)(-0.0040)]
$$

$$
\frac{\Delta V}{V}
\approx
-[0.0008+0-0.0133]
=0.0125
=1.25\%
$$

The portfolio gains because its long-rate exposure is much larger than its short-rate exposure, and the long rate fell.

That is exactly the kind of insight effective duration alone would hide.

## Effective Duration vs Key Rate Duration

| Feature | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
|---|---:|---:|
| Curve shift | Entire curve shifts together | One maturity point shifts |
| Best for | Parallel shifts | Nonparallel shifts |
| Risk captured | Level risk | Shape risk |
| Output | One number | A vector of numbers |
| Portfolio use | Broad interest rate risk estimate | Hedging and curve positioning |

Exam shortcut:

```text
Parallel shift -> effective duration.
Curve twist, steepening, flattening, shaping risk -> key rate duration.
```

## Why It Matters for Portfolio Management

Two portfolios can have the same effective duration but very different key rate duration profiles.

Example:

| Portfolio | Effective Duration | Risk Profile |
|---|---:|---|
| Barbell | 5.0 | High exposure to short and long rates |
| Bullet | 5.0 | Concentrated exposure around intermediate rates |

If the curve shifts in parallel, both may behave similarly.

But if the curve steepens or twists, they can perform very differently.

Key rate duration tells the manager where the risk actually lives.

## Hedging Implications

Suppose a portfolio has too much 10-year key rate duration.

The manager could reduce that exposure by:

| Tool | Possible Action |
|---|---|
| Treasury futures | Short futures tied to the 10-year area |
| Interest rate swaps | Pay fixed in the maturity sector with excess exposure |
| Cash bonds | Sell bonds with high 10-year key rate duration |
| Curve trades | Offset long-rate exposure while preserving other parts of the curve |

The point is not just to lower total duration.

The point is to target the specific maturity bucket that creates the unwanted risk.

## Limits of Key Rate Duration

Key rate duration is powerful, but it is still a simplified map of curve risk.

| Limitation | Why It Matters |
|---|---|
| Linear approximation | Like duration, KRD becomes less accurate for large rate moves |
| Key-rate bucketing | A "5-year" bucket may represent several nearby maturities that do not move perfectly together |
| Model dependence | Revaluations depend on the curve construction and pricing model |
| Spread risk excluded | KRD measures benchmark curve exposure, not credit spread exposure |
| Scenario interaction | Multiple large curve moves can interact in ways a simple sum may not fully capture |

For serious stress testing, the portfolio should be fully revalued under the scenario rather than relying only on key rate duration arithmetic.

## Option-Free Bond Patterns

For option-free bonds:

| Bond Type | Key Rate Duration Pattern |
|---|---|
| Par bond | Highest at maturity-matched rate; for a pure par setup, maturity key rate may dominate |
| Premium or discount bond | Maturity-matched rate is usually still most important |
| Zero-coupon bond | Exposure is concentrated near maturity |
| Very low coupon bond | Some shorter key rate durations can be negative |

The negative key rate duration point is easy to miss.

It can happen because shifting one par rate can change the implied spot curve in a way that lowers discount rates at another maturity. The bond's cash flow timing then makes its value move in the opposite direction from what a simple intuition might predict.

## Callable Bond Patterns

For a [[Callable bond]], the key maturity can shift from the final maturity date to the call date.

The mechanism:

```text
Higher coupon -> call more likely -> bond behaves more like it matures on the call date.
```

So:

| Callable Bond | Most Important Key Rate |
|---|---|
| Low coupon, unlikely to be called | Maturity-matched rate |
| High coupon, likely to be called | Call-date rate |

Deep intuition:

If a 30-year bond is almost certain to be called in 10 years, it is economically closer to a 10-year bond than a 30-year bond.

So its 10-year key rate duration can dominate its 30-year key rate duration.

## Putable Bond Patterns

For a [[Putable bond]], the key maturity can shift from the final maturity date to the put date.

The mechanism:

```text
Lower coupon -> put more likely -> bond behaves more like it matures on the put date.
```

So:

| Putable Bond | Most Important Key Rate |
|---|---|
| High coupon, unlikely to be put | Maturity-matched rate |
| Low coupon, likely to be put | Put-date rate |

Why low coupon?

A low-coupon bond is unattractive if market rates are higher, so the investor is more likely to use the put option and get out early.

## Real-World Scenarios

### Scenario 1: Bank Portfolio With Same Effective Duration, Different Curve Risk

A bank owns two possible bond portfolios, both with effective duration near 5.

One is a bullet portfolio centered around 5-year bonds.

The other is a barbell portfolio split between short and long maturities.

If the whole curve moves up 50 bps, both may lose similar amounts.

But if the curve steepens, the barbell may behave very differently because its long-rate exposure is larger.

Implication:

```text
Effective duration matched the level risk, but key rate duration reveals the shape risk.
```

### Scenario 2: Liability Hedging

An insurer has liabilities sensitive to 20-year and 30-year rates.

Buying a bond portfolio with the same effective duration is not enough.

If the asset portfolio gets its duration from 5-year and 10-year exposures, it may fail when long rates move.

Implication:

```text
The insurer needs key rate duration matching, not just effective duration matching.
```

### Scenario 3: Callable Bond Portfolio

A manager owns high-coupon callable bonds callable in 10 years but maturing in 30 years.

The manager might think the portfolio is long 30-year risk.

But if the bonds are likely to be called, the key rate duration may be concentrated around the 10-year call date.

Implication:

```text
The economically relevant maturity is the exercise date, not always the legal final maturity.
```

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Use effective duration for shaping risk | Effective duration assumes a parallel curve shift | Use key rate duration |
| Think key rate duration is one number | It is a set of exposures | Each key maturity has its own duration |
| Forget to hold other rates constant | Then you are measuring a multi-rate scenario, not one key rate | Shift one key rate at a time |
| Ignore the sign of rate changes | Price change uses $-\text{duration}\times\Delta r$ | Rate down means price up |
| Assume highest KRD is always final maturity | Options can shift economic maturity | Callable may focus on call date; putable may focus on put date |
| Forget KRDs sum to effective duration | Then parallel shift math will look inconsistent | Sum the key buckets |
| Assume key rate duration captures credit spread risk | It is about benchmark curve exposure | Use spread duration for spread risk |
| Treat negative KRD as impossible | Low-coupon/zero structures can produce negative KRDs at non-maturity points | Follow the valuation effect |
| Treat KRD as exact for a huge shock | KRD is still a linear sensitivity | Fully revalue under large stress scenarios |

## Memory Hooks

```text
Effective duration = whole curve.
Key rate duration = one key at a time.
```

```text
KRD is the curve-risk map.
```

```text
Same effective duration does not mean same curve exposure.
```

```text
Callable: likely call shifts risk to call date.
Putable: likely put shifts risk to put date.
```

## Exam Decision Checklist

When a question mentions curve risk, ask:

1. Is the yield curve shift parallel?
2. Does the question mention steepening, flattening, twist, or shaping risk?
3. Are you given several maturity-specific durations?
4. Are you asked which maturity point matters most?
5. Does the bond have a call or put that changes the economically relevant maturity?
6. Are you calculating a total portfolio price change from multiple rate changes?

Then choose:

| Situation | Measure |
|---|---|
| Parallel benchmark curve shift | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
| One maturity point changes | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
| Curve steepens/flattens/twists | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
| Credit spread changes | [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] |
| Callable/putable bond with changing cash flows | Effective/key rate measures using option-adjusted valuation |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]]
- [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]]
- [[Shaping risk]]
- [[Yield curve]]
- [[Parallel shift]]
- [[Twist]]
- [[Steepness]]
- [[Curvature]]
- [[Callable bond]]
- [[Putable bond]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
