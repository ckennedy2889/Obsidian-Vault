---
title: Fixed-Income Forwards and Bond Futures
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, fixed-income, futures]
aliases: [Bond futures, Fixed-income forwards, Treasury bond futures, Cheapest-to-deliver bond, CTD bond, Conversion factor]
---

# Fixed-Income Forwards and Bond Futures

## The Real-World Analogy

A fixed-income forward is like agreeing today on the future sale price of a bond, but bonds carry extra baggage. A stock price is just a stock price. A bond has a quoted clean price, accrued interest, coupon payments during the contract life, and sometimes several deliverable bonds that can satisfy a futures contract.

That is why fixed-income forward and futures questions feel more mechanical than equity forward questions. The underlying no-arbitrage idea is still [[Carry Arbitrage Model|cost of carry]], but the inputs must be lined up carefully.

## The Big Idea

A [[Bond futures|bond futures contract]] is an exchange-traded agreement in which:

- The **long** agrees to buy an eligible bond at delivery.
- The **short** agrees to deliver an eligible bond.
- The contract is marked to market daily through a margin account.
- The delivery price is standardized through a quoted futures price and, for many government bond futures, a [[Conversion Factor]].

The long wants bond prices to rise because rising bond prices usually push the futures price up. The short wants bond prices to fall, and the short also owns a valuable delivery option: if several bonds can be delivered, the short chooses the one that is cheapest to deliver.

```text
Long futures position
  |
  v
Receives bond at delivery and pays invoice amount

Short futures position
  |
  v
Chooses eligible bond, delivers it, receives invoice amount
```

The futures exchange does not want every contract to depend on one exact bond issue, because that would make the contract less liquid and easier to squeeze. Instead, it defines a basket of deliverable bonds. That solves the liquidity problem, but creates a valuation problem: the deliverable bonds have different coupons and maturities. The conversion factor system is the exchange's attempt to make those bonds economically comparable.

## Why Bond Futures Are Trickier Than Equity Futures

Equity index futures usually start from one clean index level, subtract expected dividends, and compound at the risk-free rate. Bond futures have more moving parts.

| Issue | Why it matters |
|---|---|
| Clean vs full price | The market quotes clean price, but the buyer pays full price including accrued interest |
| Coupons during contract life | The cash bond holder receives coupons before futures delivery, so coupons reduce the fair futures price |
| Accrued interest at delivery | Futures prices are quoted clean, so accrued interest at delivery must be removed from the quoted price |
| Deliverable basket | The short can deliver any eligible bond, not necessarily one exact issue |
| Conversion factor | Standardizes bonds with different coupons and maturities |
| Cheapest-to-deliver option | The short chooses the economically cheapest eligible bond |

## Clean Price, Full Price, And Accrued Interest

Bond markets quote clean prices, but buyers pay full prices.

$$
\text{Full price} = \text{Clean price} + \text{Accrued interest}
$$

| Term | Meaning |
|---|---|
| [[Clean Price]] | Quoted bond price excluding accrued interest |
| [[Accrued interest]] | Interest earned by seller since last coupon date |
| [[Full price]] | Actual cash price paid by buyer |

Forward pricing starts with the full spot price because that is the real cash amount needed to buy and carry the bond.

## Pricing A Fixed-Income Forward

If a bond forward matures at time $T$, and the bond pays a coupon during the contract life, the fair forward price is:

$$
F_0 =
\left[
(B_0 + AI_0) - PV_0(\text{coupons during contract})
\right](1+r)^T
- AI_T
$$

where:

| Symbol | Meaning |
|---|---|
| $B_0$ | Current clean price |
| $AI_0$ | Accrued interest today |
| $AI_T$ | Accrued interest at forward expiration |
| $PV_0(\text{coupons})$ | Present value of coupon payments received before expiration |
| $r$ | Financing rate over the contract horizon |

The formula starts with full price, subtracts the present value of coupons the spot holder will receive, compounds the net carry amount to expiration, and then subtracts accrued interest at delivery so the quoted forward price is clean.

## Bond Futures And Conversion Factors

Government bond futures often allow the short side to deliver one bond from a basket of eligible bonds. Since eligible bonds have different coupons and maturities, the exchange uses a [[Conversion Factor]] to standardize the delivery invoice.

At delivery:

$$
\text{Invoice amount}
=
(\text{Quoted futures price} \times CF) + AI_T
$$

The conversion factor is approximately the price the bond would have if it yielded the contract's standard yield assumption, commonly 6% in classic Treasury futures convention.

The conversion factor is not a perfect equalizer. It is based on a convention, not the actual market yield at delivery. Because market yields move, the conversion factor system usually makes one eligible bond slightly better for the short to deliver than the others. That bond becomes the [[Cheapest-to-Deliver (CTD)]] bond.

If the adjusted futures price is $F_0$, the quoted futures price is:

$$
Q_0 = \frac{F_0}{CF}
$$

More fully:

$$
Q_0 =
\frac{
FV(B_0 + AI_0 - PV_0(\text{coupons})) - AI_T
}{CF}
$$

The conversion factor divides the whole adjusted clean futures value. Do not multiply the spot price by the conversion factor at the start.

