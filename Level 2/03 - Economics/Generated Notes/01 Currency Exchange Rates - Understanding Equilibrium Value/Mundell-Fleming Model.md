---
title: Mundell-Fleming Model
subject: Economics
tags: [CFA-L2, economics, exchange-rates, monetary-policy, fiscal-policy, capital-flows]
aliases: [Mundell Fleming, Mundell-Fleming, Mundell-Fleming model, Mundell Fleming model, MF model, IS-LM-BP model]
---

# Mundell-Fleming Model

For this note, the relevant LOS is:

> Explain the potential effects of [[Monetary policy|monetary]] and [[Fiscal policy|fiscal policy]] on [[Exchange rate|exchange rates]].

## The Real-World Analogy

Imagine a country as a city with two big policy levers and two gates.

The first lever is [[Monetary policy]]. The central bank can make money cheaper or more expensive by changing [[Interest rate|interest rates]]. If rates rise, financial capital wants to enter the city because investors can earn more. If rates fall, financial capital wants to leave.

The second lever is [[Fiscal policy]]. The government can spend more, tax less, spend less, or tax more. That changes domestic demand. If people and businesses have more income and demand, they often buy more [[Imports|imports]]. If they buy more imports, the country must supply more of its own currency to buy foreign currency. That can weaken the domestic currency.

Now the two gates:

```text
Gate 1: Capital-flow gate
Can investment money enter and leave freely?

Gate 2: Trade-flow gate
Are people buying more imports or selling more exports?
```

The [[Mundell-Fleming Model]] asks:

```text
When policy changes, which gate matters more for the currency?
```

If the capital-flow gate is wide open, investors move money quickly in response to interest-rate differences. The [[Capital account|capital account]] dominates.

If the capital-flow gate is mostly closed, money cannot move as freely across borders. Then changes in spending and imports matter more. The [[Current account|current account]] and [[Trade balance|trade balance]] dominate.

That is the model in one sentence:

> Mundell-Fleming explains how monetary and fiscal policy affect exchange rates through interest rates, capital flows, output, and trade flows, with the result depending heavily on capital mobility.

## One-Minute Version

The [[Mundell-Fleming Model]] is a short-run, open-economy model of exchange rates. It focuses on [[Aggregate demand|aggregate demand]] and assumes the economy has enough slack that output can rise without immediate inflation.

For CFA Level II, the key exam question is usually:

```text
What happens to the domestic currency when monetary or fiscal policy changes?
```

The answer depends on capital mobility.

With high capital mobility:

- Interest-rate changes attract or repel global capital.
- Capital flows dominate trade flows.
- Higher domestic real rates usually appreciate the currency.
- Lower domestic real rates usually depreciate the currency.

With low capital mobility:

- Capital cannot respond strongly to interest-rate differences.
- Trade flows dominate capital flows.
- Expansionary policy tends to increase imports and weaken the currency.
- Restrictive policy tends to reduce imports and strengthen the currency.

The memory hook:

```text
High mobility: follow the rate.
Low mobility: follow the trade balance.
```

## Currency Appreciation and Depreciation Under Capital Mobility

This is the exam hinge:

```text
High capital mobility -> capital flows dominate -> follow interest rates.
Low capital mobility -> trade flows dominate -> follow imports.
```

### High Capital Mobility: Follow The Rate

Under high capital mobility, investors can move money across borders quickly. If domestic real interest rates rise relative to foreign rates, domestic assets become more attractive. Foreign investors need the domestic currency to buy those assets, so demand for the domestic currency rises and the currency appreciates.

```text
Higher domestic real rates
  |
  v
Capital inflows
  |
  v
Demand for domestic currency rises
  |
  v
Domestic currency appreciates
```

If domestic real interest rates fall, the chain reverses.

```text
Lower domestic real rates
  |
  v
Capital outflows or weaker inflows
  |
  v
Demand for domestic currency falls
  |
  v
Domestic currency depreciates
```

That gives the high-mobility shortcut:

| Policy | Main Rate Effect | Domestic Currency Effect |
|---|---|---|
| [[Expansionary monetary policy]] | Rates fall | Depreciates |
| [[Restrictive monetary policy]] | Rates rise | Appreciates |
| [[Expansionary fiscal policy]] | Rates rise from higher government borrowing | Appreciates |
| [[Restrictive fiscal policy]] | Rates fall from lower government borrowing | Depreciates |

