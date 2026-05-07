---
title: "Equity Valuation - Applications and Processes"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments]
aliases: []
---

# Equity Valuation: Applications and Processes

> **CFA Level II — Reading 17**
> *This reading is the gateway to all of [[Equity Valuation]]. Every model you'll learn later — [[Dividend discount model|DDM]], [[Free Cash Flow Valuation|FCF]], [[Residual Income Valuation|RI]], [[Market-Based Valuation|Multiples]] — builds on the [[Foundations|foundations]] here.*

---

## LOS 17.a — [[Valuation]] and [[Intrinsic value]], Sources of Perceived [[Mispricing]]

### What Is Valuation?

[[Valuation]] is the process of figuring out what an asset is *actually worth*. Think of it like this: if you're at a garage sale and someone is selling a vintage guitar, you need to decide — "Is this thing worth $500 or $50?" That decision-making process *is* [[Valuation|valuation]].

In finance, the "garage sale" is the [[Stock Market]], and the "guitar" is a company's stock. The price tag is whatever the stock is trading at right now (the [[Market Price]]). But is that price tag *right*? That's what [[Valuation|valuation]] tries to answer.

### What Is Intrinsic Value?

[[Intrinsic value]] (IV) is the "true" value of an asset, estimated by someone who has **complete understanding** of all the characteristics of that asset or the company that issued it.

> **Analogy:** Imagine you're the world's greatest mechanic, and someone brings you a used car. You know every part, every mile, every hidden dent. The price you'd put on that car — accounting for everything you know — is its [[Intrinsic value|intrinsic value]]. A random person on Craigslist might price it differently because they don't know what you know.

**Why does [[Intrinsic value|intrinsic value]] matter?** Because [[Market Price|market prices]] are not always "right." If the market were perfectly [[Market efficiency|efficient]] (meaning prices instantly reflected all available information), the market price would always equal [[Intrinsic value|intrinsic value]], and there would be no point in doing analysis. But markets are *not* perfectly efficient — prices can be too high or too low relative to what a company is truly worth.

### Sources of Perceived Mispricing

When an [[Analyst]] looks at a stock and says "I think this stock is mispriced," the perceived [[Mispricing|mispricing]] actually comes from **two sources**:

$$\text{IV}_{\text{analyst}} - \text{Price} = \underbrace{(\text{IV}_{\text{actual}} - \text{Price})}_{\text{True Mispricing}} + \underbrace{(\text{IV}_{\text{analyst}} - \text{IV}_{\text{actual}})}_{\text{Valuation Error}}$$

Let's break this down:

| Component | What It Means | Plain English |
|---|---|---|
| $\text{IV}_{\text{analyst}} - \text{Price}$ | **Perceived [[Mispricing|mispricing]]** — what the analyst *thinks* the gap is | "I think this stock is undervalued by $5" |
| $\text{IV}_{\text{actual}} - \text{Price}$ | **True [[Mispricing|mispricing]]** — the *real* gap between what the stock is worth and its price | The stock really *is* undervalued by $3 |
| $\text{IV}_{\text{analyst}} - \text{IV}_{\text{actual}}$ | **[[Valuation|Valuation]] error** — the analyst's own mistake in estimating value | The analyst overestimated value by $2 |

> **Real-World Example:** In 2008, many analysts at [[Investment banks|investment banks]] had models that said [[Mortgage-backed securities|mortgage-backed securities]] were worth far more than they turned out to be. Their $\text{IV}_{\text{analyst}}$ was way above $\text{IV}_{\text{actual}}$. That gap — the [[Valuation Error]] — led to massive losses.

### Key Takeaway

Even the best analyst in the world will have *some* [[Valuation Error]]. The goal isn't to eliminate it — it's to make it small enough that your estimate is closer to reality than the market price is. If $|\text{IV}_{\text{analyst}} - \text{IV}_{\text{actual}}| < |\text{IV}_{\text{actual}} - \text{Price}|$, you'll make money on average.

---

## LOS 17.b — The [[Going Concern Assumption]] vs. [[Liquidation value]]

### Going Concern Assumption

