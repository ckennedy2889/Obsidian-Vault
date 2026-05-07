---
name: private-equity-returns
description: "Use when CK asks to run `private-equity:returns` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:returns

## Trigger Aliases

- `private-equity:returns`
- `private-equity-returns`

## Workflow

Build IRR/MOIC sensitivity tables for a PE investment.

Provide a company or deal name. Ask for entry EBITDA, entry multiple, leverage assumptions, and financing structure if not provided.

Model components:
1. **Entry assumptions** — EBITDA, entry multiple, purchase price, equity check, debt (tranches, rates, amortization)
2. **Operating projections** — revenue and EBITDA growth by scenario (Bear/Base/Bull) over 5-year hold
3. **Debt paydown** — mandatory amortization + cash sweep; revolver usage
4. **Exit assumptions** — exit year (3, 4, 5), exit multiple range
5. **Returns calculation** — equity proceeds, IRR, MOIC, cash-on-cash for each scenario

Sensitivity tables (2×2 matrices):
- Entry multiple × Exit multiple (at base growth)
- Entry multiple × EBITDA growth (at base exit multiple)
- Leverage (Debt/EBITDA) × Exit multiple
- Hold period (3/4/5 yr) × Exit multiple

Deliver an Excel workbook (.xlsx) with: assumptions tab, operating model, debt schedule, returns summary, and all four sensitivity tables.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
