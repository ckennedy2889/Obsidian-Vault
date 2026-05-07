---
name: equity-research-initiate
description: "Use when CK asks to run `equity-research:initiate` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:initiate

## Trigger Aliases

- `equity-research:initiate`
- `equity-research-initiate`

## Workflow

Produce an institutional-quality initiating coverage report.

Provide a company ticker. Ask if not provided.

Five-task workflow:
1. **Industry & Market Analysis** — TAM, growth drivers, competitive dynamics, regulatory environment, key risks
2. **Company Deep Dive** — business model, revenue streams, customer base, competitive moat, management quality, capital allocation history
3. **Financial Model** — 5-year projections (revenue, margins, FCF), DCF valuation, trading comps, price target derivation
4. **Investment Thesis** — 3 key reasons to own the stock, key catalysts, bear case and why it's wrong (or acknowledged)
5. **Report Assembly** — formatted initiation report with executive summary, full analysis, and financial model appendix

Deliver a comprehensive research report (15–25 pages) with:
- Rating (Buy/Hold/Sell) and 12-month price target
- Executive summary and investment thesis
- Industry, company, and financial analysis
- Valuation (DCF + comps football field)
- Risks section
- All figures sourced from CapIQ, FactSet, SEC filings, or company disclosure


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
