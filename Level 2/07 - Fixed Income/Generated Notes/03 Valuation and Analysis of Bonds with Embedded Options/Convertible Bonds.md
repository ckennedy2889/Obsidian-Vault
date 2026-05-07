---
title: Convertible Bonds
subject: Fixed Income
tags: [CFA-L2, FixedIncome, ConvertibleBonds, EmbeddedOptions, CreditRisk]
aliases: [convertible bond, conversion value, straight value, minimum value of convertible bond, market conversion price, conversion premium, busted convertible, common stock equivalent]
---

# Convertible Bonds

## The Real-World Analogy

A [[Convertible bond]] is like buying a bond with a ticket attached.

The bond part says:

```text
You receive coupons.
You expect principal repayment.
You have credit and interest-rate exposure.
```

The ticket says:

```text
If the issuer's stock does well, you can exchange the bond for shares.
```

So a convertible bond is not just "a bond that might become stock." It is a package:

```text
Convertible bond = straight bond + investor-owned call option on the issuer's stock
```

The investor accepts a lower coupon than a comparable straight bond because the conversion option has value. The issuer gets cheaper financing, but if conversion happens, existing shareholders face dilution.

## Plain-English Definition

A convertible bond gives the bondholder the right to convert the bond into a fixed number of the issuer's common shares during a specified [[Conversion period]].

Key terms:

| Term | Meaning |
|---|---|
| [[Conversion ratio]] | Number of common shares received for each bond converted |
| [[Conversion price]] | Effective price per share at which the bond converts |
| [[Conversion period]] | Time window during which conversion is allowed |
| [[Conversion value]] | Current value of the shares received if conversion happens now |
| Straight value / investment value | Value of the same bond without the conversion option |

If a USD 1,000 par convertible has a conversion ratio of 20, the investor can convert one bond into 20 shares.

The conversion price is:

$$
\text{Conversion price} =
\frac{\text{Bond par or issue price}}{\text{Conversion ratio}}
$$

For the USD 1,000 bond with a conversion ratio of 20:

$$
\text{Conversion price} = \frac{1{,}000}{20} = 50
$$

The stock must rise above $50 before immediate conversion starts looking attractive on a pure share-value basis.

## Why CFA Tests This

CFA likes convertibles because they force you to think in layers:

```text
Bond floor
  +
Equity upside
  -
Issuer call risk
  +
Investor put protection, if any
```

They also test whether you can separate similar-sounding terms:

```text
Conversion ratio      = shares received
Conversion price      = contractual price per share
Conversion value      = current shares received x current stock price
Market conversion price = convertible price / conversion ratio
```

Most mistakes come from collapsing those into one vague "conversion number."

## Core Value Components

### Conversion Value

The [[Conversion value]] is the value of the common shares the investor would receive if the bond were converted today.

$$
\boxed{
\text{Conversion value} =
\text{Current stock price} \times \text{Conversion ratio}
}
$$

If the stock trades at USD 35 and the conversion ratio is 25:

$$
\text{Conversion value} = 35 \times 25 = 875
$$

This means immediate conversion gives the investor shares worth USD 875.

### Straight Value

The straight value, also called investment value, is the value of the bond if it were not convertible.

Mechanically, it is the present value of coupons and principal discounted at the required return on a comparable option-free bond from the same issuer.

```text
Straight value = value of the debt piece alone
```

It changes with benchmark rates, credit spreads, coupon level, and maturity. It is not a permanent fixed floor.

### Minimum Value

The minimum value of a convertible bond is:

$$
\boxed{
\text{Minimum value} =
\max(\text{Straight value}, \text{Conversion value})
}
$$

Why? The investor should be able to choose the more valuable use of the security:

```text
If stock is weak -> keep it as a bond.
If stock is strong -> convert into shares.
```

If the convertible traded below conversion value, an arbitrageur could buy the bond, convert it, and sell the shares for more. If it traded below straight value, investors would be getting the bond component too cheaply, ignoring credit and market frictions.

The actual market price is usually above the minimum value because the conversion option still has time value.

## Market Analysis Metrics

### Market Conversion Price

The [[Market conversion price]] is the effective price per share an investor is paying if they buy the convertible and convert.

$$
\boxed{
\text{Market conversion price} =
\frac{\text{Market price of convertible}}{\text{Conversion ratio}}
}
$$

If the convertible trades at USD 985 and the conversion ratio is 25:

$$
\text{Market conversion price} = \frac{985}{25} = 39.40
$$

