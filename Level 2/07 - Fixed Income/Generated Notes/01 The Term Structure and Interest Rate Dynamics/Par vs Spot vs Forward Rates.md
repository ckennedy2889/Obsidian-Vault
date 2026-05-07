---
title: Par vs Spot vs Forward Rates
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, spot-rates, forward-rates, par-rates, bootstrapping]
aliases: [Par Rates vs Spot Rates vs Forward Rates, Par Curve vs Spot Curve vs Forward Curve, Spot and Forward Rates, Term Structure Rates]
---

# Par vs Spot vs Forward Rates

## One-Minute Version

[[Par rate|Par rates]], [[Spot rate|spot rates]], and [[Forward rate|forward rates]] are three different ways to describe interest rates across time.

| Rate | Plain-English Meaning | Main Use |
|---|---|---|
| [[Par rate]] | The coupon rate that makes a bond trade at exactly par | Build the observable par curve |
| [[Spot rate]] | The yield on a single zero-coupon cash flow paid at a specific maturity | Discount each cash flow directly |
| [[Forward rate]] | The rate locked in today for borrowing or lending during a future period | Link spot rates through no-arbitrage |

The deepest difference is this:

```text
Par rate    = coupon rate that prices a whole coupon bond at 100
Spot rate   = discount rate for one cash flow at one date
Forward rate = marginal future rate implied between two spot dates
```

> [!tip] One-Line Rule
> Par rates are what coupon bonds quote, spot rates are what cash flows need, and forward rates are what no-arbitrage implies between spot dates.

---

## The Par-Spot-Forward Triangle

The "triangle" is the idea that [[Par rate|par rates]], [[Spot rate|spot rates]], and [[Forward rate|forward rates]] are not three independent data sets. They are three translations of the same underlying [[Discount factor|discount factor]] curve.

```text
                 Par rates
            coupon bond at 100
                    |
                    | bootstrapping
                    v
Discount factors <-> Spot rates <-> Forward rates
 PV of $1          zero rates      marginal future rates
```

The cleanest center of the triangle is the discount factor:

$$
DF_T = \frac{1}{(1+z_T)^T}
$$

Once you know the discount factors, you can price any risk-free cash flow. The three rate types are just different ways to talk about those discount factors.

| Triangle move | Formula / method | Intuition |
|---|---|---|
| Par rates -> spot rates | [[Bootstrapping]] | Use each solved short spot rate to solve the next longer spot rate. |
| Spot rates -> discount factors | $DF_T = \frac{1}{(1+z_T)^T}$ | A spot rate is just the yield embedded in the price of one dollar paid at time $T$. |
| Discount factors -> par rate | $\text{Par}_T = \frac{1-DF_T}{\sum_{t=1}^{T}DF_t}$ | The par coupon is the coupon that makes coupon PV plus principal PV equal 100. |
| Spot rates -> forward rates | $(1+z_B)^B=(1+z_A)^A(1+f_{A,B-A})^{B-A}$ | A long zero must match a short zero rolled forward at the implied future rate. |
| One-period forwards -> spot rate | $(1+z_T)^T=(1+z_1)(1+f_{1,1})\cdots(1+f_{T-1,1})$ | The spot rate is the geometric average of the chain of one-period rates. |

The exam-day ordering rule is:

```text
Upward-sloping curve:   par < spot < forward
Downward-sloping curve: par > spot > forward
Flat curve:             par = spot = forward
```

That ordering is not a separate formula to memorize. It comes from averaging.

Forward rates are marginal rates. Spot rates are geometric averages of the one-period rate chain. Par rates are coupon-bond rates, so they are pulled by the earlier coupon cash flows. On an upward-sloping curve, the marginal future rate must be above the average spot rate, and the par rate is usually slightly below the same-maturity spot rate because earlier coupons are discounted at lower short rates.

> [!tip] Memory Hook
> **Forwards build spots; spots build par.** If the curve slopes up, the later marginal rate sits highest: **par < spot < forward**.

---

## LOS Coverage

| CFA task | What you must be able to do |
|---|---|
| Describe relationships among spot rates, forward rates, YTM, returns, and yield curve shape | Know that spot rates price cash flows, forward rates are implied marginal rates, and YTM is a blended single rate |
| Describe bootstrapping | Derive zero-coupon spot rates from the par curve one maturity at a time |
| Describe active bond management assumptions | Understand when the forward curve is treated as the expected future spot curve |

---

## Real-World Analogy: The Hotel Price Board

Imagine a hotel sells three different products.

First, it sells a **one-night stay tonight**. That is like a [[Spot rate]]: price today for one specific future service.

