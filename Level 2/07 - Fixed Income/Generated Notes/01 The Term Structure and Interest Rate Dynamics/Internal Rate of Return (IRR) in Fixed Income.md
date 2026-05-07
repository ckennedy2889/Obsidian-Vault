---
title: Internal Rate of Return (IRR) in Fixed Income
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, irr, yield-to-maturity, realized-return]
aliases: [IRR in fixed income, bond IRR, internal rate of return for bonds, promised yield, realized IRR, horizon yield]
---

# Internal Rate of Return (IRR) in Fixed Income

## The Real-World Analogy

Think of a bond as a machine with cash coming out of it at scheduled dates.

You pay a price today. Then the machine is expected to spit out coupons, principal, sale proceeds, or recovery value if something goes wrong. The [[Internal rate of return|internal rate of return]] is the single compound return that makes the price you paid exactly line up with the cash you receive.

In fixed income, IRR shows up under different names depending on which cash flows you feed into the machine:

```text
Promised cash flows through maturity -> yield to maturity
Actual holding-period cash flows -> realized return or horizon yield
Default cash flows plus recovery -> default-scenario IRR
```

Same math. Different cash-flow story.

## Plain-English Definition

In fixed income, IRR is the discount rate that equates the present value of a bond's cash flows to its current price.

For a standard coupon bond:

$$
P_0
=
\sum_{t=1}^{T}\frac{CF_t}{(1+r)^t}
$$

where:

| Term | Meaning |
|---|---|
| $P_0$ | Price paid today, usually the full price |
| $CF_t$ | Cash flow received at time $t$ |
| $r$ | Periodic IRR |
| $T$ | Number of periods in the cash-flow horizon |

If the cash flows are the bond's promised coupons and principal through maturity, the IRR is [[Yield to maturity|yield to maturity]].

If the cash flows are what the investor actually receives over a shorter holding period, the IRR is the realized holding-period return or [[Horizon yield]].

If the bond defaults and the investor receives recovery instead of full principal, the IRR is the default-scenario realized return.

## The Big Idea

The most important distinction is:

```text
YTM = IRR on promised cash flows.
Realized IRR = IRR on actual cash flows.
```

The math may look identical, but the economic meaning changes completely.

YTM answers:

> If every promised payment arrives exactly as scheduled and I hold to maturity, what one return makes the bond price fair?

Realized IRR answers:

> Given what actually happened to coupons, reinvestment, sale price, default, or recovery, what return did I really earn?

That is why CFA treats YTM carefully. YTM is useful, but it is not automatically the investor's expected return or realized return.

## IRR And Yield To Maturity

For an annual-pay bond with coupon $C$, face value $F$, price $P_0$, and maturity $T$, the YTM is the IRR $y$ that solves:

$$
P_0
=
\frac{C}{1+y}
+
\frac{C}{(1+y)^2}
+
\cdots
+
\frac{C+F}{(1+y)^T}
$$

Or more compactly:

$$
P_0
=
\sum_{t=1}^{T}\frac{C}{(1+y)^t}
+
\frac{F}{(1+y)^T}
$$

This is an IRR equation because the price and promised cash flows are known, and the unknown is the discount rate that balances the equation.

For a zero-coupon bond, there is only one cash flow:

$$
P_0 = \frac{F}{(1+y)^T}
$$

So:

$$
y = \left(\frac{F}{P_0}\right)^{1/T}-1
$$

For a coupon bond, you usually solve for $y$ using a financial calculator or spreadsheet because the equation is a polynomial.

## Why YTM Is A Blended Rate

In arbitrage-free valuation, each cash flow should be discounted at the [[Spot rate]] for its own maturity:

$$
P_0
=
\frac{CF_1}{(1+z_1)}
+
\frac{CF_2}{(1+z_2)^2}
+
\cdots
+
\frac{CF_T}{(1+z_T)^T}
$$

YTM forces those cash flows through one rate:

$$
P_0
=
\frac{CF_1}{(1+y)}
+
\frac{CF_2}{(1+y)^2}
+
\cdots
+
\frac{CF_T}{(1+y)^T}
$$

That means YTM is a one-rate summary of a multi-rate valuation.

The intuition:

```text
Spot rates = each cash flow gets its own discount rate.
YTM = one IRR summarizes the whole cash-flow package.
```