Interpretation: buying the convertible at USD 985 is economically similar to paying USD 39.40 per share for the stock, while also receiving bond-like downside protection.

### Market Conversion Premium Per Share

The market conversion premium per share is:

$$
\boxed{
\text{Market conversion premium per share}
= \text{Market conversion price} - \text{Current stock price}
}
$$

If the stock trades at USD 35:

$$
\text{Premium per share} = 39.40 - 35.00 = 4.40
$$

This premium is the extra amount per share the investor pays for accessing the stock through the convertible rather than buying the stock directly. The investor is willing to pay it because the convertible has a bond floor and coupons.

### Market Conversion Premium Ratio

The market conversion premium ratio expresses the premium as a percentage of the current stock price:

$$
\boxed{
\text{Market conversion premium ratio}
=
\frac{\text{Market conversion premium per share}}
{\text{Current stock price}}
}
$$

Using the same numbers:

$$
\text{Premium ratio} = \frac{4.40}{35.00} = 12.57\%
$$

### Premium Over Straight Value

The premium over straight value measures how far the convertible trades above its bond-only value:

$$
\boxed{
\text{Premium over straight value}
=
\frac{\text{Convertible price}}{\text{Straight value}} - 1
}
$$

If the convertible trades at USD 985 and straight value is USD 950:

$$
\text{Premium over straight value}
=
\frac{985}{950} - 1
= 3.68\%
$$

All else equal, a higher premium over straight value means the investor is paying more above the bond floor, so the downside cushion is thinner.

## Worked Numerical Example

Assume:

| Input | Value |
|---|---:|
| Convertible market price | USD 985 |
| Par value | USD 1,000 |
| Conversion ratio | 25 shares |
| Current stock price | USD 35 |
| Straight value | USD 950 |

### Step 1: Conversion Price

$$
\text{Conversion price}
= \frac{1{,}000}{25}
= 40
$$

The bond converts at an effective contractual price of USD 40 per share.

### Step 2: Conversion Value

$$
\text{Conversion value}
= 35 \times 25
= 875
$$

Immediate conversion gives shares worth USD 875.

### Step 3: Minimum Value

$$
\text{Minimum value}
= \max(950,875)
= 950
$$

The straight value is the binding floor because the stock is below the conversion price.

### Step 4: Market Conversion Price

$$
\text{Market conversion price}
= \frac{985}{25}
= 39.40
$$

The investor is effectively paying USD 39.40 per share through the convertible.

### Step 5: Market Conversion Premium Per Share

$$
\text{Premium per share}
= 39.40 - 35.00
= 4.40
$$

### Step 6: Market Conversion Premium Ratio

$$
\text{Premium ratio}
= \frac{4.40}{35.00}
= 12.57\%
$$

### Step 7: Premium Over Straight Value

$$
\text{Premium over straight value}
= \frac{985}{950} - 1
= 3.68\%
$$

Interpretation:

```text
The investor is paying above the straight bond value
because the conversion option has value,
but immediate conversion is not attractive yet
because conversion value is only USD 875.
```

## Arbitrage-Free Valuation

For a noncallable, nonputable convertible:

$$
\boxed{
V_{\text{convertible}}
=
V_{\text{straight bond}}
+
V_{\text{call option on stock}}
}
$$

The investor owns the right to buy stock by surrendering the bond, so the stock call option adds value.

Many convertibles also include issuer calls and investor puts.

For a callable, putable convertible:

$$
\boxed{
V_{\text{convertible}}
=
V_{\text{straight bond}}
+
V_{\text{call option on stock}}
-
V_{\text{issuer call on bond}}
+
V_{\text{investor put on bond}}
}
$$

Why the signs?

| Feature | Who owns it? | Effect on investor value |
|---|---|---|
| Conversion option / call on stock | Investor | Adds value |
| Issuer call on bond | Issuer | Subtracts value |
| Investor put on bond | Investor | Adds value |

In an arbitrage-free tree, the model usually needs both an interest-rate process and a stock-price process. At each node, valuation respects the bond indenture:

```text
Continue holding
Convert into stock
Accept/avoid issuer call outcome
Exercise investor put, if available
```

The practical exam idea is less about building the full model and more about knowing which option belongs to whom and how it changes value.

## Behavior By Stock Price

Convertible behavior changes as the stock price moves relative to the conversion price.

