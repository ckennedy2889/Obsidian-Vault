---
title: Forward Rate Agreements (FRAs)
subject: Derivatives
tags: [CFA-L2, derivatives, forward-commitments, interest-rates]
aliases: [FRA, Forward rate agreement, Forward rate agreements, advanced set advanced settled]
---

# Forward Rate Agreements (FRAs)

## The Real-World Analogy

Think of a [[Forward rate agreement]] as reserving the interest rate on a loan before the loan actually begins. A treasurer knows the company will borrow in three months for the following six months. The risk is not that cash changes hands today; the risk is that the borrowing rate available in three months may be higher than expected. The FRA is the side contract that says, in effect, "If the future market rate is above the fixed rate we agree today, compensate me; if it is below, I will compensate you."

That is why an FRA feels like a [[Forward contract]], but the underlying is not a stock, bond, or currency delivered at maturity. The underlying is a future [[Market reference rate|market reference rate]] on a hypothetical deposit or loan.

## The Big Idea

An FRA is an OTC forward contract on a future short-term interest rate. The contract specifies a notional amount, a fixed FRA rate, a start date for the underlying loan period, and an end date for that loan period. The notional is only a measuring base; it is not exchanged.

The long FRA position is the side that pays fixed and receives floating. That means the long is economically long the interest rate:

| Position | Pays | Receives | Gains when |
|---|---:|---:|---|
| Long FRA | Fixed FRA rate | Future floating MRR | Market rates rise |
| Short FRA | Future floating MRR | Fixed FRA rate | Market rates fall |

The exam trap is that "long" does not mean "long a bond." A bond gains when yields fall. A long FRA gains when the reference rate rises because the long receives the higher floating rate and pays the lower fixed rate.

## FRA Notation

FRA notation is usually written as $A \times B$:

| FRA | Contract expires | Underlying loan/deposit period |
|---|---:|---:|
| $1 \times 4$ | 1 month | 3 months, from month 1 to month 4 |
| $3 \times 9$ | 3 months | 6 months, from month 3 to month 9 |
| $6 \times 9$ | 6 months | 3 months, from month 6 to month 9 |

The first number is not the loan tenor. The loan tenor is the difference between the second and first numbers.

```text
Today          FRA expires                  Hypothetical loan ends
  |----------------|--------------------------------|
       h months                  T - h months
```

## Pricing: Solving For The FRA Rate

Pricing an FRA means finding the fixed rate that makes the contract worth zero at initiation. The no-arbitrage FRA rate is the implied [[Forward rate]] between two spot rates.

Suppose:

| Symbol | Meaning |
|---|---|
| $L_h$ | Spot MRR from today to FRA expiration $h$ |
| $L_T$ | Spot MRR from today to final maturity $T$ |
| $t_h$ | Year fraction from today to $h$ |
| $t_T$ | Year fraction from today to $T$ |
| $t_m$ | Year fraction of the underlying loan period, $T-h$ |

The no-arbitrage relation is:

$$
1 + L_T t_T = (1 + L_h t_h)(1 + FRA_0 t_m)
$$

Solving for the fixed FRA rate:

$$
FRA_0 =
\frac{
\left(\frac{1 + L_T t_T}{1 + L_h t_h}\right) - 1
}{t_m}
$$

The mechanism is simple: investing directly to $T$ must produce the same future value as investing to $h$ and then reinvesting from $h$ to $T$ at the forward rate. If those paths do not match, a trader can borrow on the cheap path and lend on the expensive path.

## Why Settlement Is Discounted

FRAs are usually **advanced set, advanced settled**:

| Feature | Meaning |
|---|---|
| Advanced set | The floating rate is observed at FRA expiration, the start of the hypothetical loan period |
| Advanced settled | The cash settlement is paid immediately at FRA expiration |

The interest-rate difference economically applies over the future loan period, but cash is paid at the start of that period. Because the cash arrives early, the payoff must be discounted back from the end of the loan period to the FRA settlement date.

For a long FRA:

