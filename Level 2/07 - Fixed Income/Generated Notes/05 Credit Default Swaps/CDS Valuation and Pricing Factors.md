---
title: CDS Valuation and Pricing Factors
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-default-swaps, credit-risk, valuation]
aliases: [CDS valuation, CDS pricing factors, fair CDS spread, CDS upfront premium]
---

# CDS Valuation and Pricing Factors

## The Real-World Analogy

A [[Credit Default Swap|credit default swap]] is like buying insurance on a bond or loan. The protection buyer pays a recurring premium. The protection seller collects those premiums, but must make a large payment if the reference borrower has a defined credit event.

The valuation problem is the same as insurance pricing:

```text
Expected value of premiums collected
        =
Expected value of claims paid
```

For a CDS, those two sides are called the **premium leg** and the **protection leg**.

## Plain-English Definition

CDS valuation asks: what is the fair price of credit protection today?

At initiation, a fair CDS contract is priced so that:

$$
\text{PV(Premium Leg)} = \text{PV(Protection Leg)}
$$

The **premium leg** is the expected present value of the periodic payments made by the protection buyer. The **protection leg** is the expected present value of the payment the seller must make if default occurs.

The fair CDS spread is the periodic premium rate that makes those two present values equal.

## The Two Legs

| Leg | Paid by | Paid to | What it represents | Key driver |
|---|---:|---:|---|---|
| Premium leg | Protection buyer | Protection seller | Regular CDS coupon payments | Survival probability, coupon, discount rate |
| Protection leg | Protection seller | Protection buyer | Default compensation payment | Default probability, loss given default, discount rate |

The important CFA intuition is that the premium leg is not risk-free. The buyer pays the CDS coupon only while the reference entity has not defaulted. Once a credit event occurs, the premium payments stop and the protection settlement happens.

So default risk affects both sides:

```text
Higher default risk
  -> higher expected protection payment
  -> fewer expected future premium payments
  -> higher fair CDS spread
```

## Core Formula Logic

The protection seller's expected payout depends on two things:

1. The probability that default happens.
2. The loss if default happens.

The loss percentage is:

$$
\text{LGD} = 1 - \text{Recovery Rate}
$$

where **LGD** is [[Loss Given Default]].

A simple one-period approximation is:

$$
\text{CDS spread} \approx \text{POD} \times \text{LGD}
$$

or:

$$
\text{CDS spread} \approx \text{POD} \times (1 - \text{Recovery Rate})
$$

This formula works because a fair insurance premium should roughly equal the expected loss rate. If a borrower has a 3% chance of default and the loss if default occurs is 50%, then the expected loss is 1.5% of notional.

## Worked Example: Fair Spread Approximation

Suppose a one-year CDS has:

- Probability of default: 3%
- Recovery rate: 50%
- Loss given default: $1 - 0.50 = 0.50$, or 50%

Then:

$$
\text{CDS spread} \approx 0.03 \times 0.50 = 0.015
$$

So the fair CDS spread is approximately:

$$
1.5\% = 150 \text{ bps}
$$

The protection seller needs about 150 bps per year to be compensated for the expected loss.

## Hazard Rate and Survival Probability

In multi-period CDS valuation, CFA often uses the **hazard rate**, which is the conditional probability of default in a period, given that the borrower has survived to the start of that period.

If the annual hazard rate is constant, survival through $t$ years is:

$$
\text{Survival Probability}_t = (1 - h)^t
$$

where $h$ is the hazard rate.

Cumulative probability of default through time $t$ is:

$$
\text{POD}_t = 1 - \text{Survival Probability}_t
$$

For a specific year, the probability of default in that year is:

$$
\text{POD in year } t = \text{Survival Probability}_{t-1} \times h_t
$$

This is the mechanism behind the full CDS valuation model:

- Use survival probabilities to weight expected premium payments.
- Use period-by-period default probabilities to weight expected protection payments.
- Discount all expected cash flows.
- Set the two present values equal to solve for the fair spread.

## Why the Formula Works

The premium leg is like a stream of insurance premiums:

