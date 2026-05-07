---
name: financial-analysis-debug-model
description: "Use when CK asks to run `financial-analysis:debug-model` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:debug-model

## Trigger Aliases

- `financial-analysis:debug-model`
- `financial-analysis-debug-model`

## Workflow

Audit and debug an Excel financial model (.xlsx file).

If a file path is provided, use it. Otherwise, ask the user to identify which model to review.

Audit checklist:
- Broken or invalid formulas
- Balance sheet imbalances (assets ≠ liabilities + equity)
- Hardcoded value overrides in calculation cells
- Circular references
- Cash flow statement tie-outs to balance sheet
- Account roll-forwards (beginning + activity = ending)
- Formula consistency across rows/columns
- Negative debt or impossible values
- Logic errors in switching between scenarios

Return: the complete file path, a detailed audit report listing every issue found (type, cell location, description), and recommended fixes. Prioritize by severity: errors that break the model first, then integrity issues, then best-practice violations.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
