---
name: private-equity-ai-readiness
description: "Use when CK asks to run `private-equity:ai-readiness` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:ai-readiness

## Trigger Aliases

- `private-equity:ai-readiness`
- `private-equity-ai-readiness`

## Workflow

Evaluate portfolio companies for AI opportunity and readiness.

Provide: a folder path with portfolio company materials, a list of company names, or quarterly reporting packages. Ask if not provided.

Assessment framework (per company):

**Data Readiness**
- Data quality and availability: structured vs. unstructured, completeness, accessibility
- Current data infrastructure: CRM, ERP, data warehouse maturity
- Data governance and ownership

**AI Opportunity Identification**
- Process automation candidates (repetitive, rules-based tasks)
- Revenue enhancement opportunities (personalization, pricing, upsell)
- Cost reduction opportunities (headcount leverage, efficiency)
- Competitive moat opportunities (AI as product differentiator)

**Implementation Readiness**
- Technical talent: data science/ML capability in-house or accessible
- Vendor landscape: which AI tools are relevant to this business
- Change management: leadership buy-in, culture

**EBITDA Impact Sizing**
- Quick wins (0–6 months): estimate impact in $ EBITDA
- Medium-term (6–18 months): estimate impact
- Strategic (18+ months): optionality

**Go/No-Go Assessment**
- Score each company on: data readiness, opportunity size, implementation feasibility
- Rank portfolio by AI ROI potential
- Flag repeatable solutions applicable across multiple portfolio companies

Deliver: per-company scorecard, portfolio-level ranking by EBITDA impact potential, and recommended implementation sequence.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
