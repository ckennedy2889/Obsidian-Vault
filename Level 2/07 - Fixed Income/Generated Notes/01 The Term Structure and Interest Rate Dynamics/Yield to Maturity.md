---
title: Yield to Maturity
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, bond-yields]
aliases: [YTM, Yield-to-maturity, Yield to redemption, Redemption yield, Promised yield]
---

# Yield to Maturity

## The Real-World Analogy

Think of a bond as a rental property with scheduled rent checks and a final sale price already written into the contract.

The [[Yield to maturity|yield to maturity]] is the single annual return number that makes today's purchase price exactly equal to the present value of all those promised future payments. It is like asking:

> "If I paid this price today and every promised cash flow arrived exactly as scheduled, what one constant return would make the math balance?"

That "one constant return" language matters. A real bond has many dated cash flows, and the market may use different rates for different dates. YTM compresses the whole bond into one internal rate of return. Useful, but dangerous if you forget what has been compressed.

## Plain-English Definition

[[Yield to maturity]] is the [[Internal rate of return|internal rate of return]] on a bond's promised cash flows, assuming the investor buys the bond at its current full price and holds it to maturity.

Mechanically, it is the single [[Discount rate]] that equates:

```text
Today's full bond price
  =
Present value of all promised coupons and principal
```

For an option-free, default-free bond, YTM is often called the bond's promised yield. It is "promised" because the calculation uses the scheduled cash flows, not because the investor is guaranteed to realize that return.

## Why CFA Tests This

CFA tests YTM because it is the market's common shorthand for bond return, but Level II wants you to know exactly where that shorthand breaks.

The central exam idea is:

```text
YTM is a one-rate summary.
Spot rates are the arbitrage-free pricing engine.
Realized return depends on what actually happens.
```

If the [[Yield curve]] is flat, one rate may be a reasonable shortcut. If the curve is upward sloping, downward sloping, or twisting, each cash flow belongs to a different maturity and should be discounted at that maturity's [[Spot rate]]. YTM still exists, but it becomes a blended summary of those spot rates rather than the true rate attached to every cash flow.

## Formula and Derivation

For an annual-pay bond with price $P_0$, coupon $C$, face value $F$, maturity $T$, and annual YTM $y$:

$$
P_0=\sum_{t=1}^{T}\frac{C}{(1+y)^t}+\frac{F}{(1+y)^T}
$$

Equivalently:

$$
P_0=\frac{C}{1+y}+\frac{C}{(1+y)^2}+\cdots+\frac{C+F}{(1+y)^T}
$$

The derivation is just the time value of money applied to every promised payment, with one important restriction: every cash flow is discounted using the same rate $y$.

That is why YTM is an [[Internal rate of return]] problem. The bond's market price is known. The promised cash flows are known. The unknown is the rate that makes the present value equation balance.

For a semiannual-pay bond, the equation uses the semiannual coupon and semiannual yield:

$$
P_0=\sum_{t=1}^{2T}\frac{C/2}{(1+y_{sa})^t}+\frac{F}{(1+y_{sa})^{2T}}
$$

Then the quoted annual yield on a semiannual bond basis is usually:

$$
\text{Quoted YTM}=2y_{sa}
$$

Do not mix the periodic yield, the quoted annual yield, and the effective annual yield. The exam loves that little trap door.

## Full Price Versus Flat Price

The YTM equation uses the bond's [[Full price]], also called the dirty price:

$$
\text{Full price}=\text{Flat price}+\text{Accrued interest}
$$

Why? Because the buyer pays the seller compensation for the coupon interest earned since the last coupon date. The present value equation must match the actual cash amount exchanged for the bond, not just the quoted clean price.

Exam implication: if a question gives a flat price and accrued interest, add them before solving for YTM unless the prompt clearly says the price is already full.

## YTM Versus Spot Rates

A [[Spot rate]] is the discount rate for one cash flow at one maturity. If a bond has three annual cash flows, arbitrage-free valuation discounts each cash flow at its own spot rate:

$$
P_0=\frac{CF_1}{(1+z_1)^1}+\frac{CF_2}{(1+z_2)^2}+\cdots+\frac{CF_T}{(1+z_T)^T}
$$

where $z_t$ is the spot rate for maturity $t$.

YTM instead asks for one rate $y$ that reproduces that same price:

$$
P_0=\frac{CF_1}{(1+y)^1}+\frac{CF_2}{(1+y)^2}+\cdots+\frac{CF_T}{(1+y)^T}
$$

So, for a coupon bond:

```text
Spot-rate pricing: each date gets its own rate.
YTM pricing: every date is forced through one blended rate.
```

This is why YTM is often described as a complicated weighted average of the spot rates. It is not a simple arithmetic average. The weights depend on the size and timing of the bond's cash flows. Because the principal repayment is usually the largest cash flow, YTM is often pulled toward the final maturity spot rate.

For a [[Zero-coupon bond]], there is only one cash flow. No blending is needed. The zero-coupon bond's YTM for maturity $T$ equals the $T$-period spot rate.

## YTM Versus Forward Rates

[[Forward rate|Forward rates]] are the future one-period rates implied by today's spot curve. A multi-period spot rate is linked to the chain of forward rates through no-arbitrage.

In simple annual terms:

$$
(1+z_2)^2=(1+z_1)(1+f_{1,1})
$$

More generally:

$$
(1+z_T)^T=(1+f_0)(1+f_1)\cdots(1+f_{T-1})
$$

This gives the hierarchy:

```text
Forward rates imply spot rates.
Spot rates price each cash flow.
YTM summarizes the whole bond price as one rate.
```

