---
title: "Going Concern Value vs Liquidation Value"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, valuation, applications-and-processes]
aliases: ["Going concern assumption", "Going concern value", "Liquidation value", "Orderly liquidation value"]
---

# Going Concern Value vs Liquidation Value

The [[Going concern assumption]] says the company will keep operating instead of shutting down and selling its assets.

That assumption sits underneath almost every equity valuation model in Level II. A [[Dividend Discount Model]] assumes future dividends. A [[Free Cash Flow Valuation|free cash flow model]] assumes future operating cash flows. A [[Residual Income Valuation|residual income model]] assumes future earnings on book value. If the company will not survive, those models are answering the wrong question.

Use Apple as the clean case. Apple's FY2025 revenue was about $\$416.2$ billion, net income was about $\$112.0$ billion, and total assets were about $\$359.2$ billion. Investors do not value Apple mainly by asking what its stores, servers, inventory, and devices would fetch in a forced sale. They value Apple as an operating ecosystem that can keep earning cash flows.

## Definitions

| Concept | Meaning |
|---|---|
| Going concern value | Value of the company as an operating business |
| Liquidation value | Value if assets are sold separately and liabilities are paid |
| Orderly liquidation value | Liquidation value when assets can be sold over time |
| Forced liquidation value | Liquidation value under time pressure or distress |

The basic liquidation logic is:

$$
\text{Liquidation value to equity} =
\text{Estimated asset sale proceeds} - \text{Liabilities} - \text{Liquidation costs}
$$

Going concern value is usually based on present value:

$$
\text{Going concern value} =
\text{PV of expected future cash flows}
$$

## Why Going Concern Value Usually Exceeds Liquidation Value

Assets are usually worth more together than apart.

Apple's physical and financial assets matter, but the operating business includes more than recorded assets:

- brand value
- customer relationships
- software ecosystem
- supplier relationships
- employee knowledge
- installed user base
- pricing power

Many of those assets are hard to sell separately. They are valuable because they work together inside the operating company.

```text
Separate assets: inventory + stores + cash + equipment
Operating business: assets + people + systems + customers + strategy
```

That is why a profitable going concern usually trades far above book value or liquidation value.

## Apple Numerical Illustration

Suppose an analyst considers a rough liquidation thought experiment using simplified FY2025 balance sheet data:

| Item | Amount |
|---|---:|
| Total assets | $\$359.2$B |
| Total liabilities | $\$285.5$B |
| Shareholders' equity | $\$73.7$B |

Book equity is:

$$
359.2 - 285.5 = 73.7
$$

But liquidation proceeds would not necessarily equal book value. Some assets might sell below carrying value, while some investments and cash-like assets may be closer to fair value. If liquidation costs and asset haircuts reduced recoverable asset value to $\$330.0$B:

$$
\text{Liquidation value to equity} =
330.0 - 285.5 = 44.5
$$

With about 14.776 billion shares outstanding:

$$
\text{Liquidation value per share} =
\frac{44.5}{14.776}
= 3.01
$$

That is nowhere near a market price around $\$287.70$ because Apple is being valued as a cash-generating enterprise, not a pile of separable assets. The exact liquidation estimate is illustrative, but the intuition is the CFA point.

## When Liquidation Value Matters

Liquidation value becomes relevant when going concern is doubtful.

| Situation | More relevant value |
|---|---|
| Healthy public company | Going concern value |
| Stable dividend payer | DDM / FCF / RI under going concern |
| Distressed company near bankruptcy | Liquidation value |
| Asset-rich company with weak operations | Compare going concern and liquidation |
| Reorganization candidate | Going concern after restructuring may matter |

If liquidation value exceeds going concern value, the company may be worth more broken apart than operated.

## Orderly vs Forced Liquidation

Orderly liquidation assumes the company has time to sell assets carefully. Forced liquidation assumes assets must be sold quickly, usually at worse prices.

| Type | Sale process | Expected proceeds |
|---|---|---|
| Orderly liquidation | Patient sale over time | Higher |
| Forced liquidation | Fire sale under pressure | Lower |

The exam may describe a company that has time to dispose of assets. That points to orderly liquidation value, not forced liquidation value.

## Exam Traps

The first trap is using going concern models for a company that cannot continue operating. If the vignette says survival is doubtful, liquidation value may be the right answer.

The second trap is treating book value as liquidation value. Book value is accounting capital. Liquidation value is estimated sale proceeds minus liabilities and costs.

The third trap is ignoring intangible going concern value. A profitable public company can be worth far more than the liquidation value of its recorded assets.

The fourth trap is confusing liquidation value with fair market value. Liquidation is a premise of value; fair market value is a transaction definition.

## Memory Hook

> [!tip] Memory Hook
> Going concern asks, "What can the business earn?" Liquidation asks, "What can the pieces sell for?"

## Related Concepts

- [[Going concern assumption]]
- [[Liquidation value]]
- [[Orderly liquidation value]]
- [[Intrinsic Value and Perceived Mispricing]]
- [[Sum-of-the-Parts Valuation and Conglomerate Discount]]
- [[Equity Valuation Applications and Model Selection]]
