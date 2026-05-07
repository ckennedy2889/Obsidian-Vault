# Hedge Fund Strategies

> [!info] CFA L2 — [[Alternative investments|Alternative Investments]] | Module 4
> **Hedge Fund Strategies**
> Source: CFA Program Curriculum 2025 Level 2, Volume 8

---

## LOS (a): Classification of Hedge Fund Strategies

### The Investment Thesis

[[Hedge funds]] exist to deliver **additional [[Alpha]]** and **[[diversification]] benefits** beyond what traditional stock/bond portfolios can achieve.

### Common Characteristics of Hedge Funds

1. **Legal/Regulatory:** [[Accredited investors]] only (minimum income/net worth requirements). *Liquid alts* → [[Mutual fund]]/[[ETF]] structures for more liquid HF strategies accessible to retail investors.
2. **Flexible mandates:** Few investment constraints
3. **Large [[Investment universe|investment universe]]:** Traditional assets + [[private securities]], [[high-yield debt]], [[Distressed securities]], [[Level 2/08 - Derivatives/Derivatives]]
4. **Aggressive [[Investment style|investment style]]:** [[Short selling|Shorting]], concentration, [[Leverage]]
5. **Liberal use of [[Leverage]]:** Via loans and [[Level 2/08 - Derivatives/Derivatives]]
6. **[[Liquidity]] constraints:** [[Lock-up period|Lock-up periods]], [[liquidity gates]], exit windows
7. **Relatively high fee structure:** Management fees (1–2%) + incentive fees (10–30%)

### The Six Strategy Categories

| Category | Focus | Primary Risk | Strategies |
|---|---|---|---|
| **[[Equity strategies]]** | Equity market return and risk | Equity risk | [[Long/Short Equity]], [[Dedicated Short Bias]], [[Equity Market Neutral]] |
| **[[Event-driven strategies]]** | Corporate events | [[Event risk]] | [[Merger Arbitrage]], [[Distressed securities]] |
| **[[Relative value strategies]]** | [[Valuation|Valuation]] differences between securities | [[Credit risk]] & [[Liquidity risk]] | [[Fixed-Income Arbitrage]], [[Convertible Bond Arbitrage]] |
| **[[Opportunistic strategies]]** | Top-down, multi-asset | Varies by opportunity set | [[Global Macro]], [[Managed futures]] (CTAs) |
| **[[Specialist strategies]]** | Niche markets, specialized knowledge | Unique/esoteric risks | [[Volatility Trading]], [[Reinsurance Strategies|Reinsurance/Life Settlements]] |
| **[[Multi-manager strategies]]** | Diversified portfolio of HF strategies | Blended | [[Multi-Strategy Funds]], [[Fund-of-Funds]] |

---

## LOS (b): Equity-Related Hedge Fund Strategies

### [[Long/Short Equity]]

**The idea:** Buy stocks you think will go up (**long**), sell short stocks you think will go down (**short**). Profit from stock-picking skill on both sides.

> [!tip] Analogy
> Think of it as being a sports bettor who can bet both *for* and *against* teams. A traditional investor can only bet "for" (long-only). An L/S equity manager can also bet "against" overvalued companies.

**Key characteristics:**
- Most prevalent HF strategy (~30% of all [[Hedge funds]])
- Reliance on **fundamental research** — most managers specialize in a specific geography, sector, or style
- Typically **net long** (40–60% net long exposure) — gross exposures of 70–90% long vs. 20–50% short
- Return profiles: aim for returns roughly equivalent to long-only but with [[Standard deviation]] that is **50% lower**
- The more [[Equity Market Neutral|market-neutral]] or quantitative the strategy, the more [[Leverage]] needed to achieve meaningful returns

**Alpha source:** Stock selection defines manager skill. Market-timing ability is additive but generally secondary.

### [[Dedicated Short Bias]] / Short Selling

