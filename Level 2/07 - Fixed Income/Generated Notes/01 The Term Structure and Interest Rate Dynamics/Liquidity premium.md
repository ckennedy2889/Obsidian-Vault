---
title: Liquidity premium
subject: Fixed Income
tags: [CFA-L2, fixed-income, term-structure, liquidity-preference-theory, forward-rates, yield-curve]
aliases: [Liquidity premium, Liquidity premiums, Term premium]
---

# Liquidity premium

## The Real-World Analogy

Imagine lending money for 25 years instead of 5 years.

Even if you expect short-term rates to stay the same, you may still demand extra yield for the 25-year loan because your money is locked up longer and the bond price will be more sensitive to interest-rate changes. That extra compensation is the [[Liquidity premium]].

```text
Expected future short rate
        +
extra compensation for longer-term risk
        =
forward rate under liquidity preference theory
```

## Plain-English Definition

In Level II Fixed Income, the liquidity premium is the extra yield investors demand for lending long term and bearing greater interest-rate and liquidity risk.

Under [[Liquidity preference theory]]:

$$
\text{Forward rate} = \text{Expected future spot rate} + \text{Liquidity premium}
$$

The theory says the liquidity premium is positively related to maturity. A 25-year bond should generally have a larger liquidity premium than a five-year bond.

Be careful: CFA uses "liquidity premium" in two related but distinct ways. In term-structure theory, it mainly means compensation for long-maturity interest-rate and price uncertainty. In credit analysis, it can also mean compensation for market liquidity risk, such as wide bid-ask spreads or difficulty selling a bond quickly.

## Why CFA Tests This

CFA tests liquidity premium because it changes how you interpret the [[Yield curve]] and [[Forward curve]].

Under pure expectations theory, an upward-sloping curve means the market expects future short rates to rise.

Under liquidity preference theory, an upward-sloping curve could mean:

| Possibility | Explanation |
|---|---|
| Expected future rates are rising | Forward rates are high because expected spot rates are high |
| Expected future rates are flat | Positive liquidity premiums create the upward slope |
| Expected future rates are falling slightly | The liquidity premium may more than offset the expected decline |

So:

```text
Upward-sloping curve does not automatically mean expected rates are rising.
```

## Mechanism

Longer-maturity bonds expose investors to more:

| Risk | Why it matters |
|---|---|
| Interest-rate risk | Longer bonds have greater price sensitivity to yield changes |
| Liquidity risk | Longer or less active maturities may be harder to sell quickly at fair value |
| Horizon uncertainty | More time means more uncertainty about inflation, rates, and reinvestment conditions |

Investors demand extra yield for accepting these risks.

## Curve Shape Implications

| Yield curve shape | Liquidity preference interpretation |
|---|---|
| Upward sloping | Could reflect rising expected rates, positive liquidity premiums, or both |
| Flat | Expected future short rates may actually be falling enough to offset positive premiums |
| Downward sloping | Stronger evidence that future short rates are expected to fall, because the curve slopes down despite positive premiums |

The key exam idea:

```text
Positive liquidity premiums make forward rates upward-biased estimates of expected future spot rates.
```

## Worked Example

Suppose the one-year forward rate beginning three years from now is 5.20%.

An analyst estimates that the liquidity premium for that future period is 0.60%.

Under liquidity preference theory:

$$
f = E(s) + LP
$$

So:

$$
E(s)=f-LP
$$

$$
E(s)=5.20\%-0.60\%=4.60\%
$$

Interpretation: the 5.20% forward rate is not the pure expected future spot rate. It includes a 60 bp liquidity premium, so the implied expected future spot rate is 4.60%.

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Saying upward-sloping curve always means rates are expected to rise | Liquidity premiums can create an upward slope |
| Saying liquidity preference requires an upward-sloping curve | Expected rate declines can overwhelm the premium |
| Treating forward rates as unbiased forecasts | Under liquidity preference, forwards are upward biased |
| Confusing with preferred habitat theory | Preferred habitat premiums can vary by maturity segment and need not rise steadily |
| Ignoring time variation | Liquidity premiums can be larger during uncertainty and high risk aversion |
| Mixing term-structure liquidity premium with trading liquidity spread | Term-structure LP is about long-maturity risk; credit liquidity spread is about trading friction |

## Memory Hook

```text
Liquidity preference = forward rates wear a premium backpack.
```

The forward rate is carrying:

```text
expected future spot rate + liquidity premium
```

## Related Concepts

- [[Liquidity preference theory]]
- [[Forward curve]]
- [[Forward rate]]
- [[Spot curve]]
- [[Pure expectations theory]]
- [[Local expectations theory]]
- [[Preferred habitat theory]]
- [[Segmented markets theory]]
- [[Term Structure Theories]]
