---
title: Fixed Income Module Infographic Briefs
subject: Fixed Income
tags: [CFA-L2, FixedIncome, Infographics, VisualStudy]
aliases: [Fixed Income infographics, Fixed Income visual briefs, module infographic briefs]
---

# Fixed Income Module Infographic Briefs

This system of infographic briefs translates the quantitative requirements of CFA Level II Fixed Income into intuitive visual models.

## Infographic 1: The Yield Curve Ecosystem

### A. Infographic Title

**The Term Structure: Three Curves, One Reality**

### B. One-Sentence Core Idea

[[Par curve|Par]], [[Spot curve|spot]], and [[Forward curve|forward]] rates are different ways to view the same market structure for the time value of money.

### C. Visual Metaphor

**The Mountain Hike.** The par curve is the steady trail incline, the spot curve is the elevation at specific peaks, and the forward curve is the steepness of the next step.

### D. Layout Blueprint

Top header:

```text
Term Structure = how rates vary by maturity
```

Main center panel:

```text
Par rates -> bootstrapping -> Spot rates -> forward-rate model -> Forward rates
```

Bottom-left panel:

```text
Bootstrapping Ladder
1-year par = 1-year spot
Use 1-year spot to solve 2-year spot
Use 1-year and 2-year spots to solve 3-year spot
Continue forward
```

Bottom-right panel:

```text
Yield Curve Shapes
Upward
Downward / inverted
Flat
```

### E. Key Formulas And Relationships

Discount factor:

$$
DF_N = \frac{1}{(1+z_N)^N}
$$

Meaning: the price today of one risk-free monetary unit received in $N$ years.

Forward rate model:

$$
(1+z_B)^B = (1+z_A)^A(1+f_{A,B-A})^{B-A}
$$

Meaning: an investor should be indifferent between buying one long zero-coupon bond or buying a shorter zero and locking in the implied forward rate.

Spot rate as chain of forwards:

$$
(1+z_T)^T=(1+z_1)(1+f_{1,1})(1+f_{2,1})\cdots(1+f_{T-1,1})
$$

Meaning: the multi-period spot rate is a geometric average of the one-period rate chain.

### F. Calculation Flow

```text
Par curve given
  |
  v
Set 1-year spot = 1-year par
  |
  v
Use par bond pricing equation
  |
  v
Solve next unknown spot rate
  |
  v
Repeat maturity by maturity
  |
  v
Use spot rates to infer forwards
```

### G. Decision Rules / Comparison Tables

| Curve shape | Same-maturity hierarchy |
|---|---|
| Upward sloping | Forward > Spot > Par |
| Downward / inverted | Par > Spot > Forward |
| Flat | Forward = Spot = Par |

| Rate type | What it answers |
|---|---|
| Par rate | What coupon makes the bond trade at 100? |
| Spot rate | What discount rate prices one cash flow at this maturity? |
| Forward rate | What future rate is implied between two spot dates? |

### H. Common Traps

| Trap | Correction |
|---|---|
| Treating forwards as guaranteed future rates | Forward rates are no-arbitrage implied rates, not certain forecasts. |
| Treating long par rates as spot rates | A par rate is a coupon-bond yield; a spot rate prices one cash flow. |
| Forgetting the one-period exception | For the first annual period, par = spot = forward. |
| Averaging rates arithmetically | Use compounding and discount factors. |

### I. Memory Hooks

```text
Forwards build spots; spots build par.
```

```text
Par is the coupon.
Spot is the cash-flow discounter.
Forward is the future-period bridge.
```

### J. Suggested Visuals

- Triple-curve chart showing par, spot, and forward curves on an upward-sloping curve.
- Rate triangle with arrows:

```text
Par -> Spot -> Forward
```

- Bootstrapping ladder from 1-year to 5-year maturities.
- Timeline for $f_{2,1}$ showing a one-year loan beginning two years from now.

### K. Color / Icon Coding

Use **blue** for benchmark rates and term structure.

Icons:

| Icon | Meaning |
|---|---|
| Compass | Direction and curve shape |
| Ladder | Bootstrapping |
| Clock | Maturity and forward-start dates |

### L. Mini Self-Check

- If the spot curve is upward sloping, why must forward rates sit above spot rates?
- Why does a par rate differ from a same-maturity spot rate?
- How do you bootstrap a 2-year spot rate from a 2-year par bond?
- What does $f_{2,1}$ mean?

## Infographic 2: The Lattice Machine

