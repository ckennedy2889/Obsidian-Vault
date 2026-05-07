---
title: "Sum-of-the-Parts Valuation and Conglomerate Discount"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, valuation, applications-and-processes]
aliases: ["SOTP", "Sum-of-the-parts valuation", "Breakup value", "Private market value", "Conglomerate discount"]
---

# Sum-of-the-Parts Valuation and Conglomerate Discount

[[Sum-of-the-parts valuation]] values a company by valuing each business segment separately and adding the pieces together.

The intuition is simple: if one company contains several businesses with different economics, one blended multiple can hide value. Apple is not a classic unrelated conglomerate, but it is useful for the mechanics. Hardware products, services, wearables, and ecosystem monetization can deserve different valuation assumptions. A pure hardware multiple may undervalue services. A pure services multiple may overvalue hardware cyclicality.

In plain English:

```text
SOTP = value each business as if it stood alone, then subtract corporate-level claims and costs.
```

## Formula

A basic firm-level SOTP is:

$$
\text{Firm value} =
\sum \text{Segment values}
- \text{Corporate overhead value}
- \text{Debt and other non-equity claims}
+ \text{Nonoperating assets}
$$

Equity value per share is:

$$
\text{Equity value per share} =
\frac{\text{Equity value}}{\text{Shares outstanding}}
$$

The CFA exam often gives segment values directly. Your job is to remember the adjustments.

## Why SOTP Exists

SOTP is useful when a company has businesses that should not all be valued with the same model or multiple.

| Situation | Why SOTP helps |
|---|---|
| Multiple unrelated business lines | Each line has different risk and growth |
| Spin-off analysis | Estimate what pieces might trade for independently |
| Conglomerate valuation | Identify discount or premium to breakup value |
| Corporate restructuring | Assess whether breakup creates value |
| Different capital intensity by segment | Use different multiples or DCF assumptions |

## Apple-Style Illustration

Suppose an analyst separates Apple into three simplified economic pieces using FY2025 company revenue of about $\$416.2$ billion as the anchor:

| Segment | Normalized revenue | Selected EV/Sales multiple | Segment value |
|---|---:|---:|---:|
| Product ecosystem hardware | $\$300.0$B | 7.0x | $\$2,100.0$B |
| Services | $\$100.0$B | 12.0x | $\$1,200.0$B |
| Other ecosystem activities | $\$16.2$B | 5.0x | $\$81.0$B |

Total segment value:

$$
2{,}100.0 + 1{,}200.0 + 81.0 = 3{,}381.0
$$

Now suppose the present value of unallocated corporate overhead is $\$100.0$B, debt is $\$111.5$B, and cash plus investments are $\$132.4$B.

Equity value:

$$
3{,}381.0 - 100.0 - 111.5 + 132.4 = 3{,}301.9
$$

With about 14.776 billion shares:

$$
\text{SOTP value per share} =
\frac{3{,}301.9}{14.776}
= 223.47
$$

If Apple trades at $\$287.70$, then this specific SOTP model would not show a conglomerate discount. It would suggest the market is valuing the combined company above this analyst's simplified segment estimate. That could mean the multiples are too low, the segmentation is wrong, the market prices ecosystem synergies, or the analyst omitted valuable growth options.

The point is not that this is Apple's true value. The point is that SOTP is a framework for isolating where value is coming from.

## Conglomerate Discount

A [[Conglomerate discount]] exists when:

$$
\text{Market value} < \text{Sum-of-the-parts value}
$$

The discount can be stated as:

$$
\text{Conglomerate discount} =
1 - \frac{\text{Market value}}{\text{SOTP value}}
$$

If a conglomerate's SOTP value is $\$100$B and its market value is $\$85$B:

$$
\text{Discount} =
1 - \frac{85}{100}
= 15\%
$$

A discount means the market values the combined company below the estimated value of the pieces.

## Why Conglomerate Discounts May Exist

| Explanation | Mechanism |
|---|---|
| Inefficient internal capital allocation | Strong segments subsidize weak segments |
| Management complexity | Investors discount hard-to-understand firms |
| Agency costs | Managers may build empires rather than maximize value |
| Poor strategic fit | Unrelated businesses lack synergies |
| Measurement error | Analyst's SOTP may be too optimistic |

CFA wants you to know both sides: conglomerate discounts can reflect real inefficiency, but they can also reflect analyst measurement error.

## Corporate-Level Adjustments

The most common calculation trap is forgetting corporate-level items.

| Item | Treatment |
|---|---|
| Segment operating values | Add |
| Corporate overhead | Subtract present value |
| Debt | Subtract |
| Preferred stock or minority interest | Subtract if relevant |
| Excess cash and investments | Add |
| Nonoperating assets | Add |

If the exam gives three segment values and a headquarters cost, do not just sum the segments.

## Exam Traps

The first trap is using one blended multiple for unrelated segments. SOTP exists because segment economics differ.

The second trap is ignoring corporate overhead, debt, or nonoperating assets. Segment values are not automatically equity value.

The third trap is assuming every diversified company deserves a discount. Some diversified firms have synergies or capital allocation advantages.

The fourth trap is treating SOTP as liquidation value. SOTP usually values each segment as a going concern, not as assets sold in liquidation.

## Memory Hook

> [!tip] Memory Hook
> SOTP says, "Value the pieces like businesses, then subtract the corporate baggage."

## Related Concepts

- [[Sum-of-the-parts valuation]]
- [[Breakup value]]
- [[Conglomerate discount]]
- [[Going Concern Value vs Liquidation Value]]
- [[Intrinsic Value and Perceived Mispricing]]
- [[Market-Based Valuation]]
