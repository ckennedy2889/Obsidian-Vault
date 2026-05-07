---
title: Structural Models
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-analysis, credit-risk, structural-models]
aliases: [structural model, structural credit model, Merton model, Black-Scholes-Merton credit model, BSM credit model]
---

# Structural Models

## The Real-World Analogy

Imagine a homeowner with a house worth $400,000 and a mortgage balance of $300,000.

The homeowner's equity is worth roughly:

$$
\text{House value} - \text{Mortgage balance} = 400{,}000 - 300{,}000 = 100{,}000
$$

If the house value rises to $500,000, the homeowner keeps the upside.

If the house value falls to $250,000, the mortgage is bigger than the house value. The homeowner is underwater. In a non-recourse setting, the homeowner may walk away and hand the house to the lender.

That is the entire intuition behind a structural credit model.

The company is the house.

The company's debt is the mortgage.

Shareholders are the homeowner.

Bondholders are the lender.

Default becomes more likely when the value of the company's assets falls near or below the value of its debt.

```text
Company asset value
        |
        v
Compared with debt obligation
        |
        v
If assets < debt, equity walks away and bondholders absorb loss
```

That is why structural models are called structural. They look at the structure of the balance sheet and ask:

> Is the asset value high enough, relative to debt, to keep the company solvent?

## The Big Idea

[[Level 2/Generated Notes/07 - Fixed Income/Structural Models]] are credit-risk models that explain default from the structure of a company's balance sheet.

The core rule:

$$
\text{Default occurs when firm asset value falls below the debt obligation.}
$$

In symbols:

$$
V_A < D
$$

where:

| Symbol | Meaning |
|---|---|
| $V_A$ | Market value of the firm's assets |
| $D$ | Debt obligation or default barrier |

If $V_A$ is comfortably above $D$, the company has an equity cushion.

If $V_A$ is close to $D$, a modest decline in asset value can push the company into distress.

If $V_A$ is below $D$, the firm is economically insolvent because the assets cannot fully repay the debt.

The model is not just saying "weak companies default."

It is saying:

```text
Asset value distribution
        |
        v
Probability mass below debt barrier
        |
        v
Probability of default
        |
        v
Expected loss and credit spread
```

So the [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] comes from the probability that the future firm value lands below the debt barrier.

## Why CFA Tests This

CFA tests structural models because they force you to understand credit risk as an economic mechanism, not just as a rating label or a spread quote.

A [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings|credit rating]] tells you an ordinal rank.

A [[Credit spread]] tells you the market compensation required for risk.

A [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] tells you the conditional probability of default in a period.

A structural model asks the deeper question:

> What balance-sheet mechanics make default happen in the first place?

That distinction matters because fixed-income vignettes often mix these models:

| Concept | What it answers |
|---|---|
| [[Level 2/Generated Notes/07 - Fixed Income/Structural Models]] | Why default occurs |
| [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]] | When default is statistically likely to occur |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]] | How the issuer is ranked by credit quality |
| [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]] | How rating changes affect value before default |
| [[Credit Valuation Adjustment]] | How default risk reduces risky bond value |

The exam trap is to treat all credit models as interchangeable. They are not.

Structural models are about the economic cause of default.

Reduced-form models are about statistical default timing.

## The Merton Model Intuition

The classic structural model is the Merton model, developed from the Black-Scholes-Merton option pricing framework.

The simplified setup:

1. The firm has assets worth $V_A$.
2. The firm has one zero-coupon debt obligation with face value $D$ due at maturity $T$.
3. At $T$, the firm either repays the debt or defaults.
4. Equityholders have limited liability.

At maturity:

| Condition at maturity | What happens |
|---|---|
| $V_A > D$ | Firm repays debt; equity keeps residual value |
| $V_A \le D$ | Firm defaults; bondholders receive the firm assets |

Equity value at maturity is:

$$
E_T = \max(V_A - D, 0)
$$

That payoff is exactly the payoff of a call option.

So in the Merton framework:

$$
\text{Equity} = \text{Call option on firm assets}
$$

with:

| Option input | Corporate-credit interpretation |
|---|---|
| Underlying asset | Firm assets |
| Strike price | Face value of debt |
| Maturity | Debt maturity |
| Volatility | Volatility of firm asset value |
| Risk-free rate | Default-free interest rate |

This is the key insight.

