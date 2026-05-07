---
name: equity-research-earnings
description: "Use when CK asks to run `equity-research:earnings` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:earnings

## Trigger Aliases

- `equity-research:earnings`
- `equity-research-earnings`

## Workflow

Create a professional equity research earnings update report.

Provide a company name/ticker and the reporting quarter (e.g., "AAPL Q1 2025"). Ask if not provided.

Workflow:
1. Verify earnings data is current (within 3 months) — search for the latest results
2. Collect: SEC filings (10-Q/8-K), earnings call transcript, consensus estimates from FactSet/Bloomberg
3. Beat/miss analysis: actual vs. consensus for Revenue, Gross Margin, EBITDA, EPS; % variance for each
4. Key metrics: segment breakdown, guidance vs. prior guidance, management tone assessment
5. Generate 8–12 analytical charts: revenue trend, margin trend, segment mix, EV/EBITDA history, estimate revision history
6. Update thesis: did results strengthen or weaken the investment case?
7. Revise valuation: new price target if warranted, updated model assumptions

Deliver an 8–12 page DOCX report with:
- Summary (rating, price target, key takeaway)
- Results detail (beat/miss table, metric-by-metric analysis)
- Guidance and estimate changes
- Thesis assessment
- Valuation
- Sources with clickable hyperlinks

Target 3,000–5,000 words. All figures require source attribution.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
