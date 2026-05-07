---
title: "Private Company Valuation Framework"
subject: "Equity Investments"
tags: [CFA-L2, equity, private-company-valuation, valuation]
aliases:
  - Private company valuation
  - Discount for lack of control
  - Discount for lack of marketability
  - Guideline public company method
  - Guideline transactions method
---

# Private Company Valuation Framework

Private company valuation uses the same finance logic as public company valuation, but the inputs are harder to observe and the final value depends heavily on **control** and **marketability**.

The core exam question is: **what exactly is being valued?** A controlling interest in the whole company is not the same as a non-controlling, illiquid minority stake.

## Why Private Companies Are Valued

Private company valuations are commonly needed for:

| Purpose | Examples |
|---|---|
| Transactions | Venture capital, private equity, IPOs, acquisitions, divestitures |
| Compliance | Financial reporting, goodwill impairment, tax reporting |
| Litigation | Shareholder disputes, divorce, damages, lost profits |

The purpose matters because it can affect the standard of value, the level of control, and whether discounts or premiums apply.

## Private vs Public Companies

Private companies differ from public companies in two broad ways.

### Company-specific differences

- Smaller size.
- Earlier life-cycle stage.
- Less diversified operations.
- Limited financial disclosure.
- Lower quality or unaudited financial statements.
- Greater owner-manager overlap.
- More concentrated customer, supplier, or key-person risk.

Owner-manager overlap can reduce classic [[principal-agent conflict]], but it can also create related-party transactions, unusual compensation, or personal expenses running through the business.

### Stock-specific differences

- No active public market.
- Lower liquidity.
- Transfer restrictions.
- Concentrated ownership.
- Minority investors may lack control.

These stock-level traits lead to [[discount for lack of control]] and [[discount for lack of marketability]].

## Normalized Earnings and Cash Flow

Private company financial statements often need normalization before valuation.

The goal is to estimate what earnings and cash flows would look like under normal, arm's-length, market-based conditions.

| Adjustment | Why it is needed |
|---|---|
| Owner compensation | Replace above- or below-market owner pay with market salary |
| Personal expenses | Remove non-business expenses paid by the company |
| Related-party transactions | Restate to arm's-length pricing |
| Nonrecurring items | Remove unusual gains, losses, lawsuits, or one-time expenses |
| Real estate | Charge market rent to operations and value owned real estate separately |
| Excess cash or non-operating assets | Separate operating value from non-operating assets |

### Real estate adjustment

If the operating company owns the building it uses, analysts often:

1. Remove real-estate income or expenses that distort operations.
2. Deduct a market rent from operating earnings.
3. Value the operating company separately.
4. Add the real estate value as a non-operating asset.

The mechanism is that the operating business should be valued as if it paid a market cost for the space it uses.

## Three Valuation Approaches

| Approach | Core idea | Common methods |
|---|---|---|
| Income approach | Value equals present value of expected future economic benefits | DCF, capitalized cash flow, excess earnings |
| Market approach | Value inferred from market prices of comparable companies or transactions | GPCM, GTM, prior transaction method |
| Asset-based approach | Value equals fair value of assets minus liabilities | Adjusted net asset value |

## Income Approach

### Discounted cash flow

DCF values expected cash flows directly.

For FCFF:

$$
V_{\text{firm}} = \sum_{t=1}^{n}\frac{FCFF_t}{(1+WACC)^t} + \frac{TV_n}{(1+WACC)^n}
$$

For FCFE:

$$
V_{\text{equity}} = \sum_{t=1}^{n}\frac{FCFE_t}{(1+r_e)^t} + \frac{TV_n}{(1+r_e)^n}
$$

Use DCF when the analyst can build explicit forecasts and estimate risk.

### Capitalized cash flow method

The capitalized cash flow method is a single-stage model:

$$
V = \frac{CF_1}{r-g}
$$

It is appropriate when cash flow is expected to grow at a stable rate and detailed long-term projections are unavailable.

### Excess earnings method

The excess earnings method values intangible assets by:

1. Estimating normalized earnings.
2. Deducting required returns on working capital and fixed assets.
3. Capitalizing the remaining excess earnings as intangible value.
4. Adding working capital, fixed assets, and intangible value.

It is more common for valuing small businesses or intangible assets than for valuing large operating companies.

## Market Approach

### Guideline public company method

The [[guideline public company method]] uses multiples from comparable publicly traded companies.

