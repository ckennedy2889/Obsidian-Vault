---
name: financial-analysis-comps
description: "Use when CK asks to run `financial-analysis:comps` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:comps

## Trigger Aliases

- `financial-analysis:comps`
- `financial-analysis-comps`

## Workflow

Build an institutional-grade comparable company analysis with trading multiples and valuation benchmarking.

To get started, provide a company name or ticker. If none given, ask for one.

Workflow:
1. Understand the analysis goal — valuation, efficiency comparison, or investor presentation
2. Identify 4–6 peer companies matching business model, scale, industry, and geography
3. Gather key metrics: revenue, growth, margins, EBITDA, and valuation multiples (EV/Revenue, EV/EBITDA, P/E)
4. Build a statistical summary (median, 25th/75th percentiles)
5. Deliver an Excel workbook (.xlsx) formatted for institutional use, plus a written summary covering peer selection rationale and key insights on relative valuations

Output should include: operating statistics table, valuation multiples table, statistical summary, and methodology notes.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