The strange result is expansionary fiscal policy. Your instinct may say bigger deficits should weaken the currency. In the long run, that can be true under the [[Portfolio balance approach]]. But the [[Mundell-Fleming Model]] is short run. With high capital mobility, the immediate rate increase can attract enough foreign capital to make the currency appreciate.

### Low Capital Mobility: Follow The Trade Balance

Under low capital mobility, investors cannot easily chase higher yields across borders, or they do not respond strongly to interest-rate differences. The capital-flow channel is weak. The trade channel becomes more important.

Expansionary policy raises domestic income and spending. Some of that extra spending goes to imported goods and services. To buy imports, residents need foreign currency, so they sell domestic currency. That puts depreciation pressure on the domestic currency.

```text
Expansionary policy
  |
  v
Domestic demand rises
  |
  v
Imports rise
  |
  v
Residents sell domestic currency to buy foreign currency
  |
  v
Domestic currency depreciates
```

Restrictive policy works in the opposite direction. Domestic demand falls, imports fall, the trade balance improves, and there is less selling pressure on the domestic currency.

```text
Restrictive policy
  |
  v
Domestic demand falls
  |
  v
Imports fall
  |
  v
Trade balance improves
  |
  v
Domestic currency appreciates
```

That gives the low-mobility shortcut:

| Policy | Main Trade Effect | Domestic Currency Effect |
|---|---|---|
| [[Expansionary monetary policy]] | Demand and imports rise | Depreciates |
| [[Restrictive monetary policy]] | Demand and imports fall | Appreciates |
| [[Expansionary fiscal policy]] | Demand and imports rise | Depreciates |
| [[Restrictive fiscal policy]] | Demand and imports fall | Appreciates |

### The Fiscal Policy Flip

The policy that most often creates wrong answers is fiscal policy:

| Policy | High Capital Mobility | Low Capital Mobility |
|---|---|---|
| Expansionary fiscal policy | Appreciates because higher rates attract capital | Depreciates because higher demand increases imports |
| Restrictive fiscal policy | Depreciates because lower rates repel capital | Appreciates because lower demand reduces imports |

So never answer from the word "expansionary" alone. First ask which channel dominates.

```text
High mobility? Rate channel wins.
Low mobility? Trade channel wins.
```

## High vs Low Capital Mobility

Capital mobility means how easily financial capital can cross borders in response to better returns.

Think of global money like water. If borders are financially open, a small difference in yields can cause money to flow quickly toward the higher-return country. If borders are restricted, the water cannot move freely, so the exchange rate is driven more by the slower movement of goods and services through trade.

The deepest distinction is this:

```text
High capital mobility
  |
  v
Financial investors can move quickly
  |
  v
Interest-rate differences dominate

Low capital mobility
  |
  v
Financial investors cannot move quickly
  |
  v
Trade balance and import demand dominate
```

| Feature | High Capital Mobility | Low Capital Mobility |
|---|---|---|
| Core meaning | Money can enter and leave the country easily | Money is restricted, controlled, or slow to move |
| Typical CFA setting | Developed markets, liquid capital markets, fewer capital controls | Emerging markets, capital controls, less open financial markets |
| Dominant exchange-rate channel | [[Interest rate|Interest rates]] -> [[Capital account|capital flows]] | [[Aggregate demand|Aggregate demand]] -> [[Imports|imports]] -> [[Trade balance]] |
| What you should follow first | The direction of domestic real interest rates | The direction of domestic demand and imports |
| What appreciates the currency | Higher rates that attract capital inflows | Lower demand/imports that improve the trade balance |
| What depreciates the currency | Lower rates that cause capital outflows | Higher demand/imports that worsen the trade balance |
| Main exam trap | Forgetting fiscal expansion can appreciate the currency in the short run | Forgetting fiscal expansion can depreciate the currency when trade dominates |

### Why High Mobility Makes Interest Rates Dominate

With high mobility, international investors can compare domestic and foreign returns almost immediately.

```text
Domestic rates rise
  |
  v
Domestic bonds/deposits/assets become more attractive
  |
  v
Foreign investors buy domestic currency to invest
  |
  v
Domestic currency appreciates
```

This is why, under high capital mobility, the exam often reduces the problem to:

```text
Did the policy mix raise or lower domestic real interest rates?
```

If rates rise, the currency tends to appreciate. If rates fall, the currency tends to depreciate.

