---
title: Binomial Interest Rate Tree
subject: Fixed Income
tags: [CFA-L2, FixedIncome, BinomialTree, ArbitrageFreeValuation]
aliases: [binomial tree, interest rate tree, calibrated interest rate tree, lognormal binomial tree, binomial interest rate tree formula]
---

# Binomial Interest Rate Tree

## The Real-World Analogy

A [[Binomial Interest Rate Tree]] is like building a weather forecast for interest rates.

If tomorrow's weather can be warmer or cooler, and the day after that can branch again from whichever weather actually happened, you get a tree of possible futures. A bond with no embedded option can often be valued with the current [[Spot curve]]. But a bond with an [[Embedded options|embedded option]] needs a weather map, because the issuer or investor may act differently depending on which rate path occurs.

For a callable bond, low future rates make the issuer more likely to call the bond. For a putable bond, high future rates make the investor more likely to put the bond. The tree gives us the possible future rate states where those decisions can be tested node by node.

## Plain-English Definition

A binomial interest rate tree is a recombining lattice of possible future one-period interest rates, usually short rates or one-period forward rates.

At each node, the rate can move:

```text
          up rate
current <
          down rate
```

"Binomial" means there are two branches from each node. "Recombining" means an up-then-down path lands at the same node as a down-then-up path:

```text
t=0          t=1            t=2

                            R_uu
              R_u     ----<
R_0     ----<                R_ud = R_du
              R_d     ----<
                            R_dd
```

That recombining feature keeps the tree manageable. A non-recombining tree would explode into many separate paths. A recombining tree keeps only $n+1$ nodes at time $n$.

## Why CFA Tests This

CFA tests binomial interest rate trees because they connect four ideas that are easy to memorize separately but hard to apply under pressure:

| Idea | Why it matters |
|---|---|
| [[Arbitrage-Free Valuation Framework]] | The tree must price benchmark bonds correctly. |
| [[Term structure]] | The tree must be consistent with today's observed curve. |
| [[Volatility]] | Higher volatility spreads future rate nodes farther apart. |
| [[Backward Induction]] | Bond values are solved from maturity back to today. |

The exam trap is thinking the tree is just a forecast. It is not mainly a prediction device. It is a valuation device. The tree is built so that, after discounting cash flows through it, benchmark bonds come out at their observed market prices.

## The Formula

In the CFA lognormal binomial tree, adjacent rates in the same nodal period are related by:

$$
R_u = R_d e^{2\sigma\sqrt{t}}
$$

where:

| Term | Meaning | Intuition |
|---|---|---|
| $R_u$ | Upper node rate | The higher possible one-period rate at that date |
| $R_d$ | Lower node rate | The lower possible one-period rate at that date |
| $\sigma$ | Assumed annualized interest rate volatility | How violently rates can move |
| $t$ | Length of the time step in years | Scales volatility to the period length |
| $e^{2\sigma\sqrt{t}}$ | Multiplicative spacing factor | How much bigger the upper rate is than the lower rate |

For an annual tree, $t=1$, so:

$$
R_u = R_d e^{2\sigma}
$$

## The Intuition Behind The Formula

The formula looks strange until you realize it is not saying:

> Add some number of percentage points to the lower rate.

It is saying:

> Space the rates symmetrically in log-rate space, then convert back into ordinary rates.

That one sentence is the whole engine.

### Step 1: Why use log rates?

The common CFA setup assumes rates are [[Lognormal distribution|lognormal]]. That means the rate itself is not normally distributed, but the natural log of the rate is:

$$
\ln(R) \sim \text{normal}
$$

This matters because ordinary normal rates can go negative. If a model says:

$$
R = \text{center} \pm \text{spread}
$$

then a large enough downward move can produce a negative rate. A lognormal model avoids that because:

$$
R = e^{\ln(R)}
$$

An exponential is always positive. The model can produce tiny rates, but not negative rates.

That is the first intuition: lognormal trees model percentage-type moves, not additive basis-point moves.

### Step 2: Why is the gap based on $\sigma\sqrt{t}$?

Volatility is quoted as an annual standard deviation. If one year of volatility is $\sigma$, then a shorter or longer time step scales with the square root of time:

$$
\text{period volatility} = \sigma\sqrt{t}
$$

This is the same square-root-of-time idea used across finance. Variance grows with time, so standard deviation grows with the square root of time.

