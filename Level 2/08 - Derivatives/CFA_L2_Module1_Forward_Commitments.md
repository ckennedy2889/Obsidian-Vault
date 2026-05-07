---
title: "CFA_L2_Module1_Forward_Commitments"
subject: "Derivatives"
tags: [CFA-L2, derivatives]
aliases: []
---

# CFA Level 2 – Module 1: Pricing and Valuation of Forward Commitments

> **Curriculum:** 2025 CFA Program Level II, Volume 7 – [[Derivatives|Derivatives]]
> **Tags:** #CFA #Level2 #[[Derivatives|Derivatives]] #ForwardCommitments #Pricing #Swaps

---

## 🗺️ Module Roadmap

```
Forward Commitments
│
├── 1. The Carry Arbitrage Model (Core Framework)
│   ├── Without Underlying Cash Flows
│   └── With Underlying Cash Flows
│
├── 2. Forwards & Futures by Underlying
│   ├── A. Equity Forwards & Futures
│   ├── B. Interest Rate Forwards (FRAs)
│   ├── C. Fixed-Income Forwards & Futures
│   └── D. Currency Forwards & Futures
│
└── 3. Swaps (Priced as Portfolios of Forwards)
    ├── A. Interest Rate Swaps
    ├── B. Currency Swaps
    └── C. Equity Swaps
```

---

## 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| [[Forward contract]] | OTC agreement to buy/sell an asset at a pre-agreed price on a future date |
| [[Futures contract]] | Exchange-traded, standardized forward; marked-to-market daily |
| [[No-Arbitrage Price]] | The price that makes it impossible to earn a riskless profit |
| [[Carry Cost]] | Cost of holding/financing the underlying asset |
| [[Forward price]] F₀ | The [[No-arbitrage pricing|no-arbitrage]] delivery price set at initiation (V₀ = 0) |
| [[Convergence]] | At expiration: F_T = f_T = S_T |
| [[Discount factor]] | DF = 1 / (1 + r)^t, used to price swaps |

---

## 📐 Notation Cheat Sheet

| Symbol | Meaning |
|--------|---------|
| S₀ | Spot price of underlying at time 0 |
| F₀ | Forward price agreed at initiation |
| Fₜ | Forward price at time t (mid-life) |
| f₀, fₜ | Futures price at 0 and t |
| Vₜ | Value of a forward/[[Futures contract|futures contract]] |
| r | Risk-free rate (periodic compounding) |
| rᶜ | Continuously compounded risk-free rate |
| T | Time to expiration (in years) |
| γ (gamma) | Benefits of holding the underlying (dividends, coupons) |
| θ (theta) | Costs of holding the underlying (storage, insurance) |

---

## Part 1 – The Carry Arbitrage Model

### 🧠 Core Intuition

> **The no-arbitrage forward price equals the cost of buying the underlying today and carrying it to the delivery date.**

You can replicate owning a [[Forward contract|forward contract]] by:
1. **Borrowing** money at the risk-free rate
2. **Buying** the underlying spot (S₀)
3. **Carrying** it to time T (paying financing costs, receiving any income)

The forward price is set so this replication strategy earns **exactly zero profit**.

---

### 1A. Without Underlying Cash Flows

**[[No-Arbitrage Forward Price]]:**

$$F_0 = S_0 \times (1 + r)^T \quad \text{(periodic compounding)}$$

$$F_0 = S_0 \times e^{r_c T} \quad \text{(continuous compounding)}$$

**[[Forward Contract Value]] (long position):**

$$V_0 = 0 \quad \text{(at initiation)}$$

$$V_T = S_T - F_0 \quad \text{(long at expiration)}$$

$$V_t = S_t - \frac{F_0}{(1+r)^{T-t}} \quad \text{(long, mid-life)}$$

> 💡 **Key insight:** The forward price does **not** forecast the future spot price. It is purely a carry-adjusted version of today's spot price.

---

**⚡ Arbitrage in Action**

