---
title: Binomial Option Pricing Model
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - binomial
  - option-pricing
  - risk-neutral
  - no-arbitrage
  - American-options
  - put-call-parity
aliases:
  - binomial model
  - binomial tree
  - risk-neutral probabilities
  - backward induction
  - hedge ratio
---

# Binomial Option Pricing Model

## The Real-World Analogy

Imagine you're buying a bet on a coin flip: heads wins, tails loses. You can price this bet exactly because there are only two outcomes. Now imagine the stock market as a coin flip — at the end of each period, the stock either goes up or down. This is the binomial model.

It's not a perfect description of reality (stocks can do infinitely many things, not just two). But with enough time periods, this two-outcome model converges to the real world's continuous price movement. In fact, as the time step approaches zero, the binomial model becomes the [[Black-Scholes-Merton Model|BSM model]] exactly.

The genius of the binomial approach is this: if you can construct a risk-free portfolio by combining the option with shares of the stock, then the option's price is uniquely determined by no-arbitrage. No assumptions about risk preferences are needed.

## Plain-English Definition

The **binomial option pricing model** values options by assuming the underlying asset can take only two possible values at the end of each period — an "up" move or a "down" move. Working backwards from the known option payoffs at expiration, the current option price is determined by the principle of no-arbitrage.

---

## Why CFA Tests This

The LOS requires:
- *"Describe and interpret the binomial option valuation model and its component terms"*
- *"Calculate the no-arbitrage values of European and American options using a two-period binomial model"*
- *"Calculate and interpret the value of an interest rate option using a two-period binomial model"*

The exam frequently presents a numerical problem where you must apply backward induction and identify whether early exercise is optimal for American options.

---

## The Model Structure

### Price Tree — One Period

```
        S⁺ = S₀ × u
       /
S₀ ---|
       \
        S⁻ = S₀ × d
```

| Variable | Meaning |
|---|---|
| $S_0$ | Current stock price |
| $u$ | Up factor (e.g., 1.20 means stock rises 20%) |
| $d$ | Down factor (e.g., 0.80 means stock falls 20%) |
| $S^+ = S_0 u$ | Stock price in up state |
| $S^- = S_0 d$ | Stock price in down state |
| $c^+, c^-$ | Option payoffs in up/down states |
| $r$ | Risk-free rate per period |

Assumption: $d < 1 + r < u$ (otherwise arbitrage exists independently of options)

---

## One-Period Model: Two Equivalent Approaches

### Approach 1 — No-Arbitrage (Replication)

**Concept:** Construct a portfolio of $h$ shares of stock (long) and 1 call option (short) that is **riskless** — it pays the same in the up state and down state.

**Condition for risklessness:**

$$hS^+ - c^+ = hS^- - c^-$$

**Solving for the hedge ratio:**

$$\boxed{h = \frac{c^+ - c^-}{S^+ - S^-}}$$

This hedge ratio is the binomial model's **delta** — exactly the same concept as BSM delta.

**Since the portfolio is riskless, it must earn the risk-free rate:**

$$V_0 = \frac{hS^+ - c^+}{1 + r}$$

Rearranging for the option price:

$$\boxed{c_0 = hS_0 - V_0 = hS_0 - \frac{hS^+ - c^+}{1 + r}}$$

### Approach 2 — Risk-Neutral Probabilities

**Concept:** Find the probabilities $\pi$ (up) and $1-\pi$ (down) such that, in a risk-neutral world, the expected return on the stock equals the risk-free rate.

**Solving for risk-neutral probability $\pi$:**

$$S_0(1+r) = \pi S^+ + (1-\pi) S^-$$

$$\boxed{\pi = \frac{(1+r) - d}{u - d}}$$

**Option price:**

$$\boxed{c_0 = \frac{\pi c^+ + (1-\pi) c^-}{1+r}}$$

> [!note] Risk-Neutral Probabilities Are Not Real Probabilities
> $\pi$ is the probability that makes the stock price equal its present value discounted at the risk-free rate. It is NOT the actual probability of the stock going up. It is a mathematical device for pricing — it works because, in a complete market, you can always find prices consistent with some risk-neutral probability measure.

