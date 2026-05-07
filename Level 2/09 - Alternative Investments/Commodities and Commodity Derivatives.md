# Commodities and Commodity Derivatives

> [!info] CFA L2 — [[Alternative investments|Alternative Investments]] | Module 1
> **Introduction to [[Commodities|Commodities]] and Commodity [[Derivatives|Derivatives]]**
> Source: CFA Program Curriculum 2025 Level 2, Volume 8

---

## LOS (a)–(b): Commodity Sectors and Life Cycles

### The Five Major Commodity Sectors

[[Commodities]] are physical assets — unlike stocks or bonds, they are *things* you can touch, store, eat, or burn. They fall into five broad sectors:

| Sector | Examples | Key Characteristics |
|---|---|---|
| **Energy** | Crude oil, natural gas, gasoline | Consumed in real-time, minimal storage, geopolitical sensitivity |
| **Industrial Metals** | Copper, aluminum, zinc | Long life cycle, sensitive to global manufacturing/construction |
| **Precious Metals** | Gold, silver, platinum | [[Store of value|Store of value]], currency alternative, perpetual storage |
| **Agriculture** | Wheat, corn, soybeans, coffee | Seasonal production cycles, weather-[[Dependent|dependent]] |
| **Livestock** | Cattle, hogs | Biological life cycle, perishable, unique storage challenges |

### Life Cycle Differences

> [!tip] Why Life Cycles Matter
> A **short life cycle** (like livestock or agriculture) allows for relatively rapid adjustment to outside events — if corn prices spike, farmers can plant more next season. A **long life cycle** (like a copper mine or oil field) limits the market's ability to react — it can take 5–10 years to bring new supply online.

---

## LOS (c): Valuation — Commodities vs. Equities and Bonds

> [!important] The Key Distinction
> [[Equities]] and [[bonds]] are **financial assets** — they are valued based on **expected future cash flows** ([[dividends]], [[coupon payments|coupons]], earnings).
>
> [[Commodities]] are **physical assets** — they are valued based on a **discounted forecast of future possible prices**, which incorporates [[supply and demand]], storage costs, transportation costs, and geopolitical factors.
>
> [[Commodities|Commodities]] do **not** generate cash flows on their own (a barrel of oil sitting in a tank earns nothing). Their "return" comes entirely from price changes and the mechanics of [[futures contracts]].

---

## LOS (d): Types of Market Participants

There are three types of participants in [[commodity futures]] markets:

1. **Informed investors / Hedgers:** Producers (farmers, oil companies) and consumers (airlines, food manufacturers) who trade to hedge their exposure to price risk. They are "informed" because they understand the physical commodity markets deeply.
2. **Speculators:** Traders who take on price risk in hopes of earning a profit. They provide [[Liquidity]] and take the other side of hedgers' trades.
3. **[[Arbitrageurs|Arbitrageurs]]:** Traders who exploit mispricings between related instruments (e.g., between [[Spot price|spot]] and [[Futures price|futures prices]], or between different delivery locations). They help keep markets efficient.

---

## LOS (e): Spot vs. Futures Prices — [[Contango]] and [[Backwardation]]

### Core Definitions

**[[Spot price]]:** The current price to deliver or purchase a physical commodity at a specific location, right now.

**[[Futures price]]:** An exchange-based price agreed on today to deliver or receive a defined quantity (and often quality) of a commodity at a **future date**.

**[[Basis]]:** The difference between [[Spot price|spot]] and [[Futures price|futures]] prices.

$$\text{Basis} = \text{Spot Price} - \text{Futures Price}$$

### The Two Market States

| State | Definition | Basis | Visual |
|---|---|---|---|
| **[[Backwardation]]** | [[Spot price]] > [[Futures price]] | Positive | Futures curve slopes **downward** |
| **[[Contango]]** | [[Spot price]] < [[Futures price]] | Negative | Futures curve slopes **upward** |