### Step 3: Why two standard deviations?

The upper and lower rates are placed symmetrically around a middle log-rate.

In log space:

$$
\ln(R_u) = \text{center} + \sigma\sqrt{t}
$$

$$
\ln(R_d) = \text{center} - \sigma\sqrt{t}
$$

The upper node is one period-standard-deviation above the center. The lower node is one period-standard-deviation below the center. Therefore the distance from lower to upper is:

$$
\ln(R_u) - \ln(R_d)
= (\text{center} + \sigma\sqrt{t}) - (\text{center} - \sigma\sqrt{t})
$$

The center cancels:

$$
\ln(R_u) - \ln(R_d) = 2\sigma\sqrt{t}
$$

That is why the exponent has a $2$. It is not an arbitrary CFA nuisance. It is the full distance from one standard deviation below the center to one standard deviation above the center.

### Step 4: Why exponentiate?

Use the log rule:

$$
\ln(R_u) - \ln(R_d) = \ln\left(\frac{R_u}{R_d}\right)
$$

So:

$$
\ln\left(\frac{R_u}{R_d}\right)=2\sigma\sqrt{t}
$$

Exponentiate both sides:

$$
\frac{R_u}{R_d}=e^{2\sigma\sqrt{t}}
$$

Rearrange:

$$
R_u = R_d e^{2\sigma\sqrt{t}}
$$

The formula is just the lognormal assumption translated back into rates.

## Multiplicative Versus Additive Spacing

The formula says the ratio between adjacent rates is fixed:

$$
\frac{R_u}{R_d}=e^{2\sigma\sqrt{t}}
$$

It does not say the difference is fixed:

$$
R_u - R_d \ne \text{constant}
$$

That distinction is the intuition CFA wants.

| Model style | Rate spacing | What it means | Main implication |
|---|---|---|---|
| Additive or normal-style | $R_u - R_d$ is fixed | Rates move by the same number of percentage points | Negative rates are possible |
| Lognormal binomial tree | $R_u / R_d$ is fixed | Rates move by the same proportion | Rates stay nonnegative |

If $\sigma=20\%$ and $t=1$, then:

$$
e^{2(0.20)} = e^{0.40} = 1.4918
$$

So the upper rate is 1.4918 times the lower rate. If the lower rate is 3.00%, the upper rate is:

$$
3.00\% \times 1.4918 = 4.4754\%
$$

If the lower rate is 8.00%, the upper rate is:

$$
8.00\% \times 1.4918 = 11.9344\%
$$

Same ratio, larger basis-point gap. That is why the lognormal model has higher rate volatility in basis-point terms when the level of rates is higher.

## Where Calibration Fits

The volatility formula gives the spacing between rates in a nodal period. It does not, by itself, tell you the absolute level of the rates.

Think of the formula as setting the width of the ladder rungs. Calibration decides where the ladder sits.

```text
Volatility assumption
  |
  v
Spacing between adjacent rates

Current term structure and benchmark bond prices
  |
  v
Level of the rates in each period
```

An [[Arbitrage-free]] tree must satisfy the current market. That means when benchmark bonds are valued through the tree, the model values must equal the observed market prices.

The CFA calibration rules are:

| Calibration idea | Meaning |
|---|---|
| Benchmark bonds must price correctly | The tree must reproduce market prices, preventing model arbitrage. |
| Adjacent rates are separated by $e^{2\sigma\sqrt{t}}$ | Volatility determines the relative spacing. |
| The middle rate is close to the implied one-period forward rate | The tree remains tied to the observed [[Forward curve]]. |

So when a problem gives you one node rate and $\sigma$, you can use the formula to find adjacent node rates. But when building the full tree, you also need the observed term structure to anchor the levels.

## Backward Induction Connection

Once the tree is built, bond valuation works backward.

At each node:

$$
V_t = \frac{0.5(V_{u}+CF_{u})+0.5(V_{d}+CF_{d})}{1+r_t}
$$

The exact notation varies by problem, but the mechanism is always the same:

1. Start at maturity, where the bond's value is known from its final cash flow.
2. Move one step backward.
3. Average the two possible future values using the tree's risk-neutral probabilities.
4. Discount that expected value at the one-period rate for the current node.
5. Repeat until reaching today.

For a callable bond, the issuer chooses the lower value to the bondholder:

$$
V_{\text{callable node}} = \min(\text{continuation value}, \text{call price})
$$