Second, it sells a **three-night package** with breakfast included each morning. That is like a coupon bond. The hotel can quote one package price, but the package contains several dated services. The rate that makes the package "fairly priced" at face value is like the [[Par rate]].

Third, it lets you lock in the price today for **a one-night stay two years from now**. That is like a [[Forward rate]]: the deal is set today, but the borrowing/lending period starts later.

The CFA trick is that these are not separate universes. They are different views of the same term structure. If any one view disagrees with the others, arbitrage pressure should pull them back into alignment.

---

## The Deep Why: Why Do We Need Three Curves?

Fixed-income valuation is brutally specific about timing. A bond is not "one cash flow." A coupon bond is a bundle:

```text
Year 1 coupon
Year 2 coupon
Year 3 coupon + principal
```

Each cash flow arrives at a different date. If interest rates differ by maturity, each date deserves its own discount rate.

That is why [[Spot rate|spot rates]] are the clean valuation tool. A spot rate is attached to a **single payment date**, so it directly answers:

```text
What is $1 paid at time T worth today?
```

The [[discount factor]] is:

$$DF_T = \frac{1}{(1+z_T)^T}$$

where $z_T$ is the T-period spot rate.

A coupon bond's arbitrage-free price is therefore:

$$P_0 = \sum_{t=1}^{T} CF_t \times DF_t$$

or:

$$P_0 = \sum_{t=1}^{T} \frac{CF_t}{(1+z_t)^t}$$

The "why" underneath: if two securities produce identical dated cash flows, they must have the same price. A coupon bond can be replicated by a portfolio of zero-coupon bonds, one zero for each coupon and principal payment. If the coupon bond price differs from the sum of those zeros, arbitrage exists.

So:

```text
Spot rates are the arbitrage-free cash-flow pricing engine.
```

Then why use par rates? Because the market often observes liquid coupon bonds, especially on-the-run government bonds, not a complete set of zero-coupon bonds. Par rates are observable package rates. We use them to uncover the spot curve.

Then why use forward rates? Because once we know spot rates, no-arbitrage tells us the future single-period rates implied between maturities. Forward rates are the marginal rates hiding inside the spot curve.

---

## Definitions

### Par Rate

A [[Par rate]] is the coupon rate that makes a bond price equal to par value, usually 100.

For an annual-pay par bond:

$$100 = \sum_{t=1}^{T} \frac{C}{(1+z_t)^t} + \frac{100}{(1+z_T)^T}$$

The coupon rate $C/100$ that solves this equation is the T-year par rate.

Why does coupon equal YTM when a bond trades at par? Because the coupon rate is exactly the single discount rate that makes the present value of coupons and principal equal face value. If coupon is above the market yield, the bond trades above par. If coupon is below the market yield, it trades below par. At par, coupon rate and YTM meet.

But be careful: the par rate is a yield on a coupon bond. It is not usually the same as the T-year spot rate unless the curve is flat or maturity is one period.

### Spot Rate

A [[Spot rate]] is the interest rate determined today for a risk-free single payment at a specified future date. It is also called a [[zero-coupon rate]] or zero rate.

For a zero-coupon bond paying $1 at time $T$:

$$P_T = \frac{1}{(1+z_T)^T}$$

where $P_T$ is the discount factor and $z_T$ is the T-period spot rate.

Why is this cleaner than YTM? Because there is no coupon reinvestment assumption. A zero-coupon bond has exactly one cash flow. If you buy it and hold it to maturity, the promised yield is mechanically realized, assuming no default.

### Forward Rate

A [[Forward rate]] is an interest rate agreed today for a loan that begins in the future.

Notation:

$$f_{A,B-A}$$

means the forward rate starting at time $A$ and lasting $B-A$ periods.

Example:

$$f_{2,1}$$

means the one-year forward rate beginning two years from now.

The forward rate is not pulled from thin air. It is implied by no-arbitrage from spot rates:

$$(1+z_B)^B = (1+z_A)^A(1+f_{A,B-A})^{B-A}$$

Solving:

$$f_{A,B-A} = \left[\frac{(1+z_B)^B}{(1+z_A)^A}\right]^{\frac{1}{B-A}} - 1$$

Why this formula exists: investing from today to $B$ years must produce the same terminal value as investing from today to $A$ years, then locking in a forward rate from $A$ to $B$. If those two strategies produce different risk-free payoffs at time $B$, arbitrageurs would buy the cheap strategy and sell the expensive one.

---

## The Core Relationship: Average vs. Marginal

The spot rate is like a cumulative GPA. The forward rate is like the next semester grade.

If your cumulative GPA rises from year 1 to year 3, the later semester grades must be above the cumulative average. Same with rates:

