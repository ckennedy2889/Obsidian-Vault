---
title: "Discount for Lack of Marketability"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, private-company-valuation, discounts-and-premiums]
aliases: ["DLOM", "Lack of marketability discount", "Discount for lack of liquidity"]
---

# Discount for Lack of Marketability

A [[Discount for lack of marketability]] (DLOM) is the haircut applied because an ownership interest cannot be sold quickly, cheaply, and reliably.

Think about owning shares of Apple versus owning a 10% minority stake in a private Apple supplier. You can sell Apple stock in seconds. You may not be able to sell the private stake for months, and even then you may need board approval, a negotiated buyer, legal review, and a price concession. The business may be valuable, but the ownership interest is less useful because it is illiquid. DLOM prices that loss of flexibility.

In plain English:

```text
DLOM = the value reduction for being stuck with an otherwise valuable ownership interest.
```

## Where DLOM Fits

Private company valuation has two separate ownership questions:

| Question | Adjustment |
|---|---|
| Does the stake control the company? | [[Discount for Lack of Control]] or [[Control premium]] |
| Can the stake be readily sold? | [[Discount for Lack of Marketability]] |

DLOM is about saleability, not power. A controlling owner can still face DLOM if the company is private and the stake cannot be sold easily. A minority owner can face both [[DLOC]] and DLOM.

## Formula

If a marketable value is known, the nonmarketable value is:

$$
\text{Nonmarketable value} =
\text{Marketable value} \times (1 - \text{DLOM})
$$

If a private minority stake has a marketable value of $\$10.0$ million and the appropriate DLOM is 20%:

$$
\text{Nonmarketable value} =
10.0 \times (1 - 0.20)
= 8.0
$$

The discount is not saying the business is worse. It is saying the ownership interest is harder to convert into cash.

## Apple Supplier Example

Suppose a private electronics-component company sells into Apple's ecosystem. Public trading multiples from Apple, Microsoft, and Nvidia imply a marketable minority value of $\$12.8$ billion for the private company after normalizing revenue and margins.

Now suppose the valuation is for a 15% minority interest with transfer restrictions and no likely IPO. The analyst estimates a DLOM of 25%.

Pro rata marketable minority value:

$$
12.8 \times 15\% = 1.92
$$

Apply DLOM:

$$
\text{Nonmarketable minority value} =
1.92 \times (1 - 0.25)
= 1.44
$$

The $\$480$ million difference is the price of illiquidity:

$$
1.92 - 1.44 = 0.48
$$

## Factors That Increase Or Decrease DLOM

| Factor | Effect on DLOM | Why |
|---|---|---|
| Impending IPO or sale | Decreases | Liquidity is coming soon |
| Contractual sale restrictions | Increases | Holder cannot freely sell |
| Larger pool of potential buyers | Decreases | Easier exit |
| Greater ownership concentration | Increases | Fewer buyers and more governance risk |
| Higher asset or earnings volatility | Increases | Buyer demands compensation for holding risk |
| Reliable dividends | Decreases | Investor receives cash while waiting |

The key mechanism is opportunity cost. The longer and riskier the expected holding period, the more value the investor gives up by being unable to sell.

## Estimation Methods

CFA emphasizes three DLOM estimation approaches.

| Method | How it works | Main caution |
|---|---|---|
| Restricted stock studies | Compare restricted shares with freely traded shares of the same company | Restrictions may not match the subject company |
| Pre-IPO studies | Compare private transaction prices before IPO with IPO/public prices | Price change may reflect lower business risk, not only liquidity |
| Put option approach | Estimate value of price protection during the illiquidity period | A put gives downside protection, not actual liquidity |

## Put Option Approach

The option approach treats illiquidity like being unable to sell during a lockup period. If the owner cannot sell, one way to protect against price declines is to buy a put option. The put's value becomes a proxy for DLOM.

$$
\text{DLOM} =
\frac{\text{At-the-money put option value}}{\text{Stock price}}
$$

If the comparable stock price is $\$100$ and an at-the-money put for the expected restriction period is worth $\$18$:

$$
\text{DLOM} =
\frac{18}{100}
= 18\%
$$

This method has a nice intuition: more volatility, longer lockup, and higher uncertainty increase the put value, so they increase DLOM.

The limitation is also important. A put option protects price; it does not create a buyer for the private shares. Therefore, the option method estimates part of the illiquidity cost, not a perfect marketability discount.

## Combining DLOM With DLOC

If both [[DLOC]] and DLOM apply, combine them multiplicatively:

$$
\text{Total discount} =
1 - (1 - \text{DLOC})(1 - \text{DLOM})
$$

If DLOC is 20% and DLOM is 25%:

$$
\text{Total discount} =
1 - (0.80)(0.75)
= 40\%
$$

Do not add them:

$$
20\% + 25\% = 45\% \quad \text{wrong}
$$

The reason is base consistency. The second discount applies after the first discount has already reduced the value.

## Exam Traps

The most common trap is adding DLOC and DLOM. CFA wants the multiplicative survivor formula.

The second trap is applying DLOM to a value that already reflects illiquidity. If the transaction evidence comes from private restricted sales, some marketability discount may already be embedded.

The third trap is confusing marketability with control. A controlling shareholder may still need DLOM if the company is private. A minority shareholder may need both DLOC and DLOM.

The fourth trap is thinking an IPO always eliminates DLOM. An imminent IPO usually reduces DLOM, but lockup agreements, uncertainty, and sale restrictions may still matter.

## Memory Hook

> [!tip] Memory Hook
> DLOM is the "I cannot sell this easily" discount. DLOC is power. DLOM is liquidity.

## Related Concepts

- [[Discount for Lack of Control]]
- [[Control premium]]
- [[Guideline Public Company Method]]
- [[Guideline Transactions Method]]
- [[Private Company Valuation Framework]]
