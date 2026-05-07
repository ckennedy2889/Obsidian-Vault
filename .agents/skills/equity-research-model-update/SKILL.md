---
name: equity-research-model-update
description: "Use when CK asks to run `equity-research:model-update` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:model-update

## Trigger Aliases

- `equity-research:model-update`
- `equity-research-model-update`

## Workflow

Refresh a financial model by incorporating new earnings, guidance, or revised assumptions.

Provide a company ticker and specify what changed (e.g., "Q1 actuals just reported", "guidance raised", "margin assumptions revised"). Ask if not provided.

Update workflow:
1. **Plug in actuals**: replace estimates with reported figures for the completed period
2. **Roll forward**: update current quarter/year estimates based on new data
3. **Revise assumptions**: update revenue growth, margins, capex, or other drivers based on new guidance or analyst judgment
4. **Consensus comparison**: flag where new model is above/below Street consensus
5. **Valuation refresh**: recalculate price target with updated estimates
6. **Change summary**: table showing old vs. new estimates for key metrics (Revenue, EBITDA, EPS) for current year and next year

Deliver: updated model (.xlsx) with change log tab and a brief note (1–2 pages) summarizing what changed and why, estimate revisions, and updated price target.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
