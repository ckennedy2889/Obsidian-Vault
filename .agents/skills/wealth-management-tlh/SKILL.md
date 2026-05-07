---
name: wealth-management-tlh
description: "Use when CK asks to run `wealth-management:tlh` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:tlh

## Trigger Aliases

- `wealth-management:tlh`
- `wealth-management-tlh`

## Workflow

Identify tax-loss harvesting opportunities in taxable accounts.

Provide a client name or specific account. Ask if not provided.

TLH workflow:
1. **Scan for losses** — identify all positions with unrealized losses in taxable accounts; sort by loss size (largest first)
2. **Harvest candidates** — evaluate each loss position:
   - Loss amount ($) and holding period (short-term vs. long-term)
   - Wash sale risk: have you bought substantially identical securities in prior 30 days?
3. **Replacement securities** — for each harvested position, identify a suitable replacement:
   - Maintains similar market exposure (avoid substantially identical)
   - Examples: sell SPY → buy IVV or VTI; sell QQQ → buy VGT; sell sector ETF → buy similar-sector ETF
4. **Wash sale calendar** — track 30-day windows; flag positions where wash sale rule applies
5. **Tax impact summary** — estimated short-term and long-term losses harvestable; tax savings at estimated marginal rate
6. **Priority order** — harvest short-term losses first (offset against short-term gains at higher rate)

Deliver: harvest candidate table with loss amounts, replacement securities, and estimated tax savings. Flag any wash sale conflicts.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
