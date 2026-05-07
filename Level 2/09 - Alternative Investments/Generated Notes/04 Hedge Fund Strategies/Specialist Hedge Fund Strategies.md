---
title: "Specialist Hedge Fund Strategies"
subject: "Alternative Investments"
tags: [CFA-L2, alternative-investments, hedge-funds, volatility, reinsurance]
aliases:
  - Specialist hedge fund strategies
  - Volatility trading
  - Reinsurance hedge funds
  - Life settlements
  - Catastrophe risk
---

# Specialist Hedge Fund Strategies

Specialist hedge fund strategies are niche strategies where the edge comes from specialized market knowledge, specialized instruments, or unusual risks. In the CFA Level II hedge fund reading, the two main examples are **volatility trading** and **reinsurance/life settlements**.

The clean way to separate them:

- Volatility trading is about buying or selling market insurance.
- Reinsurance and life settlements are about underwriting non-market risks such as weather and mortality.

## Volatility Trading

Volatility trading treats [[volatility]] as the thing being bought or sold, not merely as a side effect of stock, bond, currency, or commodity prices.

The manager's goal is:

$$
\text{Buy underpriced volatility and sell overpriced volatility}
$$

This requires comparing [[implied volatility]] embedded in market prices with the manager's estimate of future realized volatility.

## Long vs Short Volatility

| Position | What the manager does | Return pattern | Portfolio role |
|---|---|---|---|
| Long volatility | Buys options or volatility exposure | Loses small premiums in calm markets; gains sharply in stress | Crisis hedge |
| Short volatility | Sells options or volatility exposure | Earns steady premiums in calm markets; loses sharply in volatility spikes | Income-like, but left-tail risk |

### Long volatility

A long-volatility manager pays a premium to own convex payoff exposure.

The mechanism:

1. Equity markets fall sharply.
2. Uncertainty rises.
3. Implied and realized volatility increase.
4. Long volatility positions rise in value.

Because equity volatility is strongly negatively correlated with equity market returns, long volatility can diversify a long-equity portfolio. The cost is time decay: if markets are calm, the premiums paid can steadily reduce returns.

### Short volatility

A short-volatility manager sells insurance to the market. The manager receives option premiums and benefits if realized volatility is lower than implied volatility.

The danger is asymmetric:

- Many small gains in calm markets.
- Potentially severe losses when volatility spikes.

This resembles other short-option or insurance-like strategies. It may show attractive Sharpe ratios in normal periods while hiding left-tail risk.

## Instruments

| Instrument | Use | Key issue |
|---|---|---|
| Listed options | Common way to buy or sell volatility | Requires delta hedging to isolate volatility |
| VIX futures | Direct exposure to expected equity volatility | VIX is mean reverting; futures curve matters |
| VIX options | Option exposure on volatility index | Liquid for shorter tenors |
| Volatility swaps | OTC exposure to realized volatility | Less liquid; counterparty risk |
| Variance swaps | OTC exposure to realized variance | Payoff based on squared volatility |

### Options vs volatility swaps

Standard options combine several exposures:

- Directional exposure.
- Volatility exposure.
- Time decay.
- Interest rate and dividend effects.

To isolate volatility, the manager may need to delta hedge.

Volatility and variance swaps provide more direct exposure to realized volatility or variance. The name "swap" can be misleading; the payoff behaves more like a forward contract on realized volatility or variance.

## Convexity

Long volatility has positive convexity. Losses are generally limited to premium paid, while gains can be large when markets move sharply.

Short volatility has the opposite profile: steady premium income with exposure to large losses.

For exam purposes:

| Market state | Long volatility | Short volatility |
|---|---|---|
| Calm, sideways market | Usually loses premium/time decay | Usually earns premium |
| Sharp selloff or crisis | Can gain substantially | Can lose substantially |
| Volatility mean reverts lower | Often loses | Often gains |

## Reinsurance and Life Settlements

Reinsurance and life-settlement strategies invest in risks that are not primarily driven by financial market returns.

The return drivers are:

- Mortality.
- Longevity.
- Hurricanes.
- Earthquakes.
- Floods.
- Other insured events.

Because these risks are tied to weather and actuarial outcomes, they can have low correlation with traditional stocks and bonds.

## Life Settlements

In a life settlement, a fund buys an existing life insurance policy from the policyholder.

The policyholder receives cash now. The fund:

1. Pays the purchase price.
2. Takes over future premium payments.
3. Receives the death benefit when the insured person dies.

The fund's return improves when:

- Purchase price is low.
- Ongoing premiums are low.
- The death benefit is high.
- The insured dies sooner than standard actuarial assumptions imply.

Exam trap: the fund does **not** want the insured to live longer than expected. Longer life means more premium payments and delayed death benefit collection, which reduces return.

## Catastrophe Reinsurance

Catastrophe reinsurance transfers disaster risk from insurers to reinsurers or capital market investors.

Examples:

- Hurricane risk.
- Earthquake risk.
- Flood risk.
- Tornado risk.

The hedge fund earns premiums if catastrophic losses are lower than expected. It loses when covered events occur and claims must be paid.

Key underwriting questions:

- Are premiums adequate for the modeled risk?
- Are risks diversified by geography?
- Are risks diversified by event type?
- Are worst-case losses survivable?
- Are loss reserves sufficient?

## Liquidity, Capacity, and Leverage

| Strategy | Liquidity | Capacity | Leverage |
|---|---|---|---|
| Listed volatility instruments | Often high for short tenors | Higher | Easy through futures/options |
| OTC volatility/variance swaps | Lower | Limited by counterparties | Embedded through derivatives |
| Life settlements | Low | Limited | Usually less liquid financing |
| Catastrophe risk | Low to moderate | Depends on market and season | Often structured through securities or reinsurance contracts |

Specialist strategies can be hard to benchmark because the exposures are niche and payoff profiles are nonlinear.

## Portfolio Role

| Strategy | Diversification source |
|---|---|
| Long volatility | Negative correlation with equity markets during stress |
| Short volatility | Premium income, but poor crisis diversification |
| Life settlements | Mortality risk independent of financial markets |
| Catastrophe reinsurance | Weather/event risk independent of normal market cycles |

The important distinction: long volatility diversifies because it tends to pay off when markets crash. Reinsurance diversifies because its underlying risk is not market risk in the first place.

## Exam Traps

- **Long volatility is the crisis hedge.** Short volatility sells the hedge and can lose badly in crises.
- **Variance is volatility squared.** A variance swap is not the same as a volatility swap.
- **Options are not pure volatility exposure unless hedged.** Volatility and variance swaps provide cleaner exposure.
- **VIX futures are direct volatility instruments, but VIX is mean reverting.**
- **Life-settlement investors prefer earlier-than-expected mortality.** Longer life lowers returns.
- **Reinsurance needs diversification.** A single concentrated catastrophe exposure can wipe out premiums.
- **Low correlation does not mean low risk.** Catastrophe and mortality risks can be severe and illiquid.

## Memory Hook

**Volatility funds trade fear. Reinsurance funds underwrite fate.**

Long fear protects a portfolio. Selling fear earns premiums until fear arrives.
