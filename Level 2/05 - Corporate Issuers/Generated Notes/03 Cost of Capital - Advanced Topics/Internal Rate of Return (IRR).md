---
title: Internal Rate of Return (IRR)
subject: Corporate Issuers
tags: [CFA-L2, corporate-issuers, capital-budgeting, cost-of-capital, investment-decisions]
aliases: [IRR, Internal rate of return, IRR rule, Internal Rate of Return]
---

# Internal Rate of Return (IRR)

## The Real-World Analogy

Imagine you lend a friend $100 today and they promise to pay you $60 next year and $60 the year after. You could describe that deal in dollars:

```text
Pay 100 today, receive 120 total later.
```

But the more useful question is:

```text
What annual return did I earn on the money while it was tied up?
```

That return is the [[Internal rate of return|internal rate of return]]. It is the discount rate that makes the present value of future cash inflows exactly equal to the cash outflow today.

IRR is popular because humans like percentages. "This project earns 14%" feels easier to interpret than "this project has an NPV of $18.7 million." But the percentage can hide scale, timing, and reinvestment assumptions. CFA tests IRR because it is useful, intuitive, and very easy to misuse.

## Plain-English Definition

[[Internal rate of return|IRR]] is the discount rate that makes an investment's [[Net present value|net present value]] equal zero.

In words:

```text
IRR is the break-even discount rate.
```

If the required return is below the IRR, the project creates value. If the required return is above the IRR, the project destroys value. If the required return equals the IRR, the project has zero NPV, meaning it earns exactly the required return and no excess return.

## Why CFA Tests This

IRR sits at the intersection of [[Capital budgeting]], [[Cost of capital]], [[Required rate of return]], [[Net present value]], and [[Money-weighted return]].

CFA wants you to know two things at the same time:

| What IRR is good for | Why IRR can mislead |
|---|---|
| It gives a quick percentage return on a set of cash flows | It can rank projects incorrectly |
| It is easy to compare with a hurdle rate | It assumes reinvestment at the IRR |
| It works cleanly for conventional cash flows | It can produce multiple IRRs or no IRR |
| It is useful for loans, bonds, leases, and project cash flows | It ignores absolute wealth creation when projects differ in scale |

The exam reflex is:

```text
Independent project? IRR rule usually works if cash flows are conventional.
Mutually exclusive projects? Prefer NPV.
Non-conventional cash flows? Beware multiple or no IRR.
```

## Formula and Derivation

The NPV of a project is:

$$
NPV=\sum_{t=0}^{T}\frac{CF_t}{(1+r)^t}
$$

where:

| Symbol | Meaning |
|---|---|
| $CF_t$ | Cash flow at time $t$ |
| $r$ | Required rate of return, discount rate, or opportunity cost of capital |
| $T$ | Final period of the project |

IRR is the specific discount rate that sets this NPV equal to zero:

$$
0=\sum_{t=0}^{T}\frac{CF_t}{(1+IRR)^t}
$$

For a simple project with one initial outflow followed by future inflows:

$$
0=CF_0+\frac{CF_1}{1+IRR}+\frac{CF_2}{(1+IRR)^2}+\cdots+\frac{CF_T}{(1+IRR)^T}
$$

Because $CF_0$ is usually negative, the equation can also be read as:

$$
\text{Initial investment}=\text{PV of future benefits discounted at IRR}
$$

That is the mechanism. IRR is the rate at which the project just pays back investors for the time value and risk of capital, with no surplus value left over.

## The IRR Decision Rule

For an independent project with conventional cash flows:

| Condition | Decision | NPV implication |
|---|---|---|
| $IRR>r$ | Accept | $NPV>0$ |
| $IRR=r$ | Indifferent / acceptable minimum | $NPV=0$ |
| $IRR<r$ | Reject | $NPV<0$ |

