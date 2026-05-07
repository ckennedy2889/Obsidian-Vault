---
title: Credit Default Swap
subject: Fixed Income
tags: [CFA-L2, fixed-income, credit-default-swap, cds, credit-risk, credit-derivatives, credit-spreads]
aliases: [credit default swap, credit default swap (CDS), CDS, single-name CDS, index CDS, credit protection]
---

# Credit Default Swap

## The Real-World Analogy

A [[Level 2/Generated Notes/07 - Fixed Income/Credit Default Swap]] is like buying fire insurance on someone else's building.

If the building burns down, the insurance seller pays you.

If the building does not burn down, you keep paying premiums and receive nothing.

For CDS:

```text
building = reference entity / reference obligation
fire = credit event
insurance premium = CDS spread / CDS coupon
insurance payout = compensation for credit loss
```

The analogy is helpful, but there is one huge finance twist:

```text
You can buy CDS protection even if you do not own the bond.
```

That is called a [[Naked credit default swap]].

So CDS can be used either as:

| Use | Meaning |
|---|---|
| Hedge | Protect a bond position you already own |
| Speculation | Bet that credit quality will improve or deteriorate |
| Relative-value trade | Exploit differences between bond, CDS, loan, equity, or index pricing |

## Plain-English Definition

A credit default swap is a derivative contract that transfers credit risk from one party to another.

The protection buyer pays periodic premiums.

The protection seller promises to compensate the buyer if a specified credit event occurs.

In simple terms:

```text
Protection buyer pays for insurance against default.
Protection seller collects premium and takes the default risk.
```

## CFA Definition

The CFA-style definition:

```text
A CDS is a credit derivative in which the protection buyer makes regular payments to the protection seller,
and the seller compensates the buyer if a credit event occurs.
```

The main contract terms are:

| Term | Meaning |
|---|---|
| [[Reference entity]] | The borrower whose credit risk is being traded |
| Reference obligation | The bond or loan used to define the contract |
| [[Notional amount]] | Face amount of credit protection |
| [[CDS spread]] / coupon | Periodic premium paid by the protection buyer |
| [[Credit event]] | Trigger event, such as bankruptcy, failure to pay, or restructuring |
| Maturity | Length of the CDS contract |
| Settlement method | Cash settlement or physical settlement |

## The Two Parties

CDS terminology is exam-dangerous because "buyer" and "seller" refer to protection, not credit exposure.

| Party | Pays / Receives | Credit View | Position |
|---|---|---|---|
| [[Credit protection buyer]] | Pays premium; receives payment after credit event | Bearish on credit / wants protection | Short credit risk |
| [[Credit protection seller]] | Receives premium; pays after credit event | Bullish on credit / willing to insure | Long credit risk |

Memory:

```text
Protection buyer = short the credit.
Protection seller = long the credit.
```

Why?

If the issuer's credit worsens, CDS spreads widen and default becomes more likely.

That helps the protection buyer because the insurance is now more valuable.

It hurts the protection seller because the seller has promised to pay if default occurs.

## The Two Legs

A CDS has two valuation legs.

| Leg | Cash Flow | Economic Meaning |
|---|---|---|
| [[Premium leg]] | Protection buyer pays periodic CDS coupon/spread | Cost of insurance |
| [[Protection leg]] | Protection seller pays if credit event occurs | Default-loss compensation |

At fair pricing:

$$
\text{PV(Premium leg)}=\text{PV(Protection leg)}
$$

That is exactly like insurance pricing:

```text
Fair premium = present value of expected claim payments.
```

The premium leg depends on survival because premium payments stop after default.

The protection leg depends on default probability and loss severity.

That is why [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]], [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]], [[Recovery rate]], and [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]] drive CDS pricing.

## CDS Spread Intuition

The CDS spread is the market price of credit protection.

A simple one-period approximation is:

$$
\text{CDS Spread} \approx \text{POD}\times \text{LGD\%}
$$

