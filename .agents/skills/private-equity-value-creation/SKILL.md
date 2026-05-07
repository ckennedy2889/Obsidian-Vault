---
name: private-equity-value-creation
description: "Use when CK asks to run `private-equity:value-creation` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:value-creation

## Trigger Aliases

- `private-equity:value-creation`
- `private-equity-value-creation`

## Workflow

Build a post-acquisition value creation plan for a portfolio company.

Provide a company name. Ask for: entry EBITDA, purchase price, key strategic context, and any known operational issues.

Value creation plan components:

**EBITDA Bridge**
- Baseline EBITDA (entry)
- Revenue initiatives: organic growth, pricing, new products, new markets → incremental EBITDA contribution
- Margin initiatives: procurement savings, operational efficiency, overhead reduction → contribution
- Target EBITDA at exit

**100-Day Plan**
Prioritized initiatives for the first 100 days post-close:
1. Management alignment and incentive plan finalization
2. Quick-win cost actions (no disruption risk)
3. Commercial priorities (key customer retention, pipeline acceleration)
4. Information and reporting infrastructure
5. Strategic review kickoff

**KPI Dashboard**
Define 5–8 leading indicators to track monthly:
- Revenue/booking metrics
- Margin and cost metrics
- Operational throughput metrics
- People/talent metrics

**Exit Preparation**
- Target exit year and multiple
- Value creation narrative for future buyer
- Risks to address before exit (customer concentration, key-person, tech debt)

Deliver a structured value creation plan document suitable for board review.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
