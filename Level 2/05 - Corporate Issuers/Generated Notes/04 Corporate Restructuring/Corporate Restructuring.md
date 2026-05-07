---
title: Corporate Restructuring
subject: 05 - Corporate Issuers
tags: [CFA-L2, Corporate-Issuers, Restructuring, M&A, Divestiture, Spin-off, Acquisition, Valuation]
aliases: [Corporate Restructuring, M&A and Restructuring, Module 4 Restructuring]
---

# Corporate Restructuring

## The Big Idea, in One Sentence

A firm can grow by getting **bigger** (investment), sharpen itself by getting **smaller** (divestment), or improve by staying the same size but fixing what's inside (restructuring). Everything in this reading — every valuation trick, every accounting rule, every ratio you watch move — is a variation on those three moves.

---

## Real-World Anchor: MSFT ↔ Activision Blizzard

On October 13, 2023, Microsoft closed its **$68.7 billion** acquisition of Activision Blizzard — the biggest gaming deal in history and the biggest tech M&A ever at the time. It's the anchor for this entire note because it contains almost every concept the CFA tests:

- **Type**: Acquisition (>50% stake, full control → consolidation method).
- **Motivation**: Synergies (gaming content for Xbox Game Pass), diversification into mobile/cloud gaming, and a strategic foothold for long-run metaverse bets.
- **Funding**: All-cash, backed by ~$38B in new bond issuance. This one choice shaped *every* downstream ratio — EPS, Net Debt/EBITDA, WACC.
- **Valuation**: $95/share in cash, a ~45% premium over Activision's unaffected price.
- **Regulatory**: 21-month review across the US FTC, UK CMA, and EU — a textbook "WHEN" evaluation risk.
- **Post-close**: EPS accretion in FY24, Net Debt/EBITDA temporarily spiked past 1.0× (still investment-grade), and [[WACC]] held roughly flat as the tax shield on new debt offset higher equity beta.

Today MSFT trades near **$420** with ~$3.1T market cap. Activision is a wholly-owned subsidiary reported inside Microsoft's *More Personal Computing* segment. Every analyst question in this reading maps onto a real decision someone had to make on this deal.

---

## Map of the Terrain

Before we dive into LOS-by-LOS, pin this mental map. Every restructuring action falls into one of three boxes, and knowing which box tells you most of what you need.

![[Corporate Restructuring Map.png]]

Three categories, three life-cycle fits, three motivations. If you can look at any deal announcement and sort it into the right box in 10 seconds, you've already done 80% of the qualitative work the exam wants.

---

## LOS 1 — Types of Restructuring and Their Motivations

Think of a firm's life cycle. Early on it's starved for scale, so it buys things (**investment**). In maturity it has too many things and investors start complaining about the "conglomerate discount," so it sells the losers (**divestment**). In decline it can't buy *or* sell its way out, so it must operate more efficiently or repair its balance sheet (**restructuring**).

### Investment Actions — Getting BIGGER

The three-tier ladder of control is the key mental model:

| Stake | Name | Control | Accounting |
|-------|------|---------|------------|
| < 20% (often) | Equity Investment | No significant influence | Financial asset (fair value) |
| 20–50% | Equity Investment | Significant influence | [[Equity Method]] (one-line) |
| 50/50 or shared | Joint Venture | Shared control | Equity method (rarely proportionate) |
| > 50% | Acquisition | Full control | [[Acquisition Method]] (full consolidation) |

The **motivations** compress into a short list CFA loves to test:

1. **Synergies** — revenue synergies (cross-sell, pricing power) or cost synergies (eliminate duplicate corporate overhead, procurement scale). Cost synergies are easier to quantify and more reliable; revenue synergies often disappoint.
2. **Speed** — buying a company is faster than building the capability. MSFT could have spent a decade building a mobile-gaming arm from scratch; buying Activision bought ~10 years.
3. **Access to resources** — customers, patents, distribution, scarce talent, regulatory licenses.
4. **Diversification** — into new geographies, products, or end-markets. Note the CFA exam tests this skeptically: diversification at the *firm* level rarely helps shareholders, who can diversify themselves cheaper. Management usually loves it anyway.
5. **Industry forces** — consolidation waves in mature industries (banking, telecom) where scale is the only path to margin protection.