### A. Infographic Title

**Arbitrage-Free Framework: The Binomial Tree**

### B. One-Sentence Core Idea

The arbitrage-free framework values bonds by building a rate model that matches current market prices and then discounting cash flows through possible future rate paths.

### C. Visual Metaphor

**The Decision Tree.** Each node is a fork where future rates can move up or down, and valuation works backward from known future cash flows.

### D. Layout Blueprint

Top header:

```text
No arbitrage = same cash flows, same value
```

Center panel:

```text
3-period binomial interest rate tree
Root rate -> up/down nodes -> recombining paths
```

Left sidebar:

```text
Model Shop
Equilibrium models
Arbitrage-free models
```

Bottom panel:

```text
Backward induction
Start at maturity -> move backward -> average and discount -> value today
```

### E. Key Formulas And Relationships

Backward induction:

$$
V_{\text{node}}
=
\frac{0.5(V_u+CF_u)+0.5(V_d+CF_d)}{1+r_{\text{node}}}
$$

Meaning: average the future node values and cash flows under risk-neutral probabilities, then discount at the current node rate.

Lognormal rate spacing:

$$
R_u = R_d e^{2\sigma\sqrt{t}}
$$

Meaning: volatility controls the width of the tree; calibration controls the level.

Arbitrage-free price:

$$
V_{\text{model}} = V_{\text{market benchmark}}
$$

Meaning: the calibrated tree must reproduce benchmark bond prices.

### F. Calculation Flow

```text
Current benchmark curve
  |
  v
Assume volatility
  |
  v
Build rate tree
  |
  v
Calibrate tree to benchmark bond prices
  |
  v
Place bond cash flows at terminal nodes
  |
  v
Backward induction
  |
  v
Value today
```

### G. Decision Rules / Comparison Tables

| Model | Type | Key feature |
|---|---|---|
| Vasicek | Equilibrium | Mean-reverting, constant volatility, negative rates possible |
| Cox-Ingersoll-Ross | Equilibrium | Mean-reverting, volatility linked to rate level, nonnegative rates |
| Ho-Lee | Arbitrage-free | Fits current curve, normally distributed rates |
| Kalotay-Williams-Fabozzi | Arbitrage-free | Lognormal rates, nonnegative rates |

| Method | Best use | Limitation |
|---|---|---|
| Spot-rate pricing | Option-free fixed cash flows | Cannot handle path-dependent exercise |
| Binomial tree | Embedded options with recombining paths | Weak for path-dependent cash flows like MBS |
| Monte Carlo | Path-dependent securities | Simulation error and computational complexity |

### H. Common Traps

| Trap | Correction |
|---|---|
| Thinking calibration is optional | Calibration is what makes the tree arbitrage-free. |
| Using a binomial tree for MBS prepayments | MBS cash flows depend on path history, so Monte Carlo is usually preferred. |
| Treating 50/50 probabilities as real-world forecasts | They are risk-neutral valuation probabilities. |
| Forgetting volatility affects node dispersion | Higher volatility widens the tree. |

### I. Memory Hooks

```text
Calibrate first, value second.
```

```text
Backward for price; forward for paths.
```

```text
Volatility sets width. Calibration sets height.
```

### J. Suggested Visuals

- Recombining binomial tree with up/down paths.
- Gear diagram labeled "calibration engine."
- Balance scale showing model value equals market benchmark price.
- Side-by-side tree versus Monte Carlo path cloud.

### K. Color / Icon Coding

Use **green** for valuation machinery and arbitrage-free logic.

Icons:

| Icon | Meaning |
|---|---|
| Gear | Valuation engine |
| Tree | Binomial lattice |
| Balance scale | No-arbitrage equality |

### L. Mini Self-Check

- Why must the interest rate tree be calibrated?
- What does backward induction do?
- Why does higher volatility widen the tree?
- Why is Monte Carlo preferred for mortgage-backed securities?

## Infographic 3: The Option Blueprint

### A. Infographic Title

**Bonds With Embedded Options: Add, Subtract, And Exercise**

### B. One-Sentence Core Idea

Bonds with embedded options are straight bonds plus or minus option value, depending on whether the option belongs to the investor or issuer.

### C. Visual Metaphor

**The Modular Toolkit.** Start with a straight bond frame, then bolt on an investor option or subtract an issuer option.

### D. Layout Blueprint

Top panel:

```text
Straight bond as base object
```

Middle panel:

```text
Callable bond = straight bond - issuer call
Putable bond = straight bond + investor put
Capped floater = straight floater - issuer cap
Floored floater = straight floater + investor floor
Convertible = straight bond + investor stock call
```

Center visual:

```text
Interest rate tree with node-by-node exercise checks
```

Bottom panel:

```text
Effective duration, effective convexity, OAS, volatility effects
```

### E. Key Formulas And Relationships

Callable bond:

$$
V_{\text{callable}}=V_{\text{straight}}-V_{\text{issuer call}}
$$

Putable bond:

$$
V_{\text{putable}}=V_{\text{straight}}+V_{\text{investor put}}
$$

Capped floater:

$$
V_{\text{capped floater}}=V_{\text{straight floater}}-V_{\text{embedded cap}}
$$

Floored floater:

$$
V_{\text{floored floater}}=V_{\text{straight floater}}+V_{\text{embedded floor}}
$$

Convertible minimum value:

$$
\text{Minimum value}=\max(\text{Straight value},\text{Conversion value})
$$

### F. Calculation Flow

```text
Build calibrated interest rate tree
  |
  v
Project cash flows at each node
  |
  v
Check option exercise rule
  |
  v
Callable: use lower of continuation value and call price
Putable: use higher of continuation value and put price
  |
  v
Discount backward to today
```

### G. Decision Rules / Comparison Tables

| Structure | Option owner | Investor value effect |
|---|---|---|
| Callable bond | Issuer | Subtract |
| Putable bond | Investor | Add |
| Capped floater | Issuer | Subtract |
| Floored floater | Investor | Add |
| Convertible conversion option | Investor | Add |

| If volatility rises | Option value | Bond value |
|---|---|---|
| Callable bond | Increases | Decreases |
| Putable bond | Increases | Increases |
| Capped floater | Increases | Decreases |
| Floored floater | Increases | Increases |

### H. Common Traps

| Trap | Correction |
|---|---|
| Adding issuer call value to callable bond | Issuer call hurts investor, so subtract it. |
| Treating callable duration as constant | Callable duration falls when rates fall and the call becomes more likely. |
| Thinking higher volatility always raises bond value | It raises option value; bond value depends on who owns the option. |
| Forgetting convertible bond floor is moving | Straight value changes with rates and credit spreads. |

### I. Memory Hooks

```text
Issuer option: subtract.
Investor option: add.
```

```text
Calls cap upside.
Puts protect downside.
```

```text
Convertible = bond floor + stock upside.
```

### J. Suggested Visuals

- Price-yield curve showing negative convexity for callable bonds.
- Side-by-side callable versus putable payoff behavior.
- Volatility slider increasing option value.
- Convertible spectrum:

```text
Busted convertible -> hybrid -> common stock equivalent
```

- Node decision boxes inside an interest rate tree.

### K. Color / Icon Coding

Use **orange** for optionality.

Icons:

| Icon | Meaning |
|---|---|
| Switch | Exercise choice |
| Lock | Cap/call restriction |
| Shield | Put/floor protection |
| Stock certificate | Conversion option |

### L. Mini Self-Check

- Why does a callable bond trade below an otherwise identical straight bond?
- What happens to callable bond value when volatility increases?
- What is the minimum value of a convertible bond?
- Why does a capped floater hurt the investor?

## Infographic 4: The Credit Lens

### A. Infographic Title

**Credit Analysis: Probability, Loss, And Recovery**

### B. One-Sentence Core Idea

Credit analysis estimates how default probability, loss severity, recovery, migration risk, and credit spreads reduce the value of risky debt.

### C. Visual Metaphor

**The Safety Net.** Probability of default is the chance of falling, loss given default is how far the fall goes, and recovery rate is how much the net catches.

### D. Layout Blueprint

Top panel:

```text
Credit risk = default probability x loss severity
```

Center panel:

```text
CVA timeline
Expected exposure -> expected loss -> discount -> sum PV losses
```

Right sidebar:

```text
Structural models vs reduced-form models
```

Bottom panel:

```text
Credit spread term structure
Investment grade vs high yield vs distressed
```

### E. Key Formulas And Relationships

Expected loss:

$$
\text{Expected loss}=\text{POD}\times\text{LGD}
$$

Loss given default:

$$
\text{LGD}=\text{Exposure}\times(1-\text{Recovery rate})
$$

Risky bond value:

$$
V_{\text{risky}}=V_{\text{no default}}-\text{CVA}
$$