Where:

| Symbol | Meaning |
|---|---|
| POD | Probability of default |
| LGD% | Loss given default as a percentage of exposure |

Since:

$$
\text{LGD\%}=1-\text{Recovery Rate}
$$

We can also write:

$$
\text{CDS Spread} \approx \text{POD}\times(1-\text{Recovery Rate})
$$

Example:

| Input | Value |
|---|---:|
| Probability of default | 3.0% |
| Recovery rate | 50.0% |
| LGD | 50.0% |

Then:

$$
\text{CDS Spread}\approx0.03\times0.50=0.015=1.50\%=150\text{ bps}
$$

So:

```text
Higher default probability -> higher CDS spread.
Lower recovery rate -> higher CDS spread.
Higher loss given default -> higher CDS spread.
```

## Why Hazard Rate Matters

Most CDS contracts cover multiple periods.

The issuer might default in Year 1, Year 2, Year 3, and so on.

But default can happen only once.

So CDS pricing uses conditional default probabilities, or [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]].

The key relationship is:

$$
\text{POD}_t
=
\text{Hazard Rate}_t
\times
\text{Probability of survival to }t-1
$$

Why this matters:

```text
The protection seller's expected payout depends on when default happens.
The protection buyer's premium payments stop once default happens.
```

So hazard rate affects both legs:

| Leg | Hazard Rate Effect |
|---|---|
| Protection leg | Higher hazard rate increases expected default payment |
| Premium leg | Higher hazard rate reduces expected future premium payments because default stops the contract |

Exam trap:

```text
Hazard rate affects both the premium leg and the protection leg.
```

## Standardized Coupons and Upfront Payment

In theory, the CDS spread should be the periodic coupon.

In practice, standardized CDS contracts often use fixed coupons:

| Reference Type | Common Standard Coupon |
|---|---:|
| Investment grade | 1% / 100 bps |
| High yield | 5% / 500 bps |

The market-implied CDS spread may differ from the fixed coupon.

That difference is handled with an [[Upfront payment]].

Approximation:

$$
\text{Upfront Payment \%}
\approx
(\text{CDS Spread}-\text{CDS Coupon})\times \text{CDS Duration}
$$

For dollar amount:

$$
\text{Upfront Payment}
\approx
(\text{CDS Spread}-\text{CDS Coupon})\times \text{CDS Duration}\times \text{Notional}
$$

Important:

```text
Use CDS duration, not bond duration.
```

### Direction of Upfront Payment

| Situation | Who Pays Upfront? | Why |
|---|---|---|
| CDS spread > fixed coupon | Protection buyer pays seller | Buyer is paying too little ongoing premium |
| CDS spread < fixed coupon | Protection seller pays buyer | Buyer is paying too much ongoing premium |

## Worked Example: Upfront Payment

A 10-year high-yield CDS has:

| Input | Value |
|---|---:|
| CDS coupon | 5.0% |
| Market CDS spread | 3.5% |
| CDS duration | 7.0 |
| Notional | $10,000,000 |

Upfront payment percent:

$$
(0.035-0.050)\times7
=-0.105
=-10.5\%
$$

Dollar amount:

$$
-10.5\%\times \$10{,}000{,}000=-\$1{,}050{,}000
$$

The negative sign means the protection seller pays the protection buyer upfront.

Why?

The protection buyer is required to pay a 5% coupon even though the fair market spread is only 3.5%.

So the seller compensates the buyer upfront for paying an above-market ongoing coupon.

## Payoff After a Credit Event

If a credit event occurs, the protection buyer receives compensation for loss.

Cash settlement payoff:

$$
\text{Payoff}
=
\text{Notional}\times(1-\text{Recovery Rate})
$$

If the defaulted bond trades at 30% of par:

$$
\text{Recovery Rate}=30\%
$$

$$
\text{Payoff}= \text{Notional}\times70\%
$$

