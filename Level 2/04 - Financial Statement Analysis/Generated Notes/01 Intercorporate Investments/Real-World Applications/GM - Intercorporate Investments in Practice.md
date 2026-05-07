---
title: "GM — Intercorporate Investments in Practice"
subject: Financial Statement Analysis
tags: [CFA-L2, FSA, intercorporate-investments, real-world-application, equity-method, consolidation, NCI]
aliases: [GM Intercorporate Investments, General Motors FSA Application]
---

d

## Why GM is a useful case

A single automaker exhibits **all four** intercorporate-investment categories simultaneously. Same parent, same year, same 10-K — different accounting treatments dictated by the level of influence and ownership. That is exactly the comparison the curriculum asks you to make.

| GM stake | Approximate ownership | Influence | Accounting treatment | Where it shows up |
|---|---|---|---|---|
| **SAIC-GM** (China JV with SAIC Motor) | ~50% | Joint control | **Equity method** (IFRS & GAAP both require for JVs post-2013) | Single line: *"Equity income"* on income statement; *"Investments in nonconsolidated affiliates"* on balance sheet |
| **GM Cruise** (autonomous vehicles) | Majority (>80% as of recent filings, after SoftBank/Honda buy-in dynamics) | Control | **Full consolidation** with **non-controlling interest** | Every line of Cruise's IS/BS rolled into GM's; minority share carved out as NCI in equity and net income attributable to NCI |
| **GM Financial** (captive lender) | 100% | Control | **Full consolidation**, no NCI | Fully embedded — receivables, debt, interest income all in GM consolidated |
| **Equity stakes in suppliers / startups** (e.g., small lithium / battery investments) | <20%, no influence | None | **Financial asset** (FVTPL or FVOCI election) | Fair-value remeasurement to OCI or P&L each period |

## Walking the curriculum framework

### 1. Financial asset (no significant influence, <20%)

GM holds minority stakes in upstream battery and lithium ventures. Under US GAAP (ASC 321), equity investments without significant influence are measured at **fair value through net income** unless the practical expedient applies.

**What you'd see in the 10-K:**
- A small line in *"Other assets"* on the balance sheet
- Unrealized gains/losses flowing through the income statement (or OCI if FVOCI elected under IFRS 9)
- No share of investee earnings — only dividend income and mark-to-market

**Why this matters for the exam:** the *form* of return recognition changes. Dividends + fair-value change, not pro-rata earnings. If the question describes a 10% stake with "no board seat, no influence," reach for the financial-asset rule, not equity method.

### 2. Equity method (significant influence, typically 20–50%, OR a JV)

SAIC-GM is a 50/50 joint venture. Both IFRS (IFRS 11) and US GAAP (ASC 323) require **equity method** for joint ventures.

**Mechanics in GM's books:**

$$\text{Investment}_{t} = \text{Investment}_{t-1} + (\%\text{ owned} \times \text{Investee NI}) - \text{Dividends received} - \text{Amortization of excess purchase price} - \text{Impairment}$$

So if SAIC-GM earns \$2B and GM owns 50%, GM books **\$1B as "Equity income"** on its income statement and the investment account on the balance sheet rises by \$1B (less any dividends received from SAIC-GM, which are *not* income — they reduce the investment account because the income was already booked).

**The single-line nature is the trap.** Cash flow looks lean (only dividends are operating cash, not the full \$1B), revenue does not include SAIC-GM's revenue, and assets/liabilities of SAIC-GM are invisible. Analysts often reconstruct "look-through" margins to compare GM to peers that consolidate similar operations.

**Example interpretation:** if SAIC-GM revenue declines (say, China EV competition crushes margins), GM's *reported revenue* is unchanged but *equity income* shrinks. A naïve YoY revenue comp would miss the story entirely.

### 3. Acquisition method + NCI (control, but <100%)

GM Cruise. GM controls Cruise (board, strategy, capital allocation) but external investors own a minority. Under **acquisition method** (IFRS 3 / ASC 805):

