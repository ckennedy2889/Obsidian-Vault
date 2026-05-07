---
title: "Arithmetic, Harmonic, and Weighted Harmonic Mean for Multiples"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, market-based-valuation, multiples, statistics]
aliases: ["Harmonic mean for multiples", "Weighted harmonic mean for multiples", "Averaging valuation multiples", "Central tendency of multiples"]
---

# Arithmetic, Harmonic, and Weighted Harmonic Mean for Multiples

When analysts compare valuation multiples, the word "average" is dangerous.

Suppose you are comparing Apple, Microsoft, and Nvidia. You can calculate a P/E for each company, but if you want a peer-group P/E, should you use the arithmetic mean, median, harmonic mean, or weighted harmonic mean? CFA cares because each choice answers a different question, and using the wrong average can make a peer group look cheaper or more expensive than it really is.

The core idea:

```text
Arithmetic mean averages the multiples.
Harmonic mean averages the earnings yields and converts back to a multiple.
Weighted harmonic mean gives the correct aggregate multiple for a portfolio or index.
Median picks the middle company.
```

## Why Multiples Are Hard To Average

A valuation multiple is a ratio:

$$
\text{P/E} = \frac{P}{E}
$$

Ratios are asymmetric. A company with a tiny denominator can have a huge P/E. If one peer trades at $100 \times$ earnings, the arithmetic mean can be pulled upward even if the rest of the group trades near $20 \times$.

That is why CFA asks which measure of central tendency is most appropriate.

## The Four Measures

| Measure | Formula | Best use | Weakness |
|---|---|---|---|
| Arithmetic mean | $\bar{X} = \frac{\sum X_i}{n}$ | Simple average when no major outliers | Pulled upward by high multiples |
| Median | Middle observation | Robust peer-group summary | Ignores distance between observations |
| Harmonic mean | $X_H = \frac{n}{\sum(1/X_i)}$ | Equal-weighted average of ratios | Sensitive to very low positive multiples |
| Weighted harmonic mean | $X_{WH} = \frac{1}{\sum(w_i/X_i)}$ | Portfolio or index multiple | Requires correct weights |

## Real Peer Example

Use a three-stock technology peer set:

| Company | Price | Net income | Approx. market value | P/E using market value / net income |
|---|---:|---:|---:|---:|
| Apple | $\$287.70$ | $\$112.010$ billion | $\$4,251.2$ billion | 37.95x |
| Microsoft | $\$413.77$ | $\$101.832$ billion | $\$3,075.6$ billion | 30.20x |
| Nvidia | $\$207.10$ | $\$120.067$ billion | $\$5,044.7$ billion | 42.02x |

These are not identical businesses, but they are useful for seeing the mechanics. The point is not to decide which stock to buy. The point is to understand what each average does.

## Arithmetic Mean

The arithmetic mean is:

$$
\bar{X} =
\frac{37.95 + 30.20 + 42.02}{3}
$$

$$
\bar{X} = 36.72
$$

This is the simple average of the three P/Es. It is easy to calculate and easy to explain.

The problem appears when one multiple is extreme. If Nvidia's P/E were $100 \times$ because near-term earnings were temporarily depressed, the arithmetic mean would jump sharply even if Apple and Microsoft did not change.

## Harmonic Mean

The harmonic mean is:

$$
X_H =
\frac{n}{\sum(1/X_i)}
$$

For the same peer set:

$$
X_H =
\frac{3}
{\frac{1}{37.95} + \frac{1}{30.20} + \frac{1}{42.02}}
$$

$$
X_H = 36.12
$$

The harmonic mean is lower than the arithmetic mean because it gives less influence to high multiples. Mechanically, it averages the reciprocals. Since the reciprocal of P/E is [[Earnings Yield]]:

$$
\frac{1}{\text{P/E}} = \frac{E}{P}
$$

the harmonic mean is really saying:

```text
Average the earnings yield, then convert back to P/E.
```

