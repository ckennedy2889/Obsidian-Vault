---
title: APT Arbitrage Opportunities
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, APT, arbitrage, multifactor-models, factor-risk-premiums]
aliases: [Arbitrage Pricing Theory Arbitrage, APT Arbitrage, Arbitrage Portfolio, Zero-Investment Portfolio]
---

# APT Arbitrage Opportunities

## Intuition

[[Arbitrage Pricing Theory]] says that two well-diversified portfolios with the same systematic factor exposures should offer the same expected return.

If they do not, the market is offering a free lunch:

- buy the portfolio with too much expected return for its factor risk,
- short the portfolio with too little expected return for its factor risk,
- make the factor exposures cancel,
- and earn the return difference with zero net investment.

That is the APT arbitrage trade.

See: [[Using Multifactor Models]] · [[Fama-French Model]] · [[Information Ratio]]

## APT Assumptions

APT rests on three assumptions:

| Assumption | Meaning |
|---|---|
| **Returns follow a factor model** | Systematic risk factors explain diversified portfolio returns |
| **Idiosyncratic risk can be diversified away** | Well-diversified portfolios have little asset-specific noise |
| **No arbitrage opportunities exist** | Identical factor exposures must command identical expected returns |

The theory is weaker than CAPM because it does not require a market portfolio or identical investor utility assumptions. But it also does not tell you which factors to use.

## APT Expected Return Equation

For a well-diversified portfolio:

$$
E(R_P) = R_F + \lambda_1\beta_{P,1} + \lambda_2\beta_{P,2} + \cdots + \lambda_K\beta_{P,K}
$$

where:

| Symbol | Meaning |
|---|---|
| $R_F$ | Risk-free rate |
| $\beta_{P,k}$ | Portfolio sensitivity to factor $k$ |
| $\lambda_k$ | Factor risk premium for one unit of exposure to factor $k$ |
| $K$ | Number of systematic factors |

If the model fully explains expected return, the alpha of a correctly priced well-diversified portfolio is zero:

$$
\alpha_P = E(R_P) - \left(R_F + \sum_{k=1}^K \lambda_k\beta_{P,k}\right) = 0
$$

If $\alpha_P \neq 0$, the portfolio is mispriced relative to the factor model.

## What Counts as Arbitrage?

An arbitrage opportunity has:

1. **Zero net investment.**
2. **Zero net systematic risk.**
3. **Positive expected profit.**

In APT problems, "zero risk" means **net factor exposure is zero** after the long and short positions offset.

## Detection Rule

If two well-diversified portfolios have the same factor sensitivities:

$$
\beta_A = \beta_B
$$

but different expected returns:

$$
E(R_A) \neq E(R_B)
$$

then arbitrage exists.

Trade rule:

- Go **long** the higher-return portfolio.
- Go **short** the lower-return portfolio.

## Worked Example 1: Same Beta, Different Expected Return

Two well-diversified portfolios have the same single-factor beta:

| Portfolio | Expected return | Factor beta |
|---|---:|---:|
| X | 10% | 1.0 |
| Y | 8% | 1.0 |

Because the factor exposure is identical, expected returns should be identical. Portfolio X offers too much return for the same risk.

Arbitrage trade:

| Position | Weight | Expected return contribution | Beta contribution |
|---|---:|---:|---:|
| Long X | +100% | +10% | +1.0 |
| Short Y | -100% | -8% | -1.0 |
| **Net** | **0%** | **+2%** | **0.0** |

The trade has:

- zero net investment,
- zero net factor exposure,
- positive expected return.

So it is an APT arbitrage.

## Worked Example 2: Creating a Matching-Beta Portfolio

Suppose:

| Portfolio | Expected return | Beta |
|---|---:|---:|
| A | 10% | 1.0 |
| B | 20% | 2.0 |
| C | 13% | 1.5 |

First create Portfolio D with the same beta as C using A and B:

$$
\beta_D = 0.5(1.0) + 0.5(2.0) = 1.5
$$

