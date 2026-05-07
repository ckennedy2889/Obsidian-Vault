---
title: "CFA L2 - Weighted Average Cost of Capital (WACC)"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, WACC, cost-of-capital, CAPM, valuation, capital-structure]
aliases: ["WACC", "Weighted Average Cost of Capital", "Cost of Capital"]
---

# Weighted Average Cost of Capital (WACC)

Think of WACC as the "rental price" a company pays to use other people's money. Just like you pay rent to live in an apartment, a company must pay its investors — both lenders and shareholders — for the privilege of using their cash to run the business. WACC is what you get when you blend all those rental prices together into a single number.

---

## Why Does Capital Have a Cost?

Say you want to build a sneaker factory. You don't have the cash, so you go looking for investors. But here's the thing — those investors aren't handing over money out of the goodness of their hearts. They're giving up the chance to spend or invest that money elsewhere. They're taking a risk that your factory might fail. In return, they expect a reward.

That reward — the return investors *demand* for handing over their money — is the **cost of capital** (defined as: the minimum return a company must earn on its investments to satisfy its investors).

From the company's side, this creates a **hurdle**: any project the company takes on must earn at least enough to cover that cost, otherwise it's actively destroying value. WACC is how you calculate exactly where that hurdle sits.

---

## Debt vs. Equity: The Two Ways to Fund a Business

Most companies raise money from two main sources, and each has a very different personality:

| | **Debt** | **Equity** |
|---|---|---|
| **What it is** | Borrowed money — bank loans, bonds | Ownership stakes — shares of stock |
| **Analogy** | A car loan — fixed payments, bank gets paid first | A business partner — shares profits, last in line if things go wrong |
| **Payments** | Mandatory interest payments | No guaranteed payments (dividends are optional) |
| **Risk to investor** | Lower — they're first in line if the company fails | Higher — they're last in line |
| **Cost to company** | Lower (less risk = lower demanded return) | Higher (more risk = higher demanded return) |
| **Tax treatment** | Interest is tax-deductible | Dividends are not tax-deductible |

This asymmetry — debt being cheaper *and* tax-advantaged — is why companies don't just fund everything with equity. But too much debt makes the company fragile (see [[Capital Structure]]).

---

## The WACC Formula

**Final formula:**

$$WACC = w_d r_d (1 - t) + w_p r_p + w_e r_e$$

**Broken down:**

| Symbol | Meaning |
|---|---|
| $w_d$, $w_p$, $w_e$ | Weights — the proportion of debt, preferred stock, and equity in the capital structure |
| $r_d$ | [[Cost of Debt]] — the interest rate the company pays on its borrowings |
| $(1 - t)$ | Tax shield adjustment — reduces the cost of debt because interest is tax-deductible |
| $r_p$ | [[Cost of Preferred Stock]] — the dividend yield on preferred shares |
| $r_e$ | [[Cost of Equity]] — the return shareholders expect |

**Derivation — the intuition:**

WACC is just a weighted average. If a company is 40% funded by debt at 5% and 60% funded by equity at 10%, then the blended cost is:

$$(0.40 \times 5\%) + (0.60 \times 10\%) = 2\% + 6\% = 8\%$$

In plain English: for every dollar the company uses, it costs 8 cents on average to maintain. That's the hurdle every project needs to clear.

The weights ($w_d$, $w_p$, $w_e$) should always be based on **market values**, not book values — because market value reflects what investors actually think things are worth today, not what was recorded on a balance sheet years ago.

---

## The Tax Shield on Debt

This is one of the most important — and counterintuitive — concepts in corporate finance.

When a company pays interest on its debt, that interest is **tax-deductible**. That means the government is effectively subsidising part of the cost. Here's how the maths works:

Say a company borrows at 10% and has a 30% tax rate:

$$\text{After-tax cost of debt} = r_d \times (1 - t) = 10\% \times (1 - 0.30) = 7\%$$

The company pays 10% in interest to the bank, but because interest reduces taxable income, it saves 3% on its tax bill. The *real* cost is only 7%.

**Analogy:** Imagine your employer lets you pay for your work laptop before tax. The laptop costs $1,000, but if your tax rate is 30%, you only feel $700 coming out of your pocket. The government is quietly picking up the rest. That's the tax shield — the government is sharing in the cost of debt financing without getting equity in return.

This is why debt is always shown as $r_d(1-t)$ in the WACC formula. Equity gets no such gift — dividends are paid from after-tax profits.

---

## Calculating the Cost of Equity — CAPM

Equity investors don't send you a bill. They don't have a stated interest rate. So how do you figure out what return they expect?

The answer is the **Capital Asset Pricing Model (CAPM)** (defined as: a model that estimates the required return on equity based on systematic risk):

$$r_e = R_f + \beta \times ERP$$

| Component | Definition | Example |
|---|---|---|
| $R_f$ — [[Risk-Free Rate]] | Return on a "safe" investment — typically a government bond | 3% (10-year Treasury yield) |
| $\beta$ — [[Beta]] | How "jumpy" the stock is relative to the overall market. A beta of 1.2 means the stock moves 20% more than the market in either direction | 1.2 |
| $ERP$ — [[Equity Risk Premium]] | The *extra* return investors demand for taking stock market risk over the risk-free rate | 5% |

