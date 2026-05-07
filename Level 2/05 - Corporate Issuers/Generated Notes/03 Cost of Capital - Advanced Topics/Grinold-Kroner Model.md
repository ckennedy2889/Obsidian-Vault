---
title: Grinold-Kroner Model
subject: Corporate Issuers
tags: [CFA-L2, corporate-issuers, cost-of-capital, equity-risk-premium, economics]
aliases: [Grinold Kroner model, Grinold-Kroner, Grinold Kronor model, GK model, macroeconomic ERP model]
---

# Grinold-Kroner Model

## The Real-World Analogy

Imagine you own an apartment building. Your return comes from three big places: the rent checks you receive, the growth in the building's future rent-producing power, and any change in what buyers are willing to pay for each dollar of rent. But there is one more twist: if the building suddenly issues more ownership claims, your personal slice gets diluted. If the building buys back ownership claims, your slice gets larger.

That is the intuition behind the **Grinold-Kroner model**. It says the expected return on an [[Equity|equity]] market is not magic. It is the sum of cash income, growth in earnings, repricing of valuation multiples, and the effect of share issuance or buybacks.

## The Big Idea

The model is a **forward-looking macroeconomic approach** to estimating the expected return on the market and, by extension, the [[Equity risk premium|equity risk premium]].

At the broad market level, CFA uses it in two connected ways:

| CFA context | What Grinold-Kroner helps answer |
|---|---|
| [[Cost of Capital]] / [[Corporate Issuers]] | What is a forward-looking estimate of the market return and ERP? |
| [[CFA_Glossary/Economic growth]] / [[Potential GDP]] | Can stock market appreciation sustainably exceed the economy's growth rate? |

The model is especially useful because it forces you to separate **sustainable return drivers** from **one-time or mean-reverting return drivers**. Dividend yield and nominal earnings growth can persist. P/E expansion cannot continue forever. Corporate profits cannot become more than the whole economy. Share dilution can quietly erase the benefit of economic growth.

## Formula

The expected equity market return is:

$$
E(R_e)=DY+\Delta(P/E)+i+g-\Delta S
$$

Where:

| Component | Meaning | Why it affects return |
|---|---|---|
| $DY$ | [[Dividend yield]] | Cash income received by shareholders |
| $\Delta(P/E)$ | Expected change in the market P/E multiple | Repricing: investors pay more or less for each dollar of earnings |
| $i$ | Expected [[Inflation]] | Turns real growth into nominal earnings growth |
| $g$ | Expected real earnings growth, often proxied by [[Real GDP]] growth | Long-run real growth in the economy's productive capacity |
| $\Delta S$ | Expected percent change in shares outstanding | New shares dilute existing owners; buybacks do the opposite |

To estimate the [[Equity risk premium|ERP]], subtract the [[Risk-free rate]]:

$$
ERP=E(R_e)-R_f
$$

Substituting the Grinold-Kroner expected return:

$$
ERP=DY+\Delta(P/E)+i+g-\Delta S-R_f
$$

You may also see the share-count term written as **repurchase yield**:

$$
\text{repurchase yield}=-\Delta S
$$

So the formula can be written:

$$
E(R_e)=DY+\Delta(P/E)+i+g+\text{repurchase yield}
$$

This is the same model. It just changes the sign convention.

## Why the Formula Exists

Start with the simple idea that equity return equals **income return plus capital gain**:

$$
E(R_e)=DY+\text{expected capital gain}
$$

The capital gain comes from the stock price rising. But price is linked to earnings and valuation:

$$
P=E \times (P/E)
$$

So a stock market can appreciate because:

1. Earnings per share grow.
2. The P/E multiple expands.

That gives:

$$
E(R_e)=DY+\Delta(P/E)+\text{earnings growth per share}
$$

Now break earnings growth per share into macro pieces:

$$
\text{earnings growth per share}=i+g-\Delta S
$$

Why? Because nominal earnings growth has a real part and an inflation part:

$$
\text{nominal growth}=i+g
$$

But shareholders own **earnings per share**, not total economy-wide earnings. If the market issues more shares, the earnings pie is divided among more claims:

$$
\text{EPS growth}<\text{aggregate earnings growth}
$$

So we subtract share dilution:

$$
E(R_e)=DY+\Delta(P/E)+i+g-\Delta S
$$

## The Share Dilution Mechanism

The $\Delta S$ term is where many candidates get tripped up.

| Share-count situation | $\Delta S$ | Impact in formula | Interpretation |
|---|---:|---:|---|
| New equity issuance | Positive | Subtracts from return | Existing shareholders are diluted |
| No net issuance or buybacks | Zero | No impact | Growth flows through unchanged |
| Net buybacks | Negative | Adds to return | Existing shareholders own a larger slice |

Example: If shares outstanding fall by 1%, then:

$$
\Delta S=-1\%
$$

The formula subtracts $\Delta S$:

$$
-\Delta S=-(-1\%)=+1\%
$$

So buybacks increase expected return through **repurchase yield**.

## Worked Numerical Example

Suppose an analyst is estimating the forward-looking return on a developed equity market:

| Input | Estimate |
|---|---:|
| Dividend yield, $DY$ | 2.2% |
| Expected P/E change, $\Delta(P/E)$ | 0.0% |
| Expected inflation, $i$ | 2.5% |
| Expected real GDP / earnings growth, $g$ | 2.0% |
| Expected change in shares outstanding, $\Delta S$ | -0.8% |
| Risk-free rate, $R_f$ | 3.5% |

First calculate expected equity market return:

$$
E(R_e)=DY+\Delta(P/E)+i+g-\Delta S
$$

$$
E(R_e)=2.2\%+0.0\%+2.5\%+2.0\%-(-0.8\%)
$$