Why does this work? The NPV profile slopes downward for a conventional project. As the discount rate increases, the present value of future inflows falls. The IRR is the discount rate where the NPV line crosses zero.

```text
Discount rate below IRR  -> future inflows are discounted less -> NPV positive
Discount rate equal IRR  -> PV inflows exactly equals outflow -> NPV zero
Discount rate above IRR  -> future inflows are discounted more -> NPV negative
```

The rule depends on conventional cash flows. That usually means one initial negative cash flow followed by positive cash flows, with only one sign change.

## Worked Numerical Example

Suppose Gerhardt Corporation is considering a project with these expected cash flows:

| Year | Cash flow |
|---:|---:|
| 0 | -$50 million |
| 1 | $16 million |
| 2 | $16 million |
| 3 | $16 million |
| 4 | $16 million |
| 5 | $20 million |

The required return is 10%.

The IRR equation is:

$$
0=-50+\frac{16}{(1+IRR)^1}+\frac{16}{(1+IRR)^2}+\frac{16}{(1+IRR)^3}+\frac{16}{(1+IRR)^4}+\frac{20}{(1+IRR)^5}
$$

Using a financial calculator:

| Key | Input |
|---|---:|
| $CF_0$ | -50 |
| $C01$ | 16 |
| $F01$ | 4 |
| $C02$ | 20 |
| $F02$ | 1 |
| CPT IRR | 19.52% |

Because:

$$
19.52\%>10.00\%
$$

the project should be accepted under the IRR rule.

Check the same project with NPV at the 10% required return:

$$
NPV=-50+\frac{16}{1.10}+\frac{16}{1.10^2}+\frac{16}{1.10^3}+\frac{16}{1.10^4}+\frac{20}{1.10^5}
$$

$$
NPV\approx13.14
$$

The positive NPV confirms the IRR decision.

## Why IRR Is Not the Same as NPV

IRR gives a percentage return. NPV gives the amount of wealth created.

That difference matters. A small project can have a dazzling percentage return and still add fewer dollars of value than a larger project with a lower percentage return. For mutually exclusive projects, choose the project with the highest positive NPV, not necessarily the highest IRR.

Why? Shareholder wealth is measured in dollars, not percentages. If two projects compete for the same slot, capital, facility, or management attention, the best project is the one that adds the most value after discounting at the correct opportunity cost of capital.

## Reinvestment Assumption

IRR implicitly assumes interim cash flows can be reinvested at the IRR. NPV assumes interim cash flows can be reinvested at the required return.

| Method | Implicit reinvestment rate | Why it matters |
|---|---|---|
| [[Net present value|NPV]] | Required return / cost of capital | Usually more realistic because it reflects market opportunity cost |
| [[Internal rate of return|IRR]] | Project IRR | Can be unrealistic when IRR is very high or very low |

This is one reason NPV is theoretically superior. If a project has a 35% IRR, it does not mean the firm can keep reinvesting every interim dollar at 35%. The firm may only be able to redeploy capital at its 10% cost of capital.

The exam implication:

```text
IRR is intuitive.
NPV is the value-maximizing rule.
```

## Multiple IRR and No IRR Problems

IRR behaves well when cash flows are conventional:

```text
Negative, positive, positive, positive
```

There is one sign change, so there is usually one economically meaningful IRR.

IRR can break when cash flows are non-conventional:

```text
Negative, positive, positive, negative
```

That pattern might occur when a project requires environmental cleanup, decommissioning, restructuring, or a large terminal outflow. More than one sign change can produce more than one IRR.

Why? The IRR equation is a polynomial. Depending on the cash flow pattern, the NPV profile can cross zero more than once.

```text
One zero crossing  -> one IRR
Two zero crossings -> two IRRs
No zero crossing   -> no IRR
```

When cash flows are non-conventional, use NPV instead of trying to force an IRR interpretation.

## NPV Profile and Ranking Conflicts

An [[NPV profile]] plots a project's NPV against different discount rates. The IRR is where the profile crosses the horizontal axis.