If F₀ ≠ S₀(1+r)^T, free money exists:

| Situation | Strategy | Steps |
|-----------|----------|-------|
| **F₀ > S₀(1+r)^T** | [[Carry Arbitrage]] | Borrow money → Buy S₀ → Short F₀ → At T: deliver S, pay back loan, pocket difference |
| **F₀ < S₀(1+r)^T** | [[Reverse carry arbitrage]] | Short S₀ → Invest proceeds → Long F₀ → At T: collect loan + interest, take delivery, close short |

**Example (from curriculum):**
- S₀ = 100, r = 5%, T = 1 year
- No-arbitrage price: F₀ = 100 × (1.05)¹ = **105**
- If market quotes F₀ = **110** → borrow $100, buy stock, short forward → profit $5 at T
- If market quotes F₀ = **90** → short stock, invest proceeds, go long forward → profit $15 at T (PV = $14.29)

---

### 1B. With Underlying Cash Flows (Benefits & Costs)

Adjust the spot price for the present value of any cash flows received (γ = benefits like dividends/coupons) or paid (θ = costs like storage) during the holding period:

$$F_0 = \left[S_0 + PV(\theta) - PV(\gamma)\right](1+r)^T$$

$$\text{Or equivalently: } F_0 = \left[S_0 - PV(\text{benefits}) + PV(\text{costs})\right](1+r)^T$$

**[[Forward Contract Value]] mid-life (long), with cash flows:**

$$V_t = \left(S_t - PV(\text{benefits remaining})\right) - \frac{F_0}{(1+r)^{T-t}}$$

> 💡 **Intuition:** Dividends/coupons reduce the forward price because the owner of the spot asset gets paid — the forward holder does not. So higher dividends → lower F₀.

---

**With Continuous Dividend Yield (δ):**

$$F_0 = S_0 \times e^{(r_c - \delta_c) \times T}$$

---

### 🌎 Real-World Example: S&P 500 Futures (Equity Index Futures)

The **[[S&P 500 E-mini futures]]** (CME) are priced using continuous dividend yield:
- If the S&P 500 spot = 5,000, r = 5%, δ = 1.5%, T = 0.25 years
- F₀ = 5,000 × e^(0.05 − 0.015) × 0.25 = 5,000 × e^0.00875 ≈ **5,043.92**
- If futures trade above this → buy the index basket, short the futures (index arbitrage)

---

## Part 2 – Forwards & Futures by Underlying

### 2A. Equity Forwards & Futures

**Pricing (discrete dividends):**

$$F_0 = (S_0 - PVD) \times (1+r)^T$$

where PVD = present value of all dividends paid during the contract's life.

**Pricing (continuous dividend yield δ):**

$$F_0 = S_0 \times e^{(r_c - \delta_c)T}$$

**Valuation (long) at time t:**

$$V_t = (S_t - PVD_t) - \frac{F_0}{(1+r)^{T-t}}$$

---

**Curriculum Example:**
- Australian stock, S₀ = A$63.31, r = 2.75%, T = 0.25 (3 months), no dividends
- F₀ = 63.31 × (1.0275)^0.25 = **A$63.74**
- If rates fall to 2.25%: F₀ = 63.31 × (1.0225)^0.25 = **A$63.66** (forward price falls with rates)

**Mid-life example:**
- Entered 1-year forward at F₀ = 102, 9 months left (T−t = 0.25)
- Sₜ = 110, r = 5%
- Fₜ = 110 × (1.05)^0.25 = 111.35
- Vₜ (long) = (111.35 − 102) / (1.05)^0.25 = **$9.11**

