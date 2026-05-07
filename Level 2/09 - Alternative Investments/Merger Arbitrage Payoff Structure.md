---
title: "Merger Arbitrage Payoff Structure"
subject: "Alternative Investments"
tags: [CFA-L2, alternative-investments]
aliases: []
---

# Merger Arbitrage Payoff Structure

> [!info] CFA L2 — [[Alternative investments|Alternative Investments]] | Module 4 (Deep Dive)
> **Why Merger [[Arbitrage|Arbitrage]] = Long Riskless Bond + Short Put**
> Source: CFA Program Curriculum 2025 Level 2, Volume 8

---

## The Setup: What Happens When a Deal Is Announced

When Company A announces it will acquire Company B in a **stock-for-stock** deal, the [[merger arbitrage|merger arb]] manager:

1. **Goes long** the target (Company B) shares
2. **Goes short** the acquirer (Company A) shares at the announced [[Exchange ratio|exchange ratio]]
3. **Waits** for the deal to close

The **spread** = difference between the current target share price and the implied [[Offer price|offer price]]. This spread exists because there's uncertainty about whether the deal will actually close.

---

## The Binary Outcome Structure

There are only two possible outcomes:

### Outcome 1: Deal Succeeds (Most Likely — ~90%+ of announced deals close)

- Target price converges **up** to the [[Offer price|offer price]]
- The spread you locked in becomes your profit
- This profit is **small and capped** — you can't earn more than the spread
- The return is **bond-like** — it resembles earning a coupon over the waiting period

### Outcome 2: Deal Fails (Rare — ~5-10% of deals)

- Target price **crashes** back to its pre-announcement level (or lower)
- The acquirer's stock may actually rise (market sees it as good news for the acquirer)
- Your long-target / short-acquirer position loses on **both legs** simultaneously
- The loss is **large and sudden** — much bigger than the small spread you were hoping to earn

> [!tip] The Insurance Analogy
> Think of the [[merger arbitrage|merger arb]] manager as an **insurance company**:
> - **Premiums collected** = the small spread earned when deals close (frequent, small, predictable)
> - **Claims paid out** = the large loss when a deal fails (rare, large, unpredictable)
>
> Most quarters, you collect premiums and show steady, positive returns. But occasionally, a catastrophe hits and you pay out much more than you collected.

---

## Why This Maps to "Long Riskless Bond + Short Put"

### Breaking It Down

| Component | What It Represents |
|---|---|
| **Long riskless bond** | The steady, small return you earn as the spread narrows — this is the "base case" return, similar to earning interest on a [[risk-free]] bond |
| **Short [[Put option]]** | The risk you're exposed to if the deal fails — you've "sold insurance" against deal failure. When the deal breaks, you must absorb the loss, just like a put seller must buy stock at the strike when prices crash |

### The Payoff Profile

```
Profit
  ^
  |     _______________  ← Small, capped upside (spread)
  |    /
  |---/------------------→ Outcome
  |  /
  | /
  |/  ← Large downside if deal fails
  |
```

This is exactly the shape of a **short [[Put option]]** payoff:
- **Upside is limited** (you only earn the premium/spread)
- **Downside is large** (if the "event" occurs, losses are significant)

---

## Why the Wrong Answers Are Wrong

### ❌ Long Riskless Bond + Short [[Call option]]

A short call would mean your losses come when the target stock **rises** dramatically. But that's backwards — the merger arb manager is *long* the target and *profits* when it rises (toward the [[Offer price|offer price]]). Rising target prices are *good*, not bad.

### ❌ Long Riskless Bond + Long [[Put option]]

A long put would mean you **profit** when the target stock crashes. But the merger arb manager is *long* the target — a target price crash means *losses*, not gains. Buying a put would be a *hedge* against deal failure, not a description of the inherent payoff.

---

## The White Knight Exception — Embedded Long Call

There's one scenario where [[merger arbitrage]] produces an *unexpected upside* beyond the spread:

> [!success] The "[[White knight|White Knight]]" Scenario
> A competing bidder emerges with a **higher offer** for the [[Target company|target company]].
>
> - Target price jumps *above* the original [[Offer price|offer price]]
> - The merger arb manager is long the target → profits from the price surge
> - This creates an embedded **long [[Call option]]** payoff — unexpected, uncapped upside
>
> This scenario is relatively rare, but it explains why merger arb returns occasionally show positive skew (large gains) despite the overall negative skew profile.

---

## Risk Factors and Market Regime Effects

> [!warning] Crisis Period Behavior
> [[Merger arbitrage]] is particularly dangerous during market crises because:
> 1. **Deal failure rates spike** — financing becomes unavailable, regulatory approval stalls, acquirer stock crashes
> 2. **Multiple deals fail simultaneously** — [[Correlation]] between deal outcomes increases
> 3. **Spreads widen on surviving deals** — even deals that eventually close see their spreads blow out temporarily, causing mark-to-market losses
>
> This is why the [[Conditional Factor Risk Model]] shows increased equity [[Beta]] for merger arb strategies during crisis periods (the $D_t$ [[Dummy variable|dummy variable]] captures this regime shift).

### Connection to the Conditional Factor Model

In the model:

$$R_{\text{merger arb},t} = \alpha + \beta_1 \cdot \text{EQUITY}_t + \beta_4 \cdot D_t \cdot \text{EQUITY}_t + \epsilon_t$$

- During **normal times** ($D_t = 0$): Merger arb has **low equity [[Beta]]** ($\beta_1$) — returns are primarily driven by deal spreads, not market direction
- During **crisis periods** ($D_t = 1$): The *total* equity exposure becomes $\beta_1 + \beta_4$, where $\beta_4 > 0$ — merger arb becomes much more correlated with the market, losing its [[diversification]] benefit exactly when you need it most

---

## Practice Question

> [!example] Which payoff profile best characterizes merger [[Arbitrage|arbitrage]]?
> 
> A. Long riskless bond + short call
> B. Long riskless bond + short put ✅
> C. Long riskless bond + long put
> D. Short riskless bond + long call
>
> **Answer: B.** The merger arb manager earns small, steady returns (like bond coupons) most of the time, but faces large, sudden losses when deals fail (like a put seller who must absorb losses when prices crash). The payoff is asymmetric: capped upside, large potential downside — the signature of a short put.

---

*See also: [[Hedge Fund Strategies]] | [[Event-driven strategies]] | [[Merger Arbitrage]]*