Shareholders do not own the assets in the same way an all-equity owner would. Economically, when there is risky debt outstanding, shareholders own the upside after debt is paid. That is a call option.

## Why Equity Is a Call Option

A call option gives the holder the right, but not the obligation, to buy an asset at a strike price.

For shareholders:

| Call option language | Corporate language |
|---|---|
| Underlying asset | Firm assets |
| Strike price | Debt repayment amount |
| Exercise if asset value exceeds strike | Repay debt if firm value exceeds debt |
| Let option expire if asset value is below strike | Default if assets cannot cover debt |

At maturity, shareholders decide economically:

```text
If assets > debt:
    Pay debt and keep residual value

If assets <= debt:
    Walk away; equity value is zero
```

That produces:

$$
E_T = \max(V_A - D, 0)
$$

Example:

| Firm asset value at maturity | Debt due | Equity payoff |
|---:|---:|---:|
| 150 | 100 | 50 |
| 120 | 100 | 20 |
| 100 | 100 | 0 |
| 80 | 100 | 0 |

The equity payoff cannot go below zero because of limited liability.

That limited downside plus unlimited upside is option-like.

## Risky Debt as Risk-Free Debt Minus a Put Option

If equity is a call option, what are bondholders holding?

Bondholders would like to hold risk-free debt worth $D$ at maturity.

But if the firm assets fall below $D$, bondholders do not receive full repayment. They receive the assets instead.

At maturity, risky debt pays:

$$
B_T = \min(D, V_A)
$$

This can be rewritten as:

$$
B_T = D - \max(D - V_A, 0)
$$

The second term is the payoff of a put option on the firm assets with strike $D$.

So:

$$
\text{Risky debt} = \text{Risk-free debt} - \text{Put option on firm assets}
$$

This matters because the bondholder has effectively sold default protection to shareholders.

If the firm performs well, bondholders receive the promised debt payoff.

If the firm performs badly, bondholders absorb the shortfall.

```text
Risk-free bond value
        |
        | subtract value of default option
        v
Risky bond value
```

This is the same economic idea behind [[Credit Valuation Adjustment]]:

$$
V_{\text{risky}} = V_{\text{default-free}} - \text{CVA}
$$

In a structural model, the "CVA-like" loss comes from the put option embedded in risky debt.

## The Default Barrier

The default barrier is the firm-value level that triggers default.

In the simplest Merton model:

$$
\text{Default barrier} = D
$$

where $D$ is the face value of debt due at maturity.

If:

$$
V_A < D
$$

the company cannot fully repay debtholders.

The higher the debt obligation, the higher the default barrier.

That is why leverage increases credit risk.

```text
Higher debt
   -> higher default barrier
   -> less asset-value decline needed to trigger default
   -> higher probability of default
   -> wider credit spreads
```

This is also why two companies can have the same asset volatility but different credit spreads.

If one company has much more debt, more of the asset-value distribution falls below the default barrier.

## Probability of Default in a Structural Model

In a structural model, [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]] is the probability that future firm asset value ends below the default barrier.

Conceptually:

$$
P(\text{default}) = P(V_A(T) < D)
$$

The future asset value is uncertain. The model assumes some probability distribution for it, usually connected to option-pricing assumptions.

The probability of default increases when:

| Driver | Why POD rises |
|---|---|
| Asset value falls | Less cushion above debt |
| Debt increases | Default barrier moves upward |
| Asset volatility rises | Wider distribution creates more downside tail risk |
| Time horizon lengthens | More time for asset value to drift into the default region |
| Risk-free rate changes | Affects discounting and option valuation mechanics |

The most exam-relevant drivers are leverage and volatility.

Higher leverage:

$$
\frac{D}{V_A} \uparrow \Rightarrow P(\text{default}) \uparrow
$$

Higher asset volatility:

$$
\sigma_A \uparrow \Rightarrow P(\text{default}) \uparrow
$$

Why does volatility raise default probability?

Because debt has limited upside but exposed downside.

For shareholders, volatility can be attractive because the equity call option becomes more valuable.

For bondholders, volatility is dangerous because the left tail gets fatter.

```text
More asset volatility
        |
        v
More chance assets fall below debt
        |
        v
Higher value of default put
        |
        v
Lower risky debt value and wider spread
```

### Distance to Default

NotebookLM emphasized a related CFA phrase: distance to default.

Distance to default measures how far the firm's asset value is from the default barrier, usually in volatility-adjusted terms.

