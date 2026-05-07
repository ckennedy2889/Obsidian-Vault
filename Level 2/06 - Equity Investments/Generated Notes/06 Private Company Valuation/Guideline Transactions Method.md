---
title: "Guideline Transactions Method"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, private-company-valuation, market-approach]
aliases: ["GTM", "Guideline transactions method", "Transaction method"]
---

# Guideline Transactions Method

The [[Guideline Transactions Method]] (GTM) values a private company using multiples from acquisitions of entire companies.

If GPCM asks, "What do public investors pay for minority shares?", GTM asks, "What have buyers paid to acquire control of comparable businesses?" That distinction drives most CFA exam traps.

In plain English:

```text
GTM = use acquisition multiples from comparable transactions to value a private company.
```

## How GTM Works

1. Identify comparable acquisitions.
2. Calculate transaction multiples such as EV/Sales, EV/EBITDA, or price/earnings.
3. Adjust for transaction date, market conditions, synergies, payment type, and comparability.
4. Apply the selected transaction multiple to the private target's normalized metric.
5. Apply marketability or minority adjustments only if needed for the specific ownership interest.

## Why GTM Is Different From GPCM

The key difference is control.

| Method | Data source | Usual value basis |
|---|---|---|
| [[Guideline Public Company Method]] | Public trading prices | Marketable minority |
| [[Guideline Transactions Method]] | Acquisition prices for whole companies | Controlling interest |

Acquisition prices often include [[Control premium|control premiums]] because buyers are purchasing the ability to set strategy, replace management, change payout policy, restructure assets, and integrate the target.

Therefore, if GTM gives a control value, do not add another control premium unless the question clearly says the transaction multiples exclude control value.

## Apple Supplier Example

Suppose an analyst is valuing a private Apple supplier. Public trading multiples suggest a minority marketable value of $\$12.8$ billion under GPCM. But recent acquisitions of comparable component manufacturers show a median transaction EV/Sales multiple of 12.5x.

If the supplier has normalized revenue of $\$1.2$ billion:

$$
\text{GTM enterprise value} =
1.2 \times 12.5
= 15.0
$$

That $\$15.0$ billion is a transaction-based control value if the comparable deals were acquisitions of entire companies.

If the valuation is for a 100% controlling acquisition, no separate control premium is needed.

If the valuation is for a 20% nonmarketable minority interest, the analyst must move from control to minority and then from marketable to nonmarketable.

Assume a 25% observed control premium and 20% DLOM.

Convert control premium to DLOC:

$$
\text{DLOC} =
1 - \frac{1}{1 + 0.25}
= 20\%
$$

Pro rata control value:

$$
15.0 \times 20\% = 3.0
$$

Apply DLOC and DLOM multiplicatively:

$$
\text{Value} =
3.0 \times (1 - 0.20)(1 - 0.20)
$$

$$
\text{Value} =
3.0 \times 0.80 \times 0.80
= 1.92
$$

The exam trap answer would often be:

$$
3.0 \times (1 - 0.25 - 0.20) = 1.65
$$

That is wrong for two reasons: it uses the control premium as if it were the DLOC, and it adds discounts instead of multiplying the survivor percentages.

## Transaction Adjustments

Not every acquisition multiple is clean. CFA expects you to think about what is inside the transaction price.

| Issue | Why it matters |
|---|---|
| Strategic versus financial buyer | Strategic buyers may pay for synergies that the subject buyer cannot realize |
| Contingent consideration | Earnouts indicate uncertainty and make headline value harder to compare |
| Stock consideration | Acquirer shares may be overvalued or undervalued |
| Transaction date | Market multiples may have changed since the deal |
| Industry cycle | Hot M&A markets can embed unusually high premiums |
| Data availability | Private deal terms may be incomplete |

## Control Premium Caution

GTM usually embeds control value. That is its strength and its danger.

If the task is to value a controlling interest, GTM can be directly relevant. If the task is to value a minority interest, the analyst may need a [[Discount for Lack of Control]].

But do not double-count:

```text
GTM control value + control premium = usually wrong
```

The transaction multiple usually already includes what buyers paid for control.

## GTM Versus Prior Transaction Method

GTM uses transactions involving comparable companies. The [[Prior Transaction Method]] uses historical transactions in the subject company's own shares.

| Method | Evidence |
|---|---|
| GTM | Deals involving comparable companies |
| Prior transaction method | Past sales of the subject company's own equity |

Prior transactions can be highly relevant, but stale prices, related-party transactions, and changes in company prospects can make them unreliable.

## Exam Traps

The first trap is adding a control premium to GTM. If the comparable transactions were acquisitions of entire companies, the multiple already reflects control.

The second trap is failing to adjust from control value to minority value. If the final interest is minority and the starting value is control, a DLOC may be needed.

The third trap is using a strategic-buyer transaction to value a financial-buyer deal. Strategic synergies can overstate stand-alone fair value.

The fourth trap is ignoring transaction date. A 2021 high-growth software acquisition multiple may not be relevant in a later, higher-rate environment.

## Memory Hook

> [!tip] Memory Hook
> GTM uses deal prices. Deal prices usually buy control, so the control premium is usually already inside the multiple.

## Related Concepts

- [[Guideline Public Company Method]]
- [[Control premium]]
- [[Discount for Lack of Control]]
- [[Discount for Lack of Marketability]]
- [[Private Company Valuation Framework]]
