---
title: Effective Duration
subject: Fixed Income
tags: [CFA-L2, fixed-income, effective-duration, duration, embedded-options, callable-bonds, putable-bonds, interest-rate-risk]
aliases: [effective duration, option-adjusted duration, curve duration, effective duration of callable bond, effective duration of putable bond]
---

# Effective Duration

## The Real-World Analogy

Imagine you are measuring how sensitive a car is to the gas pedal.

For a normal car, you can press the pedal a little and assume the car's engine response is stable. That is like measuring duration for a normal option-free bond: the cash flows are fixed, so the price response mostly comes from discount rates changing.

Now imagine the car has a computer that changes gears, limits acceleration, or cuts power depending on road conditions.

That is like a bond with an embedded option.

When rates move, the bond's expected cash flows may change too:

| Bond | Who Has the Option? | What Changes When Rates Move? |
|---|---:|---|
| [[Callable bond]] | Issuer | Issuer may redeem early when rates fall |
| [[Putable bond]] | Investor | Investor may sell the bond back when rates rise |
| [[Mortgage-backed security]] | Borrowers | Borrowers may prepay faster when rates fall |

So effective duration asks:

```text
If the benchmark yield curve shifts,
how much does the bond's price change after allowing the bond's cash flows to re-optimize?
```

That last phrase is the whole point: effective duration lets the cash flows respond to interest rates.

## Plain-English Definition

[[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] measures a bond's price sensitivity to a parallel shift in the benchmark yield curve, allowing expected cash flows to change when the bond has embedded options.

In practical language:

```text
Effective duration tells you the approximate percentage price change
for a 1% change in benchmark interest rates,
after accounting for option exercise behavior.
```

If a bond has an effective duration of 4.2, then a 100 bps parallel increase in benchmark rates should reduce the bond's price by about 4.2%, before convexity and spread changes.

## CFA Definition

For CFA Level II, effective duration is the sensitivity of a bond's full price to a 100 bps parallel shift in the benchmark yield curve, assuming no change in the bond's credit spread.

That wording contains several exam-critical details:

| Phrase | Meaning |
|---|---|
| Full price | Use the value including accrued interest when the curriculum frames it that way |
| Benchmark yield curve | We shock the underlying risk-free or benchmark curve, not just the bond's own yield to maturity |
| Parallel shift | Every maturity point on the curve moves by the same number of basis points |
| No change in credit spread | We isolate interest rate risk, not credit spread risk |
| Cash flows may change | Embedded options can change expected timing and amount of cash flows |

## The Formula

The standard CFA formula is:

$$
\text{EffDur}=\frac{PV_- - PV_+}{2 \times \Delta\text{Curve} \times PV_0}
$$

Where:

| Term | Meaning |
|---|---|
| $PV_-$ | Bond value after shifting the benchmark curve down |
| $PV_+$ | Bond value after shifting the benchmark curve up |
| $PV_0$ | Current bond value |
| $\Delta\text{Curve}$ | Size of the curve shift, expressed as a decimal |

The signs make intuitive sense:

```text
Rates down -> bond price usually up -> PV_- is usually higher
Rates up   -> bond price usually down -> PV_+ is usually lower
```

So the numerator $PV_- - PV_+$ measures the total price difference between the down-rate and up-rate scenarios.

The denominator divides by:

```text
2 x the rate shock x current value
```

That converts the two-sided dollar price change into a percentage sensitivity per 1.00 change in rates.

## Why Delta Must Be a Decimal

If the curve shift is 30 bps, then:

$$
30\text{ bps}=0.30\%=0.0030
$$

Do not plug in 30.

Do not plug in 0.30.

Use 0.0030.

This is one of those small arithmetic traps that can turn a completely correct setup into a nonsense answer.

## Worked Example

Suppose a callable bond has:

| Input | Value |
|---|---:|
| Current value, $PV_0$ | 101.000 |
| Value if curve shifts down 30 bps, $PV_-$ | 101.599 |
| Value if curve shifts up 30 bps, $PV_+$ | 100.407 |
| Curve shift, $\Delta\text{Curve}$ | 0.0030 |

Then:

$$
\text{EffDur}
=\frac{101.599-100.407}{2(0.0030)(101.000)}
$$

$$
\text{EffDur}
=\frac{1.192}{0.606}
=1.97
$$

Interpretation:

```text
For a 100 bps parallel rise in benchmark rates,
the bond's price should fall by about 1.97%.
```

For a 30 bps rise:

$$
\% \Delta P \approx -1.97 \times 0.0030 = -0.00591 = -0.591\%
$$

That approximation uses duration only. A more complete estimate would include [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]].