> [!tip] Analogy — Concert Tickets
> Think of [[Backwardation]] as concert tickets being more expensive *today* (high demand now) than tickets for a show next month. [[Contango]] is like early-bird pricing — you pay *more* to get the tickets at the last minute (delivery now) vs. buying in advance (futures).

> [!important] Key Insight
> Periods of either [[Backwardation]] or [[Contango]] do **not** persist indefinitely. Markets shift between the two states based on evolving supply and demand dynamics.

---

## LOS (f): Theories of Commodity Futures Returns

### Theory 1: Insurance Theory (Keynes) — Theory of Normal Backwardation

**The idea:** Commodity producers who are **long** the physical good are motivated to **sell** futures to hedge their production price risk. By selling futures, they push [[Futures price|futures prices]] *below* the expected future [[Spot price]].

**Why?** The producer is essentially buying "price insurance" — they accept a lower locked-in price in exchange for certainty. The speculator on the other side earns a premium for *providing* that insurance.

**Implication:** [[Backwardation]] is the "normal" state. Futures prices are below expected [[Spot prices|spot prices]], so long futures holders earn a positive expected return as futures converge upward toward spot.

### Theory 2: Hedging Pressure Hypothesis

**The idea:** Both producers *and* consumers hedge:
- **Producers** (short hedgers) sell futures to lock in selling prices → pushes futures prices down → [[Backwardation]]
- **Consumers** (long hedgers) buy futures to lock in purchase prices → pushes futures prices up → [[Contango]]

**The outcome depends on which side dominates:**

| Condition | Result |
|---|---|
| Producers > Consumers (more selling pressure) | [[Backwardation]] |
| Consumers > Producers (more buying pressure) | [[Contango]] |
| Producers ≈ Consumers | Flat curve |

### Theory 3: Theory of Storage

**The idea:** [[Futures price|Futures prices]] and [[Spot price|spot prices]] are linked through the economics of *storing* the physical commodity:

$$\text{Futures Price} = \text{Spot Price} + \text{Storage Costs} - \text{Convenience Yield}$$

Where:
- **Storage costs** = rent for warehouse, insurance, spoilage, etc. These push futures prices *above* spot ([[Contango]])
- **[[Convenience yield]]** = the non-monetary benefit of physically holding the commodity (e.g., a refinery holding crude oil avoids production shutdowns). This pushes futures prices *below* spot ([[Backwardation]])

> [!question] When is [[Convenience yield|convenience yield]] high?
> When inventories are **low** — having the physical commodity in hand is extremely valuable when supplies are scarce. When inventories are **high**, [[Convenience yield|convenience yield]] is low because there's plenty of supply available.

---

## LOS (g): Components of Total Return for a Fully Collateralized Commodity Futures Contract

$$\boxed{\text{Total Return} = \text{Price Return} + \text{Roll Return} + \text{Collateral Return}}$$

### Component 1: Price Return (Spot Yield)

The change in the commodity [[Futures price|futures contract]] price, generally the front-month contract:

$$\text{Price Return} = \frac{\text{Current Price} - \text{Previous Price}}{\text{Previous Price}}$$

### Component 2: [[Roll return]] (Roll Yield)

When a [[futures contracts|futures contract]] approaches expiration, you must "roll" your position — sell the expiring contract and buy the next one. The price difference between these two contracts creates the [[Roll return]].

$$\text{Roll Return} = \frac{\text{Near-term Futures Price} - \text{Farther-term Futures Price}}{\text{Near-term Futures Price}} \times \text{\% of Position Rolled}$$