### Why Low Mobility Makes Trade Dominate

With low mobility, the interest-rate channel is weak. Even if domestic rates rise, foreign investors may not be able or willing to move much money into the country.

So the exchange-rate pressure comes from trade.

```text
Domestic demand rises
  |
  v
Consumers and firms buy more goods
  |
  v
Some of those goods are imports
  |
  v
Residents need foreign currency to buy imports
  |
  v
They sell domestic currency
  |
  v
Domestic currency depreciates
```

This is why, under low capital mobility, the exam often reduces the problem to:

```text
Did the policy mix increase or decrease domestic demand and imports?
```

If demand and imports rise, the trade balance worsens and the currency tends to depreciate. If demand and imports fall, the trade balance improves and the currency tends to appreciate.

### Same Policy, Opposite Answer

The cleanest way to see the contrast is [[Expansionary fiscal policy]].

| Policy | High Capital Mobility | Low Capital Mobility |
|---|---|---|
| Expansionary fiscal policy | Government borrowing pushes rates up -> capital inflows -> currency appreciates | Higher demand increases imports -> trade balance worsens -> currency depreciates |

Same policy. Different dominant channel. Opposite currency result.

That is the whole reason CFA cares about capital mobility.

## Why CFA Tests This

CFA is testing whether you can connect macro policy to [[Balance of payments|balance of payments]] flows instead of memorizing a policy label.

The exam wants you to think like this:

```text
Policy change
  |
  v
Interest rates and aggregate demand change
  |
  v
Capital flows and trade flows change
  |
  v
Demand/supply for domestic currency changes
  |
  v
Domestic currency appreciates, depreciates, or is indeterminate
```

The hard part is that [[Fiscal policy|fiscal policy]] has two effects that can push the currency in opposite directions:

```text
Expansionary fiscal policy
  |
  +--> Higher government borrowing -> higher rates -> capital inflow -> appreciation pressure
  |
  +--> Higher income/demand -> more imports -> weaker trade balance -> depreciation pressure
```

So the exam often asks: which effect dominates?

The answer:

```text
High capital mobility -> capital-flow effect dominates.
Low capital mobility -> trade-balance effect dominates.
```

## Core Assumptions

The Mundell-Fleming model is powerful because it simplifies the world. But those simplifications matter.

| Assumption | What It Means | Why It Matters |
|---|---|---|
| Short-run model | It explains near-term currency movement, not long-term debt sustainability | Short-run fiscal expansion can appreciate a currency even if long-run deficits later weaken it |
| Aggregate demand focus | The model looks at spending and output demand | It is not mainly a productivity, supply-side, or long-run growth model |
| Slack in the economy | Output can increase without immediate price-level increases | Inflation is not the main transmission channel in this model |
| Flexible exchange rates in the main CFA setup | The exchange rate can move in response to supply and demand | Policy affects the currency instead of being fully offset by intervention |
| Capital mobility matters | Cross-border investment flows may be highly responsive or restricted | This determines whether rate effects or trade effects dominate |

The deepest assumption is about price adjustment.

Mundell-Fleming says:

```text
In the short run, policy affects output and interest rates before it affects prices.
```

Why does that matter? Because if prices instantly adjusted, expansionary monetary policy would quickly become an inflation story. But Mundell-Fleming is not primarily an inflation model. It asks how policy changes interest rates, spending, and cross-border flows in the short run.

That is why it differs from the [[Monetary model]] of exchange rates, which focuses more on money supply, price levels, and inflation.

## The Balance of Payments Link

This model is easier if you anchor it in the [[Balance of payments|balance of payments]].

The exchange rate moves because people need to buy or sell the domestic currency.

```text
Capital inflow
  |
  v
Foreign investors buy domestic assets
  |
  v
They need domestic currency
  |
  v
Demand for domestic currency rises
  |
  v
Domestic currency appreciates
```

```text
More imports
  |
  v
Domestic residents buy foreign goods
  |
  v
They need foreign currency
  |
  v
They sell domestic currency
  |
  v
Domestic currency depreciates
```

So there are two competing exchange-rate channels:

| Channel | Balance of Payments Side | Currency Logic |
|---|---|---|
| Interest-rate/capital-flow channel | [[Financial account]] / capital flows | Higher rates attract capital, increasing demand for the domestic currency |
| Trade/current-account channel | [[Current account]] / trade balance | Higher domestic demand increases imports, increasing supply of the domestic currency |