```text
Upward-sloping spot curve -> forward rates above spot rates
Downward-sloping spot curve -> forward rates below spot rates
Flat spot curve -> forward rates equal spot rates
```

Why? Because a long spot rate is a geometric average of shorter spot and forward rates:

$$(1+z_T)^T = (1+z_1)(1+f_{1,1})(1+f_{2,1})\cdots(1+f_{T-1,1})$$

If the average is rising, the marginal rates that pull it upward must be higher than the prior average.

---

## Worked Example: Spot Rates Price a Coupon Bond

Suppose a 3-year, annual-pay bond has:

- Face value = $1,000
- Coupon rate = 4%
- Cash flows: $40, $40, $1,040
- Spot rates: $z_1=5\%$, $z_2=6\%$, $z_3=7\%$

Price each cash flow at its own spot rate:

$$P_0 = \frac{40}{1.05} + \frac{40}{(1.06)^2} + \frac{1{,}040}{(1.07)^3}$$

Compute each piece:

$$\frac{40}{1.05} = 38.10$$

$$\frac{40}{(1.06)^2} = \frac{40}{1.1236} = 35.60$$

$$\frac{1{,}040}{(1.07)^3} = \frac{1{,}040}{1.225043} = 848.95$$

So:

$$P_0 = 38.10 + 35.60 + 848.95 = 922.65$$

The bond trades below par because its 4% coupon is low relative to the spot rates used to discount its cash flows.

---

## Worked Example: Forward Rate from Spot Rates

Suppose:

$$z_2 = 4\%, \qquad z_5 = 6\%$$

Find the 3-year forward rate starting 2 years from now:

$$f_{2,3}$$

Use:

$$(1+z_5)^5 = (1+z_2)^2(1+f_{2,3})^3$$

Plug in:

$$(1.06)^5 = (1.04)^2(1+f_{2,3})^3$$

Solve:

$$(1+f_{2,3})^3 = \frac{(1.06)^5}{(1.04)^2}$$

$$(1.06)^5 = 1.338226$$

$$(1.04)^2 = 1.081600$$

$$(1+f_{2,3})^3 = \frac{1.338226}{1.081600} = 1.237274$$

Take the cube root:

$$1+f_{2,3} = 1.237274^{1/3} = 1.0735$$

Therefore:

$$f_{2,3} = 7.35\%$$

Notice $f_{2,3} > z_5 = 6\%$. That is not a typo. Because the spot curve is upward sloping from 4% to 6%, the marginal future rate has to be above the 5-year average to pull the long average up.

---

## Bootstrapping: Par Curve to Spot Curve

The [[par curve]] is observable because coupon-paying benchmark bonds trade in the market. But spot rates are what we need for arbitrage-free valuation. [[Bootstrapping]] is the process of extracting spot rates from par rates one maturity at a time.

The logic:

```text
1-year par rate -> 1-year spot rate
Use 1-year spot rate -> solve 2-year spot rate
Use 1-year and 2-year spot rates -> solve 3-year spot rate
Continue forward
```

That is why it is called bootstrapping. Each answer becomes the input for the next step.

## Worked Example: Bootstrapping

Assume annual-pay par bonds with face value 100.

| Maturity | Par rate |
|---|---:|
| 1 year | 5.00% |
| 2 years | 5.97% |
| 3 years | 6.91% |

### Step 1: One-year spot rate

For a 1-year annual-pay par bond, there is only one cash flow. So:

$$z_1 = 5.00\%$$

### Step 2: Two-year spot rate

The 2-year par bond has coupon 5.97 and principal 100. Its price is 100:

$$100 = \frac{5.97}{1.05} + \frac{105.97}{(1+z_2)^2}$$

Compute first coupon PV:

$$\frac{5.97}{1.05} = 5.6857$$

Subtract from 100:

$$100 - 5.6857 = 94.3143$$

So:

$$94.3143 = \frac{105.97}{(1+z_2)^2}$$

$$(1+z_2)^2 = \frac{105.97}{94.3143} = 1.12358$$

$$1+z_2 = \sqrt{1.12358} = 1.05999$$

$$z_2 \approx 6.00\%$$

### Step 3: Three-year spot rate

The 3-year par bond has coupon 6.91:

$$100 = \frac{6.91}{1.05} + \frac{6.91}{(1.06)^2} + \frac{106.91}{(1+z_3)^3}$$

Compute known PVs:

$$\frac{6.91}{1.05} = 6.5810$$

$$\frac{6.91}{(1.06)^2} = \frac{6.91}{1.1236} = 6.1499$$

Subtract:

$$100 - 6.5810 - 6.1499 = 87.2691$$

So:

