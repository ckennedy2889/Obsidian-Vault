---
title: ETF Risks and Portfolio Applications
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, ETFs, risk-management]
aliases: [ETF risks, ETF portfolio uses, ETF applications, exchange-traded fund risks]
---

# ETF Risks and Portfolio Applications

## The Real-World Analogy

Think of an [[Exchange-Traded Fund|ETF]] as a delivery truck for portfolio exposure. If the truck is simple, liquid, and carries plain index securities, the delivery is usually boring: the investor gets broad exposure with low cost and intraday tradability. But some trucks carry cargo through extra parties, derivatives, borrowed securities, or daily reset leverage. The exposure can still arrive, but now the investor also cares about the driver, the route, the collateral, the timing, and whether the truck is actually designed for a one-day trip rather than a long-distance move.

That is the exam intuition. CFA does not test ETFs only as cheap index funds. It tests whether you can identify the hidden risk in the ETF structure and match the ETF to the correct portfolio job.

## The Big Idea

ETF risk comes from the difference between the exposure the investor wants and the mechanism used to deliver that exposure.

```text
Desired exposure
  |
  v
ETF structure used to deliver it
  |
  v
Added risks from counterparties, derivatives, lending, closure, liquidity, or compounding
```

A plain physical equity ETF may mostly create [[Tracking Error|tracking error]], trading-cost, and premium/discount risk. A synthetic ETF, [[Exchange-Traded Note|ETN]], leveraged ETF, inverse ETF, or securities-lending-heavy ETF adds more moving parts. More moving parts can be useful, but they create more ways for investor expectations to differ from realized outcomes.

## Why CFA Tests This

The ETF reading is practical. On the exam, the word "ETF" is rarely enough. You must ask:

1. What risk is most important for this ETF structure?
2. Is the investor using the ETF for a short-term implementation job or a long-term strategic allocation?
3. Does the ETF's quoted liquidity, cost, or factor label actually solve the client's problem?

The common trap is to memorize that ETFs are low-cost and liquid. That is often true, but not always the relevant answer. An ETN can have high [[Counterparty risk|counterparty risk]]. A leveraged inverse ETF can have high expectation-related risk. An ETF chosen for short-term tactical trading should be judged mainly on trading costs and liquidity, not the lowest management fee.

## ETF Risk Map

| Risk type | Where it usually appears | Mechanism | Exam implication |
|---|---|---|---|
| [[Counterparty risk]] | ETNs, synthetic ETFs, swap-based structures, securities lending | Investor depends on another party performing | Highest concern for ETNs because they are unsecured issuer obligations |
| Settlement risk | OTC derivative use | Derivative cash flows may not settle as expected | Mitigated by collateral and frequent settlement |
| Securities-lending risk | Physical ETFs that lend holdings | Borrower default risk remains with ETF investors | Lending fees can offset expenses, but risk is not zero |
| Closure risk | Small, unprofitable, unpopular, or strategy-changing ETFs | Fund liquidates holdings and distributes cash | Investor may face unwanted tax and reinvestment consequences |
| Creation/redemption halt risk | Especially ETNs | New shares cannot be created, so arbitrage mechanism weakens | ETN may trade at a large premium to indicative value/NAV |
| Expectation-related risk | Leveraged, inverse, complex, derivative-based ETFs | Investor expects simple long-run multiple, but daily reset compounding changes results | Leveraged/inverse ETFs are usually short-horizon tools, not buy-and-hold holdings |
| Liquidity and spread risk | ETFs with illiquid underlying securities or fragmented trading | Wide bid-ask spread and costly execution | For short-term trading, liquidity and spread dominate expense ratio |
| Premium/discount risk | Bond, foreign-market, commodity, or creation-halted ETFs | ETF price can differ from NAV estimate | Do not automatically assume arbitrage failure; NAV may be stale |

## Counterparty Risk and ETNs

An [[Exchange-Traded Note|ETN]] looks like an ETF because it trades on an exchange and promises the return of an index minus fees. Mechanically, however, an ETN is usually an unsecured debt obligation of an issuer, often a bank.

That difference matters because the investor is no longer only asking, "Will the index perform?" The investor is also asking, "Will the issuer pay?"

```text
ETF investor buys ETN
  |
  v
Issuer owes index return minus fees
  |
  v
Investor has issuer credit exposure
```

If the issuer defaults, the investor may not receive the promised index return even if the index performed well. That is why ETNs are commonly associated with high [[Counterparty risk|counterparty risk]].

