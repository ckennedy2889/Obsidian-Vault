---
title: "PEG Ratio"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, market-based-valuation, multiples]
aliases: ["P/E-to-growth ratio", "PEG", "Price earnings to growth ratio"]
---

# PEG Ratio

The [[PEG ratio]] is the market multiple version of asking, "Am I paying too much for this growth story?"

Imagine Apple trading at a high [[P/E Ratio]]. A high P/E by itself does not automatically mean "expensive" because a firm with durable growth, high margins, and strong reinvestment opportunities deserves a higher multiple than a no-growth firm. The problem is that raw P/E mixes several things together: expected [[Earnings Per Share|EPS]] growth, risk, payout policy, accounting quality, and investor sentiment. The PEG ratio tries to isolate one part of that bundle by scaling P/E by expected earnings growth.

In plain English:

```text
PEG = how many units of P/E the market is charging for one percentage point of expected EPS growth.
```

That makes it a quick relative valuation tool, not a full valuation model.

## The Formula

The usual CFA form is:

$$
\text{PEG} = \frac{\text{P/E}}{g}
$$

where:

- $\text{P/E}$ is usually a trailing or leading [[Price-to-Earnings Ratio]]
- $g$ is expected earnings growth, stated as a whole-number percentage, not a decimal

So if a stock trades at $24 \times$ earnings and expected EPS growth is 12%, the PEG is:

$$
\text{PEG} = \frac{24}{12} = 2.0
$$

Do not use $0.12$ in the denominator unless the problem specifically defines the formula that way. CFA convention normally uses the growth rate as `12`, not `0.12`.

## Why PEG Exists

A plain [[P/E Ratio]] says:

$$
\text{P/E} = \frac{P_0}{E}
$$

That ratio tells you the price paid per dollar of current or forecasted earnings. But two companies can both trade at $30 \times$ earnings for very different reasons.

| Company | P/E | Expected EPS growth | First impression | Better interpretation |
|---|---:|---:|---|---|
| SlowGrow Co. | 30x | 3% | High P/E | Very expensive relative to growth |
| FastGrow Co. | 30x | 20% | Same P/E | Less expensive per unit of growth |

PEG converts that intuition into a quick comparison:

$$
\text{SlowGrow PEG} = \frac{30}{3} = 10.0
$$

$$
\text{FastGrow PEG} = \frac{30}{20} = 1.5
$$

The rule is not "low P/E good." The better rule is "for similar risk and quality, lower PEG means cheaper growth."

## Apple Example

Use Apple as the running case. A recent data snapshot showed:

| Item | Apple data |
|---|---:|
| Share price | $\$287.70$ |
| FY2025 diluted EPS | $\$7.46$ |
| FY2023 diluted EPS | $\$6.13$ |

First calculate the trailing P/E:

$$
\text{Trailing P/E} = \frac{287.70}{7.46} = 38.57
$$

Now estimate a simple historical EPS growth rate from FY2023 to FY2025. Because this is a two-year period:

$$
g = \left(\frac{7.46}{6.13}\right)^{1/2} - 1
$$

$$
g = 10.32\%
$$

Using the CFA whole-number convention for growth:

$$
\text{PEG} = \frac{38.57}{10.32} = 3.74
$$

That means the market price reflects about $3.74$ turns of P/E for each percentage point of recent EPS growth.

## Interpretation

A lower PEG is usually more attractive than a higher PEG, assuming the companies are similar in risk, profitability, accounting quality, and growth duration.

The common shortcut is:

| PEG | Common screening interpretation | CFA-level caution |
|---:|---|---|
| Below 1.0 | Potentially cheap growth | Only meaningful if growth forecast is credible and risk is similar |
| Around 1.0 | Often treated as fairly priced growth | Still ignores risk and growth duration |
| Above 1.0 | More expensive growth | May be justified by higher quality, lower risk, or longer growth runway |

Apple's rough PEG of $3.74$ does not automatically mean "sell Apple." It means a simple screen is saying: at this price and this growth input, Apple is not cheap on P/E per unit of growth. A real analyst would then ask whether the growth input is too low, whether Apple's risk is lower than peers, whether its margins are more durable, and whether its growth lasts longer than the period used in the calculation.

## Why The Formula Is Mechanically Incomplete

PEG feels intuitive because [[Price-to-Earnings Ratio|P/E]] is positively related to growth. But the relationship is not linear.

From the [[Gordon Growth Model]]:

$$
P_0 = \frac{D_1}{r-g}
$$

If $D_1 = E_1 \times \text{payout ratio}$, then:

$$
\frac{P_0}{E_1} = \frac{\text{payout ratio}}{r-g}
$$

This tells you that P/E is driven by:

- the [[Dividend Payout Ratio]]
- the required return $r$
- expected growth $g$

Growth appears in the denominator as $r-g$, so the relation between P/E and growth is curved, not linear. Moving growth from 2% to 4% does not have the same valuation effect as moving growth from 8% to 10% when $r$ is fixed. The PEG ratio pretends the P/E-to-growth relationship is a straight line, which is why it is a useful screen but not a theoretically complete valuation model.

## Assumptions

PEG works best when:

| Assumption | Why it matters |
|---|---|
| Peer companies have similar risk | Higher-risk companies deserve lower P/Es even if growth is high |
| Growth estimates are comparable | One-year growth and five-year growth are not interchangeable |
| Growth is positive and meaningful | PEG breaks down for zero, negative, or tiny growth rates |
| Earnings are normalized | Temporary earnings distort both P/E and growth |
| Accounting quality is similar | Aggressive EPS can make PEG look falsely cheap |

For Apple, the biggest exam-style issue is the growth input. If you use recent historical EPS growth, you get one answer. If you use a forward analyst growth forecast, you may get another. CFA questions usually specify which growth rate to use. Do not substitute your own.

## Failure Modes

The PEG ratio fails when the denominator is not economically meaningful.

| Failure mode | What goes wrong | Exam implication |
|---|---|---|
| Negative EPS growth | PEG becomes negative or meaningless | Do not call a negative PEG "cheap" |
| Very low growth | PEG explodes upward | A high PEG may simply reflect mature-company math |
| Cyclical rebound growth | Growth looks temporarily high | PEG may falsely label the stock cheap |
| Different risk profiles | Low PEG may compensate for high risk | Compare risk before ranking |
| Different growth duration | Short burst and long runway treated the same | Ask whether growth is sustainable |

## Exam Traps

The most common trap is using growth as a decimal.

If P/E is $20$ and growth is 10%, CFA convention gives:

$$
\text{PEG} = \frac{20}{10} = 2.0
$$

The wrong decimal version gives:

$$
\text{Wrong PEG} = \frac{20}{0.10} = 200
$$

Another trap is comparing PEG ratios across companies with different risk. A high-growth, high-beta stock can have a low PEG because the market is demanding compensation for uncertainty. Low PEG is not automatically undervaluation.

Finally, watch the P/E base. A trailing PEG uses trailing P/E. A forward PEG uses leading P/E. Mixing trailing EPS with forward growth may be acceptable only if the question tells you to do it. Otherwise, match the definitions.

## Memory Hook

> [!tip] Memory Hook
> PEG asks, "How much P/E am I paying per point of growth?" Lower is better only when risk, earnings quality, and growth duration are comparable.

## Related Concepts

- [[Price-to-Earnings Ratio]]
- [[Justified Leading and Trailing PE]]
- [[Normalized EPS and Underlying Earnings]]
- [[Gordon Growth Model]]
- [[Present Value of Growth Opportunities]]
- [[Market-Based Valuation]]
