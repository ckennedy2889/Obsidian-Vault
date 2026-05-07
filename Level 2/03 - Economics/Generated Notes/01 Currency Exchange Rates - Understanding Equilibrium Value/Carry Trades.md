---
title: Carry Trades
subject: Economics
tags: [CFA-L2, Economics, Currency, FX, CarryTrade, UIRP, InterestRateParity, ForwardRateBias, RiskPremium, NegativeSkew, FatTails, JPY, AUD]
aliases: [FX Carry Trade, Currency Carry, Carry Strategy, JPY Carry Trade, Yen Carry Trade]
---

# Carry Trades

> [!abstract] The One-Sentence Version
> A carry trade is the bet that **uncovered interest rate parity is wrong in the short run** — so you borrow in the cheap currency, park the money in the rich-yielding currency, and pocket the rate difference, *knowing* that the same statistical regularity that pays you steadily can also blow up in your face when the world panics.

> [!success] What This Note Lets You Do — LOS Contract
> **Reading:** Economics — *Currency Exchange Rates: Understanding Equilibrium Value*
>
> **LOS:** *"describe the carry trade and its relation to uncovered interest rate parity and calculate the profit from a carry trade"*
>
> This single LOS has **three action verbs**. After reading this note you will be able to:
> 1. **DESCRIBE** the carry trade — name the two currencies, their roles, and the five-step mechanic (§§ 1–3).
> 2. **DESCRIBE its relation to UIRP** — state what UIRP predicts, why its empirical failure is the *source* of carry-trade profit, and why Covered IRP does *not* enable the same trade (§ 6).
> 3. **CALCULATE the profit** — derive and apply the CFA return formula, and walk an unwind end-to-end in currency units (§§ 4–5).
>
> Sections 7–11 are *beyond the LOS* but round out the exam-ready picture (return distribution, crash dynamics, exam traps). Jump to the **LOS Self-Check** at the end to confirm mastery.

---

## 1. DESCRIBE — The Real-World Analogy: Renting Money From Japan, Lending It to Australia

Imagine your neighbor in Tokyo is running a chronic surplus of cash and doesn't know what to do with it. His local bank pays him essentially nothing — the Bank of Japan has pinned short rates near zero for the better part of thirty years. Meanwhile, a rancher in Queensland is borrowing at a hefty rate to expand his cattle operation, because the Reserve Bank of Australia has always run a tighter monetary policy and commodity-linked economies tend to pay investors more to hold their currency.

You are the middle-person. You ask the Tokyo neighbor to **lend you ¥10,000,000 at 0.10%**. You fly to Sydney, swap the yen for Australian dollars at today's exchange rate, and put the AUD into a one-year term deposit paying **4.35%**. Twelve months later you cash out, swap the AUD back into JPY, repay your Tokyo neighbor — and the difference is yours to keep.

That's the whole mechanic. You are literally renting money in one country and lending it in another, harvesting the interest spread. The risk isn't that either deposit fails — those are contractual. The risk is the **exchange rate between the two currencies moves against you** during the year, eating your spread (or worse, your principal).

A real-world cross-section of today's short rates makes the temptation obvious:

| Central Bank | Policy rate (approx., late 2025 / early 2026) | Role in carry trades |
|---|---|---|
| Bank of Japan | ~0.50% | Classic **funding currency** (low-yielder) |
| Swiss National Bank | ~0.25% | Classic **funding currency** (safe haven) |
| US Federal Reserve | ~4.25–4.50% | Funding when global rates are higher |
| ECB (Eurozone) | ~2.25% | Middle of the pack — sometimes funding |
| Reserve Bank of Australia | ~3.85% | Historic **investment currency** (high-yielder) |
| Brazilian Central Bank (Selic) | ~13%+ | EM **investment currency** — juicy but volatile |
| Banco de México | ~10% | EM **investment currency** |
| Turkish Central Bank | 40%+ | Extreme high-yielder; often a *trap* |

Borrow JPY at 0.50%, park it in Brazilian real at 13%, and your paper carry is **12.5 percentage points a year**. That's the steak. The sizzle — and the risk — is whether BRL/JPY stays put.

---

## 2. DESCRIBE — The Two Currencies: Funding vs. Investment

Every carry trade has exactly two legs, and you need to be able to name them in your sleep:

- The **funding currency** (also called the **low-yielder** or **source currency**) is the one you borrow. You want its interest rate *low* and, ideally, you want its value to *fall or stay flat* after you borrow — because you'll eventually have to buy it back to repay the loan, and you want it to be cheap.
- The **investment currency** (also called the **high-yielder**, **target currency**, or **destination currency**) is the one you hold. You want its interest rate *high* and, ideally, you want it to *hold its value or appreciate* during your holding period.

> [!tip] Memory Hook — **"LOW → HIGH → HOME"**
> You borrow **LOW** (funding), you sit in **HIGH** (investment), then you come **HOME** (unwind the FX trade and repay). If you forget which side is which on exam day: the funding currency is the one you are *short* — you owe it, so you want it weak.

### Who Has Historically Played Each Role

- **Classic funding currencies:** [[Japanese Yen|JPY]] (near-zero rates for decades), [[Swiss Franc|CHF]] (safe-haven, low rates), USD in the ZIRP era (2009–2015, 2020–2022).
- **Classic investment currencies:** [[Australian Dollar|AUD]], [[New Zealand Dollar|NZD]] ("the Kiwi"), [[Brazilian Real|BRL]], [[Mexican Peso|MXN]], [[Turkish Lira|TRY]], [[South African Rand|ZAR]]. Commodity exporters and emerging markets dominate the list because their central banks pay up to attract capital.

---

## 3. DESCRIBE — The Diagram: Mechanic and Crash Branch

The whole life cycle of the trade, including the risk-off tail, is compressed into one picture. Spend sixty seconds on this before reading the math section — it'll all click faster.

![[carry-trade-mechanic.excalidraw]]

The top half is the calm-market scenario: five steps from "borrow ¥100" to "pocket ¥1.41." The bottom half is the same trader when the global mood flips — a risk-off shock kicks JPY up, kicks AUD down, triggers margin calls, and unwinds months of gains in a single week. That asymmetric shape is the whole story of carry-trade returns.

---

## 4. CALCULATE — The Return Formula From the Ground Up

Every carry-trade payoff has exactly two moving parts: the **interest differential** you earn and the **change in the exchange rate** while your money was parked abroad.

### 4.1 Building the Formula From First Principles

Suppose you borrow one unit of the funding currency ($1$ JPY, to make the algebra clean) at interest rate $i_f$. You convert it to the investment currency at the current **spot rate** $S_{f/h}$ — read "funding per unit of high-yielder" — meaning one unit of the investment currency costs $S_{f/h}$ units of funding. (For our JPY/AUD trade, $S_{f/h} = 71.78$ means one AUD costs ¥71.78.)

One yen therefore buys $1 / S_{f/h}$ units of AUD. You put that AUD on deposit at the investment rate $i_h$. One year later it has grown to:

$$
\frac{1}{S_{f/h}} \cdot (1 + i_h)
$$

At that point you convert back to JPY. The new spot rate is $S'_{f/h}$ (the prime means "one year later"). Your yen are now:

$$
\frac{1 + i_h}{S_{f/h}} \cdot S'_{f/h}
$$

But you also owe your Tokyo lender $1 + i_f$ yen. So your **profit per yen borrowed** is:

$$
\pi = \frac{S'_{f/h}}{S_{f/h}} \cdot (1 + i_h) \;-\; (1 + i_f)
$$

That's the **exact** formula — it compounds both effects correctly. For exam purposes, though, the CFA curriculum uses a **linearized approximation** that comes out of a first-order Taylor expansion when rates and FX moves are small:

$$
\boxed{\,R_{\text{carry}} \;\approx\; \underbrace{(i_h - i_f)}_{\text{interest differential}} \;-\; \underbrace{\%\Delta S_{h/f}}_{\text{depreciation of investment CCY}}\,}
$$

> [!warning] Quote Convention Trap
> The minus sign is only correct when $\%\Delta S$ is expressed as the **change in price of the investment currency measured in funding currency**. If the investment CCY *depreciates* (goes down) against the funding CCY, $\%\Delta S$ is negative and subtracts a negative — giving you a *boost*. If the investment CCY *appreciates*, $\%\Delta S$ is positive, which *reduces* your return. This is the opposite of the more intuitive "depreciation hurts you" framing — because remember, the depreciation that hurts you is the *funding* currency strengthening, which is the *investment* currency weakening. Read the quote carefully.

### 4.2 The L2 Quick-Form

CFA Level 2 often writes the same idea even more compactly:

$$
R_{\text{carry}} \approx (i_h - i_f) - (\%\Delta S_{h/f})
$$

with the reminder that **%Δ S is negative if the investment currency weakens against the funding currency**. Memorize both the intuition and the sign.

---

## 5. CALCULATE — Worked Example: ¥100 Into AUD for One Year

Let's grind through the exact numbers that appear in the diagram, so the formula lands. Borrow ¥100 in Tokyo, deploy into AUD, unwind after twelve months.

| Step | Action | Calculation | Result |
|---|---|---|---|
| 1 | Borrow funding | ¥100 at $i_f = 0.10\%$ | Owe ¥100.10 in one year |
| 2 | Convert to investment CCY | ¥100 ÷ 71.78 JPY/AUD | AUD 1.3931 |
| 3 | Invest at $i_h = 1.70\%$ for 1 yr | 1.3931 × (1 + 0.017) | AUD 1.4168 |
| 4 | Convert back to JPY | 1.4168 × 71.65 JPY/AUD | ¥101.51 |
| 5 | Repay loan | ¥101.51 − ¥100.10 | **Profit ¥1.41 (+1.41%)** |

Now let's verify with the approximation formula:

$$
R_{\text{carry}} \approx (1.70\% - 0.10\%) - \%\Delta S_{\text{AUD/JPY}}
$$

The AUD depreciated slightly against JPY: from 71.78 → 71.65 JPY/AUD is a −0.18% move in the investment currency. Plugging in:

$$
R_{\text{carry}} \approx (1.60\%) - (-0.18\%) = +1.78\%
$$

The exact calculation gave +1.41%; the linear approximation gives +1.78%. The ~0.4 percentage point gap is compounding noise — the textbook formula is a first-order approximation, and the *exact* calculation respects $(1 + i_h)$ compounding. **For the exam, use the approximation unless asked for an exact unwind.**

> [!note] Why the AUD "depreciated only a little"
> In the CFA example, the FX move is *small*. That's the whole profit regime — carry traders make money when FX behaves as if UIRP is false (the interest-rate gap does *not* fully reverse in the spot market). If AUD had depreciated by the full 1.60% gap, the trade would have broken even, which is exactly what UIRP predicts.

---

## 6. DESCRIBE THE RELATION TO UIRP — Why Carry Trades Shouldn't Work (But Do)

This is the piece most students miss. Carry trades sit at the intersection of three FX parity relations — and understanding which one they rely on failing is exam catnip.

### 6.1 Covered Interest Rate Parity (CIRP) — The Ironclad One

**Covered IRP** says that if you hedge your FX exposure with a forward contract locked in today, the interest-rate differential is *exactly* offset by the forward premium/discount:

$$
F_{h/f} = S_{h/f} \cdot \frac{1 + i_f}{1 + i_h}
$$

CIRP holds essentially by arbitrage — if it didn't, a bank could borrow in one currency, swap into the other, lend at the higher rate, and lock the unwind in the forward market for a riskless profit. Because CIRP holds, **a fully hedged carry trade has zero expected return**. If you bought a forward to guarantee your JPY unwind, the forward price would bake in the 1.60% rate gap and wipe out your profit.

> [!danger] Exam Trap #1 — "Hedged Carry Trade"
> If a vignette tells you the trader *hedged* the FX leg with a forward, the carry trade **has no edge**. CIRP holds, and the forward price exactly eats the interest differential. Carry trades are by definition **unhedged** — that's why they work, and that's why they blow up.

### 6.2 Uncovered Interest Rate Parity (UIRP) — The One That Fails

**Uncovered IRP** says that the spot rate's *expected* future move should offset the interest-rate differential:

$$
E[\%\Delta S_{h/f}] \;=\; i_h - i_f
$$

In plain English: the market "should" expect the high-yield currency to depreciate by exactly the interest-rate gap, making all currencies equal in expected return.

**UIRP does not hold empirically in the short and medium run.** In fact, high-yield currencies tend to *appreciate*, not depreciate — the opposite of UIRP's prediction. This is the **forward rate bias** (sometimes called the **forward puzzle** or **Fama puzzle**). The carry trade *is the trade* that exploits this bias.

### 6.3 Forward Rate Bias — The Workhorse

If UIRP doesn't hold, then the forward exchange rate — which prices in the interest-rate gap via CIRP — is a **biased predictor** of the future spot rate. Specifically:

- The forward rate shows the high-yielder depreciating (because CIRP demands it).
- In reality, the high-yielder on average *holds steady or even appreciates*.
- **Selling the forward** (i.e., locking in the "predicted depreciation") and **holding the spot** (receiving the actual "no depreciation") is the structural carry-trade bet.

This is why some textbooks describe the carry trade as "selling the forward premium" — mechanically identical.

### 6.4 Summary Table

| Parity | What it says | Does it hold? | Role in carry trade |
|---|---|---|---|
| **CIRP** (Covered) | Forward price offsets rate gap exactly | **Yes** (arbitrage) | Explains why a *hedged* carry trade earns zero |
| **UIRP** (Uncovered) | Expected spot move offsets rate gap | **Not in the short run** | Its failure is the *source* of carry-trade profits |
| **Forward Rate Bias** | Forward ≠ unbiased predictor of future spot | **Yes — it is biased** | The statistical regularity carry traders sell |

> [!tip] Memory Hook — **"COVER LOCKS, UNCOVERED ROLLS"**
> Covered parity *locks* the price with a forward — it holds because arbitrageurs keep it honest. Uncovered parity just *rolls* along hoping the spot market behaves — and the spot market doesn't. That gap is the carry trader's lunch.

---

---

> [!info] Beyond the LOS — Exam-Ready Risk Context
> The LOS only demands *describe the carry trade, describe its UIRP link, and calculate profit*. Sections 7–11 go past that into return distribution, crash dynamics, volatility regimes, and exam traps — knowledge that doesn't sit under this single LOS but routinely appears in vignettes and multi-part items. Skim these the first time, return for a second pass closer to exam.

---

## 7. The Return Distribution — Negative Skew and Fat Tails

Now for the nuance that separates a smart carry trader from a naive one. If you plot the histogram of monthly carry-trade returns over the last thirty years, it does **not** look like a normal bell curve.

```
   freq                     ▌▌
    ▲                    ▌▌▌▌▌▌
    │                 ▌▌▌▌▌▌▌▌▌▌        ← most months: small gain
    │              ▌▌▌▌▌▌▌▌▌▌▌▌▌▌
    │           ▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌
    │       ▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌
    │  ▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌▌
    │   ← long, skinny left tail (the steamrollers)
    └────────────────────────────────────▶ return
   −20%     −10%      0%       +2%        +5%
```

Two statistical features drive the whole psychology of the strategy:

### 7.1 Negative Skewness

Most months the trade grinds out a small positive return — the interest differential, chipped off month by month. But occasionally the trade takes a huge hit, far larger than any single positive month. The distribution is lopsided: the right tail (gains) is short and tidy, the left tail (losses) is long and brutal.

### 7.2 Excess Kurtosis (Fat Tails / Leptokurtosis)

Extreme events happen **far more often** than a normal distribution would predict. A 5-sigma monthly loss in carry returns is not a once-in-a-thousand-years event — historically it's occurred multiple times per decade (1998 LTCM unwind, 2008 GFC, 2011 SNB shock warm-up, 2015 CHF peg break, 2020 COVID, 2024 BOJ surprise hike). **Fat tails mean risk is worse than any normal-distribution VaR says it is.**

### 7.3 "Picking Up Nickels in Front of a Steamroller"

This is the industry's own description of the trade, and it captures the emotional profile perfectly. Every month you bend down, pick up the 1%–2% interest-rate nickel, and walk forward. Every month there's a tiny chance the steamroller rolls up behind you and flattens everything. Most traders never see the steamroller — until, one day, they do.

The corollary: **Sharpe ratios of carry strategies look magnificent during calm periods and catastrophically bad through a crash**. Pre-2008 JPY carry strategies were pitched at Sharpe > 1.0; the 2008 realized path showed the strategy lose in weeks what it had earned in years.

---

## 8. Why Carry Trades Crash — The Feedback Loop

Understanding *why* the left tail is so fat is what separates memorization from mastery. It isn't random bad luck — it's an identifiable feedback loop.

1. **Calm begets leverage.** When volatility is low, carry trades look safe, so hedge funds and macro desks add *leverage* (borrow more yen, deploy more AUD). A 1.5% annual carry becomes 15% after 10x leverage. This pulls more capital in.
2. **Crowded positioning.** Nearly every global macro book holds the *same* long-AUD, short-JPY position. The trade is no longer hidden — it's public knowledge.
3. **Shock arrives.** Something unexpected hits: a US data surprise, a BOJ policy pivot, a risk-asset sell-off, a geopolitical event. [[VIX]] spikes.
4. **Flight-to-quality bid lifts the funding currency.** In global panic, money rushes *toward* low-risk havens like JPY, CHF, USD. So the currency you are *short* suddenly appreciates — the worst possible move for your carry trade.
5. **Margin calls hit.** Your leveraged AUD/JPY position has moved against you on *both* legs: JPY up and AUD down. The prime broker demands more collateral. You can't meet it.
6. **Forced unwind.** You have to sell AUD and buy JPY — *at the worst possible moment*. So do all the other macro books. The trade unwinds in unison.
7. **The move gets worse.** The unwind itself pushes JPY higher and AUD lower, triggering more margin calls, more unwinds, a cascade. In August 2024, USD/JPY dropped ~8% in a week on exactly this dynamic when the BOJ surprised with a hike. Global equities crashed in sympathy — because carry trades fund more than just FX, they fund risk assets everywhere.

> [!danger] Exam Trap #2 — Safe Havens and Carry
> Know the reflex: **in a flight-to-quality, the funding currencies (JPY, CHF, USD) strengthen**. This is the opposite of what a carry trader needs. The very moment global markets sell off is the very moment the carry trade takes its worst hit. That correlation between crashes in carry and crashes in risk assets is *why* carry returns have such a fat left tail.

---

## 9. The Volatility Environment — Carry Loves Calm

Carry trades have one environmental variable they worship: **low volatility**. Specifically, low *realized* FX volatility and low *implied* volatility (measured by FX option prices and [[VIX|equity VIX]] as a proxy for global risk appetite).

| Regime | Carry-trade performance | Why |
|---|---|---|
| Low vol, low VIX (e.g., 2003–2007, 2017) | **Excellent** — nickels flow, leverage builds | FX stays range-bound; differential dominates |
| Moderate vol (e.g., 2012–2014) | Mixed — some trades work, some don't | Idiosyncratic FX moves start eating differentials |
| High vol / risk-off (e.g., 2008, 2020) | **Catastrophic** — steamroller arrives | Safe-haven bid + forced unwinds |

Professional macro funds now build "carry throttles" into their models: when realized vol exceeds a threshold, they *automatically cut position size* regardless of the current carry level. This is the mechanical version of "watch for the steamroller."

---

## 10. Beyond FX — Other Flavors of "Carry"

The core idea — *earn a yield spread between two assets and hope the price doesn't move against you* — generalizes well beyond FX. CFA Level 2 focuses on the FX version, but you'll see these echoed in other parts of the curriculum:

| Carry Type | Funding leg | Investment leg | Tail risk |
|---|---|---|---|
| **FX carry** (this note) | Low-yield currency | High-yield currency | FX shock / safe-haven bid |
| **Fixed-income carry / Rolldown** | Short-term funding | Long-term bonds | Rate shock / curve steepening |
| **Credit carry** | Treasuries | Corporate bonds | [[Credit Spreads|Spread widening]] / default |
| **Volatility carry** | Short options | Realized vol | Vol spike / gap move |
| **Equity carry (dividends)** | Margin loan | High-dividend stocks | Equity drawdown |

Every one of these strategies shares the same distributional DNA: small steady gain most of the time, huge occasional loss. If you ever see the phrase "short volatility" in a vignette, think *same shape as carry*.

---

## 11. Common CFA Exam Traps

The CFA Level 2 curriculum likes testing a handful of tight, nuanced points about carry trades. Commit these to muscle memory:

> [!danger] Trap Checklist
> 1. **Covered ≠ Uncovered.** A *covered* (forward-hedged) carry trade earns zero because CIRP holds. Only the *uncovered* carry trade earns the differential — and only because UIRP fails.
> 2. **Direction of the FX risk.** The trade loses when the *funding* currency *strengthens* (equivalently, the *investment* currency *weakens*). Vignettes will test this with deliberately awkward quote conventions — read slowly.
> 3. **Not a free lunch.** Carry trades earn a **risk premium** for bearing crash risk. The *expected* return in an efficient risk-adjusted world is not "free" — it's compensation for leptokurtic, negatively-skewed losses.
> 4. **Forward rate bias.** The forward rate implied by CIRP is a *biased* predictor of the future spot. Carry trades profit from exactly that bias.
> 5. **Flight to quality.** Safe-haven currencies (JPY, CHF, USD) *rally* in risk-off regimes — the worst possible environment for a carry trader short those currencies.
> 6. **Sharpe ratios overstate.** Standard Sharpe ratios assume normal returns. For carry, skew and kurtosis make Sharpe misleading — use Sortino, max drawdown, or tail metrics instead.

---

## 12. Putting It All Together — The Three-Line Summary

When the exam question lands, these three sentences should fire instantly:

1. **Mechanic:** Borrow the funding (low-yield) currency, convert to the investment (high-yield) currency, invest at the higher rate, unwind and repay. Profit ≈ (i_high − i_low) − %Δ spot of investment currency.
2. **Theory:** Carry trades profit because UIRP fails — high-yielders don't depreciate as UIRP predicts. CIRP holds, so any hedged version of the trade earns nothing.
3. **Risk:** Returns are negatively skewed with fat left tails. Most months small gains, occasional crashes during risk-off / flight-to-quality events when the funding currency rallies.

> [!tip] Final Mnemonic — **"B.L.A.S.T."**
> **B**orrow low, **L**end high, **A**rbitrage? no — you're naked on FX, **S**keleton of the trade is UIRP failing, **T**ail risk is the steamroller. If you can recite BLAST, you can answer any carry-trade vignette.

---

## LOS Self-Check — Can You Now…?

> [!question] LOS: *"describe the carry trade and its relation to uncovered interest rate parity and calculate the profit from a carry trade"*
>
> Run this check without looking at the note. If you stumble on any item, re-read the cross-referenced section.
>
> **DESCRIBE the carry trade**
> - [ ] Can you state the five-step mechanic (borrow → convert → invest → unwind → repay) without notes? *(§ 3)*
> - [ ] Can you name the **funding currency** vs. **investment currency** and say which interest rate is higher in each? *(§ 2)*
> - [ ] Can you list three classic funding currencies and three classic investment currencies? *(§ 2)*
>
> **DESCRIBE its relation to UIRP**
> - [ ] Can you state UIRP in one sentence — what it predicts about expected spot moves? *(§ 6.2)*
> - [ ] Can you explain why the *empirical failure* of UIRP is precisely the source of carry profit? *(§ 6.2)*
> - [ ] Can you explain why a **Covered IRP–hedged** version of the trade earns zero? *(§ 6.1)*
> - [ ] Can you connect the trade to the **forward rate bias** — i.e., that the forward rate is a biased predictor of the future spot? *(§ 6.3)*
>
> **CALCULATE the profit**
> - [ ] Can you write the approximation formula $R_{\text{carry}} \approx (i_h - i_f) - \%\Delta S_{h/f}$ from memory? *(§ 4.2)*
> - [ ] Can you say which sign convention applies — when the investment CCY **appreciates** vs. **depreciates** against the funding CCY, what happens to your return? *(§ 4.1 warning box)*
> - [ ] Given a borrow amount, two interest rates, and an initial and ending spot quote, can you walk the trade through steps 1–5 and compute the ending profit in funding-currency units? *(§ 5)*
> - [ ] Can you reconcile the *exact unwind* with the *linearized formula* — i.e., why they differ by a small compounding term? *(§ 5)*
>
> **If every box is checked, the LOS is discharged.** If not, go back to the section(s) cited.

---

## Related Notes

- [[Currency Exchange Rates - Understanding Equilibrium Value]] — the broader FX module this sits inside
- [[Covered Interest Rate Parity]]
- [[Uncovered Interest Rate Parity]]
- [[Forward Rate Bias]]
- [[Spot Exchange Rate]]
- [[Forward Exchange Rate]]
- [[Flight to Quality]]
- [[VIX]]
- [[Skewness and Kurtosis]] (from [[02 - Quantitative Methods]])
- [[Credit Spreads]] (carry analogue in fixed income)
