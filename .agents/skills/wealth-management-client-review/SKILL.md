---
name: wealth-management-client-review
description: "Use when CK asks to run `wealth-management:client-review` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:client-review

## Trigger Aliases

- `wealth-management:client-review`
- `wealth-management-client-review`

## Workflow

Prepare a meeting package for a client review meeting.

Provide a client name. Ask if not provided.

Meeting prep package:
1. **Relationship Summary** — client overview, AUM, account types, investment mandate, risk profile, key life events noted in history
2. **Portfolio Snapshot** — current holdings, allocation vs. target, recent transactions
3. **Performance Review** — YTD and trailing 1/3/5-year returns vs. benchmark and peers
4. **Recent Activity** — transactions, rebalancing, distributions since last meeting
5. **Market Context** — key market developments relevant to client's portfolio; how positions have been affected
6. **Agenda** — suggested meeting structure (45–60 minutes)
7. **Talking Points** — 3–5 specific, personalized discussion topics based on client situation (not generic)
8. **Action Items** — open items from prior meeting; decisions needed at this meeting

Style: advisor-only internal prep document. Direct, specific, and client-context-aware. Not for client distribution.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