Plain English:

> How many bad moves away is this company from being unable to repay debt?

The intuition:

```text
Current asset value
        |
        | distance above debt barrier
        v
Default barrier
```

If asset value is far above debt and asset volatility is low, distance to default is large.

If asset value is barely above debt or asset volatility is high, distance to default is small.

In the Black-Scholes-Merton setup, risk-neutral default probability is commonly linked to:

$$
N(-d_2)
$$

where $N(\cdot)$ is the standard normal cumulative distribution function.

You do not usually need to derive $d_2$ in the CFA fixed-income credit-analysis reading, but the interpretation matters:

| Term | Meaning |
|---|---|
| $d_2$ | Distance-like option-pricing term tied to ending above the strike/default barrier |
| $N(-d_2)$ | Risk-neutral probability of ending below the default barrier |

Exam implication:

If $d_2$ falls, $N(-d_2)$ rises, so model-implied default probability rises.

That can happen because asset value falls, debt rises, or asset volatility rises.

## Worked Numerical Example: Equity as a Call

Suppose a firm has one zero-coupon bond due in one year with face value $100 million.

At maturity, the firm asset value could be:

| Scenario | Asset value $V_A$ | Debt due $D$ | Equity payoff $\max(V_A-D,0)$ | Debt payoff $\min(D,V_A)$ |
|---|---:|---:|---:|---:|
| Strong | 140 | 100 | 40 | 100 |
| Stable | 110 | 100 | 10 | 100 |
| Breakeven | 100 | 100 | 0 | 100 |
| Distress | 70 | 100 | 0 | 70 |

Notice the payoff shape:

| Stakeholder | Upside | Downside |
|---|---|---|
| Shareholders | Benefit after debt is repaid | Limited to losing equity |
| Bondholders | Capped at promised repayment | Exposed to default loss |

So shareholders are long a call option.

Bondholders are short the default put.

Now suppose asset volatility rises. The strong scenario may become even stronger, which shareholders like. But the distress scenario may become more likely or more severe, which bondholders dislike.

That is why higher asset volatility can increase equity value while reducing risky debt value.

This is a common intuition trap.

## Worked Numerical Example: Default Probability From the Distribution

Suppose a firm has:

| Input | Value |
|---|---:|
| Current asset value | 120 |
| Debt due at maturity | 100 |
| Expected future asset value scenarios | 140, 120, 95, 70 |
| Scenario probabilities | 30%, 40%, 20%, 10% |

Default occurs when:

$$
V_A < 100
$$

The default scenarios are:

| Scenario | Asset value | Default? | Probability |
|---|---:|---|---:|
| Strong | 140 | No | 30% |
| Normal | 120 | No | 40% |
| Weak | 95 | Yes | 20% |
| Severe | 70 | Yes | 10% |

So:

$$
P(\text{default}) = 20\% + 10\% = 30\%
$$

Expected bond payoff:

| Scenario | Debt payoff | Probability | Weighted payoff |
|---|---:|---:|---:|
| Strong | 100 | 30% | 30.0 |
| Normal | 100 | 40% | 40.0 |
| Weak | 95 | 20% | 19.0 |
| Severe | 70 | 10% | 7.0 |

$$
\text{Expected payoff} = 30 + 40 + 19 + 7 = 96
$$

If the risk-free one-year rate is 4%, a rough risk-neutral-style present value would be:

$$
PV = \frac{96}{1.04} = 92.31
$$

A default-free payoff of 100 would be worth:

$$
PV_{\text{default-free}} = \frac{100}{1.04} = 96.15
$$

Credit loss in value:

$$
96.15 - 92.31 = 3.84
$$

That valuation reduction is the same broad idea as [[Credit Valuation Adjustment]]: risky debt is worth less than otherwise identical default-free debt.

## Link to Credit Spreads

A [[Credit spread]] compensates investors for bearing credit risk and related premia.

In structural-model terms:

```text
Higher default probability or loss severity
        |
        v
Lower risky bond value
        |
        v
Higher required yield
        |
        v
Wider credit spread
```

The spread should widen when:

| Change | Structural-model interpretation |
|---|---|
| Firm asset value decreases | Cushion over debt shrinks |
| Debt increases | Default barrier rises |
| Asset volatility increases | Default put becomes more valuable |
| Debt maturity lengthens | More time for firm value to fall below barrier |
| Expected recovery decreases | Bondholder loss given default increases |