## Why Modified Duration Is Not Enough

[[Modified duration]] works cleanly when the bond's promised cash flows are fixed.

The logic is:

```text
Same cash flows + new discount rate = new price
```

That is fine for a straight fixed-rate bond.

But it breaks for bonds with embedded options because the cash flows themselves are interest-rate dependent.

For a callable bond:

```text
Rates fall -> issuer is more likely to call -> bond may mature earlier
```

For a putable bond:

```text
Rates rise -> investor is more likely to put -> bond may be redeemed earlier
```

For a mortgage-backed security:

```text
Rates fall -> homeowners refinance -> principal returns earlier
```

So the valuation problem becomes:

```text
New rates -> new option exercise decisions -> new expected cash flows -> new price
```

Effective duration is built for that chain.

## The Mechanism: How Effective Duration Is Usually Calculated

For a bond with an embedded option, analysts often use an arbitrage-free interest rate tree.

The process is:

1. Build a benchmark interest rate tree.
2. Add the bond's [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]] to the tree.
3. Value the bond with backward induction, allowing the option to be exercised at each node.
4. Shift the benchmark curve down by the chosen amount.
5. Rebuild or adjust the tree and revalue the bond to get $PV_-$.
6. Shift the benchmark curve up by the chosen amount.
7. Revalue the bond to get $PV_+$.
8. Plug $PV_-$, $PV_+$, and $PV_0$ into the formula.

The key idea:

```text
Each shifted-rate scenario gets its own option exercise pattern.
```

That is why effective duration can capture the way callable and putable bonds respond asymmetrically to interest rates.

## Why OAS Is Held Constant

When calculating effective duration for a risky bond, the [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]] is held constant.

That matters because we are trying to isolate one question:

```text
How much does the bond price change because benchmark interest rates changed?
```

We are not asking:

```text
What happens if credit spreads widen?
What happens if liquidity risk changes?
What happens if investors demand more compensation for default risk?
```

Holding OAS constant keeps the credit/liquidity spread assumption fixed while the benchmark curve moves.

So:

```text
Benchmark curve moves.
OAS stays fixed.
Option exercise gets re-modeled.
Bond value changes.
```

That is effective duration.

## Effective Duration vs Modified Duration

| Feature | [[Modified duration]] | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
|---|---:|---:|
| Main question | Price sensitivity to the bond's own yield | Price sensitivity to benchmark curve shifts |
| Curve movement | Usually summarized as a yield change | Parallel shift in benchmark curve |
| Cash flows | Assumed fixed | May change |
| Best for | Option-free bonds | Bonds with embedded options |
| Spread assumption | Not the main focus | OAS held constant |
| Typical model | Yield-based bond math | Arbitrage-free valuation/tree model |

Exam shortcut:

```text
Option-free bond -> modified duration can be appropriate.
Embedded option -> use effective duration.
```

## Callable Bond Behavior

A [[Callable bond]] gives the issuer the right to redeem the bond early.

That option becomes more valuable to the issuer when rates fall.

Why?

```text
Rates fall -> issuer can refinance cheaper -> issuer wants to call old high-coupon debt
```

