---
title: CDS Curve and Basis Trades
subject: Fixed Income
tags: [CFA-L2, FixedIncome, CDS, CreditCurve, BasisTrade]
aliases: [CDS curve trades, CDS-bond basis, basis trade, negative basis trade, CDS relative value]
---

# CDS Curve and Basis Trades

## CDS For Credit Exposure

A [[Credit Default Swap]] lets an investor isolate credit risk.

| Position | View / Use |
|---|---|
| Buy CDS protection | Hedge credit exposure or express bearish credit view |
| Sell CDS protection | Earn spread or express bullish credit view |

Buying protection is economically similar to shorting credit risk. Selling protection is economically similar to going long credit risk.

Important CDS index convention:

```text
Buying a single-name CDS = buying protection = short credit.
Buying a CDS index position can mean long credit exposure depending on the index contract convention.
```

Read the vignette language carefully.

## Credit Curve Views

CDS contracts trade at different maturities, creating a CDS credit curve.

Investors can express views on:

| View | Trade Intuition |
|---|---|
| Credit curve level widens | Buy protection broadly |
| Credit curve level tightens | Sell protection broadly |
| Curve steepens | Long protection at long maturities and short protection at short maturities |
| Curve flattens | Long protection at short maturities and short protection at long maturities |

The exact implementation depends on the maturities and notionals chosen.

## CDS-Bond Basis

The [[CDS-bond basis]] compares credit risk pricing in the CDS market and bond market.

$$
\boxed{
\text{Basis} = \text{CDS spread} - \text{Bond credit spread}
}
$$

The bond credit spread is often measured by the Z-spread or comparable spread measure.

## Positive And Negative Basis

| Basis | Meaning | Relative-Value Implication |
|---|---|---|
| Positive | CDS spread > bond spread | Protection is expensive relative to bond spread |
| Negative | CDS spread < bond spread | Protection is cheap relative to bond spread |

## Negative Basis Trade

A negative basis trade exploits:

```text
Bond spread > CDS spread
```

Trade:

```text
Buy the bond
Buy CDS protection
```

Net carry:

$$
\text{Net carry} \approx \text{Bond spread} - \text{CDS spread}
$$

Example:

| Input | Value |
|---|---:|
| Bond credit spread | 250 bps |
| CDS spread | 200 bps |

$$
\text{Basis} = 200 - 250 = -50 \text{ bps}
$$

The investor earns 250 bps from the bond spread and pays 200 bps for protection, leaving about 50 bps before funding, liquidity, and implementation costs.

## Why Basis Exists

The basis should be close to zero in a frictionless world, but it can persist because of:

| Cause | Mechanism |
|---|---|
| Funding costs | Bonds require cash funding; CDS is mostly unfunded/collateralized |
| Liquidity differences | Bond and CDS markets may have different liquidity |
| Cheapest-to-deliver option | CDS settlement may not match the exact bond held |
| Counterparty/collateral effects | CDS has counterparty and margin mechanics |
| Technical demand | Hedging/speculation can pressure one market more than another |
| Regulatory capital | Bonds and CDS may receive different capital treatment |

## Cross-Market Relative Value

CDS can be used to exploit valuation disparities among:

| Market | Example View |
|---|---|
| Bonds | Bond spread is too wide/narrow versus CDS |
| Loans | Loan and bond markets price same issuer credit differently |
| Equities | Equity view implies credit deterioration or improvement |
| Convertibles | Equity option and credit components may be mispriced |

Example:

```text
Expected leveraged buyout
  |
  v
Equity may rise from takeover premium
  |
  v
Credit may deteriorate from higher leverage
  |
  v
Buy stock and buy CDS protection
```

## Useful Exam Formulas

Approximate CDS buyer profit from spread widening:

$$
\text{Profit} \approx \Delta \text{CDS spread} \times \text{CDS duration} \times \text{Notional}
$$

Approximate upfront payment when fixed CDS coupon differs from market spread:

$$
\text{Upfront} \approx (\text{Market CDS spread} - \text{Fixed coupon}) \times \text{CDS duration} \times \text{Notional}
$$

Sign depends on whether the fixed coupon is above or below the market spread.

## Exam Traps

| Trap | Correction |
|---|---|
| Confusing CDS spread with bond spread | They are related but can diverge. |
| Forgetting basis sign | Basis = CDS spread minus bond spread. |
| Calling negative basis riskless | Funding, liquidity, CTD, and counterparty risks remain. |
| Thinking CDS only hedges bonds | CDS can express views without owning bonds. |
| Ignoring curve shape | CDS can trade level, steepness, and flattening views. |
| Using bond duration for CDS upfront/profit | Use CDS duration when the question gives it. |
| Missing index convention | Single-name CDS and CDS index trade language can differ. |

## Memory Hook

```text
CDS buy protection = short credit.
CDS sell protection = long credit.
Basis = CDS minus bond.
Negative basis = bond spread bigger than CDS spread.
```

## Related Concepts

- [[Credit Default Swap]]
- [[Term Structure of Credit Spreads]]
- [[Z-Spread]]
- [[Credit Migration Risk]]
- [[Convertible Bonds]]
- [[Basis trade]]
- [[Naked credit default swap]]