So if $R_f = 3\%$, $\beta = 1.2$, and $ERP = 5\%$:

$$r_e = 3\% + 1.2 \times 5\% = 3\% + 6\% = 9\%$$

**Analogy:** Think of $R_f$ as the return you'd get sleeping with your money under a mattress (government bond). The $ERP$ is the extra bribe you need to convince yourself to invest in the stock market instead. And $\beta$ scales that bribe up or down based on how risky *this particular stock* is versus the market average.

A stock with $\beta = 1.0$ moves in lockstep with the market. $\beta = 1.5$ means it's 50% more volatile — more reward expected. $\beta = 0.5$ means it barely moves — less reward needed.

---

## Calculating the Cost of Debt

Unlike equity, debt has a stated interest rate — but that's not necessarily the cost you should use. What matters is the **current** cost of borrowing, not what was locked in years ago.

For companies with publicly traded bonds, the best estimate is the **Yield to Maturity (YTM)** (defined as: the total return anticipated on a bond if held until it matures — it reflects the market's current view of the company's credit risk).

For private companies or those without traded bonds, analysts use **matrix pricing** — looking at the interest rates of similar companies with the same credit rating and inferring what this company would have to pay.

---

## Worked Numerical Example — Solar-Go Corp

Let's build WACC from scratch for Solar-Go Corp, a fictional solar energy company.

**Given information:**

| Item | Value |
|---|---|
| Capital structure | 40% Debt, 60% Equity |
| Pre-tax cost of debt ($r_d$) | 6% |
| Corporate tax rate ($t$) | 25% |
| Risk-free rate ($R_f$) | 3% |
| Beta ($\beta$) | 1.2 |
| Equity Risk Premium ($ERP$) | 5% |

**Step 1 — Cost of Equity via CAPM:**

$$r_e = 3\% + 1.2 \times 5\% = 3\% + 6\% = 9\%$$

**Step 2 — After-Tax Cost of Debt:**

$$r_d(1 - t) = 6\% \times (1 - 0.25) = 6\% \times 0.75 = 4.5\%$$

**Step 3 — Plug into WACC:**

$$WACC = (0.40 \times 4.5\%) + (0.60 \times 9\%)$$

$$WACC = 1.8\% + 5.4\% = \mathbf{7.2\%}$$

Solar-Go pays an average of **7.2 cents for every dollar** it uses to run the business. That's the hurdle every new project must clear.

---

## What is WACC Actually Used For?

```
WACC is used in two fundamental ways:

1. HURDLE RATE (Capital Budgeting)
   ├── Project earns MORE than WACC → Accept (creates value)
   └── Project earns LESS than WACC → Reject (destroys value)

2. DISCOUNT RATE (Valuation / DCF)
   ├── Future cash flows discounted at WACC
   ├── Higher WACC → lower present value → lower company valuation
   └── Lower WACC → higher present value → higher company valuation
```

**Hurdle rate example:** Solar-Go (WACC = 7.2%) is evaluating two projects:
- Solar farm A: expected return 9% → **Accept** (9% > 7.2%)
- Solar farm B: expected return 5% → **Reject** (5% < 7.2%, destroys value)

**Valuation link:** When analysts value a company using a [[Discounted Cash Flow|DCF]] model, they project all future free cash flows and discount them back to today using WACC as the discount rate. The higher the WACC, the riskier the company, and the less those future cash flows are worth today. This is how WACC directly impacts a company's estimated value — see [[Free Cash Flow Valuation]].

---

## Side-by-Side: High WACC vs. Low WACC Companies

| | **High WACC Company** | **Low WACC Company** |
|---|---|---|
| **Example** | Early-stage tech startup | Utility company (e.g. power grid) |
| **Why** | High beta, lots of uncertainty, equity-heavy | Stable cash flows, low beta, cheap debt |
| **Implication** | Needs high-return projects to justify capital | Can take on lower-return projects and still create value |
| **Valuation** | Future cash flows worth less today | Future cash flows worth more today |

---

## Common Pitfalls

- **Using book value weights instead of market value weights** — book values are historical and misleading; always use what the market says things are worth today
- **Using the coupon rate instead of YTM for cost of debt** — the coupon was set when the bond was issued; YTM reflects current market conditions
- **Ignoring the tax shield** — forgetting the $(1-t)$ adjustment overstates the cost of debt
- **Using a single WACC for all projects** — if a company is evaluating a project in a completely different industry, that project's risk profile is different and deserves its own discount rate

---

## Related Notes

- [[Capital Structure]]
- [[Cost of Equity]]
- [[Cost of Debt]]
- [[CAPM]]
- [[Beta]]
- [[Equity Risk Premium]]
- [[Risk-Free Rate]]
- [[Discounted Cash Flow]]
- [[Free Cash Flow Valuation]]
- [[DuPont Analysis & ROE]]
- [[Analysis of Dividends and Share Repurchases]]

---
