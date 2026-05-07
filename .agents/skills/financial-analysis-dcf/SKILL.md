---
name: financial-analysis-dcf
description: "Use when CK asks to run `financial-analysis:dcf` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:dcf

## Trigger Aliases

- `financial-analysis:dcf`
- `financial-analysis-dcf`

## Workflow

Build an institutional-quality DCF model that uses comparable company analysis to inform valuation ranges.

To get started, provide a company name or ticker. If none given, ask for one.

Workflow:
1. Run comparable company analysis — identify 4–6 peers, pull operating metrics and valuation multiples (EV/Revenue, EV/EBITDA, P/E), compute statistical summary
2. Build DCF model — gather historical financials, build Bear/Base/Bull revenue projections, model operating expenses and FCF, calculate WACC using CAPM, discount cash flows, calculate terminal value, bridge to equity value and implied share price
3. Use comps to inform DCF: peer median EV/EBITDA → terminal exit multiple; peer growth rates → revenue benchmarks; peer margins → target margin assumptions
4. Cross-check: implied EV/EBITDA vs peer median, terminal value as % of EV (target 50–70%), implied growth vs peer rates
5. Deliver: comps .xlsx, DCF .xlsx with Bear/Base/Bull + sensitivity tables (WACC vs terminal growth), valuation summary with implied upside/downside

Output summary format:
- Peer group and median multiples
- DCF implied share price vs current price
- Valuation cross-check (DCF implied EV/EBITDA vs peer median)
- Key assumptions: revenue CAGR, terminal EBITDA margin, WACC, terminal growth rate


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
