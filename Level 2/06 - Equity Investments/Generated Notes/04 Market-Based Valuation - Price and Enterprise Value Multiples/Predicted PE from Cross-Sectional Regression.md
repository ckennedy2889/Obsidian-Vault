---
title: "Predicted P/E from Cross-Sectional Regression"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, market-based-valuation, regression, multiples]
aliases: ["Predicted P/E", "Cross-sectional regression P/E", "Regression-based P/E"]
---

# Predicted P/E from Cross-Sectional Regression

A [[Predicted P/E]] from cross-sectional regression is a disciplined way to ask whether a stock's observed [[P/E Ratio]] is high or low after controlling for fundamentals.

Think about Apple. If Apple trades at a higher P/E than many peers, that does not automatically mean it is overvalued. Apple may deserve a higher multiple because of stronger expected growth, better margins, lower risk, cleaner accounting, or higher returns on capital. A cross-sectional regression tries to separate "high because fundamentals justify it" from "high even after fundamentals."

In plain English:

```text
Predicted P/E = the P/E a stock should have, given its growth, risk, payout, and other fundamentals in a peer sample.
```

Then compare:

```text
Actual P/E > Predicted P/E -> potentially overvalued relative to fundamentals
Actual P/E < Predicted P/E -> potentially undervalued relative to fundamentals
```

## Why This Exists

The method of comparables can be too loose. If an analyst simply says, "Apple trades above the peer median, so it is expensive," the analysis ignores why firms have different multiples.

The forecasted-fundamentals approach says valuation multiples should be connected to drivers such as:

- expected [[Earnings Growth]]
- risk or [[Required Rate of Return]]
- [[Dividend Payout Ratio]]
- profitability
- leverage
- accounting quality

Cross-sectional regression turns that intuition into an empirical model.

## The Regression Form

A CFA-style regression might be:

$$
\widehat{\text{P/E}}_i =
b_0 + b_1 g_i + b_2 \text{Payout}_i - b_3 \text{Risk}_i
$$

where:

- $\widehat{\text{P/E}}_i$ = predicted P/E for company $i$
- $g_i$ = expected earnings growth
- $\text{Payout}_i$ = dividend payout ratio
- $\text{Risk}_i$ = risk measure such as beta or earnings volatility
- $b_0, b_1, b_2, b_3$ = regression coefficients estimated from peer-company data

The signs usually make economic sense:

| Variable | Expected sign | Why |
|---|---:|---|
| Expected growth | Positive | More future earnings growth supports a higher P/E |
| Payout ratio | Often positive | More distributable earnings can support higher value, holding growth constant |
| Risk | Negative | Higher required return lowers justified P/E |
| Profitability | Positive | Higher quality earnings deserve a higher multiple |

## Apple Example

Use Apple as the running company. A recent data snapshot showed:

| Apple input | Value |
|---|---:|
| Share price | $\$287.70$ |
| FY2025 diluted EPS | $\$7.46$ |
| FY2025 dividend per share | $\$1.02$ |
| FY2023 diluted EPS | $\$6.13$ |

Observed trailing P/E:

$$
\text{Actual P/E} =
\frac{287.70}{7.46}
= 38.57
$$

Simple two-year EPS CAGR:

$$
g =
\left(\frac{7.46}{6.13}\right)^{1/2} - 1
= 10.32\%
$$

Dividend payout ratio:

$$
\text{Payout} =
\frac{1.02}{7.46}
= 13.7\%
$$

Now suppose an exam question gives the following cross-sectional regression estimated from comparable large-cap technology companies:

$$
\widehat{\text{P/E}} =
8.0 + 1.10g + 0.15\text{Payout} - 3.0\beta
$$

where $g$ and payout are entered as whole-number percentages. If the question gives Apple a beta of $1.20$, then:

$$
\widehat{\text{P/E}} =
8.0 + 1.10(10.32) + 0.15(13.7) - 3.0(1.20)
$$

$$
\widehat{\text{P/E}} =
8.0 + 11.35 + 2.06 - 3.60
= 17.81
$$

Compare actual to predicted:

$$
\text{Actual P/E} = 38.57
$$

$$
\text{Predicted P/E} = 17.81
$$

In this exam-style setup, Apple's actual P/E is above the predicted P/E, so the stock would screen as overvalued relative to the regression fundamentals.

That is not an investment recommendation. It only means that this particular model, with these particular coefficients and inputs, does not explain the full observed multiple.

## Mechanism

The regression is trying to estimate the market's pricing rule:

```text
Across comparable companies, how much extra P/E does the market usually pay for more growth, more payout, or less risk?
```

If the market normally pays 1.10 additional P/E turns for each extra point of growth, the regression coefficient on growth captures that average relationship. If a company trades far above the predicted value, the analyst asks:

- Is the stock overpriced?
- Is the regression missing an important variable?
- Are the inputs stale or wrong?
- Is the peer group inappropriate?
- Is the market pricing a strategic option the model does not capture?

## Interpretation Rule

| Comparison | Interpretation |
|---|---|
| Actual P/E > predicted P/E | Stock may be overvalued relative to modeled fundamentals |
| Actual P/E < predicted P/E | Stock may be undervalued relative to modeled fundamentals |
| Actual P/E near predicted P/E | Stock appears fairly valued by the regression |

CFA usually expects this narrow interpretation. Do not turn it into a full buy/sell recommendation unless the question gives enough supporting evidence.

## Key Limitations

Cross-sectional regression looks scientific, but it has important weaknesses.

| Limitation | Why it matters |
|---|---|
| Coefficients can be unstable | The relationship between P/E and fundamentals changes over time |
| Multicollinearity | Growth, profitability, payout, and risk may be correlated |
| Omitted variables | Brand strength, network effects, accounting quality, and optionality may be missing |
| Peer group selection | Bad comparables produce bad predicted multiples |
| Accounting differences | EPS may not be comparable across firms or countries |
| Outliers | Extreme multiples can distort coefficients |

For Apple, omitted variables can matter. A simple regression may not fully capture ecosystem lock-in, services mix, balance sheet policy, buybacks, product-cycle risk, or regulatory exposure. The regression result is a diagnostic, not a final answer.

## Exam Traps

The most common trap is reversing the conclusion. If actual P/E is greater than predicted P/E, the stock is expensive relative to the model, not cheap.

Another trap is mixing units. If the regression says growth is entered as a percentage, use $10.32$, not $0.1032$. If it says growth is entered as a decimal, use $0.1032$. The coefficients only make sense with the units used to estimate them.

A third trap is trusting the regression without reading the limitations. CFA often asks not only for the predicted P/E calculation, but also why cross-sectional regression can mislead.

Finally, watch the word "predicted." Predicted P/E is not a forecast of where the stock will trade next month. It is the model-implied P/E given current fundamentals.

## Memory Hook

> [!tip] Memory Hook
> Regression P/E asks, "What multiple would this stock deserve if the market priced it like similar firms with similar fundamentals?"

## Related Concepts

- [[Price-to-Earnings Ratio]]
- [[Justified price multiple]]
- [[PEG Ratio]]
- [[Normalized EPS and Underlying Earnings]]
- [[Method of Comparables]]
- [[Market-Based Valuation]]
