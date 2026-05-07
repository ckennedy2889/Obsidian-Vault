---
title: Economics and Investment Markets
subject: Economics
tags: [CFA-L2, Economics, InvestmentMarkets, BusinessCycle, YieldCurve, RiskPremium, PresentValue, TaylorRule, TIPS, CreditSpreads, EquityRiskPremium, CommercialRealEstate]
aliases: [Econ & Investment Markets, L2 Econ Module 1, Economics and Investment Markets Reading]
---

# Economics and Investment Markets

> [!abstract] The One-Sentence Version
> Every asset price — a Treasury, a bond, a stock, a shopping mall — is the discounted stream of cash flows, and **everything the economy does** (growth, inflation, central-bank policy, panic, optimism) moves price by changing one of three things: **the real risk-free rate**, the **expected cash flows**, or the **risk premium** investors demand.

This is the grand unified theory of investing. If you remember nothing else from this module, remember the sentence above — every LOS below is just a special case of it.

---

## 1. The Fundamental Pricing Equation — The Master Key

Imagine you're renting out your money. Whoever borrows it must compensate you for:

1. **Waiting** (you can't spend it today — that's the real interest rate)
2. **Inflation** (when you get paid back, each dollar buys less bread)
3. **Risk** (they might not pay you back, or the deal might sour)

Stack those three compensations on top of each other, and you've built the **discount rate** — the denominator that turns tomorrow's cash flow into today's price.

$$
\boxed{\,P_t^{\,i} \;=\; \sum_{s=1}^{N}\frac{E_t\!\left[\widetilde{CF}_{t+s}^{\,i}\right]}{\bigl(1+l_{t,s}+\theta_{t,s}+\rho_{t,s}^{\,i}\bigr)^{\,s}}\,}
$$

| Symbol | Plain English | Who owns it |
|---|---|---|
| $P_t^{\,i}$ | Today's price of asset $i$ | Market |
| $E_t[\widetilde{CF}_{t+s}^{\,i}]$ | What the market **expects** to receive at time $t+s$ — the tilde means it's uncertain | Issuer's future fundamentals |
| $l_{t,s}$ | **Real default-free rate** for maturity $s$ ("just the waiting fee") | Central bank / savers vs. borrowers |
| $\theta_{t,s}$ | **Expected inflation** over the next $s$ years | Inflation regime |
| $\rho_{t,s}^{\,i}$ | **Risk premium** for this specific asset (default, liquidity, equity, illiquidity, etc.) | The asset's risk profile |

> [!tip] Memory Hook — **"L-Theta-Rho"**
> Say it out loud three times: **L** for the *Loan*-waiting fee, **Theta** for *Theta* (expected inflation — yes, it just happens to start with the same sound), **Rho** for the *Risk* cushion. Stack those three and you've built a discount rate from scratch.

### 1.1 The Three Levers Economic Factors Can Pull

Because the equation is the whole story, **any** economic fact must enter prices through one of these three doors:

```
           ┌──────────────────────────────────────────────┐
           │          PRICE = f( CF , r_f , RP )          │
           └──────────────────────────────────────────────┘
                       ↑         ↑        ↑
                       │         │        │
           ┌───────────┘         │        └────────────┐
           │                     │                      │
   (1) Expected            (2) Default-free     (3) Risk premiums
   cash flows              real rates            (credit, equity,
   (dividends,             across maturities      liquidity, ...)
   coupons, rents)         (the yield curve)
```

- **Good GDP news** (strong jobs report) → raises $E_t[CF]$ for cyclical firms; also pushes $l_{t,s}$ higher because the central bank will hike.
- **Risk-off headline** (war, bank run) → widens $\rho$, drops $E_t[CF]$ expectations, pushes $l_{t,s}$ lower (flight-to-quality).
- **Inflation surprise** → raises $\theta_{t,s}$ and the inflation-risk component of $\rho$.

Every single later LOS is a drill-down on **which lever moves, in which direction, and by how much**.

See: [[Present Value Model]] • [[Default-Free Rate]] • [[Risk Premium]]

---

## 2. Expectations: Prices Live in the Future, Not the Past

Financial assets are **pure claims on the future**. Yesterday's earnings are sunk; what matters is what the market *thinks* will happen next.

### 2.1 The "News" Rule

