---
title: Goodwill - Full vs Partial and Impairment
subject: Financial Statement Analysis
tags:
  - CFA-L2
  - FSA
  - intercorporate-investments
  - goodwill
  - impairment
aliases:
  - Goodwill full vs partial
  - Full goodwill
  - Partial goodwill
  - Goodwill impairment
---

# Goodwill - Full vs Partial and Impairment

Goodwill is the acquisition premium that cannot be pinned to a separately identifiable asset. If the acquirer pays more than the fair value of the target's identifiable net assets, the extra value is attributed to things like expected synergies, assembled workforce, brand reputation, and strategic position.

For CFA Level II, goodwill is not just a plug. It changes [[Balance sheet]] size, [[Non-controlling interest]], return ratios, impairment losses, and comparability between [[IFRS]] and [[US GAAP]].

## Where Goodwill Appears

Goodwill arises under the [[Acquisition Method]] when one company obtains control of another company.

It does **not** arise as a separate line item under the [[Equity Method]]. Under the equity method, any acquisition premium is embedded inside the single investment account and the entire investment is tested for impairment.

## Partial vs Full Goodwill

Assume Parent buys less than 100% but still obtains control. There are two measurement approaches.

| Method | Allowed under | Intuition | Goodwill recognized |
|---|---|---|---|
| Partial goodwill | IFRS only | Recognize only the parent's purchased share of goodwill | Parent's share only |
| Full goodwill | US GAAP required; IFRS allowed | Treat the whole subsidiary as measured at fair value | Parent + NCI share |

### Partial Goodwill

$$
\text{Partial goodwill}
= \text{Purchase price}
- (\%\text{ acquired} \times FV_{\text{net identifiable assets}})
$$

Partial goodwill recognizes only the goodwill embedded in the controlling stake actually purchased by the parent.

### Full Goodwill

$$
\text{Full goodwill}
= FV_{\text{subsidiary as a whole}}
- FV_{\text{net identifiable assets}}
$$

When the only observable value is the purchase price for a controlling percentage:

$$
FV_{\text{subsidiary as a whole}}
= \frac{\text{Purchase price}}{\%\text{ acquired}}
$$

Full goodwill recognizes goodwill attributable to both the parent and the [[Non-controlling interest]].

## Worked Example

Parent pays 800 for 80% of Target. The fair value of Target's identifiable net assets is 900.

$$
FV_{\text{target}} = \frac{800}{0.80} = 1{,}000
$$

| Item | Partial goodwill | Full goodwill |
|---|---:|---:|
| Purchase price / implied entity value | 800 | 1,000 |
| Less fair value of net identifiable assets | $80\% \times 900 = 720$ | 900 |
| Goodwill | 80 | 100 |

Full goodwill is larger because it includes the goodwill attributable to the 20% not owned by the parent.

## NCI Link

The goodwill method also changes NCI.

| Method | NCI measurement |
|---|---|
| Full goodwill | $\%\text{ minority} \times FV_{\text{subsidiary as a whole}}$ |
| Partial goodwill | $\%\text{ minority} \times FV_{\text{net identifiable assets}}$ |

This is why full goodwill increases both total assets and total equity. Higher assets usually lower [[ROA]], and higher equity usually lowers [[ROE]], even when the income statement is unchanged.

## Impairment

Goodwill is not amortized. It has an indefinite life and is tested for impairment at least annually.

The intuition is simple: if the acquisition premium no longer has economic support, the firm must write it down. The write-down is recognized in the [[Income statement]] and is not reversible under either IFRS or US GAAP.

### IFRS Impairment Approach

IFRS uses a one-step recoverable amount test.

1. Allocate goodwill to the [[cash-generating unit]] that benefits from the acquisition.
2. Compare recoverable amount with carrying value.
3. If recoverable amount is lower, recognize an impairment loss.
4. Apply the loss first to goodwill.
5. If goodwill is reduced to zero, allocate the excess impairment to other assets pro rata.

Recoverable amount is the higher of value in use and fair value less costs to sell.

### US GAAP Impairment Approach

US GAAP tests goodwill at the reporting unit level.

The traditional exam framing is:

1. Compare reporting unit fair value with carrying value.
2. If fair value is at least carrying value, no impairment.
3. If fair value is below carrying value, estimate implied goodwill.
4. Impairment equals carrying goodwill minus implied goodwill.

US GAAP impairment is capped at the amount of goodwill. It does not allocate extra loss to other assets through the goodwill impairment test.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| "Full goodwill creates more income." | False. Full vs partial goodwill changes the balance sheet, not initial consolidated net income. |
| "Goodwill is amortized." | False for acquisition goodwill. It is tested for impairment. |
| "Partial goodwill is available under US GAAP." | False. US GAAP requires full goodwill. |
| "A bargain purchase creates negative goodwill." | For exam purposes, a bargain purchase gain is recognized in income after reassessing measurements. |
| "Goodwill impairment reverses later if value recovers." | False. Goodwill impairment is not reversed. |

## Analyst Implications

Large goodwill can signal an acquisition-heavy strategy. That is not automatically bad, but it raises quality questions:

- Did the acquirer overpay?
- Were identifiable assets understated so that goodwill was overstated?
- Are future impairment losses likely?
- Are current return ratios being depressed by a large goodwill balance?
- Is management using "one-time" impairment losses to clean up past overstatement?

## Memory Hook

Partial goodwill asks, "What premium did the parent buy?"

Full goodwill asks, "What premium exists in the whole controlled company?"

## Related Concepts

- [[Acquisition Method]]
- [[Equity Method]]
- [[Non-controlling interest]]
- [[Impairment]]
- [[Fair value]]

