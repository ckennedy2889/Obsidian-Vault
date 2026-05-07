---
name: investment-banking-deal-tracker
description: "Use when CK asks to run `investment-banking:deal-tracker` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:deal-tracker

## Trigger Aliases

- `investment-banking:deal-tracker`
- `investment-banking-deal-tracker`

## Workflow

Track and review live deal pipeline — deal status, milestones, and action items across active transactions.

If deal information or a pipeline file is provided, use it. Otherwise, ask what deals to track and what information is available.

Workflow:
1. Capture active deals: company name, process type (sell-side, buy-side, financing), current stage, key dates
2. Track milestones by stage: NDA signed → CIM distributed → IOIs received → management presentations → LOI/exclusivity → due diligence → definitive agreement → close
3. Log open action items: owner, due date, status
4. Flag at-risk items: overdue milestones, missing deliverables, stalled parties

Deliver a pipeline summary table with deal name, stage, next milestone, date, and open items. Suitable for weekly deal team review or MD update.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
