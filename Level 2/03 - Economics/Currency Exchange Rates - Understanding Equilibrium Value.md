---
title: "Currency Exchange Rates - Understanding Equilibrium Value"
subject: "Economics"
tags: [CFA-L2, economics]
aliases: []
---

## Economic GrowthLearning Outcomes: Economic Growth

Paul R. Kutasovic, PhD, CFA.

Paul R. Kutasovic, PhD, CFA, is at New York Institute of [[Technology|Technology]] (USA).

The candidate should be able to:

- compare factors favoring and limiting [[Economic growth|economic growth]] in developed and developing economies
- describe the relation between the long-run rate of stock market appreciation and the [[Sustainable growth rate|sustainable growth rate]] of the economy
- explain why [[Potential GDP|potential GDP]] and its growth rate matter for equity and fixed income investors
- contrast [[Capital Deepening|capital deepening]]ng investment|[[Capital Deepening|capital deepening]] investment]] and technological progress and explain how each affects [[Economic growth|economic growth]] and [[Labor productivity|labor productivity]]ty|productivity]]
- demonstrate forecasting [[Potential GDP|potential GDP]] based on [[Growth Accounting|growth accounting]] relations
- explain how natural resources affect [[Economic growth|economic growth]] and evaluate the argument that limited availability of natural resources constrains [[Economic growth|economic growth]]
- explain how demographics, immigration, and [[Labor force|labor force]] participation affect the rate and sustainability of economic growth
- explain how investment in physical capital, [[Human capital|human capital]], and technological development affects economic growth
- compare [[Classical growth theory|classical growth theory]], [[Neoclassical growth theory|neoclassical growth theory]], and [[Endogenous growth theory|endogenous growth theory]]
- explain and evaluate [[Convergence|convergence]]ce Hypotheses|[[Convergence|convergence]] hypotheses]]
- describe the economic rationale for governments to provide incentives to private investment in [[Technology|technology]] and knowledge
- describe the expected impact of removing trade barriers on capital investment and profits, employment and wages, and growth in the economies involved# Currency Exchange Rates: Understanding [[Equilibrium|Equilibrium]] Value

> **CFA Level II | Economics | Learning Module 1**
> This guide covers the tools used to understand long-run [[Equilibrium|equilibrium]] exchange rate values — not to predict rates, but to assess [[Fair value|fair value]] and manage risk exposures.

---

## Table of Contents

