---
name: investment-banking-cim
description: "Use when CK asks to run `investment-banking:cim` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:cim

## Trigger Aliases

- `investment-banking:cim`
- `investment-banking-cim`

## Workflow

Draft a Confidential Information Memorandum (CIM) for a sell-side M&A process.

To proceed, I need: (1) company name, (2) available source materials (financial statements, business plans, market research, management presentations, etc.). Ask for these if not provided.

CIM structure:
1. **Executive Summary** — investment highlights, key financial metrics, transaction rationale
2. **Company Overview** — history, ownership, corporate structure, facilities, headcount
3. **Business Description** — products/services, go-to-market, customer overview, competitive positioning
4. **Market Analysis** — TAM/SAM, growth drivers, competitive landscape, industry tailwinds
5. **Financial Performance** — 3+ years historical P&L, balance sheet, cash flow; key metrics and trends; normalized EBITDA bridge
6. **Management & Operations** — org chart, key personnel bios, operational infrastructure
7. **Growth Opportunities** — organic initiatives, M&A optionality, new markets
8. **Risk Factors** — key risks and mitigants
9. **Transaction Overview** — process timeline, data room overview, contact information

All figures must be sourced from provided materials. Flag any gaps requiring management input. Output as a structured document draft.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
