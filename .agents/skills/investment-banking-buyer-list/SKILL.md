---
name: investment-banking-buyer-list
description: "Use when CK asks to run `investment-banking:buyer-list` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:buyer-list

## Trigger Aliases

- `investment-banking:buyer-list`
- `investment-banking-buyer-list`

## Workflow

Build a comprehensive buyer universe for an M&A sell-side process.

If a company or sector is provided, use it. Otherwise, ask for the target company details.

Workflow:
1. Characterize the target: sector, size, geography, business model, key assets, customer base
2. Identify strategic buyers: direct competitors, adjacent-sector acquirers, international buyers seeking market entry, customers or suppliers seeking vertical integration
3. Identify financial buyers: PE firms with relevant portfolio companies or sector expertise, appropriate fund size for the deal
4. For each buyer, assess: strategic rationale, estimated acquisition capacity, prior M&A activity in the sector, likely valuation lens
5. Prioritize: tier into A-list (most likely, highest value), B-list (possible), and C-list (long shots)

Deliver a structured buyer universe table with buyer name, type (strategic/financial), rationale, priority tier, and recent relevant activity. Flag any potential conflicts or sensitivity considerations.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
