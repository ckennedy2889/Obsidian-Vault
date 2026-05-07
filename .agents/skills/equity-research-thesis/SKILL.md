---
name: equity-research-thesis
description: "Use when CK asks to run `equity-research:thesis` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# equity-research:thesis

## Trigger Aliases

- `equity-research:thesis`
- `equity-research-thesis`

## Workflow

Create or update an investment thesis for a specific position.

Provide a company ticker. Ask if not provided. Also ask if this is a new thesis or an update to an existing one.

Thesis components:
1. **Core Thesis** — 3–5 sentences: why the stock is mispriced and what the market is missing
2. **Key Pillars** — 3 supporting arguments with evidence (competitive moat, earnings inflection, valuation discount, etc.)
3. **Key Catalysts** — upcoming events that could close the gap (earnings, product launch, management change, regulatory, M&A)
4. **Variant View** — what consensus gets wrong and why
5. **Bear Case** — the strongest argument against the position; why it doesn't change the thesis (or if it does, acknowledge)
6. **Valuation** — implied upside to price target; framework (DCF, EV/EBITDA, P/E, sum-of-parts)
7. **Monitoring Framework** — 3–5 KPIs to watch each quarter; exit criteria if thesis breaks

For updates: note what changed since last review, how it affects each pillar, and whether conviction has increased or decreased.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