$$87.2691 = \frac{106.91}{(1+z_3)^3}$$

$$(1+z_3)^3 = \frac{106.91}{87.2691} = 1.22506$$

$$1+z_3 = 1.22506^{1/3} = 1.0700$$

$$z_3 \approx 7.00\%$$

The par curve gave us package yields. Bootstrapping extracted pure zero-coupon spot rates.

---

## When You See This, Do This

| If the question gives you... | Think... | Do this... |
|---|---|---|
| A zero-coupon bond or single future payment | [[Spot rate]] | Discount with the maturity-matched spot rate |
| A coupon bond priced at 100 | [[Par rate]] | Coupon rate = YTM = par rate |
| A coupon bond with multiple cash flows | Spot curve | Discount each cash flow at its own spot rate |
| Par rates by maturity | Bootstrapping | Solve spot rates from shortest to longest |
| Two spot rates and asks for a future rate | [[Forward rate]] | Use the forward rate model |
| Upward-sloping spot curve | Forward curve above spot curve | Marginal forward rates exceed average spot rates |
| Downward-sloping spot curve | Forward curve below spot curve | Marginal forward rates are below average spot rates |

---

## Common Wrong Reasoning

### Wrong 1: "The par rate is the spot rate."

This is only true for the first maturity in an annual-pay setup, or if the yield curve is flat. A multi-period par rate is the YTM on a coupon bond. It blends cash flows across multiple dates. A spot rate belongs to one date only.

### Wrong 2: "YTM is the correct discount rate for every cash flow."

YTM is a single internal rate that forces the bond price equation to work. It is not the arbitrage-free rate for each dated cash flow unless the spot curve is flat. The arbitrage-free method discounts each cash flow at its own spot rate.

### Wrong 3: "Forward rates are forecasts."

Forward rates are no-arbitrage implied rates. Under pure expectations theory, they may be interpreted as expected future spot rates. But under liquidity preference or other term structure theories, forwards include risk or liquidity premiums. So the safe CFA wording is:

```text
Forward rates are implied by today's spot curve; they are not automatically unbiased forecasts.
```

### Wrong 4: "If the spot curve slopes upward, the forward rate is just a little above the short spot rate."

The forward rate can be above the long spot rate, not just the short spot rate. Why? The long spot rate is an average. To pull an average upward, the marginal later rate must be above the average.

---

## Do Not Confuse With

| Concept | Difference |
|---|---|
| [[Par curve]] | Curve of YTMs/coupon rates for bonds priced at par |
| [[Spot curve]] | Curve of zero-coupon rates used to discount single cash flows |
| [[Forward curve]] | Curve of future rates implied by spot rates |
| [[Yield to maturity]] | One blended rate for an entire coupon bond |
| [[Discount factor]] | Present value of $1 at a future date |
| [[Forward rate agreement]] | A derivative contract based on a forward interest rate |

---

## Minimum Memorization

1. Spot discount factor:

$$DF_T = \frac{1}{(1+z_T)^T}$$

2. Coupon bond arbitrage-free value:

$$P_0 = \sum_{t=1}^{T} \frac{CF_t}{(1+z_t)^t}$$

3. Forward rate model:

$$(1+z_B)^B = (1+z_A)^A(1+f_{A,B-A})^{B-A}$$

4. Solving for forward rate:

$$f_{A,B-A} = \left[\frac{(1+z_B)^B}{(1+z_A)^A}\right]^{\frac{1}{B-A}} - 1$$

5. Bootstrapping:

```text
Par curve -> spot curve
shortest maturity first -> longest maturity last
```

6. Curve shape:

```text
Upward spot curve -> forwards above spots
Downward spot curve -> forwards below spots
Flat curve -> forwards = spots
```

---

## Can I Solve This?

- [ ] I can define par, spot, and forward rates without mixing them.
- [ ] I can explain why spot rates are the correct rates for cash-flow-by-cash-flow valuation.
- [ ] I can compute a forward rate from two spot rates.
- [ ] I can bootstrap a 2-year or 3-year spot rate from par rates.
- [ ] I can explain why an upward-sloping spot curve implies forward rates above spot rates.
- [ ] I can explain why forward rates are implied rates, not necessarily forecasts.
- [ ] I can identify when a question is asking for a par rate, spot rate, or forward rate.

---

## Related Concepts

- [[Spot rate]]
- [[Forward rate]]
- [[Par curve]]
- [[Spot curve]]
- [[Forward curve]]
- [[Discount factor]]
- [[Bootstrapping]]
- [[Zero-coupon bond]]
- [[Yield to maturity]]
- [[Rolling down the yield curve]]
- [[Pure expectations theory]]