## Worked Example: Single-Name CDS Payoff

A protection buyer owns a $10 million senior CDS.

The reference entity defaults.

The cheapest-to-deliver senior bond trades at 25% of par.

Then:

$$
\text{Recovery Rate}=25\%
$$

$$
\text{Payoff}= \$10{,}000{,}000\times(1-0.25)
$$

$$
\text{Payoff}= \$7{,}500{,}000
$$

The [[Cheapest-to-deliver]] issue matters because CDS settlement is based on the deliverable obligation with the same seniority that produces the lowest delivery cost.

## Settlement: Physical vs Cash

After a credit event, settlement can occur in two broad ways.

| Settlement Type | What Happens |
|---|---|
| [[Physical settlement]] | Protection buyer delivers eligible debt; seller pays notional |
| Cash settlement | Seller pays notional minus market value/recovery value |

Cash settlement is often:

$$
\text{Cash Payment}=\text{Notional}\times(1-\text{Final Price})
$$

If final price is 40%:

$$
\text{Cash Payment}=60\%\times\text{Notional}
$$

Exam nuance:

```text
Cash settlement can be better if the buyer owns a bond worth more than the cheapest-to-deliver bond.
Physical settlement requires delivering an eligible obligation.
```

## Single-Name CDS

A [[Single-name CDS]] references one borrower.

It is used when the investor wants exposure to or protection against a specific issuer.

Example:

```text
Buy 5-year CDS protection on Company A.
```

The contract usually specifies:

| Parameter | Example |
|---|---|
| Reference entity | Company A |
| Seniority | Senior unsecured |
| Notional | $10 million |
| Maturity | 5 years |
| Coupon | 100 bps or 500 bps |
| Credit events | Bankruptcy, failure to pay, restructuring |

Single-name CDS is issuer-specific.

## Index CDS

An [[Index CDS]] references a basket of issuers.

Examples include CDX and iTraxx indexes.

The purpose is to trade broad credit exposure instead of one issuer.

Index CDS is useful when:

```text
You want to hedge many credit positions at once.
You want to express a macro view on credit spreads.
You want more liquidity than single-name CDS may provide.
```

## Worked Example: Index CDS Default

Suppose an index CDS has:

| Input | Value |
|---|---:|
| Total notional | $100,000,000 |
| Number of equally weighted entities | 125 |
| Defaulted entity recovery | 30% |

Notional per entity:

$$
\frac{\$100{,}000{,}000}{125}
=\$800{,}000
$$

Payoff for one default:

$$
\$800{,}000\times(1-0.30)
=\$560{,}000
$$

Remaining index notional:

$$
\$100{,}000{,}000-\$800{,}000
=\$99{,}200{,}000
$$

So the index continues after the default with reduced notional.

## Credit Correlation in Index CDS

[[Credit correlation]] matters for index CDS.

If default correlation among index constituents rises, the index CDS spread tends to rise.

Why?

```text
Highly correlated defaults mean many names may default together.
That makes protection more valuable.
Protection sellers demand more spread.
```

This matters especially for tranche CDS and structured credit.

## CDS Value After Inception

After a CDS is initiated, the reference entity's credit quality can change.

The CDS then has value to one side.

For the protection buyer:

$$
\text{Approx. Profit}
\approx
\Delta\text{CDS Spread}\times \text{CDS Duration}\times \text{Notional}
$$

If spreads widen:

```text
Protection buyer profits.
Protection seller loses.
```

If spreads narrow:

```text
Protection seller profits.
Protection buyer loses.
```

## Worked Example: Monetizing a CDS Gain

An investor buys protection at 200 bps.

Six months later, the CDS spread widens to 350 bps.

CDS duration is 5.

Notional is $10 million.

Spread change:

$$
350-200=150\text{ bps}=0.0150
$$

Approximate profit:

$$
0.0150\times5\times \$10{,}000{,}000
=\$750{,}000
$$

