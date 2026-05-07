---
name: equity-research-earnings-preview
description: "Use when CK asks to run `equity-research:earnings-preview` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:earnings-preview

## Trigger Aliases

- `equity-research:earnings-preview`
- `equity-research-earnings-preview`

## Workflow

Build a pre-earnings analysis ahead of a company's results.

Provide a company ticker. Ask if not provided.

Preview structure:
1. **Consensus Estimates** — Wall Street expectations for Revenue, Gross Margin, EBITDA, EPS; compare to prior quarter and year-ago
2. **Key Metrics to Watch** — 3–5 company-specific KPIs beyond headline numbers (e.g., ARR, units, same-store sales, bookings)
3. **Implied Guidance** — what prior guidance implies for the quarter; any preannouncement or channel checks
4. **Scenario Analysis**:
   - **Bull case**: beat on revenue and EPS, raised guidance → estimated stock reaction
   - **Base case**: in-line results, guidance maintained → estimated stock reaction
   - **Bear case**: miss or lowered guidance → estimated stock reaction
5. **Positioning & Sentiment** — short interest, options implied move, buy-side positioning if available
6. **Valuation Setup** — where stock trades vs. history heading into print

Deliver a 2–4 page preview note suitable for distribution ahead of the earnings call.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
