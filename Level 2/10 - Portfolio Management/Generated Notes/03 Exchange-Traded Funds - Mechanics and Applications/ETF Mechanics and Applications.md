---
title: "ETF Mechanics and Applications"
subject: "Portfolio Management"
tags: [CFA-L2, portfolio-management, ETFs, trading, tracking-error]
aliases:
  - ETF creation redemption
  - Authorized participants
  - ETF premiums and discounts
  - ETF tracking error
  - Exchange-traded funds
---

# ETF Mechanics and Applications

An [[exchange-traded fund]] is a fund that holds a portfolio of securities but trades intraday on an exchange like a stock. The distinctive feature is the two-layer market structure: ordinary investors trade ETF shares with each other, while authorized participants can create or redeem large blocks of ETF shares directly with the fund.

That creation/redemption mechanism is what usually keeps an ETF's market price close to its [[net asset value]].

## Primary vs Secondary Market

| Market | Participants | What trades? |
|---|---|---|
| Secondary market | Investors, brokers, market makers | ETF shares on an exchange |
| Primary market | ETF sponsor and authorized participants | Creation/redemption baskets and ETF creation units |

Most investors trade only in the secondary market. Authorized participants operate in the primary market.

## Authorized Participants

[[Authorized participants]] are usually large broker-dealers or market makers that have an agreement with the ETF sponsor.

They can:

- Deliver the underlying securities to create ETF shares.
- Deliver ETF shares to redeem for the underlying securities.
- Arbitrage premiums and discounts.
- Provide liquidity to the ETF ecosystem.

## Creation Process

When ETF demand is strong and ETF shares trade above NAV, an AP can create new shares.

Mechanism:

1. AP buys the underlying creation basket.
2. AP delivers the basket to the ETF sponsor.
3. ETF sponsor gives the AP a creation unit, often a large block such as 50,000 ETF shares.
4. AP sells ETF shares in the secondary market.

This increases ETF share supply and helps push the ETF price down toward NAV.

## Redemption Process

When ETF shares trade below NAV, an AP can redeem shares.

Mechanism:

1. AP buys ETF shares in the secondary market.
2. AP delivers ETF shares to the ETF sponsor.
3. ETF sponsor gives the AP the redemption basket of underlying securities.
4. AP sells the underlying securities.

This reduces ETF share supply and helps push the ETF price up toward NAV.

## Arbitrage and Premiums/Discounts

Premium:

$$
\text{ETF price} > NAV
$$

Discount:

$$
\text{ETF price} < NAV
$$

### Premium arbitrage

If the ETF trades at a premium:

1. Buy underlying securities at NAV-like cost.
2. Create ETF shares.
3. Sell ETF shares at the higher market price.

Selling pressure on ETF shares narrows the premium.

### Discount arbitrage

If the ETF trades at a discount:

1. Buy ETF shares cheaply.
2. Redeem for underlying securities.
3. Sell underlying securities.

Buying pressure on ETF shares narrows the discount.

### Arbitrage gap

Arbitrage is not free. The ETF can trade within a band around NAV because arbitrage costs include:

- Bid-ask spreads.
- Brokerage commissions.
- Market impact.
- Taxes or transfer costs.
- Hedging costs.
- Operational costs.

Only when the premium or discount exceeds the arbitrage cost does AP arbitrage become attractive.

## iNAV and Stale Pricing

Intraday ETF pricing often references indicated NAV, or iNAV. But iNAV can be imperfect when underlying markets are closed or illiquid.

Examples:

- A US-listed ETF holding Asian equities trades while Asian exchanges are closed.
- A bond ETF holds bonds that trade OTC and do not have synchronized closing prices.
- Illiquid holdings rely on evaluated or matrix prices.

Exam trap: an apparent premium or discount does not always mean the ETF arbitrage mechanism is broken. The NAV itself may be stale or estimated.

## Tracking Difference vs Tracking Error

Tracking difference:

$$
\text{ETF return} - \text{Index return}
$$

Tracking error:

$$
\text{Standard deviation of tracking differences}
$$

Tracking difference is about average return shortfall or excess. Tracking error is about consistency of following the index.

Sources of tracking error:

- Expense ratio.
- Sampling instead of full replication.
- Cash drag.
- Dividend reinvestment timing.
- Index reconstitution and rebalancing.
- Securities lending.
- Tax withholding.
- Trading costs.
- Illiquid underlying securities.

## Bid-Ask Spreads

ETF investors pay the bid-ask spread when trading in the secondary market.

ETF spreads are affected by:

| Factor | Effect |
|---|---|
| ETF trading volume | Higher volume usually narrows spreads |
| Liquidity of underlying securities | More liquid baskets narrow spreads |
| Market maker competition | More competition narrows spreads |
| Volatility | Higher volatility widens spreads |
| Creation/redemption costs | Higher AP costs widen spreads |
| Time of day and market overlap | Spreads can widen when underlying markets are closed |

## Costs of Owning an ETF

Total cost includes:

- Expense ratio.
- Bid-ask spread.
- Brokerage commissions, if any.
- Premium or discount at purchase/sale.
- Tracking difference.
- Taxes.

ETFs are often tax efficient because in-kind creation/redemption can avoid forcing the fund to sell appreciated securities to meet redemptions.

## ETF Risks

| Risk | Explanation |
|---|---|
| Tracking risk | ETF may not match benchmark returns |
| Liquidity risk | ETF or underlying securities may become hard to trade |
| Counterparty risk | Synthetic ETFs, swaps, securities lending, or ETNs introduce counterparty exposure |
| Premium/discount risk | ETF may trade away from NAV |
| Closure risk | Small ETFs can close, forcing taxable sales |
| Complexity risk | Leveraged and inverse ETFs can behave differently over multi-day horizons |

## Portfolio Uses

ETFs can be used for:

- Cash equitization.
- Tactical asset allocation.
- Portfolio completion.
- Rebalancing.
- Manager transitions.
- Sector, country, or factor tilts.
- Liquidity sleeves.
- Tax-loss harvesting.
- Hedging or short exposure, if ETF shares can be borrowed.

### Cash equitization

If a manager receives cash but has not yet selected individual securities, the manager can buy an ETF to maintain market exposure and reduce cash drag.

### Manager transition

When assets move from one manager to another, an ETF can maintain benchmark exposure during the transition period.

## ETF vs Mutual Fund Mechanics

| Feature | ETF | Traditional mutual fund |
|---|---|---|
| Trading | Intraday on exchange | End-of-day NAV |
| Creation/redemption | In kind through APs | Usually cash subscriptions/redemptions |
| Tax efficiency | Often higher | Redemptions can trigger fund-level sales |
| Trading costs | Bid-ask spread and commissions | Fund transaction costs and possible fees |
| Price vs NAV | Can trade at premium/discount | Transacts at NAV |

## Exam Traps

- **APs, not ordinary investors, create and redeem ETF shares.**
- **Premium arbitrage creates ETF shares.** Discount arbitrage redeems ETF shares.
- **Tracking difference is not tracking error.** Difference is return gap; error is volatility of the gap.
- **Bond ETF premiums/discounts can reflect stale NAV estimates.** Do not assume arbitrage failed.
- **ETF tax efficiency comes from in-kind creation/redemption.**
- **Bid-ask spread depends on underlying liquidity, not just ETF volume.**
- **Leveraged and inverse ETFs reset daily.** Long-horizon returns can differ from the simple multiple of index returns.

## Memory Hook

**ETF price stays near NAV because APs can swap baskets for shares and shares for baskets.**
