---
title: Duration Types — A Side-by-Side Contrast
subject: Fixed Income
tags: [CFA-L2, fixed-income, duration, interest-rate-risk, embedded-options, credit-risk]
aliases: [Types of Duration, Duration Comparison, Yield vs Curve Duration]
---

# Duration Types — A Side-by-Side Contrast

## 1. Real-World Analogy

Imagine you own a portfolio of buildings and someone asks: *"How exposed are you to weather?"* That's not one question — it's many. Are you asking about **average rainfall** (a smooth, parallel risk), or **a single hurricane hitting Miami** (a localized shock), or **how the roof reacts asymmetrically to hail vs. sunshine** (a one-sided risk), or about **insurance premiums rising independently of the weather itself** (spread risk)?

"Duration" works the same way. It is *not* one number — it is a **family of sensitivity measures**, each engineered to answer a different question about how a bond's price moves when *something* changes. The trick at L2 is knowing which member of the family is the right tool for the bond in front of you.

## 2. Plain-English Definition

**Duration = the slope of a bond's price–rate curve.** It tells you "if the relevant rate moves a little, how much does my price move?" The disagreements among duration types are about (a) *which rate* is moving, (b) *which assumption* you make about the cash flows, and (c) *what units* the answer is reported in.

The CFA curriculum splits durations into three big buckets:

| Bucket | What it reacts to | Use when… |
|---|---|---|
| **Yield duration** | The bond's *own* YTM | Cash flows are fixed and certain (option-free bonds) |
| **Curve duration** | The benchmark *yield curve* | Cash flows are uncertain (embedded options, MBS, callables/putables) |
| **Spread duration** | The bond's *credit/OAS spread* | You want to isolate credit risk from rate risk |

Empirical duration sits outside this taxonomy — it's an **observed**, regression-based number rather than an analytical formula.

## 3. The Eight Duration Measures

### 3.1 Macaulay Duration (MacDur) — *Yield duration, in years*

The weighted-average time until you get your money back, where each cash-flow time is weighted by the **present value share** that cash flow contributes to the bond's full price.

$$\text{MacDur} = \sum_{t=1}^{N} t \cdot \frac{PV(CF_t)}{PV_{\text{Full}}}$$

**Mechanism — the "sweet spot":** At horizon = MacDur, the loss from price risk (rates rose, bond worth less) exactly offsets the gain from reinvestment risk (rates rose, coupons earn more). It is the **immunization horizon** for an option-free bond.

**Units:** years. **Bond type:** option-free, fixed-rate. For a zero-coupon bond, MacDur = maturity.

→ See [[Macaulay duration]].

### 3.2 Modified Duration (ModDur) — *Yield duration, in %*

A linear estimate of the **% price change** for a 100 bp change in the bond's own YTM.

$$\text{ModDur} = \frac{\text{MacDur}}{1 + r}, \qquad \%\Delta P \approx -\text{ModDur} \cdot \Delta y$$

The $1/(1+r)$ adjustment converts MacDur from a time measure into a true derivative of price w.r.t. yield. It's the *first-order Taylor term* of the price–yield function.

**Failure mode:** Assumes cash flows don't change when yields change. The instant a bond has an embedded option, that assumption breaks — and you must switch to **effective duration**.

→ See [[Modified duration]].

### 3.3 Money Duration (a.k.a. Dollar Duration) — *Yield duration, in currency*

$$\text{MoneyDur} = \text{AnnModDur} \times PV_{\text{Full}}$$
$$\Delta P \text{ (in \$)} \approx -\text{MoneyDur} \cdot \Delta y$$

Same risk as ModDur, but expressed in currency, not %. Useful at the **portfolio** level when you care about dollars-at-risk, not percent-at-risk. The related **PVBP** (price value of a basis point) = MoneyDur × 0.0001.

→ See [[Money duration]].

### 3.4 Effective Duration (EffDur) — *Curve duration, in %*

$$\text{EffDur} = \frac{V_- - V_+}{2 \cdot V_0 \cdot \Delta\text{Curve}}$$

Bumps the **entire benchmark curve** up by ΔCurve and down by ΔCurve, reprices the bond (using a binomial tree or Monte Carlo for option-bearing bonds), and measures the symmetric percentage change.

**Why it replaces ModDur for option-bearing bonds:** When rates fall, a callable bond gets called → cash flows shorten → price ceiling at the call price. ModDur, blind to this, overstates the upside and is just *wrong*. EffDur captures it because $V_-$ is computed with the option exercised.

→ See [[Effective duration]].

### 3.5 Key Rate Duration (a.k.a. Partial Duration) — *Curve duration, decomposed*

