---
title: Forward Price vs Forward Rate
subject: Derivatives
tags: [CFA-L2, derivatives, forwards, forward-rate-agreements, no-arbitrage, valuation]
aliases: [Forward price versus forward rate, Forward price vs forward rate, FRA price, Forward contract price vs value]
---

# Forward Price vs Forward Rate

## The Real-World Analogy

Imagine two different promises.

First, you agree today to buy a stock from someone in 90 days for \$52. That \$52 is a **forward price**. It is a future delivery price for an asset.

Second, you agree today that if you borrow money 90 days from now, the borrowing rate will be 5.25%. That 5.25% is a **forward rate**. It is a future borrowing or lending rate.

Both are forward commitments because the deal is locked in today and settles later. The difference is what is being locked in:

```text
Forward price = future asset delivery price
Forward rate  = future interest rate
```

The exam trap is that CFA sometimes says the "price" of a forward contract. For a normal asset forward, that price is a dollar price, index level, bond price, yield, or exchange rate. For a [[Forward rate agreement|forward rate agreement]] (FRA), the "price" is itself an interest rate.

## The Big Idea

A [[Forward price]] is the no-arbitrage delivery price that makes a forward contract worth zero at initiation.

A [[Forward rate]] is the no-arbitrage interest rate agreed today for a loan or investment period that starts in the future.

The shared principle is:

```text
At initiation, choose the forward price or forward rate so:

Value to long = 0
Value to short = 0
```

The difference is the unit:

| Concept | Unit | Typical contract |
|---|---|---|
| [[Forward price]] | Dollars, index points, exchange rate, bond price, yield quote, discount quote | Equity forward, bond forward, currency forward, commodity forward |
| [[Forward rate]] | Annualized interest rate | [[Forward rate agreement]] |
| Forward value | Currency amount | Any existing forward after initiation |

Do not blur **price** and **value**. The forward price/rate is the contract term. The forward value is the mark-to-market value of the existing contract.

## Why CFA Tests This

This distinction sits inside the Level II Derivatives reading on pricing and valuing forward commitments. The LOS asks you to price and value equity forwards, interest rate forwards, fixed-income forwards, and swaps.

That means CFA expects you to know three separate ideas:

| Question wording | What they are asking for |
|---|---|
| "Calculate the forward price" | Find the no-arbitrage delivery price |
| "Calculate the forward rate" or "price of an FRA" | Find the implied future interest rate |
| "Calculate the value of the forward" | Mark an existing contract to market |

The hard part is not usually algebra. It is identifying which object the question is asking for.

## Price vs Value: The Non-Negotiable Distinction

At initiation, a forward is usually entered at zero value.

```text
t = 0:
Forward price or rate is set.
Contract value = 0.
```

After initiation, market conditions change.

```text
t > 0:
Original contract price/rate stays fixed.
Current market forward price/rate changes.
Contract value becomes positive for one side and negative for the other.
```

For a long asset forward:

```text
Original forward price = the delivery price locked into the contract
Current forward price  = today's fair delivery price for the same remaining maturity
Forward value          = PV(current forward price - original forward price)
```

The long benefits when the current fair forward price rises above the locked-in forward price. The long has the right and obligation to buy cheaply relative to the market.

## Forward Price For An Asset

For a simple asset with no storage costs, no dividends, no coupons, and no other benefits:

$$
F_0=S_0(1+r)^T
$$

or with continuous compounding:

$$
F_0=S_0e^{rT}
$$

where:

| Symbol | Meaning |
|---|---|
| $F_0$ | No-arbitrage forward price at initiation |
| $S_0$ | Current spot price of the underlying |
| $r$ | Risk-free rate over the contract life |
| $T$ | Time to contract maturity |

Why this formula exists:

```text
Buy the asset today and carry it to maturity
must cost the same as
agreeing today to buy it at maturity through a forward.
```

If the forward price is too high, an arbitrageur can borrow, buy the asset, and short the forward. If the forward price is too low, an arbitrageur can short the asset, invest the proceeds, and go long the forward.

### With Cash Flows From The Underlying

If the underlying pays known dividends or coupons during the life of the contract, the long forward does **not** receive those interim cash flows. So they reduce the forward price.

For known cash flows with present value $PVC$:

$$
F_0=(S_0-PVC)(1+r)^T
$$

For a continuous dividend yield $q$:

$$
F_0=S_0e^{(r-q)T}
$$

The mechanism:

```text
Carry costs increase forward price.
Carry benefits decrease forward price.
```

Dividends and coupons are benefits of owning the asset, not benefits of holding the long forward. So they lower the fair forward delivery price.

### Convergence To Spot At Expiration

The current market [[Forward price]] converges to the [[Spot price]] at expiration because the carry period disappears.

For a simple asset:

$$
F_t=S_t(1+r)^{T-t}
$$

At expiration, $T-t=0$, so:

