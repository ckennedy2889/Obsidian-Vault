---
name: equity-research-morning-note
description: "Use when CK asks to run `equity-research:morning-note` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:morning-note

## Trigger Aliases

- `equity-research:morning-note`
- `equity-research-morning-note`

## Workflow

Draft a morning meeting note covering overnight developments relevant to the coverage universe.

Provide the date or relevant tickers/sectors. If not provided, ask what to cover.

Structure:
1. **Market Overnight** — key index moves, macro data, central bank commentary, geopolitical developments
2. **Sector Highlights** — material news in covered sectors: earnings, guidance changes, management updates, M&A, regulatory
3. **Stock-Specific Events** — specific names with price reaction, brief analysis, and implication for thesis
4. **Today's Calendar** — upcoming earnings, data releases, investor events
5. **Analyst Take** — 2–3 sentences on the most actionable item of the morning

Style: concise, factual, written for pre-market read. Max 1 page. No speculation beyond clearly flagged analysis. All quotes attributed.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
