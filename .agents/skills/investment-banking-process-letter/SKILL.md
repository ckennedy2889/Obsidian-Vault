---
name: investment-banking-process-letter
description: "Use when CK asks to run `investment-banking:process-letter` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:process-letter

## Trigger Aliases

- `investment-banking:process-letter`
- `investment-banking-process-letter`

## Workflow

Draft process correspondence for an M&A transaction.

If a letter type is specified, use it. Otherwise, ask which stage of the process to address.

Supported letter types:
- **IOI (Indication of Interest)**: guidance on format, valuation range, key assumptions, exclusivity ask, requested next steps
- **Final Bid Instructions**: process timeline, required bid components (price, structure, financing, management rollover), data room access, Q&A procedures, submission deadline and format
- **Management Presentation Invitation**: scheduling details, presentation agenda outline, NDA reminder, logistics, contact information

Each letter should include: deal codename (if applicable), bank contact information placeholder, appropriate confidentiality language, and professional tone consistent with institutional sell-side practice.

Deliver as a formatted document draft ready for banker review and customization.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