The protection buyer can monetize the gain by entering an offsetting transaction: sell protection with similar remaining terms at the now-higher spread.

## Hedging a Bond Position

Suppose a portfolio owns a corporate bond and is worried about default or spread widening.

The portfolio can buy CDS protection.

| Bond Position | CDS Hedge | Result |
|---|---|---|
| Long corporate bond | Buy CDS protection | Reduce credit risk |
| No bond position | Buy CDS protection | Speculate on credit deterioration |
| Wants more credit exposure | Sell CDS protection | Earn premium, take credit risk |

Buying CDS protection does not hedge every risk.

It hedges credit risk, not market-wide interest rate risk.

For rate risk, the manager needs duration hedges such as Treuries, futures, or swaps.

## Naked CDS

A [[Naked credit default swap]] is a CDS position without owning the underlying credit exposure.

Example:

```text
Investor buys CDS protection on Company A but owns no Company A bonds.
```

This is a pure bearish credit position.

If Company A's credit worsens:

```text
CDS spread widens -> protection becomes more valuable -> buyer profits.
```

If Company A improves:

```text
CDS spread narrows -> protection loses value -> buyer loses.
```

## CDS Curve Trades

A [[Curve trade]] uses CDS of different maturities on the same reference entity.

The goal is to express a view on the [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]].

### Steepening View

If the investor expects long-term credit risk to rise relative to short-term credit risk:

| Leg | Action |
|---|---|
| Long-term CDS | Buy protection |
| Short-term CDS | Sell protection |

This profits if the credit curve steepens.

### Flattening / Near-Term Stress View

If the investor expects near-term credit risk to rise relative to long-term credit risk:

| Leg | Action |
|---|---|
| Short-term CDS | Buy protection |
| Long-term CDS | Sell protection |

This profits if the curve flattens or inverts because short-term spreads widen relative to long-term spreads.

## Basis Trades

A [[Basis trade]] exploits a difference between credit risk priced in the bond market and credit risk priced in the CDS market.

One common definition:

$$
\text{Basis}=\text{CDS Spread}-\text{Bond Credit Spread}
$$

If:

```text
Bond spread = 4.00%
CDS spread = 3.00%
```

Then credit protection is cheaper in CDS than credit risk compensation in the bond.

A possible trade:

| Leg | Action |
|---|---|
| Bond market | Buy the bond |
| CDS market | Buy protection |

Why?

The investor earns the high bond spread while buying cheaper CDS protection.

If the bond-CDS basis converges, the trade can profit.

## Equity / LBO Example

If an investor expects a leveraged buyout:

```text
Equity may rise because shareholders receive a takeover premium.
Credit risk may worsen because the firm issues more debt.
```

A possible trade:

| View | Position |
|---|---|
| Equity benefits from LBO | Buy stock |
| Credit deteriorates from more leverage | Buy CDS protection |

This is why CDS can be used with equity views, not only bond hedging.

## CDS vs Bond Exposure

| Position | Similar Economic View |
|---|---|
| Buy corporate bond | Long credit risk |
| Sell CDS protection | Long credit risk |
| Short corporate bond | Short credit risk |
| Buy CDS protection | Short credit risk |

But they are not identical:

| Difference | Why It Matters |
|---|---|
| Funding | Bonds require cash funding; CDS usually requires collateral/margin |
| Interest rate risk | Bonds have rate duration; CDS mainly isolates credit risk |
| Deliverability | CDS payoff depends on eligible obligations |
| Basis | CDS and bond spreads can diverge |
| Counterparty risk | CDS depends on protection seller's ability to pay |

## Real-World / Vignette Scenarios

### Scenario 1: Hedging a Bank's Corporate Bond

A bank owns $50 million of a corporate bond.

The credit analyst worries that the issuer may be downgraded.

The bank buys CDS protection.

