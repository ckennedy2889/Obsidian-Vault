---
name: financial-analysis-competitive-analysis
description: "Use when CK asks to run `financial-analysis:competitive-analysis` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:competitive-analysis

## Trigger Aliases

- `financial-analysis:competitive-analysis`
- `financial-analysis-competitive-analysis`

## Workflow

Create a competitive landscape analysis for a specified company or industry.

If a company or industry name is provided as an argument, use it. Otherwise, ask the user to specify.

Workflow:
1. Define the competitive arena: market scope, geography, customer segments
2. Map key players: market share, positioning, go-to-market approach
3. Analyze competitive dynamics: Porter's Five Forces, barriers to entry, switching costs
4. Benchmark the subject company: strengths, weaknesses, differentiation, pricing
5. Identify trends: consolidation activity, new entrants, technology disruption
6. Summarize investment implications: who wins, who's vulnerable, key watchpoints

Deliver a structured written analysis with an executive summary, competitive map, positioning grid, and key takeaways.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