**The idea:** Focus on finding **overvalued** companies to [[Short selling|short sell]]. Profit when stock prices decline.

**Key characteristics:**
- **Dedicated short sellers:** 60–120% short at all times
- **Short-biased managers:** 30–60% net short, may hold some value-oriented longs as offset
- Focus on single equity stock picking (not index shorting)
- Targets: flawed business models, unsustainable debt levels, poor governance, questionable accounting
- Low [[Leverage]] (natural [[Volatility]] from short exposure is already high)

**Return profile:** Typically lower returns than most other HF strategies, but with a **negative [[Correlation]]** benefit — increasing returns when the market declines, decreasing returns when it rises.

> [!important] [[Bottom-up|Bottom-up]]up approach|[[Bottom-up|Bottom-up]] approach]] (deep-dive research). May publicly present short theses (activist [[Short selling|short selling]]) — the reputation effect of a well-known short seller publishing a report can itself move prices.

### [[Equity Market Neutral]] (EMN)

**The idea:** Take advantage of **idiosyncratic short-term [[Mispricing|mispricing]]** between securities. Hold balanced long and short equity exposures to maintain **zero (or near-zero)** net exposure to the equity market.

> [!tip] Analogy
> Imagine you're at a shoe store where two identical pairs of shoes are mispriced — one costs \$50 and the other \$70. You buy the cheap pair and sell the expensive pair. You don't care if shoe prices generally go up or down; you profit from the *gap* closing.

**Key characteristics:**
- Sources of return do **not require accepting [[Beta]] risk** — especially attractive during market weakness
- Most EMN managers are **purely quantitative** (algorithm-driven)
- [[Pairs trading|Pairs trading]] is common: long undervalued stock + short overvalued similar stock
- Requires significant [[Leverage]] to generate meaningful returns (since individual mispricings are small)
- Very attractive [[Sharpe ratio|Sharpe ratios]] and low [[Maximum drawdown]]

---

## LOS (c): Event-Driven Hedge Fund Strategies

### [[Merger Arbitrage]]

**The idea:** When Company A announces it will acquire Company B, the **target's** stock price typically jumps but remains below the [[Offer price|offer price]] (the gap is called the **"spread"**). Merger arb funds capture this spread by going long the target and (in stock deals) short the acquirer.

> [!tip] Analogy
> Think of it as selling insurance on a wedding. Most weddings happen (deal closes → you keep the premium/spread). But occasionally a wedding gets called off (deal fails → you face a large loss). Small, frequent profits with rare, large losses.

**The payoff structure:** *Long riskless bond + short [[Put option]]*
- **If deal succeeds:** You earn a small, bond-like return (the spread) — like collecting insurance premiums
- **If deal fails:** Target price crashes → large loss — like an insurance payout on a disaster

**Mechanics for a stock-for-stock deal:**
1. **Go long** the [[Target company|target company]] shares
2. **Go short** the acquirer shares (at the [[Exchange ratio|exchange ratio]])
3. **Wait** for the deal to close → spread converges to zero → profit

> [!warning] Key Risks
> - **Deal failure risk** (regulatory block, financing collapse, shareholder rejection)
> - **[[Market risk|Market risk]]** — deals are more likely to fail in market stress periods
> - **Left-[[Tail risk|tail risk]]** — losses when deals fail are much larger than the typical small gains

**The "[[White knight|White Knight]]" scenario:** If a competing bidder emerges with a higher offer, the target's price jumps *above* the original offer → creates an embedded **long [[Call option]]** payoff (unexpected upside).

See: [[Merger Arbitrage Payoff Structure]] for deep dive.

### [[Distressed securities]]

**The idea:** Invest in the debt or equity of companies that are in or near [[Bankruptcy]], [[Financial distress|financial distress]], or [[Restructuring|restructuring]]. Buy at deep discounts and profit from recovery.