But be careful: structural models explain default probability through asset value and leverage. They do not automatically give you the entire market spread.

Market spreads may also include:

- [[Liquidity premium]]
- risk aversion
- tax effects
- market technicals
- model uncertainty
- compensation for unexpected loss

So the model-implied spread and market spread can differ.

That difference can create an analyst view:

| Analyst belief | Possible interpretation |
|---|---|
| Market spread too wide relative to structural risk | Bond may be undervalued |
| Market spread too tight relative to structural risk | Bond may be overvalued |

## The Balance-Sheet Mechanism

The model begins with a balance sheet:

```text
Assets
  = Debt + Equity
```

But the risk allocation is not symmetric.

Debt has priority.

Equity is residual.

So the balance sheet can be viewed as:

```text
Firm assets
        |
        +--> Bondholders get first claim up to D
        |
        +--> Shareholders get residual above D
```

When asset value is high:

$$
V_A > D
$$

both groups are fine.

When asset value is low:

$$
V_A < D
$$

shareholders are wiped out and bondholders take the company assets.

This is why a structural model is not just a statistical model. It tells a story about legal claims, priority, leverage, and limited liability.

## Key Inputs

Structural models need inputs that are easy to describe but difficult to observe.

| Input | Meaning | Why it matters |
|---|---|---|
| Firm asset value | Total market value of the company's operating assets | Determines cushion above debt |
| Asset volatility | Volatility of firm asset value | Determines tail risk |
| Debt level / default barrier | Promised debt repayment or threshold | Determines when default occurs |
| Time horizon | Usually debt maturity | More time changes default probability |
| Risk-free rate | Discounting and option-pricing input | Affects option values |
| Debt structure | Maturity, priority, covenants | Changes the true default barrier |

The big practical problem:

> Equity trades. Debt may trade. Firm assets do not trade directly.

So analysts often infer hidden asset value and hidden asset volatility from observable equity market data.

The common implementation idea is:

| Observable input | Why it helps |
|---|---|
| Market value of equity | Equity is modeled as a call option on assets |
| Equity volatility | Helps infer asset volatility |
| Face value of debt | Proxy for the default barrier |
| Risk-free rate | Option-pricing and discounting input |
| Time to maturity | Horizon for default/barrier comparison |

The model solves backward from the traded equity claim to infer the untraded asset claim.

That is clever, but it is also fragile.

If the equity price is distorted, the debt structure is simplified too aggressively, or the default barrier is wrong, the inferred asset value and default probability can be wrong.

That inference is one reason structural models can be powerful but messy.

## Strengths

Structural models are useful because they provide an economic explanation for default.

| Strength | Why it matters |
|---|---|
| Explains why default occurs | Default follows from assets falling below liabilities |
| Connects credit risk to leverage | Higher debt raises the default barrier |
| Connects credit risk to volatility | More asset volatility increases downside tail risk |
| Uses option-pricing intuition | Equity and risky debt payoffs become easier to understand |
| Helps link equity markets and credit markets | Equity volatility can signal changing credit risk |

The most important exam phrase:

> Structural models explain why default occurs.

They are not merely classification tools.

They are not just ratings.

They are not just spread-duration calculations.

They are models of the capital structure.

## Limitations

Structural models also have important weaknesses.

| Limitation | Why it matters |
|---|---|
| Firm asset value is not directly observable | The model needs a key input that does not trade directly |
| Asset volatility is hard to estimate | Equity volatility is observable, but asset volatility must be inferred |
| Default barrier can be ambiguous | Real firms have many debt issues, covenants, bank lines, and maturities |
| Simple capital-structure assumptions may be unrealistic | Real debt is not one zero-coupon bond |
| May require information best known to management | Outside investors may not know the true asset values and liabilities |
| Accounting debt may not capture economic obligations | Off-balance-sheet or hidden obligations can distort the default barrier |

CFA likes this distinction:

[[Level 2/Generated Notes/07 - Fixed Income/Structural Models]] may require "inside" information best known to company management.

[[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]] can be based on observable market and firm variables.

That does not mean structural models are useless or outdated.

It means their input demands can be harder.

## Comparison With Reduced-Form Models

The cleanest comparison:

| Feature | Structural models | [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]] |
|---|---|---|
| Main question | Why does default occur? | When might default occur? |
| Default mechanism | Asset value falls below debt/default barrier | Default modeled statistically, often through [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]] / default intensity |
| Core framework | Option pricing and capital structure | Statistical models, regression, hazard rates |
| Key variables | Firm value, asset volatility, debt level | Firm ratios, macro variables, market variables |
| Default trigger | Endogenous to firm balance sheet | Exogenous/random in the model |
| Data challenge | Needs asset value and asset volatility | Uses more observable variables |
| Major weakness | Simplifying assumptions and hard-to-observe inputs | Less economic explanation for why default occurs |

Memory version:

```text
Structural = why default happens.
Reduced-form = when default may happen.
```

Do not choose an answer just because it says reduced-form models are newer. The date of development is usually not the economically relevant distinction.

## Structural Models and Credit Migration

Structural models focus on default, but their logic also helps explain [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]].

If the firm's asset cushion shrinks but does not disappear, the issuer may not default yet.

Instead:

```text
Lower asset value or higher leverage
        |
        v
Higher default probability
        |
        v
Lower credit quality
        |
        v
Possible downgrade
        |
        v
Wider spread and price decline
```

So a structural deterioration can show up first as:

- a wider [[Credit spread]]
- a higher [[CDS spread]]
- a downgrade
- a higher [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]] loss
- a lower risky bond value

Default is the endpoint. Migration is often the path toward it.

## Structural Models and CDS