### Divestment Actions — Getting SMALLER

Four flavors, distinguished by *who ends up holding the sub's shares* and *whether parent gets cash*:

| Action | Buyer | Parent Gets | Shareholder Receives | Tax Status |
|--------|-------|-------------|----------------------|------------|
| **Sale** | 3rd party | Cash | Nothing (just smaller parent) | Taxable gain at parent level |
| **Spin-off** | Existing shareholders (pro-rata) | Nothing | New shares in sub | Usually tax-free if structured right |
| **Split-off** | Existing shareholders (choose) | Some shares retired | Choice: keep parent OR swap for sub | Usually tax-free |
| **Carve-out** | Public markets (IPO) | Cash | Nothing (parent still controls) | Taxable (partial IPO) |

Motivations collapse to three words: **focus, unlock, liquidity**.
- *Focus*: investors will pay more for two pure-play firms than one sprawling conglomerate (the **conglomerate discount** / "sum-of-the-parts" discount).
- *Unlock*: a high-growth subsidiary buried inside a slow-growth parent gets its own P/E multiple once it trades separately — see GE's 2024 three-way split into GE Aerospace, GE Vernova (energy), and GE HealthCare, each of which immediately traded at multiples the old GE could never have commanded.
- *Liquidity*: parent raises cash it needs for debt paydown or reinvestment.

### Restructuring Actions — Getting BETTER

This is the "stay the same size but fix the engine" box.

- **Cost restructuring**: headcount cuts, offshoring, process re-engineering, shared-services centers. Goal: **EBITDA margin ↑**.
- **Balance sheet restructuring**: sale-leasebacks (convert owned real estate to cash + rent expense), dividend recapitalizations (borrow → pay special dividend), share buybacks, LBOs. Goal: **WACC ↓** via optimized leverage *or* return cash to shareholders.
- **Reverse stock split**: cosmetic — 1-for-10 consolidation to avoid exchange delisting when shares fall below $1. No fundamental change, but important to recognize so you don't mistakenly read it as a distress signal when it *is* a distress signal in most cases.
- **Bankruptcy / reorganization**: court-supervised debt renegotiation. Operations continue; equity usually gets wiped or massively diluted; debt-holders become new equity-holders. US Chapter 11 is the classic example.

**Memory hook — "BIGGER / SMALLER / BETTER"**: three gears a firm can shift into. And each gear matches a life-cycle stage: young firms get bigger, mature firms get smaller, troubled firms get better.

---

## LOS 2 — Initial Evaluation: The Four Questions

Any time a deal hits the tape, your first 60 seconds as an analyst should answer four questions in order:

**1. WHAT?** — *What kind of transaction is this?* Sort it into the typology above. An acquisition is a completely different analysis than a spin-off.

**2. WHY?** — *Is this on-strategy or a pivot?* Read management's stated motivation in the press release, then stress-test it. The stated rationale is almost always "synergies" — but what kind, and are they credible?

**3. MATERIAL?** — *Is this big enough to matter?* The rough rule is **deal value ≥ 10% of enterprise value**. Below that, it barely moves the needle; above it, rebuild your model. MSFT buying Activision for $68.7B against MSFT's then-$2.5T EV was ~2.7% — materiality is a judgment call, not a hard rule.