- 100% of Cruise's assets, liabilities, revenue, expenses are **fully consolidated** into GM's statements
- Minority owners' share is broken out as **non-controlling interest** (NCI) in equity and as *"net loss attributable to noncontrolling interests"* on the income statement
- Goodwill arose at the original combination(s) — the difference between purchase price + NCI fair value − fair value of identifiable net assets

**Full vs. partial goodwill choice (IFRS only):**

| Method | NCI measured at | Goodwill recognized |
|---|---|---|
| **Full goodwill** (IFRS option, US GAAP required) | Fair value | Includes NCI's share of goodwill |
| **Partial goodwill** (IFRS option only) | Proportionate share of identifiable net assets | Excludes NCI's share of goodwill |

GM as a US filer uses **full goodwill** by mandate. The choice would only matter if GM were an IFRS preparer.

**Why Cruise matters for FSA:** Cruise has burned billions in operating losses. Those losses hit GM's *consolidated operating income* in full, then a chunk gets attributed back to NCI — so **net income attributable to GM stockholders** > consolidated net income. If you only read the top of the income statement you'd overstate GM-shareholder losses; if you only read the bottom you'd miss the operational cash drag. Both views are required.

### 4. Full consolidation, 100% (no NCI)

GM Financial. Wholly owned, fully consolidated, no NCI line. Every receivable, every dollar of debt funding the loan book, every basis point of interest income is GM's. This is the *vanilla* case — and the contrast with the SAIC-GM line is the whole point.

## The side-by-side that will appear on the exam

If GM held identical 30% economic interests in four entities, with different *forms* of involvement, the income statement impact differs dramatically:

| Treatment | Revenue line | Operating expenses | Operating income | Net income to parent |
|---|---|---|---|---|
| Financial asset (no influence) | — | — | — | Dividend + Δ fair value |
| Equity method (significant influence / JV) | — | — | — | 30% × investee NI (single line) |
| Proportionate consolidation (rare, IFRS legacy) | 30% of investee | 30% of investee | 30% of investee op. income | 30% × investee NI |
| Full consolidation + 70% NCI | 100% of investee | 100% of investee | 100% of investee op. income | 30% × investee NI (NCI strips out the rest) |

**Net income to parent is identical across the bottom three.** Revenue, EBITDA, total assets, and leverage are *not*. This is precisely why the curriculum keeps hammering "method choice doesn't change ultimate equity claim — it changes every ratio above the bottom line."

## Practitioner takeaways the curriculum hints at

- **Comparability is broken** when peers in the same industry use different methods for similar economic exposures. GM (50/50 JV → equity method) vs. Stellantis (a wholly-owned Chinese subsidiary, fully consolidated) would not be apples-to-apples on revenue or EBITDA without adjustment.
- **Look-through reconstruction:** sell-side analysts often build "proportionate" GM by adding back 50% of SAIC-GM revenue and costs to estimate what consolidated GM "really" looks like. CFA does not require you to build this, but it expects you to recognize *why* an analyst would.
- **NCI is not debt and not equity in the traditional sense.** It is a residual claim of outside owners on a *subsidiary*. Treat it carefully in EV calculations: most practitioners add NCI to enterprise value because the EV must support claims of all capital providers, not just the parent's shareholders.

## Exam traps this case prevents

1. Assuming "majority owned" always means consolidate — the question may describe a structure where another party has *substantive participating rights*, defeating control. Then equity method despite >50%.
2. Confusing the *direction* of the dividend adjustment under equity method — dividends *reduce* the investment account, they are not income.
3. Forgetting that **JVs are equity method under both IFRS 11 and ASC 323** — the IFRS option of proportionate consolidation was eliminated in 2013.
4. Treating NCI's share of goodwill as identical under IFRS partial vs. full method — goodwill *amount* differs, and so does any future impairment allocation.

## Memory hook

**"Influence dictates inclusion."** No influence → fair value (one line, mark-to-market). Significant influence or JV → equity method (one line, share of earnings). Control → consolidate (every line, NCI carved out if not 100%).

## Related

- [[Equity Method]]
- [[Acquisition Method]]
- [[Financial Asset Classification]]
- [[Goodwill Full vs Partial and Impairment]]
- [[SPE VIE Consolidation]]
