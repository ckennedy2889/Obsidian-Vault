---
title: "Intrinsic Value and Perceived Mispricing"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, valuation, applications-and-processes]
aliases: ["Intrinsic value", "Perceived mispricing", "Valuation error", "True mispricing"]
---

# Intrinsic Value and Perceived Mispricing

[[Intrinsic value]] is the value a perfectly informed investor would assign to a security after understanding all of its investment characteristics.

For CFA Level II, the key word is not "value." The key word is "estimate." True intrinsic value is unobservable. An analyst can estimate Apple's intrinsic value using [[Dividend Discount Model|DDM]], [[Free Cash Flow Valuation|FCF]], [[Residual Income Valuation|residual income]], or [[Market-Based Valuation|multiples]], but the analyst never observes the true number directly. That gap between true value and estimated value is where perceived mispricing can become real alpha or just model error.

In plain English:

```text
Intrinsic value is what the stock is worth.
Estimated intrinsic value is what the analyst thinks it is worth.
Market price is what the stock currently trades for.
```

## The CFA Mispricing Decomposition

Let:

- $V$ = true intrinsic value
- $V_E$ = analyst's estimated intrinsic value
- $P$ = current market price

The analyst observes:

$$
V_E - P
$$

This is perceived mispricing. CFA decomposes it as:

$$
V_E - P = (V - P) + (V_E - V)
$$

where:

| Term | Meaning | Interpretation |
|---|---|---|
| $V - P$ | True mispricing | The real gap between value and price |
| $V_E - V$ | Valuation error | The analyst's model error |
| $V_E - P$ | Perceived mispricing | What the analyst thinks the opportunity is |

This formula is small, but it is conceptually important. An analyst can be right that their model value is above the market price and still be wrong about the investment if the model value is too optimistic.

## Apple Example

Suppose Apple trades at $\$287.70$. An analyst builds a free cash flow model and estimates intrinsic value at $\$325$ per share.

Perceived mispricing:

$$
V_E - P = 325.00 - 287.70 = 37.30
$$

The analyst perceives Apple as undervalued by $\$37.30$ per share.

But assume the unknowable true intrinsic value is actually $\$300$.

True mispricing:

$$
V - P = 300.00 - 287.70 = 12.30
$$

Valuation error:

$$
V_E - V = 325.00 - 300.00 = 25.00
$$

Check the decomposition:

$$
37.30 = 12.30 + 25.00
$$

The analyst saw a $\$37.30$ opportunity, but only $\$12.30$ was true undervaluation. The rest was model optimism.

## Why This Matters

The mispricing equation forces humility. It says:

```text
Your estimate being different from price does not prove the market is wrong.
It may prove your estimate is wrong.
```

This is why CFA links valuation to:

- careful model selection
- sensitivity analysis
- sound inputs
- a clear investment horizon
- a catalyst for convergence

If the analyst thinks Apple is worth $\$325$, the next question is not merely "how large is the upside?" It is "why should the market converge to that value, and what evidence would prove the estimate wrong?"

## Market Efficiency Assumption

Searching for mispricing assumes markets are not perfectly efficient. If the market price always equaled intrinsic value, then:

$$
P = V
$$

and true mispricing would be zero:

$$
V - P = 0
$$

In that world, active valuation would not produce positive risk-adjusted returns. CFA does not require you to assume markets are always perfectly efficient. It requires you to understand that profitable valuation depends on both identifying mispricing and managing valuation error.

## The Catalyst Problem

Even if true mispricing exists, price may not converge to intrinsic value quickly. A catalyst is an event that can force the market to update.

For Apple, possible catalysts might include:

- an earnings release
- a major product cycle
- a regulatory decision
- a change in capital return policy
- a services growth inflection

Without a catalyst, an undervalued stock can remain undervalued longer than the analyst's investment horizon.

## Failure Modes

| Failure mode | What happens | Exam implication |
|---|---|---|
| Bad growth assumption | $V_E$ is too high or too low | Perceived mispricing may be valuation error |
| Wrong discount rate | Small input error creates large value error | Sensitivity matters |
| No catalyst | Mispricing may not close | Recommendation is incomplete |
| Wrong model | DDM, FCF, RI, or multiples may not fit company | Model selection matters |
| Market already knows | Price may already reflect the thesis | No true mispricing |

## Exam Traps

The first trap is treating $V_E - P$ as guaranteed alpha. CFA wants you to separate true mispricing from valuation error.

The second trap is reversing the formula. The analyst's perceived mispricing is not just $V - P$ because the analyst does not observe $V$.

The third trap is forgetting the catalyst. A stock can be undervalued and still be a weak recommendation if there is no path to convergence within the client's horizon.

The fourth trap is confusing intrinsic value with investment value. Intrinsic value is usually the relevant concept for public equity analysis. [[Investment value]] may be relevant to a specific buyer with synergies.

## Memory Hook

> [!tip] Memory Hook
> Your model gap equals real mispricing plus your mistake: $V_E - P = (V - P) + (V_E - V)$.

## Related Concepts

- [[Intrinsic value]]
- [[Mispricing]]
- [[Market efficiency]]
- [[Equity Valuation Applications and Model Selection]]
- [[Absolute and Relative Valuation Models]]
- [[Going Concern Value vs Liquidation Value]]