$$
\text{PV(Premium Leg)} =
\sum_t \text{CDS coupon} \times \text{Notional} \times \text{Survival Probability}_t \times \text{Discount Factor}_t
$$

The protection leg is like the expected claim:

$$
\text{PV(Protection Leg)} =
\sum_t \text{Default Probability}_t \times \text{LGD} \times \text{Notional} \times \text{Discount Factor}_t
$$

The fair spread is the coupon rate that makes:

$$
\sum_t s \times \text{Notional} \times \text{Survival Probability}_t \times DF_t
=
\sum_t q_t \times \text{LGD} \times \text{Notional} \times DF_t
$$

where:

- $s$ = fair CDS spread
- $q_t$ = default probability in period $t$
- $DF_t$ = discount factor for period $t$

The notional appears on both sides. That is why spreads are quoted in basis points of notional.

## Standard Coupons and Upfront Payments

In the real CDS market, contracts often trade with standardized fixed coupons rather than a coupon that exactly equals the current market spread.

Common standard coupons:

| Reference credit type | Standard CDS coupon |
|---|---:|
| Investment grade | 1% |
| High yield | 5% |

If the fixed coupon does not equal the market-implied CDS spread, the contract needs an **upfront payment** to make the economics fair.

The approximation is:

$$
\text{Upfront Premium \%} \approx
(\text{Market CDS Spread} - \text{Fixed CDS Coupon}) \times \text{CDS Duration}
$$

Use **CDS duration**, not the duration of the reference bond.

### Upfront Payment Direction

| Market condition | Meaning | Who pays upfront? |
|---|---|---|
| Market spread > fixed coupon | The buyer's future coupon is too low for the credit risk | Protection buyer pays seller |
| Market spread < fixed coupon | The buyer's future coupon is too high for the credit risk | Protection seller pays buyer |

The intuition is simple: if the ongoing coupon is too small, the buyer must compensate the seller upfront. If the ongoing coupon is too large, the seller must compensate the buyer upfront.

CDS price can be quoted as:

$$
\text{CDS Price} = 100 - \text{Upfront Premium \%}
$$

If the upfront premium is negative, the price is above 100.

## Worked Example: Upfront Premium

Suppose:

- Notional: USD 10,000,000
- Market CDS spread: 3.5%
- Fixed CDS coupon: 5.0%
- CDS duration: 7

Then:

$$
\text{Upfront Premium \%} \approx (0.035 - 0.050) \times 7
$$

$$
= -0.015 \times 7 = -0.105
$$

So the upfront premium is:

$$
-10.5\%
$$

In dollars:

$$
-10.5\% \times 10{,}000{,}000 = -1{,}050{,}000
$$

The negative sign means the protection seller pays the protection buyer USD 1,050,000. Why? Because the buyer is agreeing to pay a 5% coupon when the market only requires 3.5%; the buyer is overpaying through time and needs to be compensated upfront.

The CDS price is:

$$
100 - (-10.5) = 110.5
$$

## Mark-to-Market After Inception

After a CDS is entered, its value changes when the market's required CDS spread changes.

For the protection buyer:

```text
Credit quality worsens
  -> CDS spread widens
  -> protection becomes more valuable
  -> buyer gains, seller loses
```

For the protection seller:

```text
Credit quality improves
  -> CDS spread narrows
  -> protection sold becomes less costly
  -> seller gains, buyer loses
```

A common approximation for the protection buyer's gain is:

$$
\text{Gain to Protection Buyer}
\approx
\Delta \text{CDS Spread} \times \text{CDS Duration} \times \text{Notional}
$$

The sign flips for the protection seller.

## Worked Example: Spread Widening

An investor buys CDS protection on USD 10,000,000 notional.

- Original CDS spread: 200 bps
- New CDS spread: 350 bps
- CDS duration: 5

The spread change is:

$$
350 - 200 = 150 \text{ bps} = 0.015
$$

The buyer's approximate gain is:

$$
0.015 \times 5 \times 10{,}000{,}000 = 750{,}000
$$

