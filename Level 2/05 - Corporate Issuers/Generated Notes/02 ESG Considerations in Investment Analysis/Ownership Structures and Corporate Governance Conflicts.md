---
title: "Ownership Structures and Corporate Governance Conflicts"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, esg, corporate-governance]
aliases:
  - Concentrated ownership
  - Dispersed ownership
  - Principal-agent conflict
  - Principal-principal conflict
---

# Ownership Structures and Corporate Governance Conflicts

Think of [[corporate governance]] as the control system that answers one exam-critical question: **who can make the company do something, and whose wealth might be harmed when they do?** Ownership structure tells you where the power sits. Once you know where the power sits, the likely conflict becomes much easier to diagnose.

The CFA Level II trap is that ownership percentage and control are not always the same thing. A shareholder can own less than 50% of the cash-flow rights but still control the vote through [[dual-class shares]], pyramid structures, cross-holdings, or voting arrangements.

## Core Intuition

If ownership is dispersed, no shareholder has enough power or incentive to monitor management closely. Managers become strong, shareholders become weak, and the main concern is that managers use the firm for themselves.

If ownership is concentrated, a controlling owner can monitor management effectively. That reduces the manager problem, but it creates a different problem: the controlling owner may extract value from minority shareholders.

## Ownership Structures

| Structure | Who has control? | Main governance concern | Exam language |
|---|---:|---|---|
| Dispersed ownership, dispersed voting power | Managers | Managers may act against shareholder interests | [[Principal-agent conflict]] |
| Concentrated ownership, concentrated voting power | Controlling shareholders | Controlling shareholders may harm minority owners | [[Principal-principal conflict]] |
| Dispersed ownership, concentrated voting power | Controlling minority shareholders | Control exceeds economic ownership | Principal-principal conflict |
| Concentrated ownership, dispersed voting power | Large owners limited by voting caps | Control is intentionally restricted | Often used to limit foreign control |

### Dispersed ownership

Dispersed ownership means many shareholders own the company, but none controls it. This structure is common in markets such as the United States, the United Kingdom, and Australia.

The mechanism is simple:

1. Each shareholder owns a small stake.
2. Monitoring management is costly.
3. The benefit of monitoring is shared by all shareholders.
4. Each shareholder has an incentive to free ride.
5. Management faces weaker discipline.

That is why dispersed ownership creates the classic [[principal-agent conflict]]: shareholders are the principals, managers are the agents, and managers may pursue compensation, perks, empire building, or job security instead of maximizing shareholder value.

### Concentrated ownership

Concentrated ownership means an individual, family, government, company, bank, or investor group can exercise control.

This reduces the principal-agent conflict because the controlling shareholder has both the incentive and power to monitor management. But it creates a [[principal-principal conflict]]: the controlling shareholder is one principal, minority shareholders are other principals, and the controlling shareholder may use control rights to redirect value toward itself.

Examples include:

| Mechanism | How value can shift away from minority shareholders |
|---|---|
| Related-party transactions | The company buys from or sells to another entity controlled by the same family or group on unfavorable terms. |
| Dual-class voting | Insiders retain voting control while outside shareholders provide capital. |
| Pyramid ownership | Control is magnified through layers of holding companies. |
| Cross-holdings | Related companies own each other's shares, making outside discipline harder. |
| Board control | The controlling owner appoints directors who prioritize the controller's interests. |

## Control Can Exceed Ownership

This is one of the highest-yield mechanics in the reading.

Suppose a family owns 51% of Holding Company A, and Holding Company A owns 51% of Operating Company B.

The family controls B because it controls A, which controls B. But the family's indirect cash-flow ownership in B is:

$$
0.51 \times 0.51 = 26.01\%
$$

The family controls 100% of the voting path with only 26.01% of the economics. That wedge between control rights and cash-flow rights is dangerous because the controller can capture private benefits while bearing only part of the economic cost.

## Influential Shareholder Types