For a coupon bond, YTM behaves like a weighted average of the spot rates, but not a simple arithmetic average. The weights depend on the present value importance of each cash flow. Since principal is usually the largest cash flow, YTM is often pulled toward the final maturity spot rate.

For a zero-coupon bond, there is only one cash flow, so:

```text
Zero-coupon bond: YTM = matching maturity spot rate
Coupon bond: YTM generally differs from matching maturity spot rate
```

## IRR, Expected Return, And Realized Return

YTM equals realized compound return only under strict conditions:

| Condition | Why it matters |
|---|---|
| Hold the bond to maturity | Otherwise sale price enters the return calculation |
| No default or delayed payment | YTM uses promised cash flows |
| Reinvest coupons at the original YTM | Coupon bonds generate interim cash that must earn something |

The reinvestment condition is the quiet trap. A coupon bond is not one final cash flow. It pays coupons along the way. To actually earn the original YTM as a compound return, those coupons must be reinvested at the same YTM.

If reinvestment rates differ, realized return differs.

If the bond is sold before maturity, realized return also depends on the sale price.

If the issuer defaults, realized return depends on recovery amount and default timing.

## Horizon Yield

[[Horizon yield]] is the IRR over the investor's actual investment horizon, which may be shorter than the bond's maturity.

For a simple one-period holding period:

$$
\text{Realized return}
=
\frac{\text{Coupon received}+\text{Sale price}-\text{Purchase price}}
{\text{Purchase price}}
$$

For a multi-period horizon:

$$
\text{Horizon yield}
=
\left(
\frac{\text{Future value of coupons}+\text{Sale price or redemption value}}
{\text{Purchase price}}
\right)^{1/H}
-1
$$

where $H$ is the holding period in years.

This is still IRR logic. The difference is that the ending value includes what actually happens by the horizon date:

```text
Coupons received
+ reinvestment income on coupons
+ sale price or redemption value
= ending value
```

## Worked Example: YTM As Promised IRR

Suppose a 3-year annual-pay bond has:

| Input | Value |
|---|---:|
| Face value | USD 100 |
| Coupon rate | 5% |
| Annual coupon | USD 5 |
| Current full price | USD 85.49 |

The YTM is the IRR that solves:

$$
85.49
=
\frac{5}{1+y}
+
\frac{5}{(1+y)^2}
+
\frac{105}{(1+y)^3}
$$

Using a financial calculator:

| Key | Input |
|---|---:|
| $N$ | 3 |
| $PV$ | -85.49 |
| $PMT$ | 5 |
| $FV$ | 100 |
| CPT $I/Y$ | 10.93% |

So the promised IRR is approximately:

$$
y = 10.93\%
$$

Interpretation:

```text
If the investor buys at 85.49,
receives all promised coupons and principal,
holds to maturity,
and reinvests coupons at 10.93%,
then the compound return equals 10.93%.
```

That is a lot of "ifs." CFA cares about those "ifs."

## Worked Example: Realized IRR Over A Short Horizon

Use the same bond:

```text
Purchase price = 85.49
Annual coupon = 5
Original YTM = 10.93%
```

Now suppose the investor sells after one year. Right after purchase, market yields rise to 12%, so after one coupon is received, the remaining 2-year bond is priced at a 12% yield.

Sale price at the end of Year 1:

$$
\text{Sale price}
=
\frac{5}{1.12}
+
\frac{105}{(1.12)^2}
$$

$$
\text{Sale price}
=
4.4643+83.7054
=
88.1697
$$

Ending value after one year:

$$
\text{Ending value}
=
\text{Coupon}+\text{Sale price}
=
5+88.1697
=
93.1697
$$

One-year realized IRR:

$$
\text{Realized IRR}
=
\frac{93.1697}{85.49}-1
=
8.98\%
$$

The investor's realized return is lower than the original YTM because rates rose, pushing down the sale price.

The mechanism:

```text
Original YTM looked attractive.
But the investor did not hold to maturity.
Sale price mattered.
Higher market yield lowered the sale price.
Realized IRR fell below original YTM.
```

## Default Scenario IRR

For credit-risky bonds, YTM is often called a promised yield because it assumes promised cash flows are paid. But if the issuer defaults, the actual cash flows change.

In default analysis, IRR can be calculated using the recovery value received at default.