> ⚠️ If a dividend is **announced** (but the spot price doesn't change), the forward **value falls** immediately because PVD increases while F₀ and Sₜ stay the same.

---

**🌎 Real World:** A portfolio manager holds Apple stock but is worried about a short-term drawdown. They enter a **single-stock forward** to sell at F₀. If Apple pays a dividend before expiration, the forward price would have been set lower to account for that dividend — otherwise arbitrageurs would exploit the mispricing.

---

### 2B. Interest Rate Forwards – [[Forward rate agreement]] (FRA)

An [[FRA]] is an OTC contract on a **future interest rate**:
- **Underlying:** A notional deposit or loan starting at time T₁ and ending at T₂
- **Long position (receive floating):** Profits if floating rates rise above the FRA rate
- **Short position (receive fixed):** Profits if floating rates fall below the FRA rate
- **No exchange of notional principal**

**Notation: m × n FRA**
- A **3×9 FRA** = rate on a 6-month deposit beginning in 3 months
- The "price" = the implied [[Forward rate|forward rate]] between the two spot rates

---

**FRA Pricing (Forward Rate):**

Using no-arbitrage across spot rates L(T₁) and L(T₂):

$$\left[1 + L(T_2)\cdot\frac{T_2}{360}\right] = \left[1 + L(T_1)\cdot\frac{T_1}{360}\right]\left[1 + f(T_1, T_2-T_1)\cdot\frac{T_2-T_1}{360}\right]$$

Solving for the FRA fixed rate f:

$$f(T_1, T_2-T_1) = \frac{\left[\frac{1 + L(T_2)\cdot\frac{T_2}{360}}{1 + L(T_1)\cdot\frac{T_1}{360}}\right] - 1}{\frac{T_2-T_1}{360}}$$

---

**FRA Settlement (Advanced Set, Advanced Settled):**

At expiration, the FRA settles in **cash**, discounted back from the end of the deposit period:

**Receive-fixed payoff:**

$$\text{Payoff} = \frac{NP \times (FRA_{rate} - L_{settle}) \times \frac{days}{360}}{1 + L_{settle} \times \frac{days}{360}}$$

**Receive-floating payoff:**

$$\text{Payoff} = \frac{NP \times (L_{settle} - FRA_{rate}) \times \frac{days}{360}}{1 + L_{settle} \times \frac{days}{360}}$$

---

**Curriculum Example – 1×4 FRA:**
- UK company, £10M notional, 90-day Libor, receive-fixed at **0.60%**
- After 30 days: 90-day Libor = **0.55%**
- Payoff (receive-fixed) = £10M × (0.0060 − 0.0055) × (90/360) / (1 + 0.0040 × 90/360)
- = £10M × 0.000125 / 1.001 ≈ **£1,248.75** (paid to the fixed receiver)

---

**Timeline:**
```
0 ──────────── 30 days ──────── 120 days
              FRA expires         Deposit matures
              ↑                   
         Settlement cash
         flows discounted
         back to day 30
```

---

**🌎 Real World:** A CFO of a manufacturing company knows in 30 days she'll need to borrow £10M for 90 days. Worried rates will rise, she **buys an FRA** (receive-floating, pay-fixed) — wait, she actually wants to **hedge borrowing costs**, so she enters a **receive-fixed FRA**. If rates rise, the FRA gain offsets higher borrowing costs. This is how **corporate treasurers** hedge interest rate risk on short-term borrowings.

---

### 2C. Fixed-Income Forwards & Futures

**Key concepts:**
- [[Full price]] = [[Clean Price]] + [[Accrued interest]] (AI)
- [[Treasury Bond Futures]] are based on a **notional "generic" bond** (e.g., 6% coupon, $100,000 face)
- The **short side** chooses which eligible bond to deliver → they pick the [[Cheapest-to-Deliver (CTD)]] bond

---

**[[Conversion Factor]] (CF):**
The price a bond *would* have if yields were exactly 6%. Used to normalize delivery across different bonds.

Payment to short = (Quoted Futures Price × CF) + Accrued Interest at delivery

**[[CTD Bond]] Identification:**
$$\text{Cost-to-Deliver} = \text{Full Price}_T - (F_T \times CF)$$
→ Short delivers the bond with the **lowest** cost-to-deliver.

**Example:**
| Bond | Full Price | CF | Cost-to-Deliver |
|------|-----------|----|----|
| 1 | 99.50 | 1.0382 | 99.50 − (93.25 × 1.0382) = **2.69** |
| 2 | 143.50 | 1.5188 | 143.50 − (93.25 × 1.5188) = **1.87** ✓ CTD |
| 3 | 119.75 | 1.2615 | 119.75 − (93.25 × 1.2615) = **2.12** |

---

**Fixed-Income Forward Price:**

$$F_0 = \left[(S_0 + AI_0) - \frac{I}{(1+r)^{t_I}}\right](1+r)^T - AI_T$$

where:
- S₀ = quoted (clean) spot price
- AI₀ = accrued interest at initiation
- I = coupon payment received during life of forward, PV'd to today
- AI_T = accrued interest at delivery

**Quoted Futures Price:**

$$QF_0 = \frac{F_0}{CF}$$

---

**🌎 Real World:** The **[[US Treasury Bond Futures]]** market (CME Group) is one of the world's largest derivatives markets. Pension funds and insurance companies use T-bond futures to manage [[Duration]] of their portfolios without selling underlying bonds. A fund manager who wants to reduce duration **shorts T-bond futures**. The conversion factor system ensures fair delivery regardless of which eligible bond is cheapest.

---

### 2D. Currency Forwards & Futures

Currencies are treated like an asset with a **continuous "yield"** equal to the foreign risk-free rate (r_f):

**[[Covered interest rate parity]] (no-arbitrage pricing):**

$$F_0^{d/f} = S_0^{d/f} \times \frac{(1+r_d)^T}{(1+r_f)^T} \quad \text{(periodic)}$$

$$F_0^{d/f} = S_0^{d/f} \times e^{(r_d - r_f)T} \quad \text{(continuous)}$$

where d/f means "domestic currency per unit of foreign currency."

**Logic:**
- If r_d > r_f → domestic interest rates are higher → the domestic currency is expected to **depreciate** (F₀^(d/f) > S₀^(d/f))
- If r_f > r_d → foreign rates are higher → foreign currency trades at a **forward discount** (F₀^(d/f) < S₀^(d/f))

---

**Curriculum Example:**
- USD/AUD = 0.6200 (spot), r_AUD = 5%, r_USD = 7%, T = 2 years
- F₀ = 0.6200 × (1.07/1.05)² = 0.6200 × (1.0381) = **0.6436**
- AUD expected to depreciate vs USD (higher USD rates)

**GBP/EUR Example:**
- Spot = 0.7920, r_GBP = 1%, r_EUR = 0.3%, T = 1 yr
- F₀ = 0.7920 × (1.01/1.003) = 0.7920 × 1.00697 = **0.7975**

---

**🌎 Real World:** A US company expects to receive €10M in 6 months. To eliminate FX risk, the CFO enters a **currency forward** to sell €10M at the forward rate. This is textbook [[Hedging]]. The forward rate is determined purely by [[Covered interest rate parity]], not by anyone's prediction of where EUR/USD will be in 6 months.

---

## Part 3 – Swaps

> **Key insight:** A swap is economically equivalent to a **portfolio of forward contracts**, one for each settlement date.

---

### 3A. Interest Rate Swaps

**Structure:**
- [[Fixed-rate payer]] (pay fixed, receive floating) = **short a fixed-rate bond, long a floating-rate bond**
- [[Fixed-rate receiver]] (receive fixed, pay floating) = **long a fixed-rate bond, short a floating-rate bond**

```
Company A ──── fixed rate ────► Dealer
Company A ◄─── Libor/MRR ───── Dealer
```

The **[[Swap rate]]** is the fixed rate that makes the swap value = 0 at initiation, i.e., where:

$$B_{fixed} = B_{floating}$$

---

**Pricing – Finding the [[Swap Fixed Rate]] (SFR):**

Since a floating rate bond resets to par at each reset date, B_fl = 1 (per $1 notional). The fixed rate PMT solves:

$$1 = PMT \cdot \sum_{i=1}^{n} DF_i + DF_n$$

$$\boxed{SFR = \frac{1 - DF_n}{\sum_{i=1}^{n} DF_i}}$$

where DF_i = [[Discount factor|discount factor]] for period i = 1/(1+r_i)^i

---

**Curriculum Example – 5-Year Annual Swap:**

| Maturity | [[Discount factor|Discount Factor]] (DF) |
|----------|---------------------|
| 1 | 0.99099 |
| 2 | 0.97788 |
| 3 | 0.96514 |
| 4 | 0.95153 |
| 5 | 0.93747 |
| **Sum** | **4.82211** |

$$SFR = \frac{1 - 0.93747}{4.82211} = \frac{0.06253}{4.82211} \approx \mathbf{1.297\%}$$

---

**[[Swap Valuation]] (after initiation):**

For a **receive-fixed, pay-floating** swap:

$$V_{swap} = (SFR_{new} - SFR_{old}) \times \sum DF_i \times NP$$

Or equivalently, value the fixed leg and floating leg as bond positions:

$$V_{swap} = B_{fixed} - B_{floating}$$

$$B_{fixed} = PMT_{old} \cdot \sum DF_i + DF_n$$

Since floating bond always resets to 1 at reset dates: $B_{floating} = 1$ at reset

---

**Curriculum Example:**
- Entered 2 years ago: 7-year swap, €100M, receive-fixed at **2.00%**, annual resets
- Today's [[Swap rate|swap rate]] = **1.2968%** (from DF table above)
- V_swap = (0.02 − 0.012968) × 4.82211 × 100M = **€3,390,905**

---

**🌎 Real World:** [[Fixed-for-floating interest rate swaps]] are the largest segment of the OTC [[Derivatives|derivatives]] market (notional outstanding in the hundreds of trillions). A classic use case: a bank makes **floating-rate loans** but **funds itself with fixed-rate deposits**. It enters a swap to receive floating and pay fixed, aligning its cash flows. Corporate issuers often do the reverse — issue floating-rate debt, then swap to fixed.

---

### 3B. Currency Swaps

**Structure:**
- Exchange **[[Notional principal|notional principal]]al|principal]]** in two [[Currencies|currencies]] at initiation AND at expiration
- Exchange fixed (or floating) interest payments in each currency throughout