The [[Going Concern Assumption]] is the assumption that a company **will continue to operate as a business** into the foreseeable future. It won't shut down, go bankrupt, or sell off all its stuff tomorrow.

**Why does this matter?** Because *every single valuation model* you'll learn in CFA Level II — [[Dividend discount model|DDM]], [[Free Cash Flow Valuation|FCF]], [[Residual Income Valuation|Residual Income]] — is built on this assumption. These models say "the company will keep generating cash flows into the future, and we can discount those back to today." If the company is about to go out of business, that logic falls apart.

> **Analogy:** Valuing a company as a [[Going Concern]] is like valuing a pizza restaurant based on how many pizzas it will sell over the next 20 years. You're valuing the *business* — the oven, the recipes, the customer relationships, the brand. It's worth more as a running operation than as a pile of used kitchen equipment.

### Liquidation Value

[[Liquidation value]] is what you'd get if you **broke the company apart and sold every asset separately**, then paid off all the [[Liabilities|debts]].

This is the "worst case" value — the "if everything goes wrong, what's the floor?" number.

There are two flavors:

| Type | Definition | When It's Used |
|---|---|---|
| **[[Liquidation value]]** | Assets sold off quickly (fire sale) | Company needs cash *now* — [[Bankruptcy|bankruptcy]], forced sale |
| **[[Orderly liquidation value]]** | Assets sold over time to get better prices | Company has some time — voluntary wind-down |

> **Real-World Example:** When Toys "R" Us went bankrupt in 2018, it couldn't continue as a [[Going Concern]]. Nobody was going to buy it as a running toy store. Instead, liquidators came in and sold the [[Inventory|inventory]], the [[Real estate|real estate]], the brand name — all separately. The total they collected (minus debts) was the [[Liquidation value]]. It was far less than what the company would have been worth if it had stayed in business.

### When to Use Which

| Situation | Appropriate Approach |
|---|---|
| Healthy company with stable operations | [[Going Concern]] [[Valuation|valuation]] (DDM, FCF, RI) |
| Company is bankrupt or about to fail | [[Liquidation value]] |
| Company's future is uncertain | Consider both, compare |

---

## LOS 17.c — Definitions of Value

There are several different definitions of "value," and each one is useful in a different context. Think of them as different lenses you can put on to look at the same company.

### The Definitions

#### 1. [[Intrinsic value]] (IV)
The value of an asset based on a **complete understanding** of its characteristics. This is what *you* (the analyst) are trying to estimate. It's the "truth" — or as close as you can get.

**Most relevant to:** [[Public Company Valuation|Public company valuation]] by equity analysts trying to find [[Mispricing|mispriced]] stocks.

#### 2. [[Fair market value]] (FMV)
The price at which a **hypothetical willing, informed, and able seller** would trade the asset to a **willing, informed, and able buyer**. Neither party is under pressure to transact.

This is similar to the concept of [[Fair value]] used in [[Financial Reporting]]. It's the price that *should* emerge in an arm's-length transaction.

> **Analogy:** If you're selling your house and both you and the buyer know everything about the house, the neighborhood, and the market — and neither of you is desperate — the price you agree on is the [[Fair market value]].

#### 3. [[Investment value]]
The value of a stock **to a particular buyer**. This can differ from [[Intrinsic value]] because a specific buyer might see [[Synergies]] — cost savings, revenue boosts, strategic advantages — that a generic buyer wouldn't.

**Most relevant to:** [[Mergers and Acquisitions|Acquisitions]], where a strategic buyer (like a competitor) might be willing to pay more than what the company is worth on a standalone basis.

> **Real-World Example:** When Disney acquired Pixar in 2006, the [[Investment value]] of Pixar to Disney was higher than its standalone [[Intrinsic value]]. Why? Because Disney could use Pixar's animation talent across its theme parks, merchandise, and streaming platforms — [[Synergies]] that only Disney could unlock.

### Which Definition Matters Most?

| Context | Most Appropriate Definition |
|---|---|
| Equity analyst picking stocks | [[Intrinsic value]] |
| [[Acquisition|Acquisition]] by a strategic buyer | [[Investment value]] |
| Legal/tax proceedings | [[Fair market value]] |
| Financial reporting (GAAP/[[IFRS]]) | [[Fair value]] |