$$\text{KeyRateDur}_k = -\frac{1}{PV} \cdot \frac{\Delta PV}{\Delta r_k}$$

EffDur shifts the *whole* curve in parallel. Key rate duration shifts **only one tenor** (say the 5-year par rate) and holds the rest fixed — measuring sensitivity to **shaping risk** (steepening, flattening, butterfly twists).

Property: $\sum_k \text{KeyRateDur}_k = \text{EffDur}$.

→ See [[Key rate duration]] and [[Key Rate Duration]].

### 3.6 One-Sided Durations — *Curve duration, asymmetric*

For an at-the-money callable bond, the "up bump" and "down bump" don't produce symmetric price moves. **One-sided duration** computes them separately:

$$\text{EffDur}_{\text{up}} = \frac{V_0 - V_+}{V_0 \cdot \Delta\text{Curve}}, \qquad \text{EffDur}_{\text{down}} = \frac{V_- - V_0}{V_0 \cdot \Delta\text{Curve}}$$

For a **callable** bond near the call price: down-duration < up-duration (price capped above). For a **putable** bond: up-duration < down-duration (price floored below). Standard EffDur averages them and *hides* this asymmetry.

→ See [[One-sided durations]] and [[One-Sided Durations]].

### 3.7 Spread Duration — *Spread sensitivity, in %*

$$\%\Delta P \approx -\text{SpreadDur} \cdot \Delta\text{Spread}$$

Holds the benchmark curve fixed and asks: "if my OAS / Z-spread / nominal spread moves 100 bp, how much does my price move?" The risk being measured is **credit + liquidity**, not rates. For Treasuries, spread duration = 0. For a high-yield corporate, it's the dominant risk.

For a **CDS**: $\%\Delta P_{\text{CDS}} \approx \Delta\text{Spread}_{\text{bps}} \times \text{Duration}_{\text{CDS}}$.

→ See [[Spread duration]].

### 3.8 Empirical Duration — *Statistical, from regression*

Instead of a formula, **regress** the bond's actual historical returns on changes in a benchmark yield:

$$\Delta P_t / P_t = \alpha + \beta \cdot \Delta y_t + \varepsilon_t \;\;\Rightarrow\;\; \text{EmpDur} = -\beta$$

Why bother? Because analytical durations assume **rates and spreads are uncorrelated**. In reality — especially in *flight-to-quality* episodes — government yields fall while credit spreads widen, partially offsetting each other. A high-yield bond's empirical duration is therefore typically **lower** (sometimes near zero or even negative) than its analytical EffDur.

→ See [[Empirical duration]].

## 4. The Master Comparison Table

| # | Duration | Bucket | Units | What moves | Cash-flow assumption | Bond type it fits | Key formula |
|---|---|---|---|---|---|---|---|
| 1 | Macaulay | Yield | Years | Bond's own YTM | Fixed | Option-free | $\sum t \cdot w_t$ |
| 2 | Modified | Yield | % | Bond's own YTM | Fixed | Option-free | $\text{MacDur}/(1+r)$ |
| 3 | Money | Yield | Currency | Bond's own YTM | Fixed | Portfolios | $\text{ModDur} \cdot PV$ |
| 4 | Effective | Curve | % | Benchmark curve (parallel) | Variable | Embedded options, MBS, FRNs | $(V_- - V_+)/(2 V_0 \Delta\text{Curve})$ |
| 5 | Key Rate | Curve | % | One tenor on benchmark curve | Variable | Bonds with non-uniform exposure | $-\Delta PV / (PV \cdot \Delta r_k)$ |
| 6 | One-Sided | Curve | % | Curve up *or* down only | Variable | Options near-the-money | $(V_0 - V_+)/(V_0 \Delta\text{Curve})$ |
| 7 | Spread | Spread | % | Credit / OAS spread | Fixed (rates held) | Corporates, CDS | $-\Delta P/(P \cdot \Delta s)$ |
| 8 | Empirical | Statistical | % | Benchmark yield (observed) | Realised history | Risky bonds in stressed regimes | $-\hat{\beta}$ from regression |

## 5. Worked Numerical Example — One Bond, Three Different Duration Numbers

**Setup:** 5-year, 5% annual-coupon, $100 par bond, currently priced at $100 (so YTM = 5%). The bond is **callable at par in year 3**. Benchmark 5-year par rate = 4.5%; the bond trades at a 50 bp Z-spread.

**(a) Modified duration** (treating as if option-free):

$\text{MacDur} \approx 4.55$ years → $\text{ModDur} = 4.55 / 1.05 \approx 4.33$.

So a 100 bp rise in the bond's *own YTM* should drop the price ~4.33%.

