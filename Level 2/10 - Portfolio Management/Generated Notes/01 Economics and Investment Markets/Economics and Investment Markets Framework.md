---
title: "Economics and Investment Markets Framework"
subject: "Portfolio Management"
tags: [CFA-L2, portfolio-management, economics, business-cycle, risk-premiums]
aliases:
  - Economics and Investment Markets
  - Business cycle and asset values
  - Consumption hedging
  - Equity risk premium and consumption hedging
---

# Economics and Investment Markets Framework

Macroeconomic variables matter for asset prices only if they change one of three things: expected cash flows, default-free rates, or risk premiums. The exam often gives a macro story and asks which valuation channel is affected.

The shortcut:

```text
Macro surprise
  -> cash flows, rates, or risk premiums
  -> asset value changes
```

If the macro factor does not change one of those channels, it should not change value.

## The Three Valuation Channels

A simplified asset value model is:

$$
P = \sum_{t=1}^{n}\frac{E(CF_t)}{(1+I+\theta+\rho)^t}
$$

Where:

| Term | Meaning |
|---|---|
| \(E(CF_t)\) | Expected cash flows |
| \(I\) | Real default-free rate |
| \(\theta\) | Expected inflation component |
| \(\rho\) | Risk premium |

Macroeconomic factors affect value through:

| Channel | Example |
|---|---|
| Cash flow timing or magnitude | Earnings expectations rise in expansion |
| Default-free interest rates | Central bank policy changes short-term rates |
| Risk premiums | Credit spreads widen in recession |

## Expectations Matter

Asset prices already reflect expected information. Prices move when expectations change.

Example:

- If investors already expect inflation to rise, bond prices may already reflect that.
- If inflation rises more than expected, bond values can fall further.
- If inflation rises less than expected, bond values may rise even though inflation is still high.

The exam trap is to confuse a high level with a surprise. Markets react to the difference between expected and realized information.

## Real Rates and Future Growth

The real risk-free rate is tied to intertemporal substitution: how much investors value consumption today versus consumption in the future.

If investors expect strong future growth:

1. Future wealth is expected to be high.
2. Marginal utility of future consumption is lower.
3. Investors are less eager to save.
4. Real rates must rise to induce saving.

If investors expect weak future growth:

1. Future consumption is expected to be scarce.
2. Marginal utility of future consumption is high.
3. Investors want to save.
4. Real rates fall.

Exam trap: a weak economy does not automatically mean high real default-free rates. Poor expected growth tends to push real risk-free rates down.

## Business Cycle and the Yield Curve

| Phase | Policy rate behavior | Yield curve | Bond implication |
|---|---|---|---|
| Initial recovery | Rates low or bottoming | Steep | Long bonds may underperform as yields rise |
| Expansion | Central bank raises short rates | Flattening | Short rates rise faster than long rates |
| Slowdown/peak | Short rates high | Flat or inverted | Long yields may anticipate recession |
| Contraction/recession | Central bank cuts short rates | Steepening | High-quality bonds often benefit |

The curve often inverts before or near the peak, not at the deepest point of recession. During recession, policy easing usually pushes short rates down and steepens the curve.

## Credit Spreads

[[Credit spreads]] compensate investors for default risk and other credit-related risks.

Business-cycle pattern:

| Phase | Credit spreads | Credit-sensitive bonds |
|---|---|---|
| Expansion | Narrow | Outperform default-free bonds |
| Slowdown | Begin widening | Performance weakens |
| Recession | Wide | Underperform default-free bonds |
| Recovery | Narrow from wide levels | Lower-rated bonds can outperform strongly |

Lower-rated bonds are more sensitive to spread changes. When spreads narrow, lower-rated bonds may outperform because their yields fall more. When spreads widen, higher-rated bonds typically outperform on a relative basis.

## Sector Credit Quality

Company credit quality depends partly on product-market characteristics.

| Sector type | Cycle sensitivity | Credit spread behavior |
|---|---|---|
| Cyclical | Revenues and profits swing with economy | Spreads widen more in downturns |
| Defensive/non-cyclical | Revenues and profits more stable | Spreads more stable |

Financial leverage also matters. A cyclical company with high leverage is especially exposed because cash flows fall just when debt capacity matters most.

## Earnings and Multiples

Cyclical companies have earnings that rise sharply in expansions and fall sharply in recessions. Defensive companies have more stable earnings.

Valuation multiples tend to be cyclical:

| Macro condition | Effect on multiples |
|---|---|
| Higher expected growth | Multiples rise |
| Lower required return | Multiples rise |
| Lower equity risk premium | Multiples rise |
| Recession and higher uncertainty | Multiples fall |

This connects to:

$$
P/E \approx \frac{\text{Payout ratio}}{r-g}
$$

If \(g\) rises or \(r\) falls, the justified P/E rises. During expansions, growth expectations often improve and risk premiums decline, pushing multiples higher.

## Consumption Hedging and Equity Risk Premium

An asset has good consumption-hedging properties if it pays off when investors most need wealth: bad economic times, when marginal utility of consumption is high.

| Asset behavior | Consumption hedge? | Required risk premium |
|---|---:|---:|
| Pays off in bad times | Good hedge | Low or negative |
| Performs poorly in bad times | Poor hedge | Positive |

Equities are generally poor consumption hedges because stock prices tend to fall in recessions. They fail exactly when investors most value extra consumption.

That is why investors require a positive [[equity risk premium]].

Exam trap: equities do not earn a high risk premium because they are good hedges. They earn it because they are poor hedges.

## Commercial Real Estate

Commercial real estate has both bond-like and equity-like characteristics.

Bond-like:

- Lease contracts create rental income streams.
- Tenant credit quality affects value.
- Income resembles scheduled cash flows.

Equity-like:

- Property values depend on economic growth.
- Terminal value is uncertain.
- Demand, occupancy, and cap rates are cyclical.

Additional risk premiums:

- Illiquidity premium.
- Tenant credit premium.
- Term premium.
- Risk premium for uncertain terminal value.

Rents may be relatively stable during a lease term, but property values can be highly cyclical because cap rates, discount rates, and terminal value expectations change.

## Exam Traps

- **Macro affects value through cash flows, rates, or risk premiums.** Identify the channel.
- **Markets respond to surprises.** Expected bad news may already be priced.
- **Yield curve inversion is a slowdown/peak signal.** In recession, rate cuts can steepen the curve.
- **Lower-rated bonds benefit more when credit spreads narrow and suffer more when spreads widen.**
- **Equities are poor consumption hedges.** That is why the equity risk premium is positive.
- **Commercial real estate cash flows can look bond-like, but property values are cyclical.**
- **Cyclical companies have more volatile earnings and credit spreads than defensive companies.**
- **Multiples rise when growth expectations rise or required returns/risk premiums fall.**

## Memory Hook

**Every macro story must enter valuation through cash flows, rates, or risk premiums.**

If you cannot name the channel, do not change the value.
