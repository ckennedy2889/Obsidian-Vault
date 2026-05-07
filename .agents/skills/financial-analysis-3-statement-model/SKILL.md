---
name: financial-analysis-3-statement-model
description: "Use when CK asks to run `financial-analysis:3-statement-model` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:3-statement-model

## Trigger Aliases

- `financial-analysis:3-statement-model`
- `financial-analysis-3-statement-model`

## Workflow

Populate a 3-statement financial model (Income Statement, Balance Sheet, Cash Flow Statement).

If a file path to an existing template is provided, use it. Otherwise, ask the user to supply their model template or confirm building from scratch.

Workflow:
1. Income Statement: revenue build, gross margin, operating expenses, EBITDA, D&A, EBIT, interest, taxes, net income
2. Balance Sheet: current assets, PP&E, intangibles, current liabilities, debt, equity — must balance each period
3. Cash Flow Statement: operating (net income + working capital changes + D&A), investing (capex, acquisitions), financing (debt issuance/repayment, equity)
4. Verify: BS balances, CFS ties to cash on BS, net income flows correctly

Return the completed model in full, preserving all original file formatting and contents. Every formula cell should contain a formula — no hardcoded values in calculation cells.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