This affects duration:

| Rate Environment | Call Option Status | Price Behavior | Duration Effect |
|---|---|---|---|
| Rates fall | Call moves in the money | Price upside is capped | Effective duration shortens |
| Rates rise | Call moves out of the money | Bond behaves more like a straight bond | Effective duration can lengthen |

The deep mechanism is that a callable bond loses some of the best part of being a bond.

Normally, when rates fall, a bondholder enjoys price appreciation. But the call option gives that upside to the issuer. The investor's price appreciation gets capped near the call price, so the bond becomes less sensitive to further rate declines.

That is why callable bonds can have lower effective duration than otherwise similar straight bonds.

## Putable Bond Behavior

A [[Putable bond]] gives the investor the right to sell the bond back to the issuer.

That option becomes more valuable to the investor when rates rise.

Why?

```text
Rates rise -> bond price would normally fall -> investor can put the bond back at the exercise price
```

This affects duration:

| Rate Environment | Put Option Status | Price Behavior | Duration Effect |
|---|---|---|---|
| Rates rise | Put moves in the money | Price downside is floored | Effective duration shortens |
| Rates fall | Put moves out of the money | Bond behaves more like a straight bond | Effective duration can lengthen |

The put option protects the investor from the worst part of rising rates. Because the bond's downside is limited, its price becomes less sensitive to further rate increases.

That is why putable bonds also usually have lower effective duration than otherwise similar straight bonds.

## Duration Ranking Intuition

Holding other features reasonably comparable:

| Bond Type | Duration Intuition |
|---|---|
| Zero-coupon bond | Duration is approximately maturity |
| Fixed-rate coupon bond | Duration is less than maturity |
| Floating-rate note | Duration is approximately time to next reset |
| Callable bond | Effective duration is less than or equal to straight-bond duration |
| Putable bond | Effective duration is less than or equal to straight-bond duration |

Why the floater has low duration:

```text
Coupon resets to market rates,
so the bond price does not need to move much to make the yield competitive again.
```

Why embedded-option bonds often have lower duration:

```text
The option changes the cash-flow pattern exactly when rates move enough to matter.
```

## One-Sided Durations

The regular effective duration formula uses both an up-rate and down-rate scenario.

That gives an average sensitivity.

But bonds with embedded options can be asymmetric.

For example, a callable bond near the call price may behave like this:

```text
Rates fall -> price barely rises because the call caps upside.
Rates rise -> price falls more normally because the call becomes less relevant.
```

So a two-sided average may hide the fact that the bond is much more sensitive to rate increases than to rate decreases.

That is why analysts use [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]].

Common formulas are:

$$
\text{Duration if rates fall}
=\frac{PV_- - PV_0}{\Delta\text{Curve}\times PV_0}
$$

$$
\text{Duration if rates rise}
=\frac{PV_0 - PV_+}{\Delta\text{Curve}\times PV_0}
$$

Interpret these as directional sensitivities:

| One-Sided Measure | What It Captures |
|---|---|
| Down-rate duration | How much price rises when rates fall |
| Up-rate duration | How much price falls when rates rise |

For a callable bond near the money:

```text
Down-rate duration is low because price upside is capped.
Up-rate duration is higher because price can still fall.
```

For a putable bond near the money:

```text
Up-rate duration is low because price downside is floored.
Down-rate duration is higher because price can still rise.
```

## Effective Duration vs Key Rate Duration

Effective duration assumes a parallel shift in the benchmark curve.

But real yield curves do not always move in parallel.

Sometimes:

```text
2-year yields rise,
10-year yields barely move,
30-year yields fall.
```

That is curve-shape risk.

