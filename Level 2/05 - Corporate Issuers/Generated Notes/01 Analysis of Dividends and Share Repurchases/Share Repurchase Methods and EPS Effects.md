---
title: "Share Repurchase Methods and EPS Effects"
subject: "Corporate Issuers"
tags: [CFA-L2, corporate-issuers, share-repurchases, payout-policy, eps]
aliases:
  - Share repurchase methods
  - Buyback EPS effect
  - Debt-financed repurchase
  - Open market repurchase
---

# Share Repurchase Methods and EPS Effects

A [[share repurchase]] is a payout method where the company returns cash by buying back its own shares. The important exam idea is that repurchases change both the **share count** and sometimes the **earnings numerator**, so they can mechanically change [[earnings per share]] without necessarily creating value.

Do not let EPS optics fool you. A buyback can raise EPS simply by reducing shares outstanding, while also increasing leverage and risk.

## Repurchase Methods

| Method | How it works | Main feature | Exam angle |
|---|---|---|---|
| Open market repurchase | Company buys shares in the market over time | Most common and flexible | Announcement is not a binding commitment |
| Fixed-price tender offer | Company offers to buy a set number of shares at a fixed premium | Fast; premium attracts sellers | Usually above market price |
| Dutch auction tender offer | Shareholders submit quantities and acceptable prices within a range | Clearing price paid to accepted sellers | Can be cheaper than fixed-price tender |
| Direct negotiation | Company buys from a specific large shareholder | Customized block transaction | May involve greenmail or liquidity-motivated discount |

### Open market repurchase

This is the most common method because it gives management flexibility. The firm can announce an authorization and then buy shares only when conditions are attractive.

Exam trap: an open market authorization is not the same as a declared dividend. The firm is generally not legally required to complete the full buyback.

### Fixed-price tender offer

The company offers to buy a specified number of shares at a fixed price, usually above the current market price. This is faster than open market repurchases but often requires paying a premium.

### Dutch auction tender offer

The company specifies a price range. Shareholders indicate how many shares they will sell and at what price. The company chooses the lowest price that allows it to buy the desired number of shares, and accepted shareholders receive that clearing price.

### Direct negotiation

The company negotiates directly with a large shareholder. The price may be above market if the firm is trying to remove a hostile or activist block, or below market if the seller needs liquidity.

## EPS Effect

The post-repurchase EPS formula is:

$$
\text{EPS}_{\text{after}} =
\frac{\text{Net income} - \text{After-tax cost of funds}}{\text{Shares outstanding after repurchase}}
$$

The denominator always falls. The numerator depends on how the repurchase is financed.

## Surplus Cash Repurchase

If the firm uses excess cash, the cost is the after-tax interest income the firm gives up by spending the cash.

Mechanism:

1. Cash decreases.
2. Equity decreases.
3. Shares outstanding decrease.
4. Interest income may decrease.
5. EPS may increase if the denominator effect is larger than the lost income effect.

If the cash was truly surplus and earning a low after-tax return, EPS usually rises.

## Debt-Financed Repurchase

If the firm issues debt to repurchase shares, net income falls because of after-tax interest expense:

$$
\text{After-tax interest cost} = \text{Debt issued} \times r_d \times (1-t)
$$

The key decision rule compares:

$$
\text{After-tax cost of debt} \quad \text{vs.} \quad \text{Earnings yield}
$$

Where:

$$
\text{Earnings yield} = \frac{\text{EPS}}{\text{Share price}} = \frac{E}{P}
$$

| Condition | EPS effect |
|---|---|
| After-tax cost of debt < earnings yield | EPS increases |
| After-tax cost of debt = earnings yield | EPS unchanged |
| After-tax cost of debt > earnings yield | EPS decreases |

### Why the rule works

When the company buys back one share at price \(P\), it removes \(EPS\) from the denominator's share base. The earnings yield \(EPS/P\) is the income yield represented by the repurchased share.

If the debt used to buy that share costs less than the earnings yield, the buyback is accretive to EPS. If the debt costs more, it is dilutive to EPS.