Credit valuation adjustment:

$$
\text{CVA}=\text{PV of expected credit losses}
$$

### F. Calculation Flow

```text
For each period:
  |
  v
Estimate exposure
  |
  v
Estimate probability of default
  |
  v
Estimate loss given default
  |
  v
Expected loss = POD x LGD
  |
  v
Discount expected loss
  |
  v
Sum PV losses = CVA
  |
  v
Risky value = no-default value - CVA
```

### G. Decision Rules / Comparison Tables

| Feature | Structural models | Reduced-form models |
|---|---|---|
| Default trigger | Assets fall below liabilities | Default arrives as stochastic event |
| Main inputs | Balance sheet, asset value, asset volatility | Market variables, hazard rates, macro variables |
| Default interpretation | Endogenous | Exogenous |
| Best intuition | Firm value as option model | Default intensity process |

| Change | Effect on credit value |
|---|---|
| POD rises | Expected loss rises, risky bond value falls |
| Recovery rate rises | LGD falls, CVA falls, risky bond value rises |
| Credit spread widens | Risky bond value falls |
| Rating migrates down | Price usually falls |

### H. Common Traps

| Trap | Correction |
|---|---|
| Confusing POD and LGD | POD is chance of default; LGD is severity if default occurs. |
| Thinking recovery rate and LGD move together | They move opposite each other. |
| Using YTM alone to measure credit risk | Credit analysis needs default probabilities, recovery, spreads, and migration. |
| Treating credit ratings as cardinal numbers | Ratings are ordinal rankings, not precise default probabilities by themselves. |

### I. Memory Hooks

```text
CVA is the price of credit risk.
```

```text
Expected loss = chance of bad event x size of bad event.
```

```text
Recovery up -> LGD down -> CVA down -> bond value up.
```

### J. Suggested Visuals

- Safety net diagram: default probability as fall probability, recovery as net height.
- CVA timeline with expected losses at each year.
- Structural model balance sheet showing assets versus default barrier.
- Credit spread curve comparing investment grade, high yield, and distressed issuers.
- Transition matrix heatmap for rating migration.

### K. Color / Icon Coding

Use **red** for credit risk and loss.

Icons:

| Icon | Meaning |
|---|---|
| Shield | Recovery / protection |
| Warning triangle | Default risk |
| Heatmap grid | Migration matrix |
| Scale | Structural default barrier |

### L. Mini Self-Check

- If recovery rate rises, what happens to LGD and CVA?
- Why does a downgrade usually reduce bond value?
- How does a structural model define default?
- Why is risky bond value equal to no-default value minus CVA?

## Infographic 5: The CDS Workbench

### A. Infographic Title

**Credit Default Swaps: Trading The Credit Gap**

### B. One-Sentence Core Idea

A [[Credit Default Swap]] lets investors buy or sell credit protection, isolating credit risk from the cash bond.

### C. Visual Metaphor

**The Insurance Policy.** The protection buyer pays periodic premiums; the protection seller pays if a credit event occurs.

### D. Layout Blueprint

Top panel:

```text
Protection buyer vs protection seller
Premium leg vs protection leg
```

Middle panel:

```text
CDS spread, upfront payment, and CDS price
```

Bottom-left panel:

```text
Credit curve views
Steepening
Flattening
Curve trade
```

Bottom-right panel:

```text
Basis trades
Bond spread vs CDS spread
```

### E. Key Formulas And Relationships

Approximate upfront payment:

$$
\text{Upfront payment}
\approx
(\text{CDS spread}-\text{Fixed coupon})\times\text{Duration}
$$

CDS price:

$$
\text{CDS price}=100-\text{Upfront percentage}
$$

Approximate profit from spread change:

$$
\text{Profit}
\approx
\Delta \text{Spread}\times\text{Duration}\times\text{Notional}
$$

Protection payoff after default:

$$
\text{Protection payment}
=
\text{Notional}\times(1-\text{Recovery rate})
$$

### F. Calculation Flow

Settlement after credit event:

```text
Credit event occurs
  |
  v
Determine settlement type
  |
  +-- Physical settlement:
  |     buyer delivers bond, seller pays par
  |
  +-- Cash settlement:
        seller pays par - post-default market value
```

Valuing a spread view:

```text
Take CDS position
  |
  v
Spread changes
  |
  v
Approximate gain/loss = spread change x duration x notional
```

### G. Decision Rules / Comparison Tables

