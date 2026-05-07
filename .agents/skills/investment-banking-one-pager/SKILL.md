---
name: investment-banking-one-pager
description: "Use when CK asks to run `investment-banking:one-pager` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:one-pager

## Trigger Aliases

- `investment-banking:one-pager`
- `investment-banking-one-pager`

## Workflow

Create a professional single-page company strip profile for pitch books and deal materials.

If a company name or ticker is provided, use it. Otherwise, ask for the company details. Ask if a branded PowerPoint template is available.

Layout (4-quadrant, 4:3 slide at 10" × 7.5"):
- **Top-left — Company Overview**: name, ticker, HQ, founding date, employee count, CEO, business description (2–3 sentences)
- **Top-right — Business & Positioning**: core products/services, end markets, competitive advantages, key customers
- **Bottom-left — Key Financials**: table with Revenue, EBITDA, EBITDA margin, EV/EBITDA, EV/Revenue for LTM and 1–2 forecast years
- **Bottom-right — Stock Performance**: 1-year price chart with volume, or recent material news if private; shareholder composition if public

Quality standards: all data fields populated (no placeholders), sources cited, investment banking formatting, brand colors applied if template provided. Deliver as .pptx with image preview.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