Ranking conflicts occur when:

| Cause | What happens | Why IRR misleads |
|---|---|---|
| Scale difference | Smaller project has higher percentage return | IRR ignores how many dollars can be invested |
| Timing difference | One project pays earlier, another pays later | IRR and NPV react differently as discount rates change |
| Non-conventional cash flows | Cash flow signs change more than once | IRR may be multiple or nonexistent |
| Mutually exclusive choice | Only one project can be selected | Highest IRR may not maximize wealth |

The crossover rate is the discount rate at which two projects have the same NPV. Below or above that rate, the NPV ranking can switch. CFA may ask which project to choose at a given cost of capital; use the NPV at that cost of capital.

## Calculator Setup

On a TI BA II Plus-style calculator:

```text
CF
2nd CLR WORK
CF0 = initial investment, usually negative
C01 = first cash flow
F01 = frequency if repeated
C02 = next different cash flow
F02 = frequency
IRR
CPT
```

Common input traps:

| Trap | Correct setup |
|---|---|
| Forgetting the sign of $CF_0$ | Initial investment is negative |
| Entering repeated cash flows one by one when frequency works | Use frequency to save time |
| Leaving old cash flows in the calculator | Clear work before entering the new problem |
| Treating IRR as annual when periods are not annual | Match the cash flow period |
| Accepting IRR blindly for non-conventional cash flows | Check sign changes |

## IRR in Level II Contexts

IRR appears in more places than capital budgeting.

| Context | How IRR appears |
|---|---|
| [[Capital budgeting]] | Project return compared with hurdle rate |
| [[Cost of equity]] using multi-stage cash flows | Discount rate that equates current price to future dividends and terminal value |
| [[Equity risk premium]] estimates | Implied required return minus risk-free rate |
| [[Yield to maturity]] | Bond YTM is the IRR of promised bond cash flows |
| [[Rate implicit in the lease]] | Lease discount rate is solved as an IRR on lease payments and residual value |
| [[Money-weighted return]] | Portfolio IRR based on timing and size of investor cash flows |

The unifying idea is always the same:

```text
Given price/outlay today and cash flows over time,
solve for the rate that makes PV benefits equal PV costs.
```

## Exam Traps

| Trap | Why it is tempting | Correct exam reflex |
|---|---|---|
| Choosing the highest IRR for mutually exclusive projects | Highest percentage feels best | Choose highest NPV at the required return |
| Treating IRR as value created | IRR is quoted like performance | NPV measures dollar wealth creation |
| Ignoring non-conventional cash flows | Calculator still returns something | Count sign changes before trusting IRR |
| Assuming reinvestment at IRR is realistic | IRR is the project return | NPV's cost-of-capital reinvestment assumption is usually better |
| Comparing IRRs across different time periods | Percentages look comparable | Match periodicity |
| Forgetting that IRR is a break-even rate | IRR feels like a profit amount | IRR is the rate where NPV equals zero |

## Memory Hooks

IRR is the "zero-NPV rate."

Use this ladder:

```text
Cash flows -> NPV equation -> set NPV to zero -> solve discount rate -> compare with hurdle rate
```

Use this decision rule:

```text
Independent + conventional cash flows: IRR > required return means accept.
Mutually exclusive projects: NPV wins.
Non-conventional cash flows: distrust IRR, use NPV.
```

And remember the philosophical difference:

```text
IRR tells you the rate.
NPV tells you the dollars.
Shareholders eat dollars, not percentages.
```

## Related Concepts

- [[Net present value]]
- [[NPV profile]]
- [[Capital budgeting]]
- [[Cost of capital]]
- [[Required rate of return]]
- [[Opportunity cost of capital]]
- [[Money-weighted return]]
- [[Yield to maturity]]
- [[Rate implicit in the lease]]
- [[Hurdle rate]]
- [[Modified internal rate of return]]