> A price moves only when *new information* arrives — information that **surprises** the consensus. Everything already expected is already in the price.

| Scenario | Consensus expected | Actual outcome | Price reaction |
|---|---|---|---|
| Good "news" | +3% EPS growth | +5% EPS growth | **Rises** (positive surprise) |
| "Less-good" news | +8% EPS growth | +5% EPS growth | **Falls** (negative surprise, even though growth is positive!) |
| Confirming news | +5% EPS growth | +5% EPS growth | **Flat** (already baked in) |

This is why a company can "beat expectations" yet see its stock fall — analysts had whispered something even higher. *Whisper numbers > published consensus*.

### 2.2 Why This Matters Mechanically

Every denominator term ($l$, $\theta$, $\rho$) and the numerator $E_t[CF]$ carries an **expectations subscript** $E_t$. When expectations shift, prices jump before any actual data changes. This is why markets seem "forward-looking" — because they literally are. They're pricing $t+s$, not $t$.

See: [[Expectations]] • [[Efficient Market Hypothesis]]

---

## 3. Real Short Rates: Growth, Volatility & the Inter-temporal Rate of Substitution

Why are real short-term rates ~0.5% in Japan but ~2% in the US over long averages? The answer lies in how people trade off **consumption today vs. consumption tomorrow**.

### 3.1 The Inter-temporal Rate of Substitution (IRS)

Think of $m_{t,s}$ as the ratio: *how much would I pay today for an extra burger delivered $s$ years from now*?

- If you expect to be **richer** in the future, an extra burger then is less exciting (diminishing marginal utility) → $m$ is **low** → you demand a **high** real rate to delay spending.
- If you expect **bad times** ahead, an extra burger later is very valuable → $m$ is **high** → you'll accept a **low** real rate.

$$
1 + l_{t,s} \;\approx\; \frac{1}{E_t[m_{t,s}]}
$$

The real default-free rate is essentially **1 over the average IRS**.

### 3.2 Growth Rate → Real Rate (Positive Link)

High expected GDP growth → people expect to be richer tomorrow → low desire to save → savers must be bribed with higher real rates.

> **Fast-growing economies have higher real short-term rates on average.**

### 3.3 Volatility → Real Rate (Negative Link)

If the future is "wobbly" (high variance of growth), risk-averse people hedge by **saving more today** (precautionary savings). Higher supply of savings drives down the real rate.

> **Volatile economies have *lower* average real short-term rates**, because savers' demand for safe assets is elevated.

| Economy | Long-run real growth | Growth volatility | Expected real short rate |
|---|---|---|---|
| Stable, fast-growing (e.g., historical US) | High | Moderate | **High** |
| Stable, slow-growing (e.g., Japan) | Low | Low | **Low** |
| Fast-growing but volatile (emerging) | High | High | **Mixed** — can be suppressed |
| Slow + volatile | Low | High | **Very low / negative** |

### 3.4 Taylor Rule — The Central Bank's GPS

Central banks don't set $l_{t,s}$ directly; they set the **overnight policy rate** $pr_t$. John Taylor's heuristic:

$$
\boxed{\,pr_t \;=\; l_t \;+\; \pi_t \;+\; 0.5\,(\pi_t - \pi_t^*) \;+\; 0.5\,(Y_t - Y_t^*)\,}
$$

| Term | Meaning |
|---|---|
| $l_t$ | Neutral real rate (neither stimulative nor restrictive) |
| $\pi_t$ | Current inflation |
| $\pi_t - \pi_t^*$ | **Inflation gap** (actual minus target) |
| $Y_t - Y_t^*$ | **Output gap** (actual GDP minus potential GDP, in log terms) |

#### Worked Example — Taylor Rule

> Neutral real rate $l_t = 2\%$; current inflation $\pi_t = 3\%$; target $\pi_t^* = 2\%$; economy is overheating with output gap $= +2\%$.
>
> $pr_t = 2.0 + 3.0 + 0.5(3.0-2.0) + 0.5(2.0) = 2 + 3 + 0.5 + 1 = \mathbf{6.5\%}$
>
> A "correct" policy rate is 6.5%. If the central bank is holding rates at 4%, policy is **too easy** — inflation will accelerate.

**Reading the rule:** a positive inflation or output gap *adds* to the neutral rate (hawkish); a negative gap subtracts (dovish).