## Worked Example: Debt-Financed Repurchase

A company has:

- Net income: \$6.6 million
- Shares outstanding: 2.2 million
- Share price: \$60
- Debt-financed repurchase: \$12 million
- Shares repurchased: 200,000

Current EPS:

$$
\text{EPS}_0 = \frac{6.6}{2.2} = \$3.00
$$

Earnings yield:

$$
\frac{E}{P} = \frac{3.00}{60.00} = 5.0\%
$$

### Scenario 1: after-tax cost of debt is 5%

After-tax interest:

$$
12{,}000{,}000 \times 0.05 = 600{,}000
$$

New EPS:

$$
\text{EPS}_1 = \frac{6{,}600{,}000 - 600{,}000}{2{,}200{,}000 - 200{,}000}
= \frac{6{,}000{,}000}{2{,}000{,}000}
= \$3.00
$$

EPS is unchanged because the after-tax cost of debt equals the earnings yield.

### Scenario 2: after-tax cost of debt is 6%

After-tax interest:

$$
12{,}000{,}000 \times 0.06 = 720{,}000
$$

New EPS:

$$
\text{EPS}_1 =
\frac{6{,}600{,}000 - 720{,}000}{2{,}000{,}000}
= \frac{5{,}880{,}000}{2{,}000{,}000}
= \$2.94
$$

EPS decreases because the after-tax cost of debt exceeds the earnings yield.

## Book Value Per Share Effect

A repurchase reduces total equity by the cash spent and reduces shares outstanding.

$$
\text{BVPS}_{\text{after}} =
\frac{\text{Total equity} - \text{Repurchase amount}}{\text{Shares before} - \text{Shares repurchased}}
$$

Decision rule:

| Repurchase price vs original BVPS | BVPS effect |
|---|---|
| Repurchase price > original BVPS | BVPS decreases |
| Repurchase price = original BVPS | BVPS unchanged |
| Repurchase price < original BVPS | BVPS increases |

### Worked Example: BVPS

A company has:

- Book value of equity: \$100 million
- Shares outstanding: 10 million
- Share price: \$20
- Repurchase amount: \$5 million

Current BVPS:

$$
\text{BVPS}_0 = \frac{100{,}000{,}000}{10{,}000{,}000} = \$10
$$

Shares repurchased:

$$
\frac{5{,}000{,}000}{20} = 250{,}000
$$

New BVPS:

$$
\text{BVPS}_1 =
\frac{100{,}000{,}000 - 5{,}000{,}000}{10{,}000{,}000 - 250{,}000}
= \frac{95{,}000{,}000}{9{,}750{,}000}
= \$9.74
$$

BVPS decreases because the firm repurchased shares at \$20, which is above the original BVPS of \$10.

## Value Creation vs EPS Accretion

An EPS increase does not automatically mean shareholder wealth increased.

Debt-financed repurchases can raise EPS while also increasing:

- Financial leverage.
- Interest obligations.
- Default risk.
- The required return on equity.
- The cost of financial distress.

Under [[Modigliani-Miller]] assumptions with no taxes, no transaction costs, and no signaling effects, a cash dividend and an equal-value repurchase are economically equivalent. Real-world differences arise because of taxes, flexibility, signaling, agency costs, and investor preferences.

## Exam Traps

- **Use after-tax cost of debt**, not pretax cost, when testing EPS accretion for a debt-financed repurchase.
- **EPS accretion is not value creation.** Leverage can increase EPS and risk at the same time.
- **Open market buyback authorizations are flexible.** The company does not have to complete the announced amount.
- **BVPS depends on repurchase price vs pre-repurchase BVPS.** Do not compare repurchase price to market value of equity.
- **Repurchases reduce cash and equity.** Leverage ratios usually increase.
- **Tender offers are faster but less flexible than open market repurchases.**

## Memory Hook

**EPS asks: what did we remove from the denominator and what did financing cost the numerator?**

For debt-financed buybacks, compare **after-tax debt cost** with **earnings yield**.