If spreads widen or default risk rises, the CDS gains value and offsets some bond loss.

Exam implication:

```text
Buying protection reduces credit exposure but does not remove interest rate duration.
```

### Scenario 2: Credit Bullish Portfolio Manager

A manager expects credit spreads to tighten after strong earnings.

The manager can sell CDS protection.

If spreads tighten, the protection seller benefits because the insurance sold at a higher spread is now more valuable to have sold.

Exam implication:

```text
Selling protection is long credit risk.
```

### Scenario 3: Broad Credit Hedge

A sovereign wealth fund owns many investment-grade corporate bonds.

It wants to hedge broad credit exposure quickly.

A single-name CDS would hedge only one issuer.

An index CDS can hedge multiple names at once.

Exam implication:

```text
Use index CDS for diversified credit exposure.
```

## Common Exam Traps

| Trap | Why It Is Wrong | Correct Thinking |
|---|---|---|
| Think protection buyer is long credit risk | Buyer benefits from credit deterioration | Protection buyer is short credit risk |
| Think protection seller is short credit risk | Seller loses when default risk rises | Protection seller is long credit risk |
| Use bond duration in upfront payment formula | Upfront approximation uses CDS duration | Use CDS duration |
| Forget standardized coupons | CDS coupon can differ from market CDS spread | Difference is handled through upfront payment |
| Get upfront direction backward | Above-market coupon benefits seller unless compensated | If spread < coupon, seller pays buyer upfront |
| Think CDS hedges interest rate risk | CDS is about credit events/spreads | Use duration tools for rate risk |
| Ignore hazard rate's effect on premium leg | Premiums stop after default | Hazard rate affects both premium and protection legs |
| Confuse single-name and index CDS | Single-name references one borrower; index references many | Match instrument to exposure |
| Forget index notional falls after a default | Defaulted entity is settled and removed | Remaining index continues on reduced notional |
| Choose wrong curve trade leg | Buying protection benefits from widening spreads | Buy protection where you expect relative spread widening |
| Ignore cheapest-to-deliver | Settlement can depend on eligible lowest-priced obligation | Payoff uses CTD/recovery mechanics |
| Confuse CDS spread with bond spread | They are related but can diverge | Basis trades exploit the difference |

## Memory Hooks

```text
Buy protection = buy insurance = short the credit.
```

```text
Sell protection = sell insurance = long the credit.
```

```text
CDS spread up: buyer happy, seller sad.
CDS spread down: seller happy, buyer sad.
```

```text
Upfront payment uses CDS duration, not bond duration.
```

## Exam-Day Checklist

When a CDS question appears, ask:

1. Who is buying protection and who is selling protection?
2. Is the investor trying to hedge or speculate?
3. Did spreads widen or narrow?
4. Is the question asking about credit risk or interest rate risk?
5. Is this single-name CDS or index CDS?
6. Is there a credit event and settlement payoff?
7. Is the market spread different from the fixed coupon?
8. Which side pays the upfront amount?
9. Is the trade about curve steepening, curve flattening, or basis convergence?
10. Does the question require CDS duration rather than bond duration?

## Related Concepts

- [[Credit default swap (CDS)]]
- [[Single-name CDS]]
- [[Index CDS]]
- [[Tranche CDS]]
- [[Credit protection buyer]]
- [[Credit protection seller]]
- [[Premium leg]]
- [[Protection leg]]
- [[CDS spread]]
- [[Upfront payment]]
- [[Credit event]]
- [[Physical settlement]]
- [[Recovery rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Loss Given Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Hazard Rate]]
- [[Level 2/Generated Notes/07 - Fixed Income/Probability of Default]]
- [[Level 2/Generated Notes/07 - Fixed Income/Spread Duration]]
- [[Level 2/Generated Notes/07 - Fixed Income/Term Structure of Credit Spreads]]
- [[Curve trade]]
- [[Basis trade]]
- [[Naked credit default swap]]