See: [[Neutral Real Rate]] • [[Taylor Rule]] • [[Level 2/Generated Notes/03 - Economics/Output Gap]] • [[Inter-temporal Rate of Substitution]]

---

## 4. The Business Cycle → Policy Rates, Yield-Curve Slope, Bond Returns

The business cycle is the heartbeat of fixed income. Every phase changes the policy rate and the *slope* of the Treasury yield curve — and therefore which maturity of bond wins.

![[business-cycle-yield-curves.png]]

### 4.1 Yield-Curve Vocabulary — the Four Moves

| Move | What happens | When |
|---|---|---|
| **Bullish steepening** | **Short rates fall faster** than long rates → curve steepens | Recovery / early expansion (rate cuts) |
| **Bearish flattening** | **Short rates rise faster** than long rates → curve flattens | Late expansion / peak (rate hikes) |
| **Bullish flattening** | **Long rates fall faster** than short rates → curve flattens | Recession / flight-to-quality |
| **Bearish steepening** | **Long rates rise faster** than short rates → curve steepens | Inflation scare / fiscal shock |

> [!tip] Mnemonic — **"Bull = rates falling, Bear = rates rising"**
> "Bull" markets in bonds mean **prices UP, yields DOWN**. "Bear" markets in bonds mean prices down, yields up. So:
> - *Bullish* steepening/flattening = **yields falling**
> - *Bearish* steepening/flattening = **yields rising**
> And "steepening/flattening" tells you *which end* (short or long) is moving faster.

### 4.2 Full Phase-by-Phase Table

| Phase | Output gap | CB stance | Yield-curve move | Best maturity | Economic intuition |
|---|---|---|---|---|---|
| **Trough / Initial Recovery** | Very negative | Aggressive cuts | Bullish steepening | **Long-duration** Treasuries win (biggest price jump as rates collapse) | Fed slashes short rates; long rates fall too but less, leaving curve steep |
| **Early Expansion** | Closing | Still easy | Steep curve; bull-flattens as rates drift down | Intermediate | Carry + roll-down; curve is still steep |
| **Late Expansion** | Positive & rising | Tightening | **Bearish flattening** | Short-maturity (duration hedge) | Fed hikes lift short end faster than long end |
| **Peak** | Peak positive | Restrictive | Flat → **inverted** | Cash / T-Bills | Classic recession-warning signal |
| **Early Contraction** | Turns negative | Begins easing | Bullish flattening | **Long Treasuries** (flight-to-quality) | Investors dump risky assets, pile into long Treasuries |
| **Deep Recession** | Very negative | Ultra-easy | Re-steepening | Long-duration initially, then shortens | Cycle resets to trough |

> [!tip] Mnemonic — **"LIS-C-L"** (pronounced "lisc-L")
> Bond maturity winner by phase, starting at the trough: **L**ong → **I**ntermediate → **S**hort → **C**ash → **L**ong. Long comes first (capital gains from falling rates) and returns last (flight-to-quality).

### 4.3 Why Duration is Destiny

Remember **Macaulay duration**: %ΔP ≈ –Dur × Δy. A 10-year bond with duration ~8.5 moves ~8.5× as much as a 1-year bond per basis point of yield change. In rate-cutting phases, long bonds win *on price alone*; in rate-hiking phases, short bonds *lose less*.

See: [[Yield Curve]] • [[Duration]] • [[Business Cycle]] • [[Flight to Quality]]

---

## 5. Nominal vs. Inflation-Indexed Bonds — The Break-Even Inflation Spread

A nominal Treasury pays a fixed *dollar* coupon; a **TIPS** (Treasury Inflation-Protected Security) adjusts principal with CPI, so its coupon is fixed in *real* terms. The yield gap between the two is a window into what the market believes about future inflation — and how risky that belief feels.

### 5.1 The Break-Even Inflation Rate (BEI)

$$
\boxed{\,\text{BEI} \;=\; y_{\text{nominal}} \;-\; y_{\text{TIPS}} \;=\; \theta_{t,s} \;+\; \pi_{t,s}\,}
$$

| Component | Meaning |
|---|---|
| $\theta_{t,s}$ | **Expected inflation** over the period |
| $\pi_{t,s}$ | **Inflation risk premium** (compensation for *uncertainty* about inflation, separate from the point forecast) |

