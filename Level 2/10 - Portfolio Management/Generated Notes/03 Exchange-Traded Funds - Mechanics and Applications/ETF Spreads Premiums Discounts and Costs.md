---
title: ETF Spreads Premiums Discounts and Costs
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, ETFs, bid-ask-spread, premium-discount, ETF-costs]
aliases: [ETF Bid-Ask Spreads, ETF Premiums and Discounts, ETF Cost of Ownership, ETF Round-Trip Trading Cost]
---

# ETF Spreads Premiums Discounts and Costs

## Intuition

An ETF can look cheap because it has a low management fee, but still be expensive to trade.

The total investor cost depends on:

- the bid-ask spread,
- commissions,
- market impact,
- premium or discount to NAV,
- management fees,
- and how long the investor holds the ETF.

Short-term traders care most about trading costs. Long-term investors care more about management fees.

See: [[ETF Mechanics and Applications]]

## Bid-Ask Spreads

An ETF bid-ask spread compensates market makers for the cost and risk of providing liquidity.

Spreads are affected by:

| Factor | Effect on spread |
|---|---|
| Liquidity of underlying securities | More liquid underlying securities narrow spreads |
| ETF trading volume | Higher volume usually narrows spreads |
| Market maker competition | More competition narrows spreads |
| Volatility | Higher volatility widens spreads |
| Creation/redemption fees | Higher fees widen spreads |
| Time-zone mismatch | Wider when ETF and underlying markets do not overlap |
| Probability of offsetting trade | Higher probability narrows spreads |

Fixed-income ETFs often have wider spreads than large-cap equity ETFs because the underlying bonds trade OTC and can be less liquid.

## Maximum Spread Components

The maximum quoted spread can be thought of as:

$$
\begin{aligned}
\text{Maximum spread}
=&\ \text{creation/redemption fees and trading costs}\\
&+ \text{spread of underlying securities}\\
&+ \text{risk premium for carrying/hedging inventory}\\
&+ \text{AP or market maker profit margin}\\
&- \text{discount for probability of secondary-market offset}
\end{aligned}
$$

The minus sign is the trap. If the market maker expects an offsetting customer order soon, inventory risk is lower, so the spread can be narrower.

## Premiums and Discounts

An ETF trades at a premium when:

$$
\text{ETF price} > NAV
$$

It trades at a discount when:

$$
\text{ETF price} < NAV
$$

The percentage premium or discount is:

$$
\text{Premium/discount \%}
= \frac{\text{ETF price} - \text{NAV per share}}{\text{NAV per share}}
$$

Example:

- ETF price = \$23.45
- NAV = \$23.00

$$
\frac{23.45 - 23.00}{23.00}
= \frac{0.45}{23.00}
= 1.96\%
$$

The ETF trades at a 1.96% premium.

## Sources of Premiums and Discounts

| Source | Mechanism |
|---|---|
| Timing differences | ETF trades while underlying market is closed |
| Stale pricing | Last ETF trade or underlying price is not current |
| Illiquid underlying securities | NAV uses estimates rather than live executable prices |
| Bond market pricing | OTC bonds often lack synchronized closing prices |
| Creation/redemption friction | Arbitrage is costly, so price can stay inside an arbitrage band |
| Creation/redemption halt | Arbitrage mechanism weakens or stops |

ETF prices can sometimes be more informative than NAV when the underlying securities are closed, volatile, illiquid, or stale.

## Arbitrage Gap

APs arbitrage only when the premium or discount is large enough to cover costs.

If the ETF trades at a premium:

1. AP buys the underlying basket.
2. AP creates ETF shares.
3. AP sells ETF shares at the premium.

If the ETF trades at a discount:

1. AP buys ETF shares.
2. AP redeems them for underlying securities.
3. AP sells the underlying securities.

But if transaction costs exceed the premium or discount, arbitrage is not profitable.

## Total Cost of ETF Ownership

The simplified exam formula:

$$
\text{Total cost} = \text{round-trip trading cost} + \text{management fees over holding period}
$$