**(b) Effective duration** (using a binomial tree, ΔCurve = 25 bp):

Suppose $V_- = 101.20$, $V_+ = 99.10$, $V_0 = 100.00$.

$\text{EffDur} = (101.20 - 99.10) / (2 \cdot 100 \cdot 0.0025) = 2.10 / 0.50 = 4.20$.

EffDur (4.20) < ModDur (4.33) — the **call** truncates the upside, so the bond's true rate sensitivity is lower than the option-free formula suggests.

**(c) One-sided durations:**

- Up: $(100 - 99.10) / (100 \cdot 0.0025) = 3.60$
- Down: $(101.20 - 100) / (100 \cdot 0.0025) = 4.80$

The down-duration (4.80) is *higher* than the up-duration (3.60)? That looks backwards — but recall, the call kicks in *as rates fall further*. At ΔCurve = 25 bp the call hasn't bound yet; push to 50 bp and the down-duration would collapse below the up-duration. **The asymmetry is what one-sided duration is built to expose.**

**(d) Spread duration:** if the 50 bp Z-spread widens to 100 bp and SpreadDur = 4.0, then $\Delta P \approx -4.0 \cdot 0.005 = -2.0\%$. Note that the *benchmark curve never moved* — this is pure credit risk.

**(e) Empirical duration:** if we regressed this bond's returns on Δ(5-yr Treasury), we might get $\hat{\beta} = -3.6$, implying EmpDur = 3.6 — *lower* than EffDur because in past flight-to-quality episodes the spread widened when Treasuries rallied.

**The punchline:** *one bond, five different duration values*, each answering a different question. Picking the wrong one is a classic L2 trap.

## 6. Decision Tree — Which Duration Do I Use?

```
Does the bond have embedded options or rate-dependent cash flows (MBS, FRN)?
│
├── NO  → Yield duration family
│        ├── Want a time / immunization horizon? .............. Macaulay
│        ├── Want % price change for ΔYTM? ................... Modified
│        └── Want $ change for portfolio risk? ............... Money
│
└── YES → Curve duration family
         ├── Parallel shift, single number? ................. Effective
         ├── Care about steepening/flattening? .............. Key Rate
         └── Option near-the-money, asymmetric reaction? ... One-Sided

Separately, always ask:
  Bond has credit risk?  → Add Spread duration.
  Need real-world (stressed) sensitivity? → Use Empirical duration.
```

## 7. Exam Traps

1. **"Use modified duration on a callable bond."** Wrong. The instant cash flows depend on rates, ModDur is invalid — switch to EffDur.
2. **Confusing units.** MacDur is in *years*; ModDur is *% per 100 bp*; MoneyDur is in *currency*. Mixing them is the most common arithmetic error.
3. **Assuming EffDur captures non-parallel shifts.** It doesn't — that's what *key rate* duration is for. EffDur assumes the curve moves up/down in parallel.
4. **Treating spread duration as redundant with EffDur.** They measure orthogonal risks. A long-corporate bond has both.
5. **Forgetting that for option-free bonds, EffDur ≈ ModDur.** They only diverge when cash flows are uncertain — a quick sanity check on tree calculations.
6. **Ignoring the sign convention on one-sided durations.** A callable bond's *down*-duration is the smaller number (call cap kicks in); a putable bond's *up*-duration is the smaller number (put floor kicks in).
7. **Empirical < Analytical for risky bonds — and the *why*.** Spread/yield negative correlation in stress, not a calculation mistake.
8. **CDS spread duration sign.** If you are the protection *seller* (long credit), spread widening hurts you; if you are the protection *buyer*, it helps you. Sign flips with position.

## 8. Memory Hook

**"YCS-E"** — the four families of duration:

- **Y**ield (Mac, Mod, Money) — the bond talks to itself
- **C**urve (Eff, Key Rate, One-Sided) — the benchmark talks to the bond
- **S**pread — the credit market talks to the bond
- **E**mpirical — the *real world* talks to the bond

And the one-line rule of thumb: *"If the cash flows can change, switch from Yield to Curve; if credit can move, add Spread; if you trust history more than models, use Empirical."*

## 9. Related

- [[Macaulay duration]] · [[Modified duration]] · [[Money duration]]
- [[Effective duration]] · [[Effective Duration]]
- [[Key rate duration]] · [[Key Rate Duration]] · [[Partial duration]] · [[Key rate durations]]
- [[One-sided durations]] · [[One-Sided Durations]]
- [[Spread duration]] · [[Spread Duration]]
- [[Empirical duration]]
- [[Curve duration]] · [[Yield duration]] · [[Duration]]
- [[Duration gap]] · [[Duration matching]] · [[Leverage-adjusted duration gap]]
