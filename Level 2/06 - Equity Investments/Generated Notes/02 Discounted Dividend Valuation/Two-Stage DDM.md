---
title: "Two-Stage DDM"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, discounted-dividend-valuation, multistage-ddm]
aliases: ["Two-stage dividend discount model", "Two-stage fixed growth rate model", "Two-stage DDM"]
---

# Two-Stage DDM

The [[Two-Stage DDM]] values a stock by splitting its dividend life into two regimes: a finite high-growth period followed by stable growth forever.

For Apple, imagine an analyst expects dividends to grow faster for the next few years while earnings and buyback capacity remain strong, then settle into a mature long-run growth rate. The two-stage DDM is built for exactly that story. It is not saying Apple is a two-stage company forever; it is saying the analyst can reasonably separate the forecast into a visible stage and a stable terminal stage.

## Formula

If dividends grow at $g_S$ for $n$ years, then at $g_L$ forever:

$$
V_0 =
\sum_{t=1}^{n}
\frac{D_0(1+g_S)^t}{(1+r)^t}
+ \frac{V_n}{(1+r)^n}
$$

with:

$$
V_n =
\frac{D_{n+1}}{r-g_L}
$$

and:

$$
D_{n+1} = D_n(1+g_L)
$$

where:

- $D_0$ = most recent dividend
- $g_S$ = short-term growth rate
- $g_L$ = long-run stable growth rate
- $r$ = required return
- $n$ = length of the first stage

## Apple Example

Use the same assumptions as the terminal value note:

| Input | Value |
|---|---:|
| $D_0$ | $\$1.02$ |
| Stage 1 growth | 6% for 3 years |
| Stable growth | 3% forever after Year 3 |
| Required return | 8% |

Forecast dividends:

$$
D_1 = 1.02(1.06) = 1.0812
$$

$$
D_2 = 1.0812(1.06) = 1.1461
$$

$$
D_3 = 1.1461(1.06) = 1.2148
$$

Stable dividend:

$$
D_4 = 1.2148(1.03) = 1.2512
$$

Terminal value at Year 3:

$$
V_3 =
\frac{1.2512}{0.08-0.03}
= 25.02
$$

Present value:

| Cash flow | Amount | Discount factor | Present value |
|---|---:|---:|---:|
| $D_1$ | $\$1.0812$ | $1.08^1$ | $\$1.00$ |
| $D_2$ | $\$1.1461$ | $1.08^2$ | $\$0.98$ |
| $D_3$ | $\$1.2148$ | $1.08^3$ | $\$0.96$ |
| $V_3$ | $\$25.02$ | $1.08^3$ | $\$19.86$ |

Total value:

$$
V_0 = 1.00 + 0.98 + 0.96 + 19.86 = 22.80
$$

If Apple's market price is about $\$287.24$, this dividend-only DDM value is far below market price. That does not automatically mean Apple is overvalued. It means dividends alone are not capturing the full cash return and reinvestment story. Apple returns capital through buybacks and retains value inside the business, so a DDM using only dividends may understate value.

## When To Use It

| Company pattern | Two-stage DDM fit |
|---|---|
| High growth for a short visible period, then stable growth | Good fit |
| Mature firm already in stable growth | Use Gordon Growth Model |
| Growth declines gradually | [[H-Model]] may fit better |
| Distinct growth, transition, and maturity phases | [[Three-Stage DDM]] may fit better |
| Irregular dividends | Spreadsheet modeling may fit better |

## Assumptions

The two-stage DDM assumes:

- dividends are meaningful and related to earnings
- the high-growth period length is known
- growth shifts abruptly from $g_S$ to $g_L$
- $r > g_L$
- stable growth is sustainable

The abrupt shift is the model's biggest realism problem. Businesses usually do not fall from high growth to mature growth overnight.

## Exam Traps

The first trap is using $g_S$ to calculate the terminal dividend. Once the stable stage begins, use $g_L$:

$$
D_{n+1} = D_n(1+g_L)
$$

The second trap is discounting terminal value by the wrong number of periods. $V_n$ is discounted by $n$ periods.

The third trap is forgetting no-dividend first stages. If the company pays no dividends in Stage 1, the value can be just the present value of terminal value.

The fourth trap is model selection. If growth declines linearly, the H-model is more natural. If there are three distinct phases, use a three-stage model.

## Memory Hook

> [!tip] Memory Hook
> Two-stage DDM is a step-down model: high growth for $n$ years, then stable growth forever.

## Related Concepts

- [[Terminal Value in DDM]]
- [[Gordon Growth Model]]
- [[H-Model]]
- [[Three-Stage DDM]]
- [[Spreadsheet Modeling in DDM]]
- [[Discounted Dividend Valuation]]
