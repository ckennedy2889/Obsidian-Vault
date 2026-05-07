---
title: "Equity Valuation Applications and Model Selection"
subject: "Equity Investments"
tags: [CFA-L2, equity, valuation, model-selection]
aliases:
  - Intrinsic value
  - Going concern value
  - Liquidation value
  - Sum-of-the-parts valuation
  - Conglomerate discount
---

# Equity Valuation Applications and Model Selection

Equity valuation is the process of estimating what a stock or business is worth. The CFA Level II emphasis is practical: choose a model that fits the company, the data, and the purpose of the valuation.

The central comparison is:

$$
\text{Estimated value} \quad \text{vs.} \quad \text{Market price}
$$

But the exam wants you to remember that your estimate can be wrong.

## Intrinsic Value and Mispricing

[[Intrinsic value]] is the value an investor would assign if they had complete understanding of an asset's investment characteristics.

Because true intrinsic value is unobservable, analysts estimate it:

| Symbol | Meaning |
|---|---|
| \(P\) | Market price |
| \(V\) | True intrinsic value |
| \(V_E\) | Analyst's estimated intrinsic value |

The perceived mispricing can be decomposed as:

$$
V_E - P = (V-P) + (V_E-V)
$$

Where:

| Component | Meaning |
|---|---|
| \(V-P\) | True mispricing |
| \(V_E-V\) | Valuation error |

This is a major exam idea. If your model says a stock is undervalued, that could mean the market is wrong, or it could mean your valuation estimate is wrong.

## Margin of Safety and Catalysts

Because valuation error exists, analysts often require a margin of safety before acting. The less confidence you have in the inputs, the larger the required gap between estimated value and price should be.

Also, undervaluation does not guarantee quick convergence. A catalyst may be needed, such as:

- Earnings surprise.
- Restructuring.
- Asset sale.
- Takeover bid.
- Regulatory change.
- Capital return announcement.

## Going Concern vs Liquidation Value

| Value concept | Assumption | Typical use |
|---|---|---|
| [[Going concern value]] | Company continues operating | Most public equity valuation |
| [[Liquidation value]] | Company is dissolved and assets are sold separately | Distress, bankruptcy, downside floor |

Going concern value usually exceeds liquidation value because assets are worth more when organized into a functioning business with customers, employees, systems, and strategy.

For distressed firms, compare both. If liquidation value exceeds going concern value, the company may be worth more broken apart than operated.

## Definitions of Value

| Definition | Meaning |
|---|---|
| Fair market value | Price between willing, informed buyer and seller, neither compelled |
| Investment value | Value to a specific buyer, including buyer-specific synergies |
| Intrinsic value | Analyst's estimate of fundamental value based on investment characteristics |

For public company valuation, intrinsic value is usually the most relevant concept. For an acquisition, investment value may exceed fair market value if a buyer can realize synergies.

## Applications of Equity Valuation

Analysts use valuation to:

- Select stocks.
- Infer market expectations embedded in price.
- Evaluate mergers, acquisitions, spin-offs, and restructurings.
- Issue fairness opinions.
- Appraise private companies.
- Estimate terminal value in DCF models.
- Evaluate compensation, tax, or legal claims.

## Industry and Competitive Analysis

Before forecasting cash flows, the analyst needs to understand the business.

Key questions:

| Question | Why it matters |
|---|---|
| What industry is the company in? | Defines growth, margins, cyclicality, and peers |
| Is the industry attractive? | Determines whether returns can exceed the cost of capital |
| What is the company's competitive strategy? | Explains how revenue and margins are generated |
| Does the firm have a moat? | Determines persistence of excess returns |
| How strong are suppliers and buyers? | Affects pricing power and margins |
| Are there substitutes or new entrants? | Affects long-run growth and profitability |
| What are the key value drivers? | Guides model assumptions |

Porter's five forces are often used to organize this analysis:

- Rivalry among existing competitors.
- Threat of new entrants.
- Threat of substitutes.
- Supplier power.
- Buyer power.

## Absolute vs Relative Valuation

| Model type | Core idea | Examples |
|---|---|---|
| Absolute valuation | Estimate standalone intrinsic value | DDM, FCFF, FCFE, residual income, asset-based valuation |
| Relative valuation | Compare to similar assets | P/E, P/B, P/S, EV/EBITDA, EV/Sales |

Absolute valuation can identify whether an entire sector is overvalued or undervalued. Relative valuation is faster and market-grounded, but it can only say cheap or expensive relative to peers.

Exam trap: a stock can be cheap relative to overvalued peers and still be overvalued in absolute terms.

## Sum-of-the-Parts Valuation

[[Sum-of-the-parts valuation]] values each business segment separately and then adds the segment values.

It is useful when a company has multiple unrelated businesses.

General process:

1. Identify distinct business segments.
2. Choose peers or valuation models for each segment.
3. Estimate each segment's value.
4. Add non-operating assets.
5. Subtract debt and other claims.
6. Compare total value with market value.

## Conglomerate Discount

A [[conglomerate discount]] exists when a diversified company's market value is less than the estimated sum of its parts.

Possible explanations:

- Inefficient internal capital allocation.
- Loss of strategic focus.
- Management empire building.
- Complexity that makes analysis harder.
- Poor disclosure by segment.
- Measurement error in the analyst's sum-of-the-parts estimate.

The exam may also mention endogenous factors: weak companies may diversify to hide poor performance, so the discount may reflect company quality rather than diversification itself.

## Model Selection Criteria

Choose a valuation model based on three broad criteria.

### Company characteristics

| Company feature | More suitable model |
|---|---|
| Stable dividends and mature growth | DDM |
| No dividends or dividends far below capacity | FCFF or FCFE |
| Changing capital structure | FCFF |
| Meaningful book value and poor dividend/FCF fit | Residual income |
| Multiple unrelated segments | Sum-of-the-parts |
| Asset-heavy or liquidation case | Asset-based valuation |
| Private company | Income, market, or asset approach with private-company adjustments |

### Data availability and quality

Use a model only if the required inputs are available and credible. A complex multistage model is not superior if the forecasts are unsupported.

This is the law of parsimony: use the simplest model that adequately captures the economics.

### Purpose and perspective

| Perspective | More relevant model |
|---|---|
| Minority public shareholder | DDM may be relevant if dividends drive returns |
| Control buyer | FCFF/FCFE more relevant because buyer can change payout policy |
| Distressed investor | Liquidation value and going concern comparison |
| M&A buyer | Investment value and synergies |

## Exam Traps

- **Estimated value is not true value.** \(V_E-P\) includes valuation error.
- **Undervalued does not mean immediate convergence.** A catalyst and time horizon matter.
- **Going concern and liquidation values answer different questions.**
- **Investment value can exceed fair market value because of buyer-specific synergies.**
- **Relative cheapness is not absolute cheapness.** The peer group may be mispriced.
- **Do not force a DDM on a non-dividend payer.**
- **Do not choose the most complex model by default.** Match complexity to data quality.
- **Conglomerate discount may reflect inefficiency, opacity, or measurement error.**

## Memory Hook

**Value the business that exists, with the data you have, for the investor you represent.**