> [!tip] Analogy
> Like buying a house after a flood at 50 cents on the dollar, then renovating it and selling for [[Full price|full price]]. The key skill is knowing *which* flood-damaged houses are structurally sound vs. which are beyond repair.

**Key concepts:**
- **[[Fulcrum security]]:** The security in the [[Capital structure]] that will be converted to equity in a [[Restructuring|restructuring]]. The fulcrum is where the "pain" begins — everything above it gets paid in full, everything below gets impaired.
- **[[Capital structure arbitrage]]:** Going long the fulcrum security (undervalued) and short a more senior security (less upside) to capture relative value.
- Requires deep legal and financial analysis of [[Bankruptcy|bankruptcy]] proceedings
- Returns are driven by the **[[Corporate Restructuring|corporate restructuring]] process**, not by broad market movements

**Risks:** [[Liquidity risk]] is extreme — [[Distressed securities|distressed securities]] are hard to sell during market stress, creating large [[Maximum drawdown|drawdowns]].

---

## LOS (d): Relative Value Hedge Fund Strategies

### [[Fixed-Income Arbitrage]]

**The idea:** Exploit small pricing [[Anomalies|anomalies]] between related [[fixed-income]] securities. The classic trade: buy lower-[[Liquidity]], [[Off-the-run]] [[bonds]] and sell higher-[[Liquidity|liquidity]], duration-matched, [[On-the-run]] bonds.

> [!question] Why does this work?
> [[On-the-run]] bonds (most recently issued) carry a "[[Liquidity]] premium" — investors pay extra for the convenience of holding the most liquid security. [[Off-the-run]] bonds are fundamentally equivalent but slightly cheaper. The arb fund captures this spread as it converges.

**Requires very high [[Leverage]]** because individual spreads are tiny (a few basis points). This magnifies both returns and risks.

**Risk:** In a [[Liquidity]] crisis (like 2008), the spread between [[On-the-run|on-the-run]] and [[Off-the-run|off-the-run]] bonds **widens** dramatically instead of converging → catastrophic losses with high leverage.

### [[Convertible Bond Arbitrage]]

**The idea:** Buy [[Convertible Bonds]] (bonds that can be converted to stock) and short the [[Underlying|underlying]] stock to hedge out equity risk. Profit from the embedded [[optionality]] in the [[Convertible bond|convertible bond]].

**Key concepts:**
- A [[Convertible bond]] = regular bond + embedded [[Call option]] on the stock
- The strategy isolates the option component through [[Delta hedging]] — selling shares short in proportion to the bond's sensitivity to stock price changes
- Profit from: [[Gamma]] (changes in delta), [[Volatility]] [[Mispricing|mispricing]], credit improvement, and income (coupon vs. short rebate)

**Risk:** [[Credit risk]] and [[Liquidity risk]] — [[Convertible Bonds|convertible bonds]] become very illiquid in market stress, and the [[Delta hedging|delta hedge]] may break down.

---

## LOS (e): Opportunistic Hedge Fund Strategies

### [[Global Macro]]

**The idea:** Take large, directional positions across multiple asset classes ([[Currencies|currencies]], [[bonds]], [[equities]], [[Commodities]]) based on **macroeconomic themes** and global trends.

> [!tip] Analogy
> A global macro manager is like a chess player seeing the whole board — they analyze central bank policies, [[Inflation]] trends, geopolitical events, and trade flows to predict which asset classes will move and in what direction.

**Key characteristics:**
- **Top-down** approach (start with the big picture, then find specific trades)
- Use both **discretionary** (human judgment) and **systematic** (model-driven) implementation
- Key source of returns: correctly discerning and capitalizing on **trends** in global markets
- Very low [[Correlation]] with traditional assets → excellent [[diversification]] tool
- Low [[Maximum drawdown]] → strong crisis performance

### [[Managed futures]] (CTAs — Commodity Trading Advisors)

**The idea:** Use systematic, rules-based strategies to trade [[futures contracts]] across multiple markets ([[Currencies|currencies]], [[bonds]], [[equities]], [[Commodities]]).