> [!tip] The Concert Ticket Analogy for [[Roll return|Roll Return]]
> Imagine you have a concert ticket for tonight's show worth \$100. You need to exchange it for a ticket to next month's show. In [[Backwardation]] (tonight's show is more popular), next month's ticket only costs \$80 — you "pocket" \$20 worth of value when you roll. That's a **positive** [[Roll return|roll return]].
>
> In [[Contango]] (next month's show is more popular), the new ticket costs \$110 — you *lose* \$10 of value when rolling. That's a **negative** [[Roll return|roll return]].

> [!warning] [[Roll return|Roll Return]] Is Not Independently Capturable
> [[Roll return]] is an *accounting decomposition* — you cannot construct a portfolio of *only* roll returns. It replicates a portion of the [[Total return|total return]] calculation for a fully collateralized index.

### Component 3: Collateral Return (Collateral Yield)

The yield earned on the [[collateral]] (typically [[Treasury bills]] or cash) posted to maintain the [[futures contracts|futures position]]:

$$\text{Collateral Return} = \text{Risk-free Rate} \times \text{Collateral Percentage}$$

### Worked Example — Total Return Calculation

**Given:**
- [[Price return|Price return]] = 5%
- [[Roll return]] = 2.5%
- Held for one year with 100% collateral at [[risk-free rate]] = 2%

$$\text{Total Return} = 5\% + 2.5\% + (2\% \times 100\%) = 9.5\%$$

### Worked Example — Complete Total Return with Roll Calculation

**Given:**
- Current price: 877.0; Previous price: 865.0
- Near-term futures: 877.0; Farther-term futures: 883.0
- 100% of position rolled; 3-month holding period; annual [[risk-free rate]] = 0.60%

**Step 1: [[Price return|Price Return]]**

$$\frac{877.0 - 865.0}{865.0} = 1.387\%$$

**Step 2: [[Roll return]]**

$$\frac{877.0 - 883.0}{877.0} \times 100\% = -0.684\%$$

(Negative because we're in [[Contango]] — the farther-term contract is more expensive)

**Step 3: [[Collateral return|Collateral Return]]**

$$\frac{3}{12} \times 0.60\% = 0.15\%$$

**Step 4: [[Total return|Total Return]]**

$$1.387\% - 0.684\% + 0.15\% = 0.853\%$$

---

## LOS (h): Roll Return in Contango vs. Backwardation

| Feature | [[Backwardation]] | [[Contango]] |
|---|---|---|
| Futures curve | Slopes **downward** | Slopes **upward** |
| Near contract vs. far contract | Near > Far | Near < Far |
| Rolling requires | Buying **more** contracts | Buying **fewer** contracts |
| [[Roll return]] | **Positive** | **Negative** |
| Why | You sell expensive (near) and buy cheap (far) | You sell cheap (near) and buy expensive (far) |

### Rolling Mechanics Example — Backwardation

An investor has £110 of exposure in wheat futures. The near contract is worth £10/contract (11 contracts), but the far contract is worth only £9/contract.

To maintain £110 exposure: $\frac{110}{9} \approx 12$ contracts needed → must **buy 1 additional contract**

The investor gets "more commodity" for the same money — this is the **positive [[Roll return]]**.

### Rolling Mechanics Example — Contango

An investor has £108 of exposure in gasoline futures. The near contract is worth £9/contract (12 contracts), but the far contract is worth £10/contract.

To maintain £108 exposure: $\frac{108}{10} \approx 11$ contracts needed → must **sell 1 extra contract**

The investor gets "less commodity" for the same money — this is the **negative [[Roll return]]**.

### Historical Roll Return Data (S&P GSCI, 1970–2019)

| Sector | Mean Annual Roll Return |
|---|---|
| S&P GSCI Total | −1.3% |
| Energy | −1.5% |
| Industrial Metals | −1.3% |
| Agriculture | −4.5% |
| Livestock | −1.1% |
| Precious Metals | −5.1% |
| Softs | −5.5% |

> [!warning] Key Takeaway
> Most commodity sectors exhibit **negative** mean [[Roll return|roll returns]] historically — meaning [[Contango]] has been more common than [[Backwardation]] for most [[Commodities|commodities]]. Only energy has had a statistical possibility of positive mean roll return, and even that diminished after 2010 with the shale oil revolution.

---

## LOS (i): Commodity Swaps

[[Commodity swaps]] are used to obtain or modify exposure to [[Commodities]] without trading in the physical or [[futures contracts|futures]] markets directly.

| Swap Type | What It Does |
|---|---|
| **[[Total return swap]]** | One party pays the [[Total return|total return]] of a commodity index; the other pays a fixed or floating rate. Monthly [[Cash settlement|cash settlement]]nt|settlement]] based on index performance. |
| **[[Excess return swap]]** | Like a [[Total return swap|total return swap]] but excludes the [[Collateral return]] — only the [[Price return|price return]] + [[Roll return]] component. |
| **[[Basis swap]]** | [[Exchanges|Exchanges]] the price difference between two related [[Commodities|commodities]] (e.g., WTI crude vs. Brent crude) or two delivery locations. |
| **[[Variance swap]]** | Pays out based on the difference between realized [[Variance]] and a pre-agreed strike variance. Used for [[Volatility]] exposure. |
| **[[Volatility swap]]** | Similar to variance swap but based on realized [[Volatility]] ([[Standard deviation|standard deviation]]) rather than variance. |

### Worked Example — Total Return Swap Payment

**Given:**
- [[Total return swap]] on [[S&P GSCI]], notional = \$25,000,000
- Index level May: 2,582.23; Index level June: 2,525.21

**Step 1: Calculate return**

$$\frac{2{,}525.21 - 2{,}582.23}{2{,}582.23} = -2.2082\%$$

**Step 2: Calculate payment**

$$\$25{,}000{,}000 \times (-2.2082\%) = -\$552{,}042.23$$

Since the return is **negative**, the **swap buyer (long)** must pay the seller \$552,042.

---

## LOS (j): Commodity Index Construction and Its Effect on Returns

Different [[commodity index|commodity indexes]] use different methodologies, which affects returns:

| Feature | [[S&P GSCI]] | [[Bloomberg Commodity Index]] (BCOM) | [[DBIQ Optimum Yield]] |
|---|---|---|---|
| **Weighting** | World production-weighted | 2/3 [[Liquidity|liquidity]], 1/3 production (with caps) | Rules-based optimum yield |
| **Energy weight** | ~60% (heavily energy) | ~30% (more balanced) | Varies |
| **Rolling method** | Fixed 5-day roll into next month | Fixed roll schedule | Selects contract with best [[Roll return]] |
| **[[Rebalancing|Rebalancing]]** | Annual | Annual | Periodic |
| **Result** | Most energy-sensitive | More diversified | Aims to minimize [[Contango]] drag |

> [!important] Key Insight
> The construction methodology — especially **weighting** and **rolling rules** — can significantly impact index returns. An index that rolls into the contract with the best [[Roll return]] (like DBIQ) can outperform one that mechanically rolls into the next month (like S&P GSCI), particularly in [[Contango]] markets.

---

## Key Formulas Summary

| Formula | Expression |
|---|---|
| [[Basis]] | $\text{Spot} - \text{Futures}$ |
| Theory of Storage | $F = S + \text{Storage} - \text{Convenience Yield}$ |
| [[Price return|Price Return]] | $\frac{P_{\text{current}} - P_{\text{previous}}}{P_{\text{previous}}}$ |
| [[Roll return]] | $\frac{F_{\text{near}} - F_{\text{far}}}{F_{\text{near}}} \times \text{\% rolled}$ |
| [[Collateral return|Collateral Return]] | $r_f \times \text{Collateral \%}$ |
| [[Total return|Total Return]] | $\text{Price} + \text{Roll} + \text{Collateral}$ |

---

*See also: [[Real Estate - Public Securities (REITs, REOCs, NAVPS)]] | [[Real Estate - Private Investment and Valuation]] | [[Hedge Fund Strategies]]*