That is often more sensible for valuation because a P/E is just the inverse of an earnings yield.

## Weighted Harmonic Mean

For a portfolio or index, the correct aggregate P/E is:

$$
\text{Aggregate P/E} =
\frac{\text{Total market value}}{\text{Total earnings}}
$$

The weighted harmonic mean gives the same answer when weights are market-value weights:

$$
X_{WH} =
\frac{1}{\sum(w_i/X_i)}
$$

Using the market values above:

| Company | Approx. market value | Weight |
|---|---:|---:|
| Apple | $\$4,251.2$ billion | 34.4% |
| Microsoft | $\$3,075.6$ billion | 24.9% |
| Nvidia | $\$5,044.7$ billion | 40.8% |

Weighted harmonic mean:

$$
X_{WH} =
\frac{1}
{\frac{0.344}{37.95} + \frac{0.249}{30.20} + \frac{0.408}{42.02}}
$$

$$
X_{WH} = 37.05
$$

Now calculate the direct aggregate P/E:

$$
\text{Total market value} =
4{,}251.2 + 3{,}075.6 + 5{,}044.7
= 12{,}371.5
$$

$$
\text{Total earnings} =
112.010 + 101.832 + 120.067
= 333.909
$$

$$
\text{Aggregate P/E} =
\frac{12{,}371.5}{333.909}
= 37.05
$$

The match is the point. The weighted harmonic mean is not just a statistical preference. It is the mathematically correct way to combine individual P/Es into a market-value-weighted portfolio P/E.

## Why The Weighted Arithmetic Mean Is Wrong

A tempting wrong method is:

$$
\text{Wrong weighted average P/E} =
\sum w_i X_i
$$

That averages ratios directly. But an index P/E is not the weighted average of company P/Es. It is total price divided by total earnings.

The weighted arithmetic mean answers:

```text
What is the average of the members' P/E ratios, weighted by market value?
```

The portfolio P/E asks:

```text
How many dollars of portfolio market value are investors paying per dollar of portfolio earnings?
```

Those are not the same question.

## Median

The median is the middle value after sorting the multiples:

```text
30.20x, 37.95x, 42.02x
```

So the median is:

$$
\text{Median} = 37.95
$$

The median is useful when the peer group has an outlier and the analyst wants a representative company rather than a portfolio-level multiple. It is not the same as an index P/E.

## Decision Rule

| Task | Preferred measure |
|---|---|
| Summarize a peer group with outliers | Median or harmonic mean |
| Calculate equal-weighted portfolio multiple | Harmonic mean |
| Calculate market-cap-weighted index/portfolio P/E | Weighted harmonic mean |
| Quick rough average with clean data | Arithmetic mean may be acceptable |
| Extreme high multiples | Avoid relying on arithmetic mean |
| Very small positive multiples | Use caution with harmonic mean |

## Exam Traps

The biggest trap is using the arithmetic mean for a portfolio or index P/E. If the question gives portfolio weights and individual P/Es, CFA usually wants the weighted harmonic mean.

Another trap is thinking the harmonic mean always solves outliers. It reduces the effect of very high multiples, but it can be overly influenced by very low positive multiples. A company at $2 \times$ earnings can pull the harmonic mean downward.

Also watch for negative earnings. P/E is not meaningful when earnings are negative, and the harmonic mean can break down. In those cases, analysts may use normalized earnings, [[Earnings Yield]], EV-based multiples, or exclude nonmeaningful observations with justification.

## Memory Hook

> [!tip] Memory Hook
> For portfolio P/E, add the dollars first: total market value divided by total earnings. The weighted harmonic mean is the shortcut that gets you there.

## Related Concepts

- [[Price-to-Earnings Ratio]]
- [[Earnings Yield]]
- [[Enterprise Value Multiples and Comparable Valuation]]
- [[Normalized EPS and Underlying Earnings]]
- [[Weighted harmonic mean]]
- [[Market-Based Valuation]]