**For the CFA exam and for most public company valuation, [[Intrinsic value]] is the most relevant concept.**

---

## LOS 17.d — Applications of [[Equity Valuation]]

[[Equity Valuation]] isn't just for stock picking. Analysts use the same toolkit across many scenarios. Here are the key applications:

### 1. [[Stock Selection]]
The most obvious use. An analyst builds a valuation model, estimates [[Intrinsic value]], and compares it to [[Market Price]]. If IV > Price → buy. If IV < Price → sell (or short).

### 2. Reading the Market
Analysts use valuation models to **infer what the market is implying** about a company's future. For example, if a stock trades at a [[P/E Ratio]] of 40, the market is implying very high future [[Earnings Growth]]. The analyst can then decide whether that implied growth is realistic.

### 3. Projecting the Value of [[Corporate Actions]]
When a company announces a [[Mergers and Acquisitions|merger]], a [[Share Buyback|stock buyback]], or a [[Spin-off]], analysts use valuation to estimate how the action will affect the stock price.

### 4. [[Fairness Opinions]]
When a company is being acquired, the board of directors hires an investment bank to issue a [[Fairness Opinion]] — a formal statement that the acquisition price is "fair" to shareholders. This requires rigorous valuation.

### 5. Planning and Consulting
Management teams use valuation to make strategic decisions: Should we enter a new market? Should we divest a division? What's our company worth if we restructure?

### 6. Communication with Analysts and Investors
Valuation provides a **common language** between management, investors, and analysts. Everyone can discuss the company's performance and outlook using the same framework.

### 7. Valuation of [[Private Company Valuation|Private Businesses]]
Companies that aren't publicly traded still need to be valued — for [[Venture capital]] rounds, [[Initial public offering|IPOs]], estate planning, or divorce settlements.

### 8. [[Portfolio Management]]
In the broader [[Investment Process]], valuation feeds into both the **planning** phase (what strategy to follow) and the **execution** phase (which securities to buy or sell).

---

## LOS 17.e — Industry and [[Competitive Analysis]]

Before you can value a company, you need to understand the industry it operates in. A great company in a terrible industry can still be a bad investment.

### [[Porter's Five Forces]]

Professor [[Michael Porter]] developed a framework of five competitive forces that determine how profitable an industry is. Think of these forces as "headwinds" — the stronger they are, the harder it is for companies in the industry to make money.

```
                    ┌─────────────────────┐
                    │  Threat of New      │
                    │  Entrants           │
                    └────────┬────────────┘
                             │
                             ▼
┌──────────────┐   ┌─────────────────────┐   ┌──────────────┐
│ Bargaining   │──▶│  Rivalry Among      │◀──│ Bargaining   │
│ Power of     │   │  Existing           │   │ Power of     │
│ Suppliers    │   │  Competitors        │   │ Buyers       │
└──────────────┘   └────────┬────────────┘   └──────────────┘
                             │
                             ▼
                    ┌─────────────────────┐
                    │  Threat of          │
                    │  Substitutes        │
                    └─────────────────────┘
```

| Force | What It Means | Real-World Example |
|---|---|---|
| **Threat of New Entrants** | How easy is it for new competitors to enter? High barriers = good for incumbents. | Opening a new airline is incredibly expensive (planes, routes, regulations) → low threat. Opening a new food truck is cheap → high threat. |
| **Threat of Substitutes** | Can customers switch to a different product that serves the same need? | Netflix is a substitute for cable TV. Uber is a substitute for taxis. |
| **Bargaining Power of Buyers** | Can customers force prices down? | Walmart has enormous bargaining power over its suppliers because it buys in such huge volumes. |
| **Bargaining Power of Suppliers** | Can suppliers charge more? | Intel (as a chip supplier) had huge bargaining power over PC makers because there were few alternatives. |
| **Rivalry Among Existing Competitors** | How intense is competition? | Airlines compete fiercely on price → high rivalry. Luxury brands compete on exclusivity, not price → lower rivalry. |

### Three [[Generic Competitive Strategies]]

Once you understand the industry, you need to understand *how* the company competes:

1. **[[Cost Leadership]]** — Being the cheapest producer. Example: Walmart, Ryanair.
2. **[[Product Differentiation]]** — Making your product unique so customers pay a premium. Example: Apple, Tesla.
3. **[[Focus Strategy]]** — Applying either cost leadership or differentiation to a *narrow* segment. Example: Rolls-Royce (luxury focus), Dollar Shave Club (price focus in razors).

### [[Quality of Earnings]]

When analyzing a company's financials, the analyst must assess whether the reported numbers are reliable. [[Quality of Earnings]] refers to how accurately the financial statements reflect the company's true economic performance.

**Warning signs of poor [[Earnings quality|earnings quality]] include:**

| Red Flag | What's Happening |
|---|---|
| Premature [[Revenue Recognition]] | Recording sales before products are shipped or accepted |
| Reclassifying [[Non-Operating Income]] as operating | Making one-time gains look like regular business income |
| Delaying [[Expense Recognition]] | Pushing costs into future periods to inflate current profits |
| Aggressive [[Depreciation]]/[[Amortization]] choices | Using longer asset lives to reduce annual expenses |
| [[Off-Balance-Sheet]] items | Hiding liabilities in [[Special Purpose Entities]] |

> **Real-World Example:** Enron used [[Special Purpose Entities]] (SPEs) to hide billions in debt off its [[Balance sheet]]. Analysts who dug into the footnotes could see the warning signs, but many didn't. When the truth came out, the stock went from $90 to $0.

---

## LOS 17.f — [[Absolute Valuation Models]] vs. [[Relative valuation models]]

This is one of the most important distinctions in all of equity valuation. Every model you'll ever use falls into one of these two buckets.

### Absolute Valuation Models

An [[Absolute Valuation Models|absolute valuation model]] estimates the [[Intrinsic value]] of an asset based on its **own** characteristics — its cash flows, growth rate, and risk — **without** reference to other companies.

> **Analogy:** It's like appraising your house by calculating the present value of all the rent you could collect if you rented it out for the next 30 years. You're not looking at what the neighbor's house sold for. You're building value from scratch.

**Types of Absolute Models:**

| Model | How It Works | Best For |
|---|---|---|
| [[Dividend discount model]] (DDM) | Value = PV of all future [[Dividends]] | Mature companies that pay stable dividends (utilities, banks) |
| [[Free Cash Flow Valuation|Free Cash Flow]] (FCF) | Value = PV of all future [[Free cash flow]] to equity or firm | Companies with predictable cash flows; also useful when an acquirer can control [[Dividend policy]] |
| [[Residual Income Valuation|Residual Income]] (RI) | Value = [[Book value]] + PV of future [[Residual income]] | Companies with negative [[Free cash flow]] or no dividend history, but transparent accounting |
| [[Asset-based valuation|Asset-Based]] | Value = Sum of [[Market value]] of all assets owned | Companies with significant tangible assets (oil companies, mining firms, real estate) |

### Relative Valuation Models

A [[Relative valuation models|relative valuation model]] estimates the value of an asset by comparing it to **similar assets**. Instead of building value from scratch, you look at how the market has priced comparable companies and ask: "Is this stock cheap or expensive relative to its peers?"

> **Analogy:** It's like pricing your house by looking at what similar houses in your neighborhood recently sold for. You don't calculate rental income — you just compare.

**Types of Relative Models (common [[Multiples]]):**

| Multiple | Formula | What It Tells You |
|---|---|---|
| [[P/E Ratio]] ([[Price-to-earnings ratio|price-to-earnings]]) | $\frac{\text{Price per share}}{\text{EPS}}$ | How much investors pay for each dollar of earnings |
| [[P/B Ratio]] ([[Price-to-book ratio|price-to-book]]) | $\frac{\text{Price per share}}{\text{Book Value per share}}$ | How much investors pay relative to the company's accounting net worth |
| [[P/S Ratio]] (Price-to-Sales) | $\frac{\text{Price per share}}{\text{Sales per share}}$ | Useful for companies with no earnings yet |
| [[EV/EBITDA]] | $\frac{\text{[[Enterprise value|enterprise value]]}}{\text{EBITDA}}$ | Capital-structure-neutral comparison of operating value |

