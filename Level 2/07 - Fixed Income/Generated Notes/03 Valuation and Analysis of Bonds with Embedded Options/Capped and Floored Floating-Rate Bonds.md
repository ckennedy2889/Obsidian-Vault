---
title: Capped and Floored Floating-Rate Bonds
subject: Fixed Income
tags: [CFA-L2, FixedIncome, EmbeddedOptions, FloatingRateNotes, BinomialTree]
aliases: [capped floater, floored floater, capped floating-rate bond, floored floating-rate bond, capped and floored floaters]
---

# Capped and Floored Floating-Rate Bonds

## The Real-World Analogy

A [[Floating-rate note|floating-rate bond]] is like an adjustable-rate loan. The coupon resets as market rates move, so neither side is locked into one fixed coupon forever.

Now imagine the borrower and lender add guardrails:

```text
Cap   = borrower says, "I will pay floating, but never above this rate."
Floor = lender says, "I will accept floating, but never below this rate."
```

That is the whole intuition. A cap protects the issuer from rising rates. A floor protects the investor from falling rates.

## Plain-English Definition

A floating-rate bond, or floater, pays a coupon based on a [[Market reference rate|market reference rate]] plus a quoted margin:

$$
\text{Coupon rate} = \text{MRR} + \text{quoted margin}
$$

A **capped floater** has a maximum coupon rate:

$$
\text{Coupon rate} = \min(\text{floating formula rate}, \text{cap rate})
$$

A **floored floater** has a minimum coupon rate:

$$
\text{Coupon rate} = \max(\text{floating formula rate}, \text{floor rate})
$$

The cap or floor turns a plain floater into a floater with an [[Embedded option]].

## The Big Idea

The investor in a straight floater receives the benefit of rising reference rates and suffers from falling reference rates. Caps and floors change who gets that upside or downside protection.

| Instrument | What happens when rates rise? | What happens when rates fall? | Who benefits from the option? |
|---|---|---|---|
| Straight floater | Coupon rises | Coupon falls | No embedded cap/floor |
| Capped floater | Coupon rises only until the cap | Coupon falls normally | Issuer |
| Floored floater | Coupon rises normally | Coupon falls only until the floor | Investor |

The important CFA move is to view the bond as a package:

```text
Capped floater  = straight floater - cap owned by issuer
Floored floater = straight floater + floor owned by investor
```

## Value Formulas

### Capped Floater

The cap is valuable to the issuer because it limits future coupon payments when rates rise. From the investor's perspective, that cap is a liability because it takes away upside.

$$
\boxed{
V_{\text{capped floater}} = V_{\text{straight floater}} - V_{\text{embedded cap}}
}
$$

Mechanism:

```text
Reference rate rises above cap
  |
  v
Investor would like full floating coupon
  |
  v
Cap limits the coupon
  |
  v
Issuer saves money; investor loses upside
```

### Floored Floater

The floor is valuable to the investor because it guarantees a minimum coupon when rates fall.

$$
\boxed{
V_{\text{floored floater}} = V_{\text{straight floater}} + V_{\text{embedded floor}}
}
$$

Mechanism:

```text
Reference rate falls below floor
  |
  v
Investor would receive a low floating coupon
  |
  v
Floor raises the coupon to the minimum
  |
  v
Investor receives downside protection
```

## Why A Straight Floater Is Often Near Par

At a reset date, a plain floater usually prices close to par if the quoted margin equals the required margin for the issuer's credit risk.

Why? Because the coupon is about to reset to the market-required rate. If the bond will pay the current required floating coupon, there is little reason for it to trade far above or below par.

The exam version is often:

```text
Straight floater value = 100
```

But that is not magic. It relies on the reset-date logic and the assumption that the bond's quoted margin matches the market-required margin. If credit risk changes or the margin is no longer fair, the straight floater may not be exactly par.

## Valuation In A Binomial Interest Rate Tree

CFA values capped and floored floaters using [[Backward Induction]] in a [[Binomial Interest Rate Tree]].

The process:

1. Build the interest rate tree.
2. Determine the floating coupon at each node.
3. Apply the cap or floor if it is in the money.
4. Work backward by discounting expected future values at each node.

The coupon adjustment is the heart of the problem:

| Structure | Node rule |
|---|---|
| Capped floater | If floating coupon > cap, use cap. |
| Floored floater | If floating coupon < floor, use floor. |
| Option out of the money | Use the ordinary floating coupon. |