> **BEI is NOT just "the market's inflation forecast."** It's the forecast *plus* a risk premium.

### 5.2 Worked Example

> 10-year nominal Treasury yield = **4.5%**
> 10-year TIPS real yield = **2.0%**
> BEI = 4.5% − 2.0% = **2.5%**
>
> If surveys/estimates put the inflation risk premium at **0.3%**, the market's point forecast for inflation is:
>
> $\theta = \text{BEI} - \pi = 2.5\% - 0.3\% = \mathbf{2.2\%}$

### 5.3 Factors That Move the BEI Spread

| Factor | Direction | Why |
|---|---|---|
| Rising inflation expectations ($\theta$ ↑) | BEI widens | Nominals need higher yield to compensate |
| Greater inflation **uncertainty** ($\pi$ ↑) | BEI widens | Investors demand bigger risk premium |
| Improved central-bank credibility | BEI narrows | Risk premium collapses |
| TIPS illiquidity premium | BEI **understates** inflation | TIPS yield is pushed up by liquidity discount |
| Deflation scare | BEI collapses / negative | Nominal yields crash faster than TIPS |

See: [[TIPS]] • [[Break-Even Inflation]] • [[Inflation Risk Premium]]

---

## 6. Credit Spreads & the Business Cycle

A **credit spread** is the extra yield a corporate (or sovereign) borrower pays over a default-free benchmark. It's the $\gamma_{t,s}$ piece of the risk premium $\rho$.

$$
\text{Credit Spread} \;=\; y_{\text{corporate}} \;-\; y_{\text{Treasury (same maturity)}}
$$

Two ingredients compensate:
1. **Probability of default** ($PD$) — will they pay?
2. **Loss given default** ($LGD = 1 - \text{recovery rate}$) — if they don't pay, how much do I lose?

### 6.1 Why Spreads Widen in Recessions (Double Whammy)

| Factor | Recession effect |
|---|---|
| Default probability ($PD$) | **↑** — weaker cash flows, refinancing stress |
| Recovery rates | **↓** — collateral (real estate, equipment) falls in value |
| Result | Expected loss = $PD \times LGD$ **explodes** → spreads widen |

Additionally, investor **risk aversion** rises in bad times — the inter-temporal rate of substitution $m$ is high, so the market demands extra premium for assets that pay off poorly in those states.

### 6.2 Cycle-by-Cycle Credit-Sensitive Bond Performance

| Phase | Spread direction | High-yield (HY) vs. investment grade (IG) |
|---|---|---|
| Trough / recovery | Spreads **narrow rapidly** | **HY outperforms IG dramatically** (more spread to compress) |
| Expansion | Spreads stable or slowly narrow | HY > IG slightly |
| Late expansion / peak | Spreads begin widening | IG > HY |
| Contraction | Spreads **blow out** | IG >> HY (HY gets crushed) |

> [!tip] Mnemonic — **"Junk Loves Recovery"**
> High-yield (junk) bonds deliver equity-like returns in the early recovery because their enormous spreads compress quickly. In recessions, they behave like a stock portfolio — ugly.

### 6.3 Worked Example — Decomposing a Corporate Yield

> A 1-year corporate bond yields **10%**. Market-implied components:
> - Real default-free rate: **3.25%**
> - Expected inflation: **2.0%**
> - Inflation risk premium: **0.25%**
>
> Credit premium = $10\% - (3.25\% + 2.0\% + 0.25\%) = \mathbf{4.5\%}$
>
> That 4.5% is the market's compensation for the issuer's default + liquidity risk combined.

See: [[Credit Spread]] • [[Default Probability]] • [[CFA_Glossary/Loss given default]] • [[High Yield Bonds]]

---

## 7. Product-Market Characteristics → Credit Quality

Not every firm breathes in rhythm with the economy. The nature of what a company *sells* determines how stable its cash flows (and therefore its credit spread) are across the cycle.

### 7.1 Cyclical vs. Defensive Demand

| Business type | Examples | Demand in recession | Credit-spread volatility |
|---|---|---|---|
| **Cyclical — consumer durables** | Ford, Toll Brothers, Caterpillar | Collapses (big-ticket deferrable) | **High** |
| **Cyclical — consumer discretionary** | Las Vegas Sands, Norwegian Cruise | Collapses | High |
| **Defensive — consumer staples** | Procter & Gamble, Coca-Cola, Kroger | Nearly flat | **Low** |
| **Defensive — utilities, healthcare** | Duke Energy, Johnson & Johnson | Very stable | Very low |