**4. WHEN?** — *Announced vs. closed, and what's in between?* The gap is regulatory review + financing + shareholder approval. It's where deals break (arbitrage spread tells you the market's probability of close), and it's where ratios look weird (the target is still independent on paper but everyone models it as part of the acquirer).

**Memory hook — "WHAT WHY MATERIAL WHEN"**: four questions, one per analyst, one minute each.

---

## LOS 3 — Valuation Methods for the Target

You cannot evaluate whether a deal is wise until you value the target *yourself* — independent of the announced price — and then compare. Three standard methods, each with a different idea of "value":

### Discounted Cash Flow (DCF)

Project the target's free cash flow for 5–10 years, discount at its own [[WACC]] (not the acquirer's!), add a terminal value, subtract net debt → equity value.

$$
\text{EV} = \sum_{t=1}^{T} \frac{\text{FCFF}_t}{(1 + \text{WACC})^t} + \frac{\text{TV}}{(1 + \text{WACC})^T}
$$

**Why target's WACC, not acquirer's?** Because it's the *target's* cash flows you're discounting. Using the acquirer's WACC (usually lower, because bigger firms are less risky) would artificially inflate the value and make any deal look good. Classic CFA trap.

### Comparable Company Analysis ("Trading Comps")

Pick 4–8 publicly traded peers, calculate their EV/EBITDA or P/E multiples, apply the median multiple to the target's EBITDA/earnings.

- **Pro**: current market prices, simple.
- **Con**: no control premium baked in. These are minority-interest prices — they tell you what a *passive investor* pays per unit of EBITDA, not what a *controlling acquirer* would pay.

### Precedent Transactions ("Transaction Comps")

Same idea, but using actual M&A deals in the sector. This *does* include the control premium, so it sets a realistic floor for bid price.

- Control premiums typically run **20–40%** over the target's unaffected share price (the price 30–60 days before the bid leaks).
- Premiums are larger in hostile deals, smaller in friendly deals with agreed-upon management.

### The Valuation Triangulation

Good analysts present all three side-by-side, discuss why they differ, and arrive at a range. Deal price above the top of the range? Overpayment — look for what intangible the acquirer thinks justifies it. Below the bottom? Either the target is distressed, or you're missing something.

**Worked mini-example — valuing Activision for the MSFT bid:**
- DCF on standalone Activision cash flows (low-teens growth, 15% EBITDA margin, 8.5% WACC) → ~$65–75/share.
- Trading comps (EA, Take-Two, Ubisoft at ~12–15× EV/EBITDA) → ~$70–80/share.
- Precedent transactions (ZeniMax/Bethesda at $7.5B; older deals) + typical 30% control premium → ~$85–95/share.

MSFT bid **$95 cash/share** — right at the top of the range. The "excess" over DCF is what MSFT thinks Game Pass synergies are worth.

---

## LOS 4 — Impact on EPS, Net Debt/EBITDA, WACC

The single most-tested section of this reading. Your job: given the **funding mix** of a deal (cash vs. stock vs. mixed), predict the direction of three ratios.

![[Deal Financing Impact.png]]

Rather than memorize nine cells, understand the two underlying mechanics:

### Mechanic 1 — EPS is about share count vs. earnings added

$$
\text{Post-deal EPS} = \frac{\text{NI}_{\text{acquirer}} + \text{NI}_{\text{target}} - \text{new interest} \times (1-t)}{\text{Shares}_{\text{acquirer}} + \text{new shares issued}}
$$