[[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] measures sensitivity to changes at specific maturity points on the yield curve.

| Measure | Best Question |
|---|---|
| Effective duration | What if the whole benchmark curve shifts up or down? |
| Key rate duration | What if one part of the curve moves? |
| Effective convexity | How curved is the price-yield relationship after options respond? |

Exam implication:

```text
If the question says parallel shift, think effective duration.
If the question says nonparallel shift or curve shape risk, think key rate duration.
```

## Real-World Scenarios

### Scenario 1: Bank Owns Callable Agency Bonds

A bank owns callable agency bonds for yield pickup.

Rates fall sharply.

The bank may expect its bond prices to rise, but the callable bonds do not rise as much as straight bonds. The issuers are now more likely to call the bonds and refinance.

Implication:

```text
Effective duration falls when the bank most wants duration exposure.
```

This creates reinvestment risk: principal comes back just when available reinvestment rates are lower.

### Scenario 2: Investor Buys Putable Bonds for Downside Protection

An investor buys putable bonds because they are worried rates might rise.

Rates rise.

Straight bonds decline sharply, but the putable bonds hold value better because the investor can sell them back to the issuer.

Implication:

```text
Effective duration shortens as the put option moves in the money.
```

The investor has less price downside, but usually accepts a lower yield upfront for that protection.

### Scenario 3: Mortgage Portfolio During Falling Rates

A portfolio manager owns mortgage-backed securities.

Rates fall.

Homeowners refinance.

Principal returns earlier than expected, and the securities stop behaving like long-duration assets. Their effective duration contracts.

Implication:

```text
The portfolio loses duration exactly when the manager may want to keep it.
```

This is a major reason mortgage portfolios can require active hedging.

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Use modified duration for a callable bond | Modified duration assumes fixed cash flows | Use effective duration |
| Forget that OAS is held constant | Then you mix interest rate risk with spread risk | Shift the benchmark curve, keep OAS fixed |
| Use 30 instead of 0.0030 for a 30 bps shock | Basis points must be converted to decimals | 30 bps = 0.0030 |
| Reverse $PV_-$ and $PV_+$ | Rates down usually means price up | Numerator is $PV_- - PV_+$ |
| Assume effective duration captures all yield curve risk | It assumes a parallel shift | Use key rate duration for nonparallel shifts |
| Think callable duration rises when rates fall | The call caps upside | Callable duration usually shortens when rates fall |
| Think putable duration rises when rates rise | The put floors downside | Putable duration usually shortens when rates rise |
| Ignore one-sided duration near the money | Two-sided duration averages away asymmetry | Use one-sided duration for directional option behavior |

## Memory Hooks

```text
Effective = cash flows can Effectively change.
```

```text
Callable: rates fall, issuer calls, duration collapses.
```

```text
Putable: rates rise, investor puts, duration collapses.
```

```text
Effective duration shocks the curve; OAS stays still.
```

## Exam Decision Checklist

When you see a duration question, ask:

1. Does the bond have an embedded option?
2. Are cash flows fixed or interest-rate dependent?
3. Is the question about a parallel benchmark curve shift?
4. Is the spread supposed to stay constant?
5. Is the bond near the option exercise boundary?
6. Would one-sided duration reveal asymmetry?
7. Is the question actually about nonparallel curve movement?

Then choose:

| Situation | Measure |
|---|---|
| Option-free bond, fixed cash flows | [[Modified duration]] |
| Embedded option, parallel curve shift | [[Level 2/Generated Notes/07 - Fixed Income/Effective Duration]] |
| Embedded option, asymmetric rate response | [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]] |
| Nonparallel curve movement | [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]] |
| Curvature in price response | [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]] |

## Related Concepts

- [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]]
- [[Modified duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Effective Convexity]]
- [[Level 2/Generated Notes/07 - Fixed Income/One-Sided Durations]]
- [[Level 2/Generated Notes/07 - Fixed Income/Key Rate Duration]]
- [[Callable bond]]
- [[Putable bond]]
- [[Embedded option]]
- [[Binomial Interest Rate Tree]]
- [[Mortgage-backed security]]