| Shareholder type | Governance benefit | Governance risk |
|---|---|---|
| Families | Long-term orientation; closer monitoring of management | Low transparency; nepotism; weak minority protection |
| State-owned enterprises | Government support; strategic stability | Political goals may override shareholder value |
| Banks | Monitoring expertise; lending relationship | Conflict if bank is both lender and shareholder |
| Institutional investors | Professional monitoring; pressure for transparency | May still be too diversified to monitor deeply |
| Foreign investors | Often demand stronger disclosure and investor protection | May be limited by local ownership rules |
| Private equity firms | Performance incentives; active governance | High leverage and exit focus can change risk profile |
| Managers and directors | Better alignment when insiders own shares | Entrenchment if ownership protects insiders from discipline |

## Board and Voting Mechanisms

Governance policies are supposed to make sure power is watched by someone who can use it responsibly.

| Mechanism | Why it matters |
|---|---|
| Independent directors | Better monitoring of management, especially under dispersed ownership |
| One-tier board | Internal and external directors sit on one board |
| Two-tier board | Supervisory board oversees the management board |
| Independent committees | Audit, compensation, nomination, risk, and compliance committees should not be dominated by conflicted insiders |
| Special voting arrangements | Minority shareholders may receive protection in board elections or major transactions |
| Comply-or-explain codes | Firms either follow governance best practices or explain why they do not |
| Stewardship codes | Encourage institutional investors to exercise ownership rights actively |

### CEO duality

[[CEO duality]] exists when the CEO is also chair of the board. The concern is not that CEO duality is automatically fatal; the concern is that the CEO is partly responsible for monitoring the CEO. That weakens board oversight and can raise perceived governance risk.

## Valuation Implications

Governance affects valuation because it affects expected cash flows, risk, and the distribution of value among security holders.

### Equity valuation

For equity analysts, weak governance can be reflected by:

- Lower expected revenue growth if governance problems damage competitiveness or reputation.
- Lower margins if related-party transactions, poor incentives, or weak oversight increase costs.
- Higher capital expenditures if managers overinvest in negative-NPV projects.
- Higher discount rates if investors demand a governance risk premium.
- A voting-rights discount for inferior-vote shares in a dual-class structure.

In discounted cash flow language:

$$
V_0 = \sum_{t=1}^{n} \frac{FCFE_t}{(1 + r_e)^t}
$$

Weak governance can reduce \(FCFE_t\), increase \(r_e\), or both. The exam may describe either adjustment, so do not assume all ESG or governance effects must go through the discount rate.

### Fixed-income valuation

For fixed-income analysts, governance is mostly a downside-risk issue. Poor governance can increase:

- Probability of default.
- Expected loss given default.
- Credit spreads.
- Covenant risk.
- Event risk from leverage, acquisitions, or restructurings.

If a governance weakness increases credit risk, the analyst may widen the credit spread used to value the debt.

## Worked Example: Principal-Agent vs Principal-Principal

A public company has thousands of small shareholders. The CEO proposes an acquisition that will double the firm's assets but has a negative expected NPV. No shareholder owns more than 1%.

This is mainly a **principal-agent conflict**. The CEO may benefit from running a larger company, even if shareholders lose value.

Now change the facts. A family owns 25% of the economic rights but controls 60% of the votes through dual-class shares. The company signs a long-term supply contract with another family-owned business at above-market prices.

This is mainly a **principal-principal conflict**. The family controller can shift value from the public company to another entity it controls, while minority shareholders bear part of the cost.

## Exam Traps

- **Do not equate control with more than 50% ownership.** Control can come from voting rights, pyramids, cross-holdings, or dispersed outside ownership.
- **Dispersed ownership points to principal-agent conflict.** Managers are the likely problem.
- **Concentrated voting power points to principal-principal conflict.** Controlling shareholders are the likely problem.
- **Family ownership is not purely good or bad.** It can reduce manager agency costs while increasing minority-shareholder risk.
- **SOEs may not maximize shareholder value.** Public policy objectives can dominate profitability.
- **Banks can have conflicts.** A bank that is both lender and shareholder may push financing that benefits the bank.
- **ESG valuation adjustments can hit either cash flows or discount rates.** Choose the adjustment that matches the stated risk.

## Memory Hook

**Weak owners, strong managers: agent problem. Strong owners, weak minorities: principal-principal problem.**

When you see an ownership vignette, first ask: **who controls the vote?** Then ask: **who is not protected from that control?**