Suppose an investor pays USD 89.36 for a 3-year zero-coupon corporate bond with USD 100 face value. If the bond does not default, it pays USD 100 at maturity.

No-default IRR:

$$
89.36 = \frac{100}{(1+r)^3}
$$

$$
r=\left(\frac{100}{89.36}\right)^{1/3}-1
=3.82\%
$$

Now suppose the bond defaults at the end of Year 2 and the investor receives recovery of USD 58.25.

Default-in-Year-2 IRR:

$$
89.36=\frac{58.25}{(1+r)^2}
$$

$$
r=\left(\frac{58.25}{89.36}\right)^{1/2}-1
= -19.26\%
$$

Interpretation:

```text
The original yield was based on promised payment.
The default IRR is based on recovery payment.
Lower realized cash flow means lower realized IRR.
Earlier default usually produces a more severe IRR hit.
```

## Periodicity Trap

IRR is a periodic rate. Bond yields are often quoted using market conventions.

For a semiannual-pay bond, the calculator solves for a semiannual IRR:

$$
y_{\text{periodic}} = y_{\text{semiannual}}
$$

The quoted bond-equivalent yield is:

$$
\text{BEY}=2y_{\text{semiannual}}
$$

The effective annual yield is:

$$
\text{EAY}=(1+y_{\text{semiannual}})^2-1
$$

Do not mix them.

```text
Calculator periodic IRR
  != quoted annual bond yield
  != effective annual yield
```

## IRR Versus Other Fixed-Income Return Concepts

| Concept | What it is | Cash flows used | Main trap |
|---|---|---|---|
| [[Yield to maturity]] | IRR on promised cash flows through maturity | Coupons plus principal | Treating it as guaranteed realized return |
| [[Spot rate]] | Zero-coupon yield for one maturity | One cash flow | Using YTM instead for arbitrage-free valuation |
| [[Horizon yield]] | IRR over investor's actual horizon | Coupons, reinvestment income, sale/redemption value | Ignoring sale price or reinvestment rate |
| [[Realized return]] | Actual return earned | Actual cash flows | Assuming it must equal original YTM |
| Default-scenario IRR | IRR conditional on default timing and recovery | Recovery value, maybe prior coupons | Forgetting recovery replaces promised principal |
| [[Expected Return]] | Probability-weighted average expected outcome | Scenario-weighted cash flows/returns | Confusing expected return with promised yield |

## Exam Traps

| Trap | Correct reflex |
|---|---|
| "YTM is the expected return." | YTM is promised IRR. Expected return adjusts for default, reinvestment, sale price, and scenario probabilities. |
| "YTM is guaranteed if I buy the bond." | Only if held to maturity, no default, and coupons reinvested at YTM. |
| "A coupon bond's YTM equals its final spot rate." | Only zero-coupon YTM equals the matching spot rate. Coupon-bond YTM is blended. |
| "IRR is always annual." | IRR is periodic unless converted. Match the compounding convention. |
| "Higher YTM means better investment." | Higher yield may reflect credit risk, liquidity risk, call risk, or distressed pricing. |
| "Default IRR uses promised principal." | Default IRR uses actual recovery and any cash flows received before default. |
| "Realized return ignores reinvestment." | Multi-period realized return includes coupon reinvestment income. |

## Memory Hooks

```text
IRR is the rate that makes price = PV of cash flows.
```

```text
YTM = promised IRR.
Horizon yield = actual-horizon IRR.
Default IRR = recovery-cash-flow IRR.
```

```text
YTM tells the contract story.
Realized IRR tells what actually happened.
```

## Can You Now?

- Describe why YTM is an IRR on promised bond cash flows.
- Explain why coupon-bond YTM differs from spot-rate valuation.
- Calculate a simple YTM using price, coupon, face value, and maturity.
- Calculate realized IRR over a shorter holding period.
- Interpret how default timing and recovery affect realized IRR.
- Identify when YTM is not a reliable estimate of expected or realized return.

## Related Concepts

- [[Yield to maturity]]
- [[Internal rate of return]]
- [[Spot rate]]
- [[Forward rate]]
- [[Horizon yield]]
- [[Realized return]]
- [[Expected Return]]
- [[Reinvestment risk]]
- [[Default risk]]
- [[Recovery rate]]
- [[Probability of Default]]
- [[Loss Given Default]]
