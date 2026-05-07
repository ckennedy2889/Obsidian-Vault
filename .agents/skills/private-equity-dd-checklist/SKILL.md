---
name: private-equity-dd-checklist
description: "Use when CK asks to run `private-equity:dd-checklist` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:dd-checklist

## Trigger Aliases

- `private-equity:dd-checklist`
- `private-equity-dd-checklist`

## Workflow

Generate a comprehensive, sector-tailored due diligence checklist with status tracking.

Provide a company name and sector. Ask if not provided.

Checklist structure with status tracking (Not Started / In Progress / Complete / N/A):

**Commercial Diligence**
- Market size and growth validation
- Customer reference calls (target: 10–15)
- Channel partner interviews
- Competitive positioning assessment
- Win/loss analysis
- Pricing power and contract analysis

**Financial Diligence**
- Quality of earnings (QoE) review
- Revenue recognition analysis
- Working capital normalization
- Capex history and maintenance vs. growth split
- Customer-level profitability
- Management account reconciliation to audited financials

**Legal & Compliance**
- Corporate structure and cap table
- Material contracts review
- IP ownership and encumbrances
- Litigation and contingent liabilities
- Regulatory and licensing compliance
- Employment agreements and non-competes

**Operational Diligence**
- Technology infrastructure and scalability
- Key person dependencies
- Supply chain and vendor concentration
- Management team assessment
- Systems and data quality

**Tax**
- Historic tax returns and positions
- NOL carryforwards
- State and local tax exposure
- Transaction tax structuring

Output as a checklist document with owner column and deadline column, customized to the target company's sector.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
