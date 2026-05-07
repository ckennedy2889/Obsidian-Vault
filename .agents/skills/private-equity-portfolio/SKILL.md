---
name: private-equity-portfolio
description: "Use when CK asks to run `private-equity:portfolio` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:portfolio

## Trigger Aliases

- `private-equity:portfolio`
- `private-equity-portfolio`

## Workflow

Analyze portfolio company performance against plan and benchmarks.

Provide a company name or financial data file. Ask if neither is provided — also ask for the relevant period (monthly, quarterly, annual).

Review framework:
1. **Financial KPIs vs. plan** — Revenue, EBITDA, EBITDA margin, FCF, net debt; actual vs. budget vs. prior period
2. **Operational KPIs** — company-specific leading indicators (e.g., new ARR, units shipped, occupancy rate, same-store sales)
3. **Variance analysis** — explain material variances: volume vs. price vs. mix vs. cost; one-time vs. recurring
4. **Trajectory** — is the business trending better or worse vs. plan? Rate of change matters
5. **Issues & risks** — flag items requiring board or management attention
6. **Value creation progress** — status of 100-day plan items and strategic initiatives

Output: a board-ready performance summary (2–4 pages) with KPI dashboard, variance commentary, and recommended action items. Flag any covenant risk or liquidity concerns.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
