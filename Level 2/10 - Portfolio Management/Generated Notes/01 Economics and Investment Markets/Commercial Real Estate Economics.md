---
title: Commercial Real Estate Economics
subject: Portfolio Management
tags: [CFA-L2, portfolio-management, economics, commercial-real-estate, real-estate, risk-premiums]
aliases: [CRE Economics, Commercial Real Estate Risk Premiums, Real Estate Business Cycle Effects, Cap Rate and NOI Growth]
---

# Commercial Real Estate Economics

## Intuition

Commercial real estate is part bond, part equity, and part illiquidity problem.

It is bond-like because leases create contractual rental cash flows. It is equity-like because property values, vacancies, rents after lease expiration, and terminal values move with the economy. It is illiquid because selling a building is slow, costly, and uncertain.

That mix is why real estate requires several risk premiums at once.

See: [[Economics and Investment Markets Framework]] · [[Consumption Hedging and Equity Risk Premium]] · [[Business Cycle Effects on Bonds Credit Spreads and Multiples]]

## Bond-Like Features

Commercial property leases create rental income streams.

If a tenant signs a long-term lease, the landlord receives scheduled payments much like a bondholder receives coupons.

Bond-like drivers:

- contractual rent,
- lease maturity,
- tenant credit quality,
- default risk,
- interest-rate sensitivity.

Tenant credit quality matters because rent is only as reliable as the tenant's ability and willingness to pay.

## Tenant Credit Premium

A lease can be viewed as a credit exposure to the tenant.

If the tenant is financially strong, expected rent cash flows are more secure. If the tenant is weak or highly cyclical, the landlord bears higher default and vacancy risk.

So the real estate discount rate includes a tenant credit premium:

$$
\text{Credit premium} \uparrow \quad \Rightarrow \quad \text{Property value} \downarrow
$$

## Equity-Like Features

Commercial real estate is equity-like because the owner bears residual value risk.

Equity-like drivers:

- future market rents,
- occupancy rates,
- lease rollover risk,
- demand for the location,
- terminal sale price,
- capitalization rates,
- business-cycle sensitivity.

Even if current rental cash flows are stable, the building's market value can change sharply when discount rates, financing conditions, and growth expectations change.

## Cash Flows vs Property Values

This is the main exam distinction.

| Component | Business-cycle sensitivity | Why |
|---|---|---|
| **Rental cash flows under existing leases** | Lower | Lease contracts lock in payments |
| **Property values** | Higher | Cap rates, expected rents, vacancies, and terminal values change with the economy |

Exam trap:

> Commercial real estate cash flows may be relatively stable, but commercial real estate values are cyclical.

## Illiquidity Premium

Real estate is illiquid because properties are:

- heterogeneous,
- location-specific,
- expensive to inspect and value,
- costly to transact,
- slow to finance,
- difficult to sell quickly without a price concession.

Investors require an illiquidity premium for locking up capital:

$$
\text{Illiquidity premium} \uparrow \quad \Rightarrow \quad \text{Required return} \uparrow \quad \Rightarrow \quad \text{Value} \downarrow
$$

## Discount Rate Components

A simplified real estate required return can include:

$$
\text{Required return}
= R_F
+ \text{term premium}
+ \text{tenant credit premium}
+ \text{equity/property risk premium}
+ \text{illiquidity premium}
$$

| Component | What it compensates |
|---|---|
| Default-free rate | Time value of money |
| Term premium | Long-lived cash-flow uncertainty |
| Credit premium | Tenant default and lease-payment risk |
| Equity/property risk premium | Uncertain terminal value, rents, vacancies, and economic sensitivity |
| Illiquidity premium | Difficulty selling the property quickly at fair value |

## Cap Rate and Expected Return

A common real estate return approximation is:

$$
E(R_{RE}) = \text{Cap rate} + \text{NOI growth rate} - \%\Delta \text{Cap rate}
$$

where:

| Term | Meaning |
|---|---|
| Cap rate | Current income yield, roughly NOI / property value |
| NOI growth | Expected growth in net operating income |
| $\%\Delta$ Cap rate | Expected percentage change in cap rate |

### The minus-sign trap

If cap rates fall, property values rise.

Example:

- Cap rate = 6%.
- NOI growth = 2%.
- Cap rate expected to decline by 5%.

Then:

$$
E(R_{RE}) = 6\% + 2\% - (-5\%) = 13\%
$$

The cap-rate decline adds to return because the terminal value rises.

If cap rates rise by 5%:

$$
E(R_{RE}) = 6\% + 2\% - 5\% = 3\%
$$

The cap-rate increase subtracts from return.

## Consumption-Hedging Comparison

Real estate has mixed consumption-hedging properties.

### Better than equities in one way

Existing leases can make rental income more stable than corporate earnings during a recession.

### Still weak in another way

Property values often fall in downturns because:

- vacancy expectations rise,
- tenant credit risk increases,
- financing becomes harder,
- required returns rise,
- cap rates rise.

So commercial real estate is not a strong consumption hedge overall. It often requires a risk premium that can be close to the equity risk premium.

## Worked Example: Office Building in a Recession

An office building is fully leased for 10 years to an investment-grade tenant.

During a recession:

- The tenant keeps paying rent.
- Near-term rental cash flow remains stable.
- But buyers demand a higher cap rate.
- Financing is scarcer.
- Expected future market rents fall.

Result:

| Component | Likely effect |
|---|---|
| Current lease cash flow | Stable |
| Tenant credit spread | May widen slightly or remain manageable |
| Cap rate | Rises |
| Property value | Falls |
| Liquidity | Worsens |

The building can have stable income and still lose market value.

## Exam Traps

| Trap | Correct response |
|---|---|
| Say commercial real estate is purely bond-like | It has bond-like lease cash flows but equity-like terminal value |
| Say commercial real estate is purely equity-like | Existing leases make near-term cash flows more stable than equity earnings |
| Treat rental cash flows and property values as equally cyclical | Cash flows can be stable; values are more cyclical |
| Forget tenant credit quality | A lease is only as good as the tenant |
| Forget illiquidity premium | Real estate requires compensation for slow and costly sale |
| Use the wrong sign on cap-rate change | Expected return subtracts $\%\Delta$ cap rate |
| Assume stable rents mean low interest-rate risk | Long-lived assets can have high effective duration |

## Memory Hook

> **Rent is bond-like. Terminal value is equity-like. Sale process is illiquid.**

For cap rates:

> **Cap rate down, price up, return up. Cap rate up, price down, return down.**

## Exam-Day Checklist

1. Separate current lease cash flows from property value.
2. Check tenant credit quality.
3. Identify whether cap rates are rising or falling.
4. Include illiquidity in required return.
5. For consumption hedging, ask whether the asset pays off in bad times.
6. If using expected return, apply:

$$
E(R_{RE}) = \text{Cap rate} + \text{NOI growth} - \%\Delta \text{Cap rate}
$$

## Related Concepts

- [[Economics and Investment Markets Framework]]
- [[Consumption Hedging and Equity Risk Premium]]
- [[Business Cycle Effects on Bonds Credit Spreads and Multiples]]
- [[Credit spreads]]
- [[Risk Premium]]
- [[Yield Curve]]