**Pricing:**

Think of the [[Currency swap|currency swap]] as **two fixed-rate bonds in different [[Currencies|currencies]]**:

$$V_{swap} = V_D - S_0^{d/f} \times V_F$$

At initiation, V_swap = 0, so:
$$V_D = S_0^{d/f} \times V_F$$

The swap rates in each currency are set so the values of both bond legs are equal (at the spot exchange rate).

---

**Curriculum Example – 1-Year AUD/USD Swap:**
- US Company wants A$100M, AUD/USD = 1.1400
- Calculate DF for both AUD and USD legs:

| Period | AUD Rate | AUD DF | USD Rate | USD DF |
|--------|----------|--------|----------|--------|
| Q1 (90d) | 2.50% | 0.99381 | 0.10% | 0.99975 |
| Q2 (180d) | 2.60% | 0.98712 | 0.15% | 0.99925 |
| Q3 (270d) | 2.70% | 0.98007 | 0.20% | 0.99850 |
| Q4 (360d) | 2.80% | 0.97270 | 0.25% | 0.99750 |
| **Sum** | | **3.93370** | | **3.99500** |

AUD [[Swap rate|swap rate]] = (1 − 0.97270) / 3.93370 = **0.6942%** per quarter → **2.7767% per year**
USD [[Swap rate|swap rate]] = (1 − 0.99750) / 3.99500 = **0.0626%** per quarter → **0.2504% per year**

