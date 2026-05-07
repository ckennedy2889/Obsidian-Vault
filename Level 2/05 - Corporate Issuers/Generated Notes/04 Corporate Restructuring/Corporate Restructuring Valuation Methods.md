---
title: "Corporate Restructuring Valuation Methods"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, restructuring, valuation, mergers-acquisitions]
aliases:
  - Comparable company analysis
  - Comparable transaction analysis
  - Premium paid analysis
  - Takeover premium
---

# Corporate Restructuring Valuation Methods

Corporate restructuring valuation is about estimating what a business, division, target, or combined company is worth **after** a transaction changes control, strategy, financing, or operating structure.

For CFA Level II, the key is not memorizing four methods in isolation. The key is knowing which method already includes a control premium, which method needs one added, and which method requires pro forma assumptions.

## The Four Methods

| Method | Core input | Best use | Control premium treatment |
|---|---|---|---|
| [[Discounted cash flow analysis]] | Forecasted free cash flows and discount rate | Detailed valuation of target or combined entity | Built into assumptions if modeled correctly |
| [[Comparable company analysis]] | Trading multiples of similar public companies | Spin-offs and trading-value estimates | Usually does **not** include takeover premium |
| [[Comparable transaction analysis]] | Multiples from actual M&A deals | Acquisitions | Already includes takeover premium |
| [[Premium paid analysis]] | Deal price vs unaffected share price | Judging acquisition premium | Directly measures premium |

## Comparable Company Analysis

Comparable company analysis values a target by applying the valuation multiples of similar publicly traded companies.

Common multiples:

- \(EV/EBITDA\)
- \(EV/Sales\)
- \(EV/FCFF\)
- \(P/E\)
- Sector-specific measures, such as \(EV/\text{subscribers}\) or \(EV/\text{reserves}\)

Basic process:

1. Identify comparable companies.
2. Calculate trading multiples for the peer set.
3. Choose a mean, median, or selected multiple.
4. Apply the multiple to the target's metric.
5. Add a takeover premium if using the result for an acquisition.

### Why it is often used for spin-offs

Comparable company analysis is based on publicly traded minority shares. That makes it more natural for valuing a spin-off, where the new company will trade as a public company and no buyer is necessarily paying for control.

### Advantages

- Data is accessible.
- It is market-based rather than entirely assumption-based.
- It is intuitive: similar assets should sell for similar values.

### Disadvantages

- True peers may not exist.
- Peer multiples may reflect market overvaluation or undervaluation.
- Different growth, margin, risk, and ROIC profiles can make comparisons misleading.
- The result is a fair trading value, not necessarily a fair takeover price.

## Comparable Transaction Analysis

Comparable transaction analysis values a target using multiples from actual acquisition transactions involving similar targets.

The key distinction: **transaction prices usually include a control premium.**

That makes comparable transaction analysis especially relevant for acquisitions.

### Advantages

- Based on actual deal prices.
- Control premium is already embedded.
- Useful for judging what buyers have recently paid for similar assets.

### Disadvantages

- Recent comparable deals may be scarce.
- Past deals may have occurred under different market, financing, regulatory, or industry conditions.
- Past acquirers may have overpaid or underpaid.
- Deal terms may differ in ways the multiple does not capture.

### Exam trap

Do not add another takeover premium to a comparable transaction valuation unless the question explicitly says the transaction multiple excludes one. In normal CFA wording, CTA multiples already include the price of control.

## Premium Paid Analysis

Premium paid analysis measures how much an acquirer pays above the target's unaffected market price.

Formula:

$$
\text{Premium} = \frac{DP - UP}{UP}
$$

Where:

| Term | Meaning |
|---|---|
| \(DP\) | Deal price per share |
| \(UP\) | Unaffected pre-announcement share price |

### Worked Example

A target's unaffected share price is \$40. The acquirer offers \$52 per share.

$$
\text{Premium} = \frac{52 - 40}{40} = \frac{12}{40} = 30\%
$$

### Why unaffected price matters

If rumors leaked before the announcement, the target's share price may already include part of the expected takeover premium. Using the announcement-day price can understate the true premium.

Analysts may use a price from before rumors began or a volume-weighted trading price over an earlier period.

## Discounted Cash Flow Analysis

DCF analysis values the target or combined entity by forecasting future free cash flows and discounting them at an appropriate rate.

DCF is useful when the analyst can model:

- Revenue synergies.
- Cost synergies.
- Integration costs.
- Working capital changes.
- Capital expenditure changes.
- Financing changes.
- Tax effects.
- Terminal value.

General DCF form:

$$
V_0 = \sum_{t=1}^{n} \frac{FCF_t}{(1+WACC)^t} + \frac{TV_n}{(1+WACC)^n}
$$

## Pro Forma Modeling in Restructurings

For acquisitions, the analyst often builds pro forma financial statements:

1. Combine acquirer and target revenues.
2. Adjust for revenue synergies or dis-synergies.
3. Combine operating expenses.
4. Adjust for cost synergies or integration costs.
5. Combine depreciation and amortization.
6. Add financing effects, such as new interest expense.
7. Estimate taxes.
8. Include additional shares issued as consideration.
9. Estimate pro forma EPS, leverage, and WACC.

## WACC Must Match the Restructured Firm

A restructuring can change:

- Business risk.
- Financial leverage.
- Collateral and recovery prospects.
- Cost of debt.
- Cost of equity.
- Debt and equity weights.

So the relevant discount rate is usually the **pro forma WACC**, not the acquirer's old WACC.

Weights should use market values and include new debt or equity issued in the transaction.

## Choosing the Right Method

| Vignette clue | Likely method |
|---|---|
| Public peers, spin-off, fair trading value | Comparable company analysis |
| Recent similar acquisitions, target takeover value | Comparable transaction analysis |
| Deal price vs unaffected market price | Premium paid analysis |
| Explicit synergies, financing, integration costs, pro forma projections | DCF |

## Exam Traps

- **CCA does not normally include a takeover premium.** Add one if valuing an acquisition.
- **CTA normally already includes a takeover premium.** Do not double count it.
- **Use unaffected price in premium paid analysis.** Announcement-day price may include rumors.
- **DCF is assumption-sensitive.** Synergies, terminal value, and WACC can dominate the result.
- **Use pro forma WACC for pro forma cash flows.** The transaction may change leverage and risk.
- **Mean vs median matters.** A peer outlier can distort the mean, so the median may be more representative.

## Memory Hook

**Trading comps show minority trading value. Deal comps show control value. Premium paid measures the control uplift. DCF models the actual future.**