| Stock price position | Name / behavior | Main drivers |
|---|---|---|
| Far below conversion price | Busted convertible / fixed-income equivalent | Credit spreads, interest rates, recovery expectations |
| Near conversion price | Hybrid security | Stock price, stock volatility, rates, credit spreads |
| Far above conversion price | Common stock equivalent | Stock price and conversion value dominate |

### Low Stock Price: Bond-Like

When the stock is far below the conversion price, the conversion option is out of the money. The convertible behaves mostly like a straight bond.

```text
Stock value too low
  |
  v
Conversion unattractive
  |
  v
Straight value dominates
```

This is the "busted convertible" case. CFA may ask which risk factor matters most. The answer is usually bond factors, such as credit spreads and benchmark rates, not stock price.

### High Stock Price: Equity-Like

When the stock is far above the conversion price, conversion value dominates. The convertible behaves more like common stock.

```text
Stock value high
  |
  v
Conversion attractive
  |
  v
Equity upside dominates
```

The bond floor matters less because the investor is focused on the valuable conversion option.

### Middle Zone: True Hybrid

Near the conversion price, both pieces matter. The convertible is sensitive to stock price, stock volatility, interest rates, credit spreads, and call/put features.

This is why convertibles can be awkward on exam questions: the answer depends on which zone the stock is in.

## Risk-Return Versus Straight Bond And Stock

| Compared with... | Convertible advantage | Convertible drawback |
|---|---|---|
| Straight bond | Equity upside if stock rises | Lower coupon / yield |
| Common stock | Less downside because of bond floor and coupons | Less upside because of conversion premium |

When the stock falls, the convertible usually loses less than the stock because the straight bond value provides a cushion. This assumes the issuer's credit does not collapse at the same time.

When the stock rises sharply, the convertible usually underperforms the stock because the investor paid a conversion premium and may be affected by issuer call provisions.

When the stock is stable, the convertible may outperform the stock because the bond pays coupons while the stock may pay lower dividends.

## Rule To Mechanism To Exam Implication

| Rule | Why it exists | Mechanism | Assumption / failure mode | Exam implication |
|---|---|---|---|---|
| Convertible = straight bond + stock call | Investor owns upside conversion right | Bond can be exchanged for shares | Issuer call or investor put modifies package | Know the signs in the valuation formula |
| Minimum value = max(straight value, conversion value) | Investor can use the bond in its better form | Hold as debt or convert to stock | Straight value moves with rates and credit spreads | Do not call the floor fixed |
| Market conversion price = convertible price / conversion ratio | Converts bond price into per-share equivalent | Shows effective stock price paid via bond | Not the same as contractual conversion price | Use market price in numerator |
| Conversion value = stock price x conversion ratio | Measures immediate conversion payoff | Shares received are worth current stock price | Ignores time value of option | Market price usually exceeds conversion value |
| Busted convertibles behave like bonds | Stock option far out of the money | Straight value dominates | Credit deterioration can break downside protection | Risk drivers are rates and credit spreads |
| Common stock equivalents behave like equity | Stock option deep in the money | Conversion value dominates | Issuer call may force conversion | Stock price dominates value |

## Common Exam Traps

| Trap | Correction |
|---|---|
| Saying the convertible's minimum value is the lower of straight value and conversion value | It is the higher of the two. |
| Treating straight value as fixed | Straight value changes with rates and credit spreads. |
| Confusing conversion price with market conversion price | Conversion price is contractual; market conversion price uses current convertible market price. |
| Confusing conversion ratio with conversion value | Ratio is number of shares; conversion value is share price times ratio. |
| Forgetting issuer calls reduce investor value | Issuer call can cap upside or force conversion. |
| Assuming convertibles always behave like stock | Busted convertibles behave more like bonds. |
| Assuming downside protection is perfect | Credit deterioration can reduce the straight value floor. |
| Ignoring dilution | Conversion can dilute existing shareholders. |

## Memory Hooks

```text
Convertible = bond floor + stock upside.
```

```text
Minimum value = max(straight, conversion).
```

```text
Low stock: bond brain.
High stock: stock brain.
Near conversion: hybrid brain.
```

## Related Concepts

- [[Convertible bond]]
- [[Conversion ratio]]
- [[Conversion price]]
- [[Conversion value]]
- [[Market conversion price]]
- [[Market conversion premium per share]]
- [[Market conversion premium ratio]]
- [[Straight value]]
- [[Embedded option]]
- [[Callable and Putable Bond Value Relationships]]
- [[Binomial Interest Rate Tree]]
- [[Credit spread]]
