---
title: "Normalized EPS and Underlying Earnings"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, market-based-valuation, earnings-quality]
aliases: ["Normalized EPS", "Normal EPS", "Underlying earnings", "Core earnings", "Persistent earnings", "Continuing earnings"]
---

# Normalized EPS and Underlying Earnings

[[Normalized EPS]] and [[Underlying earnings]] exist because the denominator of a [[P/E Ratio]] is fragile.

Price is observable. Earnings are accounting output. If earnings include a one-time legal charge, a tax benefit, a restructuring cost, an asset sale gain, or a cyclical trough, then the P/E ratio may be mathematically correct but economically misleading. CFA wants you to notice that "P divided by EPS" is only useful if EPS represents the earnings power investors are actually buying.

Use Apple as the running case. Apple is not a classic deep cyclical company, but it is useful because it has large reported earnings, major share repurchases, and a balance sheet affected by capital return policy. That makes it a good reminder that normalizing EPS is not just a mechanical average. You must understand what the earnings number is supposed to represent.

## Plain-English Definition

Underlying earnings are earnings from the recurring, continuing operations of the business.

Normalized EPS is an estimate of the EPS the company could earn under normal, mid-cycle conditions.

The difference is subtle:

| Concept | Question it answers | Typical adjustment |
|---|---|---|
| [[Underlying earnings]] | What did the company earn from recurring operations this period? | Remove nonrecurring gains/losses |
| [[Normalized EPS]] | What EPS should we use if current EPS is cyclically high or low? | Average across a cycle or apply average ROE to current BVPS |

Underlying earnings clean up the current period. Normalized EPS smooths the cycle.

## Why Analysts Adjust EPS

The raw trailing P/E is:

$$
\text{Trailing P/E} = \frac{P_0}{\text{Trailing EPS}}
$$

If trailing EPS is temporarily depressed, the P/E looks too high. If trailing EPS is temporarily inflated, the P/E looks too low.

That problem is especially dangerous in cyclical companies. At the bottom of a cycle, earnings collapse, so P/E can look absurdly high even when the stock is cheap on normalized earnings. At the top of a cycle, earnings are temporarily strong, so P/E can look cheap right before earnings fall. This is the [[Molodovsky effect]].

```text
Cycle trough: low EPS -> high P/E -> may look expensive when it is not
Cycle peak: high EPS -> low P/E -> may look cheap when it is not
```

## Underlying Earnings

Underlying earnings remove nonrecurring items from reported EPS.

A simple CFA-style structure is:

$$
\text{Underlying EPS} =
\text{Reported EPS}
- \text{Nonrecurring gains per share}
+ \text{Nonrecurring losses per share}
$$

The signs matter:

| Item in reported EPS | Adjustment | Why |
|---|---:|---|
| One-time gain | Subtract | It inflated reported earnings |
| One-time loss | Add back | It depressed reported earnings |
| Recurring expense | Do not add back | It is part of the business |
| Recurring restructuring | Usually do not add back blindly | "Recurring nonrecurring" is not truly nonrecurring |

If Apple reported EPS of $\$7.46$ and had a clearly nonrecurring after-tax gain of $\$0.20$ per share, underlying EPS would be:

$$
\text{Underlying EPS} = 7.46 - 0.20 = 7.26
$$

At a price of $\$287.70$:

$$
\text{Reported P/E} = \frac{287.70}{7.46} = 38.57
$$

$$
\text{Underlying P/E} = \frac{287.70}{7.26} = 39.63
$$

The reported P/E looked lower because the denominator included a gain that should not be capitalized.

## Normalized EPS: Historical Average EPS Method

The first normalizing method averages EPS over a business cycle:

$$
\text{Normalized EPS} =
\frac{\sum_{t=1}^{n} \text{EPS}_t}{n}
$$

For Apple, using FY2023-FY2025 diluted EPS:

| Fiscal year | Diluted EPS |
|---|---:|
| FY2023 | $\$6.13$ |
| FY2024 | $\$6.08$ |
| FY2025 | $\$7.46$ |

The average EPS is:

$$
\text{Normalized EPS} =
\frac{6.13 + 6.08 + 7.46}{3}
= 6.56
$$

At the same share price:

$$
\text{Normalized P/E} =
\frac{287.70}{6.56}
= 43.88
$$

This method is easy and transparent, but it can be weak when the company changes size, repurchases many shares, issues shares, acquires businesses, or materially changes margins.

## Normalized EPS: Average ROE Method

The second method uses average [[Return on Equity|ROE]] over the cycle and applies it to current [[Book Value Per Share|BVPS]]:

$$
\text{Normalized EPS} =
\text{Average ROE} \times \text{Current BVPS}
$$

This method tries to answer:

```text
Given the company's current equity base, what EPS would normal profitability produce?
```

For Apple, use a simplified year-end ROE approximation from recent annual data:

| Fiscal year | Net income | Shareholders' equity | Approx. ROE |
|---|---:|---:|---:|
| FY2023 | $\$96.995$ billion | $\$62.146$ billion | 156.1% |
| FY2024 | $\$93.736$ billion | $\$56.950$ billion | 164.6% |
| FY2025 | $\$112.010$ billion | $\$73.733$ billion | 151.9% |

Average ROE:

$$
\text{Average ROE} =
\frac{156.1\% + 164.6\% + 151.9\%}{3}
= 157.5\%
$$

Current BVPS:

$$
\text{BVPS} =
\frac{73.733\text{ billion}}{14.776\text{ billion shares}}
= 4.99
$$

Normalized EPS:

$$
\text{Normalized EPS} =
1.575 \times 4.99
= 7.86
$$

Normalized P/E:

$$
\text{Normalized P/E} =
\frac{287.70}{7.86}
= 36.60
$$

This example also shows why CFA expects judgment. Apple's ROE is extremely high partly because its equity base is small relative to its earnings, reflecting years of repurchases and capital returns. The average ROE method can be better than a raw EPS average, but it is not magic. If book value is unusually low, the analyst must understand why.

## Choosing The Method

| Situation | Better method | Reason |
|---|---|---|
| Stable company, little size change | Historical average EPS | Simple cycle smoothing is enough |
| Company has grown or shrunk materially | Average ROE method | Applies normal profitability to current size |
| Large share repurchases | Average ROE method with caution | Current BVPS reflects altered capital base |
| Negative or tiny current EPS | Normalized EPS or E/P | Raw P/E may be meaningless |
| One-time gain/loss in current year | Underlying earnings adjustment | Fix the period before comparing P/E |

## Mechanism: Why This Changes Valuation

A P/E multiple capitalizes earnings:

$$
P_0 = \text{P/E} \times E
$$

If the earnings input is too high, the valuation is too high for a given multiple. If the earnings input is too low, the valuation is too low for a given multiple.

The hidden assumption in every P/E comparison is:

```text
The E in P/E is representative of future maintainable earnings.
```

If that assumption fails, the comparison can fail even if the arithmetic is perfect.

## Exam Traps

The most common trap is sign direction. Add back nonrecurring losses. Subtract nonrecurring gains.

Another trap is using management's adjusted EPS without judgment. CFA questions often give you enough detail to decide which items are genuinely nonrecurring. A restructuring charge that appears every year is not a clean add-back just because management labels it adjusted.

A third trap is ignoring the [[Molodovsky effect]]. A low P/E for a cyclical company near peak earnings may signal danger, not cheapness. A high P/E near trough earnings may be normal once earnings recover.

Finally, remember that normalized EPS is usually designed for valuation, not performance reporting. You are trying to estimate sustainable earnings power, not describe the exact GAAP result for the year.

## Memory Hook

> [!tip] Memory Hook
> P/E is only as good as its E. Underlying EPS removes unusual items; normalized EPS asks what earnings should look like in a normal part of the cycle.

## Related Concepts

- [[Price-to-Earnings Ratio]]
- [[Normalized PE]]
- [[Normal EPS]]
- [[Underlying earnings]]
- [[Earnings Yield]]
- [[Molodovsky effect]]
- [[PEG Ratio]]
- [[Market-Based Valuation]]