Mundell-Fleming is really a question about which side of the balance of payments reacts more strongly.

## Monetary Policy

[[Monetary policy]] is the cleaner part of the model because it mainly works through interest rates.

### Expansionary Monetary Policy

Expansionary monetary policy means the central bank makes money easier.

Examples:

- Lower policy rates
- More money supply
- Easier credit conditions

The basic chain is:

```text
Expansionary monetary policy
  |
  v
Lower domestic interest rates
  |
  v
Domestic assets become less attractive
  |
  v
Capital outflows or reduced capital inflows
  |
  v
Less demand for domestic currency
  |
  v
Domestic currency depreciates
```

Why does the currency depreciate?

Because foreign and domestic investors compare returns. If domestic interest rates fall while foreign rates are unchanged, domestic assets now offer a lower return. Investors shift toward higher-yielding foreign assets. To buy foreign assets, they sell domestic currency and buy foreign currency. That increases the supply of domestic currency in the FX market and lowers its value.

The why ladder:

```text
Rule:
Expansionary monetary policy tends to depreciate the domestic currency.

Why:
It lowers domestic interest rates.

Mechanism:
Lower rates reduce demand for domestic financial assets.

Assumption:
Capital can move across borders and investors respond to return differences.

Failure mode:
If capital controls are severe, the capital-flow response is weaker.

Exam implication:
The more mobile capital is, the stronger the depreciation pressure from monetary easing.
```

### Restrictive Monetary Policy

Restrictive monetary policy means the central bank makes money tighter.

Examples:

- Higher policy rates
- Slower money growth
- Tighter credit conditions

The chain reverses:

```text
Restrictive monetary policy
  |
  v
Higher domestic interest rates
  |
  v
Domestic assets become more attractive
  |
  v
Capital inflows
  |
  v
More demand for domestic currency
  |
  v
Domestic currency appreciates
```

Why does the currency appreciate?

Because investors must buy the domestic currency before they can buy domestic bonds, deposits, or other domestic assets. Higher rates pull money into the country. More demand for the currency pushes its value up.

### Monetary Policy Summary

| Monetary Policy | Rate Effect | Capital-Flow Effect | Currency Effect |
|---|---:|---|---|
| Expansionary monetary policy | Rates fall | Capital outflow or weaker inflow | Domestic currency depreciates |
| Restrictive monetary policy | Rates rise | Capital inflow | Domestic currency appreciates |

This part is relatively stable across the model, but the magnitude depends on capital mobility.

## Fiscal Policy

[[Fiscal policy]] is trickier because it has two channels.

Expansionary fiscal policy means:

- Government spending rises, or
- Taxes fall, or
- The budget deficit increases.

Restrictive fiscal policy means:

- Government spending falls, or
- Taxes rise, or
- The budget deficit decreases.

### Expansionary Fiscal Policy: The Two Opposing Forces

Expansionary fiscal policy usually raises aggregate demand.

```text
Government spends more or taxes less
  |
  v
Households/firms have more demand
  |
  v
Output and income rise in the short run
```

That creates the trade-flow effect:

```text
Higher income and spending
  |
  v
More imports
  |
  v
Trade balance worsens
  |
  v
Domestic currency faces depreciation pressure
```

But expansionary fiscal policy can also raise domestic interest rates because larger deficits must be financed.

```text
Larger fiscal deficit
  |
  v
More government borrowing
  |
  v
Upward pressure on domestic interest rates
  |
  v
Capital inflows
  |
  v
Domestic currency faces appreciation pressure
```

So expansionary fiscal policy creates a tug-of-war:

| Force | Direction |
|---|---|
| Higher rates -> capital inflows | Appreciation pressure |
| Higher demand -> more imports | Depreciation pressure |

The winner depends on capital mobility.

### Restrictive Fiscal Policy: The Reverse Tug-of-War

Restrictive fiscal policy usually lowers aggregate demand.

```text
Government spends less or taxes more
  |
  v
Households/firms have less demand
  |
  v
Imports fall
  |
  v
Trade balance improves
  |
  v
Domestic currency faces appreciation pressure
```

But smaller deficits can reduce government borrowing and lower interest rates:

```text
Smaller fiscal deficit
  |
  v
Less government borrowing
  |
  v
Downward pressure on domestic interest rates
  |
  v
Capital outflows
  |
  v
Domestic currency faces depreciation pressure
```