Common multiples:

- \(EV/EBITDA\)
- \(EV/Sales\)
- \(P/E\)
- \(P/B\)

Because public companies and private companies differ in size, liquidity, risk, and capital structure, adjustments may be needed.

### Guideline transactions method

The [[guideline transactions method]] uses multiples from actual acquisitions of comparable companies.

This method often reflects control value because M&A transactions usually involve control premiums. But analysts must watch for:

- Synergies specific to the buyer.
- Contingent consideration.
- Non-cash payment terms.
- Market conditions at the transaction date.
- Strategic vs financial buyer differences.

### Prior transaction method

The prior transaction method uses actual past transactions in the subject company's own shares.

This can be useful because it uses the subject company directly, but stale transactions or unusual terms may make the price unreliable.

## Asset-Based Approach

The asset-based approach values the business as:

$$
\text{Equity value} = \text{Fair value of assets} - \text{Fair value of liabilities}
$$

It is most useful for:

- Asset-heavy companies.
- Holding companies.
- Investment companies.
- Liquidations.
- Companies with weak or negative earnings.

It may be less useful for operating companies whose value comes mainly from intangible assets, brand, customer relationships, or going-concern value.

## Control and Marketability

The same company can have different values depending on the interest being valued.

| Interest | Control? | Marketable? | Typical adjustment |
|---|---:|---:|---|
| Strategic control | Yes | Often yes | Highest value; may include synergies |
| Financial control | Yes | Often yes | Control premium without buyer-specific synergies |
| Marketable minority | No | Yes | No control premium |
| Nonmarketable minority | No | No | DLOC and DLOM may apply |

## Control Premium and DLOC

A control premium reflects the extra value of controlling corporate actions, such as:

- Choosing management.
- Setting dividend policy.
- Selling assets.
- Approving mergers.
- Changing capital structure.

If a valuation starts from a control value and the analyst needs a minority value, apply a discount for lack of control.

If the control premium is given:

$$
DLOC = 1 - \frac{1}{1+\text{Control premium}}
$$

### Worked Example: DLOC

If the control premium is 25%:

$$
DLOC = 1 - \frac{1}{1.25} = 1 - 0.80 = 20\%
$$

Do not subtract 25%. A 25% premium over minority value corresponds to a 20% discount from control value.

## DLOM

A discount for lack of marketability reflects the absence of a liquid market for the shares.

DLOM can be estimated using:

- Restricted stock studies.
- Pre-IPO transaction studies.
- Option-pricing methods.

The intuition behind option methods is that a put option can approximate the value of protection against being unable to sell.

## Combining DLOC and DLOM

Discounts are multiplicative, not additive:

$$
\text{Total discount} = 1 - [(1-DLOC)(1-DLOM)]
$$

### Worked Example

Suppose:

- DLOC = 15%
- DLOM = 20%

Then:

$$
\text{Total discount} = 1 - [(1-0.15)(1-0.20)]
$$

$$
= 1 - (0.85)(0.80) = 1 - 0.68 = 32\%
$$

Not 35%.

## Total Equity vs Minority Interest

Before applying discounts or premiums, identify the starting point.

| Starting value | Desired value | Adjustment |
|---|---|---|
| Minority marketable value | Control value | Add control premium |
| Control value | Minority value | Apply DLOC |
| Marketable value | Nonmarketable value | Apply DLOM |
| Control marketable value | Nonmarketable minority value | Apply DLOC, then DLOM multiplicatively |

## Exam Traps

- **Normalize owner compensation to market pay.** Do not remove compensation entirely.
- **Related-party transactions need arm's-length adjustment.**
- **Owned real estate is often separated.** Charge market rent to operations, then add real estate as a non-operating asset.
- **DLOC is not equal to the control premium.** Convert it with \(1 - 1/(1+\text{premium})\).
- **DLOC and DLOM are multiplicative.** Do not add them.
- **GTM transaction multiples may include control premiums.** GPCM trading multiples usually reflect minority marketable values.
- **Strategic buyers may pay more than financial buyers.** Synergies can justify a higher control value.
- **Know what is being valued.** Total equity, controlling interest, minority interest, and nonmarketable minority interest are not interchangeable.

## Memory Hook

**Private valuation is public valuation plus cleanup, control, and liquidity.**

First clean the financials. Then value the business. Then adjust for the exact ownership interest being valued.
