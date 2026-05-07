---
name: private-equity-ic-memo
description: "Use when CK asks to run `private-equity:ic-memo` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:ic-memo

## Trigger Aliases

- `private-equity:ic-memo`
- `private-equity-ic-memo`

## Workflow

Draft a structured Investment Committee (IC) memo for a PE deal.

Provide a company name and available materials (financial statements, market research, valuation models, term sheets, due diligence reports). Ask if not provided.

IC memo structure:
1. **Executive Summary** — deal overview, entry valuation, returns summary (base case IRR/MOIC), recommendation
2. **Company Overview** — business description, products/services, end markets, customer base, competitive positioning
3. **Investment Thesis** — 3 key reasons to invest; what the fund brings as an owner
4. **Market Analysis** — TAM, growth, competitive dynamics, why now
5. **Financial Analysis** — historical financials (3+ years), LTM metrics, key KPIs, unit economics, working capital profile
6. **Valuation & Returns** — entry multiple and price, debt structure (sources & uses), IRR/MOIC under Bear/Base/Bull scenarios, sensitivity tables
7. **Due Diligence Summary** — key findings across commercial, financial, legal, and operational diligence; open items
8. **Risks & Mitigants** — top 5 risks with mitigant for each
9. **Management & Team** — key executives, track record, rollover/retention plan
10. **Value Creation Plan** — 100-day priorities, EBITDA improvement initiatives, exit strategy

All figures must be sourced from provided materials. Flag open items requiring resolution before close.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