$$
F_T=S_T(1+r)^0=S_T
$$

This does **not** mean the original delivery price locked into an existing contract changes. It means the fair market forward price for delivery now equals the spot price now. The existing long forward's payoff is still:

$$
S_T-F_0
$$

See [[Convergence]] for the full basis and exam-trap explanation.

## Forward Rate For An FRA

A [[Forward rate agreement]] is different because the underlying is not an asset delivered for a dollar price. It is an interest rate on a future loan.

The "price" of an FRA is the fixed interest rate agreed today.

```text
FRA price = forward interest rate
```

The long FRA position is effectively the party that benefits from borrowing at a fixed rate if market rates rise. In short form:

| Position | Economic view | Gains when |
|---|---|---|
| Long FRA | Pay fixed / receive floating; effectively long the rate | Rates rise |
| Short FRA | Receive fixed / pay floating; effectively short the rate | Rates fall |

Suppose an FRA covers a future loan from time $h$ to time $T$. The current MRR for maturity $h$ is $L_h$, and the current MRR for maturity $T$ is $L_T$. With money-market add-on rates:

$$
1+L_Tt_T=(1+L_ht_h)(1+FRA_0t_m)
$$

where:

| Symbol | Meaning |
|---|---|
| $L_h$ | Current market reference rate to the FRA expiration date |
| $L_T$ | Current market reference rate to the end of the underlying loan |
| $t_h$ | Year fraction to FRA expiration |
| $t_T$ | Year fraction to underlying loan maturity |
| $t_m$ | Year fraction of the underlying loan period, $T-h$ |
| $FRA_0$ | No-arbitrage forward rate, annualized |

Solving:

$$
FRA_0=\left[\frac{1+L_Tt_T}{1+L_ht_h}-1\right]\frac{1}{t_m}
$$

This is the same no-arbitrage idea as spot and forward rates in fixed income. Investing to the long maturity directly must equal investing to the short maturity and then rolling at the implied forward rate.

## Worked Example 1: Asset Forward Price

Suppose a non-dividend-paying stock trades at:

| Input | Value |
|---|---:|
| Spot price, $S_0$ | \$50 |
| Risk-free rate, $r$ | 4% |
| Time to maturity, $T$ | 0.5 years |

No-arbitrage forward price:

$$
F_0=S_0(1+r)^T
$$

$$
F_0=50(1.04)^{0.5}
$$

$$
(1.04)^{0.5}=1.0198
$$

$$
F_0=50(1.0198)=50.99
$$

So the fair six-month forward price is:

$$
F_0=50.99
$$

If the contract were instead offered at \$53, the forward is overpriced. A trader could borrow \$50, buy the stock, and short the forward. At maturity, the trader delivers the stock for \$53 and repays the loan of \$50.99, locking in about \$2.01 before frictions.

## Worked Example 2: Value Of An Existing Asset Forward

Now suppose you entered the long forward at:

$$
F_0=50.99
$$

Three months later, the stock is \$54 and there are three months left. The current risk-free rate is still 4%.

The current fair forward price for the remaining life is:

$$
F_t=S_t(1+r)^{T-t}
$$

$$
F_t=54(1.04)^{0.25}
$$

$$
(1.04)^{0.25}=1.0099
$$

$$
F_t=54.53
$$

The value to the long is the present value of the difference between the current fair forward price and the original locked-in price:

$$
V_t=\frac{F_t-F_0}{(1+r)^{T-t}}
$$

$$
V_t=\frac{54.53-50.99}{(1.04)^{0.25}}
$$

$$
V_t=\frac{3.54}{1.0099}=3.51
$$

The long forward is worth about \$3.51 because the long can buy at \$50.99 when the current fair forward delivery price is \$54.53.

Notice the vocabulary:

```text
Original forward price = 50.99
Current forward price  = 54.53
Forward value          = 3.51
```

Those are three different numbers.

## Worked Example 3: Forward Rate For An FRA

Suppose a company wants to lock in the rate on a 90-day loan that starts 30 days from now. This is a 1 x 4 FRA: the contract expires in 1 month, and the underlying loan ends in 4 months.

| Input | Value |
|---|---:|
| 30-day MRR, $L_h$ | 4.00% |
| 120-day MRR, $L_T$ | 5.00% |
| $t_h$ | $30/360 = 0.083333$ |
| $t_T$ | $120/360 = 0.333333$ |
| $t_m$ | $90/360 = 0.25$ |

Use:

$$
FRA_0=\left[\frac{1+L_Tt_T}{1+L_ht_h}-1\right]\frac{1}{t_m}
$$

Plug in:

$$
FRA_0=\left[\frac{1+0.05(120/360)}{1+0.04(30/360)}-1\right]\frac{1}{90/360}
$$

Compute the two accumulation factors:

$$
1+0.05(120/360)=1.016667
$$

$$
1+0.04(30/360)=1.003333
$$

