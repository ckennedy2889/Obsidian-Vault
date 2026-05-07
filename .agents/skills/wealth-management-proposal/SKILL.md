---
name: wealth-management-proposal
description: "Use when CK asks to run `wealth-management:proposal` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:proposal

## Trigger Aliases

- `wealth-management:proposal`
- `wealth-management-proposal`

## Workflow

Create a customized investment proposal for a prospective client.

Provide a prospect name and any available information (assets, goals, current situation, risk tolerance). Ask if not provided.

Proposal structure:
1. **Understanding Your Situation** — summary of prospect's goals, timeline, risk tolerance, and key concerns (personalized, not generic)
2. **Our Approach** — investment philosophy, process, risk management framework
3. **Proposed Portfolio** — recommended strategic allocation; rationale tied to client's specific goals; benchmark
4. **Portfolio Characteristics** — expected return, volatility, Sharpe ratio, income yield; comparison to alternatives
5. **Implementation Plan** — how the portfolio would be built; timeline; tax-efficient transition if moving from existing holdings
6. **Fee Structure** — clear, transparent fee schedule; what's included
7. **Our Team** — brief, relevant credentials and relevant client experience
8. **Next Steps** — specific, low-friction call to action

Tone: professional, client-centric, specific to their situation — not a generic brochure. Demonstrate you listened to their concerns. Deliver as a polished document (8–12 pages).


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