So restrictive fiscal policy also has two forces:

| Force | Direction |
|---|---|
| Lower rates -> capital outflows | Depreciation pressure |
| Lower demand -> fewer imports | Appreciation pressure |

Again, capital mobility determines which force matters more.

## High Capital Mobility

High capital mobility means global investors can move money across borders easily.

This is more typical of developed markets and countries with fewer capital controls.

In this setting, the capital-flow channel dominates.

```text
High capital mobility
  |
  v
Small rate changes can trigger large cross-border flows
  |
  v
Capital-flow effect dominates trade-flow effect
  |
  v
Follow the interest-rate direction
```

### High Mobility Decision Table

| Policy Mix | Interest-Rate Pressure | Dominant Channel | Domestic Currency |
|---|---:|---|---|
| Expansionary monetary + expansionary fiscal | Monetary lowers rates, fiscal raises rates | Mixed | Indeterminate |
| Expansionary monetary + restrictive fiscal | Both tend to lower rates | Capital outflow | Depreciates strongly |
| Restrictive monetary + expansionary fiscal | Both tend to raise rates | Capital inflow | Appreciates strongly |
| Restrictive monetary + restrictive fiscal | Monetary raises rates, fiscal lowers rates | Mixed | Indeterminate |

This is the most important high-mobility table for exam questions.

### Why Expansionary Fiscal Can Appreciate the Currency

This is the part that feels strange at first.

Your instinct may say:

```text
More government spending -> bigger deficit -> bad -> currency down
```

That can be true in the long run, but Mundell-Fleming is a short-run model.

In the short run, with high capital mobility:

```text
Expansionary fiscal policy
  |
  v
More government borrowing
  |
  v
Higher domestic real interest rates
  |
  v
Foreign capital flows in
  |
  v
Investors buy domestic currency
  |
  v
Domestic currency appreciates
```

The trade balance may worsen, but the model says the capital inflow can dominate when capital is highly mobile.

The exam trap is confusing:

```text
Short-run Mundell-Fleming effect
```

with:

```text
Long-run fiscal sustainability effect
```

Those are different models and different time horizons.

## Low Capital Mobility

Low capital mobility means money cannot move freely across borders or does not respond strongly to interest-rate differences.

This is more relevant for economies with capital controls, less integrated financial markets, or weaker investor access.

In this setting, the trade-flow channel dominates.

```text
Low capital mobility
  |
  v
Interest-rate changes do not cause large capital flows
  |
  v
Trade balance effect becomes more important
  |
  v
Follow aggregate demand and imports
```

### Low Mobility Decision Table

| Policy Mix | Aggregate-Demand Pressure | Dominant Channel | Domestic Currency |
|---|---:|---|---|
| Expansionary monetary + expansionary fiscal | Demand rises strongly | Imports rise, trade worsens | Depreciates |
| Expansionary monetary + restrictive fiscal | Mixed | Trade effect unclear | Indeterminate |
| Restrictive monetary + expansionary fiscal | Mixed | Trade effect unclear | Indeterminate |
| Restrictive monetary + restrictive fiscal | Demand falls strongly | Imports fall, trade improves | Appreciates |

Why do both expansionary policies weaken the currency under low capital mobility?

Because both push domestic demand upward. Higher domestic demand means more spending, and some of that spending falls on imported goods. More imports mean domestic residents sell domestic currency to buy foreign currency. That weakens the domestic currency.

Why do both restrictive policies strengthen the currency under low capital mobility?

Because both push domestic demand downward. Lower domestic demand means fewer imports. Fewer imports mean less selling of domestic currency to buy foreign currency. The trade balance improves, and the currency faces appreciation pressure.

## Single-Policy Shortcut Table

This table is useful when a question gives only one policy change.

| Setting | Expansionary Monetary | Restrictive Monetary | Expansionary Fiscal | Restrictive Fiscal |
|---|---|---|---|---|
| High capital mobility | Depreciates | Appreciates | Appreciates | Depreciates |
| Low capital mobility | Depreciates through weaker trade/demand effects | Appreciates through improved trade/demand effects | Depreciates | Appreciates |

The safer CFA way is to think in policy mixes because fiscal and monetary policy often interact. But for single-policy questions, this table gives the default intuition.

## Worked Example 1: High Capital Mobility

Suppose Country A has:

- Floating exchange rate
- High capital mobility
- Current domestic real rate: 2.0%
- Foreign real rate: 2.0%
- Neutral starting point

Now the central bank tightens monetary policy and the government expands fiscal policy.

Assume:

- Restrictive monetary policy raises the domestic real rate by 1.0%.
- Expansionary fiscal policy raises the domestic real rate by 0.8% because the government borrows more.

Step 1: Compute the new domestic real-rate pressure.

$$
\Delta r_{domestic} = +1.0\% + 0.8\% = +1.8\%
$$

Step 2: Compare domestic and foreign rates.

$$
r_{domestic,new} = 2.0\% + 1.8\% = 3.8\%
$$

$$
r_{foreign} = 2.0\%
$$

Step 3: Compute the rate differential.

$$
\text{Rate differential} = 3.8\% - 2.0\% = +1.8\%
$$

Step 4: Interpret the currency effect.

Domestic assets now offer a higher real return. With high capital mobility, capital flows into Country A.

```text
Higher domestic real rates
  |
  v
Capital inflow
  |
  v
Foreign investors buy domestic currency
  |
  v
Domestic currency appreciates
```

Conclusion:

> Under high capital mobility, restrictive monetary policy plus expansionary fiscal policy is strongly bullish for the domestic currency.

## Worked Example 2: Low Capital Mobility

Suppose Country B has:

- Floating exchange rate
- Low capital mobility
- Capital controls
- Imports equal 30% of domestic demand

The government and central bank both become expansionary.

Assume:

- Expansionary fiscal policy increases domestic demand by 4%.
- Expansionary monetary policy increases domestic demand by 3%.
- Imports are 30% of domestic demand.

Step 1: Add the demand effects.

$$
\Delta \text{Domestic demand} = 4\% + 3\% = 7\%
$$

Step 2: Estimate import demand pressure.

If imports are 30% of demand, then the import component of the demand increase is:

$$
\Delta \text{Import pressure} = 7\% \times 30\% = 2.1\%
$$

Step 3: Interpret the trade balance.

Higher import pressure means residents need more foreign currency to buy foreign goods.

```text
Higher domestic demand
  |
  v
More imports
  |
  v
More demand for foreign currency
  |
  v
More supply of domestic currency
  |
  v
Domestic currency depreciates
```

Conclusion:

> Under low capital mobility, expansionary monetary plus expansionary fiscal policy is bearish for the domestic currency because the trade-balance channel dominates.

## Why This Can Conflict With Interest Rate Parity

A common confusion:

> Wait, under [[Uncovered interest rate parity|uncovered interest rate parity]], high-interest-rate currencies are expected to depreciate. But Mundell-Fleming says higher rates can make a currency appreciate. Why?

They are answering different questions under different assumptions.

Under [[Uncovered interest rate parity]]:

```text
Higher nominal interest rate
  |
  v
Often reflects higher expected inflation or currency risk
  |
  v
Currency expected to depreciate enough to offset the higher yield
```

Under Mundell-Fleming:

```text
Higher real interest rate from policy
  |
  v
Domestic assets become more attractive now
  |
  v
Capital flows in
  |
  v
Currency appreciates in the short run
```

The key distinction is:

| Framework | Main Driver | Currency Logic |
|---|---|---|
| [[Uncovered interest rate parity]] | Expected return parity and expected depreciation | Higher-yielding currency may be expected to depreciate |
| [[Mundell-Fleming Model]] | Short-run capital flows from policy-driven real-rate changes | Higher real rates can attract capital and appreciate the currency |

Do not mix the assumptions. CFA loves this trap.

## Short Run vs Long Run

Mundell-Fleming is mainly short run.

That matters most for fiscal policy.

### Short Run: Mundell-Fleming

With high capital mobility:

```text
Expansionary fiscal policy
  |
  v
Higher rates
  |
  v
Capital inflow
  |
  v
Currency appreciates
```

### Long Run: Portfolio Balance Approach

But if fiscal expansion creates persistent deficits:

```text
Persistent fiscal deficits
  |
  v
Rising government debt supply
  |
  v
Investors demand higher risk premium or refuse to fund deficits
  |
  v
Fear of debt monetization or fiscal stress
  |
  v
Currency depreciates
```

So the same policy can have opposite time-horizon effects:

| Time Horizon | Model | Expansionary Fiscal Policy With High Capital Mobility |
|---|---|---|
| Short run | [[Mundell-Fleming Model]] | Currency may appreciate because rates rise and capital flows in |
| Long run | [[Portfolio balance approach]] | Currency may depreciate if debt becomes unsustainable |

Memory hook:

```text
Fiscal expansion can be short-run sugar, long-run debt.
```

## Fixed Exchange Rates and the Impossible Trinity

The main CFA Mundell-Fleming setup often focuses on flexible exchange rates, but the fixed-rate implication is important.

Under a [[Fixed exchange rate|fixed exchange rate]], the currency is not allowed to move freely. If policy creates depreciation pressure, the central bank must intervene to defend the peg.

Example:

```text
Expansionary monetary policy
  |
  v
Lower rates
  |
  v
Capital outflow
  |
  v
Depreciation pressure
  |
  v
Central bank must buy domestic currency / sell foreign reserves
  |
  v
Money supply contracts back
  |
  v
Original monetary expansion is offset
```

This leads to the [[Impossible trinity|impossible trinity]]:

```text
A country cannot simultaneously have:

1. Free capital mobility
2. Fixed exchange rate
3. Independent monetary policy
```

It can choose only two.

Why?

Because if capital is mobile and the exchange rate is fixed, interest-rate changes trigger capital flows that force the central bank to intervene. That intervention reverses independent monetary policy.

## Developed vs Emerging Market Intuition

This is not a perfect rule, but it is the CFA intuition:

| Economy Type | Capital Mobility | More Relevant Channel | Typical Exam Lens |
|---|---|---|---|
| Developed market / G-10 style economy | High | Interest-rate/capital-flow channel | Follow policy impact on real rates |
| Emerging market with capital controls | Low | Trade/current-account channel | Follow aggregate demand and imports |

The deeper logic:

Developed markets usually have liquid capital markets, fewer barriers to international investment, and credible institutions. A small change in domestic rates can move a large amount of money.

Emerging markets may restrict capital flows to reduce instability from hot money. If capital is less free to move, the exchange rate responds more through trade: imports, exports, and current-account pressure.

## Full Decision Framework

When you see a Mundell-Fleming question, use this exact process.

### Step 1: Identify the Exchange Rate Regime

Ask:

```text
Is the currency floating or fixed?
```

If floating, the currency can appreciate or depreciate.

If fixed, policy pressure may show up as central bank intervention, reserve changes, or loss of monetary independence.

### Step 2: Identify Capital Mobility

Ask:

```text
Are capital flows high/mobile/free, or low/restricted/controlled?
```

High mobility:

```text
Follow interest rates and capital flows.
```

Low mobility:

```text
Follow aggregate demand, imports, and the trade balance.
```

### Step 3: Identify the Policy Mix

Classify monetary policy:

| Monetary Policy | Direction |
|---|---|
| Expansionary/easy/loose | Rates down |
| Restrictive/tight | Rates up |

Classify fiscal policy:

| Fiscal Policy | Demand Effect | Rate Effect |
|---|---|---|
| Expansionary fiscal | Demand up, imports up | Rates up from borrowing |
| Restrictive fiscal | Demand down, imports down | Rates down from less borrowing |

### Step 4: Apply the Dominant Channel

High mobility:

```text
Higher rates -> capital inflow -> appreciation
Lower rates -> capital outflow -> depreciation
```

Low mobility:

```text
Higher demand -> more imports -> depreciation
Lower demand -> fewer imports -> appreciation
```

### Step 5: Check for Indeterminate Cases

Indeterminate usually means one policy pushes the currency up while the other pushes it down.

High capital mobility:

| Policy Mix | Result |
|---|---|
| Expansionary monetary + expansionary fiscal | Indeterminate |
| Restrictive monetary + restrictive fiscal | Indeterminate |

Low capital mobility:

| Policy Mix | Result |
|---|---|
| Expansionary monetary + restrictive fiscal | Indeterminate |
| Restrictive monetary + expansionary fiscal | Indeterminate |

## The Two Big Tables to Memorize

### High Capital Mobility

Follow the interest-rate/capital-flow channel.

| | Expansionary Fiscal | Restrictive Fiscal |
|---|---|---|
| Expansionary Monetary | Indeterminate | Domestic currency depreciates |
| Restrictive Monetary | Domestic currency appreciates | Indeterminate |

### Low Capital Mobility

Follow the trade/current-account channel.

