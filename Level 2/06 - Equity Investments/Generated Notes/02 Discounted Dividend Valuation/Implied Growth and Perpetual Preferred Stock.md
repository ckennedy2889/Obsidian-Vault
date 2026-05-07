---
title: "Implied Growth and Perpetual Preferred Stock"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, discounted-dividend-valuation, preferred-stock]
aliases: ["Implied dividend growth", "Implied growth rate", "Fixed-rate perpetual preferred stock", "Perpetual preferred stock"]
---

# Implied Growth and Perpetual Preferred Stock

The [[Gordon Growth Model]] can be run forward or backward.

Forward use: estimate value from dividends, required return, and growth.

Backward use: observe market price and dividends, then infer the growth rate or required return implied by the price.

This is useful for Apple because the market price is observable and dividends are observable. The question becomes: "If I trust my required return estimate, what dividend growth is the market pricing in?"

## Implied Growth From GGM

Start with:

$$
P_0 =
\frac{D_0(1+g)}{r-g}
$$

Solve for $g$:

$$
P_0(r-g) = D_0(1+g)
$$

$$
P_0r - P_0g = D_0 + D_0g
$$

$$
P_0r - D_0 = P_0g + D_0g
$$

$$
P_0r - D_0 = g(P_0 + D_0)
$$

$$
g =
\frac{P_0r - D_0}{P_0 + D_0}
$$

## Apple Example

Use:

| Input | Value |
|---|---:|
| Apple price | $\$287.24$ |
| Most recent annual dividend | $\$1.02$ |
| Assumed required return | 8% |

Then:

$$
g =
\frac{287.24(0.08) - 1.02}{287.24 + 1.02}
$$

$$
g =
\frac{22.9792 - 1.02}{288.26}
= 7.62\%
$$

If the required return estimate is 8%, the market price implies about 7.62% perpetual dividend growth.

That is an aggressive perpetual assumption for a mature company. The interpretation is not automatically "Apple is overvalued." It may mean the simple dividend model is incomplete because Apple also returns capital through repurchases and retains value in the business.

## Implied Required Return

The GGM can also solve for required return:

$$
r =
\frac{D_1}{P_0} + g
$$

Since $D_1 = D_0(1+g)$:

$$
r =
\frac{D_0(1+g)}{P_0} + g
$$

If Apple dividend growth is assumed to be 4%:

$$
D_1 = 1.02(1.04) = 1.0608
$$

$$
r =
\frac{1.0608}{287.24} + 0.04
= 0.0037 + 0.04
= 4.37\%
$$

That implied required return is very low for common equity, again warning that a dividend-only GGM is not a complete valuation model for Apple.

## Perpetual Preferred Stock

Fixed-rate non-callable perpetual preferred stock is a zero-growth perpetuity.

Because the dividend is fixed and continues forever:

$$
V_0 =
\frac{D_p}{r_p}
$$

where:

- $D_p$ = fixed preferred dividend
- $r_p$ = required return on preferred stock

If a preferred stock pays a fixed $\$6$ annual dividend and investors require 9.5%:

$$
V_0 =
\frac{6}{0.095}
= 63.16
$$

The same formula can solve for the capitalization rate:

$$
r_p =
\frac{D_p}{V_0}
$$

If the preferred trades at $\$75$ and pays $\$6$:

$$
r_p =
\frac{6}{75}
= 8.0\%
$$

## Why Preferred Stock Has No Growth Term

Common stock dividends can grow if earnings grow and the board increases payouts. Fixed-rate perpetual preferred dividends do not grow. The cash flow is level, so the growth rate is zero:

$$
V_0 =
\frac{D}{r-g}
\quad \text{with } g=0
$$

$$
V_0 =
\frac{D}{r}
$$

## Exam Traps

The first trap is using $D_0$ instead of $D_1$ in the GGM numerator without adjusting. The implied-growth formula above handles $D_0$ correctly.

The second trap is interpreting an unrealistic implied growth rate as a final valuation conclusion. It may simply show that the model does not fit the company.

The third trap is adding growth to fixed-rate perpetual preferred stock. Fixed preferred dividends do not grow.

The fourth trap is confusing preferred required return with common equity required return. Preferred has different risk and a fixed dividend claim.

## Memory Hook

> [!tip] Memory Hook
> Common GGM can solve backward for market-implied growth. Fixed perpetual preferred has no growth, so value is just dividend divided by required return.

## Related Concepts

- [[Gordon Growth Model]]
- [[Dividend yield]]
- [[Required Rate of Return]]
- [[Fixed-rate perpetual preferred stock]]
- [[Terminal Value in DDM]]
- [[Discounted Dividend Valuation]]
