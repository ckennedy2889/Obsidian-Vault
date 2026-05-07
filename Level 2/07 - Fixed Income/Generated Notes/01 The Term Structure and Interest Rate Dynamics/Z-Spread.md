---
title: Z-Spread
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-spreads, z-spread, bond-valuation, spot-rates]
aliases: [Z-spread, zero-volatility spread, zero volatility spread, ZS, zero-volatility spread (Z-spread)]
---

# Z-Spread

## The Real-World Analogy

Imagine the default-free spot curve as the base price of shipping packages by delivery date.

```text
1-year cash flow -> 1-year shipping rate
2-year cash flow -> 2-year shipping rate
3-year cash flow -> 3-year shipping rate
```

Now suppose the package is riskier: maybe it is fragile, harder to insure, or more likely to be delayed. You need to add a risk surcharge to every delivery date.

That risk surcharge is the [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]].

```text
Default-free spot rate for each cash flow
        +
constant risk/liquidity spread
        =
discount rate used for that risky bond cash flow
```

The Z-spread is not just one yield difference at maturity. It is a constant spread added across the entire spot curve.

## Plain-English Definition

The [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]] is the constant spread that must be added to every default-free spot rate so that the present value of a bond's promised cash flows equals its market price.

The "Z" stands for zero volatility.

That means the method assumes no interest rate volatility and fixed promised cash flows. Because of that, it is most appropriate for option-free risky bonds.

## CFA Definition

CFA defines the Z-spread as the constant basis point spread that needs to be added to the implied spot yield curve such that the discounted cash flows of a bond equal its current market price.

Also called:

```text
zero-volatility spread
```

## Why It Matters

The Z-spread is useful because a coupon bond has multiple cash flows.

A simple yield spread compares one bond yield to one benchmark yield. But a bond's value comes from cash flows at many dates:

```text
Coupon 1
Coupon 2
Coupon 3
...
Final coupon + principal
```

Each cash flow should be discounted at the appropriate spot rate for its maturity. The Z-spread respects the full term structure.

That is why the Z-spread is more precise than a simple [[G-spread]] or [[I-spread]] when the yield curve is not flat.

## Pricing Equation

For an annual-pay bond:

$$
P
=
\sum_{t=1}^{N}
\frac{CF_t}{(1+z_t+ZS)^t}
$$

Where:

| Symbol | Meaning |
|---|---|
| $P$ | Current full price of the bond |
| $CF_t$ | Bond cash flow at time $t$ |
| $z_t$ | Default-free spot rate for maturity $t$ |
| $ZS$ | Z-spread |
| $N$ | Number of periods |

For a plain coupon bond:

$$
P
=
\frac{CPN}{(1+z_1+ZS)}
+
\frac{CPN}{(1+z_2+ZS)^2}
+
\cdots
+
\frac{CPN+Par}{(1+z_N+ZS)^N}
$$

The Z-spread is the spread that makes this equation exactly match the market price.

## Why The Spread Is Added To Spot Rates

Spot rates are the correct discount rates for individual zero-coupon cash flows.

A coupon bond is really a package of zero-coupon cash flows:

```text
Coupon in year 1
Coupon in year 2
Coupon in year 3
Principal in final year
```

The benchmark spot curve prices the time value of money for each cash flow. But a risky corporate bond has additional compensation for risks such as:

- [[Credit risk]];
- [[Liquidity risk]];
- possible tax differences;
- market segmentation or technical factors.

The Z-spread is the constant extra spread that represents that compensation across all maturities of the bond's promised cash flows.

## Worked Example: Solve By Testing A Z-Spread

Suppose a two-year corporate bond has:

- Annual coupon: $4.15$
- Par value: $100$
- One-year spot rate: $2.25\%$
- Two-year spot rate: $2.70\%$
- Market price: $101.54$

We want the Z-spread that solves:

$$
101.54
=
\frac{4.15}{(1+0.0225+ZS)}
+
\frac{104.15}{(1+0.0270+ZS)^2}
$$

Try:

$$
ZS = 0.0065 = 65 \text{ bps}
$$

Year 1 discount rate:

$$
0.0225 + 0.0065 = 0.0290 = 2.90\%
$$

Year 2 discount rate:

$$
0.0270 + 0.0065 = 0.0335 = 3.35\%
$$

Discount the year 1 coupon:

$$
\frac{4.15}{1.0290}
=
4.033
$$

Discount the final cash flow:

$$
\frac{104.15}{(1.0335)^2}
=
97.507
$$

Total present value:

$$
4.033 + 97.507 = 101.540
$$

So:

$$
\boxed{ZS = 65 \text{ bps}}
$$

## How To Interpret A Higher Z-Spread

A higher Z-spread generally means investors demand more compensation above the default-free spot curve.

That compensation can reflect:

| Source | Why It Raises The Spread |
|---|---|
| Higher default risk | Investors require compensation for possible nonpayment |
| Lower liquidity | Investors require compensation for harder trading |
| Worse relative value | Bond price is lower relative to benchmark cash flows |
| Technical pressure | Supply/demand imbalance can widen spreads |

