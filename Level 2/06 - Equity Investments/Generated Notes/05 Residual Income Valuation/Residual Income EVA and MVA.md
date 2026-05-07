---
title: "Residual Income EVA and MVA"
subject: "Equity Investments"
tags: [CFA-L2, equity, residual-income, EVA, MVA]
aliases:
  - Economic Value Added
  - Market Value Added
  - EVA
  - MVA
  - Economic profit
---

# Residual Income EVA and MVA

Accounting net income subtracts interest expense, but it does not subtract the cost of common equity. [[Residual income]], [[Economic Value Added]], and [[Market Value Added]] all address that problem by asking whether the company earned more than the capital providers required.

The exam distinction is about perspective:

| Measure | Perspective | Type |
|---|---|---|
| Residual income | Common equity | Period flow |
| EVA | Total capital providers | Period flow |
| MVA | Market value vs invested capital | Cumulative stock measure |

## Residual Income

Residual income is net income minus an equity charge:

$$
RI_t = NI_t - (r \times B_{t-1})
$$

Where:

| Term | Meaning |
|---|---|
| \(NI_t\) | Net income in period \(t\) |
| \(r\) | Required return on equity |
| \(B_{t-1}\) | Beginning book value of equity |

Equivalently:

$$
RI_t = (ROE_t-r)B_{t-1}
$$

Positive residual income means the company earned more than the shareholders' required return. Negative residual income means it destroyed value, even if net income was positive.

## Economic Value Added

EVA is a commercial implementation of economic profit. It uses a total-capital perspective:

$$
EVA = NOPAT - (\text{Total capital} \times WACC)
$$

Where:

$$
NOPAT = EBIT(1-t)
$$

EVA deducts the required return for both debt and equity capital through WACC.

### Common EVA Adjustments

EVA often adjusts accounting numbers to better reflect economic performance.

| Adjustment | Reason |
|---|---|
| Capitalize and amortize R&D | Treats R&D as investment rather than immediate expense |
| Add LIFO reserve to capital | Makes inventory capital comparable |
| Add increase in LIFO reserve to NOPAT | Removes inventory accounting distortion |
| Remove deferred taxes | Focuses on cash taxes |
| Capitalize operating leases | Treats leases as financing obligations |

The exam may give specific adjustments. Apply only the adjustments supported by the vignette.

## Market Value Added

MVA measures the market's cumulative assessment of value created:

$$
MVA = \text{Market value of company} - \text{Book value of total capital}
$$

Equity version:

$$
MVA_{\text{equity}} = \text{Market value of equity} - \text{Book value of equity}
$$

MVA is a stock measure at a point in time. RI and EVA are period flow measures.

## Worked Example

A company has:

- Assets: €2,000,000
- Debt: €1,000,000
- Equity: €1,000,000
- Pretax cost of debt: 7%
- Tax rate: 30%
- Cost of equity: 12%
- EBIT: €200,000

### Step 1: Net income

Interest expense:

$$
1{,}000{,}000 \times 7\% = €70{,}000
$$

Pretax income:

$$
200{,}000 - 70{,}000 = €130{,}000
$$

Net income:

$$
130{,}000(1-0.30)=€91{,}000
$$

### Step 2: Residual income

Equity charge:

$$
1{,}000{,}000 \times 12\% = €120{,}000
$$

Residual income:

$$
RI = 91{,}000 - 120{,}000 = -€29{,}000
$$

The company has positive net income but negative residual income. It did not earn enough to cover the equity investors' required return.

### Step 3: EVA without special adjustments

NOPAT:

$$
200{,}000(1-0.30)=€140{,}000
$$

WACC:

$$
WACC = 0.50(7\%)(1-0.30)+0.50(12\%)
$$

$$
WACC = 2.45\%+6.00\%=8.45\%
$$

Capital charge:

$$
2{,}000{,}000 \times 8.45\% = €169{,}000
$$

EVA:

$$
EVA = 140{,}000 - 169{,}000 = -€29{,}000
$$

Here RI and EVA produce the same value because there are no special EVA adjustments and the capital structure is simple.

## Why RI and EVA Can Match

When accounting is clean and no EVA adjustments are made, the equity-perspective and total-capital-perspective calculations can reconcile.

Residual income:

$$
NI - r_eE
$$

EVA:

$$
NOPAT - WACC(D+E)
$$

Because NOPAT is before financing costs and WACC includes after-tax debt cost and equity cost, both approaches can measure the same economic shortfall or surplus.

## Interpretation

| Metric result | Meaning |
|---|---|
| Positive RI or EVA | Company earned more than required return; value created |
| Zero RI or EVA | Company earned exactly required return; value neutral |
| Negative RI or EVA | Company earned less than required return; value destroyed |
| Positive MVA | Market values company above invested capital |
| Negative MVA | Market values company below invested capital |

For residual income valuation, expected positive future residual income supports a price-to-book ratio above 1.

## RI vs EVA vs MVA

| Feature | RI | EVA | MVA |
|---|---|---|---|
| Starting profit | Net income | NOPAT | Market value |
| Capital charge | Cost of equity x equity capital | WACC x total capital | Book capital subtracted from market value |
| Capital perspective | Equity | Debt plus equity | Market's cumulative value creation |
| Accounting adjustments | Usually fewer | Often many | Market-based |
| Period or point in time | Period | Period | Point in time |

## Exam Traps

- **Match the profit measure with the charge.** Net income pairs with equity charge; NOPAT pairs with total capital charge.
- **Calculate NOPAT from EBIT, not EBT.** Interest is ignored because debt cost is in WACC.
- **Use beginning capital for charges when specified.** Many RI calculations use beginning book value.
- **Positive net income can still mean negative RI.**
- **EVA adjustments affect both NOPAT and capital.** Do not adjust only one side when the vignette requires both.
- **MVA is not a one-period performance measure.** It is market value minus invested capital at a point in time.

## Memory Hook

**RI charges equity. EVA charges the whole firm. MVA asks what the market thinks all past charges and profits were worth.**