### Why an issuer might create an ETN

Suppose a bank wants to borrow, but normal unsecured debt would require a high fixed coupon. Instead, the bank issues an ETN linked to an equity index and hedges by entering into an equity swap. If the bank can fund synthetically at a better effective rate, the ETN structure may be attractive to the bank.

For the ETF investor, that funding logic is not the key exam point. The exam point is that the investor has credit exposure to the bank. A larger [[Credit Default Swap|CDS spread]] on the issuer signals more counterparty credit risk.

## Settlement Risk and Securities Lending

Some ETFs use [[OTC Derivatives|OTC derivatives]] to create the intended exposure. That introduces settlement risk: the derivative counterparty might fail to settle promised payments.

ETF sponsors can reduce, but not eliminate, this risk by:

- settling frequently, such as daily or weekly;
- requiring collateral;
- monitoring the counterparty's credit quality;
- diversifying counterparties when possible.

Securities lending creates a related but distinct risk. An ETF may lend portfolio securities to short sellers and receive a lending fee. The lending arrangement is often overcollateralized, and the collateral is usually invested in short-term, low-risk instruments. The lending revenue can offset fund expenses and improve investor returns.

The failure mode is borrower default. If the borrower defaults and collateral is insufficient or impaired, ETF investors bear the loss. CFA often presents this as a small but real risk: securities lending can be beneficial, but it is not free money.

## Fund Closures and Creation/Redemption Halts

ETF closure risk is similar to [[Mutual Fund|mutual fund]] closure risk. If an ETF is too small, no longer profitable for the sponsor, affected by regulation, merged into another sponsor's lineup, or tied to a strategy the sponsor wants to abandon, the fund can close.

The mechanism is usually:

```text
ETF closes
  |
  v
Underlying holdings are sold or distributed according to fund terms
  |
  v
Investor receives cash and must reinvest
  |
  v
Possible tax realization, transaction cost, and exposure gap
```

A soft closure can involve a halt to creations or a strategy change rather than immediate liquidation. Creation/redemption halts are especially important for ETNs. If the issuer stops creating new ETN shares, the arbitrage mechanism cannot easily increase supply when market price rises above indicative value. The result can be a large premium.

The exam trap is directionality:

| Situation | Arbitrage mechanism | Likely pricing effect |
|---|---|---|
| Creation works normally and ETF trades above NAV | APs create shares and sell them | Premium is pressured down |
| Redemption works normally and ETF trades below NAV | APs buy shares and redeem | Discount is pressured up |
| Creation is halted while investor demand remains high | APs cannot add supply | Premium can persist or widen |

If a vignette says creations are halted and an ETN trades far above indicative value, the issue is not low expense ratio or normal tracking error. The arbitrage channel is impaired.

## Expectation-Related Risk in Leveraged and Inverse ETFs

Expectation-related risk means the product behaves differently from what investors expect. It is most associated with complex ETFs, especially leveraged and inverse ETFs.

A leveraged ETF usually targets a multiple of the index's **daily** return, not a multiple of the index's long-term cumulative return. The word "daily" is the key.

For a 2x ETF:

$$
R_{ETF,day} \approx 2 \times R_{index,day}
$$

That does not imply:

$$
R_{ETF,month} = 2 \times R_{index,month}
$$

The reason is compounding. Each day's leveraged return applies to that day's starting NAV, and the ETF resets its exposure daily.

### Worked example: offsetting index returns do not offset ETF returns

Assume a 2x leveraged ETF starts at NAV = $\$100$.

| Day | Index return | ETF target daily return | ETF NAV calculation | Ending ETF NAV |
|---|---:|---:|---:|---:|
| Start | - | - | - | $\$100.00$ |
| 1 | +5% | +10% | $\$100.00 \times 1.10$ | $\$110.00$ |
| 2 | -5% | -10% | $\$110.00 \times 0.90$ | $\$99.00$ |

The index is not perfectly unchanged after +5% and -5%:

$$
1.05 \times 0.95 - 1 = -0.25\%
$$

But the 2x ETF is down 1.00%:

$$
\frac{99 - 100}{100} = -1.00\%
$$

The investor who expected "two times zero" is wrong because the fund targets daily returns and compounds through a changing NAV base.

### Why volatility makes the problem worse

Volatile paths create more compounding drag for leveraged products. Even if the index ends close to its starting level, the leveraged ETF can lose value because gains and losses are repeatedly applied to a fluctuating base.

