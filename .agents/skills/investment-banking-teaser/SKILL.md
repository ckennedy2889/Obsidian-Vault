---
name: investment-banking-teaser
description: "Use when CK asks to run `investment-banking:teaser` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:teaser

## Trigger Aliases

- `investment-banking:teaser`
- `investment-banking-teaser`

## Workflow

Create an anonymized one-page company teaser for initial buyer outreach in an M&A process.

If a company name is provided, use it. Otherwise, ask for the company. Teasers are intentionally anonymous — do not reveal the company identity.

Teaser structure (1 page):
1. **Situation Overview** — "A leading provider of [category] serving [end markets]" — describe without naming
2. **Investment Highlights** — 4–6 bullet points on key strengths (market position, growth, margins, customer quality, recurring revenue, etc.)
3. **Financial Snapshot** — Revenue, EBITDA, growth rate for the most recent period (rounded or ranged to preserve anonymity)
4. **Transaction Rationale** — Why the company is compelling for acquirers
5. **Process Details** — Contact banker name/firm placeholder, indication of interest deadline, confidentiality reminder

Tone: concise, factual, compelling. No company name, logo, or identifiable details. Deliver as a clean document or single slide.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