The full logic is:

```text
Start with cash bond full price today
  - PV of coupons received before delivery
  = net cost to carry
  x financing growth to delivery
  = full forward value at delivery
  - accrued interest at delivery
  = clean forward value
  / conversion factor
  = quoted futures price
```

## Cheapest-To-Deliver Bond

The short futures position chooses which eligible bond to deliver. Because conversion factors are imperfect, one bond is usually cheapest to acquire and deliver. That is the [[Cheapest-to-Deliver (CTD)]] bond.

The short's delivery economics are:

```text
Buy deliverable bond in cash market
Deliver into futures
Receive invoice amount from long
```

For CTD comparison, use:

$$
\text{Cost to deliver}
=
B_T - (Q_T \times CF)
$$

The bond with the lowest cost to deliver is the CTD bond.

Accrued interest cancels in the comparison because the short pays accrued interest when buying the bond and receives accrued interest in the invoice amount.

Another way to see the same idea is from the short's net economics:

$$
\text{Short net delivery cost}
= \text{cash price paid for bond} - \text{invoice amount received}
$$

Using full prices:

$$
(B_T + AI_T) - (Q_T \times CF + AI_T)
= B_T - Q_TCF
$$

The $AI_T$ terms cancel. That is why the clean-price CTD shortcut works.

## Delivery Options

Bond futures often give the short side delivery options:

| Option | Why it matters |
|---|---|
| Quality option | Short chooses which eligible bond to deliver, usually the CTD bond |
| Timing option | Short chooses when to deliver during the delivery month |
| Wild card play | Short may benefit from late-day bond price moves after futures settlement is fixed |

These options benefit the short and therefore reduce the value of the futures contract to the long relative to a single-asset forward with no delivery flexibility.

## Value After Initiation

For a long fixed-income forward:

$$
V_t =
PV_t(F_t - F_0)
$$

where $F_t$ is the current fair adjusted forward price for the remaining life and $F_0$ is the original locked-in price.

For exchange-traded futures, gains and losses are marked to market daily through the margin account, so the futures contract value resets to zero after daily settlement.

This is the conceptual difference between a forward value and a futures account balance. A forward contract can accumulate value because gains and losses are settled at maturity. A futures contract is settled every day, so after settlement the contract is reset at the new futures price and its value is approximately zero. The trader's profit or loss has already moved into or out of the margin account.

## Worked Numerical Example: Quoted Bond Futures Price

Assume a Euro-bund futures contract expires in one month. The current one-month risk-free rate is 0.10% annual. The deliverable bond has:

| Input | Value |
|---|---:|
| Clean price, $B_0$ | €108.000 |
| Accrued interest today, $AI_0$ | €0.083 |
| Accrued interest at expiration, $AI_T$ | €0.250 |
| Coupons before expiration | €0 |
| Conversion factor, $CF$ | 0.729535 |
| Time to expiration | $1/12$ year |

First compute the future value of the full spot price:

$$
FV(B_0 + AI_0)
=
(108.000 + 0.083)(1.001)^{1/12}
$$

$$
FV(B_0 + AI_0)
\approx
108.092
$$

Subtract accrued interest at expiration to express the delivery price clean:

$$
F_0 = 108.092 - 0.250 = 107.842
$$

Divide by the conversion factor:

$$
Q_0 =
\frac{107.842}{0.729535}
=
147.82
$$

The quoted futures price is about €147.82.

## Worked Numerical Example: Cheapest To Deliver

The current futures settlement price is $Q_T=143.47$. The short can deliver Bond A or Bond B:

| Bond | Clean price $B_T$ | Conversion factor | Cost to deliver |
|---|---:|---:|---:|
| A | 120.75 | 0.8388 | $120.75 - 143.47(0.8388) = 0.41$ |
| B | 128.50 | 0.8883 | $128.50 - 143.47(0.8883) = 1.06$ |

Bond A is cheapest to deliver because it has the lower cost to deliver.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Starting from clean price only | Ignores cash actually paid for the bond | Start with $B_0 + AI_0$ |
| Forgetting coupon benefits | Overstates fair futures price | Subtract PV of coupons received during the contract |
| Forgetting $AI_T$ | Gives a full-price forward quote instead of clean quote | Subtract accrued interest at delivery |
| Misplacing the conversion factor | Multiplies the spot price by CF before compounding | Divide the adjusted clean futures value by CF |
| Including accrued interest in CTD comparison | Double-counts accrued interest | Use $B_T - Q_TCF$ |
| Thinking long chooses delivery bond | Reverses optionality | Short chooses the deliverable bond |

## Memory Hooks

**Bond forward starts dirty and ends clean.** Start with full price; subtract accrued interest at delivery for the quoted price.

**Coupons are carry benefits.** Subtract their present value before compounding.

**CTD = lowest clean cost after conversion factor.**

## Related Concepts

- [[Carry Arbitrage Model]]
- [[Forward Price vs Forward Rate]]
- [[Clean Price]]
- [[Full price]]
- [[Accrued interest]]
- [[Conversion Factor]]
- [[Cheapest-to-Deliver (CTD)]]
- [[Futures contract]]
- [[Duration]]