| View | CDS trade |
|---|---|
| Credit quality will worsen | Buy protection / long CDS |
| Credit quality will improve | Sell protection / short CDS |
| Spread will widen | Long protection profits |
| Spread will tighten | Short protection profits |

| Term | Meaning |
|---|---|
| Protection buyer | Pays spread, receives default compensation |
| Protection seller | Receives spread, bears default loss |
| Premium leg | Present value of spread payments |
| Protection leg | Present value of expected default payment |
| CDS basis | CDS spread minus comparable bond spread |

### H. Common Traps

| Trap | Correction |
|---|---|
| Thinking long CDS means bullish on credit | Long CDS means long protection, bearish on credit. |
| Confusing CDS spread with bond coupon | CDS spread is insurance premium for credit protection. |
| Forgetting upfront payment direction | If CDS spread exceeds fixed coupon, protection buyer pays upfront. |
| Treating CDS as interest-rate exposure | CDS isolates credit risk more directly than a cash bond. |

### I. Memory Hooks

```text
Long CDS = long protection = short credit.
```

```text
Buy protection if you fear default.
Sell protection if you trust credit.
```

```text
Pay upfront if market spread > fixed coupon.
```

### J. Suggested Visuals

- Two-way cash-flow diagram:

```text
Buyer -> premium leg -> seller
Seller -> protection leg after default -> buyer
```

- Settlement fork: physical versus cash settlement.
- CDS curve showing near-term and long-term spread changes.
- Basis trade scale comparing CDS spread and cash bond spread.
- Profit/loss arrow for spread widening and tightening.

### K. Color / Icon Coding

Use **purple** for CDS and credit-risk transfer.

Icons:

| Icon | Meaning |
|---|---|
| Handshake | Swap contract |
| Umbrella | Protection |
| Arrows | Two legs of the swap |
| Gauge | Spread movement |

### L. Mini Self-Check

- If you buy CDS protection and spreads widen, do you gain or lose?
- Who receives the default payment?
- What is the difference between physical and cash settlement?
- Why is long CDS economically bearish on the reference credit?

## Unified Fixed Income Infographic System

### Cohesive Story Arc

The five infographics should read as one connected sequence:

```text
Module 1: Build the rate curves.
  |
  v
Module 2: Turn rates into arbitrage-free valuation trees.
  |
  v
Module 3: Add embedded options to the valuation tree.
  |
  v
Module 4: Add default probability, loss severity, and credit spreads.
  |
  v
Module 5: Trade or hedge credit risk using CDS.
```

### Recurring Symbols

| Symbol | Meaning | Modules |
|---|---|---|
| Clock | Time, maturity, forward-start dates | 1, 2, 5 |
| Tree | Rate path / backward induction | 2, 3, 4 |
| Switch | Option exercise | 3 |
| Shield | Protection, recovery, risk transfer | 4, 5 |
| Delta | Sensitivity to rates/spreads | 2, 3, 4, 5 |
| Balance scale | No-arbitrage / value equality | 1, 2, 4 |

### Color System

| Color | Module / concept |
|---|---|
| Blue | Benchmark curves, spot rates, forward rates |
| Green | Arbitrage-free valuation machinery |
| Orange | Embedded options and exercise decisions |
| Red | Credit risk, expected loss, CVA |
| Purple | CDS, credit-risk transfer, basis trades |

### Typography Hierarchy

```text
Large title: module identity
Medium subtitle: one-sentence core idea
Formula boxes: monospaced or high-contrast math treatment
Callout strips: exam traps and memory hooks
Small labels: arrows, node names, timing markers
```

### Formula Treatment

Every formula should sit in a consistent "data box":

```text
Formula
  |
  v
Plain-English meaning
  |
  v
Exam use
```

Example:

```text
V_risky = V_no-default - CVA
Meaning: risky debt is worth less because expected credit losses reduce value.
Exam use: if POD or LGD rises, CVA rises and risky value falls.
```

### Cross-Module Links To Show Visually

```text
Spot rates from Module 1
  -> calibrate trees in Module 2
  -> price embedded options in Module 3
  -> discount expected losses in Module 4
  -> connect credit spreads to CDS in Module 5
```

### Anti-Clutter Rule

Each infographic should show only 5-8 major visual elements:

1. One central metaphor.
2. One formula box cluster.
3. One calculation flow.
4. One comparison table.
5. One exam-trap strip.
6. One memory hook.
7. One cross-module arrow.
8. One mini self-check.