- **Cash/debt deal** → numerator rises (target's NI added, minus after-tax interest on debt), denominator unchanged. Usually **accretive**.
- **Stock deal** → numerator rises (target's NI added), denominator also rises (new shares). Accretion/dilution depends on the **P/E test**:
  - Acquirer P/E > target P/E → accretive (your earnings "multiplier" is higher, so the deal creates EPS).
  - Acquirer P/E < target P/E → dilutive (paying a premium in expensive shares).

### Mechanic 2 — Leverage is about debt vs. EBITDA added

$$
\text{Post-deal ND/EBITDA} = \frac{\text{Net Debt}_{\text{combined}} + \text{new debt raised}}{\text{EBITDA}_{\text{acquirer}} + \text{EBITDA}_{\text{target}}}
$$

- **Cash deal** with new debt → numerator shoots up, denominator grows modestly → ratio **rises**. Sometimes sharply. Ratings agencies will often downgrade.
- **Stock deal** → no new debt in numerator, full EBITDA added → ratio often **falls**.

### Mechanic 3 — WACC is about the capital mix and risk

Recall the [[WACC]] formula:

$$
\text{WACC} = \frac{E}{V} r_e + \frac{D}{V} r_d (1-t)
$$

A cash/debt deal *raises* D/V (more debt weight) which pushes WACC down via the tax shield — but it also raises financial risk, which raises $r_e$ and sometimes $r_d$. In the [[trade-off theory]] framework, you're moving *along* the U-curve from [[Optimal Capital Structure|Optimal Capital Structure]]. The net WACC move depends on which side of the optimum you started.

**Exam shortcut** — memorize the directional table from the diagram above. When in doubt:
- All-cash → **EPS ↑, leverage ↑, WACC ambiguous** (↓ first, then ↑).
- All-stock → **EPS usually ↓, leverage ↓, WACC ↑**.
- Mixed → everything muted.

**MSFT/Activision applied:** All-cash/debt → FY24 EPS grew roughly 20% (accretive), ND/EBITDA briefly hit ~1.0× (up from ~0.5×), WACC held in the 9–10% range because the tax shield on new bonds roughly offset a small rise in equity beta.

---

## LOS 5 — Investment Actions in Detail

The accounting treatment is where the exam lives, because the same underlying economic stake produces very different numbers on the financial statements depending on the method.

### Equity Investment (typically < 50%)

Two sub-cases:

**Case A — No significant influence (usually < 20%)**: Treat as a financial asset. Record at fair value; changes hit either P&L (FVTPL) or OCI (FVOCI, for most equity investments under IFRS). Dividends received → income. No share of earnings recognized.

**Case B — Significant influence (usually 20%–50%)**: [[Equity Method]]. Balance sheet shows one line: "Investment in Associate," carried at cost + cumulative share of associate's net income − dividends received. Income statement shows one line: "Equity in earnings of associate" = your ownership % × associate's net income. Dividends from associate *reduce* the investment balance (they're a partial return of the investment, not income).

**Key exam wrinkle**: "significant influence" is usually indicated by ≥ 20% ownership *but also* can exist below 20% (board seat, material intercompany transactions) — and can be *denied* above 20% (another shareholder has majority control).

### Joint Venture

Two or more firms jointly control a new entity (NewCo) under a contractual arrangement. Under both IFRS and US GAAP, joint ventures are accounted for using the **equity method** (proportionate consolidation is no longer permitted under IFRS since 2013). The balance-sheet footprint is small; the equity-method carrying value aggregates your share.

Use cases: new market entry (foreign JV with local partner who knows the regulatory landscape), R&D cost sharing (Sony-Ericsson), capex-intensive projects (oil-and-gas JVs).

### Acquisition ( > 50% / full control)

[[Acquisition Method]] — the full consolidation treatment. Every line of the target's financial statements is added to the parent's at **fair value** at the acquisition date. The mechanics:

1. **Identify the acquirer**.
2. **Measure the consideration transferred** (cash + stock + any contingent consideration).
3. **Fair-value the target's identifiable assets and liabilities** (often revising up PP&E and identifying previously-unbooked intangibles: brand, customer relationships, IP).
4. **Goodwill** = Consideration − Fair value of net identifiable assets. It plugs the difference. Goodwill is not amortized; tested annually for impairment.
5. **Non-controlling interest (NCI)** if parent owns < 100%: the minority shareholders' slice of net assets shows up in equity and their slice of earnings in the income statement.

**Worked example — MSFT/Activision consolidation (simplified):**
- Consideration: $68.7B cash.
- Activision fair value of net identifiable assets (rough estimates): ~$25B (cash, A/R, PP&E, game IP intangibles, net of liabilities).
- **Implied goodwill: ~$43B**.
- That $43B now sits on MSFT's balance sheet indefinitely unless the gaming segment underperforms and triggers an impairment test.

**Key ratio side-effect**: goodwill inflates total assets, so post-acquisition ROA and asset turnover look worse than pre-acquisition — not because the business got worse, but because the denominator is bigger.

---

## LOS 6 — Divestment Actions in Detail

Understanding who ends up with what is the whole game.

### Sale

Simplest: parent sells segment to a 3rd party for cash. Book gain/loss on disposal = cash received − book value of net assets sold. The gain is generally taxable at the parent level (in the US, at full corporate rate, unless structured to qualify for specific rollovers).

**Valuation**: transaction comps (what similar segments have sold for recently).

### Spin-off

Parent distributes shares of a subsidiary **pro rata** to existing shareholders as a **stock dividend**. After: parent has fewer assets; shareholders own two separate stocks (the leaner parent + the new sub). **No cash changes hands** — shareholders just got two pieces of paper instead of one.

- **Tax**: Usually **tax-free** to both parent and shareholders if it qualifies as a "Section 355" distribution (meets IRS tests on business-purpose, continuity of interest, and the "active trade or business" requirement).
- **Motivation**: Separate management focus, different investor bases, unlock hidden value. Spin-offs empirically outperform the market in the 1–2 years post-separation (well-documented anomaly).
- **Example**: GE's 2024 three-way split — GE Aerospace, GE Vernova (energy), GE HealthCare. Each now runs with its own strategy and trades at its own multiple instead of all three getting dragged down by the lowest common denominator.

### Split-off

Like a spin-off, but **shareholders choose**: keep your parent shares, OR exchange some/all of them for shares in the sub. The sub shares are essentially "bought" using parent shares, which the parent then retires (reducing parent share count).

- **Effect on parent**: Share count falls (unlike spin-off where it stays flat). EPS mechanics get interesting.
- **Use case**: parent wants to tighten its own shareholder base or return capital efficiently.

### Equity Carve-out

Parent IPOs a **minority stake** (typically 10–20%) of a subsidiary to the public, keeps majority control. Parent raises cash; sub gets a public market price and currency for its own M&A.

- Often a prelude to a full spin-off 1–3 years later (two-step exit).
- **Price discovery** is a big motivation: the market tells you what the sub is actually worth before you fully separate.

**Exam trap**: spin-off (parent unchanged share count, shareholder gets 2 stocks) vs split-off (parent share count *falls*, shareholder exchanges) vs carve-out (parent gets cash from public). Know the cash flows.

---

## LOS 7 — Cost and Balance Sheet Restructuring

### Cost Restructuring

The playbook:
- **Headcount**: layoffs, voluntary separations, hiring freezes.
- **Footprint**: close plants, consolidate offices, offshore support functions.
- **Process**: automation, shared-services, procurement consolidation.
- **Make-vs-buy**: outsource non-core (IT, facilities, manufacturing steps).

**Effect on ratios**: EBITDA margin ↑ (good), but restructuring *charges* (severance, impairments) hit the income statement as **non-recurring** expenses in the year of the action. Analysts strip these out when computing "underlying" or "adjusted" EBITDA.

### Balance Sheet Restructuring

Four main tools:

| Tool | Mechanics | Goal |
|------|-----------|------|
| **Sale-leaseback** | Sell owned real estate, lease it back | Unlock cash, reduce assets; net rent expense rises |
| **Dividend recap** | Borrow large sum, pay as special dividend to equity holders | Return cash, raise leverage to optimum |
| **Share buyback** | Repurchase own shares with excess cash or new debt | Reduce share count → EPS ↑; signal undervaluation |
| **[[LBO]]** | Buyer uses mostly debt to take company private | Extract tax shield, force discipline via debt service |

All four move the firm **along its capital-structure curve** toward its [[Optimal Capital Structure|optimum]]. If the firm was under-levered, these actions lower WACC. Overshoot the optimum and distress costs kick in.

**Key formula recap** for exam:

$$
\text{WACC} = \frac{E}{V} r_e + \frac{D}{V} r_d (1-t)
$$

A well-calibrated balance sheet restructuring moves the debt-weight term up while keeping $r_d(1-t)$ low (tax shield intact) and before $r_e$ explodes from financial distress risk.

### Reverse Stock Split

Cosmetic: 1-for-10 means 10 old shares → 1 new share, share price × 10. Market cap unchanged. Used to:
- Avoid delisting (most exchanges require price > $1).
- Attract institutional investors who won't buy "penny stocks."
- Signal stability after prior distress.

No impact on fundamentals; but note that many reverse splits precede or follow genuine distress, so it's a flag — not a cause — for further investigation.

### Bankruptcy / Reorganization

The nuclear option. Court-supervised debt renegotiation under US Chapter 11 (operations continue) or Chapter 7 (liquidation). In Chapter 11:
- Equity usually wiped or massively diluted.
- Unsecured debt often converts to new equity.
- Secured debt and trade creditors typically made whole or close to it.
- Operations continue during the process under court oversight ("debtor in possession").

Not usually on a CFA Level 2 quantitative question but the **impact on capital structure** is tested — who gets what in the post-emergence entity.

---

## The Memory Palace

If you remember nothing else from this reading:

- **Three boxes**: Investment (BIGGER), Divestment (SMALLER), Restructuring (BETTER). Motivations follow life-cycle stage.
- **Four questions**: WHAT, WHY, MATERIAL, WHEN. Run them on every deal announcement in the first 60 seconds.
- **Three valuations**: DCF (fundamental), trading comps (minority price), precedent transactions (control price). Triangulate.
- **Three ratios for deals**: EPS, Net Debt/EBITDA, WACC. Funding method drives the direction.
- **Control ladder**: < 20% (fair value), 20–50% (equity method), 50/50 (JV equity method), > 50% (acquisition/consolidate).
- **Divestment distinguish-er**: Sale (cash, 3rd party), Spin-off (shareholders get new shares), Split-off (shareholders choose), Carve-out (IPO minority stake).

**Mnemonic — "BSD BED"** for the three main boxes and their typical sub-life-cycle:
- **B**igger / **S**tart-up & Growth / **D**eal-making
- **S**maller / maturity / **E**xit carve
- **D** (=Distress) / **B**ankruptcy/**E**fficiency / **D**ebt fix

(Not the prettiest mnemonic, but it hooks the triangle shape.)

---

## Cross-Links to the Rest of the Vault

This reading is tightly connected to the capital-structure and cost-of-capital readings that come just before it:

- [[Cost of Capital - Advanced Topics]] — the WACC changes you compute post-deal rely on everything from top-down factors to cost of debt to ERP methods.
- [[Optimal Capital Structure]] — balance-sheet restructuring = movement along this U-curve.
- [[WACC]] — post-consolidation WACC recomputation.
- [[Equity Method]] — how 20–50% stakes flow through IS and BS.
- [[Acquisition Method]] — full consolidation mechanics, goodwill, NCI.
- [[LBO]] — one specific flavor of balance-sheet restructuring.
- [[Goodwill and Impairment]] — what happens to the $43B of MSFT/Activision goodwill if gaming underperforms.
- [[Relative Valuation]] — trading comps and precedent transactions.
- [[DCF Valuation]] — the fundamental leg of the valuation triangle.

On the exam, restructuring questions will almost always pivot on one of three things: **the accounting treatment** (equity vs acquisition method — does goodwill arise? what's the income-statement impact?), **the directional ratio effect** (cash vs stock deal → EPS/leverage/WACC direction), or **a valuation triangulation** (DCF + comps + transactions → is the price justified?). Master those three pivots and you've handled 90% of what can be asked.