```text
Daily reset
  |
  v
Each day targets leverage on new NAV
  |
  v
Volatile path creates compounding effects
  |
  v
Multi-day return differs from simple index multiple
```

Exam implication: leveraged and inverse ETFs are usually tactical, short-term tools. They are not generally suitable for buy-and-hold investors with horizons beyond about one month unless the investor explicitly understands the path dependency.

## Portfolio Applications of ETFs

ETFs are implementation tools. The best ETF depends on the job the portfolio manager needs done.

## Efficient Portfolio Management

### Cash equitization

Cash equitization means using an ETF to turn idle cash into market exposure. If a portfolio receives cash inflows but the manager has not yet selected individual securities, buying an ETF can reduce cash drag.

```text
Cash inflow
  |
  v
Cash would underperform if market rises
  |
  v
Buy ETF temporarily
  |
  v
Maintain benchmark exposure while manager researches securities
```

The exam phrasing often says the manager wants to remain invested, avoid cash drag, or quickly match the benchmark. That points to cash equitization.

### Portfolio rebalancing

ETFs can quickly bring a portfolio back to target asset-class weights. If equities rise and the portfolio is now overweight equities, the manager can sell an equity ETF or buy a bond ETF to rebalance. ETFs can also be shorted to reduce a sector, country, or asset-class exposure quickly.

The mechanism is speed and low implementation friction. Buying or selling one ETF can replace many underlying trades.

### Portfolio completion

Portfolio completion means filling a missing exposure gap.

Example: a client hires an active equity manager who has strong large-cap holdings but little small-cap exposure. If the client's policy benchmark includes small caps, the client can add a small-cap ETF to complete the exposure.

```text
Desired policy exposure
  |
  v
Actual manager portfolio has a gap
  |
  v
ETF fills the missing slice
```

The exam trap is distinguishing completion from tactical allocation. Completion fixes a gap relative to desired strategic exposure. Tactical allocation intentionally tilts away from the normal allocation because of a short-term view.

### Transition management

Transition management uses ETFs to maintain market exposure while assets move from one manager or strategy to another. When the old manager is being terminated and the new manager has not fully built the portfolio, an ETF can provide temporary benchmark exposure.

The problem solved is implementation risk during the transition period: without a temporary exposure tool, the portfolio might sit in cash or carry unintended sector and asset-class bets.

## Asset-Class Exposure Management

ETFs can provide core exposure to broad asset classes, sub-asset classes, sectors, countries, commodities, and fixed income segments. They are especially useful when the underlying securities are hard or expensive to trade directly.

Fixed income is a common example. A bond ETF can be easier to trade than hundreds of individual bonds, especially if the underlying bonds are illiquid. The ETF does not make the underlying bonds liquid, but it can give the investor a more convenient trading vehicle.

### Tactical strategies

Managers can use ETFs to temporarily rotate into sectors, countries, themes, factors, or asset classes they expect to outperform. For a short-term tactical strategy, the manager should emphasize:

- tight bid-ask spreads;
- high trading volume;
- high average dollar volume relative to fund assets;
- depth of the underlying market;
- reliable creation/redemption capacity.

The exam trap is cost priority. For a short-term tactical ETF trade, low trading cost and liquidity matter more than a slightly lower annual management fee. For a long-term buy-and-hold allocation, the management fee becomes more important.

## Active, Smart Beta, and Risk-Management ETFs

ETF applications are not limited to passive cap-weighted index exposure.

| ETF type | What it does | Why an investor might use it | Main due-diligence question |
|---|---|---|---|
| Smart beta / factor ETF | Uses rules to target factors such as size, value, momentum, quality, or low volatility | Seek factor exposure or potential outperformance | Did the rules actually create the intended factor exposure? |
| Multifactor ETF | Combines several factor exposures, sometimes with dynamic weights | Diversify factor bets or adapt to changing opportunities | Are factor definitions, weights, and rebalancing rules sensible? |
| Low-volatility ETF | Builds a portfolio with lower expected volatility than the broad index | Reduce equity risk while staying invested | Is risk reduced because of true defensive exposure or unintended sector concentration? |
| Currency-hedged global equity ETF | Holds foreign equity exposure while hedging currency risk | Separate equity risk from currency risk | What currency exposure is hedged, and at what cost? |
| Duration-hedged high-yield ETF | Keeps credit exposure while hedging interest-rate duration | Target credit spread risk without much rate risk | Does the hedge introduce derivative or basis risk? |
| Alternatively weighted ETF | Uses equal weights, fundamental weights, or other non-cap weights | Avoid pure market-cap weighting or express a rule-based view | What tilts does the weighting method introduce? |
| Discretionary active ETF | Manager or strategy actively selects holdings | Active exposure in an ETF wrapper, common in fixed income | Is the active process transparent enough and suitable for the client? |
| Dynamic asset allocation ETF | Shifts across asset classes based on risk/return forecasts | Outsource top-down allocation | How reliable and transparent are the allocation rules? |

