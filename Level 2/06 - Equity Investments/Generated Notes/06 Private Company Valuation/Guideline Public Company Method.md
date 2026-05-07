---
title: "Guideline Public Company Method"
subject: "Equity Investments"
tags: [CFA-L2, equity-investments, private-company-valuation, market-approach]
aliases: ["GPCM", "Guideline public companies", "Public company method"]
---

# Guideline Public Company Method

The [[Guideline Public Company Method]] (GPCM) values a private company by asking, "What are comparable public companies worth, and how should we adjust those multiples for the private target?"

Imagine valuing a private electronics hardware company that supplies components into Apple's ecosystem. It has no traded share price, but public companies such as Apple, Microsoft, and Nvidia provide observable market data. GPCM borrows those public market multiples and adapts them to the private company.

In plain English:

```text
GPCM = use trading multiples from comparable public companies to value a private company.
```

## The Basic Process

1. Select comparable public companies.
2. Calculate relevant multiples, often [[Enterprise Value]] multiples such as EV/Sales or EV/EBITDA.
3. Adjust for differences in size, risk, growth, profitability, leverage, and life-cycle stage.
4. Apply the selected multiple to the private company's normalized metric.
5. Adjust for control and marketability if the valuation basis requires it.

## Why The Method Exists

Private companies do not trade continuously. Public companies do. GPCM uses public market prices as evidence of what investors currently pay for similar businesses.

The method is useful because it is market-grounded, but it is dangerous if the public companies are not truly comparable.

## Value Basis

Public shares normally trade in small minority blocks. That means GPCM usually starts from a:

```text
marketable minority value
```

That phrase matters:

| Word | Meaning |
|---|---|
| Marketable | Public shares can be sold in an active market |
| Minority | Public share trades usually do not transfer control |

Therefore:

- If valuing a controlling interest, a [[Control premium]] may be needed.
- If valuing a nonmarketable private interest, a [[Discount for Lack of Marketability]] may be needed.
- If valuing a minority interest, do not automatically apply [[DLOC]], because public trading multiples are already minority-basis.

## Public Peer Example

Use Apple, Microsoft, and Nvidia as a simplified public comparable set. A recent data snapshot gave:

| Company | Approx. market value | Debt | Cash and investments | Revenue | Approx. EV/Sales |
|---|---:|---:|---:|---:|---:|
| Apple | $\$4,251.2$B | $\$111.5$B | $\$132.4$B | $\$416.2$B | 10.17x |
| Microsoft | $\$3,075.6$B | $\$46.2$B | $\$115.2$B | $\$281.7$B | 10.67x |
| Nvidia | $\$5,044.7$B | $\$9.5$B | $\$32.9$B | $\$215.9$B | 23.20x |

Nvidia's multiple is much higher, so a median may be more defensible than a simple average.

Sorted EV/Sales:

```text
10.17x, 10.67x, 23.20x
```

Median EV/Sales:

$$
10.67x
$$

Suppose the private company has normalized revenue of $\$1.2$ billion.

$$
\text{Enterprise value} =
1.2 \times 10.67
= 12.80
$$

So the GPCM indication is approximately $\$12.8$ billion before any control or marketability adjustment.

## Adjustments

| Difference | Typical adjustment logic |
|---|---|
| Private firm is smaller | Lower multiple |
| Private firm has higher customer concentration | Lower multiple |
| Private firm has faster growth | Higher multiple |
| Private firm has weaker margins | Lower multiple |
| Private firm has more leverage | Prefer EV multiples or adjust discount rate |
| Private firm has lower liquidity | Apply DLOM if valuing illiquid interest |

The exam often gives the adjustment directly. Your job is to identify whether the starting multiple is minority or control basis and whether marketability is embedded.

## Control Premium In GPCM

Because GPCM uses public trading prices, it usually reflects minority value. If the analyst is valuing a controlling interest, a control premium may be added:

$$
\text{Control value} =
\text{Minority marketable value} \times (1 + \text{Control premium})
$$

If the $\$12.8$ billion GPCM value is minority marketable and the appropriate control premium is 25%:

$$
\text{Control value} =
12.8 \times 1.25
= 16.0
$$

If the analyst is valuing a nonmarketable minority interest instead, do not add the control premium. Apply DLOM to the minority marketable value.

## Exam Traps

The first trap is applying DLOC to a GPCM minority value. Public trading multiples already reflect minority interests. If the target stake is also minority, there is no lack-of-control adjustment needed.

The second trap is blindly adding a control premium when public-company prices may already reflect takeover speculation. If an industry is "in play," public prices can already include some control value.

The third trap is using an outlier multiple without judgment. Nvidia's EV/Sales may be valid for Nvidia but too aggressive for a smaller private supplier with lower margins or weaker growth.

The fourth trap is using equity multiples when capital structures differ. EV multiples are often cleaner when leverage varies.

## Memory Hook

> [!tip] Memory Hook
> GPCM starts with public trading multiples: marketable, usually minority. Add control only if you need control; subtract marketability only if the target interest is illiquid.

## Related Concepts

- [[Guideline Transactions Method]]
- [[Discount for Lack of Marketability]]
- [[Discount for Lack of Control]]
- [[Enterprise Value Multiples and Comparable Valuation]]
- [[Private Company Valuation Framework]]