Expected return on D:

$$
E(R_D) = 0.5(10\%) + 0.5(20\%) = 15\%
$$

Portfolio D and Portfolio C have the same factor exposure:

$$
\beta_D = \beta_C = 1.5
$$

but D offers higher expected return:

$$
15\% > 13\%
$$

Arbitrage trade:

- Long Portfolio D.
- Short Portfolio C.

Expanded weights:

| Position | Weight | Expected return contribution | Beta contribution |
|---|---:|---:|---:|
| Long A | +50% | +5.0% | +0.5 |
| Long B | +50% | +10.0% | +1.0 |
| Short C | -100% | -13.0% | -1.5 |
| **Net** | **0%** | **+2.0%** | **0.0** |

The arbitrage profit is:

$$
15\% - 13\% = \boxed{2\%}
$$

## Worked Example 3: Inferring Factor Premium

In a one-factor APT model:

$$
E(R_i) = R_F + \beta_i\lambda
$$

Two correctly priced portfolios have:

| Portfolio | Expected return | Beta |
|---|---:|---:|
| A | 7.0% | 1.0 |
| B | 7.8% | 1.2 |

Set up equations:

$$
0.070 = R_F + 1.0\lambda
$$

$$
0.078 = R_F + 1.2\lambda
$$

Subtract:

$$
0.008 = 0.2\lambda
$$

$$
\lambda = 0.040 = 4.0\%
$$

Then:

$$
R_F = 0.070 - 0.040 = 0.030 = 3.0\%
$$

If Portfolio C has beta 0.8, its fair expected return is:

$$
E(R_C) = 3.0\% + 0.8(4.0\%) = 6.2\%
$$

If C's actual expected return is above 6.2%, C is underpriced. If below 6.2%, C is overpriced.

## Underpriced vs Overpriced

| Actual return vs APT fair return | Price status | Trade |
|---|---|---|
| Actual expected return is **higher** than model return | Underpriced / cheap | Buy it |
| Actual expected return is **lower** than model return | Overpriced / rich | Short it |

Memory shortcut:

> **Above the APT line = buy. Below the APT line = short.**

## Why Individual Stocks Are Not Pure APT Arbitrage

APT assumes idiosyncratic risk has been diversified away. A single stock can have:

- earnings surprises,
- fraud risk,
- legal risk,
- takeover risk,
- product failure,
- management risk.

Even if a single stock looks mispriced by the factor model, a trade in that stock alone is not risk-free. APT arbitrage is cleanest with well-diversified portfolios.

## Exam Traps

| Trap | Correct response |
|---|---|
| Say APT identifies the correct factors | APT does not specify the factors or number of factors |
| Forget zero net investment | Long and short weights must sum to zero |
| Forget zero net factor exposure | Long and short factor sensitivities must offset |
| Short the high-return portfolio | Long the portfolio with too much return for its factor exposure |
| Treat individual-stock mispricing as pure arbitrage | Individual stocks still have idiosyncratic risk |
| Say arbitrage makes factor risk premiums zero | Arbitrage removes mispricing; systematic factor risk still earns a premium |
| Compare raw returns without matching beta | First match factor exposures, then compare returns |

## Memory Hook

> **Same beta, same return. If not, long high, short low.**

For multi-factor problems:

> **Match every beta, then compare return.**

## Exam-Day Checklist

1. Write the APT equation.
2. Compute fair expected return from factor sensitivities and factor risk premiums.
3. Compare actual expected return to fair return.
4. If constructing arbitrage, make long and short weights sum to zero.
5. Make all net factor exposures equal zero.
6. Confirm expected profit is positive.
7. State that arbitrage pressure should eliminate the mispricing.

## Related Concepts

- [[Using Multifactor Models]]
- [[Fama-French Model]]
- [[CAPM]]
- [[Factor Risk Premium]]
- [[Active Risk and Tracking Error]]
- [[Information Ratio]]