1. [[#Foreign Exchange Market Concepts]]
2. [[#Bid-Offer Spreads]]
3. [[#Arbitrage Constraints on Spot Exchange Rate Quotes]]
4. [[#Triangular Arbitrage]]
5. [[#Forward Markets]]
6. [[#Forward Premium and Discount]]
7. [[#Mark-to-Market Value of a Forward Contract]]
8. [[#International Parity Conditions Overview]]
9. [[#Covered interest rate parity (CIP)]]
10. [[#uncovered interest rate parity (UIP)]]
11. [[#forward rate Parity]]
12. [[#purchasing power parity (PPP)]]
13. [[#The Fisher Effect and International Fisher Effect]]
14. [[#Tying All Parity Conditions Together]]
15. [[#The Carry Trade]]
16. [[#balance of payments Flows]]
17. [[#Capital Flows]]
18. [[#Monetary and Fiscal Policies]]
19. [[#The Mundell-Fleming Model]]
20. [[#Monetary Models of Exchange Rate Determination]]
21. [[#The Portfolio Balance Approach]]
22. [[#Exchange Rate Management — Intervention and Controls]]
23. [[#Warning Signs of a Currency Crisis]]

---

## Foreign Exchange Market Concepts

### What is an Exchange Rate?

An [[exchange rate]] is simply the price of one currency expressed in terms of another. Think of it like a price tag at a store — except instead of pricing a product in dollars, you're pricing one currency in terms of another.

**Notation: P/B (Price/Base)**

The CFA curriculum uses the convention **P/B**, which means:
- **B** = [[Base currency]] (the currency you're buying/selling — it sits in the denominator)
- **P** = [[Price currency]] (the currency used to express the price — it sits in the numerator)

> **Analogy:** Think of it like buying apples. If apples cost \$3 each, the "exchange rate" is \$3/apple. The apple is the **base** (what you're buying), and the dollar is the **price** (what you're paying with).

**Example:** A USD/EUR rate of 1.1650 means:
- 1 EUR (base) costs 1.1650 USD (price)
- You pay 1.1650 US dollars to buy 1 euro

### f/d Notation

The textbook also uses **f/d (foreign/domestic)** notation for theoretical explanations. Here:
- **d** = [[Domestic currency]] (the investor's [[Home currency|home currency]], placed in the base/denominator)
- **f** = [[Foreign currency]] (placed in the price/numerator)

> **Why two notations?** P/B is what professionals use in real markets (no one argues about what's "foreign"). f/d is convenient for theory because it makes the investor's perspective clearer — "how many units of [[Foreign currency|foreign currency]] does my one domestic unit buy?"

### Spot Rate

The [[spot exchange rate]] is the rate for **immediate** delivery — technically [[Settlement|settlement]] on the second business day after the trade date (**T + 2**). The exception is CAD/USD, which settles T + 1.

> **Real-world example:** You're at an airport currency exchange counter. The rate on the board is essentially a [[Spot rate|spot rate]] — the price to exchange currency right now.

---

## Bid-Offer Spreads

### What is a Bid-Offer Spread?

When a [[Dealer]] quotes an exchange rate, they don't give you one number — they give you two:

- **[[Bid price]]**: The price at which the dealer is willing to **buy** the base currency from you
- **[[Offer price]]** (also called **[[Ask price|ask price]]**): The price at which the dealer is willing to **sell** the base currency to you

The **[[bid-offer spread]]** = Offer − Bid. This spread is how dealers make money.

> **Analogy:** Think of a used car dealer. They'll buy your car for \$15,000 (their bid) and sell it for \$17,000 (their offer). The \$2,000 difference is their [[Profit margin|profit margin]]. FX dealers work the same way, just with much thinner margins.

**Key rules:**
1. The offer is **always** higher than the bid
2. The person requesting the quote can choose to "**hit the bid**" (sell the base) or "**pay the offer**" (buy the base)

### What is a Pip?

A **[[pip]]** is the smallest standard unit of price movement:
- For most [[Currencies|currencies]]: the 4th decimal place (0.0001)
- For JPY quotes: the 2nd decimal place (0.01)

**Example:** If USD/EUR moves from 1.1649 to 1.1651, it moved **2 pips**.

### The Interbank Market

The [[Interbank market]] is the global wholesale network where professional dealers trade [[Currencies|currencies]] among themselves, typically in lots of at least 1 million units. Spreads here are tightest. Dealers then mark up these spreads for their clients.

**Example of dealer profit:**
- [[Interbank market|Interbank market]]: USD/EUR = 1.1649/1.1651 (2 pips wide)
- Dealer quotes client: USD/EUR = 1.1648/1.1652 (4 pips wide)
- Client sells EUR (hits dealer's bid at 1.1648)
- Dealer covers in interbank (hits interbank bid at 1.1649)
- Dealer profit: 1.1649 − 1.1648 = **0.0001 USD per EUR** = USD 100 per EUR 1 million

### Factors Affecting the Bid-Offer Spread

**Three main factors determine spread width:**

| Factor | Effect on Spread |
|--------|-----------------|
| **[[Interbank market|Interbank market]] [[Liquidity|liquidity]]** | More liquid = tighter spreads |
| **Transaction size** | Very large or very small = wider spreads |
| **Dealer-client relationship** | Valued clients get tighter spreads |

**[[Liquidity|Liquidity]] is driven by:**

1. **Currency pair involved**: Major pairs (USD/EUR, JPY/USD, USD/GBP) have the tightest spreads because they're traded most heavily. Obscure cross rates (e.g., MXN/CHF) have wider spreads.

2. **Time of day**: Spreads are tightest when London and New York are both open (roughly 8:00 AM – 11:00 AM New York time). This is when the most dealers and volume are active. Spreads widen during off-hours (e.g., late New York afternoon before Asia opens).

3. **Market [[Volatility|volatility]]**: During market stress (wars, crashes, surprise data releases), dealers widen spreads to protect themselves from getting caught on the wrong side of sudden moves.

> **Real-world example:** If you try to exchange Thai baht for Swiss francs at 3 AM Tokyo time during a geopolitical crisis, expect a very wide spread. If you exchange USD for EUR at 10 AM in New York on a calm day, expect a razor-thin spread.

---

## Arbitrage Constraints on Spot Exchange Rate Quotes

### What is Arbitrage?

[[Arbitrage]] is the simultaneous buying and selling of the same asset in different markets to profit from a price discrepancy — with **zero risk**. In FX markets, [[Arbitrage|arbitrage]] keeps prices [[Consistent|consistent]].

### Two Arbitrage Constraints

**Constraint 1: Direct Consistency**
A dealer's bid cannot exceed the current interbank offer, and a dealer's offer cannot be below the current interbank bid. Otherwise, traders buy cheap and sell dear instantly.

> **Example:** If the [[Interbank market|interbank market]] is 1.1649/1.1651 for USD/EUR, and a dealer quotes 1.1652/1.1654, then anyone can:
> - Buy EUR in interbank at 1.1651 (pay the interbank offer)
> - Sell EUR to the dealer at 1.1652 (hit the dealer's bid)
> - **Riskless profit: 1 pip per EUR**

**Constraint 2: Cross-Rate Consistency ([[Triangular Arbitrage]])**
Exchange rates must be [[Consistent|consistent]] across currency pairs. If you can trade A/B and C/B, the implied A/C cross rate must match the actual A/C quote.

---

## Triangular Arbitrage

### What is Triangular Arbitrage?

[[Triangular Arbitrage]] exploits pricing inconsistencies among **three** [[Currencies|currencies]]. If the cross rate implied by two currency pairs doesn't match a dealer's direct quote for that cross rate, you can trade in a "triangle" to lock in a riskless profit.

### How to Calculate an Implied Cross Rate

The key formula for cross rates:

$$\frac{A}{C} = \frac{A}{B} \times \frac{B}{C}$$

> **In plain words:** To get the exchange rate between [[Currencies|currencies]] A and C, multiply the A/B rate by the B/C rate. The B's "cancel out" like fractions.

**Incorporating bid-offer rates:**
- To get the cross-rate **bid**, multiply the **bids** of the component pairs
- To get the cross-rate **offer**, multiply the **offers** of the component pairs

> **Why?** When you're buying at the bid, you want the cheapest available [[Combination|combination]]. When selling at the offer, you need the most expensive.

### When You Need to Invert

Sometimes the quotes you're given don't line up algebraically. You may need to **invert** one quote.

**Inversion rule:**
$$\frac{B}{A}_{bid} = \frac{1}{\left(\frac{A}{B}\right)_{offer}}$$

$$\frac{B}{A}_{offer} = \frac{1}{\left(\frac{A}{B}\right)_{bid}}$$

> **Why do bid and offer swap when you invert?** When you invert a quote, buying becomes selling and vice versa. The bid for one direction is the inverse of the offer in the other.

### Worked Example: Triangular Arbitrage

**Given interbank quotes:**
- USD/EUR: 1.1649/1.1651
- JPY/USD: 105.39/105.41

**Step 1: Calculate the implied JPY/EUR cross rate.**

$$\frac{JPY}{EUR} = \frac{JPY}{USD} \times \frac{USD}{EUR}$$

- **Bid:** $105.39 \times 1.1649 = 122.77$
- **Offer:** $105.41 \times 1.1651 = 122.81$

**Implied interbank JPY/EUR = 122.77/122.81**

**Step 2: Compare with a dealer's quote.**

Suppose a dealer quotes JPY/EUR = 122.75/122.79.

- Dealer's offer (122.79) < Interbank bid (122.77)? **No** (122.79 > 122.77)
- Dealer's bid (122.75) < Interbank bid (122.77)? **Yes**
- Dealer's offer (122.79) < Interbank implied offer (122.81)? **Yes**

Since the dealer's offer is **below** the interbank bid (wait — let me re-check: 122.79 vs. 122.77. The dealer's offer is 122.79 which is above the interbank bid of 122.77), so no violation here. Let me check the other direction:

If a dealer quoted **79.81/79.83** in JPY/CAD when the interbank implied rate is **79.84/79.86**:
- The dealer's **offer** (79.83) is **below** the interbank **bid** (79.84)
- This means: **Buy CAD from the dealer at 79.83, sell it in the interbank at 79.84**
- **Profit: JPY 0.01 per CAD**

---

## Forward Markets

### What is a Forward Contract?

A [[Forward contract]] is an agreement to exchange one currency for another at a **future date** at an exchange rate agreed upon **today**. Any settlement beyond T + 2 is a forward.

> **Real-world example:** A Japanese car manufacturer knows it will receive USD 50 million in 6 months from US sales. To eliminate currency risk, it enters a [[Forward contract|forward contract]] today to sell those USD for JPY at a locked-in rate. No matter what happens to exchange rates over the next 6 months, the company knows exactly how many yen it will receive.

### The Logic Behind Forward Rates

Forward rates aren't forecasts — they're determined by a **[[No-arbitrage pricing|no-arbitrage]]** relationship. Here's the core idea:

An investor has 1 unit of [[Domestic currency|domestic currency]] and two choices for a 1-year investment:

**Option A (Invest domestically):**
```
Today                          1 Year Later
  1 unit domestic currency ──→  (1 + id) units domestic currency
```

**Option B (Invest abroad, hedged):**
```
Today                                              1 Year Later
  1 unit domestic    Convert at    Invest at     Convert back
  currency        ──→  Sf/d    ──→  (1+if)   ──→  at 1/Ff/d
```

Result of Option B: $S_{f/d} \times (1 + i_f) \times \frac{1}{F_{f/d}}$

**Because both options are risk-free, they must give the same return** (otherwise, you'd borrow in the cheaper one and invest in the dearer one for a riskless profit). Setting them equal:

$$(1 + i_d) = S_{f/d} \times (1 + i_f) \times \frac{1}{F_{f/d}}$$

---

## Covered Interest Rate Parity (CIP)

### The Formula

Rearranging the no-arbitrage condition above gives us the **[[Covered interest rate parity]]** formula:

$$\boxed{F_{f/d} = S_{f/d} \times \frac{1 + i_f \left[\frac{Actual}{360}\right]}{1 + i_d \left[\frac{Actual}{360}\right]}}$$

**What each variable means:**

| Variable | Meaning | Why It's There |
|----------|---------|---------------|
| $F_{f/d}$ | [[Forward exchange rate]] (foreign per domestic) | This is what we're solving for |
| $S_{f/d}$ | [[Spot exchange rate]] (foreign per domestic) | Starting point — today's price |
| $i_f$ | [[Foreign risk-free rate]] (annualized) | Interest earned in the foreign market |
| $i_d$ | [[Domestic risk-free rate]] (annualized) | Interest earned at home |
| $\frac{Actual}{360}$ | [[Day count fraction]] | Adjusts annualized rates to the actual investment period |

**In plain English:** The forward rate equals the spot rate multiplied by the ratio of what you'd earn in the foreign market to what you'd earn in the domestic market. If foreign rates are higher, the foreign currency trades at a **forward discount** (it'll be cheaper in the future to compensate for the higher interest).

In **P/B notation** (used on the exam):

$$\boxed{F_{P/B} = S_{P/B} \times \frac{1 + i_P \left[\frac{Actual}{360}\right]}{1 + i_B \left[\frac{Actual}{360}\right]}}$$

> **Memory trick:** The **price currency rate** goes on top, the **base currency rate** goes on the bottom. "Price on top, Base on bottom" — just like the exchange rate itself (P/B).

### Why CIP Must Hold

CIP is enforced by **arbitrage**. If it didn't hold, you could:
1. Borrow in the cheap currency
2. Convert to the expensive currency at spot
3. Invest at the higher rate
4. Lock in the exchange rate back with a forward
5. Pocket a riskless profit

Traders with computers do this automatically in milliseconds, so any deviation is instantly corrected.

> **Key exam point:** CIP is the **only** parity condition enforced by arbitrage. All others are theoretical ideals.

---

## Forward Premium and Discount

### The Formula

$$\boxed{F_{f/d} - S_{f/d} = S_{f/d} \times \frac{\left[\frac{Actual}{360}\right]}{1 + i_d\left[\frac{Actual}{360}\right]} \times (i_f - i_d)}$$

**In plain English:** The forward premium/discount equals the spot rate scaled by the interest rate differential and the time period.

**Key insight:**
- If $i_f > i_d$ → $F_{f/d} > S_{f/d}$ → The **domestic currency** trades at a **forward premium** (it's more expensive in the forward market because it earns less interest)
- If $i_f < i_d$ → $F_{f/d} < S_{f/d}$ → The **domestic currency** trades at a **forward discount**

> **Analogy:** Imagine two savings accounts. Account A earns 5% and Account B earns 2%. To prevent arbitrage, the currency of Account A must be expected to **lose value** over time. The forward rate bakes in this compensation so that both investments yield the same hedged return.

### Forward Points

In practice, forward rates are quoted as **[[forward points]]** — the difference between the forward rate and the spot rate, scaled to match the last decimal place of the spot quote.

**To convert points to a rate:**
- For most currencies: divide points by **10,000**
- For JPY: divide points by **100**

Then add to the spot rate.

**Example from Exhibit 1:**

| Maturity | Forward Points (bid/offer) |
|----------|--------------------------|
| Spot USD/EUR | 1.1649/1.1651 |
| 3 months | −15.9/−15.3 |

Three-month forward bid = $1.1649 + \frac{-15.9}{10,000} = 1.16331$

**Key observations:**
- Negative points → base currency at a forward **discount** (it's the "high-yield" currency)
- The offer is always larger than the bid (even when both are negative: −5.6 < −5.1, so −5.1 is "larger")
- Longer terms → more forward points (the interest differential accumulates)

### Worked Example: Forward Premium/Discount

**Given:**
- Spot CAD/AUD = 0.9000
- 270-day MRR (AUD) = 1.47% (AUD is the **base**)
- 270-day MRR (CAD) = 0.41% (CAD is the **price**)

$$F - S = S \times \frac{\left[\frac{270}{360}\right]}{1 + i_B\left[\frac{270}{360}\right]} \times (i_P - i_B)$$

$$= 0.9000 \times \frac{0.75}{1 + 0.0147 \times 0.75} \times (0.0041 - 0.0147)$$

$$= 0.9000 \times \frac{0.75}{1.011025} \times (-0.0106)$$

$$= 0.9000 \times 0.7418 \times (-0.0106) = -0.0071$$

The AUD (base) trades at a **forward discount** of 71 pips. Why? Because AUD has the higher interest rate (1.47% > 0.41%), so the forward market "punishes" it to prevent arbitrage.

---

## Mark-to-Market Value of a Forward Contract

### What Does Mark-to-Market Mean?

[[Mark-to-market]] means calculating what a position is worth **right now** if you were to close it out. When you initially enter a forward contract, its value is zero (no cash changes hands). As spot rates and interest rates change, the contract gains or loses value.

> **Analogy:** Imagine you signed a contract to buy a house for \$500,000 in 6 months. If houses in that area are now selling for \$550,000, your contract is "worth" \$50,000 to you — you locked in a below-market price. That's mark-to-market.

### The 4-Step Process

```
Step 1: Create an offsetting forward position
        (If you're long, go short the same amount, and vice versa)
                    ↓
Step 2: Determine the all-in forward rate for the offsetting position
        (Use current spot + current forward points)
        (If selling the base currency → use the BID side)
        (If buying the base currency → use the OFFER side)
                    ↓
Step 3: Calculate the cash flow at the settlement date
        = Contract size × (New forward rate − Original forward rate)
        (Positive if your original position's currency appreciated)
                    ↓
Step 4: Discount that cash flow to present value
        (Use the interest rate of the currency of the cash flow)
```

### Worked Example

**Setup:**
- A market participant **bought GBP 10 million** against AUD, 6 months forward at 1.8100 AUD/GBP
- **3 months later**, they want to mark this position to market

**Current market (3 months before settlement):**
- Spot AUD/GBP: 1.8210/1.8215
- 3-month forward points: 130/140
- 3-month AUD MRR: 2.40% (annualized)

**Timeline:**
```
t=0                    t=3 months (NOW)              t=6 months (Settlement)
│                           │                              │
│  Bought GBP 10M           │  Want to mark-to-market      │  Original settlement
│  at F = 1.8100 AUD/GBP    │  Close with offsetting       │  
│                           │  forward                     │
│                           │                              │
│◄─────── 6 months ────────►│◄───── 3 months ─────────────►│
```

**Step 1:** Offset by **selling** GBP 10M forward (3 months to settlement).

**Step 2:** Selling GBP (the base currency) → use the **bid** side.
$$\text{All-in forward bid} = 1.8210 + \frac{130}{10,000} = 1.8340$$

**Step 3:** Cash flow at settlement:
$$(1.8340 - 1.8100) \times 10,000,000 = +\text{AUD } 240,000$$

This is **positive** because we were **long GBP** and GBP **appreciated** (the AUD/GBP rate went up).

**Step 4:** Discount to present value (this cash flow is in AUD, so use AUD MRR):

$$\text{MtM Value} = \frac{\text{AUD } 240,000}{1 + 0.024 \times \frac{90}{360}} = \frac{240,000}{1.006} = \text{AUD } 238,569$$

> **Why discount?** The cash flow won't actually arrive for 3 more months. To know what it's worth **today**, we need to calculate its present value.

### Factors Affecting Forward Bid-Offer Spreads

The same factors as spot spreads, plus:
- **Longer contract term → wider spread** (less liquidity, more credit risk, more interest rate risk)

---

## International Parity Conditions Overview

The [[International Parity Conditions]] describe how exchange rates, interest rates, and inflation rates should be linked in an ideal world. They are the **building blocks** for understanding long-run equilibrium exchange rates.

> **Analogy:** Think of parity conditions like the law of gravity in physics. In a vacuum, a feather and a bowling ball fall at the same rate. In the real world, air resistance causes deviations. Similarly, parity conditions describe what *should* happen without frictions, but transaction costs, capital controls, and risk premiums cause real-world deviations — especially in the short run.

**Three critical concepts for exchange rate analysis:**

1. **Long run vs. short run**: Parity conditions work better over years, not days
2. **Expected vs. unexpected changes**: Markets price in expectations; surprises move rates
3. **Relative movements**: It's not about one country's inflation — it's about the **difference** between two countries

The five key conditions:

| Parity Condition | What It Links | Enforced by Arbitrage? |
|-----------------|--------------|----------------------|
| [[Covered interest rate parity]] | Spot, forward, and interest rates | **Yes** |
| [[Uncovered interest rate parity]] | Expected spot change and interest rates | No |
| [[Forward rate parity]] | Forward rate and expected future spot | No |
| [[Purchasing power parity]] | Exchange rates and inflation | No |
| [[International Fisher Effect]] | Interest rates and expected inflation | No |

---

## Covered Interest Rate Parity (CIP)

Already discussed above. The key takeaway:

$$F_{f/d} = S_{f/d} \times \frac{1 + i_f \left[\frac{Actual}{360}\right]}{1 + i_d \left[\frac{Actual}{360}\right]}$$

- **Enforced by arbitrage** — must hold (or nearly so) at all times
- A hedged foreign investment must yield the same as a domestic investment
- The forward premium/discount exactly offsets the interest rate differential

> **Exam point:** If someone asks "what return does a fully hedged foreign investment earn?" the answer is always **the domestic risk-free rate**. No calculation needed — that's CIP.

---

## Uncovered Interest Rate Parity (UIP)

### The Idea

[[Uncovered interest rate parity]] says that the **expected** change in the spot exchange rate should equal the interest rate differential between two countries. In other words, the currency of the high-interest-rate country should **depreciate** just enough to offset its yield advantage.

### The Formula

$$\boxed{\%\Delta S_{f/d}^{e} = i_f - i_d}$$

**What each variable means:**

| Variable | Meaning |
|----------|---------|
| $\%\Delta S_{f/d}^{e}$ | Expected percentage change in the spot rate |
| $i_f$ | Foreign interest rate |
| $i_d$ | Domestic interest rate |

**In plain English:** If the foreign interest rate is 10% and the domestic rate is 4%, UIP says the foreign currency should depreciate by 6% against the domestic currency. This depreciation exactly wipes out the extra yield, leaving both investments with the same expected return.

> **Analogy:** Imagine two stores having a sale. Store A has a 10% discount but is in a neighborhood where parking costs \$6. Store B has a 4% discount but free parking. After accounting for parking, both deals are equally attractive. That's UIP — the currency depreciation is the "parking cost" that equalizes returns.

### Key Assumptions

UIP assumes **[[risk-neutral]] investors** — people who care only about expected return and ignore risk. In reality, investors are risk-averse, which is one reason UIP often fails in the short run.

### Does UIP Hold?

**Short answer: No, not in the short to medium term.**

Most studies find that high-yield currencies **don't depreciate** as much as UIP predicts. In fact, they often **appreciate**. This violation of UIP is what makes the [[Carry trade]] profitable.

However, UIP tends to hold better over **very long** time horizons (10+ years).

### The Approximate Return on an Unhedged Foreign Investment

$$\text{Return} \approx i_f - \%\Delta S_{f/d}$$

- If the foreign currency depreciates (%ΔS > 0), the return is reduced
- If the foreign currency appreciates (%ΔS < 0), the return is enhanced

---

## Forward Rate Parity

### The Idea

[[Forward rate parity]] states that the forward exchange rate is an **unbiased predictor** of the future spot exchange rate.

$$\boxed{F_{f/d} = S_{f/d}^{e}}$$

**In plain English:** The forward rate should, on average, equal where the spot rate ends up in the future. It won't be perfect for any single forecast, but over many observations, it shouldn't systematically over- or under-predict.

### Why It Matters

Forward rate parity is a **combination** of two other conditions:
- CIP tells us: $\frac{F_{f/d} - S_{f/d}}{S_{f/d}} = i_f - i_d$ (approximately)
- UIP tells us: $\%\Delta S_{f/d}^{e} = i_f - i_d$

If both hold simultaneously:

$$\frac{F_{f/d} - S_{f/d}}{S_{f/d}} = \%\Delta S_{f/d}^{e}$$

Therefore: **$F_{f/d} = S_{f/d}^{e}$** — the forward rate equals the expected future spot rate.

### Does Forward Rate Parity Hold?

Since CIP holds (arbitrage enforces it), forward rate parity hinges on whether **UIP holds**. Since UIP generally doesn't hold in the short run, forward rates are typically **poor predictors** of future spot rates in the short run. Over longer horizons, they perform better.

### Spot Rate as a Forecaster

If you believe exchange rates follow a **[[Random walk]]** (today's rate is the best predictor of tomorrow's), then you'd forecast the future spot rate to equal **today's** spot rate. This approach actually performs surprisingly well in the short run — often better than the forward rate!

---

## Purchasing Power Parity (PPP)

### The Law of One Price

The foundation of PPP is the **[[Law of one price]]**: identical goods should cost the same everywhere when converted to a common currency.

$$P_x^f = S_{f/d} \times P_x^d$$

> **Example:** If a Big Mac costs €4.00 in Europe and the USD/EUR rate is 1.15, then the Big Mac should cost $4.60 in the US. If it costs $5.00 instead, something is "off" — either the dollar is too weak, or US prices are too high.

### Absolute PPP

[[Absolute PPP]] extends the law of one price to **all** goods and services:

$$S_{f/d} = \frac{P^f}{P^d}$$

**In plain English:** The exchange rate should equal the ratio of price levels between two countries.

**Why it doesn't work in practice:**
- Not all goods are tradable (you can't ship a haircut)
- Countries consume different bundles of goods
- Transaction costs, tariffs, and trade barriers exist

### Relative PPP

[[Relative PPP]] is more practical. It says the **change** in the exchange rate should reflect the **difference** in inflation rates:

$$\boxed{\%\Delta S_{f/d} \approx \pi_f - \pi_d}$$

| Variable | Meaning |
|----------|---------|
| $\%\Delta S_{f/d}$ | Percentage change in the spot exchange rate |
| $\pi_f$ | Foreign inflation rate |
| $\pi_d$ | Domestic inflation rate |

**In plain English:** If Country A has 9% inflation and Country B has 5% inflation, Country A's currency should depreciate by 4% relative to Country B's. Why? Because Country A's goods are getting more expensive, making its exports less competitive.

> **Real-world example:** Turkey experienced double-digit inflation throughout the 2010s and 2020s. As predicted by PPP, the Turkish lira depreciated massively against the US dollar over this period. Similarly, Brazil's hyperinflation in the 1980s–1990s was accompanied by dramatic currency depreciation — almost perfectly in line with PPP predictions.

### Ex Ante PPP

[[Ex ante PPP]] uses **expected** inflation rather than actual:

$$\boxed{\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e}$$

Countries expected to have persistently high inflation should expect currency depreciation.

### Does PPP Hold?

| Time Horizon | Does PPP Hold? |
|-------------|---------------|
| 1 year | Poorly — almost no relationship |
| 5 years | Starting to emerge |
| 10–15 years | Strong positive relationship |
| Hyperinflation | Holds even in the short run! |

> **Key insight:** PPP is a **long-run anchor**, not a short-run forecasting tool.

---

## The Fisher Effect and International Fisher Effect

### The (Domestic) Fisher Effect

The [[Fisher effect]] breaks down a country's [[nominal interest rate]] into two components:

$$\boxed{i = r + \pi^e}$$

| Variable | Meaning |
|----------|---------|
| $i$ | Nominal interest rate |
| $r$ | [[Real interest rate]] |
| $\pi^e$ | Expected inflation rate |

**In plain English:** The interest rate you see quoted (nominal) is really just compensation for (1) the real time value of money and (2) expected loss of purchasing power from inflation.

> **Example:** If the real interest rate is 2% and expected inflation is 3%, the nominal rate should be 5%. Lenders need 5% just to break even in real terms — 2% for giving up their money and 3% to keep up with rising prices.

### The International Fisher Effect

The [[International Fisher Effect]] applies the Fisher equation across countries:

For two countries:
- $i_d = r_d + \pi_d^e$
- $i_f = r_f + \pi_f^e$

Subtracting:

$$i_f - i_d = (r_f - r_d) + (\pi_f^e - \pi_d^e)$$

If **[[Real interest rate parity]]** holds ($r_f = r_d$), then:

$$\boxed{i_f - i_d = \pi_f^e - \pi_d^e}$$

**In plain English:** The difference in nominal interest rates between two countries should equal the difference in their expected inflation rates. A country with higher interest rates simply has higher expected inflation — not a "better" investment opportunity.

### Real Interest Rate Parity

If both UIP and ex ante PPP hold:
- UIP: $\%\Delta S_{f/d}^e = i_f - i_d$
- Ex ante PPP: $\%\Delta S_{f/d}^e = \pi_f^e - \pi_d^e$

Therefore: $i_f - i_d = \pi_f^e - \pi_d^e$

Rearranging: $(i_f - \pi_f^e) = (i_d - \pi_d^e)$, which means $r_f = r_d$

**[[Real interest rate parity]]**: Real interest rates converge across countries.

> **Caveat:** This doesn't always hold. Emerging markets often have higher real interest rates because investors demand a **risk premium** for the additional currency and country risk.

---

## Tying All Parity Conditions Together

If all parity conditions held simultaneously, then the expected change in the spot exchange rate would equal:

$$\frac{F_{f/d} - S_{f/d}}{S_{f/d}} = \%\Delta S_{f/d}^e = i_f - i_d = \pi_f^e - \pi_d^e$$

```
                    Forward Premium/Discount
                    (Covered Interest Rate Parity)
                            ↕
Expected Exchange    ←→    Interest Rate         ←→    Expected Inflation
Rate Change                Differential                Differential
(Uncovered IRP)            (Intl Fisher Effect)        (Ex Ante PPP)
                            ↕
                    Forward Rate = Expected
                    Future Spot Rate
                    (Forward Rate Parity)
```

**If all conditions held perfectly:**
- No profit from forward speculation
- No profit from carry trades
- All markets would offer the same currency-adjusted return
- The real interest rate spread would be zero

**In reality:** Only CIP consistently holds. The others are violated in the short to medium run, creating opportunities (and risks) for traders.

| Parity Condition | Holds Short-Run? | Holds Long-Run? |
|-----------------|-------------------|-----------------|
| CIP | **Yes** (arbitrage) | **Yes** |
| UIP | Usually No | Better |
| Forward Rate Parity | Usually No | Better |
| Relative PPP | No (unless hyperinflation) | **Yes** |
| Intl Fisher Effect | Sometimes | Better |
| Real Interest Rate Parity | Often No | Better |

---

## The Carry Trade

### What is the Carry Trade?

The [[Carry trade]] is a strategy where you:
1. **Borrow** in a low-interest-rate currency (the "[[funding currency]]")
2. **Invest** in a high-interest-rate currency (the "target currency")
3. Pocket the interest rate differential

> **Analogy:** It's like borrowing from a bank at 1% interest and putting the money in a CD earning 9%. The 8% spread is your profit — as long as nothing goes wrong with the exchange rate.

### How It Works — Step by Step

**Example:** Borrow CAD at 1%, invest in BRL at 9%.

```
t=0 (Today)                                t=1 (One Year Later)
│                                          │
│  1. Borrow CAD at 1%                     │  4. Liquidate BRL investment
│  2. Convert CAD → BRL at spot rate       │  5. Convert BRL → CAD at spot rate
│  3. Invest BRL at 9%                     │  6. Repay CAD loan + 1% interest
│                                          │
│  Interest differential = 8%              │  Profit depends on what happened
│                                          │  to the BRL/CAD exchange rate
```

### The Return

$$\text{Carry Trade Return} \approx i_{high} - i_{low} - \%\Delta S_{\text{funding/target}}$$

Three scenarios:
- **BRL appreciates** → Return > 8% (you get the spread PLUS currency gain)
- **BRL stays flat** → Return ≈ 8% (just the interest spread)
- **BRL depreciates by 8%** → Return ≈ 0% (depreciation wipes out the spread)
- **BRL depreciates > 8%** → **Losses** (you actually lose money)

### Why Does the Carry Trade Work?

It works because **UIP doesn't hold** in the short to medium term. UIP predicts that high-yield currencies should depreciate enough to eliminate the interest advantage. In reality, they often **don't** depreciate — and sometimes they even **appreciate**.

### The Risks: Crash Risk

The carry trade has an asymmetric risk profile:

- **Most of the time:** Small, steady gains (interest accrual in calm markets)
- **Occasionally:** Large, sudden losses (when volatility spikes)

> **Analogy:** The carry trade is like picking up pennies in front of a steamroller. You collect a lot of pennies most days, but when the steamroller suddenly speeds up, you can get crushed.

**The return distribution has:**
- **Negative skewness**: More frequent large losses than large gains
- **Fat tails**: Extreme events happen more often than a normal distribution predicts
- **High peak**: Many small gains clustered around the average

**What causes crashes:**
1. Volatility spikes → investors rush to unwind positions
2. Everyone tries to sell the high-yield currency at once
3. Stop-loss orders trigger a cascade of selling
4. "Flight to quality" into safe-haven currencies (USD, JPY, CHF)
5. Leverage amplifies losses

> **Historical example:** In 2008, carry trades involving AUD, NZD, and emerging market currencies suffered massive losses as the global financial crisis triggered a rush into the USD and JPY. The AUD fell 35%+ against the USD in just months.

### Worked Example: Carry Trade Return

**Given:**
| | Rate | Currency Pair | Spot Today | Spot in 1 Year |
|---|---|---|---|---|
| JPY MRR | 0.10% | JPY/USD | 105.40 | 104.60 |
| AUD MRR | 1.70% | USD/AUD | 0.6810 | 0.6850 |

**Strategy:** Borrow JPY at 0.10%, invest in AUD MRR at 1.70%.

**Step 1: Calculate today's JPY/AUD cross rate.**
$$105.40 \times 0.6810 = 71.78 \text{ JPY/AUD}$$

**Step 2: Calculate the cross rate one year later.**
$$104.60 \times 0.6850 = 71.65 \text{ JPY/AUD}$$

**Step 3: Calculate the gross return in JPY.**
$$\frac{1}{71.78} \times (1 + 0.017) \times 71.65 - 1 = 0.0152 = 1.52\%$$

**Step 4: Subtract borrowing cost.**
$$1.52\% - 0.10\% = 1.42\% \text{ net return}$$

---

## Balance of Payments Flows

### Current Account vs. Capital Account

A country's [[Balance of payments]] has two main parts:

| Account | What It Covers | Example |
|---------|---------------|---------|
| [[Current account]] | Trade in goods and services (the "real economy") | Toyota exports cars from Japan |
| [[Capital account]] | Financial flows (investment, lending) | A US pension fund buys Japanese bonds |

**Key rule:** Current account + Capital account = 0 (they must balance)

If a country **imports more than it exports** (current account deficit), it must attract foreign capital to pay for those imports (capital account surplus).

### Three Channels of Current Account Influence

**1. The [[Flow Supply/Demand Channel]]**

The simplest model: Countries that export more create more demand for their currency (foreigners need to buy it to pay for exports). Over time:
- **Persistent surpluses → currency appreciation**
- **Persistent deficits → currency depreciation**

> **Example:** Japan consistently exported more than it imported for decades. Foreign buyers needed yen to pay for Japanese goods, pushing the yen higher over time.

**2. The [[Portfolio Balance Channel]]**

Trade deficits shift wealth from deficit to surplus nations. Surplus nations accumulate financial claims on deficit nations. Eventually, surplus nations may not want to hold more of the deficit country's assets, putting downward pressure on the deficit country's currency.

> **Example:** China accumulated trillions of USD assets from its trade surplus with the US. If China decided it held "too many" dollars and started diversifying, this would put downward pressure on the USD.

**3. The [[Debt Sustainability Channel]]**

There's an upper limit to how much debt a country can owe foreigners. As external debt rises to unsustainable levels, investors begin to fear a major currency depreciation and start demanding higher risk premiums or withdrawing capital entirely.

> **Real-world example:** The US dollar has experienced three major downward cycles (1977–78, 1985–87, 2002–08). Each was driven by concerns over outsized current account deficits combined with relatively low interest rates that couldn't attract enough foreign capital.

### Why Capital Flows Often Matter More (Short to Medium Term)

1. Financial prices adjust instantly; goods prices adjust slowly
2. Financial flows can be redirected in milliseconds; shifting production takes months
3. Capital flows involve **reallocation of existing portfolios**, not just current transactions
4. Expected exchange rate movements can trigger massive speculative flows

---

## Capital Flows

### How Capital Flows Affect Exchange Rates

Greater global financial integration has made [[capital flows]] the dominant short-term driver of exchange rates. Capital can be both a blessing and a curse for emerging markets.

**The blessing:** Capital inflows → investment → economic growth → asset appreciation → currency appreciation → more capital inflows

**The curse:** If inflows reverse suddenly, the result can be:
- Economic contraction
- Asset price collapse
- Currency crash
- Banking crisis

### What Excessive Capital Inflows Can Cause

1. Unwarranted currency appreciation
2. Huge buildup in external debt
3. Asset price bubbles
4. Consumption binges and credit booms
5. Overinvestment in risky projects

### Equity Markets and Exchange Rates

The correlation between equity markets and exchange rates is **unstable** and converges toward **zero** in the long run. Sometimes they move together (both up), sometimes they move opposite (equities up, currency down — e.g., the "risk-on/risk-off" dynamic where the USD weakens when stocks rally because investors move out of the safe-haven dollar into riskier assets).

---

## Monetary and Fiscal Policies

## The Mundell-Fleming Model

The [[Mundell-Fleming Model]] explains how monetary and fiscal policy affect exchange rates through their impact on interest rates, output, and capital flows.

### Key Assumptions
- Sufficient slack in the economy (no immediate price-level effects)
- Focuses on **aggregate demand**
- Capital mobility matters enormously

### Monetary Policy Effects

| Policy | Interest Rates | Capital Flows | Currency Effect |
|--------|---------------|---------------|----------------|
| **Expansionary** (rates↓, money supply↑) | Fall | Capital flows **out** | Currency **depreciates** |
| **Restrictive** (rates↑, money supply↓) | Rise | Capital flows **in** | Currency **appreciates** |

### Fiscal Policy Effects (High Capital Mobility)

| Policy | Interest Rates | Capital Flows | Trade Balance | Currency Effect |
|--------|---------------|---------------|---------------|----------------|
| **Expansionary** (spending↑ or taxes↓) | Rise | Capital flows **in** | Worsens | Currency **appreciates** (capital flows dominate) |
| **Restrictive** (spending↓ or taxes↑) | Fall | Capital flows **out** | Improves | Currency **depreciates** |

### The Policy Mix — High Capital Mobility

| | Expansionary Fiscal | Restrictive Fiscal |
|---|---|---|
| **Restrictive Monetary** | **Currency appreciates strongly** (both push rates up / attract capital) | Indeterminate |
| **Expansionary Monetary** | Indeterminate | **Currency depreciates strongly** (both push rates down / repel capital) |

### The Policy Mix — Low Capital Mobility

When capital can't flow freely, the trade balance dominates:

| | Expansionary Fiscal | Restrictive Fiscal |
|---|---|---|
| **Expansionary Monetary** | **Currency depreciates** (imports surge) | Indeterminate |
| **Restrictive Monetary** | Indeterminate | **Currency appreciates** (imports fall) |

> **Key insight:** High capital mobility → capital flows dominate → interest rate effects matter most. Low capital mobility → trade flows dominate → aggregate demand effects matter most.

> **Real-world example (Germany 1990–1992):** After reunification, Germany ran expansionary fiscal policy (spending to rebuild East Germany) and restrictive monetary policy (Bundesbank fighting inflation). This is the "most bullish" combination under high capital mobility — and indeed, the Deutsche Mark appreciated strongly.

---

## Monetary Models of Exchange Rate Determination

### The Pure Monetary Model

The [[monetary model]] takes the opposite perspective from Mundell-Fleming:
- Output is **fixed**
- Monetary policy affects exchange rates through the **price level** and **inflation**

**Core idea:** An X% increase in money supply → X% increase in prices → X% depreciation of currency (via PPP).

**Problem:** Assumes PPP holds in the short run, which it doesn't.

### The Dornbusch Overshooting Model

The [[Dornbusch overshooting model]] is a more realistic version:
- Prices are **sticky** in the short run but flexible in the long run
- When money supply increases:
  - **Short run:** Interest rates fall → capital outflows → currency **overshoots** its long-run equilibrium (depreciates MORE than PPP would predict)
  - **Long run:** Prices adjust upward, interest rates normalize, currency appreciates back toward its PPP path

> **Analogy:** Imagine throwing a ball to a friend. You throw it too hard (overshoot), it goes past them, then gravity pulls it back. The exchange rate does the same thing — it overreacts initially, then corrects.

> **Real-world examples:**
> - The Fed's quantitative easing (2009–2014) weakened the dollar
> - Japan's Abenomics and QE (2013–2015) caused the yen to weaken from ~90 JPY/USD to ~120 JPY/USD
> - ECB's QE in 2015 weakened the euro
> - Excessive monetary easing in emerging markets (Argentina, Brazil, Venezuela) has repeatedly led to currency crises

---

## The Portfolio Balance Approach

The [[Portfolio balance approach]] addresses what Mundell-Fleming misses: the **long-term** effects of persistent government budget deficits.

### Core Idea

Global investors hold diversified portfolios of domestic and foreign bonds. If a government runs persistent budget deficits, the supply of its bonds increases. Investors will only hold more of these bonds if compensated through:

1. **Higher interest rates / risk premium**
2. **Immediate currency depreciation** to a level where future appreciation is expected
3. Some combination of both

### Short Run vs. Long Run

This is a critical distinction for the exam:

| Time Horizon | Effect of Expansionary Fiscal Policy (High Capital Mobility) |
|-------------|-------------------------------------------------------------|
| **Short run** | Currency **appreciates** (higher rates attract capital — Mundell-Fleming) |
| **Long run** | Currency **depreciates** (rising debt → rising risk premium → debt monetization fears) |

> **Real-world example:** The US ran large fiscal deficits in the early 1980s. Initially, high interest rates attracted foreign capital and the dollar **soared**. But by the mid-1980s, the unsustainable current account deficit and rising external debt caused the dollar to **collapse** — exactly as the portfolio balance model predicts.

---

## Exchange Rate Management — Intervention and Controls

### Why Governments Intervene

Governments and central banks may act to:
- Prevent excessive currency appreciation from capital inflows
- Defend a currency peg
- Reduce exchange rate volatility
- Maintain independent monetary policy

### Types of Intervention

**1. Direct FX Market Intervention**
- Central bank buys/sells its own currency in the FX market
- **Effectiveness in developed markets:** Limited — daily FX turnover dwarfs reserves
- **Effectiveness in emerging markets:** More effective — reserves are larger relative to FX turnover

**2. [[Capital Controls]]**
- Taxes on foreign exchange transactions (e.g., Brazil's 2016 tax)
- Required non-interest-bearing deposits (e.g., Thailand's 30% deposit requirement in 2006)
- Restrictions on foreign ownership (e.g., Vietnam limiting foreign bank ownership)
- Multiple exchange rates (e.g., Venezuela's four different rates by 2016)

### Push vs. Pull Factors for Capital Flows

| Pull Factors (Domestic Improvements) | Push Factors (External Drivers) |
|--------------------------------------|-------------------------------|
| Lower inflation | Low interest rates in developed markets |
| More flexible exchange rates | Portfolio reallocation toward EM |
| Improved fiscal position | Search for yield |
| Financial market liberalization | |
| Privatization | |

### Effectiveness of Intervention

- **Developed markets:** Mostly ineffective at changing exchange rate **levels**, may reduce short-term volatility
- **Emerging markets:** More effective due to larger reserves relative to FX turnover, but still limited

> **Key exam point:** Intervention to **weaken** your currency is theoretically unlimited (you can always print more of your own currency). Intervention to **strengthen** your currency is limited by your reserves.

---

## Warning Signs of a Currency Crisis

### What is a Currency Crisis?

A [[Currency crisis]] is a sudden, sharp depreciation of a country's currency, often accompanied by economic contraction, asset price collapses, and capital flight.

> **Example:** In 2008–2009, 23 currencies dropped 25%+ against the USD. The AUD, SEK, and GBP fell 35%+. The BRL, RUB, and KRW fell 50%+.

### Two Schools of Thought on Causes

1. **Fundamentals-based:** Deteriorating economic fundamentals gradually weaken the currency until a crisis erupts. These should be somewhat predictable.

2. **Self-fulfilling:** Crises can strike countries with sound fundamentals when market sentiment shifts or contagion spreads from other countries. These are harder to predict.

### The 9 Warning Signs

An early warning system should monitor these conditions. A crisis rarely stems from just one — it's typically a **combination** of several:

| # | Warning Sign | Why It Matters |
|---|-------------|---------------|
| 1 | **Capital market liberalization** | Free capital flows can reverse suddenly |
| 2 | **Large foreign capital inflows** (especially short-term, foreign-denominated debt) | Creates vulnerability to capital flight |
| 3 | **Banking crisis** (often precedes or coincides) | Banks can't service foreign debt if currency falls |
| 4 | **Fixed or pegged exchange rate** | Reduces flexibility; creates speculative targets |
| 5 | **Declining FX reserves** | Government running out of ammunition to defend currency |
| 6 | **Currency substantially above historical mean** | Overvaluation makes exports uncompetitive |
| 7 | **Deteriorating terms of trade** (exports/imports ratio falling) | Earning less foreign currency |
| 8 | **Rising M2/bank reserves ratio and broad money growth** | Excessive domestic credit creation |
| 9 | **High inflation** relative to tranquil periods | Erodes competitiveness and confidence |

### How These Factors Feed Off Each Other

```
Capital market liberalization
        ↓
Large foreign capital inflows
        ↓
Banks borrow short-term in foreign currencies
        ↓
If currency depreciates even slightly...
        ↓
Banks can't service foreign debt → Banking crisis
        ↓
Foreign investors withdraw capital
Speculators short the currency
        ↓
Government raises rates (hurts economy) OR
spends reserves (finite ammunition)
        ↓
If government can't/won't defend → CURRENCY CRISIS
        ↓
More capital flight → more depreciation → cascading losses
```

### Case Study: Iceland 2008

Iceland's crisis is a textbook example of how multiple warning signs compound:

- **Capital liberalization:** Banking sector deregulated in 2001
- **Massive capital inflows:** Banks grew assets to 14× GDP
- **Foreign-denominated debt:** Banks borrowed in GBP and EUR
- **Currency overvaluation:** Krona appreciated 40% from 2001–2007
- **Deteriorating trade balance:** Surplus turned to deficit
- **Explosive money growth:** 14–35% annually
- **Rising [[Inflation|inflation]]:** Hit 14% by fall 2008

When the global financial crisis hit, foreign depositors withdrew funds, banks couldn't roll over short-term debt, and all three major banks collapsed. The krona fell 60%+, the stock market fell 77%, and Iceland required an IMF bailout.

### Properties of an Ideal Early Warning System

1. **Strong predictive record** with **few false alarms**
2. Uses data available on a **timely basis** (not lagged)
3. **Broad-based** — monitors multiple indicators, not just one
4. Signals **well in advance** to allow portfolio adjustments

> **Limitation:** No model catches every crisis, and all models sometimes generate false alarms. Early warning systems are useful supplements to judgment, not replacements for it.

---

## Forecasting Exchange Rates: A Summary

| Method | What It Assumes | Best Use Case |
|--------|----------------|---------------|
| **Current [[Spot rate|spot rate]]** | [[Random walk|Random walk]] (today's rate is the best predictor) | Short-term forecasting |
| **[[Forward rate|Forward rate]]** | CIP + UIP both hold; investors are risk-neutral | When you believe UIP holds |
| **PPP** | [[Inflation|Inflation]] differentials drive exchange rates | Long-run [[Equilibrium|equilibrium]] assessment |
| **UIP** | [[Interest rate|Interest rate]] differentials predict [[Depreciation|depreciation]] | When you believe risk neutrality holds |

---

## Key Formulas — Quick Reference

### Covered Interest Rate Parity
$$F_{P/B} = S_{P/B} \times \frac{1 + i_P \left[\frac{Actual}{360}\right]}{1 + i_B \left[\frac{Actual}{360}\right]}$$

### Forward Premium/Discount
$$F_{P/B} - S_{P/B} = S_{P/B} \times \frac{\left[\frac{Actual}{360}\right]}{1 + i_B\left[\frac{Actual}{360}\right]} \times (i_P - i_B)$$

### Uncovered Interest Rate Parity
$$\%\Delta S_{f/d}^{e} = i_f - i_d$$

### Ex Ante PPP
$$\%\Delta S_{f/d}^{e} = \pi_f^e - \pi_d^e$$

### International Fisher Effect
$$i_f - i_d = \pi_f^e - \pi_d^e$$

### Fisher Effect
$$i = r + \pi^e$$

### Forward Rate Parity
$$F_{f/d} = S_{f/d}^{e}$$

### Cross Rate
$$\frac{A}{C} = \frac{A}{B} \times \frac{B}{C}$$

### Inversion
$$\frac{B}{A}_{bid} = \frac{1}{\left(\frac{A}{B}\right)_{offer}} \quad;\quad \frac{B}{A}_{offer} = \frac{1}{\left(\frac{A}{B}\right)_{bid}}$$

---

## Glossary of Key Terms

| Term | Definition |
|------|-----------|
| [[Arbitrage]] | Simultaneous buying and selling to profit from price discrepancies with zero risk |
| [[Base currency]] | The currency in the denominator of an exchange rate quote (P/B); the currency being bought or sold |
| [[Bid price]] | The price at which a dealer will buy the base currency |
| [[Bid-offer spread]] | The difference between the offer and [[Bid price|bid price]]; dealer compensation |
| [[Capital account]] | The portion of [[Balance of payments|balance of payments]] recording financial flows |
| [[Capital controls]] | Government restrictions on capital flows in/out of a country |
| [[Carry trade]] | Borrowing in a low-yield currency and investing in a high-yield currency |
| [[Covered interest rate parity]] | [[Arbitrage|Arbitrage]] condition linking [[Spot rates|spot rates]], forward rates, and interest rates |
| [[Currency crisis]] | Sudden, sharp [[Depreciation|depreciation]] of a currency, often with economic collapse |
| [[Current account]] | The portion of [[Balance of payments|balance of payments]] recording trade in goods and services |
| [[Day count fraction]] | Adjustment to convert annualized rates to the actual investment period (e.g., Actual/360) |
| [[Exchange rate]] | The price of one currency in terms of another |
| [[Fisher effect]] | The relationship i = r + πe linking nominal rates, real rates, and [[Expected inflation|expected inflation]] |
| [[Forward contract]] | Agreement to exchange currencies at a future date at a rate set today |
| [[Forward points]] | The difference between forward and [[Spot rates|spot rates]], scaled to the last decimal place |
| [[Forward rate parity]] | The condition that forward rates are unbiased predictors of future [[Spot rates|spot rates]] |
| [[Funding currency]] | The low-yield currency borrowed in a [[Carry trade|carry trade]] |
| [[Interbank market]] | Wholesale FX market among professional dealers |
| [[International Fisher Effect]] | Nominal [[Interest rate|interest rate]] differentials equal [[Expected inflation|expected inflation]] differentials |
| [[Law of one price]] | Identical goods should cost the same everywhere in a common currency |
| [[Mark-to-market]] | Calculating the current value of a position based on current market prices |
| [[Mundell-Fleming Model]] | Model describing how monetary/[[Fiscal policy|fiscal policy]] affects exchange rates via interest rates and output |
| [[Offer price]] | The price at which a dealer will sell the base currency (also called [[Ask price|ask price]]) |
| [[Pip]] | Smallest standard unit of exchange rate movement (0.0001 for most; 0.01 for JPY) |
| [[Portfolio balance approach]] | Model focusing on long-run effects of government debt on exchange rates |
| [[Price currency]] | The currency in the numerator of an exchange rate quote (P/B) |
| [[Purchasing power parity]] | Exchange rates should reflect [[Relative price|relative price]] levels or [[Inflation|inflation]] differentials |
| [[Random walk]] | A process where today's value is the best predictor of tomorrow's value |
| [[Real interest rate]] | [[Nominal rate|Nominal rate]] minus [[Expected inflation|expected inflation]]; the "true" return on an investment |
| [[Real interest rate parity]] | Real interest rates converge across countries |
| [[Risk-neutral]] | An investor who cares only about expected return, not risk |
| [[Spot exchange rate]] | The rate for immediate (T+2) currency delivery |
| [[Triangular Arbitrage]] | Exploiting pricing inconsistencies among three currency pairs |
| [[Uncovered interest rate parity]] | Expected currency [[Depreciation|depreciation]] equals the [[Interest rate|interest rate]] differential |