### 7.2 Pricing Power

Pricing power = the ability to raise prices without losing volume. Two drivers:
- **Differentiation / brand** (Apple can raise iPhone prices; a commodity steelmaker cannot).
- **Elasticity of demand** (insulin is inelastic; leisure air travel is elastic).

High pricing power → stable margins → stable cash flows → tighter credit spreads.

### 7.3 Customer Concentration

A firm with three big customers has huge idiosyncratic credit risk: lose one contract, lose the firm. This is especially common in B2B suppliers (auto-parts makers selling into the Big Three). Concentration risk = wider credit spread at any cycle stage.

### 7.4 The Composite Picture

| Factor | Better credit quality when... |
|---|---|
| Demand cyclicality | **Defensive** / non-cyclical |
| Pricing power | **High** (brand, patents, network effects) |
| Customer base | **Diversified** (many small customers) |
| Input cost pass-through | Easy (e.g., utilities with regulated pass-through) |
| Operating leverage | Low (variable-cost base) |

### 7.5 Worked Comparison

> Two 5-year BBB-rated corporate bonds, same Treasury curve, same rating, same recession:
> - **Firm A (cyclical heavy-equipment maker)** — spread widens from 150 bp → **400 bp**.
> - **Firm B (consumer-staples conglomerate)** — spread widens from 120 bp → **170 bp**.
>
> The *same* credit rating can produce wildly different spread behaviour through the cycle. Rating agencies move slowly; spreads don't.

See: [[Cyclical vs Defensive]] • [[Pricing Power]] • [[Credit Analysis]]

---

## 8. Equity Risk Premium — The Consumption-Hedging Story

Equities are claims on *forever* dividends, which makes them (i) long-duration, (ii) growth-levered, and (iii) **terrible hedges for bad times**. That last property is the deep reason equities command a high risk premium.

### 8.1 Consumption-CAPM Intuition (No Math Required)

Risk-averse investors value a dollar **most** when they need it most. When do they need it most? In bad times, when income is low and marginal utility of consumption is high.

**What does equity do in bad times?** It crashes. Exactly the opposite of what you want.

$$
\text{Required ERP} \;\propto\; -\,\text{Cov}\!\left(R_{\text{equity}},\; m_{t,s}\right)
$$

Equity returns $R_{\text{equity}}$ are **pro-cyclical** (high when economy is good = when $m$ is low) and **negatively covary** with the inter-temporal rate of substitution. That negative covariance is risk that can't be diversified away — and it commands the **Equity Risk Premium (ERP)**.

> [!tip] Mnemonic — **"BTBP — Bad Times, Bad Payoffs"**
> Any asset that pays off *poorly* when marginal utility is *high* (bad times) is risky and must offer a premium. Equities are the canonical example.

### 8.2 What Moves the ERP Over Time?

| Factor | ERP impact | Why |
|---|---|---|
| Higher **consumption volatility** (recessions feel deeper) | ↑ | Worse hedging → bigger premium |
| Higher **risk aversion** (aging demographics, bear-market memory) | ↑ | Investors more sensitive to bad states |
| Better hedging alternatives (TIPS, hedged funds) | ↓ | Substitutes reduce demand for ERP |
| Stable GDP regime | ↓ | Lower fundamental volatility |

Historical US ERP: roughly **4–6%** over long windows, but *implied* ERP from dividend-discount models can spike to 7–8% in crises (1974, 2008, 2020) and drop below 3% in euphoria (1999).

See: [[Equity Risk Premium]] • [[Consumption CAPM]] • [[Pro-cyclical]] • [[Marginal Utility]]

---

## 9. Earnings Growth Expectations Across the Cycle

This is two different conversations, depending on your horizon.

### 9.1 Short-Term Earnings — All Cycle, All the Time

Aggregate corporate earnings are **more volatile than GDP** because firms have operating leverage (fixed costs). Every recession since WWII has coincided with a sharp drop in real S&P 500 earnings — often –20% to –50% peak-to-trough.