**Both approaches give identical prices** — this is not a coincidence, it is a theorem.

---

## Worked Numerical Example — One Period

**Setup:** $S_0 = 50$, $X = 55$, $u = 1.20$, $d = 0.80$, $r = 5\%$ per period

**Price tree:**
- $S^+ = 50 \times 1.20 = 60$
- $S^- = 50 \times 0.80 = 40$

**Call payoffs:**
- $c^+ = \max(60 - 55, 0) = 5$
- $c^- = \max(40 - 55, 0) = 0$

**Step 1 — Hedge ratio:**

$$h = \frac{5 - 0}{60 - 40} = \frac{5}{20} = 0.25$$

**Step 2 — Risk-neutral probability:**

$$\pi = \frac{1.05 - 0.80}{1.20 - 0.80} = \frac{0.25}{0.40} = 0.625$$

**Step 3 — Option price (risk-neutral approach):**

$$c_0 = \frac{0.625 \times 5 + 0.375 \times 0}{1.05} = \frac{3.125}{1.05} = \mathbf{2.98}$$

**Verify with no-arbitrage:**

Riskless portfolio value at $T=1$: $hS^+ - c^+ = 0.25 \times 60 - 5 = 10.00$

PV of riskless payoff: $\frac{10.00}{1.05} = 9.52$

$$c_0 = hS_0 - V_0 = 0.25 \times 50 - 9.52 = 12.50 - 9.52 = \mathbf{2.98} \checkmark$$

---

## Two-Period Model: Backward Induction

### The Tree

```
              S⁺⁺ = S₀u²
             /
        S⁺ -|
       /     \
S₀ --|        S⁺⁻ = S₀ud
       \     /
        S⁻ -|
             \
              S⁻⁻ = S₀d²
```

Note: $S^{+-} = S^{-+} = S_0 \cdot u \cdot d$ (the middle node is the same regardless of path — this is the "recombining" property).

### Process: Backward Induction

**Step 1 — Compute terminal payoffs ($T=2$):**

$$c^{++} = \max(S_0 u^2 - X, 0)$$
$$c^{+-} = \max(S_0 ud - X, 0)$$
$$c^{--} = \max(S_0 d^2 - X, 0)$$

**Step 2 — Solve for $T=1$ option values using one-period formula:**

$$c^+ = \frac{\pi c^{++} + (1-\pi) c^{+-}}{1+r}$$

$$c^- = \frac{\pi c^{+-} + (1-\pi) c^{--}}{1+r}$$

**Step 3 — Solve for $T=0$ option value:**

$$c_0 = \frac{\pi c^+ + (1-\pi) c^-}{1+r}$$

The same $\pi = \frac{(1+r)-d}{u-d}$ is used at every node.

---

## American Options and Early Exercise

For **European options**, you always take the backward induction value at each node. The option cannot be exercised early.

For **American options**, at each intermediate node you compare:
1. **Hold value:** The backward induction value (keep the option alive)
2. **Exercise value:** The immediate intrinsic value if exercised now

Take the **maximum** of the two:

$$V^{American}_{\text{node}} = \max(\text{Hold value}, \text{Exercise value})$$

### When Is Early Exercise Optimal?

| Option Type | Early Exercise Optimal When |
|---|---|
| **American call (no dividends)** | **Never** — time value is always positive; sell the option rather than exercise |
| **American call (with dividends)** | Possibly just before a large dividend payment |
| **American put** | When put is deep in-the-money — exercising captures the strike immediately, allowing reinvestment at risk-free rate |

> [!important] Why Never Exercise an American Call on a Non-Dividend Stock?
> An American call on a non-dividend stock always has intrinsic value ≤ market value. If you exercise early, you get $S - X$ in cash. But if you instead sell the option, you get at least $S - X$ (intrinsic) plus the time value. You always receive at least as much (and usually more) by selling rather than exercising.

> [!important] Why Early Exercise of a Put Can Be Optimal?
> A deep ITM put is nearly certain to pay $X - S$ at expiration. If you exercise now, you receive $X - S$ immediately and can earn the risk-free rate on it for the remaining life. The time value of a deep ITM put can be *negative* — you'd rather have the cash now than wait.