US company pays USD at 0.0626%/quarter on $87.72M (= A$100M / 1.1400), receives AUD at 0.6942%/quarter on A$100M.

**[[Valuation|Valuation]] after 60 days (300 days remaining):**

$$V_{swap} = V_D^{USD} - \frac{A\$100M}{1.1400} \times V_F^{AUD}$$

With new rates/DFs → compute updated present values of each leg.

---

**🌎 Real World:** [[Cross-currency swaps]] are essential for **multinational corporations**. An American company issuing bonds in Japan gets yen it doesn't need. It enters a [[Currency swap|currency swap]]: pays USD fixed to a counterparty, receives JPY fixed → uses JPY to service Japanese bond. At maturity, the notional is re-exchanged. This effectively converts Japanese yen debt into USD debt at a potentially lower cost than borrowing directly in USD.

---

### 3C. Equity Swaps

**Structure:**
- One party pays the **equity return** (capital gain + dividends, or just [[Price return|price return]])
- Other party pays either **fixed, floating, or another equity return**

**Types:**
| Leg A | Leg B |
|-------|-------|
| Equity return | Fixed rate |
| Equity return | Floating (Libor/MRR) |
| Equity return (index A) | Equity return (index B) |

---

**Pricing ([[Swap rate|Swap Rate]]):**

