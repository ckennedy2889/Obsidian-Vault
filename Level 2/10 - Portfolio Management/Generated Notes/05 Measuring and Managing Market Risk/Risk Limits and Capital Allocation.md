---
title: Risk Limits and Capital Allocation
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, market-risk, risk-limits, risk-budgeting, capital-allocation]
aliases: [Risk Budgeting, Position Limits, Scenario Limits, Stop-Loss Limits, Economic Capital, Capital Allocation]
---

# Risk Limits and Capital Allocation

## Intuition

Risk measurement answers, "How much can we lose?" Risk limits answer, "What are we allowed to do about it?"

That distinction matters. A [[Value at Risk (VaR)]] number that sits in a report does not manage risk. Risk is managed when the firm converts that number into:

- a total risk budget,
- position limits,
- scenario loss limits,
- stop-loss triggers,
- and capital allocation decisions.

The CFA exam often tests whether you can identify the **type of limit** from a vignette and explain the tradeoff between too much freedom and too much restriction.

See: [[Measuring and Managing Market Risk]] · [[Parametric Historical and Monte Carlo VaR]] · [[Incremental VaR]] · [[Stress Testing and Scenario Analysis]]

## The Governance Problem

Every limit sits between two bad outcomes:

| If limits are too loose | If limits are too tight |
|---|---|
| Excessive losses, liquidity stress, forced selling, capital impairment, possible reorganization or bankruptcy | Missed opportunities, low returns, inefficient portfolios, managers unable to implement skill |

The risk manager's job is not to eliminate risk. The job is to make sure the risk taken is **intentional, funded, diversified, and aligned with the firm's survival constraint**.

## Four Market Risk Constraints

| Constraint | What it controls | Trigger | Exam phrase |
|---|---|---|---|
| **Risk budget** | Total allowable risk allocated across activities | Ex ante risk limit | "Maximum VaR allocated to each desk" |
| **Position limit** | Maximum exposure to a security, sector, country, currency, asset class, or strategy | Exposure size | "No more than 10% in high-yield bonds" |
| **Scenario limit** | Maximum loss under a specified stress scenario | Hypothetical or historical scenario loss | "Loss under recession scenario cannot exceed $X" |
| **Stop-loss limit** | Required reduction or hedge after realized losses exceed a threshold | Actual realized loss | "Sell if monthly loss exceeds $X" |

## Risk Budgeting

Risk budgeting starts at the top:

> How much total risk can the organization tolerate?

Then it allocates that risk to activities, strategies, asset classes, or business units.

Example:

| Unit | Daily 5% VaR budget |
|---|---:|
| Equity trading | $5 million |
| Currency trading | $15 million |
| Rates trading | $8 million |
| Credit trading | $7 million |
| **Total allocated VaR** | **$35 million** |

The firm can then monitor whether each unit is staying inside its assigned risk envelope.

### Why VaR budgets are not perfectly additive

Portfolio risk is affected by diversification:

$$
\text{Firm VaR} \neq \sum_i \text{Desk VaR}_i
$$

If desks are imperfectly correlated, total firm VaR may be less than the sum of desk VaRs. That creates a governance issue: setting limits only at the business-unit level may be too restrictive if it ignores offsetting exposures across units.

### Role of marginal and incremental VaR

Risk budgets often use:

- [[Incremental VaR]]: change in total VaR from adding or removing a position.
- **Marginal VaR**: approximate change in VaR from a small change in a position.
- **Component VaR**: contribution of a position or business unit to total VaR.

These measures help answer:

> Which position is using the most risk budget, and is the expected return worth it?

## Position Limits

Position limits are hard exposure caps.

They can apply to:

- a single issuer,
- one sector or industry,
- one asset class,
- one country,
- one currency,
- long-short net exposure,
- gross exposure,
- derivatives notional,
- or exposure as a percentage of average daily trading volume.

Example:

> "High-yield bonds may not exceed 10% of assets under management."

That is a **position limit**, not a scenario limit, even if the reason is concern about recession. The limit is written on the **exposure size**, not on the scenario loss.

### Why position limits exist

Position limits force diversification and liquidity discipline. VaR can look acceptable while one position is dangerously concentrated if the historical volatility estimate is stale or the market is illiquid.

## Scenario Limits

A scenario limit caps the loss under a specified stress scenario:

> "The portfolio must not lose more than $25 million under a repeat of the 2008 credit-spread shock."

This is different from VaR because a scenario does not necessarily carry a probability. It is a conditional loss estimate:

$$
\text{If scenario X occurs, loss must be no more than Y.}
$$

Scenario limits are useful when:

- risk factors move jointly,
- correlations change,
- options have nonlinear payoffs,
- liquidity disappears,
- or the firm wants to test survival under extreme conditions.

See: [[Stress Testing and Scenario Analysis]].

## Stop-Loss Limits

A stop-loss limit is based on **realized losses**:

> "If the position loses $8 million in a month, reduce or close it."

This is an ex-post rule. It activates after losses have already occurred.

Stop-loss actions can include:

- selling the position,
- reducing exposure,
- hedging with derivatives,
- buying index puts,
- or shifting into a lower-risk allocation.

When the hedging rule is designed to protect a portfolio as it falls, it is often called **portfolio insurance**.

### Stop-loss tradeoff

| Advantage | Disadvantage |
|---|---|
| Prevents a small loss from becoming a catastrophic loss | Can force selling during temporary drawdowns |
| Clear and easy to monitor | Can crystallize losses and cause whipsaw |
| Useful for discipline and governance | May worsen liquidity pressure if many investors have similar triggers |

## VaR Limit vs Stop-Loss Limit