```
S&P 500 real EPS, stylized:

  ┌─────────────── Peak EPS ────────────────┐
  │                                          │
  │   ╱╲       ╱╲                            │
  │  ╱  ╲     ╱  ╲        ← peak             │
  │ ╱    ╲   ╱    ╲                          │
  │╱      ╲_╱      ╲_    ← trough           │
  │                                          │
  └──────────────────────────────────────────┘
       time →
```

**Short-horizon equity analysts are, whether they admit it or not, macro forecasters in disguise.** Getting the cycle right matters more than getting any one name right.

### 9.2 Long-Term Earnings — Bounded by Potential GDP

Over a long horizon, aggregate real earnings **cannot exceed** real potential GDP growth. Why?

> If corporate earnings grew faster than GDP forever, the **earnings share of GDP** would eventually hit 100% — labour's share would go to zero. Impossible. So earnings growth must **mean-revert** to potential GDP growth.

Long-run real growth rate:
$$
g_{\text{real EPS, long-run}} \;\approx\; g_{\text{potential GDP}}
$$

### 9.3 Implication for Discounted-Cash-Flow Models

In a two-stage DDM, use:
- **High growth** (or cycle-sensitive growth) for the near term (years 1–5).
- **Steady-state growth** = potential GDP growth for the terminal value. **Never put a terminal growth rate above potential GDP** — it implies eating the economy.

See: [[Potential GDP]] • [[Earnings Growth]] • [[Two-Stage DDM]]

---

## 10. Cyclical Effects on Valuation Multiples

The P/E ratio is a **mood ring** for the market. Because earnings $E$ move sharply with the cycle and price $P$ moves on expectations of future earnings, the ratio $P/E$ dances.

### 10.1 The "P/E Paradox"

| Cycle phase | Current $E$ | Forward expectations | $P$ | Resulting $P/E$ | Why |
|---|---|---|---|---|---|
| **Early recovery** | Depressed (trough) | Sharply higher | Rising | **Very high** | Market prices the rebound before it shows in $E$ |
| **Mid-expansion** | Rising | Steady | Rising | **Normal** | Earnings and price grow together |
| **Late-cycle peak** | Very high | Cautious (mean reversion) | Flat | **Low** | Market doubts sustainability — *this is when retail investors feel stocks are "cheap"* |
| **Recession** | Collapsing | Uncertain | Falling faster | **Very low initially, then spikes** as $E$ collapses faster than $P$ | Earnings denominator implodes |

> [!warning] The Trap
> **Low P/E at the peak** can be a sell signal, not a buy signal. **High P/E at the trough** often marks the *best* entry point. The ratio must be interpreted *against the cycle*.

### 10.2 The Shiller CAPE Fix

Cyclically-Adjusted P/E (Shiller) uses **10-year average real earnings** in the denominator, smoothing out the cycle. It's more stable and better at long-horizon forecasting.

$$
CAPE_t \;=\; \frac{P_t}{\text{avg}_{k=1}^{10}E_{t-k}^{\text{real}}}
$$

### 10.3 Earnings Yield, Real Rates & the Fed Model

Take the reciprocal of P/E: the **earnings yield** $E/P$. Over long stretches, it tracks real interest rates + an equity risk premium:

$$
\frac{E}{P} \;\approx\; l_{t,s} \;+\; \text{ERP}
$$

- Falling real rates ($l$ ↓) → earnings yield falls → $P/E$ **expands**.
- Rising real rates → $P/E$ **contracts**.

This is why the 2010s "TINA" (There Is No Alternative) era saw multiple expansion — suppressed $l$ lifted the fair P/E.

### 10.4 EV/EBITDA Dynamics

EV/EBITDA is less volatile than P/E because EBITDA strips out interest, taxes, and D&A — but it still **expands in recoveries and compresses at peaks**. Same story, slightly muted.

See: [[P/E Ratio]] • [[Shiller CAPE]] • [[Earnings Yield]] • [[Fed Model]] • [[EV/EBITDA]]

---

## 11. Economic Factors in Commercial Real Estate (CRE)

CRE is the **Frankenstein asset**: half bond (lease contracts), half equity (residual value), with a hefty dose of illiquidity on top. Its required-return formula has *more* components than any other asset.

### 11.1 The Six-Piece CRE Discount Rate