The protection buyer gains about USD 750,000. The protection seller loses about USD 750,000.

## Factors Affecting CDS Pricing

| Factor | If it increases | Effect on CDS spread | Why |
|---|---:|---:|---|
| Probability of default | Up | Up | The expected protection payment is more likely |
| Hazard rate | Up | Up | Conditional default risk is higher in each period |
| Loss given default | Up | Up | The seller's expected payment after default is larger |
| Recovery rate | Up | Down | Higher recovery means lower LGD |
| Credit risk premium | Up | Up | Investors require more compensation for bearing credit risk |
| CDS duration | Up | More value sensitivity | A given spread change has a larger PV effect |
| Fixed coupon | Up relative to market spread | Upfront paid by seller to buyer | Buyer is paying too much through time |
| Market spread | Up relative to fixed coupon | Upfront paid by buyer to seller | Buyer is paying too little through time |
| Liquidity risk | Up | Usually up | Less liquid protection requires compensation |
| Reference obligation quality | Down | Up | Weaker credit means higher expected loss |
| Maturity | Longer | Usually up, but curve-dependent | More time for default risk to emerge |

The clean CFA drivers are **POD**, **LGD**, and the **coupon/upfront structure**. Market CDS prices can also reflect liquidity, supply and demand for protection, counterparty risk, deliverable obligation options, and the shape of the credit curve.

## Protection Buyer vs Protection Seller

| Scenario | Protection buyer | Protection seller |
|---|---:|---:|
| Reference credit worsens | Gains | Loses |
| CDS spread widens | Gains | Loses |
| Reference credit improves | Loses | Gains |
| CDS spread narrows | Loses | Gains |
| Buyer of protection position | Short credit risk | N/A |
| Seller of protection position | N/A | Long credit risk |

Buying CDS protection is economically similar to shorting the reference entity's credit. Selling protection is economically similar to being long the reference entity's credit.

## Exam Traps

1. **CDS spread is not always the fixed coupon.** The market spread is the fair required premium. The fixed coupon may be standardized at 1% or 5%, with the difference handled through an upfront payment.

2. **Use CDS duration, not bond duration.** The upfront approximation uses the duration of the CDS cash flows, not the duration of the reference bond.

3. **Recovery rate and LGD move in opposite directions.** Higher recovery means lower loss given default, so the fair CDS spread decreases.

4. **Premium payments stop after default.** Default risk affects the premium leg because the buyer only keeps paying while the reference entity survives.

5. **Spread widening helps the protection buyer.** The buyer owns insurance. If the insured risk becomes more dangerous, that insurance becomes more valuable.

6. **Upfront direction depends on market spread versus fixed coupon.** If the market spread is above the fixed coupon, the buyer pays upfront. If the market spread is below the fixed coupon, the seller pays upfront.

7. **A negative upfront premium means a price above 100.** Since price equals $100 - \text{upfront premium \%}$, subtracting a negative upfront premium increases the price.

## Memory Hooks

- **Premium leg = insurance premiums. Protection leg = expected claim.**
- **Spread up: buyer happy, seller sad.**
- **Recovery up -> LGD down -> CDS spread down.**
- **Market spread above coupon -> buyer owes upfront. Market spread below coupon -> seller owes upfront.**

## Can You Now?

- Explain why a CDS has a premium leg and a protection leg.
- Derive the intuition for $\text{CDS spread} \approx \text{POD} \times \text{LGD}$.
- Calculate LGD from a recovery rate.
- Explain why hazard rates and survival probabilities matter.
- Determine who pays the upfront premium when the market spread differs from the fixed coupon.
- Compute an approximate upfront payment using CDS duration.
- State who gains when CDS spreads widen or narrow.

## Related Concepts

- [[Credit Default Swap]]
- [[CDS Curve and Basis Trades]]
- [[Loss Given Default]]
- [[Probability of Default]]
- [[Hazard Rate]]
- [[Recovery Rate]]
- [[Credit Spread]]
- [[Credit Risk]]
- [[Fixed-Income Valuation]]