The Level II trap is to treat YTM as if it were the expected future return. It is not. Even if the forward curve becomes the future spot curve, the investor's realized return on a coupon bond depends on reinvestment rates and the holding period.

## When YTM Equals Realized Return

YTM equals the investor's realized compound return only if all three conditions hold:

| Condition | Why it matters | What breaks if it fails |
|---|---|---|
| The bond is held to maturity | YTM is solved using all cash flows through maturity | Selling early introduces price risk |
| All promised payments are made in full and on time | The YTM equation uses promised coupons and principal | Default, delay, or restructuring changes cash flows |
| Coupons are reinvested at the original YTM | Compound return requires interim coupons to earn the same rate | Actual reinvestment rates differ as market rates move |

The reinvestment assumption is usually the least realistic. If rates fall, coupons get reinvested at lower rates, reducing realized return. If rates rise, coupons may be reinvested at higher rates, but the bond's market price falls if sold before maturity.

That is the deeper mechanism:

```text
YTM assumes a constant compound rate.
Coupon bonds produce interim cash flows.
Interim cash flows must be reinvested somewhere.
Therefore realized return depends on actual reinvestment rates.
```

## Worked Numerical Example

Suppose a three-year, annual-pay bond has:

| Input | Value |
|---|---:|
| Face value | $1,000 |
| Coupon rate | 4% |
| Annual coupon | $40 |
| One-year spot rate, $z_1$ | 5% |
| Two-year spot rate, $z_2$ | 6% |
| Three-year spot rate, $z_3$ | 7% |

First, price the bond using spot rates:

$$
P_0=\frac{40}{1.05}+\frac{40}{(1.06)^2}+\frac{1{,}040}{(1.07)^3}
$$

$$
P_0=38.095+35.600+848.950=922.645
$$

Now solve for the single YTM $y$:

$$
922.645=\frac{40}{1+y}+\frac{40}{(1+y)^2}+\frac{1{,}040}{(1+y)^3}
$$

Using a financial calculator:

| Key | Input |
|---|---:|
| $N$ | 3 |
| $PV$ | -922.645 |
| $PMT$ | 40 |
| $FV$ | 1,000 |
| CPT $I/Y$ | 6.9446% |

So:

$$
y\approx6.94\%
$$

Notice the intuition check:

$$
5\%<6.94\%<7\%
$$

The YTM sits between the short and long spot rates, and it is close to the three-year spot rate because the final principal-heavy cash flow dominates the bond's value.

## Price, Coupon, and Par Relationships

For a plain fixed-rate bond:

| Relationship | Price result | Intuition |
|---|---|---|
| Coupon rate = YTM | Bond trades at par | Coupon exactly matches the market-required yield |
| Coupon rate > YTM | Bond trades above par | Coupon is generous, so investors bid up the price |
| Coupon rate < YTM | Bond trades below par | Coupon is stingy, so price must fall to raise the yield |

This is not just a memorization rule. It comes directly from the present value equation. A higher coupon increases promised cash flows. If the discount rate is lower than that coupon rate, those cash flows are worth more than par. If the discount rate is higher, the same cash flows are worth less than par.

## Comparison Table

| Concept | What it means | Best use | Main trap |
|---|---|---|---|
| [[Yield to maturity]] | One IRR that prices the entire bond | Quoting and comparing promised bond yields | Treating it as guaranteed realized return |
| [[Spot rate]] | Discount rate for one zero-coupon cash flow at a specific maturity | Arbitrage-free valuation | Forgetting each maturity has its own rate |
| [[Forward rate]] | Rate implied today for a future borrowing/lending period | No-arbitrage term structure analysis | Treating it as a certain forecast |
| [[Par rate]] | Coupon rate/YTM that makes a bond trade at par | Building and interpreting the par curve | Treating it as the spot rate for long maturities |
| [[Realized return]] | Actual return earned over the investor's holding period | Performance measurement | Assuming it must equal original YTM |

## Exam Traps

| Trap | Why it is tempting | Correct exam reflex |
|---|---|---|
| "YTM is the expected return." | YTM looks like a return number | Say "only if held to maturity, no default, coupons reinvested at YTM" |
| "Use YTM to discount every cash flow." | The YTM equation does exactly that | For arbitrage-free valuation, use spot rates by maturity |
| "YTM equals the final maturity spot rate." | Both refer to the same final maturity | True for zero-coupon bonds, generally false for coupon bonds |
| "Flat price goes into the calculator." | Flat price is the quoted bond price | Use full price when solving the cash flow equation |
| "Annual and semiannual yields are comparable as quoted." | Both are called yield | Match periodicity or convert to effective annual yield |
| "Higher YTM always means better realized return." | Higher yield feels like higher return | Check credit risk, embedded options, reinvestment assumptions, and price path |

## Memory Hooks

YTM is the bond's "one-number story." Spot rates are the actual chapter-by-chapter discount rates.

Use this chain under exam pressure:

```text
One cash flow? YTM = spot rate.
Many cash flows? YTM = blended IRR.
Need arbitrage-free price? Use spot rates.
Need actual investor outcome? Check holding period, default, and reinvestment.
```

And for the calculator:

```text
N = periods
PV = negative full price
PMT = coupon per period
FV = face value
CPT I/Y = periodic YTM
```

## Related Concepts

- [[Bond price]]
- [[Coupon rate]]
- [[Discount rate]]
- [[Full price]]
- [[Flat price]]
- [[Accrued interest]]
- [[Internal rate of return]]
- [[Spot rate]]
- [[Forward rate]]
- [[Par rate]]
- [[Par curve]]
- [[Yield curve]]
- [[Realized return]]
- [[Reinvestment risk]]
- [[Yield-to-worst]]
- [[Yield duration]]