$$
\boxed{\,r_{\text{CRE}} \;=\; l_{t,s} \;+\; \theta_{t,s} \;+\; \pi_{t,s} \;+\; \gamma_{t,s} \;+\; \kappa_{t,s} \;+\; \phi_{t,s}\,}
$$

| Symbol | Component | Rough range (rough, current-cycle illustrative) |
|---|---|---|
| $l_{t,s}$ | Real default-free rate | 1–2% |
| $\theta_{t,s}$ | Expected inflation | 2–3% |
| $\pi_{t,s}$ | Inflation risk premium | 0.25–0.75% |
| $\gamma_{t,s}$ | **Credit spread** — tenant default risk | 0.5–2% (retail/office higher) |
| $\kappa_{t,s}$ | **Equity / terminal-value risk** — property value uncertainty at lease end | 0.25–1.5% |
| $\phi_{t,s}$ | **Illiquidity premium** — you can't sell a building in a day | 0.75–1.5% |

> [!tip] Mnemonic — **"RE-CLIP"**
> **R**eal rate → **E**xpected inflation → **C**redit risk (tenant) → **L**iquidity → **I**nflation risk → **P**roperty/equity risk. Six bricks that build the CRE discount rate.

### 11.2 Cap Rate vs. Discount Rate

Capitalization rate (cap rate) is the *current yield* on a property:
$$
\text{Cap rate} \;=\; \frac{\text{NOI}}{\text{Property value}}
$$

In a constant-growth (Gordon-style) model:
$$
r \;=\; \text{cap rate} \;+\; g_{\text{NOI}}
$$

A 6% cap rate + 2% NOI growth ≈ 8% total required return.

### 11.3 Business Cycle & CRE

| CRE characteristic | Cycle behaviour |
|---|---|
| **Rental income** | Surprisingly **sticky** — long leases (5–15 years) smooth income. UK 1990–92: rents held up while values crashed. |
| **Capital values** | Highly **pro-cyclical** — they swing with cap rates (discount rate) and expected NOI |
| **Vacancy** | Rises in recessions, especially for office/retail |
| **New supply** | Lags the cycle (construction pipeline) — often delivers *into* a downturn, amplifying price drops |
| **Inflation hedge** | Partial — leases often have CPI escalators; replacement cost rises with inflation |

### 11.4 Worked Example — CRE Investment Decision

> You're underwriting a 10-year triple-net lease to a national grocery chain.
>
> **Inputs**
> - Real rate $l = 1.25\%$
> - Expected inflation $\theta = 2.5\%$
> - Inflation risk premium $\pi = 0.5\%$
> - Credit spread (grocer is BBB) $\gamma = 1.5\%$
> - Equity/terminal-value risk $\kappa = 0.5\%$
> - Illiquidity premium $\phi = 1.0\%$
>
> **Discount rate**
> $r = 1.25 + 2.5 + 0.5 + 1.5 + 0.5 + 1.0 = \mathbf{7.25\%}$
>
> **Cash flows**
> - Annual net rent: $500{,}000$ (flat for simplicity)
> - Terminal sale value (year 10): $10{,}000{,}000$
>
> **Present value**
> $PV = \sum_{t=1}^{10}\frac{500{,}000}{(1.0725)^t} + \frac{10{,}000{,}000}{(1.0725)^{10}}$
> $PV \approx 3{,}478{,}000 + 4{,}967{,}000 \approx \mathbf{\$8{,}445{,}000}$
>
> **Decision**: if the asking price is **$8.2M**, buy (PV > price). If asking is **$9.0M**, pass.

### 11.5 What Makes CRE Unique

- Long leases → cash-flow smoothing relative to equity.
- Large illiquidity premium → don't compare naked yields to REIT yields; public REITs embed liquidity.
- Heavy use of **leverage** (70–80% LTV typical) amplifies both upside and downside — small NOI changes can wipe out equity.
- **Local** — CRE returns are tied to a single metro's supply-demand balance, not national GDP alone.

See: [[Commercial Real Estate]] • [[Cap Rate]] • [[Net Operating Income]] • [[REITs]] • [[Illiquidity Premium]]

---

## 12. Putting It All Together — The Master Summary Table