**Key concepts:**
- **[[Time-series momentum]]:** If an asset has been going up, bet it will continue going up (and vice versa). Also called "**trend following**."
- **[[Cross-sectional momentum]]:** Among a group of assets, go long the ones with the strongest recent performance and short the weakest.
- Most CTAs are **purely systematic/quantitative** — algorithms identify and follow trends automatically
- Very attractive [[diversification]] properties — tends to perform well in crisis periods (trends tend to be stronger during crises)

**[[Risk exposure|Risk exposure]]:** Market directionality / "trendiness" — if markets are choppy with no clear trend, CTAs struggle.

---

## LOS (f): Specialist Hedge Fund Strategies

### [[Volatility Trading]]

**The idea:** Trade [[options]] to profit from differences between **implied [[Volatility]]** (what the market *expects*) and **realized [[Volatility]]** (what *actually happens*).

**Key concepts:**
- **Long [[Volatility|volatility]]:** Buy options → profit when realized vol > implied vol (markets move more than expected)
- **Short [[Volatility|volatility]]:** Sell options → profit when realized vol < implied vol (markets are calmer than expected)
- **[[Delta hedging]]:** Continuously adjust the hedge to remain neutral to the stock price direction
- **[[Gamma]] trading:** Profit from the *change* in delta — when markets move sharply, gamma creates profits for long-vol positions

> [!important] During financial crises, long-vol strategies can maintain or even increase their [[Sharpe ratio]] — making them valuable portfolio insurance.

### [[Reinsurance Strategies]] / Life Settlements

**Reinsurance:** [[Hedge funds|Hedge funds]] act as specialized insurance companies, providing catastrophe coverage (hurricanes, earthquakes). They earn premiums from insurance companies and pay out if a disaster occurs.

**Life settlements:** Buying [[Life insurance|life insurance]] policies from elderly individuals at a discount, then collecting the death benefit. Returns are driven by mortality tables, not financial markets → very low [[Correlation]].

---

## LOS (g): Multi-Manager Hedge Fund Strategies

### [[Fund-of-Funds]] (FoF)

**The idea:** A fund that allocates capital to **multiple [[Underlying|underlying]] [[Hedge funds]]**, each running different strategies.

> [!success] Advantages
> - [[Diversification]] across strategies, managers, and risk exposures
> - Access to managers that may be closed to new investors
> - Professional manager selection and [[Due diligence|due diligence]]

> [!warning] Disadvantages
> - **Double layer of fees:** FoF charges its own management + incentive fees *on top of* the [[Underlying|underlying]] funds' fees
> - **[[Netting risk]]:** Even if some [[Underlying|underlying]] funds lose money, the profitable ones still charge incentive fees → total fees can exceed what a single fund would charge
> - **Dilution of returns:** Too many managers can lead to average, index-like performance

### [[Multi-Strategy Funds]]

**The idea:** A single fund with **multiple trading teams**, each running a different strategy under one roof.

> [!success] Advantages over FoF
> - **Single fee layer** (no double fee problem)
> - **Dynamic capital allocation:** The CIO can quickly shift capital from underperforming teams to better opportunities
> - **Centralized [[Risk management|risk management]]:** Better oversight and risk controls across all strategies
> - **Netting benefit:** Gains and losses are netted *within* the fund before incentive fees are calculated

---

## LOS (h): Conditional Factor Risk Model

The conditional factor risk model evaluates [[Hedge funds|hedge fund]] exposures by allowing [[Factor sensitivities|factor sensitivities]] to **change during crisis periods**.

$$R_{HF,t} = \alpha + \beta_1 \cdot \text{EQUITY}_t + \beta_2 \cdot \text{BOND}_t + \beta_3 \cdot \text{CMDTY}_t + \beta_4 \cdot D_t \cdot \text{EQUITY}_t + \beta_5 \cdot D_t \cdot \text{BOND}_t + \epsilon_t$$

