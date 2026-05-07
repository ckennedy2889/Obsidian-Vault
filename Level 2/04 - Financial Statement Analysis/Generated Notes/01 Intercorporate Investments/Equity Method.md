---
title: Equity Method
subject: Financial Statement Analysis
tags: [CFA-L2, FSA, intercorporate-investments, equity-method, associates]
aliases: [Equity method, One-line consolidation, Investment in associates]
---

# Equity Method

## The Real-World Analogy

Imagine you own 30% of a restaurant chain. You do not control every daily decision, but you sit on the board and can influence strategy. You are not just a passive shareholder anymore, but you also do not control the company.

That middle ground is the [[Equity Method]].

The accounting mirrors that middle ground:

```text
Not passive enough for fair value through P&L.
Not controlled enough for full consolidation.
Use one-line consolidation.
```

## Plain-English Definition

The equity method is used when an investor has significant influence over an investee, usually presumed at 20% to 50% ownership.

Under the equity method, the investor reports:

| Financial statement | Reporting |
|---|---|
| Balance sheet | One noncurrent asset: investment in associate |
| Income statement | One line: share of investee net income, adjusted for excess amortization and unrealized profits |
| Cash flow statement | Dividends received are cash inflows but not income |

It is often called **one-line consolidation** because the investee's individual assets, liabilities, revenues, and expenses do not appear line by line.

## Core Formula

The investment account evolves as:

$$
\text{Ending investment}
=\text{Beginning investment}
+\text{Investor's share of investee NI}
-\text{Investor's share of dividends}
-\text{Excess amortization}
-\text{Impairment}
\pm\text{other adjustments}
$$

The income statement amount is:

$$
\text{Equity income}
=\text{Ownership \%}\times\text{Investee NI}
-\text{excess amortization}
-\text{unrealized profit adjustments}
$$

## Why Dividends Are Not Income

The biggest exam trap is dividends.

Under the equity method, dividends are **not** dividend income. They are treated as a return of capital.

Why? The investor already records its share of the investee's net income when the investee earns it. If dividends were also recorded as income, the investor would double count.

```text
Investee earns income -> investor records equity income.
Investee pays dividend -> investor reduces investment account.
```

## Worked Example

Company P buys 30% of Company S for 1,000.

During 20X6:

| Item | Company S |
|---|---:|
| Net income | 400 |
| Dividends | 100 |

Company P records equity income:

$$
400 \times 30\% = 120
$$

Company P receives dividends:

$$
100 \times 30\% = 30
$$

Ending carrying value:

$$
1{,}000+120-30=1{,}090
$$

Interpretation:

| Effect | Amount |
|---|---:|
| Income statement equity income | 120 |
| Cash dividend received | 30 |
| Ending investment carrying value | 1,090 |

## Excess Purchase Price Over Book Value

If the investor pays more than its share of the investee's book value, the excess is allocated to identifiable assets and liabilities based on fair values. Any remainder is goodwill.

Under the equity method, this allocation is not shown separately on the investee's statements. It is embedded inside the investor's one-line investment account.

If excess is allocated to depreciable assets, the investor recognizes extra depreciation or amortization by reducing equity income.

```text
Share of investee NI
  -
amortization of excess fair value
  =
reported equity income
```

## Analytical Implications

The equity method can make the investor look cleaner than full consolidation.

| Metric | Equity method effect |
|---|---|
| Revenue | Investee revenue is excluded |
| Expenses | Investee expenses are excluded |
| Assets | One investment line instead of investee assets |
| Liabilities | Investee debt is not reported line by line |
| Margins | Often higher because revenue is excluded but equity income is included below operating lines |
| Leverage | Often lower because investee debt is off the investor's balance sheet |
| Cash quality | Equity income can be non-cash if dividends are low |

Analyst reflex:

```text
Equity income may increase net income without bringing in cash.
Look at dividends received and investee debt.
```

## Upstream And Downstream Transactions

Profits on transactions between investor and investee are deferred until confirmed through sale to a third party.

| Transaction | Direction | Adjustment |
|---|---|---|
| Upstream | Investee sells to investor | Investor eliminates its ownership share of unconfirmed profit from equity income |
| Downstream | Investor sells to investee | Investor eliminates its ownership share of unconfirmed profit |

The exam usually gives ownership percentage and unsold inventory. Multiply:

$$
\text{unconfirmed profit}\times\text{ownership \%}
$$

## Exam Traps

| Trap | Correct reflex |
|---|---|
| Treating dividends as income | Dividends reduce the investment account |
| Forgetting excess amortization | Reduce equity income for amortization of fair value excess |
| Assuming 20%-50% is automatic | Significant influence is judgment-based |
| Ignoring investee debt | Equity method can hide leverage |
| Thinking fair value changes matter | Fair value changes are ignored unless fair value option applies |
| Assuming equity income is cash | Cash only arrives through dividends |

## Memory Hook

```text
Equity method:
Start with cost.
Add your share of earnings.
Subtract dividends.
Adjust for excess amortization and impairment.
```

## Related Concepts

- [[Acquisition Method]]
- [[Intercorporate Investments]]
- [[Significant influence]]
- [[Investment in associates]]
- [[Dividends]]
- [[Goodwill]]
- [[Impairment]]
- [[DuPont Analysis & ROE]]
- [[Cash Flow from Operations]]