Ratio:

$$
\frac{1.016667}{1.003333}=1.013289
$$

Unannualized 90-day forward rate:

$$
1.013289-1=0.013289
$$

Annualize:

$$
FRA_0=0.013289 \times 4=0.05316
$$

So:

$$
FRA_0=5.32\%
$$

This 5.32% is the **forward rate** and also the **price of the FRA**. It is not a dollar price. It is the fixed annualized rate that makes the FRA worth zero at initiation.

## Worked Example 4: FRA Value At Settlement

Continue the prior example. The company is long the FRA at 5.32% on a \$1,000,000 notional. At FRA expiration, the 90-day market rate is 6.00%.

The long benefits because it effectively locked in borrowing at 5.32% when the market rate is 6.00%.

Interest savings at the end of the underlying 90-day loan:

$$
\text{Savings}=N(L_{\text{market}}-FRA_0)t_m
$$

$$
\text{Savings}=1{,}000{,}000(0.0600-0.0532)(90/360)
$$

$$
\text{Savings}=1{,}000{,}000(0.0068)(0.25)=1{,}700
$$

But an FRA is cash-settled at the FRA expiration date, while the interest savings would occur at the end of the loan. So discount the savings back 90 days at the current 90-day market rate:

$$
\text{FRA value at settlement}=\frac{1{,}700}{1+0.0600(90/360)}
$$

$$
=\frac{1{,}700}{1.015}=1{,}674.88
$$

The long receives about \$1,675 from the short.

The key mechanism:

```text
Long FRA gains when rates rise.
Payoff is interest savings.
Settlement is advanced, so discount the savings back to FRA expiration.
```

## Forward Price vs Forward Rate vs Forward Value

| Item | What it means | Unit | Set when? | Changes after inception? |
|---|---|---|---|---|
| Forward price | Agreed delivery price for an underlying asset | Dollars, index points, exchange rate, bond price, yield quote | At contract initiation | Original contract price stays fixed; current market forward price changes |
| Forward rate | Agreed interest rate for a future borrowing/lending period | Annualized percentage rate | At FRA initiation | Original FRA rate stays fixed; current market forward rate changes |
| Forward value | Mark-to-market value of an existing forward | Currency amount | Zero at initiation | Changes as spot prices, rates, and carry inputs change |

The quickest exam filter:

```text
If the underlying is an asset, think forward price.
If the underlying is a future loan rate, think forward rate.
If the contract already exists and market data changed, think forward value.
```

## Common Exam Traps

### Trap 1: Calling The Forward Price The Cost To Enter The Contract

Usually, no money changes hands at initiation. The forward price is the agreed future delivery price, not an upfront premium.

Correct reflex:

```text
Forward price/rate makes initial value zero.
```

### Trap 2: Mixing Current Forward Price With Original Contract Price

After inception, the original forward price remains locked in. The current fair forward price changes. The contract value comes from the difference.

For the long:

$$
V_t=\frac{F_t-F_0}{(1+r)^{T-t}}
$$

where $F_t$ is the current fair forward price and $F_0$ is the original contract price.

### Trap 3: Thinking A Long FRA Gains When Rates Fall

A long FRA is effectively long the interest rate. It gains when the market reference rate rises above the contract rate because it locked in a below-market borrowing rate.

```text
Long asset forward -> gains when asset price rises.
Long FRA -> gains when interest rates rise.
```

### Trap 4: Forgetting FRA Advanced Settlement

The underlying interest savings occur at the end of the hypothetical loan, but the FRA settles at the start of that loan. Therefore, discount the interest difference back to the FRA settlement date.

### Trap 5: Misreading FRA Notation

A 1 x 4 FRA does not mean a 4-month loan. It means:

```text
Expires in 1 month.
Underlying loan ends in 4 months.
Loan period = 4 - 1 = 3 months.
```

### Trap 6: Treating Forward Rates As Forecasts By Default

A forward rate is a no-arbitrage break-even rate implied by current spot rates. It is not automatically an unbiased forecast of the future spot rate unless a term-structure theory assumption says so.

## Memory Hooks

```text
Price locks the asset delivery amount.
Rate locks the future loan cost.
Value marks the existing contract.
```

For FRAs:

```text
Long FRA = long rates.
Rates up -> long receives.
Rates down -> long pays.
```

For asset forwards:

```text
Long forward = obligated buyer.
Underlying up -> long wins.
Underlying down -> short wins.
```

## Related Concepts

- [[Forward price]]
- [[Forward rate]]
- [[Forward rate agreement]]
- [[Forward contract]]
- [[No-arbitrage pricing]]
- [[Carry arbitrage model]]
- [[Cost of carry]]
- [[Spot price]]
- [[Implied forward rates]]
- [[Discount factor]]
- [[Interest rate swap]]
- [[Currency forward]]
- [[Equity forward]]
- [[Fixed-income forward]]