Smart beta is not the same as pure passive indexing. It is rules-based active exposure. The manager may not be making discretionary stock picks every day, but the rule itself is an active choice about which risks should be rewarded.

## When ETFs May Not Be the Best Tool

ETFs are flexible, but they are not automatically optimal. Very large asset owners may prefer [[Separately Managed Account|separately managed accounts]] because SMAs can:

- be customized to the investor's constraints;
- operate at very low cost at large scale;
- avoid the rigid holdings of a public ETF;
- reduce public disclosure issues that may arise with large ETF positions.

The exam implication is that "ETF is low-cost" is not always enough. For a very large, sophisticated investor with customization needs, an SMA may be better.

## Decision Table for Exam Vignettes

| Vignette clue | Best interpretation |
|---|---|
| ETN issuer may default; bank CDS spread is high | Counterparty risk |
| OTC swaps, daily collateral, derivative counterparty | Settlement risk and counterparty control |
| ETF lends securities to short sellers | Securities-lending risk, partly offset by lending revenue |
| Small ETF lacks assets and sponsor plans liquidation | Fund closure risk |
| Creations halted and market price exceeds indicative value | Arbitrage mechanism impaired; premium may persist |
| Leveraged or inverse ETF held for several months | Expectation-related risk and daily reset compounding |
| Cash inflow needs immediate market exposure | Cash equitization |
| Portfolio moved away from policy target weights | Rebalancing |
| Desired exposure missing because active manager underweights a segment | Portfolio completion |
| Old manager terminated, new manager not yet invested | Transition management |
| Short-term sector rotation | Tactical ETF use; prioritize liquidity and trading costs |
| Investor wants value, momentum, quality, or low-volatility exposure | Smart beta/factor ETF |
| Large asset owner wants custom exposure at very low cost | Consider SMA rather than ETF |

## Exam Traps

- **ETN means issuer credit risk.** The investor owns an unsecured promise from the issuer, so [[Counterparty risk|counterparty risk]] is the key risk.
- **Settlement risk is not the same as fund closure risk.** Settlement risk is about derivative counterparties paying as promised. Closure risk is about the ETF being shut down.
- **Securities lending fees are not free.** They can offset expenses, but borrower default risk belongs to ETF investors.
- **Creation halts can cause premiums.** If new shares cannot be created, APs cannot easily arbitrage away high market prices.
- **Leveraged and inverse ETFs reset daily.** Do not multiply the index's monthly return by the leverage multiple unless the product explicitly targets that horizon.
- **Tactical ETF selection focuses on trading cost.** Low management fees matter more for long-term holding periods.
- **Portfolio completion fixes a strategic gap.** Tactical allocation expresses a short-term view.
- **Smart beta is rules-based active exposure.** It is not pure market-cap passive investing.
- **Large investors may outgrow ETFs.** SMAs can be cheaper and more customizable for large asset owners.

## Memory Hooks

Use **CLOSE** for ETF risks:

| Letter | Risk |
|---|---|
| C | Counterparty and creation-halt risk |
| L | Lending and liquidity risk |
| O | Outcome/expectation risk from leveraged or inverse products |
| S | Settlement risk |
| E | Exit risk from fund closure |

Use **CRaP-TAS** for ETF applications:

| Hook | Application |
|---|---|
| C | Cash equitization |
| R | Rebalancing |
| P | Portfolio completion |
| T | Transition management |
| A | Asset-class exposure |
| S | Smart beta, sector, and tactical strategies |

## Related Concepts

- [[ETF Mechanics and Applications]]
- [[ETF Spreads Premiums Discounts and Costs]]
- [[Tracking Error]]
- [[Counterparty risk]]
- [[Exchange-Traded Note]]
- [[Authorized Participant]]
- [[Net Asset Value]]
- [[Premium]]
- [[Discount]]
- [[Smart Beta]]
- [[Factor Investing]]
- [[Tactical Asset Allocation]]
- [[Separately Managed Account]]
