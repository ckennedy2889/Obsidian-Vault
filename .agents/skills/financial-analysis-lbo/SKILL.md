---
name: financial-analysis-lbo
description: "Use when CK asks to run `financial-analysis:lbo` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:lbo

## Trigger Aliases

- `financial-analysis:lbo`
- `financial-analysis-lbo`

## Workflow

Build an LBO financial model for a specified acquisition target.

To get started, provide a company name or deal details. If none given, ask for target company details and deal parameters (entry EBITDA/multiple, leverage structure, investment horizon, exit assumptions).

Workflow:
1. Gather entry assumptions: purchase price, entry multiple, EBITDA, sources & uses
2. Build debt schedule: tranches, interest rates, amortization, cash sweep
3. Project income statement and free cash flow over hold period (typically 5 years)
4. Calculate exit: exit multiple range, exit EBITDA, equity proceeds
5. Compute returns: IRR and MOIC across Bear/Base/Bull scenarios
6. Build sensitivity tables: entry multiple × exit multiple, leverage × growth

Deliver an Excel workbook (.xlsx) with sources & uses, debt schedule, operating projections, returns summary, and sensitivity tables.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
