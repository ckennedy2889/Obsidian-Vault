---
name: equity-research-catalysts
description: "Use when CK asks to run `equity-research:catalysts` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:catalysts

## Trigger Aliases

- `equity-research:catalysts`
- `equity-research-catalysts`

## Workflow

Build or review a catalyst calendar across the coverage universe.

If a timeframe is provided (e.g., "next 2 weeks"), use it. Otherwise default to the next 14 days.

Catalyst types to track:
- **Earnings**: reporting dates, expected key metrics, consensus estimates
- **Guidance events**: investor days, capital markets days, management conferences
- **Product/regulatory**: FDA decisions, product launches, approval timelines
- **Macro data**: CPI, Fed meetings, jobs reports relevant to covered sectors
- **M&A**: rumored deals, strategic review announcements, deal close dates
- **Analyst events**: estimate revision deadlines, rating changes expected

Format:
| Date | Company/Event | Type | Expected Impact | Analyst Note |
|------|--------------|------|-----------------|--------------|

Flag highest-impact events. Include pre-event positioning suggestions where thesis-relevant.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
