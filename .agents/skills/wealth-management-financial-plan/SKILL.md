---
name: wealth-management-financial-plan
description: "Use when CK asks to run `wealth-management:financial-plan` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:financial-plan

## Trigger Aliases

- `wealth-management:financial-plan`
- `wealth-management-financial-plan`

## Workflow

Build or update a comprehensive financial plan for a client.

Provide a client name. Ask if not provided, and gather key inputs: age, income, assets, liabilities, retirement goal, family situation, risk tolerance, estate planning status.

Financial plan components:
1. **Current Financial Position** — net worth statement, income vs. expenses, savings rate, debt analysis
2. **Goals & Priorities** — retirement (target date, income need), education funding, major purchases, legacy/charitable goals
3. **Retirement Projections** — Monte Carlo or scenario analysis; probability of success at current savings rate; required savings rate to meet goal
4. **Education Funding** — 529 plan contribution needed to fund target college costs; impact on retirement savings
5. **Insurance Review** — life insurance (income replacement analysis), disability, long-term care needs assessment
6. **Estate Planning** — will/trust status, beneficiary designations, power of attorney, estate tax exposure
7. **Cash Flow Projections** — income and expense projection to retirement and through retirement
8. **Recommendations** — prioritized action list with specific, actionable steps

Deliver a structured financial plan document (10–20 pages) with supporting projections. All assumptions stated explicitly. Suitable for client presentation with advisor guidance.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