For a putable bond, the investor chooses the higher value:

$$
V_{\text{putable node}} = \max(\text{continuation value}, \text{put price})
$$

This is why a tree is needed. The value of the embedded option depends on what rates are doing at each future decision node.

## Worked Numerical Example

Suppose a one-year nodal period has:

$$
R_d = 4.00\%, \quad \sigma = 15\%, \quad t=1
$$

Use:

$$
R_u = R_d e^{2\sigma\sqrt{t}}
$$

Substitute:

$$
R_u = 4.00\% \times e^{2(0.15)\sqrt{1}}
$$

$$
R_u = 4.00\% \times e^{0.30}
$$

$$
e^{0.30}=1.3499
$$

$$
R_u = 4.00\% \times 1.3499 = 5.3996\%
$$

So the upper rate is approximately:

$$
R_u \approx 5.40\%
$$

Now notice the intuition. The difference is:

$$
5.3996\% - 4.00\% = 1.3996\%
$$

But the model did not start by adding 1.3996 percentage points. It started by multiplying by 1.3499. If the lower rate had been 8.00% with the same volatility, the upper rate would be:

$$
8.00\% \times 1.3499 = 10.7992\%
$$

The basis-point gap would be 279.92 bps, not 139.96 bps, even though volatility is unchanged. This is the mechanical meaning of "higher volatility at higher rates" in a lognormal tree.

## Rule To Mechanism To Exam Implication

| Rule | Why it exists | Mechanism | What can fail | Exam implication |
|---|---|---|---|---|
| Adjacent rates satisfy $R_u=R_d e^{2\sigma\sqrt{t}}$ | The tree assumes lognormal rates | Upper and lower log rates are one standard deviation above and below the center | Treating rates as additive changes the spacing | Use multiplication, not addition |
| Rates are nonnegative | Lognormal rates are exponentials | $R=e^{\ln(R)}$ | A normal model can produce negative rates | Do not say lognormal allows negative rates |
| Up and down probabilities are 50/50 in the CFA tree | Risk-neutral valuation simplifies the lattice | Market prices are embedded through calibrated rates | Confusing risk-neutral probabilities with real-world forecasts | Do not interpret 50/50 as "the market thinks up and down are equally likely" |
| The tree must be calibrated | The model must match today's market | Benchmark bonds priced through the tree equal market prices | Uncalibrated trees can misprice bonds | Calibration is what makes the tree arbitrage-free |
| Higher volatility widens the tree | More uncertainty creates more dispersion | $e^{2\sigma\sqrt{t}}$ rises as $\sigma$ rises | Thinking volatility only changes probabilities | Volatility changes node rates and embedded option values |

## Exam Traps

| Trap | Correction |
|---|---|
| Memorizing $R_u = R_d e^{2\sigma\sqrt{t}}$ without knowing why the 2 appears | The up node is one standard deviation above the center and the down node is one below, so the full gap is two standard deviations. |
| Adding $2\sigma\sqrt{t}$ to the lower rate | The formula is multiplicative because it comes from log rates. |
| Treating 50/50 probabilities as real-world forecasts | They are risk-neutral valuation probabilities in the CFA framework. |
| Forgetting calibration | Volatility sets spacing; calibration sets levels. |
| Thinking higher volatility changes option-free bond value in a calibrated tree | A properly calibrated tree should still price option-free benchmark bonds consistently with the curve. |
| Using only the spot curve for callable and putable bonds | Embedded-option decisions require node-by-node valuation through possible future rates. |
| Saying lognormal volatility is constant in basis-point terms | The proportional volatility is constant; the basis-point spread is larger when rates are higher. |

## Memory Hooks

```text
Lognormal tree:
Think logs first, rates second.
```

```text
Why the 2?
Down node is -1 sigma.
Up node is +1 sigma.
Distance from down to up is 2 sigma.
```

```text
Volatility sets the width.
Calibration sets the height.
Backward induction prices the bond.
```

## Related Concepts

- [[Arbitrage-Free Valuation Framework]]
- [[Backward Induction]]
- [[2.04 - Calibrating the Binomial Tree]]
- [[Term Structure Models]]
- [[Forward curve]]
- [[Spot curve]]
- [[Option-Adjusted Spread]]
- [[Effective Duration]]
- [[Callable bond]]
- [[Putable bond]]
- [[Pathwise Valuation]]