$$
E(R_e)=7.5\%
$$

Then calculate ERP:

$$
ERP=E(R_e)-R_f
$$

$$
ERP=7.5\%-3.5\%=4.0\%
$$

The key arithmetic move is the buyback term:

$$
-(-0.8\%)=+0.8\%
$$

Because shares outstanding are shrinking, existing shareholders receive a return boost.

## Inflation and the ERP Trap

At first glance, higher expected inflation seems like it should increase the ERP because $i$ is added in the model:

$$
ERP=DY+\Delta(P/E)+i+g-\Delta S-R_f
$$

But if the [[Risk-free rate]] rises one-for-one with expected inflation, the ERP may not change:

```text
Higher inflation
  |
  v
Higher nominal earnings growth (+i)
  |
  v
Higher nominal risk-free rate (-Rf)
  |
  v
ERP roughly unchanged if both move together
```

So CFA may ask: "What happens to ERP if expected inflation rises?" The clean answer is: **not necessarily much**, if the nominal risk-free rate also rises by the same amount. Inflation can raise the expected nominal equity return without raising the expected excess return over the risk-free rate.

## Long-Run Interpretation

For very long-run analysis, the model becomes a guardrail against unrealistic equity return forecasts.

In the long run:

$$
\Delta(P/E)\approx 0
$$

because valuation multiples cannot expand forever. If P/E rose every year indefinitely, investors would eventually pay absurd prices for each dollar of earnings.

Also, real corporate earnings growth cannot permanently exceed real economic growth unless corporate profits become an ever-larger share of GDP forever. That cannot continue indefinitely because labor income, household demand, taxes, competition, and political constraints eventually matter.

So a long-run version is often:

$$
E(R_e)\approx DY+i+g-\Delta S
$$

If share dilution is assumed to be zero:

$$
E(R_e)\approx DY+i+g
$$

This is why the model connects to [[Potential GDP]]. Sustainable real growth in the economy places a ceiling on sustainable real earnings growth. Stock prices can run ahead of GDP for a while because of P/E expansion, profit-margin expansion, or buybacks, but those are not all permanent engines.

## When the Model Works Best

The Grinold-Kroner model works best when the public equity market is a large, representative part of the economy.

That usually fits:

| Market type | Fit |
|---|---|
| Developed, broad, liquid equity market | Better fit |
| Market where listed companies represent a large share of economic activity | Better fit |
| Small or developing market with few listed firms | Weaker fit |
| Economy where much growth comes from private firms not in the index | Weaker fit |

The last point matters. If much of a country's real GDP growth comes from private companies, startups, or state-owned enterprises outside the public market, then GDP growth may not flow into public-market EPS growth. The economy can grow quickly while listed shareholders do not fully capture that growth.

## Assumptions and Failure Modes

| Assumption | Why it matters | What breaks if false |
|---|---|---|
| Real GDP growth is a reasonable proxy for real earnings growth | Links macro growth to shareholder earnings | Public firms may not represent the economy |
| P/E change can be forecast or assumed zero | Captures valuation repricing | Multiple expansion/contraction may dominate short-run returns |
| Inflation flows into nominal earnings and risk-free rates | Separates nominal from real return | Inflation shocks may hurt margins or multiples |
| Share dilution is estimated correctly | Converts aggregate growth into per-share growth | Buybacks or issuance can materially change returns |
| Market is broad and developed | Makes macro-to-equity link more reliable | Developing markets may have weak public-market representation |

## Exam Traps

| Trap | Correct exam move |
|---|---|
| Treating GDP growth as equal to shareholder return | Add dividend yield, inflation, repricing, and dilution effects |
| Forgetting to subtract the risk-free rate when asked for ERP | First compute $E(R_e)$, then subtract $R_f$ |
| Getting the sign of share dilution wrong | Positive $\Delta S$ reduces return; negative $\Delta S$ increases return |
| Assuming P/E expansion is sustainable forever | For long-run estimates, $\Delta(P/E)$ is often assumed near zero |
| Thinking inflation always raises ERP | Inflation raises nominal equity return, but may also raise $R_f$ |
| Using the model in a developing market without caution | It may be inappropriate if public equities are not a large part of the economy |

## Comparison With Other ERP Approaches

| Approach | Core idea | Strength | Weakness |
|---|---|---|---|
| Historical ERP | Use past equity returns minus risk-free returns | Simple, data-based | Sensitive to sample period, survivorship, non-stationarity |
| Survey ERP | Ask experts what premium they expect | Forward-looking | Behavioral and response biases |
| DDM-implied ERP | Infer return from dividend yield plus growth | Market-price based | Growth and terminal assumptions are fragile |
| Grinold-Kroner | Build expected return from macro and market components | Explicitly decomposes income, growth, repricing, and dilution | Depends on forecasts and public-market representativeness |

## Memory Hooks

Use this sentence:

> **Equity return = income + repricing + nominal growth - dilution.**

Or:

$$
\text{GK}=\text{Dividends}+\text{P/E change}+\text{Inflation}+\text{Real growth}-\text{Share issuance}
$$

For ERP:

$$
\text{GK ERP}=\text{GK expected equity return}-R_f
$$

For the sign of buybacks:

> If the share count goes **down**, your ownership slice goes **up**, so expected return goes **up**.

## Related Concepts

- [[Equity risk premium]]
- [[Dividend yield]]
- [[Repurchase yield]]
- [[Cost of Capital]]
- [[Risk-free rate]]
- [[Real GDP]]
- [[Potential GDP]]
- [[CFA_Glossary/Economic growth]]
- [[Sustainable growth rate]]
- [[Historical equity risk premium approach]]
- [[Survey approach]]