Where:
- $R_{HF,t}$ = [[Hedge funds|hedge fund]] return in period $t$
- $\text{EQUITY}_t$, $\text{BOND}_t$, $\text{CMDTY}_t$ = returns on equity, bond, and commodity factors
- $D_t$ = **[[Dummy variable|dummy variable]]** that equals **1** during crisis periods and **0** otherwise
- $\beta_4$, $\beta_5$ = the *additional* factor exposure that appears only during crises

> [!question] Why the [[Dummy variable|dummy variable]]?
> Many [[Hedge funds|hedge fund]] strategies behave differently during normal times vs. crisis times. For example, [[Merger Arbitrage]] may have low equity beta in normal markets but become highly correlated with stocks when markets crash (because deal failures spike). The [[Dummy variable|dummy variable]] $D_t$ captures this **regime shift**.

> [!important] Key Insight
> Strategies like [[Merger Arbitrage]], [[Distressed securities]], and [[Convertible Bond Arbitrage]] tend to show **increased equity and credit sensitivity during crises** — exactly when you don't want it. Conversely, [[Global Macro]], [[Managed futures]], and [[Equity Market Neutral]] tend to show **stable or reduced** sensitivity during crises — providing true [[diversification]].

---

## LOS (i): Portfolio Contribution of Hedge Fund Strategies

### Adding a 20% Hedge Fund Allocation to a 60/40 Portfolio

When combining [[Hedge funds]] with a traditional 60% equity / 40% bond portfolio, the key metrics to evaluate are:

| Metric | What It Measures | Best HF Strategies |
|---|---|---|
| **[[Sharpe ratio]]** | Risk-adjusted return (penalizes all [[Volatility]]) | [[Managed futures]], [[Fixed-Income Arbitrage]], [[Distressed securities]], [[Global Macro]] |
| **[[Sortino ratio]]** | Risk-adjusted return (penalizes only *downside* [[Volatility]]) | [[Equity Market Neutral]], [[Managed futures]], L/S Equity, Event-Driven |
| **[[Maximum drawdown]]** | Largest peak-to-trough decline | [[Global Macro]], [[Managed futures]], [[Merger Arbitrage]], [[Equity Market Neutral]] (smallest drawdowns) |

> [!success] Best Portfolio Diversifiers
> Strategies with the **smallest [[Maximum drawdown]]** when combined with a traditional portfolio:
> - [[Global Macro]]
> - [[Managed futures]] (systematic futures/CTAs)
> - [[Merger Arbitrage]]
> - [[Equity Market Neutral]]
>
> These strategies tend to have **low serial [[Autocorrelation|autocorrelation]]** (good [[Liquidity]]) and **low equity/credit exposure during crises**.

> [!warning] Worst Portfolio Diversifiers During Crises
> - [[Long/Short Equity]] (still carries significant equity beta)
> - [[Distressed securities]] / Event-Driven ([[Credit risk|credit risk]] surges in crises)
> - [[Convertible Bond Arbitrage]] ([[Liquidity]] dries up)

---

## Key Formulas Summary

| Formula | Expression |
|---|---|
| Conditional Factor Model | $R_{HF} = \alpha + \beta_1 \text{EQ} + \beta_2 \text{BOND} + \beta_4 D \cdot \text{EQ} + \epsilon$ |
| [[Sharpe ratio]] | $\frac{R_p - R_f}{\sigma_p}$ |
| [[Sortino ratio]] | $\frac{R_p - R_{\text{min}}}{\sigma_{\text{downside}}}$ |
| [[Maximum drawdown]] | Largest peak-to-trough decline |

---

*See also: [[Merger Arbitrage Payoff Structure]] | [[Commodities and Commodity Derivatives]] | [[Real Estate - Public Securities (REITs, REOCs, NAVPS)]] | [[Real Estate - Private Investment and Valuation]]*
