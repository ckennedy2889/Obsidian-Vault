---
name: financial-analysis-ppt-template
description: "Use when CK asks to run `financial-analysis:ppt-template` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# financial-analysis:ppt-template

## Trigger Aliases

- `financial-analysis:ppt-template`
- `financial-analysis-ppt-template`

## Workflow

Develop a reusable PowerPoint template skill from an existing .pptx or .potx file.

If a template file path is provided, use it. Otherwise, ask the user to supply a PowerPoint template containing their desired slide layouts and branding.

Workflow:
1. Examine template structure: master slides, layouts, color palette, fonts, logo placement
2. Gather context: organization name, intended use cases (pitch decks, board materials, client presentations)
3. Document the template: layout names, placeholder positions, brand colors (hex), font stack
4. Generate a sample presentation using the template to verify all layouts work correctly
5. Package and deliver: a documented template skill ready for use in future deck creation

Output: template documentation (layout inventory, brand guide), sample .pptx, and usage instructions.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
