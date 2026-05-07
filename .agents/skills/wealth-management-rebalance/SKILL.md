---
name: wealth-management-rebalance
description: "Use when CK asks to run `wealth-management:rebalance` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# wealth-management:rebalance

## Trigger Aliases

- `wealth-management:rebalance`
- `wealth-management-rebalance`

## Workflow

Analyze allocation drift and recommend tax-aware rebalancing trades.

Provide a client name or account. Ask if not provided.

Rebalancing workflow:
1. **Current vs. Target** — map each position to its asset class; compare current weight to target weight; calculate dollar and percentage drift
2. **Drift Threshold** — flag positions exceeding drift threshold (typically ±5% for asset class, ±2% for individual position)
3. **Tax Analysis** — for each position needing reduction: short-term vs. long-term gain/loss, estimated tax cost of selling
4. **Rebalancing Options**:
   - Redirect cash flows (dividends, new contributions) to underweight positions first
   - Harvest losses where available to offset gains from rebalancing
   - Sell positions with lowest tax cost first if forced to realize gains
5. **Trade List** — specific buy/sell recommendations with: security, shares, estimated price, tax impact, rationale
6. **Post-Rebalance Projection** — pro forma allocation after trades; drift vs. target after execution

Output: rebalancing recommendation memo with trade list, tax impact summary, and estimated post-trade allocation. Flag wash sale risks.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