[[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] pricing depends heavily on default probability and recovery assumptions.

A structural model can help form a view on default probability.

If a company becomes more leveraged or more volatile, the model-implied default probability rises.

That should make CDS protection more expensive:

$$
\text{Higher POD} \Rightarrow \text{higher protection leg value} \Rightarrow \text{higher CDS spread}
$$

But CDS markets often imply risk-neutral default probabilities, not necessarily historical physical probabilities.

That means:

| Probability type | Meaning |
|---|---|
| Actual / physical POD | Expected real-world default likelihood |
| Risk-neutral POD | Pricing probability that embeds risk premia |

Structural models can be estimated under either lens depending on purpose. CFA questions usually signal which probability concept is being used.

## Exam Trap: Higher Volatility Can Help Equity but Hurt Debt

This one is sneaky.

If equity is a call option on firm assets, then higher asset volatility can increase the value of equity.

Why?

Because call options benefit from upside volatility while downside is limited.

But bondholders are effectively short a put option.

Higher volatility makes the default put more valuable.

That reduces risky debt value.

```text
Higher asset volatility
        |
        +--> equity call option more valuable
        |
        +--> default put more valuable
                 |
                 v
             risky debt less valuable
```

If a vignette says a highly leveraged firm takes on a very risky project, shareholders may like it while bondholders dislike it. This is an asset-substitution problem.

## Exam Trap: Risk-Neutral POD Is Not Historical POD

NotebookLM also flagged the probability distinction.

The Merton model is built from option-pricing logic, and option-pricing usually works in a risk-neutral valuation framework.

That means the model-implied probability of default may be a risk-neutral probability, not a real-world historical probability.

| Probability | What it means |
|---|---|
| Actual / physical POD | Expected real-world frequency of default |
| Risk-neutral POD | Pricing probability that embeds compensation for bearing credit risk |

Risk-neutral POD can be higher than historical POD because investors require compensation for uncertainty, downside skew, and systematic credit risk.

Exam implication:

If the question is about pricing a risky bond, CDS, or option-based credit model, be alert for risk-neutral language.

If the question is about forecasting actual defaults for credit research, historical or physical probabilities may be more relevant.

## Exam Trap: Structural Does Not Mean "Uses Only Accounting Ratios"

Because structural models are based on the balance sheet, it is tempting to think they are just accounting-ratio models.

That is too thin.

Structural models use the economic structure of claims:

- asset value
- debt priority
- default barrier
- equity residual claim
- option-like payoffs

Accounting ratios may help estimate inputs, but the model itself is not merely "high debt-to-assets means risky."

The deeper mechanism is:

$$
P(V_A < D)
$$

## Exam Trap: Structural Models Do Not Need to Predict the Exact Default Date

The simplest Merton model often places default at debt maturity.

Real companies can default before maturity because of:

- missed coupon payments
- covenant violations
- liquidity shortages
- refinancing failure
- cross-default provisions

So do not overstate the model.

Structural models explain the economic condition that creates default pressure. They may simplify the timing of default.

Reduced-form models are more directly focused on modeling default timing through intensity or hazard rates.

## Mini Vignette Scenarios

### Scenario 1: More Debt

A company issues a large new bond to fund a share repurchase.

Structural interpretation:

```text
Debt rises
   -> default barrier rises
   -> equity cushion shrinks
   -> probability of default rises
   -> credit spread widens
```

Bondholder implication:

The existing bonds may fall in price, even if the company's operating assets have not changed.

### Scenario 2: Asset Volatility Rises

A stable utility pivots into a speculative commodity-linked business.

Structural interpretation:

```text
Asset volatility rises
   -> left-tail default probability rises
   -> default put becomes more valuable
   -> risky debt value falls
```

Equityholders may still like the project if upside is large.

Bondholders care more about downside tail risk.

### Scenario 3: Asset Value Rises

A company wins a major long-term contract and its enterprise value rises.

Structural interpretation:

```text
Asset value rises
   -> cushion above debt grows
   -> probability of default falls
   -> spreads tighten
   -> risky debt value rises
```

This can improve both equity and debt value.

### Scenario 4: Hidden Liabilities

A company has off-balance-sheet obligations or understated debt-like commitments.

Structural interpretation:

The stated default barrier is too low.

The model may understate default probability.

Exam implication:

If a question says structural models require information best known to management, this is the idea.

## Decision Table

| If the vignette says... | Think... | Likely effect |
|---|---|---|
| Higher leverage | Default barrier rises | Higher POD, wider spreads |
| Higher asset volatility | More downside tail risk | Higher POD, lower risky debt value |
| Asset value falls | Less cushion | Higher POD |
| Asset value rises | More cushion | Lower POD |
| Debt maturity lengthens | More time for downside movement | Often higher cumulative POD |
| Model uses hazard rates and observable variables | Reduced-form, not structural | Predicts when, not why |
| Model treats equity as call on assets | Structural | Option-pricing framework |
| Model says bondholders own assets and shareholders own call | Structural | Merton logic |

## Memory Hooks

Structural models:

```text
Assets vs debt.
If assets fall below debt, default.
Equity = call.
Debt = risk-free bond minus put.
```

The shortest version:

> Structural = balance-sheet structure.

Another exam hook:

```text
S in structural = Solvency structure.
R in reduced-form = Regression / random timing.
```

## Common Exam Traps

| Trap | Why it is wrong | Better exam response |
|---|---|---|
| "Structural models predict when default occurs" | They primarily explain why default occurs | Reduced-form models focus more on statistical timing |
| "Reduced-form models explain default through asset value falling below liabilities" | That is structural-model logic | Reduced-form models use hazard/default intensity |
| "Equity is like a put option" | Equity has upside after debt is repaid and limited downside | Equity is a call option on firm assets |
| "Risky debt is risk-free debt plus a put" | The default put is a cost to bondholders | Risky debt = risk-free debt - put |
| "Higher asset volatility is good for all investors" | It can help equity but hurt debt | Higher volatility raises default-put value |
| "Structural models use only public observable variables" | Key inputs like asset value and asset volatility are hard to observe | Reduced-form models are more associated with observable variables |
| "Model development date determines the better answer" | CFA cares about mechanism, not age | Focus on why vs when and input requirements |
| "Credit spread equals expected loss exactly" | Spreads include risk premia and other effects | Expected loss is a core component, not the whole spread |

## Exam-Day Checklist

When you see a structural-model question, ask:

1. Is the model using firm assets, debt, and an option-pricing view?
2. Is default caused by asset value falling below the debt/default barrier?
3. Is equity being treated as a call option on assets?
4. Is risky debt being treated as risk-free debt minus a put?
5. Did leverage increase or decrease?
6. Did asset volatility increase or decrease?
7. Is the question asking why default occurs or when default may occur?
8. Are the key inputs directly observable or hard to estimate?

If the answer says:

> Structural models explain why default occurs.

that is usually the safe spine of the concept.

## Related Concepts

- [[Credit analysis]]
- [[Credit risk]]
- [[Default risk]]
- [[Defaultable debt]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Expected Loss]]
- [[Credit Valuation Adjustment]]
- [[Credit spread]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Migration Risk]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Ratings]]
- [[Level 2/Generated Notes/07 - Fixed Income/Reduced Form Models]]
- [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]]
- [[CDS spread]]
- [[Option contract]]
- [[Call option]]
- [[Put option]]
- [[Leverage]]
- [[Bankruptcy]]