| Asset class | Main levers affected | Best in expansion | Worst in recession |
|---|---|---|---|
| **Default-free short bonds** | $l_{t,s}$, $\theta_{t,s}$ (short end) | Modest returns | Flat-to-positive (policy cuts) |
| **Default-free long bonds** | $l_{t,s}$ + term premium | Small losses in hikes | **Best performer** in flight-to-quality |
| **TIPS** | Real $l$ only | Modest | Good when inflation rising + real rates falling |
| **Investment-grade credit** | Rate + modest $\gamma$ | Tight spreads, carry | Modest widening |
| **High-yield credit** | $\gamma$ dominates | **Spread compression bonanza** | **Catastrophic** (spread blow-out + defaults) |
| **Equities** | $E[CF]$, ERP, $l_{t,s}$ | **Best performer** | Worst performer |
| **Commercial real estate** | All six RE-CLIP pieces | Very strong | Steep capital-value drops, sticky rents |

### 12.1 The Three-Lever Recap (memorize this)

> All asset-price movements trace back to changes in:
> 1. **Default-free real rates across maturities** (the yield curve)
> 2. **Expected cash flows** (earnings, dividends, rents, coupons)
> 3. **Risk premiums** (credit, equity, liquidity, inflation)
>
> Every LOS in this reading is one of those three levers being pulled by a macro force.

### 12.2 Exam Danger Zones

| Trap | Fix |
|---|---|
| Confusing **bullish/bearish steepening** vs. flattening | Bull = yields falling; steep/flat = which end moved more |
| Assuming BEI = inflation forecast | BEI = expected inflation **+** inflation risk premium |
| Reading a **low P/E at the peak** as cheap | Earnings are peaking — regression to mean awaits |
| Forgetting the ERP comes from **consumption hedging**, not volatility alone | A high-vol asset that hedges bad times could have a *low* premium |
| Using a terminal growth rate > potential GDP | Physically impossible long-run; always bounded by $g_{\text{GDP}}$ |
| Ignoring the illiquidity premium in CRE | It's 75–150 bp; huge relative to cap rates |

---

## 13. Formula Cheat Sheet

| Formula | What it gives you |
|---|---|
| $P_t^i = \sum_s \dfrac{E_t[CF_{t+s}]}{(1+l+\theta+\rho)^s}$ | Master present-value equation |
| $1+l \approx 1/E[m]$ | Real rate from inter-temporal substitution |
| $pr_t = l + \pi + 0.5(\pi-\pi^*) + 0.5(Y-Y^*)$ | Taylor rule policy rate |
| $\text{BEI} = y_{\text{nom}} - y_{\text{TIPS}} = \theta + \pi$ | Break-even inflation decomposition |
| $E/P \approx l + \text{ERP}$ | Earnings yield ≈ real rate + equity premium |
| $r_{\text{CRE}} = l + \theta + \pi + \gamma + \kappa + \phi$ | CRE required return (RE-CLIP) |
| $\text{Cap rate} + g_{\text{NOI}} = r$ | Gordon CRE relationship |
| $g_{\text{real EPS, L/R}} \le g_{\text{potential GDP}}$ | Long-run earnings bound |

---

## 14. Related Notes

- [[Present Value Model]]
- [[Yield Curve]] · [[Duration]] · [[Convexity]]
- [[Taylor Rule]] · [[Neutral Real Rate]] · [[Level 2/Generated Notes/03 - Economics/Output Gap]]
- [[TIPS]] · [[Break-Even Inflation]] · [[Inflation Risk Premium]]
- [[Credit Spread]] · [[High Yield Bonds]] · [[Credit Analysis]]
- [[Consumption CAPM]] · [[Equity Risk Premium]] · [[Marginal Utility]]
- [[Business Cycle]] · [[Flight to Quality]]
- [[P/E Ratio]] · [[Shiller CAPE]] · [[Fed Model]]
- [[Commercial Real Estate]] · [[Cap Rate]] · [[Net Operating Income]] · [[REITs]]
- Practice: `Practice Questions/03 - Economics/Economics and Investment Markets/`

---

> [!quote] Final Frame
> Every headline you'll ever read — a Fed rate decision, a CPI print, an earnings report, a default headline, a REIT index move — is the economy tugging on one of the three levers: **real rates, cash flows, or risk premiums**. The levers are universal; the assets just respond differently to the same pulls. Master the pricing equation, and the rest is application.