This is a common exam trap.

| Feature | VaR limit | Stop-loss limit |
|---|---|---|
| Timing | Ex ante | Ex post |
| Based on | Forecast loss distribution | Actual realized loss |
| Form | "1-day 5% VaR must be below $X" | "Reduce exposure after losing $X" |
| Purpose | Control probabilistic future risk | Stop realized drawdown |

VaR says what loss might occur. Stop-loss says what to do after losses occur.

## Capital Allocation

Capital allocation is the firm-level cousin of portfolio allocation.

Instead of asking:

> Which securities should receive portfolio weight?

the firm asks:

> Which business units or activities should receive firm capital?

Ignoring risk, the firm would allocate capital to the highest expected return activities. Risk management changes the question:

> Which activities produce the best return **for the capital needed to survive their risks**?

## Economic Capital

**Economic capital** is the amount of capital a firm estimates it needs to survive severe losses from its business risks.

It is usually linked to high-confidence tail loss over a horizon, such as:

$$
\text{Economic capital} \approx \text{loss at 99.9% confidence over one year}
$$

Economic capital is internal and risk-based. It should not be confused with regulatory capital, which is externally imposed by regulators.

## VaR Allocation Across Business Units

A firm can allocate risk capital using VaR:

1. Estimate VaR for each business unit.
2. Estimate diversification across units.
3. Allocate total acceptable firm VaR across units.
4. Compare each unit's return to the VaR or economic capital it consumes.
5. Increase capital for units with attractive risk-adjusted returns and reduce capital for units that consume too much capital for too little return.

Example:

| Business unit | Expected annual profit | Economic capital | Profit / economic capital |
|---|---:|---:|---:|
| Equity desk | $12 million | $100 million | 12.0% |
| FX desk | $10 million | $50 million | 20.0% |
| Credit desk | $18 million | $180 million | 10.0% |

Ignoring risk, the credit desk looks best because it has the highest profit. After risk adjustment, the FX desk is most efficient.

The broad industry label for this kind of comparison is **risk-adjusted return on capital**:

$$
\text{Risk-adjusted return on capital}
= \frac{\text{Risk-adjusted return}}{\text{Economic capital}}
$$

The key CFA idea is not the label. The key is that risk measures change capital allocation away from raw return and toward return per unit of capital at risk.

## Worked Example: Classifying Limits

A risk committee believes high-yield bonds will fall if the economy enters recession. It therefore says:

> High-yield bonds may not exceed 10% of assets under management.

Classification:

- The rule caps the **allocation** to an asset class.
- It does not specify a maximum loss under a recession scenario.
- It does not require action after an actual loss.

So it is a:

$$
\boxed{\text{Position limit}}
$$

If the rule instead said:

> Under a recession scenario, the portfolio's high-yield bond losses may not exceed $20 million.

that would be a **scenario limit**.

If the rule said:

> Reduce high-yield exposure if the position loses more than 6% in a month.

that would be a **stop-loss limit**.

## Institution-Specific Emphasis

| Institution | Typical risk focus | Why |
|---|---|---|
| **Banks** | VaR, economic capital, leverage, sensitivities, stress tests, asset-liability mismatch | Trading books, leverage, regulation, balance-sheet risk |
| **Traditional asset managers** | Position limits, tracking error, active share, beta, duration, scenario analysis | Relative-return mandates and lower leverage |
| **Hedge funds** | VaR, leverage, gross exposure, scenario analysis, drawdown limits | Long-short exposure, derivatives, leverage, nonlinear returns |
| **Pension funds** | Surplus at risk, asset-liability matching, interest-rate sensitivity | Assets must fund long-term liabilities |
| **Insurers** | Economic capital, reserve adequacy, ALM, scenario analysis | Investment risk interacts with insurance liabilities |

## Exam Traps

| Trap | Correct response |
|---|---|
| Call an exposure cap a scenario limit because the reason is macro concern | If the rule limits allocation size, it is a position limit |
| Confuse VaR with stop-loss | VaR is forecast risk; stop-loss is a realized-loss trigger |
| Assume tighter limits are always better | Tight limits can impair profitability and prevent efficient risk taking |
| Add business-unit VaRs mechanically | Diversification means total firm VaR may be less than the sum |
| Choose projects by raw expected return | Capital allocation should consider risk and economic capital |
| Confuse economic capital with regulatory capital | Economic capital is internally estimated capital needed for survival; regulatory capital is externally required |
| Apply hedge-fund leverage measures to a traditional long-only manager | Traditional managers focus more on relative risk, position limits, and active share |

## Memory Hook

> **Budget before, position now, scenario if, stop after.**

- **Risk budget:** before the risk is taken.
- **Position limit:** how large the exposure can be now.
- **Scenario limit:** what happens if a specified stress occurs.
- **Stop-loss:** what to do after realized losses breach the threshold.

## Exam-Day Checklist

1. Read the limit language literally.
2. If it caps a risk metric such as VaR or tracking error, classify it as risk budgeting.
3. If it caps exposure size, classify it as a position limit.
4. If it caps loss under a named stress, classify it as a scenario limit.
5. If it forces action after an actual loss, classify it as a stop-loss limit.
6. For capital allocation, compare return to risk or economic capital, not raw return alone.
7. Watch for diversification benefits across units before adding risk measures mechanically.

## Related Concepts

- [[Measuring and Managing Market Risk]]
- [[Parametric Historical and Monte Carlo VaR]]
- [[Incremental VaR]]
- [[Conditional VaR (CVaR) and Expected Shortfall]]
- [[Stress Testing and Scenario Analysis]]
- [[Active Risk and Tracking Error]]
- [[Information Ratio]]