Exam interpretation:

```text
Higher Z-spread -> lower price relative to benchmark curve -> more compensation demanded
```

But do not automatically say "higher Z-spread means better investment." A wide spread may be compensation for real risk, or it may indicate undervaluation. You need credit analysis.

## Z-Spread vs Other Spreads

| Spread | Benchmark | Main Idea | Best Use |
|---|---|---|---|
| Nominal spread | Similar-maturity Treasury YTM | Simple YTM difference | Quick rough comparison |
| [[G-spread]] | Actual/interpolated government bond yield | YTM over government yield | Simple government benchmark spread |
| [[I-spread]] | Swap rate | YTM over swap curve | Markets where swaps are better benchmark |
| [[Level 2/Generated Notes/07 - Fixed Income/Z-Spread]] | Spot curve | Constant spread over every spot rate | Option-free risky bond valuation |
| [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]] | Interest rate tree forward rates | Spread after adjusting for embedded option | Bonds with embedded options |

The big conceptual difference:

```text
G-spread and I-spread compare one yield to one benchmark yield.
Z-spread discounts every cash flow using the spot curve plus a constant spread.
OAS adjusts for optionality and interest rate volatility.
```

## Z-Spread vs OAS

For an option-free bond:

$$
OAS \approx ZS
$$

Why?

There is no embedded option to adjust for.

For a callable bond, the issuer owns the call option. That option hurts the investor because the bond may be called when rates fall and the bond price would otherwise rise.

So:

$$
OAS = ZS - \text{call option cost}
$$

For a putable bond, the investor owns the put option. That option helps the investor because the bondholder can put the bond back to the issuer when rates rise.

Using the common formula-sheet convention:

$$
OAS = ZS + \text{put option value}
$$

The exam intuition:

```text
Callable bond:
Z-spread includes compensation for credit/liquidity plus the value lost to the issuer's call.
OAS strips out the option effect.

Putable bond:
The investor owns a valuable put, so the observed Z-spread may be lower than the option-adjusted pure spread.
```

## Why "Zero Volatility" Matters

The term zero-volatility means the spread calculation assumes interest rates do not move randomly.

That assumption is fine for option-free bonds because the promised cash flows do not depend on interest rate paths.

But it is not fine for bonds with embedded options.

For callable and putable bonds, future cash flows depend on interest rate paths:

```text
Rates fall -> callable bond more likely to be called
Rates rise -> putable bond more likely to be put
```

If the model assumes zero volatility, it cannot properly value those path-dependent cash flows.

That is why Z-spread is not the right spread for valuing embedded-option bonds. Use [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]].

## Calculation Logic

In real life, the Z-spread is found by iteration.

There is no simple closed-form shortcut for most coupon bonds.

The process is:

```text
1. Start with the bond's market price.
2. Project promised cash flows.
3. Get the benchmark spot curve.
4. Add a trial spread to every spot rate.
5. Discount each cash flow.
6. Sum present values.
7. Adjust the spread until model price = market price.
```

If the model price is too high, the discount rates are too low, so the Z-spread needs to rise.

If the model price is too low, the discount rates are too high, so the Z-spread needs to fall.

## Exam Traps

| Trap | Correct Thinking |
|---|---|
| Z-spread is just YTM minus Treasury yield | That is closer to nominal/G-spread. Z-spread uses every spot rate |
| Z-spread uses par curve rates | It uses the spot curve, not the par curve |
| Z-spread is best for callable bonds | False. Use OAS for embedded-option bonds |
| Zero volatility means zero credit risk | False. It means zero interest rate volatility in the spread model |
| Higher Z-spread always means cheap bond | It may mean cheap, but it may also mean higher credit/liquidity risk |
| G-spread and Z-spread are always similar | They can differ when the yield curve is steep or cash flows are uneven |
| OAS equals Z-spread for all bonds | Only approximately true for option-free bonds |

## Memory Hook

```text
Z-spread = Zip the same spread onto every spot rate.
```

Another:

```text
G/I = one-point yield comparison.
Z = every-cash-flow spot-curve spread.
OAS = Z after option adjustment.
```

## Exam-Day Checklist

When a vignette mentions Z-spread, ask:

1. Is the bond option-free or does it have an embedded option?
2. Are you discounting cash flows with spot rates?
3. Is the same spread added to every point on the spot curve?
4. Is the question comparing Z-spread to G-spread, I-spread, or OAS?
5. Does a higher spread reflect more risk, lower price, or potential relative value?
6. If the bond is callable or putable, should you switch to OAS?

## Related Concepts

- [[G-spread]]
- [[I-spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Option-Adjusted Spread]]
- [[Spot rates]]
- [[Forward rate]]
- [[Credit risk]]
- [[Liquidity risk]]
- [[Embedded option]]
- [[Callable bond]]
- [[Putable bond]]
- [[Par vs Spot vs Forward Rates]]