| | Expansionary Fiscal | Restrictive Fiscal |
|---|---|---|
| Expansionary Monetary | Domestic currency depreciates | Indeterminate |
| Restrictive Monetary | Indeterminate | Domestic currency appreciates |

## Common Wrong Reasoning

### Wrong Reasoning 1: Expansionary Fiscal Always Weakens a Currency

This is too simple.

Expansionary fiscal policy can weaken a currency through a worse trade balance, but with high capital mobility it can strengthen the currency in the short run because higher rates attract capital inflows.

Correct version:

```text
Expansionary fiscal + high capital mobility -> appreciation pressure
Expansionary fiscal + low capital mobility -> depreciation pressure
```

### Wrong Reasoning 2: Higher Interest Rates Always Mean Future Depreciation

That mixes Mundell-Fleming with [[Uncovered interest rate parity]].

Correct version:

```text
Mundell-Fleming: higher policy-driven real rates can appreciate the currency now.
UIP: higher nominal yields may be offset by expected depreciation.
```

### Wrong Reasoning 3: Monetary and Fiscal Policy Work the Same Way

They do not.

Monetary policy is mostly an interest-rate/capital-flow story.

Fiscal policy is a two-channel story:

```text
Rates/capital flows
and
Demand/imports/trade balance
```

### Wrong Reasoning 4: Long-Run Debt Effects Are Part of Mundell-Fleming

They are not.

Mundell-Fleming is short run. Long-run fiscal deficit effects belong more to the [[Portfolio balance approach]].

### Wrong Reasoning 5: Capital Mobility Is a Detail

It is not a detail. It is the switch that changes the answer.

```text
High mobility -> rate effect wins.
Low mobility -> trade effect wins.
```

## Minimum Memorization

If you only memorize one thing, memorize this:

```text
High capital mobility:
Follow rates.
Tight money + expansionary fiscal = strongest appreciation.
Easy money + restrictive fiscal = strongest depreciation.

Low capital mobility:
Follow trade balance.
Both expansionary = depreciation.
Both restrictive = appreciation.
```

And this:

```text
Fiscal expansion:
Short run with high capital mobility -> can appreciate.
Long run with debt concerns -> can depreciate.
```

## Can I Solve This?

Use these questions to test yourself.

1. A developed market with a floating exchange rate adopts restrictive monetary policy and expansionary fiscal policy. What happens to the currency?

Answer: It likely appreciates. Both policies tend to raise domestic real interest rates, attracting capital inflows under high capital mobility.

2. An emerging market with capital controls adopts expansionary monetary and fiscal policy. What happens to the currency?

Answer: It likely depreciates. With low capital mobility, the trade-balance channel dominates. Expansionary policy raises demand and imports, worsening the trade balance.

3. Why can expansionary fiscal policy appreciate a currency in the short run but depreciate it in the long run?

Answer: In the short run, expansionary fiscal policy can raise rates and attract capital inflows. In the long run, persistent deficits can increase debt sustainability concerns, risk premiums, or fears of debt monetization, weakening the currency.

4. Under high capital mobility, why is expansionary monetary plus restrictive fiscal bearish for the currency?

Answer: Both policies tend to lower domestic real rates. Expansionary monetary policy lowers rates directly, and restrictive fiscal policy lowers borrowing pressure. Lower rates create capital outflows and depreciation pressure.

5. Under low capital mobility, why is restrictive monetary plus expansionary fiscal indeterminate?

Answer: The policies have opposing effects on aggregate demand and the trade balance. Restrictive monetary policy reduces demand/imports, while expansionary fiscal policy increases demand/imports. The net trade effect is unclear.

## Related Concepts

- [[Balance of payments]]
- [[Balance of Payments Flows and Exchange Rates]]
- [[Current account]]
- [[Financial account]]
- [[Capital account]]
- [[Exchange rate]]
- [[Monetary policy]]
- [[Fiscal policy]]
- [[Expansionary monetary policy]]
- [[Restrictive monetary policy]]
- [[Expansionary fiscal policy]]
- [[Trade balance]]
- [[Capital mobility]]
- [[Interest rate parity]]
- [[Uncovered interest rate parity]]
- [[Portfolio balance approach]]
- [[Monetary model]]
- [[Dornbusch overshooting model]]
- [[Fixed exchange rate]]
- [[Floating exchange rate]]
- [[Impossible trinity]]
