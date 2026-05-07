---
name: investment-banking-merger-model
description: "Use when CK asks to run `investment-banking:merger-model` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# investment-banking:merger-model

## Trigger Aliases

- `investment-banking:merger-model`
- `investment-banking-merger-model`

## Workflow

Build a merger consequences (accretion/dilution) analysis for an M&A transaction.

If acquirer and target companies are provided (e.g., "Microsoft acquiring Salesforce"), use them. Otherwise, ask for deal details: acquirer, target, deal value, consideration mix (cash/stock), and financing assumptions.

Workflow:
1. Standalone financials: acquirer and target EPS (or net income + share count)
2. Transaction assumptions: purchase price, premium, consideration mix, new shares issued
3. Financing: debt raised, interest rate, cash used, after-tax interest cost
4. Pro forma adjustments: synergies (if any), one-time costs, D&A step-up from purchase price allocation
5. Pro forma EPS: combined net income ÷ combined diluted shares
6. Accretion/dilution: (pro forma EPS − standalone acquirer EPS) ÷ standalone acquirer EPS

Deliver: Excel model (.xlsx) with sources & uses, pro forma income statement, accretion/dilution summary, and sensitivity table (synergies vs. premium paid).


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
