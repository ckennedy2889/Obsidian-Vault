---
title: Risk-Neutral Probabilities
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - binomial
  - risk-neutral
  - no-arbitrage
aliases:
  - risk-neutral probabilities
  - risk neutral probabilities
  - risk-neutral probability
  - risk-neutral valuation
  - up-state probability
---

# Risk-Neutral Probabilities

## The Real-World Analogy

Imagine two casino games with the same payoff: if the coin lands heads, you get 10; if tails, you get 0. In the real world, the coin might be biased. Maybe heads is actually 70% likely. But if the payoff can be perfectly replicated by trading other assets, the price of the game is pinned down by replication, not by anyone's personal belief about heads.

Risk-neutral probabilities are like the "pricing probabilities" that make the replicated payoff line up with the market prices we already observe.

They are not forecasts. They are accounting weights that make no-arbitrage pricing work.

## The Big Idea

In a [[Binomial Option Pricing Model]], the underlying asset can move up or down over one period.

Risk-neutral probabilities are the probabilities that make the expected return on the underlying equal the [[Risk-free rate|risk-free rate]].

That sentence is weird on purpose. It does **not** mean investors truly expect the stock to earn the risk-free rate. It means we switch into a mathematical pricing world where investors are risk-neutral, so every asset can be priced by:

$$
\text{Value today}
= \frac{\text{Risk-neutral expected payoff}}{1+r}
$$

The magic is that this gives the same option price as the replication/no-arbitrage method.

## Why CFA Tests This

CFA tests risk-neutral probabilities because they let you price options without estimating the real expected return on the stock.

That matters because the real expected return is subjective and risk-premium-loaded. Option pricing should not depend on your personal view of whether the stock is attractive. If the option payoff can be replicated, no-arbitrage pins down the price.

So the exam wants you to know:

- How to calculate the risk-neutral up probability.
- Why it is not the actual probability of an up move.
- How to use it to discount expected option payoffs.
- How it connects to [[Hedge Ratio|hedge ratio]] replication.
- Why $N(d_2)$ in [[Black-Scholes-Merton Model|BSM]] is interpreted as a risk-neutral probability.

## Deriving the Binomial Risk-Neutral Probability

Let:

| Symbol | Meaning |
|---|---|
| $S_0$ | Current underlying price |
| $u$ | Up factor |
| $d$ | Down factor |
| $S^+ = S_0u$ | Up-state underlying price |
| $S^- = S_0d$ | Down-state underlying price |
| $r$ | One-period risk-free rate |
| $\pi$ | Risk-neutral probability of the up move |
| $1-\pi$ | Risk-neutral probability of the down move |

In the risk-neutral world, the expected future stock price must equal the current stock price grown at the risk-free rate:

$$
S_0(1+r) = \pi S_0u + (1-\pi)S_0d
$$

Divide both sides by $S_0$:

$$
1+r = \pi u + (1-\pi)d
$$

Expand:

$$
1+r = \pi u + d - \pi d
$$

Group the $\pi$ terms:

$$
1+r - d = \pi(u-d)
$$

Solve:

$$
\boxed{\pi = \frac{(1+r)-d}{u-d}}
$$

If the risk-free rate is continuously compounded over a time step $\Delta t$, use:

$$
\boxed{\pi = \frac{e^{r\Delta t}-d}{u-d}}
$$

The down probability is:

$$
\boxed{1-\pi = \frac{u-(1+r)}{u-d}}
$$

## The No-Arbitrage Assumption

For the risk-neutral probabilities to make sense:

$$
d < 1+r < u
$$

The risk-free growth rate must sit between the down return and the up return.

If $1+r$ is above $u$, the stock's best possible return is still below the risk-free return, so arbitrage would exist. If $1+r$ is below $d$, the stock's worst possible return still beats the risk-free return, so arbitrage would also exist.

This is why $\pi$ must fall between 0 and 1 in a valid no-arbitrage binomial tree.

## Pricing an Option With Risk-Neutral Probabilities

Once you have $\pi$, the option value is the present value of expected payoff using risk-neutral probabilities.

For a one-period call:

$$
c_0 =
\frac{\pi c^+ + (1-\pi)c^-}{1+r}
$$

For a one-period put:

$$
p_0 =
\frac{\pi p^+ + (1-\pi)p^-}{1+r}
$$

The structure is:

```text
Compute option payoff in each state
  |
  v
Weight payoffs with risk-neutral probabilities
  |
  v
Discount expected payoff at the risk-free rate
  |
  v
No-arbitrage option value today
```

## Worked Numerical Example

Assume:

- $S_0 = 50$.
- $u = 1.20$.
- $d = 0.80$.
- $r = 5\%$.
- Call strike $X = 55$.

Stock prices:

$$
S^+ = 50(1.20) = 60
$$

$$
S^- = 50(0.80) = 40
$$

Call payoffs:

$$
c^+ = \max(60-55,0)=5
$$

$$
c^- = \max(40-55,0)=0
$$

Risk-neutral up probability:

$$
\pi = \frac{1.05-0.80}{1.20-0.80}
= \frac{0.25}{0.40}
= 0.625
$$

Risk-neutral down probability:

$$
1-\pi = 0.375
$$

Call value:

$$
c_0 =
\frac{0.625(5) + 0.375(0)}{1.05}
= \frac{3.125}{1.05}
= 2.98
$$

The call is worth 2.98 today.

## Why This Matches Replication

The replication method constructs a portfolio of stock and borrowing/lending that has the same payoff as the option. If two things have the same payoff in every state, they must have the same price today.

The risk-neutral method looks different, but it is the same no-arbitrage logic in disguise.

For the example above, the hedge ratio is:

$$
h = \frac{5-0}{60-40}=0.25
$$

A portfolio long 0.25 shares and short one call pays the same amount in both states:

Up state:

$$
0.25(60) - 5 = 10
$$

Down state:

$$
0.25(40) - 0 = 10
$$

That riskless 10 payoff is worth:

$$
\frac{10}{1.05}=9.52
$$

Therefore:

$$
c_0 = 0.25(50) - 9.52 = 12.50 - 9.52 = 2.98
$$

Same answer. The risk-neutral probability method is faster; the replication method explains why it works.

## Risk-Neutral Probability vs Actual Probability

This is the heart of the concept.

| Probability type | What it means | Used for |
|---|---|---|
| Actual probability | Real-world chance of up/down movement | Forecasting and risk analysis |
| Risk-neutral probability | Pricing weight consistent with no-arbitrage | Derivative valuation |

If the actual probability of an up move is 70%, you still might use $\pi = 62.5\%$ for pricing. That is not a contradiction because the two probabilities answer different questions.

Actual probability asks:

> What do we think will happen?

Risk-neutral probability asks:

> What probability weights make today's market price consistent with risk-free discounting and no arbitrage?

The deeper reason is that risk preferences and expected risk premiums are already reflected in the current underlying price $S_0$. Once $S_0$ is observed, option pricing becomes a relative-pricing problem: price the option consistently with the stock, not with a separate forecast of the stock's expected return.

## Connection to BSM

In the [[Black-Scholes-Merton Model]], $N(d_2)$ is interpreted as the risk-neutral probability that a call option expires in the money:

$$
N(d_2) = P^{RN}(S_T > X)
$$

For a put:

$$
N(-d_2) = P^{RN}(S_T < X)
$$

Do not confuse this with $N(d_1)$.

| BSM term | Interpretation |
|---|---|
| $N(d_1)$ | Delta / hedge ratio for a call |
| $N(d_2)$ | Risk-neutral probability the call expires in the money |

$N(d_1)$ and $N(d_2)$ are close cousins, but they are not the same. The exam loves that little trapdoor.

## Interest Rate Trees

For binomial interest rate trees in CFA Level II, the up and down moves are often assigned equal risk-neutral probabilities:

$$
\pi = 0.50,\qquad 1-\pi = 0.50
$$

That does not mean rates are truly equally likely to rise or fall. It means the tree is calibrated so pricing works under the risk-neutral measure.

## Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating $\pi$ as the actual probability | Turns a pricing device into a forecast | Say: "risk-neutral, not real-world" |
| Using expected stock return instead of $r$ | Imports risk premium into no-arbitrage pricing | Use the risk-free rate in $\pi$ |
| Confusing $\pi$ with hedge ratio | Mixes probability with slope | $\pi$ prices expected payoff; $h$ replicates payoff |
| Forgetting to discount | Stops at expected payoff | Discount at $1+r$ |
| Confusing $N(d_1)$ and $N(d_2)$ | Calls delta a probability | $N(d_1)$ is delta; $N(d_2)$ is risk-neutral ITM probability |
| Using unequal probabilities in CFA interest rate trees when equal probabilities are stated | Breaks the calibrated tree setup | Use 0.5/0.5 when the tree is specified that way |

## Directional Effects

From:

$$
\pi = \frac{(1+r)-d}{u-d}
$$

holding $u$ and $d$ constant, a higher risk-free rate increases $\pi$. Mechanically, the risk-neutral expected stock price must grow faster, so more weight is placed on the up state.

This is one reason higher interest rates generally increase call values and decrease put values, all else equal.

## Memory Hooks

**Risk-neutral probability is a pricing weight, not a prediction.**

**It makes the stock earn the risk-free rate in the model.**

**Expected payoff with fake probabilities, discounted at the real risk-free rate, gives the no-arbitrage price.**

## Related Concepts

- [[Binomial Option Pricing Model]]
- [[Hedge Ratio]]
- [[Black-Scholes-Merton Model]]
- [[Option Greeks]]
- [[No-arbitrage]]
- [[Risk-free rate]]
- [[Expected value]]