### Head-to-Head Comparison

| Feature | Absolute Models | Relative Models |
|---|---|---|
| **Approach** | Build value from fundamentals | Compare to peers |
| **Output** | Dollar value (e.g., "This stock is worth $45") | Ratio (e.g., "This stock's P/E is 15 vs. industry average of 20") |
| **Strength** | Theoretically rigorous — based on [[Present Value]] principles | Easy to compute, intuitive, reflects current market sentiment |
| **Weakness** | Highly sensitive to input assumptions (growth rate, discount rate) | Entire peer group could be over/undervalued; tells you *relative* cheapness, not *absolute* value |
| **Example** | [[Dividend discount model|DDM]]: $V_0 = \frac{D_1}{r - g}$ | [[P/E Ratio]]: If peer average P/E = 20 and this stock has P/E = 12, it *may* be undervalued |

> **Real-World Example:** During the [[Dot-Com Bubble]] (1999-2000), [[Relative valuation models|relative valuation]] was misleading. If you compared a tech stock's [[P/E Ratio]] to other tech stocks, it might have looked "fairly valued" — but the *entire sector* was wildly overpriced. An [[Absolute Valuation Models|absolute model]] like [[Free Cash Flow Valuation|DCF]] would have shown that many of these companies had negative cash flows and no path to profitability.

---

## LOS 17.g — [[Sum-of-the-parts valuation]] and [[Conglomerate discount]]

### Sum-of-the-Parts Valuation

[[Sum-of-the-parts valuation]] (also called [[Breakup value]] or [[Private market value]]) is a technique where you **value each division or business line of a company separately**, then add them up.

**Why do this?** Because a [[Conglomerate]] — a company that operates in multiple unrelated industries — might have divisions with very different risk profiles, growth rates, and appropriate [[Multiples]]. Valuing them as one blob would be imprecise.

> **Analogy:** Imagine a holding company that owns both a fast-food chain and a software company. The fast-food business might deserve a [[P/E Ratio]] of 15 (slow, stable growth), while the software business might deserve a P/E of 30 (high growth). If you applied a single P/E of 22 to the whole company, you'd be undervaluing the software business and overvaluing the fast-food business.

> **Real-World Example:** General Electric (GE) operated in aviation, healthcare, power, and financial services. Analysts often valued each division separately using industry-specific [[Multiples]], then summed them up. In 2021, GE announced it would actually *break up* into three separate companies — essentially agreeing that the sum-of-the-parts was worth more than the whole.

### Conglomerate Discount

