---
title: N(d2)
subject: Derivatives
tags:
  - CFA-L2
  - derivatives
  - options
  - BSM
  - risk-neutral
  - probability
aliases:
  - N(d2)
  - N(d_2)
  - Nd2
  - BSM N(d2)
  - d2
---

# N(d2)

## The Real-World Analogy

Imagine a call option as a ticket that only matters if a door opens. The door opens if the stock finishes above the strike price.

`N(d2)` answers the door question in the Black-Scholes-Merton world:

> Under risk-neutral pricing, what is the probability that the call finishes in the money?

For a put, `N(-d2)` answers the parallel question:

> Under risk-neutral pricing, what is the probability that the put finishes in the money?

## The Big Idea

In the [[Black-Scholes-Merton Model]], `N(d2)` is the [[Risk-Neutral Probabilities|risk-neutral probability]] that a European call option expires in the money:

$$
N(d_2)=P^{RN}(S_T>X)
$$

For a put:

$$
N(-d_2)=P^{RN}(S_T<X)
$$

The European call formula is:

$$
c = S N(d_1) - Xe^{-rT}N(d_2)
$$

The second term:

$$
Xe^{-rT}N(d_2)
$$

is the present value of the strike payment, weighted by the risk-neutral probability that the strike will actually be paid.

## Formula

For a non-dividend-paying stock:

$$
d_1 =
\frac{\ln(S/X)+\left(r+\frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

$$
d_2=d_1-\sigma\sqrt{T}
$$

Equivalently:

$$
d_2 =
\frac{\ln(S/X)+\left(r-\frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

Then:

$$
N(d_2)=\text{standard normal CDF evaluated at }d_2
$$

## Why `N(d2)` Is the Risk-Neutral Exercise Probability

Under BSM, the stock price at expiration is lognormally distributed. The call expires in the money when:

$$
S_T>X
$$

Take logs:

$$
\ln(S_T)>\ln(X)
$$

Under the risk-neutral measure, the expected drift of the stock is the risk-free rate adjusted for volatility:

$$
\ln(S_T)
\sim
N\left(
\ln(S)+\left(r-\frac{1}{2}\sigma^2\right)T,\;
\sigma^2T
\right)
$$

Standardizing the condition $S_T>X$ gives exactly $d_2$:

$$
d_2=
\frac{\ln(S/X)+\left(r-\frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

Therefore:

$$
P^{RN}(S_T>X)=N(d_2)
$$

That is the clean probability interpretation.

## Why `N(d2)` Is Not the Actual Probability

`N(d2)` is a risk-neutral probability, not a real-world forecast. It is calculated using risk-neutral drift, not the stock's actual expected return.

| Probability | Drift used | Meaning |
|---|---|---|
| Actual probability | Expected return required by investors | Forecasting probability |
| Risk-neutral probability | Risk-free rate | No-arbitrage pricing probability |

If a portfolio manager believes the stock has a high expected return, the real-world probability of finishing in the money may be higher than `N(d2)`. But BSM does not need that forecast to price the option because the current stock price already reflects risk preferences and expected returns.

## Why `d2 = d1 - sigma sqrt(T)`

The relationship is:

$$
d_1=d_2+\sigma\sqrt{T}
$$

or:

$$
d_2=d_1-\sigma\sqrt{T}
$$

The gap is one full volatility-over-time term.

Intuition:

- `d2` is about the probability of crossing the strike.
- `d1` is about stock-weighted exposure conditional on future stock outcomes.
- Stock-weighted successful states put more emphasis on high-stock-price outcomes.

Because high stock outcomes matter more for delta and the stock component, `d1` is shifted upward relative to `d2`.

That is why, when volatility and time are positive:

$$
N(d_1)>N(d_2)
$$

## Worked Example

Assume:

- $S=100$.
- $X=100$.
- $r=5\%$ continuously compounded.
- $\sigma=30\%$.
- $T=1$ year.

From the paired `N(d1)` example:

$$
d_1=0.3167
$$

Compute:

$$
d_2=d_1-\sigma\sqrt{T}
=0.3167-0.30
=0.0167
$$

Look up the cumulative normal value:

$$
N(d_2)=N(0.0167)\approx 0.507
$$

Interpretation:

- The risk-neutral probability the call expires in the money is about 50.7%.
- The risk-neutral probability the corresponding put expires in the money is:

$$
N(-d_2)=1-N(d_2)=1-0.507=0.493
$$

In the same example:

$$
N(d_1)\approx 0.624
$$

So `N(d1)` is much higher than `N(d2)`. That is not a contradiction. `N(d1)` is stock exposure; `N(d2)` is risk-neutral exercise probability.

## How `N(d2)` Appears in Calls and Puts

For a call:

$$
c = S N(d_1)-Xe^{-rT}N(d_2)
$$

Interpretation:

- Buy `N(d1)` shares.
- Borrow the present value of `N(d2)` strike payments.

For a put:

$$
p = Xe^{-rT}N(-d_2)-S N(-d_1)
$$

Interpretation:

- Own a risk-free bond component that pays when the put finishes in the money.
- Short stock exposure equal to `N(-d1)` shares.

## Dividend and Currency Carry

With continuous dividend yield $\delta$:

$$
d_2 =
\frac{\ln(S/X)+\left(r-\delta-\frac{1}{2}\sigma^2\right)T}
{\sigma\sqrt{T}}
$$

Call formula:

$$
c=Se^{-\delta T}N(d_1)-Xe^{-rT}N(d_2)
$$

For currency options, replace the dividend yield with the foreign risk-free rate $r_f$:

$$
c=Se^{-r_fT}N(d_1)-Xe^{-r_dT}N(d_2)
$$

The strike component still uses the domestic discount rate because the strike is paid in domestic currency.

## Black Model, Caps/Floors, and Swaptions

The same `N(d2)` logic appears in Black-style formulas.

For options on futures or forwards:

$$
c=e^{-rT}[F_0N(d_1)-XN(d_2)]
$$

Here:

- `N(d1)` weights the forward/futures exposure.
- `N(d2)` weights the strike payment probability.

For interest rate options, caps/floors, and swaptions, the notation changes but the structure remains:

```text
Option value = discounted [underlying rate/swap component weighted by N(d1)
                           - strike component weighted by N(d2)]
```

That pattern is the transferable idea. The "asset" changes; the roles of `N(d1)` and `N(d2)` do not.

## Exam Traps

| Trap | Correct interpretation |
|---|---|
| `N(d2)` is the actual probability of exercise | False. It is risk-neutral probability. |
| `N(d2)` is delta | False. `N(d1)` is call delta for a non-dividend stock. |
| `N(d1)` and `N(d2)` are close, so use either | False. They multiply different BSM terms. |
| For puts, use `N(d2)` directly | Use `N(-d2)` for put ITM probability and strike component. |
| Forgetting carry adjustments | Dividend yield or foreign rate changes both `d1` and `d2`. |
| Thinking `N(d2)` is always near 0.50 for ATM options | Rates, dividends, volatility, and time can push it away from 0.50. |

## Memory Hooks

**`d2` is the door probability.** It asks whether the option finishes through the strike.

**`N(d2)` weights the strike.**

**`N(d1)` is how much stock; `N(d2)` is how likely exercise under risk-neutral pricing.**

## Related Concepts

- [[N(d1)]]
- [[Risk-Neutral Probabilities]]
- [[Black-Scholes-Merton Model]]
- [[Option Greeks]]
- [[Hedge Ratio]]
- [[Swaptions]]
- [[Interest Rate Options — Caps and Floors]]