Same formula as [[Interest rate|interest rate]]te swap|[[Interest rate|interest rate]] swap]]:

$$SFR = \frac{1 - DF_n}{\sum_{i=1}^{n} DF_i}$$

---

**[[Valuation|Valuation]]:**

**Receive equity, pay fixed:**

$$V_{swap} = \frac{S_t}{S_0} - (SFR_{fixed} \cdot \sum DF_i + DF_n)$$

Per $1 of notional. Scale by NA.

**Receive fixed, pay equity:**

$$V_{swap} = B_{fixed} - \frac{S_t}{S_0}$$

---

**Cash Flow Example (from curriculum):**

- NA = $5M, receive equity, pay fixed at 1.6%/year, quarterly
- Q1: equity index return = +4% → payment = 5M × (4% − 0.4%) = **$180,000** to equity receiver
- Q2: equity index return = −6% → payment = 5M × (−6% − 0.4%) = **−$320,000** (equity receiver pays)

Note: The equity leg can go **negative** — this is a critical difference from a regular [[Long position|long position]].

---

**[[Valuation|Valuation]] Example:**
- 5-year swap, receive fixed (1.5%), pay equity (index), quarterly resets
- 6 months later: index moved from 100 → 105, new swap rate = 1.2%

$$V_{swap} \text{ (receive fixed)} = NP \times \left[(SFR_{old} \cdot \sum DF_i + DF_n) - \frac{S_t}{S_0}\right]$$
$$= 10M \times \left[(0.015 \cdot \sum DF + DF_n) - \frac{105}{100}\right] = \mathbf{-\$369,869}$$

(Negative because equity outperformed the fixed leg)

---

**🌎 Real World:** An asset manager wants **exposure to the S&P 500** without buying equities directly (maybe for regulatory, tax, or [[Balance sheet|balance sheet]] reasons). She enters an [[Equity swap|equity swap]]: pays fixed to a bank, receives S&P 500 [[Total return|total return]]. This is a common technique in **synthetic [[Replication|replication]]** of index exposure. If the index falls, she owes the bank the fixed rate **and** the shortfall — the risk is real.

---

## 📊 Summary: Pricing Formulas at a Glance

