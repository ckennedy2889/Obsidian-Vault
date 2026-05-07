---
name: private-equity-unit-economics
description: "Use when CK asks to run `private-equity:unit-economics` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:unit-economics

## Trigger Aliases

- `private-equity:unit-economics`
- `private-equity-unit-economics`

## Workflow

Analyze unit economics: ARR cohorts, LTV/CAC, and retention metrics.

Provide a company name or path to data. Ask if not provided.

Analysis framework:
1. **ARR cohort analysis** — plot cohorts by start period; track revenue retention and expansion over time; identify cohort performance trends
2. **Net Revenue Retention (NRR)** — expansion + contraction + churn by cohort; benchmark vs. SaaS standards (>120% = excellent, >100% = good)
3. **Gross Revenue Retention (GRR)** — churn only, excluding expansion; reveals underlying customer stickiness
4. **LTV/CAC** —
   - CAC = S&M spend ÷ new customers acquired (trailing 12 months)
   - LTV = (ARPU × Gross Margin %) ÷ Churn Rate
   - LTV/CAC ratio (>3x is healthy; >5x = pricing power opportunity)
   - CAC payback period in months
5. **Revenue quality** — % recurring vs. transactional; mix shift over time; customer concentration (top 10 as % of ARR)
6. **Cohort benchmarking** — how do newer cohorts compare to older ones? Are unit economics improving or deteriorating?

Deliver: cohort chart, NRR/GRR table, LTV/CAC summary, and interpretation of what the unit economics imply for business quality and growth investment level.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
