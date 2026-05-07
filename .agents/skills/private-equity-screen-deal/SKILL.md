---
name: private-equity-screen-deal
description: "Use when CK asks to run `private-equity:screen-deal` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:screen-deal

## Trigger Aliases

- `private-equity:screen-deal`
- `private-equity-screen-deal`

## Workflow

Screen an inbound investment opportunity (CIM or teaser) against fund criteria.

Provide a file path to CIM/teaser materials, or describe the deal. Ask if neither is provided.

Screening framework:
1. **Fund Fit** — sector, size, geography, business model vs. fund mandate
2. **Business Quality** — recurring revenue, customer concentration, competitive moat, management quality indicators
3. **Financial Profile** — revenue scale, EBITDA margin, growth rate, FCF conversion, leverage capacity
4. **Valuation** — implied entry multiple from seller guidance or comp precedents; realistic?
5. **Return Potential** — quick math on base case IRR/MOIC at indicated entry; does it clear the hurdle?
6. **Diligence Risk** — key unknowns; what could kill the deal (regulatory, customer, tech, people)?

Output: concise pass/pursue recommendation (1 page max) with: deal summary (3 bullets), fund fit assessment, financial snapshot, preliminary return math, key risks, and recommended next step (pass / first call / site visit / IOI).


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
