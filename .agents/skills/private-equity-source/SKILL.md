---
name: private-equity-source
description: "Use when CK asks to run `private-equity:source` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:source

## Trigger Aliases

- `private-equity:source`
- `private-equity-source`

## Workflow

Source target companies and generate founder outreach for a deal sourcing campaign.

Provide search criteria (e.g., "industrial services in Texas $10–50M EBITDA") or ask the user to specify: sector, geography, company size (revenue or EBITDA range), business model preference.

Workflow:
1. **Define universe** — apply criteria to identify target profile; estimate market size of potential targets
2. **Generate target list** — 20–50 companies matching criteria; include: company name, HQ, estimated revenue/EBITDA, description, why it fits the thesis
3. **CRM check** — flag any companies with existing relationship history or prior outreach
4. **Prioritize** — tier targets: warm (existing relationship or referral), cool (no prior contact), cold
5. **Draft outreach** — personalized email for each tier:
   - Subject line
   - Opening with specific hook (why this company, why now)
   - Fund overview (2 sentences)
   - Call to action
   - Appropriate confidentiality/no-pressure framing

Deliver: target list table + email templates per tier. Flag targets most likely to be receptive based on ownership profile (founder-owned, PE-backed approaching exit, etc.).


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