where:

$$
\text{Round-trip trading cost} = \text{round-trip commission} + \text{bid-ask spread}
$$

Management fee must be prorated for the holding period:

$$
\text{Management fee cost} = \text{annual fee}\times\frac{\text{months held}}{12}
$$

## Worked Example: Curriculum-Style ETF Cost

An ETF has:

- Bid-ask spread = 0.15%
- Commission = 0.10% per trade
- Management fee = 0.08% per year

Round-trip commission:

$$
2 \times 0.10\% = 0.20\%
$$

Round-trip trading cost:

$$
0.20\% + 0.15\% = 0.35\%
$$

### Three-month holding period

Management fee:

$$
\frac{3}{12}\times 0.08\% = 0.02\%
$$

Total cost:

$$
0.35\% + 0.02\% = \boxed{0.37\%}
$$

### One-year holding period

$$
0.35\% + 0.08\% = \boxed{0.43\%}
$$

### Five-year holding period

$$
0.35\% + 5(0.08\%) = 0.35\% + 0.40\% = \boxed{0.75\%}
$$

Average annual cost over five years:

$$
\frac{0.75\%}{5} = \boxed{0.15\%}
$$

## Short-Term vs Long-Term Investor

| Investor type | Main cost concern | Why |
|---|---|---|
| Tactical short-term trader | Bid-ask spread, commissions, market impact | Trading costs dominate over short horizons |
| Long-term buy-and-hold investor | Management fee and tracking difference | Recurring costs compound over time |

This is why a short-term trader may choose a highly liquid ETF with a slightly higher management fee, while a long-term investor may prefer the lowest expense ratio.

## ETF Cost Checklist

Include:

- management fee,
- bid-ask spread,
- brokerage commission,
- market impact for large orders,
- premium/discount at purchase and sale,
- tracking difference,
- tax effects,
- creation/redemption costs reflected in spreads.

Do not include creation/redemption fees as a direct cost to ordinary secondary-market investors unless the vignette says they are transacting through the primary market. These fees are usually reflected indirectly through spreads.

## Bond ETF Premium Trap

A bond ETF trading at a premium does not automatically mean it is overvalued.

Reasons:

- underlying bonds trade OTC,
- NAV may be based on evaluated prices,
- bond quotes can be stale,
- dealer bid prices may understate executable value,
- ETF market price may incorporate fresher information than NAV.

The exam phrase "price above iNAV" means premium, not necessarily overvaluation.

## Exam Traps

| Trap | Correct response |
|---|---|
| Say high offset probability widens ETF spreads | It narrows spreads because inventory risk is lower |
| Treat price above NAV as automatically overvalued | It is a premium; may reflect stale NAV or timing differences |
| Forget to double the commission for round-trip cost | Buy and sell commissions both count |
| Annualize trading costs incorrectly | Trading cost is paid once per round trip; management fee accrues with time |
| Use management fee as the main cost for a one-week tactical trade | Short-horizon investors focus on spread and commissions |
| Use trading spread as the main cost for a long-term holding | Long-horizon investors focus more on recurring management fees |
| Treat creation/redemption fees as direct ordinary-investor costs | They are AP costs, usually reflected in ETF spreads |

## Memory Hook

> **ETF cost = cross the spread, pay the ticket, carry the fee.**

And:

> **Premium means price above NAV, not necessarily overvalued.**

## Exam-Day Checklist

1. Identify whether the question is about spread, premium/discount, or holding-period cost.
2. For spreads, list additive cost/risk components and subtract offset probability.
3. For premium/discount, use $(P - NAV)/NAV$.
4. For cost, compute round-trip commission first.
5. Add the bid-ask spread once for round-trip trading cost.
6. Prorate management fee by holding period.
7. Match investor horizon to the dominant cost.

## Related Concepts

- [[ETF Mechanics and Applications]]
- [[Parametric Historical and Monte Carlo VaR]]
- [[Risk Limits and Capital Allocation]]
