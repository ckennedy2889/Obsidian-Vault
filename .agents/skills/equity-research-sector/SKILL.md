---
name: equity-research-sector
description: "Use when CK asks to run `equity-research:sector` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:sector

## Trigger Aliases

- `equity-research:sector`
- `equity-research-sector`

## Workflow

Generate a comprehensive sector or industry landscape report.

Provide a sector or industry name. Ask if not provided.

Report structure:
1. **Market Sizing** — TAM, SAM, current market size, historical growth rate, 5-year CAGR forecast, key sizing assumptions
2. **Industry Structure** — value chain, key segments, business model archetypes, typical margin profiles
3. **Competitive Dynamics** — major players by segment, market share, Porter's Five Forces assessment, barriers to entry, switching costs
4. **Key Drivers & Risks** — demand drivers (macro, secular, cyclical), supply dynamics, regulatory environment, key risk factors
5. **Recent Activity** — notable M&A, new entrants, technology disruption, capacity additions
6. **Investment Implications** — which parts of the value chain to own, preferred names, what multiples are appropriate and why

Deliver a structured 5–10 page sector primer suitable for investor onboarding or internal research. Include a peer trading comps table (8–15 names) with Revenue, EBITDA, growth, margins, and key multiples.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