| Instrument | Price Formula | Value (Long, mid-life) |
|-----------|---------------|----------------------|
| **Equity Forward (no div)** | F₀ = S₀(1+r)^T | Vₜ = Sₜ − F₀/(1+r)^(T−t) |
| **Equity Forward (discrete div)** | F₀ = (S₀ − PVD)(1+r)^T | Vₜ = (Sₜ − PVDₜ) − F₀/(1+r)^(T−t) |
| **Equity Index (cont. yield δ)** | F₀ = S₀ e^(r−δ)T | Vₜ = Sₜ e^(−δ(T−t)) − F₀ e^(−r(T−t)) |
| **FRA** | f = implied [[Forward rate|forward rate]] | NP × (FR−L) × (days/360) / (1 + L × days/360) |
| **Fixed-Income Forward** | F₀ = [(S₀+AI₀) − PVC](1+r)^T − AI_T | Vₜ = (Sₜ + AIₜ − PVCₜ) − F₀/(1+r)^(T−t) |
| **Currency Forward** | F₀ = S₀ × (1+r_d)^T / (1+r_f)^T | Vₜ = Sₜ^(d/f) / (1+r_f)^(T−t) − F₀/(1+r_d)^(T−t) |
| **IR Swap (SFR)** | SFR = (1 − DF_n) / ΣDF | V = (SFR_new − SFR_old) × ΣDF × NP |
| **[[Currency swap|Currency Swap]]** | Set rates so V_D = S₀ × V_F | V = V_D − S_t × V_F |
| **[[Equity swap|Equity Swap]]** | SFR = (1 − DF_n) / ΣDF | V = Sₜ/S₀ − (SFR × ΣDF + DF_n) |

---

## 🧠 Conceptual Distinctions: Forwards vs. Futures

| Feature | [[Forward Contract\|Forward]] | [[Futures Contract\|Futures]] |
|---------|----------|---------|
| Trading venue | OTC (bilateral) | Exchange |
| Customization | Fully customizable | Standardized |
| [[Credit risk|Credit risk]] | [[Counterparty risk|Counterparty risk]] | Cleared, minimal |
| [[Settlement|Settlement]] | At expiration only | Daily [[Mark-to-Market]] |
| Value between dates | Vₜ = Sₜ − F₀/(1+r)^(T−t) | vₜ = fₜ − fₜ₋₁ (daily reset) |
| Pricing equivalence | Same no-[[Arbitrage|arbitrage]] price if rates are non-stochastic | |

---

## ❓ Exam Tips & Common Pitfalls

> [!tip] Tips for the Exam
> 1. **Forwards vs. Futures pricing**: Prices are theoretically equal when interest rates are non-stochastic. In practice, futures may differ due to [[Correlation|correlation]] between futures prices and interest rates.
> 2. **F₀ is not a forecast**: The [[Forward price|forward price]] reflects carry, not market expectations of the future [[Spot price|spot price]].
> 3. **Dividend announcements**: If a dividend is announced mid-life, the [[Forward value|forward value]] falls *even if the [[Spot price|spot price]] doesn't change* (because PVD rises).
> 4. **FRA [[Settlement|settlement]]**: FRAs are *[[Advanced set|advanced set]], [[Advanced settled|advanced settled]]* — the payoff is discounted because you receive cash at the start of the loan period, not the end.
> 5. **Swap rate formula**: Always: SFR = (1 − last DF) / sum of all DFs. Memorize this cold.
> 6. **[[Currency swap|Currency swap]]**: Always identify which party is "domestic" and which is "foreign." F₀^(d/f) means domestic per foreign — higher domestic rates → forward > spot.
> 7. **[[Equity swap|Equity swap]] cash flows can be negative**: The equity leg is not floored at zero.

> [!warning] Common Mistakes
> - Forgetting to subtract PV of dividends/coupons from S₀ when pricing
> - Using the wrong [[Compounding|compounding]] convention (continuous vs. periodic)
> - Confusing the FRA fixed rate with the [[Settlement|settlement]] rate
> - Misidentifying the CTD bond (pick the one with **lowest** cost-to-deliver)
> - Mixing up bid/ask in currency quotes (always check which currency is in the numerator)

---

## 🔗 Related Notes

- [[CFA L2 Module 2 – Valuation of Contingent Claims]]
- [[No-Arbitrage Pricing]]
- [[Covered interest rate parity]]
- [[Forward rate agreement]]
- [[Interest rate swap]]
- [[Duration Management with Futures]]
- [[Cheapest-to-Deliver Bond]]

---

*Sources: CFA Program Curriculum 2025, Level II, Volume 7 ([[Derivatives|Derivatives]]); MarkMeldrum 2025 L2 Derivatives Notes*
