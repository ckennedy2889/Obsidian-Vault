---
title: Rolling Down the Yield Curve
subject: Fixed Income
tags: [CFA-L2, FixedIncome, TermStructure, ActiveManagement]
aliases: [riding the yield curve, rolling down the curve, roll-down strategy, yield curve roll down]
---

# Rolling Down the Yield Curve

## The Real-World Analogy

Rolling down the yield curve is like buying a ticket for a long slide.

If the slide slopes downward as you move closer to maturity, the bond may be priced using lower yields later. Lower yields mean higher prices, so the investor can earn a capital gain in addition to coupon income.

## Definition

Rolling down the yield curve is an active bond strategy in which the manager buys a bond with a maturity longer than the investment horizon and sells it before maturity after it has "rolled down" to a shorter point on the yield curve.

The strategy works best when:

```text
Yield curve is upward sloping
and
Yield curve does not shift upward enough to offset roll-down gains
```

## Mechanism

```text
Buy longer-maturity bond
  |
  v
Hold as it ages
  |
  v
Bond has shorter remaining maturity
  |
  v
If curve is upward sloping, shorter maturity has lower yield
  |
  v
Bond price rises
  |
  v
Investor earns coupon income + roll-down price gain
```

## Why Upward Slope Matters

With an upward-sloping spot curve:

```text
Longer maturity -> higher yield
Shorter maturity -> lower yield
```

If the curve stays unchanged, a bond purchased at a longer maturity is later valued at a lower yield when its remaining maturity is shorter.

Because bond prices and yields move inversely:

```text
Lower valuation yield -> higher bond price
```

## Active Management Link

The strategy depends on a view that future spot rates will be lower than current forward rates imply.

```text
Future spot rates < current forwards
  |
  v
Market is discounting future cash flows too heavily
  |
  v
Bonds are undervalued
  |
  v
Longer maturity exposure can outperform
```

If forward rates are realized exactly as future spot rates, then active maturity bets should not add value.

## Main Risk

The main risk is that yields rise.

```text
Spot rates rise
  |
  v
Price decline from higher yields
  |
  v
Roll-down gain may be offset or overwhelmed
```

Leveraged roll-down strategies are especially vulnerable to rising rates.

## Exam Traps

| Trap | Correction |
|---|---|
| Thinking roll-down works best on a downward-sloping curve | It is most naturally attractive on an upward-sloping curve. |
| Ignoring curve shifts | The strategy assumes the curve stays stable or moves favorably. |
| Confusing roll-down with maturity matching | Roll-down uses bonds longer than the investor's horizon. |
| Forgetting forward-rate implication | If forward rates become future spot rates, active roll-down should not generate excess return. |
| Ignoring leverage risk | Borrowing short and buying long magnifies losses if rates rise. |

## Memory Hook

```text
Upward curve + aging bond + stable yields = price rolls up as maturity rolls down.
```

## Related Concepts

- [[Par vs Spot vs Forward Rates]]
- [[Term Structure Theories]]
- [[Yield curve]]
- [[Spot rate]]
- [[Forward rate]]
- [[Active bond portfolio management]]