The [[Conglomerate discount]] is the amount by which a [[Conglomerate|conglomerate's]] [[Market Price]] falls *below* its [[Sum-of-the-parts valuation|sum-of-the-parts value]].

$$\text{Conglomerate Discount} = \text{Sum-of-the-Parts Value} - \text{Market Value}$$

**Why would the market discount a conglomerate?** Three explanations:

| Explanation | What It Means | Example |
|---|---|---|
| **Internal Capital Inefficiency** | Management allocates money to underperforming divisions instead of returning it to shareholders | A profitable tech division subsidizes a money-losing retail division |
| **Endogenous (Internal) Factors** | Company pursued unrelated acquisitions to hide poor core performance | A struggling manufacturer buys a random services company to distract from falling margins |
| **Research Measurement Errors** | Maybe the discount doesn't really exist — it's just hard to measure accurately | Difficulty in assigning correct [[Multiples]] to each division creates an *apparent* discount |

> **Real-World Example:** When United Technologies merged with Raytheon in 2020, it simultaneously *spun off* its Carrier (HVAC) and Otis (elevators) divisions. The market had been applying a [[Conglomerate discount]] — once the businesses were separated, the combined market value of all three entities exceeded what United Technologies had been trading at as a whole.

---

## LOS 17.h — Choosing the Right [[Valuation Model]]

![[Valuation-Model-Selection.excalidraw]]

There is no single "best" valuation model. The right choice depends on **three broad criteria**:

### The Three Criteria

```
┌─────────────────────────────────────────────────────────┐
│           CHOOSING A VALUATION MODEL                    │
├──────────────────┬──────────────────┬───────────────────┤
│  1. Does the     │  2. Is the data  │  3. Does it fit   │
│  model FIT the   │  AVAILABLE and   │  the PURPOSE of   │
│  company?        │  RELIABLE?       │  the analysis?    │
├──────────────────┼──────────────────┼───────────────────┤
│ • Does it pay    │ • Can you get    │ • Are you buying  │
│   dividends?     │   clean financial│   a controlling   │
│ • Is earnings    │   data?          │   interest?       │
│   growth         │ • Are forecasts  │ • Is this for     │
│   predictable?   │   reasonable?    │   stock selection │
│ • Does it have   │ • Are comparable │   or an           │
│   significant    │   firms          │   acquisition?    │
│   intangible     │   available?     │                   │
│   assets?        │                  │                   │
└──────────────────┴──────────────────┴───────────────────┘
```

### Decision Guide: Which Model When?

| Company Characteristic | Best Model(s) | Why |
|---|---|---|
| Pays stable, predictable [[Dividends]] | [[Dividend discount model|DDM]] | The model directly values what shareholders receive |
| Doesn't pay dividends but has positive [[Free cash flow]] | [[Free Cash Flow Valuation|FCF]] | Captures all cash available to shareholders, not just what's paid out |
| Negative [[Free cash flow]], volatile earnings | [[Residual Income Valuation|Residual Income]] | Anchors on [[Book value]] plus excess earnings; less sensitive to volatile cash flows |
| Heavy tangible assets (oil, mining, real estate) | [[Asset-based valuation]] | Value is primarily in the assets, not in the earnings stream |
| Acquiring a controlling interest | [[Free Cash Flow Valuation|FCF]] (preferred over DDM) | A controlling buyer can *change* the [[Dividend policy]], so DDM based on historical dividends is misleading |
| Quick comparison across peers | [[Relative valuation models|Multiples]] ([[P/E Ratio|P/E]], [[EV/EBITDA]]) | Fast, intuitive, and reflects current market sentiment |

### Important Principle: Use Multiple Models

The textbook makes a key point: **you don't have to pick just one model**. Smart analysts use multiple models and compare the results. If a [[Dividend discount model|DDM]] says the stock is worth $50 and a [[Free Cash Flow Valuation|DCF]] says $45, but a [[Relative valuation models|relative valuation]] says $60, the differences reveal which assumptions are driving value — and where the analyst's uncertainty lies.

> **Real-World Example:** When an investment bank is advising on a major acquisition, the pitch book will typically include a "football field" chart showing the valuation range from multiple methods — DDM, DCF, comparable companies, precedent transactions. The buyer uses this to triangulate a reasonable offer price.

---

## Putting It All Together — The Valuation Process

Here's how all these concepts connect in practice:

```
Step 1: Understand the Industry
    │   → Porter's Five Forces
    │   → Competitive strategy (cost, differentiation, focus)
    ▼
Step 2: Analyze the Company's Financials
    │   → Quality of earnings check
    │   → Warning signs of poor reporting
    ▼
Step 3: Choose the Right Valuation Approach
    │   → Absolute vs. Relative?
    │   → Which specific model fits?
    │   → Going concern or liquidation?
    ▼
Step 4: Build the Model and Estimate Intrinsic Value
    │   → Apply DDM, FCF, RI, multiples, etc.
    ▼
Step 5: Compare IV to Market Price
    │   → IV > Price → Undervalued → BUY
    │   → IV < Price → Overvalued → SELL
    │   → IV ≈ Price → Fairly Valued → HOLD
    ▼
Step 6: Acknowledge Uncertainty
        → Your IV_analyst ≠ IV_actual
        → Use multiple models to cross-check
        → Sensitivity analysis on key inputs
```

---

## Practice Problem — Walkthrough

> **Question:** Sun Pharma, a pharmaceutical company in Sri Lanka, is evaluating acquiring Island Cookware, a cooking utensil manufacturer. Sun Pharma's CEO believes the company's distribution network could add value to Island Cookware. What is the most appropriate [[Definition of value|definition of value]] for this [[Acquisition|acquisition]]?

**Step 1: Identify the context.**
This is an [[Mergers and Acquisitions|acquisition]] by a strategic buyer. Sun Pharma isn't just buying Island Cookware at arm's length — it specifically sees [[Synergies]] (its distribution network can boost Island Cookware's sales).

**Step 2: Match to the [[Definition of value|definition of value]].**

| Definition | Applicable Here? | Why / Why Not |
|---|---|---|
| [[Intrinsic value]] | No | This is a standalone value — doesn't account for buyer-specific synergies |
| [[Fair market value]] | No | This assumes generic willing buyer/seller — misses the distribution synergy |
| [[Investment value]] | **Yes** | This captures the value *to Sun Pharma specifically*, including the synergies from its distribution network |
| [[Liquidation value]] | No | Sun Pharma plans to operate Island Cookware, not shut it down |

**Answer: [[Investment value]]** — because it incorporates the additional value from buyer-specific [[Synergies]].

**Follow-up:** When the market hears Sun Pharma (a pharma company) bought Island Cookware (a cookware company), the stock drops. Why? This is the [[Conglomerate discount]] in action. Investors worry about a pharma company entering an unrelated business — it smells like poor capital allocation ([[Internal Capital Inefficiency]]) and could signal management is trying to hide problems in the core business ([[Endogenous Factors]]).

---

## Key Terms Glossary

| Term | Definition |
|---|---|
| [[Valuation]] | The process of determining the value of an asset |
| [[Intrinsic value]] | The "true" value of an asset based on complete understanding of its characteristics |
| [[Market Price]] | The price at which a security currently trades in the market |
| [[Mispricing]] | When market price differs from [[Intrinsic value|intrinsic value]] |
| [[Valuation Error]] | The difference between an analyst's estimate of IV and the actual IV |
| [[Going Concern Assumption]] | The assumption that a company will continue operating as a business |
| [[Liquidation value]] | What assets would fetch if sold separately, net of [[Liabilities|liabilities]] |
| [[Orderly liquidation value]] | [[Liquidation|Liquidation]]on value|[[Liquidation|Liquidation]] value]] when assets are sold over time (not a fire sale) |
| [[Fair market value]] | Price agreed upon by willing, informed, and able buyer and seller |
| [[Investment value]] | Value to a specific buyer, including synergies |
| [[Fair value]] | Concept used in financial reporting; similar to [[Fair market value|fair market value]]ue|market value]] |
| [[Porter's Five Forces]] | Framework analyzing industry competitiveness |
| [[Quality of Earnings]] | How accurately financial statements reflect true economic performance |
| [[Absolute Valuation Models]] | Models that estimate IV based on the asset's own [[Fundamentals|fundamentals]] |
| [[Relative valuation models]] | Models that estimate value by comparison to similar assets |
| [[Sum-of-the-parts valuation]] | Valuing each division separately and adding them up |
| [[Conglomerate discount]] | [[Market value|Market value]] below sum-of-the-parts value for diversified firms |
| [[Breakup value]] | Another name for sum-of-the-parts value |
| [[Synergies]] | Value created by combining two businesses that wouldn't exist separately |

---

## Exam Tips

1. **[[Mispricing|Mispricing]] formula** — Know the two components: true mispricing + valuation error. The exam loves asking "which is the *least likely* explanation for a difference between estimated IV and market price."

2. **Going concern vs. [[Liquidation|liquidation]]** — If the question says "the company cannot be assumed to continue operating," the answer is [[Liquidation value]]. Every other model (DDM, FCF, RI) assumes going concern.

3. **[[Investment value|Investment value]] vs. [[Intrinsic value|intrinsic value]]** — If the question involves an *[[Acquisition|acquisition]] with synergies*, the answer is [[Investment value]]. If it's a regular equity analyst picking stocks, the answer is [[Intrinsic value]].

4. **Absolute vs. relative** — The [[P/E Ratio|P/E multiple]] is the classic example of a *relative* model. If the question asks "which is least likely an absolute model?" look for a multiple-based answer.

5. **[[Conglomerate discount|Conglomerate discount]]** — Know all three explanations (capital inefficiency, endogenous factors, measurement error). The exam tests whether you can identify *why* a conglomerate might trade at a discount.

---

*Next: [[Discounted Dividend Valuation]] (Reading 18) →*
