---
name: equity-research-screen
description: "Use when CK asks to run `equity-research:screen` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:screen

## Trigger Aliases

- `equity-research:screen`
- `equity-research-screen`

## Workflow

Run a stock screen or generate investment ideas based on specified criteria.

If screening criteria are provided (e.g., "undervalued midcap tech", "high FCF yield industrials"), use them directly. Otherwise, ask:
- Long or short bias?
- Sector/industry focus?
- Investment style (value, growth, GARP, momentum)?
- Size preference (small/mid/large cap)?
- Geographic focus?
- Any thematic angle?

Screening approach:
1. **Quantitative screen**: apply financial filters (valuation multiples, growth rates, margins, balance sheet quality, momentum) to identify a candidate universe
2. **Thematic sweep**: identify companies exposed to a specific theme (AI infrastructure, GLP-1 supply chain, reshoring, etc.)
3. **Quality filter**: remove low-quality names (persistent FCF negative, heavy dilution, governance concerns)
4. **Output list**: 10–20 names with ticker, market cap, key metrics (P/E, EV/EBITDA, FCF yield, growth), and 1-sentence thesis hook per name

Deliver ranked list with rationale for inclusion. Flag highest-conviction names.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