The backward induction value at a node has the same general structure as other tree valuation problems:

$$
V_t =
\frac{0.5(V_u + CF_u) + 0.5(V_d + CF_d)}
{1+r_t}
$$

The key is that $CF_u$ and $CF_d$ must reflect the cap or floor exercise rule.

## Worked Numerical Example

Assume a $100 par floater resets annually and the straight floater is worth $100$ at reset. Ignore credit spread complications.

### Capped Floater

Suppose the embedded cap is worth $0.80$.

Use:

$$
V_{\text{capped floater}} = V_{\text{straight floater}} - V_{\text{embedded cap}}
$$

Substitute:

$$
V_{\text{capped floater}} = 100.00 - 0.80 = 99.20
$$

The capped floater is worth less than the straight floater because the investor gave up the right to receive very high coupons.

### Floored Floater

Suppose the embedded floor is worth $0.65$.

Use:

$$
V_{\text{floored floater}} = V_{\text{straight floater}} + V_{\text{embedded floor}}
$$

Substitute:

$$
V_{\text{floored floater}} = 100.00 + 0.65 = 100.65
$$

The floored floater is worth more than the straight floater because the investor owns protection against low coupons.

## Volatility Effect

Higher interest rate volatility increases the value of both caps and floors. This is the same option logic as elsewhere: more volatility creates more chances the option finishes in the money.

But the bond price effect differs because the investor is on opposite sides of the option.

| Volatility rises | Embedded option value | Investor's bond value |
|---|---|---|
| Capped floater | Cap value rises | Capped floater value falls |
| Floored floater | Floor value rises | Floored floater value rises |

Why the asymmetry?

```text
Capped floater:
Investor is short the cap.
More valuable cap = bigger subtraction from straight floater value.

Floored floater:
Investor is long the floor.
More valuable floor = bigger addition to straight floater value.
```

## Rule To Mechanism To Exam Implication

| Rule | Why it exists | Mechanism | Assumption / failure mode | Exam implication |
|---|---|---|---|---|
| Capped floater value = straight floater - cap | Issuer owns the coupon ceiling | Coupon is limited when reference rates exceed cap | If cap is never reached, option value may be zero | Do not add cap value to the investor's bond value |
| Floored floater value = straight floater + floor | Investor owns the coupon floor | Coupon is raised when reference rates fall below floor | If floor is never reached, option value may be zero | Do not subtract floor value |
| Straight floater often equals par at reset | Coupon resets to current market rate | Required coupon and promised coupon line up | Credit spread or margin mismatch breaks par value | Check whether the question assumes fair margin / same credit quality |
| Higher volatility increases option value | Options benefit from dispersion | More possible in-the-money states | Direction depends on who owns option | Higher volatility lowers capped floater value but raises floored floater value |
| Use backward induction | Cash flows depend on future rate states | Adjust coupon at each node, then discount backward | Ignoring node exercise misprices embedded option | Treat it like other option-embedded bond problems |

## Common Exam Traps

| Trap | Correction |
|---|---|
| Thinking a cap helps the investor | A cap helps the issuer by limiting coupons paid. |
| Thinking a floor helps the issuer | A floor helps the investor by guaranteeing a minimum coupon. |
| Adding cap value to a capped floater | The investor is short the cap, so subtract it. |
| Subtracting floor value from a floored floater | The investor owns the floor, so add it. |
| Assuming every floater always equals par | It is near par at reset only if the quoted margin matches the required margin. |
| Forgetting out-of-the-money states | If the cap or floor is not triggered at a node, use the normal floating coupon. |
| Misreading reset timing | Coupon set in advance versus set in arrears changes which tree rate determines the payment. |
| Getting volatility direction backward | More volatility makes the embedded option more valuable; then ask who owns it. |

## Memory Hooks

```text
Cap caps investor upside.
Floor floors investor downside.
```

```text
Capped floater:
Issuer owns the cap -> investor subtracts it.
```

```text
Floored floater:
Investor owns the floor -> investor adds it.
```

## Related Concepts

- [[Floating-rate note]]
- [[Embedded option]]
- [[Callable and Putable Bond Value Relationships]]
- [[Option-Adjusted Spread]]
- [[Binomial Interest Rate Tree]]
- [[Backward Induction]]
- [[Effective Duration]]
- [[Discount margin]]
- [[Cap]]
- [[Floor]]
