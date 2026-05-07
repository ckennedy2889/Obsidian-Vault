---
name: wealth-management-client-report
description: "Use when CK asks to run `wealth-management:client-report` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:client-report

## Trigger Aliases

- `wealth-management:client-report`
- `wealth-management-client-report`

## Workflow

Generate a client performance report for a specified period.

Provide client name and reporting period (e.g., "Smith Family Q4 2025"). Ask if not provided.

Report structure:
1. **Executive Summary** — portfolio value, period return, benchmark comparison, key takeaways
2. **Performance Attribution** — return breakdown by asset class, sector, geography; what drove outperformance or underperformance
3. **Portfolio Snapshot** — current allocation vs. target allocation; drift analysis
4. **Holdings Detail** — position-level performance table: holding, weight, return, contribution
5. **Income Summary** — dividends, interest, realized gains/losses for the period
6. **Market Commentary** — brief context on market conditions during the period (2–3 paragraphs)
7. **Looking Ahead** — key themes and positioning for the next quarter

Deliver a professional, client-ready document in a clear, non-jargon style. Charts for: allocation pie, performance vs. benchmark line chart, attribution waterfall.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
