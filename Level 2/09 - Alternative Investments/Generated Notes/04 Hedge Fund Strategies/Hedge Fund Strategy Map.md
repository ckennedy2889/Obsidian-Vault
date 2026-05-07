---
title: "Hedge Fund Strategy Map"
subject: "Alternative Investments"
tags: [CFA-L2, alternative-investments, hedge-funds, strategies]
aliases:
  - Hedge fund strategies
  - Equity hedge
  - Event-driven strategies
  - Relative value strategies
  - Global macro
  - Managed futures
---

# Hedge Fund Strategy Map

Hedge funds are private pooled vehicles with flexible mandates. They can short securities, use derivatives, use leverage, and invest in less liquid opportunities. For CFA Level II, the point is not just naming strategies. The point is identifying each strategy's **return driver**, **risk exposure**, **liquidity profile**, and **tail risk**.

## Strategy Families

| Family | Main return driver | Typical risk profile |
|---|---|---|
| Equity hedge | Security selection in equities | Equity beta varies by subtype |
| Event-driven | Corporate events and deal outcomes | Left-tail event risk |
| Relative value | Mispricing between related securities | Leverage and convergence risk |
| Opportunistic | Macro themes or trends | Model, policy, and trend-reversal risk |
| Multi-manager | Allocation across managers or strategies | Fee, netting, and operational risk |

## Equity Hedge Strategies

### Long/short equity

Managers buy undervalued stocks and short overvalued stocks.

Typical profile:

- Net long exposure.
- Positive correlation with equity markets.
- Lower volatility than long-only equity if shorts hedge part of market exposure.
- Returns depend on stock selection and net exposure.

### Dedicated short bias

Managers maintain net short exposure to equities.

Use case:

- Can diversify a portfolio during equity bear markets.
- Returns are often difficult in long bull markets.
- Shorting creates theoretically unlimited loss potential.

### Equity market neutral

Equity market neutral strategies balance long and short positions to target beta near zero.

The manager tries to earn alpha from relative mispricing, not broad market direction.

Because expected spreads are small, these strategies often use leverage.

Common subtypes:

- Statistical arbitrage.
- Pairs trading.
- Factor-neutral stock selection.

## Event-Driven Strategies

Event-driven funds invest around corporate events such as mergers, bankruptcies, restructurings, spin-offs, and recapitalizations.

### Merger arbitrage

In a cash merger, the manager usually buys the target company's stock below the deal price.

In a stock-for-stock merger, the manager typically:

1. Buys the target.
2. Shorts the acquirer.
3. Uses the exchange ratio to size the hedge.

The spread is compensation for deal risk.

Payoff intuition:

$$
\text{Merger arb payoff} \approx \text{risk-free bond} + \text{short put option}
$$

If the deal closes, the manager earns a relatively steady spread. If the deal breaks, the target price can fall sharply. That creates negative skewness and left-tail risk.

### Distressed securities

Distressed managers buy debt or equity of companies in or near bankruptcy.

They may buy debt at a deep discount and participate actively in restructuring. A security that is expected to convert into control of the reorganized company is often called the fulcrum security.

Typical profile:

- Illiquid.
- Long-biased credit exposure.
- Lower leverage than many arbitrage strategies.
- Often performs best in early economic recoveries after distressed prices have fallen.

## Relative Value Strategies

Relative value strategies exploit pricing discrepancies between related instruments.

### Convertible arbitrage

A convertible bond combines:

- Straight bond value.
- Embedded equity call option.

The classic trade:

1. Buy the convertible bond.
2. Short the underlying stock to hedge equity exposure.

The strategy is typically long volatility because the embedded option benefits from realized volatility. It can suffer from credit spread widening, short squeezes, financing stress, and time decay when the stock is stagnant.

### Fixed-income arbitrage

Fixed-income arbitrage exploits small pricing differences in yield curves, spreads, or liquidity.

Example:

- Buy off-the-run Treasuries.
- Short on-the-run Treasuries.

Because mispricings are small, the strategy often uses high leverage. The main danger is forced deleveraging when spreads widen before converging.

## Opportunistic Strategies

### Global macro

Global macro managers make top-down bets on:

- Interest rates.
- Currencies.
- Equity indexes.
- Commodities.
- Sovereign credit.

They may be discretionary or systematic and often use derivatives for leverage and convexity.

### Managed futures and CTAs

Managed futures funds, or CTAs, trade liquid futures markets using systematic rules.

Many rely on time-series momentum:

- Go long assets trending upward.
- Go short assets trending downward.

CTAs can perform well during prolonged market stress if trends are strong. They often provide crisis diversification and may exhibit positive right-tail skewness.

## Multi-Manager Structures

### Fund of funds

A fund of funds invests in multiple external hedge funds.

Benefits:

- Diversification.
- Manager access.
- Due diligence resources.

Costs:

- Double layer of fees.
- Fee netting risk.
- Less direct control over underlying positions.

Fee netting risk means winning underlying funds can earn incentive fees even if the overall fund-of-funds portfolio has weak or negative performance.

### Multi-strategy funds

A multi-strategy fund allocates capital across strategies inside one fund platform.

Compared with fund of funds:

- Capital can be reallocated more quickly.
- The investor usually pays incentive fees on net overall performance.
- The general partner absorbs more netting risk.
- Operational risk is more concentrated in one organization.

## Fees and Liquidity Terms

Hedge funds often charge:

- Management fee on AUM or NAV.
- Incentive fee on profits.
- High-water mark.
- Hurdle rate.

### Hard vs soft hurdle

With a hard hurdle, the manager earns incentive fees only on returns above the hurdle.

With a soft hurdle, once the hurdle is met, the manager may earn incentive fees on the full return, often with a catch-up provision.

### Liquidity terms

Common terms:

- Lock-up period.
- Notice period.
- Redemption frequency.
- Gates.
- Side pockets.

These terms protect the manager from forced liquidation but reduce investor liquidity.

## Risk Exposures

Hedge fund risk can be nonlinear and state-dependent. A strategy may look market-neutral in normal periods but become highly correlated with risky assets during crises.

Risks to watch:

- Leverage.
- Liquidity.
- Short squeeze.
- Counterparty risk.
- Model risk.
- Financing risk.
- Crowded-trade risk.
- Left-tail event risk.

Conditional factor models can reveal crisis-period exposures that ordinary average betas hide.

## Exam Traps

- **Merger arbitrage has left-tail risk.** It earns small spreads until a deal breaks.
- **Convertible arbitrage is usually long volatility.** The manager owns the convertible option and shorts stock.
- **Fixed-income arbitrage can be very highly levered.** Small spread trades can create large losses when convergence fails.
- **Equity market neutral targets beta near zero, not zero risk.**
- **Managed futures are trend-following, not mean-reversion by default.**
- **Fund of funds has double fees and fee netting risk.**
- **Hedge fund management fees are usually based on AUM/NAV, unlike private equity committed-capital fee structures.**
- **Liquidity gates protect the fund but restrict investors.**

## Memory Hook

**Equity hedge picks stocks. Event-driven bets on events. Relative value waits for convergence. Macro and CTAs ride big moves. Multi-manager changes who bears fee and allocation risk.**