$$
\text{Settlement}_{long}
=
NA \times
\frac{(L_{settle} - FRA_0)t_m}
{1 + L_{settle}t_m}
$$

For a short FRA:

$$
\text{Settlement}_{short}
=
NA \times
\frac{(FRA_0 - L_{settle})t_m}
{1 + L_{settle}t_m}
$$

If the question says the contract is settled in arrears instead, do not use the same discounting shortcut. CFA usually tests the standard advanced-settled structure, but the wording controls the calculation.

## Valuation After Initiation

Pricing at initiation gives a rate. Valuation after initiation gives a dollar value. Once market rates move, the original FRA rate is stale. The existing contract is valued by comparing the original fixed rate with the current market FRA rate for the remaining period.

For a long FRA at time $g$:

$$
V_g =
NA \times
\frac{(FRA_g - FRA_0)t_m}
{1 + D_{T-g}t_{T-g}}
$$

where $FRA_g$ is the current forward rate for the remaining underlying period and $D_{T-g}$ is the current discount rate over the remaining cash-settlement horizon. Mechanically, you are asking: "If I entered an offsetting FRA today, how much better or worse is my old rate than the new market rate?"

## Worked Numerical Example

Assume a company enters a $6 \times 9$ FRA on a $10,000,000 notional. The 180-day spot MRR is 1.50%, the 270-day spot MRR is 1.75%, and rates use a 360-day year.

The year fractions are:

$$
t_h = \frac{180}{360}=0.50
$$

$$
t_T = \frac{270}{360}=0.75
$$

$$
t_m = \frac{90}{360}=0.25
$$

The no-arbitrage FRA rate is:

$$
FRA_0 =
\frac{
\left(\frac{1 + 0.0175(0.75)}{1 + 0.0150(0.50)}\right)-1
}{0.25}
$$

$$
FRA_0 =
\frac{
\left(\frac{1.013125}{1.007500}\right)-1
}{0.25}
$$

$$
FRA_0 = 0.02233 = 2.233\%
$$

Now suppose the company is long the FRA, and at settlement the 90-day market reference rate is 2.80%. The long gains because floating is now above the locked-in fixed rate.

The undiscounted interest difference is:

$$
10{,}000{,}000(0.02800 - 0.02233)(0.25) = 14{,}175
$$

Because the FRA settles at the start of the 90-day period, discount the amount:

$$
\text{Settlement}_{long}
=
\frac{14{,}175}{1 + 0.02800(0.25)}
=
\frac{14{,}175}{1.007}
=
14{,}076.47
$$

The long receives about $14,076.47.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Confusing pricing and valuation | Candidate gives a dollar value when the question asks for the FRA rate, or vice versa | "Price" of an FRA is the fixed rate; "value" is the mark-to-market dollar amount |
| Misreading $A \times B$ notation | Treats a $3 \times 9$ FRA as a 9-month loan | Loan period is $B-A$ months |
| Reversing long/short direction | Thinks long FRA gains when rates fall | Long FRA pays fixed, receives floating, gains when rates rise |
| Forgetting settlement discounting | Calculates only the interest differential | Standard FRA payoff is advanced settled, so divide by $1+L t$ |
| Using the wrong spot rates | Uses the loan-period rate directly without extracting the forward rate | Use the two spot rates that bracket the future period |

## Memory Hooks

**Long FRA = long rates.** If the market reference rate jumps, the long receives the jump and pays the old fixed rate.

**FRA price is a rate; FRA value is money.** The first is the locked-in forward rate at initiation. The second is the contract's current mark-to-market amount after rates move.

**Advanced settlement means discount.** The payoff is based on interest over the hypothetical loan period, but cash arrives at the beginning of that period.

## Related Concepts

- [[Forward Price vs Forward Rate]]
- [[Forward rate agreement]]
- [[Forward rate]]
- [[Market reference rate]]
- [[Interest rate swap]]
- [[Swap rate]]
- [[Covered interest rate parity]]
- [[No-arbitrage pricing]]