### Two-Period American Put Example

At the down-down node: $S^{--} = 40$, $X = 50$

- Intrinsic value = $50 - 40 = 10$
- Hold value (backward induction from expiry) = $8.50$ (hypothetical)

Since $10 > 8.50$, **exercise early**. Use 10 as the node value, not 8.50.

This propagates upward: the $T=1$ down node value is recalculated using 10 instead of 8.50, which may change the $T=0$ option price.

---

## Put-Call Parity — No-Arbitrage Derivation

Put-call parity is derived from constructing two portfolios with identical payoffs:

| Portfolio | Composition | Value at expiry if $S_T > X$ | Value at expiry if $S_T < X$ |
|---|---|---|---|
| **Fiduciary Call** | Long call + Long bond ($PV(X)$) | $(S_T - X) + X = S_T$ | $0 + X = X$ |
| **Protective Put** | Long stock + Long put | $S_T + 0 = S_T$ | $S_T + (X - S_T) = X$ |

Both portfolios pay $\max(S_T, X)$ in every state. By no-arbitrage:

$$\boxed{c + \frac{X}{(1+r)^T} = S + p}$$

Or equivalently:

$$c - p = S - \frac{X}{(1+r)^T}$$

**Uses of put-call parity:**

1. Given any three of {$c$, $p$, $S$, $PV(X)$}, solve for the fourth
2. Identify arbitrage if the relationship is violated
3. Derive relationships between option Greeks (e.g., call and put have the same vega, same gamma)

> [!example] Arbitrage with Put-Call Parity
> If $c = 5$, $S = 50$, $X = 50$, $r = 5\%$, $T = 1$ → $PV(X) = 50/1.05 = 47.62$
>
> Parity requires: $p = c + PV(X) - S = 5 + 47.62 - 50 = 2.62$
>
> If the market trades $p = 4$, the put is overpriced. Arbitrage: sell put, buy call, short stock, invest $PV(X)$ → earn riskless profit.

---

## Exam Traps

> [!danger] Key Binomial Model Exam Traps

| Trap | Correct Understanding |
|---|---|
| $\pi$ = actual probability of up move | $\pi$ is the **risk-neutral** probability — not the real-world probability |
| Use $d = 1/u$ always | The exam may give $u$ and $d$ separately; don't assume $d = 1/u$ unless stated |
| American call = European call always | True for non-dividend stocks; **false** for dividend-paying stocks |
| American put = European put | American put ≥ European put; early exercise may be optimal |
| Two-period price = discount two-period tree | Must do backward induction one step at a time — cannot skip to the end |
| Exercise value at $T=0$ | At the initial node, you should not compare to exercise value for European options |
| Risk-neutral prob depends on real-world return | $\pi = [(1+r) - d] / (u-d)$ — uses only the risk-free rate and up/down factors, NOT expected return |

---

## Memory Hooks

- **Hedge ratio = $(c^+ - c^-)/(S^+ - S^-)$** — option's payoff range divided by stock's price range
- **Risk-neutral $\pi = [(1+r) - d] / (u-d)$** — "how far up is the risk-free rate as a fraction of the full up-down range"
- **Two-period: work backwards** — always start at expiration nodes, then $T=1$, then $T=0$
- **American = European + early exercise check**: at every node, max(hold, exercise)
- **Early exercise put: deep ITM only** — when interest on the strike exceeds remaining time value
- **Put-call parity: call + bond = stock + put** → fiduciary call = protective put

---

## Related Concepts

- [[Black-Scholes-Merton Model]] — the BSM formula is the continuous limit of the binomial model
- [[Option Greeks]] — delta = binomial hedge ratio; gamma = how delta changes between nodes
- [[Put-Call Parity]] — derived from the no-arbitrage argument, tested separately
- [[Interest Rate Options — Caps and Floors]] — interest rate binomial trees value caps/floors
- [[Swaptions]] — binomial interest rate tree is used to value swaptions in fixed income
- [[CFA_L2_Valuation_of_Contingent_Claims]] — full module with additional examples
