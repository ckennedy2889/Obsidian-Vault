---
title: "Terminal Value in DDM"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, discounted-dividend-valuation, terminal-value]
aliases: ["Terminal value in DDM", "Terminal stock value", "DDM terminal value"]
---

# Terminal Value in DDM

[[Terminal value]] in a [[Dividend Discount Model]] is the value, at a future date, of all dividends expected after the explicit forecast period.

Think about valuing Apple with dividends. You might be comfortable forecasting the next three to five years of dividends because Apple has recent dividend data and a visible capital return policy. But you cannot forecast every annual dividend forever line by line. Terminal value solves that problem by compressing the long tail of future dividends into one value at the end of the explicit forecast horizon.

In plain English:

```text
Terminal value = what the stock should be worth at the end of the forecast period, based on all dividends after that point.
```

## The Timeline

If the explicit forecast lasts $n$ years, the stock value today is:

$$
V_0 =
\sum_{t=1}^{n}\frac{D_t}{(1+r)^t}
+ \frac{V_n}{(1+r)^n}
$$

where:

- $D_t$ = dividend in year $t$
- $r$ = required return on equity
- $V_n$ = terminal value at the end of year $n$

The critical timing point is that $V_n$ sits at time $n$, not time $n+1$.

## GGM Terminal Value

The most common CFA approach uses the [[Gordon Growth Model]] after the company reaches stable growth:

$$
V_n =
\frac{D_{n+1}}{r - g_L}
$$

where:

- $D_{n+1}$ = first dividend after the explicit forecast period
- $g_L$ = long-run sustainable dividend growth rate
- $r$ = required return

The numerator is $D_{n+1}$ because a value at time $n$ is the present value, at time $n$, of dividends starting one period later.

## Apple Example

Apple paid dividends per common share of $\$0.94$ in FY2023, $\$0.98$ in FY2024, and $\$1.02$ in FY2025. Suppose an analyst forecasts:

| Year | Dividend assumption |
|---|---:|
| $D_0$ | $\$1.02$ |
| Years 1-3 | 6% annual dividend growth |
| Stable growth after Year 3 | 3% |
| Required return | 8% |

First forecast explicit dividends:

$$
D_1 = 1.02(1.06) = 1.0812
$$

$$
D_2 = 1.0812(1.06) = 1.1461
$$

$$
D_3 = 1.1461(1.06) = 1.2148
$$

The first stable-growth dividend is:

$$
D_4 = D_3(1.03) = 1.2148(1.03) = 1.2512
$$

Terminal value at time 3:

$$
V_3 =
\frac{D_4}{r-g_L}
= \frac{1.2512}{0.08 - 0.03}
= 25.02
$$

Now discount dividends and terminal value back to today:

$$
V_0 =
\frac{1.0812}{1.08}
+ \frac{1.1461}{1.08^2}
+ \frac{1.2148}{1.08^3}
+ \frac{25.02}{1.08^3}
$$

$$
V_0 =
1.00 + 0.98 + 0.96 + 19.86
= 22.80
$$

Terminal value contributes:

$$
\frac{19.86}{22.80} = 87.1\%
$$

That is why terminal assumptions dominate multistage DDM valuations.

## Multiple-Based Terminal Value

Analysts can also estimate terminal value using a market multiple:

$$
V_n =
\text{Terminal P/E} \times E_n
$$

or:

$$
V_n =
\text{Leading P/E} \times E_{n+1}
$$

The multiple approach uses market comparables. The GGM approach uses forecasted fundamentals.

| Approach | Strength | Weakness |
|---|---|---|
| GGM terminal value | Tied to $r$, $g$, and dividends | Extremely sensitive to $r-g$ |
| Multiple terminal value | Grounded in market evidence | Imports peer mispricing |

## Exam Traps

The first trap is the off-by-one error. Use $D_{n+1}$ in the GGM formula to calculate $V_n$, then discount $V_n$ back $n$ periods.

The second trap is discounting terminal value by $n+1$ periods. The dividend in the numerator is at $n+1$, but the value is at $n$.

The third trap is forgetting that terminal value often drives most of total value. Small changes to $g_L$ or $r$ can dominate the explicit dividend forecast.

The fourth trap is mixing trailing and leading multiples. A trailing P/E terminal multiple uses $E_n$. A leading P/E terminal multiple uses $E_{n+1}$.

## Memory Hook

> [!tip] Memory Hook
> Terminal value at $n$ uses the first cash flow after $n$, then gets discounted back exactly $n$ periods.

## Related Concepts

- [[Gordon Growth Model]]
- [[Two-Stage DDM]]
- [[Three-Stage DDM]]
- [[H-Model]]
- [[Leading PE Ratio]]
- [[Discounted Dividend Valuation]]
