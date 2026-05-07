---
title: "Economics"
subject: "Economics"
tags: [CFA-L2, economics]
aliases: []
---

# Economics

*CFA Level II — Schweser Notes 2025*

---

## Readings

- [[#Reading 5 — Currency Exchange Rates: Understanding Equilibrium Value|Reading 5: Currency Exchange Rates: Understanding Equilibrium Value]]
- [[#Reading 6 — Economic Growth|Reading 6: Economic Growth]]

---

# Reading 5 — Currency Exchange Rates: Understanding Equilibrium Value


> [!tip] Exam Focus
> There’s no fluff here; you need it all. Take it slow and get a good understanding of quotes,
> currency cross rates, [[Triangular Arbitrage|triangular arbitrage]]ge|arbitrage]], all parity conditions, and their interrelationships.
> Forecasting exchange rates has important applications for [[Valuation|valuation]] (which is the focus of
> Level II). Accordingly, theories of [[Exchange Rate]] determination as well as factors influencing
> exchange rates are all important. Be prepared to identify warning signs of currency crises.


## Module 5.1: Forex Quotes, Spreads, and Triangular Arbitrage


> **LOS 5.a:** Calculate and interpret the [[Bid–offer spread|bid–offer spread]] on a spot or forward
currency quotation and describe the factors that affect the bid–offer
spread.


> [!pnote] Professor's Note
> ***The “bid–offer” spread is also known as the “bid–ask” spread: the terms “ask”***
> ***and “offer” mean the same thing. Accordingly, we will be using them***
> ***interchangeably.***
>
> ***Exchange Rates***
> ***An exchange rate is simply the price of one currency in terms of another. For example, a***
> ***quote of 1.4126 USD/EUR means that each euro costs $1.4126. In this example, the euro is***
> ***called the base currency and the USD the price currency. Hence, a quote is the price of one***
> ***unit of the base currency in terms of the price currency.***
> ***A spot exchange rate is the currency exchange rate for immediate delivery, which for most***
> ***[[Currencies|currencies]] means the exchange of [[Currencies|currencies]] takes place two days after the trade. A***
> ***forward exchange rate is a currency exchange rate for an exchange to be done in the***
> ***future. Forward rates are quoted for various future dates (e.g., 30 days, 60 days, 90 days, or***
> ***one year). A [[Forward contract]] is an agreement to exchange a specific amount of one***
> ***currency for a specific amount of another currency on a future date specified in the***
> ***forward agreement.***
>
> ***Dealer quotes often include both bid and offer (ask) rates. For example, the euro could be***
> ***quoted as $1.4124 − 1.4128. The bid price ($1.4124) is the price at which the dealer will***
> ***buy euros, and the [[Offer price|offer price]] ($1.4128) is the price at which the dealer will sell euros.***
>
> ***Foreign Exchange Spread***
> ***The difference between the offer and [[Bid price|bid price]] is called the spread. Spreads are often***
> ***stated as “pips.” When the spot quote has four decimal places, one pip is 1/10,000. In the***
> ***previous example, the spread is $0.0004 (4 pips) reflecting the dealer’s profit. Dealers***
> ***manage their [[Foreign currency|foreign currency]] inventories by transacting in the [[Interbank market|interbank market]] (think of***
> ***this as a wholesale market for currency). Spreads are narrow in the [[Interbank market|interbank market]].***
> ***The spread quoted by a dealer depends on:***
> ***The spread in an [[Interbank market|interbank market]] for the same currency pair. Dealer spreads vary***
> ***directly with spreads quoted in the [[Interbank market|interbank market]].***
> ***The size of the transaction. Larger, [[Liquidity|liquidity]]-demanding transactions generally get***
> ***quoted a larger spread.***
> ***The relationship between the dealer and client. Sometimes dealers will give favorable***
> ***rates to preferred clients based on other ongoing business relationships.***
> ***The interbank spread on a currency pair depends on:***
> ***[[Currencies|Currencies]] involved. Similar to stocks, high-volume currency pairs (e.g., USD/EUR,***
> ***USD/JPY, and USD/GBP) command lower spreads than do lower-volume currency pairs***
> ***(e.g., AUD/CAD).***
> ***Time of day. The time overlap during the trading day when both the New York and***
> ***London currency markets are open is considered the most liquid time window; spreads***
> ***are narrower during this period than at other times of the day.***
> ***Market [[Volatility|volatility]]. Spreads are directly related to the exchange rate [[Volatility|volatility]] of the***
> ***[[Currencies|currencies]] involved. Higher [[Volatility|volatility]] leads to higher spreads to compensate market***
> ***makers for the increased risk of holding those currencies. Spreads change over time in***
> ***response to [[Volatility|volatility]] changes.***
> ***In addition to these factors, spreads in forward exchange rate quotes increase with***
> ***maturity. The reasons for this are: longer maturity contracts tend to be less liquid,***
> ***counterparty [[Credit risk]] in forward contracts increases with maturity, and [[Interest rate risk]]***
> ***in forward contracts increases with maturity.***
>
> ***Warm-Up: Working with Foreign Exchange Quotes***
> ***Earlier, we stated that a dealer will sell a currency at the [[Ask price|ask price]] and purchase it at the bid***
> ***price. We need to be a bit more specific. For example, imagine that you are given a***
> ***USD/AUD bid and ask quote of 1.0508-1.0510. Investors can buy AUD (i.e., the base***
> ***currency) from the dealer at the [[Ask price|ask price]] of USD 1.0510. Similarly, investors can sell AUD***
> ***to the dealer at the [[Bid price|bid price]] of USD 1.0508. Remember, investors always take a loss due to***
> ***the spread. So the rule is buy the base currency at ask, and sell the base currency at bid.***
>
> ***For transactions in the price currency, we do the opposite. If we need to buy USD (i.e., the***
> ***price currency) using AUD (i.e., selling the base currency), we now use the dealer bid***
> ***quote. Similarly, to sell the price currency, we use the dealer ask quote. So the rule is buy***
> ***the price currency at bid, and sell the price currency at ask.***
> ***Alternatively, it is useful to follow the up-the-bid-and-multiply, down-the-ask-and-divide***
> ***rule. Again given a USD/AUD quote, if you want to convert USD into AUD (you are going***
> ***down the quote—from USD on top to AUD on bottom), use the [[Ask price|ask price]] for that quote.***
> ***Conversely, if you want to convert AUD into USD, you are going up the quote (from bottom***
> ***to top) and, hence, use the [[Bid price|bid price]].***

### Example: Converting currencies using spot rates


A dealer is quoting the AUD/GBP [[Spot rate]] as 1.5060 − 1.5067. How would we:
1. Compute the proceeds of converting 1 million GBP.
2. Compute the proceeds of converting 1 million AUD.
Answer:
1. To convert 1 million GBP into AUD, we go “up the quote” (i.e., from GBP in the
denominator to AUD in the numerator). Hence, we would use the [[Bid price|bid price]] of 1.5060
and multiply.
1 million GBP × 1.5060 = 1,506,000 AUD
2. To convert 1 million AUD into GBP, we go “down the quote” (i.e., from AUD in the
numerator to GBP in the denominator). Hence, we would use the [[Ask price|ask price]] of 1.5067
and divide.
1 million AUD / 1.5067 = 663,702.13 GBP


> **LOS 5.b:** Identify a triangular [[Arbitrage opportunity|arbitrage opportunity]] and calculate its profit, given the bid–
offer quotations for three currencies.

Cross Rate
The cross rate is the exchange rate between two currencies implied by their exchange rates
with a common third currency. It is necessary to use cross rates when there is no active
foreign exchange (FX) market in the currency pair being considered. The cross rate must be
computed from the exchange rates between each of these two currencies and a major
third currency, usually the USD or EUR.
Suppose we have the following quotes:
USD/AUD = 0.60 and MXN/USD = 10.70. What is the cross rate between Australian dollars
and pesos (MXN/AUD)?

So our MXN/AUD cross rate is 6.42 pesos per Australian dollar. The key to calculating cross
rates is to make sure the common currency cancels out.

Cross Rates with Bid–Ask Spreads
Bid–ask spreads complicate the calculation of cross rates considerably. Suppose we are
given three currencies A, B, and C; we can have three pairs of currencies (i.e., A/B, A/C, and

### B/C).

Rules:

To compute the cross rate for A/C, given A/B and B/C, we can follow these rules to obtain
the bid and offer prices. If we are instead given A/B and C/B rates, we will have to make
adjustments to obtain the B/C bid and offer rates from the C/B bid and offer rates, because
A/B × C/B ≠ A/C. The process is as follows:

[[Triangular Arbitrage|Triangular Arbitrage]]ge|Arbitrage]]
Real-world currency dealers will maintain bid/ask quotes that ensure a profit to the dealer,
regardless of which currencies customers choose to trade. If this was not the case,
customers could earn profits through the process of [[Triangular Arbitrage|triangular arbitrage]]ge|arbitrage]]. In triangular
[[Arbitrage|arbitrage]], we begin with three pairs of currencies, each with bid and ask quotes, and
construct a triangle where each node in the triangle represents one currency. To check for
arbitrage opportunities, we go around the triangle clockwise (and later, counterclockwise)
until we reach our starting point. As before, we follow the up-the-bid-and-multiply, downthe-ask-and-divide rule.
The following example will illustrate [[Triangular Arbitrage|triangular arbitrage]].

### Example: Triangular arbitrage


The following quotes are available from the interbank market:
Quotes:

### Usd/Aud 0.6000 − 0.6015


### Usd/Mxn 0.0933 − 0.0935

1. Compute the implied MXN/AUD cross rate.
2. If your dealer quotes MXN/AUD = 6.3000 − 6.3025, is an arbitrage profit possible? If
so, compute the arbitrage profit in USD if you start with USD 1 million.

Answer:
1. To compute implied cross rates, we need:

Since we are given USD/MXN quotes instead of MXN/USD quotes, we first invert
these quotes:

and

Now, the implied cross rates:

2. Since the dealer quote of MXN/AUD = 6.3000 − 6.3025 falls outside of these cross
rates, arbitrage profit may be possible (we have to check this). Remember to use the
dealer quotes in the triangle and not the cross rates we computed.

To label the arrows in this triangle, we follow the “up the bid, down the offer” rule. To
convert from USD to MXN, (“down” with respect to the USD/MXN quote), we use the
offer rate of 0.0935.
Going clockwise and starting with USD 1 million:
1. Convert USD 1 million into MXN @ 0.0935 USD/MXN. Note that the quote is
USD/MXN and hence we are going down, and thus need to use the ask. Also
remember: down, divide. We get 1 million/0.0935 = 10,695,187 MXN.
2. Next, we convert 10,695,187 MXN into AUD @ 6.3025 MXN/AUD to get 1,696,975
AUD.

3. Finally, we convert AUD 1,696,975 into USD @ 0.6000 USD/AUD. Here the quote is
USD/AUD and we are converting from AUD to USD, so we are going “up the quote”
and need to multiply by the bid. (Remember: up, multiply.) We get 1,696,975 × 0.60 =
1,018,185 USD − a profit of 18,185 USD.
We can also check for arbitrage in the counter-clockwise direction (even though we can
never earn an arbitrage profit in both directions):
1. Convert USD 1 million into AUD using 0.6015. Again, the quote is USD/AUD and we
are going down, so use the ask price and divide. We get 1 million/0.6015 = 1,662,510
AUD.
2. Next, we convert 1,662,510 AUD into MXN using 6.3000 to get 10,473,814 MXN.
3. Finally, we convert MXN 10,473,814 into USD at 0.0933 to get 977,207 USD − a loss of

### 22,793 Usd.


> **LOS 5.c:** Explain spot and forward rates and calculate the forward premium/discount for
a given currency.
A currency is quoted at a forward premium relative to a second currency if the forward
price (in units of the second currency) is greater than the [[Spot price|spot price]]. A currency is quoted
at a forward discount relative to a second currency if the [[Forward price|forward price]] (in units of the
second currency) is less than the [[Spot price|spot price]]. The premium or discount is for the base
currency (i.e., the currency at the bottom of the quote). For example, if the [[Spot price|spot price]] is
1.20$/€ and the forward price is 1.25$/€, we say that the euro is trading at a forward
premium.
forward premium (discount) = F − S0
Given a quote of A/B, if this equation results in a positive value, we say that currency B
(i.e., the base currency) is trading at a premium in the [[Forward market|forward market]].
In the FX markets, forward quotes are often presented as a premium or discount over spot
rates. The following example illustrates this convention.

### Example: Spot and forward quotes


Given the following quotes for AUD/CAD, compute the bid and offer rates for a 30-day
[[Forward contract|forward contract]].

Answer:
Since the forward quotes presented are all positive, the CAD (i.e., the base currency) is
trading at a forward premium.

30-day bid = 1.0511 + 3.9/10,000 = 1.05149
30-day offer = 1.0519 + 4.1/10,000 = 1.05231
The 30-day all-in forward quote for AUD/CAD is 1.05149/1.05231.

> [!pnote] Professor's Note
> ***For an investor wishing to convert AUD into CAD in the [[Forward market|forward market]], the***
> ***relevant quote would be the ask rate (remember the “down-the-ask” rule) of***
> ***1.05231. This is also known as the all-in (i.e., after adding (subtracting) the***
> ***forward premium (discount) rate for the investor in question.***

### Module Quiz 5.1

1. All of the following factors are likely to contribute to an increase in USD/EUR dealer spread
except:
A. increase in the volatility of EUR/USD [[Spot rate|spot rate]].
B. increase in the EUR/USD spread in the interbank market.
C. smaller order size.
2. The bid–ask quotes for the USD, GBP, and EUR are:

### Eur/Usd: 0.7000 − 0.7010


### Usd/Gbp: 1.7000 − 1.7010


### Eur/Gbp: 1.2000 − 1.2010

The potential arbitrage profit from a triangular arbitrage based on an initial position of 1
million USD is closest to:

### A. Usd0.


### B. Usd7,212.


### C. Usd6,372.


## Module 5.2: Mark-To-Market Value, and Parity Conditions


> **LOS 5.d:** Calculate the mark-to-[[Market value|market value]] of a [[Forward contract|forward contract]].
If the [[Forward contract|forward contract]] price is [[Consistent|consistent]] with [[Covered interest rate parity]] (discussed later),
the value of the contract at initiation is zero to both parties. After initiation, the value of
the [[Forward contract|forward contract]] will change as forward quotes for the currency pair change in the
market.

Mark-to-[[Market value|Market Value]]
The value of a forward currency contract prior to expiration is also known as the mark-tomarket value. To compute the value of a [[Forward contract|forward contract]] prior to expiration, we take the
difference between the [[Forward price|forward price]] we locked-in and the current [[Forward price|forward price]], multiply

that by the size of the contract, and then discount for the time period remaining until the
contract [[Settlement|settlement]]nt date|[[Settlement|settlement]] date]].


> [!pnote] Professor's Note
> ***The [[Interest rate|interest rate]] references used throughout this reading are the rates on bank***
> ***deposits using the appropriate market reference rate (MRR), and based on the***
> ***days/360 convention. MRR is the generic label used in the CFA curriculum to***
> ***represent various LIBOR successors globally.***

### Example: Valuing a forward contract prior to maturity


Yew Mun Yip has entered into a 90-day forward contract long CAD 1 million against AUD
at a [[Forward rate]] of 1.05358 AUD/CAD. Thirty days after initiation, the following
AUD/CAD quotes are available:

The following information is available (at t = 30) for AUD interest rates:
30-day rate: 1.12%
60-day rate: 1.16%
90-day rate: 1.20%
What is the mark-to-[[Market value|market value]] in AUD of Yip’s forward contract?
Answer:
Yip’s contract calls for long CAD (i.e., converting AUD to CAD). To value the contract, we
would look to unwind the position. To unwind the position, Yip can take an offsetting
position in a new forward contract with the same maturity. Hence, Yip would be selling
CAD in exchange for AUD and, hence, going up the bid (i.e., use the bid price). Note that
after 30 days, 60 more days remain in the original contract.

The forward bid price for a new contract expiring in T − t = 60 days is 1.0612 +
8.6/10,000 = 1.06206.
The [[Interest rate|interest rate]] to use for discounting the value is also the 60-day AUD [[Interest rate|interest rate]] of
1.16%:

Thirty days into the forward contract, Yip’s position has gained (positive value) AUD
8,463.64. This is because Yip’s position is long CAD, which has appreciated relative to
AUD since inception of the contract. Yip can close out the contract on that day and
receive AUD 8,463.64.
Note: Be sure to use the AUD (price currency) [[Interest rate|interest rate]].


> **LOS 5.e:** Explain [[International Parity Conditions|international parity conditions]] (covered and uncovered interest rate
parity, [[Forward rate|forward rate]] parity, [[Purchasing power parity]], and the [[International Fisher Effect|international Fisher effect]]ct|Fisher effect]]).

Covered [[Interest rate parity|interest rate parity]]
The word covered in the context of covered interest parity means bound by arbitrage.
Covered [[Interest rate parity]] holds when any forward premium or discount exactly offsets
differences in interest rates, so that an investor would earn the same return investing in
either currency. If euro interest rates are higher than dollar interest rates, the forward
discount on the euro relative to the dollar will just offset the higher euro interest rate.
Formally, [[Covered interest rate parity|covered interest rate parity]] requires that (given A/B quote structure):


> [!pnote] Professor's Note
> ***For all parity relations, follow the numerator-denominator rule. If you are given a***
> ***USD/EUR quote, the USD interest rate should be in the numerator and the EUR***
> ***interest rate in the denominator of the parity equation.***
> ***Recall that:***

### Example: Covered interest arbitrage


The U.S. dollar MRR is 8%, and the euro MRR is 6%. The spot exchange rate is $1.30 per
euro (USD/EUR), and the 1-year [[Forward rate|forward rate]] is $1.35 per euro. Determine whether a
profitable [[Arbitrage opportunity|arbitrage opportunity]] exists, and illustrate such an arbitrage if it does.
Answer:
First, we note that the [[Forward value|forward value]] of the euro is too high. [[Interest rate parity|Interest rate parity]] would
require a [[Forward rate|forward rate]] of:

Because the market [[Forward rate|forward rate]] of $1.35 is higher than that implied by interest rate
parity, we should sell euros in the [[Forward market|forward market]] and do the opposite (i.e., buy euros)
in the spot market. The steps in the covered interest arbitrage are as follows.
Initially:

After one year:

[[Uncovered interest rate parity|uncovered interest rate parity]]
With [[Covered interest rate parity|covered interest rate parity]], arbitrage will force the forward contract exchange rate to
a level [[Consistent|consistent]] with the difference between the two country’s nominal interest rates. If
forward currency contracts are not available, or if capital flows are restricted so as to
prevent arbitrage, the relationship need not hold. [[Uncovered interest rate parity|Uncovered interest rate parity]] refers to
such a situation; uncovered in this context means not bound by arbitrage.
Consider Country A where the interest rate is 4%, and Country B where the interest rate is
9%. Under [[Uncovered interest rate parity]], currency B is expected to depreciate by 5%

annually relative to currency A, so that an investor should be indifferent between investing
in Country A or B.
Given a quote structure of A/B, the base currency (i.e., currency B) is expected to
appreciate by approximately RA − RB. (When RA − RB is negative, currency B is expected to
depreciate). Mathematically:
The following example illustrates the use of [[Uncovered interest rate parity|uncovered interest rate parity]]ty|interest rate parity]] to forecast
future spot exchange rates using market interest rates.

### Example: Forecasting spot rates with uncovered interest rate parity


Suppose the spot exchange rate quote is ZAR/EUR = 8.385. The 1-year [[Nominal rate|nominal rate]] in
the eurozone is 10% and the 1-year [[Nominal rate|nominal rate]] in South Africa is 8%. Calculate the
expected percentage change in the exchange rate over the coming year using uncovered
[[Interest rate parity|interest rate parity]].
Answer:
The rand interest rate is less than the euro interest rate, so uncovered interest rate
parity predicts that the value of the rand will rise (it will take fewer rand to buy one
euro) because of higher interest rates in the eurozone. The euro (the base currency) is
expected to “appreciate” by approximately RZAR − REUR = 8% − 10% = –2%. (Note the
negative 2% value.) Thus the euro is expected to depreciate by 2% relative to the rand,
leading to a change in exchange rate from 8.385 ZAR/EUR to 8.217 ZAR/EUR over the
coming year.
Comparing covered and uncovered interest parity, we see that [[Covered interest rate parity|covered interest rate parity]]
derives the [[No-arbitrage pricing|no-arbitrage]] [[Forward rate|forward rate]], while [[Uncovered interest rate parity|uncovered interest rate parity]] derives the
expected future [[Spot rate|spot rate]] (which is not market traded). Covered interest parity is assumed
by arbitrage, but this is not the case for [[Uncovered interest rate parity|uncovered interest rate parity]]ty|interest rate parity]].
Under uncovered interest rate parity, if the foreign interest rate is higher by 2%, the foreign
currency is expected to depreciate by 2%, so the investor should be indifferent between
investing in the [[Foreign currency|foreign currency]] or in their own [[Domestic currency|domestic currency]]. An investor that
chooses to invest in the [[Foreign currency|foreign currency]] without any additional return (the interest rate
differential is offset by currency value changes) is not demanding a [[Risk premium]] for the
[[Foreign currency|foreign currency]] risk. Hence, uncovered interest rate parity assumes that the investor is
risk-neutral.
If the forward rate is equal to the expected future [[Spot rate|spot rate]], we say that the forward rate is
an unbiased predictor of the future [[Spot rate|spot rate]]. In such an instance, F = E(S1); this is called
[[Forward rate parity|forward rate parity]]. In this special case, if covered interest parity holds (and it will; by
arbitrage) uncovered interest parity would also hold (and vice versa). Stated differently, if
uncovered interest rate parity holds, [[Forward rate parity|forward rate parity]] also holds (i.e., the forward rate is
an unbiased predictor of the future [[Spot rate|spot rate]]).

There is no reason that uncovered interest rate parity must hold in the short run, and
indeed it typically does not. There is evidence that it does generally hold in the long run, so
longer-term expected future [[Spot rates|spot rates]] based on uncovered interest rate parity are often
used as forecasts of future exchange rates.

(Domestic) Fisher Relation
Professor Irving Fisher originated the idea that the [[Nominal rate|nominal rate]] of return is
(approximately) the sum of the real rate and the expected rate of [[Inflation|inflation]].
We can write this relation (known as the Fisher relation) as:

International Fisher Relation
Under [[Real interest rate|real interest rate]]te parity|[[Real interest rate|real interest rate]] parity]], real interest rates are assumed to converge across different
markets. Taking the Fisher relation and [[Real interest rate parity|real interest rate parity]] together gives us the
[[International Fisher Effect|international Fisher effect]]ct|Fisher effect]]:
This tells us that the difference between two countries’ nominal interest rates should be
equal to the difference between their [[Expected inflation|expected inflation]] rates.
The argument for the equality of real interest rates across countries is based on the idea
that with free capital flows, funds will move to the country with a higher real rate until real
rates are equalized.

### Example: Calculating the real interest rate


Suppose the nominal South African interest rate is 9.0% and the expected [[Inflation rate|inflation rate]]
is 3.5%. Calculate the [[Real interest rate|real interest rate]].
Answer:
0.090 = real rZAR + 0.035
real rZAR = 0.090 − 0.035 = 0.055, or 5.5%
If we move to a 2-country scenario, we will now have two nominal interest rates and two
[[Expected inflation|expected inflation]]on|inflation]] rates. If the real rates for both countries are assumed to be equal, they
drop out of the equation, and we are left with the international Fisher relation, as shown in
the following example.

### Example: Using the international Fisher relation


Suppose that the eurozone expected annual [[Inflation rate|inflation rate]] is 9.0%, and that the expected
South African [[Inflation|inflation]]on rate|[[Inflation|inflation]] rate]] is 13.0%. The nominal interest rate is 10.09% in the
eurozone. Use the international Fisher relation to estimate the nominal interest rate in
South Africa.

Answer:
real rate ZAR = real rate EUR ≈ (nominal interest rate in the eurozone) – (eurozone
expected annual [[Inflation rate|inflation rate]]) = 10.09% − 9% = 1.09%

$$
RZAR = (expected South African inflation rate) + (real ZAR interest rate)
$$

= 13% + 1.09% = 14.09%

[[Purchasing power parity|purchasing power parity]]
The [[Law of one price|law of one price]] states that identical goods should have the same price in all locations.
For instance, a pair of designer jeans should cost the same in Paris as they do in New York,
after adjusting for the exchange rate. The potential for arbitrage is the basis for the law of
one price: if designer jeans cost less in New York than they do in Paris, an enterprising
individual will buy designer jeans in New York and sell them in Paris, until this action causes
the price differential to disappear. Note, however, that the [[Law of one price|law of one price]] does not hold
in practice, due to the effects of frictions such as tariffs and transportation costs.
Instead of focusing on individual products, absolute [[Purchasing power parity|purchasing power parity]] (absolute
[[Purchasing power parity]]) compares the average price of a representative basket of consumption goods
between countries using an index such as The United States Consumer [[Price index|Price Index]] (CPI).
Absolute PPP requires only that the [[Law of one price|law of one price]] be correct on average, that is, for like
baskets of goods in each country.
S(A/B) = CPI(A) / CPI(B)
In practice, even if the [[Law of one price|law of one price]] held for every good in two economies, absolute PPP
might not hold because the weights (consumption patterns) of the various goods in the
two economies may not be the same (e.g., people eat more potatoes in Russia and more
rice in Japan).

Relative [[Purchasing power parity|Purchasing Power Parity]]
Relative [[Purchasing power parity|purchasing power parity]] (relative PPP) states that changes in exchange rates
should exactly offset the price effects of any inflation differential between two countries.
Simply put, if (over a 1-year period) Country A has a 6% inflation rate and Country B has a
4% inflation rate, then Country A’s currency should depreciate by approximately 2% relative
to Country B’s currency over the period.
The equation for relative PPP is as follows:

Relative PPP is based on the idea that even if absolute PPP does not hold, there may still be
a relationship between changes in the exchange rate and differences between the inflation
rates of the two countries.

Ex-Ante Version of PPP
The ex-ante version of [[Purchasing power parity|purchasing power parity]] is the same as relative purchasing power
parity except that it uses [[Expected inflation|expected inflation]] instead of actual inflation.
The following example illustrates the use of the ex-ante version of the PPP relation.

### Example: Calculating the exchange rate predicted by the ex-ante version of PPP


The current spot rate is USD/AUD = 1.00. You expect the annualized Australian inflation
rate to be 5%, and the annualized U.S. inflation rate to be 2%. According to the ex-ante
version of PPP, what is the expected change in the spot rate over the coming year?
Answer:
Since the AUD has the higher [[Expected inflation|expected inflation]] rate, we expect that the AUD will
depreciate relative to the USD. To keep the cost of goods and services the same across
borders, countries with higher rates of inflation should see their currencies depreciate.
The expected change in the spot rate over the coming year is inflation(USD) −
inflation(AUD) = 2% − 5% = –3%. This predicts a new USD/AUD exchange rate of
approximately 0.97 USD/AUD.
Because there is no true arbitrage available to force relative PPP to hold, violations of
relative PPP in the short run are common. However, because the evidence suggests that
the relative form of PPP holds approximately in the long run, it remains a useful method for
estimating the relationship between exchange rates and inflation rates.

> **LOS 5.f:** Describe relations among the [[International Parity Conditions|international parity conditions]].
It is useful to establish how all the parity relations described earlier fit together. Figure 5.1
shows the interrelationships among parity conditions. Though these relationships are not
all exact, together they provide an extremely useful framework for thinking about
exchange rates.


**Figure 5.1: The International Parity Relationships Combined**


Several observations can be made from the relationships among the various parity
conditions:
Covered interest parity holds by arbitrage. If [[Forward rate parity|forward rate parity]] holds, uncovered
interest rate parity also holds (and vice versa).
Interest rate differentials should mirror inflation differentials. This holds true if the
international Fisher relation holds. If that is true, we can also use inflation differentials to
forecast future exchange rates—which is the premise of the ex-ante version of PPP.
If the ex-ante version of relative PPP as well as the international Fisher relation both
hold, uncovered interest rate parity will also hold.

> **LOS 5.g:** Evaluate the use of the current spot rate, the forward rate, purchasing power parity, and
uncovered interest parity to forecast future spot exchange rates.

> **LOS 5.h:** Explain approaches to assessing the [[Long-Run Fair Value of an Exchange Rate|long-run fair value of an exchange rate]]n exchange rate.

We can use ex-ante PPP, uncovered interest rate parity, or forward rates to forecast future
[[Spot rates|spot rates]]. As stated earlier, uncovered interest rate parity and PPP are not bound by
arbitrage and seldom work over the short and medium terms. Similarly, the forward rate is
not an unbiased predictor of future spot rate. However, PPP holds over reasonably long
time horizons. If relative PPP holds at any point in time, the real exchange rate (i.e., the
exchange rate adjusted for relative historical inflation between the currency pair) would be
constant. However, since relative PPP seldom holds over the short term, the real exchange
rate fluctuates around its mean-reverting [[Equilibrium|equilibrium]] value.
The [[International Fisher Effect|international Fisher effect]]ct|Fisher effect]] (and real rate parity) assumes that there are no differences
between [[Sovereign risk|sovereign risk]] premia (i.e., all countries are perceived to be equally risky by
investors). This is obviously untrue as investors do demand a higher real rate of return (i.e.,
a [[Risk premium|risk premium]]) for investing in emerging market currencies that are perceived to be riskier.


### Module Quiz 5.2

1. Suppose the spot exchange rate quote is 1.0120 Canadian dollars (C$) per U.S. dollar. The 1year nominal interest rate in Canada is 3.0% and the 1-year nominal interest rate in the
United States is 1.0%. The expected exchange rate at the end of the year using the uncovered
interest rate parity is closest to:

### A. C$1.0322.


### B. C$0.9923.


### C. C$0.9918.

2. The international parity relationships indicate that the [[Expected Return]] on risk-free securities
should be the same in all countries and exchange rate risk is really just inflation risk. Which of
the following is least likely to be considered a practical implication of this framework?
A. Investors will earn the same real rate of return on investments once their own currency
impact is accounted for.
B. Interest rate differentials reflect currency expectations. As a result, covered interest
arbitrage will provide a return in any foreign currency that is equal to the domestic return.
C. There are significant rewards for bearing foreign exchange risk.
3. For uncovered interest rate parity to hold, which condition is necessary?
A. [[Forward rate parity|Forward rate parity]] holds.
B. [[Covered interest rate parity|Covered interest rate parity]] holds and ex-ante relative PPP holds.
C. [[Real interest rate parity|Real interest rate parity]] and ex-ante relative PPP holds.
Use the following information to answer Questions 4 through 9.
Sally Franklin, CFA, is a financial advisor to Jamie Curtess, a U.S. citizen interested in learning
more about how her investments will be affected by exchange rates and differences in interest
rates internationally. Franklin has gathered the following information based on Curtess’s
investment interests.
The current spot exchange rate: $1 = €0.74.

4. According to the international Fisher relation, the 1-year nominal interest rate in the United
States should be closest to:

### A. 3.00%.


### B. 4.34%.


### C. 6.00%.

5. If the relative form of the PPP holds, the expected exchange rate in one year is closest to:
A. $1.3378 per €.
B. $0.7463 per €.
C. $1.3647 per €.
6. For this question only, assume that the U.S. interest rate is 3.5%. The 1-year forward rate
should be closest to:
A. $1.3647 per €.
B. $0.7463 per €.

C. $1.3449 per €.
7. Curtess wonders how [[Spot rates|spot rates]] are expected to change in the future and asks the following
question: “What are the implications for the South African rand relative to the Swiss franc
under uncovered interest rate parity, and the implications for the euro relative to the U.S.
dollar under the relative form of purchasing power parity?” Franklin responds by making two
statements:
Statement 1: The South African rand is expected to depreciate relative to the Swiss franc.
Statement 2: The euro is expected to depreciate relative to the U.S. dollar.
Based upon the [[Underlying|underlying]] parity relationships cited, are Franklin’s statements accurate?
A. No, both statements are inaccurate.
B. Yes, both statements are accurate.
C. One statement is accurate and one is inaccurate.
8. For this question only, imagine that the nominal interest rate in the United States is 3%. Real
interest rates, using the Fisher relation, are most likely to be:
A. greater in the United States than in Europe.
B. lower in Europe than in South Africa.
C. equal among Europe, South Africa, Switzerland, and the United States.
9. A forecasted $/€ exchange rate in one year equal to the current 1-year forward rate is most
likely to be based on the assumption that:
A. absolute PPP holds.
B. investors are risk neutral.
C. [[Real interest rate|real interest rate]]te parity|real interest rate parity]] holds.


## Module 5.3: Exchange Rate Determinants, Carry Trade, and Central Bank Influence


> **LOS 5.i:** Describe the [[Carry trade|carry trade]] and its relation to uncovered interest rate
parity and calculate the profit from a [[Carry trade]].

[[FX carry trade|FX Carry Trade]]de|Carry Trade]]
Uncovered interest rate parity states that a currency with a high interest rate should
depreciate relative to a currency with a lower interest rate, so that an investor would earn
the same return investing in either currency. For example, suppose that short-term interest
rates are 3% in the U.K. and 1% in the United States. Uncovered interest rate parity implies
that the GBP should depreciate by 2% relative to the USD over the coming year.
However, uncovered interest rate parity is not bound by arbitrage. If the GBP depreciates
by less than 2% (or even appreciates), an investor who has invested in the higher yielding
GBP using funds borrowed in USD will earn excess profits. In a [[FX carry trade|FX carry trade]]de|carry trade]], an investor
invests in a higher yielding currency using funds borrowed in a lower yielding currency. The
lower yielding currency is called the funding currency.
Consider the following example.


### Example: Carry trade


Compute the profit to an investor borrowing in the United States and investing in the
U.K.
Answer:

The [[FX carry trade|FX carry trade]]de|carry trade]] attempts to capture an interest rate differential and is a bet against
uncovered interest rate parity. [[Carry Trades|Carry trades]] typically perform well during low-volatility
periods. Sometimes, higher yields attract larger capital flows, which in turn lead to an
economic boom and appreciation (instead of [[Depreciation|depreciation]]) of the higher yielding currency.
This could make the [[Carry trade|carry trade]] even more profitable because the investor earns a return
from currency appreciation in addition to the return from the interest rate spread.

Risks of the Carry Trade
As discussed earlier, the carry trade is profitable only if uncovered interest rate parity does
not hold over the investment horizon. The risk is that the funding currency may appreciate
significantly against the currency of the investment, which would reduce a trader’s profit—
or even lead to a loss. Furthermore, the return distribution of the carry trade is not normal;
it is characterized by negative skewness and [[Excess kurtosis|excess kurtosis]] (i.e., fat tails), meaning that
the [[Probability|probability]] of a large loss is higher than the [[Probability|probability]] implied under a normal
distribution. We call this high [[Probability|probability]] of a large loss the crash risk of the carry trade.
Crash risk stems from the carry trade’s leveraged nature: an investor borrows a low-yielding
(funding) currency and then invests in a high-yielding currency. As more investors follow
and adopt the same strategy, the demand for high-yielding currency actually pushes its
value up. However, with this herding behavior comes the risk that all investors may attempt
to exit the trade at the same time. (This is especially true if investors use stop-loss orders in
their [[Carry Trades|carry trades]].) During turbulent times, as investors exit their positions (i.e., a flight to
safety), the high-yielding currency can experience a steep decline in value, generating large
losses for traders pursuing FX [[Carry Trades|carry trades]].


> **LOS 5.j:** Explain how flows in the balance of payment accounts affect currency exchange
rates.

[[Balance of payments|balance of payments]]
Balance-of-payments (BOP) accounting is a method used to keep track of transactions
between a country and its international trading partners. It includes government
transactions, consumer transactions, and business transactions. The BOP accounts reflect
all payments and [[Liabilities|liabilities]] to foreigners as well as all payments and obligations received
from foreigners.
The [[Current account]] measures the exchange of goods, the exchange of services, the
exchange of investment income, and unilateral transfers (gifts to and from other nations).
The [[Current account|current account]] balance summarizes whether we are selling more goods and services
to the rest of the world than we are buying from them (a [[Current account|current account]] surplus) or
buying more from the rest of the world than we are selling to them (a [[Current account|current account]]
deficit).
The [[Financial account|financial account]] (also known as the [[Capital account]]) measures the flow of funds for
debt and equity investment into and out of the country.
When a country experiences a [[Current account|current account]] deficit, it must generate a surplus in its
[[Capital account|capital account]] (or see its currency depreciate). Capital flows tend to be the dominant
factor influencing exchange rates in the short term, as capital flows tend to be larger and
more rapidly changing than goods flows.

Influence of BOP on Exchange Rates
Current Account Influences
Current account deficits lead to a [[Depreciation|depreciation]] of [[Domestic currency|domestic currency]] via a variety of
mechanisms:
Flow supply/demand mechanism. Current account deficits in a country increase the
supply of that currency in the markets (as exporters to that country convert their
revenues into their own [[Local currency|local currency]]). This puts downward pressure on the exchange
value of that currency. The decrease in the value of the currency may restore the current
account deficit to a balance—depending on the following factors:
- The initial deficit. The larger the initial deficit, the larger the [[Depreciation|depreciation]] of domestic
currency needed to restore current account balance.
- The influence of exchange rates on domestic import and export prices. As a country’s
currency depreciates, the cost of imported goods increases. However, some of the
increase in cost may not be passed on to consumers.
- [[Price elasticity of demand|Price elasticity of demand]]ity]]ty of demand|[[Elasticity|elasticity]] of demand]] of the traded goods. If the most important imports are
relatively price [[Inelastic|inelastic]], the quantity imported will not change.
Portfolio balance mechanism. Countries with current account surpluses usually have
[[Capital account|capital account]] deficits, which typically take the form of investments in countries with
current account deficits. As a result of these flows of capital, investor countries may find

their portfolios’ composition being dominated by few investee currencies. When
investor countries decide to rebalance their investment portfolios, it can have a
significant negative impact on the value of those investee country currencies.
Debt sustainability mechanism. A country running a current account deficit may be
running a [[Capital account|capital account]] surplus by borrowing from abroad. When the level of debt
gets too high relative to [[GDP]], investors may question the sustainability of this level of
debt, leading to a rapid [[Depreciation|depreciation]] of the borrower’s currency.
[[Capital account|Capital Account]] Influences
Capital account flows are one of the major determinants of exchange rates. As capital flows
into a country, demand for that country’s currency increases, resulting in appreciation.
Differences in real rates of return tend to be a major determinant of the flow of capital:
higher relative real rates of return attract foreign capital. Capital flows into a country may
be needed to overcome a shortage of internal savings to fund investments needed for
[[Economic growth|economic growth]]. However, capital flows in excess of needed investment capital pose
several problems. This is especially problematic for emerging markets.
Excessive capital inflows into emerging markets create problems for those countries such
as:
Excessive real appreciation of the [[Domestic currency|domestic currency]].
Financial asset and/or [[Real estate]] bubbles.
Increases in external debt by businesses or government.
Excessive consumption in the domestic market fueled by credit.
Emerging market governments often counteract excessive capital inflows by imposing
capital controls or by direct intervention in the foreign exchange markets. We will discuss
this further in a subsequent LOS.

> **LOS 5.k:** Explain the potential effects of monetary and [[Fiscal policy|fiscal policy]] on exchange rates.

[[Mundell-Fleming Model|Mundell-Fleming Model]]
Developed in early 1960s, the [[Mundell-Fleming Model|Mundell-Fleming model]] evaluates the short-term impact of
monetary and fiscal policies on interest rates—and consequently on exchange rates. The
model assumes that there is sufficient slack in the economy to handle changes in aggregate
demand, and that inflation is not a concern. Accordingly, changes in inflation rates due to
changes in monetary or [[Fiscal policy|fiscal policy]] are not explicitly modeled by the Mundell-Fleming
model.
We will look at the implications of this model for flexible exchange rate regimes as well as
for fixed exchange rate regimes.
Flexible Exchange Rate Regimes
In a flexible (“floating”) exchange rate system, rates are determined by supply and demand
in the foreign exchange markets. We will examine the influence of monetary and fiscal
policies when international capital flows are relatively unrestricted (high mobility of capital)

versus when capital flows are relatively restricted (low mobility of capital), both under a
flexible exchange rate system.
High Capital Mobility
[[Expansionary|Expansionary]] [[Monetary policy|monetary policy]] and [[Expansionary fiscal policy|expansionary fiscal policy]] are likely to have opposite
effects on exchange rates. [[Expansionary|Expansionary]] [[Monetary policy|monetary policy]] will reduce the real interest rate
and, consequently, reduce the inflow of capital investment in physical and financial assets.
This decrease in financial inflows (deterioration of the [[Financial account|financial account]]) reduces the
demand for the [[Domestic currency|domestic currency]], resulting in depreciation of the domestic currency.
Restrictive [[Monetary policy|monetary policy]] should have the opposite effect, increasing real interest rates
and leading to an appreciation in the value of the domestic currency.
[[Expansionary fiscal policy|Expansionary fiscal policy]] (an increased deficit from lower taxes or higher government
spending) will increase government borrowing and, consequently, real interest rates. An
increase in real interest rates will attract foreign investment, improve the [[Financial account|financial account]],
and consequently, increase the demand for the domestic currency.
Low Capital Mobility
Our discussion so far has assumed free flow of capital, which is a valid assumption with
respect to developed markets. In emerging markets, however, capital flows may be
restricted. In that case, the impact of trade imbalance on exchange rates (goods flow
effect) is greater than the impact of interest rates (financial flows effect). In such a case,
[[Expansionary|expansionary]] fiscal or [[Monetary policy|monetary policy]] leads to increases in net imports, leading to
depreciation of the domestic currency. Similarly, restrictive monetary or [[Fiscal policy|fiscal policy]] leads
to an appreciation of domestic currency. Figure 5.2 summarizes the influence of fiscal and
monetary policy on the value of the domestic currency.

**Figure 5.2: Monetary and [[Fiscal policy|Fiscal Policy]] vs. the Value of the Domestic Currency**


> [!pnote] Professor's Note
> ***Candidates are often confused by the implication under the Mundell-Fleming***
> ***model that a higher-interest-rate currency will appreciate relative to a lowerinterest-rate currency, because this is exactly the opposite of what we learned***
> ***under uncovered interest rate parity. Note, though, that uncovered interest rate***
> ***parity assumed that real interest rates are equal globally, and thus that nominal***
> ***interest rates merely mirror expected inflation. That condition no longer holds***
> ***under the [[Mundell-Fleming Model|Mundell-Fleming model]], which does not consider inflation.***
> ***Fixed Exchange Rate Regimes***
> ***Under a fixed exchange rate regime, the government fixes the rate of exchange of its***
> ***currency relative to one of the major currencies.***
>
> ***An [[Expansionary|expansionary]] (restrictive) monetary policy would lead to depreciation (appreciation) of***
> ***the domestic currency as stated previously. Under a fixed rate regime, the government***
> ***would then have to purchase (sell) its own currency in the foreign exchange market. This***
> ***action essentially reverses the expansionary (restrictive) stance.***
> ***This explains why, in a world with mobility of capital, governments cannot both manage***
> ***exchange rates as well as pursue [[Independent|independent]] monetary policy. If the government wants to***
> ***manage monetary policy, it must either let exchange rates float freely or restrict capital***
> ***movements to keep them stable.***
>
> ***Monetary Approach to Exchange Rate Determination***
> ***Monetary models only take into account the effect of monetary policy on exchange rates***
> ***(fiscal policy effects are not considered). With the [[Mundell-Fleming Model|Mundell-Fleming model]], we assume that***
> ***inflation (price levels) plays no role in exchange rate determination. Under monetary***
> ***models, we assume that output is fixed, so that monetary policy primarily affects inflation,***
> ***which in turn affects exchange rates. There are two main approaches to monetary models:***
> ***1. Pure monetary model. Under a pure monetary model, the PPP holds at any point in***
> ***time and output is held constant. An expansionary (restrictive) monetary policy leads to***
> ***an increase (decrease) in prices and a decrease (increase) in the value of the domestic***
> ***currency. Therefore an x% increase [[In the money|in the money]] supply leads to an x% increase in price***
> ***levels and then to an x% depreciation of domestic currency. The pure monetary***
> ***approach does not take into account expectations about future monetary [[Expansion|expansion]] or***
> ***[[Contraction|contraction]].***
> ***2. Dornbusch overshooting model. This model assumes that prices are sticky (inflexible) in***
> ***the short term and, hence, do not immediately reflect changes in monetary policy (in***
> ***other words, PPP does not hold in the short term). The model concludes that exchange***
> ***rates will overshoot the long-run PPP value in the short term. In the case of an***
> ***expansionary monetary policy, prices increase, but over time. Expansionary monetary***
> ***policy leads to a decrease in interest rates—and a larger-than-PPP-implied depreciation***
> ***of the domestic currency due to capital outflows. In the long term, exchange rates***
> ***gradually increase toward their PPP implied values.***
> ***Similarly, a restrictive monetary policy leads to excessive appreciation of the domestic***
> ***currency in the short term, and then a slow depreciation toward the long-term PPP value.***
>
> ***[[Portfolio balance approach|Portfolio Balance Approach]] to Exchange Rate Determination***
> ***The [[Portfolio balance approach|portfolio balance approach]] focuses only on the effects of fiscal policy (and not***
> ***monetary policy). While the Mundell-Fleming model focuses on the short-term***
> ***implications of fiscal policy, the [[Portfolio balance approach|portfolio balance approach]] takes a long-term view and***
> ***evaluates the effects of a sustained fiscal deficit or surplus on currency values.***
> ***When the government runs a fiscal deficit, it borrows money from investors. Under the***
> ***[[Portfolio balance approach|portfolio balance approach]], investors evaluate the debt based on expected risk and return.***
> ***A sovereign debt investor would earn a return based on both the debt’s yield and its***
> ***currency return. (When we invest in a foreign-currency-denominated security, our realized***
> ***return will be comprised of the return earned on that security in its [[Local currency|local currency]], as well***
>
> ***as a return from the performance of that foreign currency versus our domestic currency.)***
> ***When a government pursues a long-term stance of [[Expansionary fiscal policy|expansionary fiscal policy]], an investor***
> ***should evaluate the implications of such a policy on expected risk and return (typically the***
> ***yield should increase due to a higher [[Risk premium|risk premium]]). If investors perceive that the yield***
> ***and/or currency return is sufficient, they will continue to purchase the bonds. However,***
> ***continued increases in fiscal deficits are unsustainable and investors may refuse to fund the***
> ***deficits—leading to currency depreciation.***
> ***Combining the Mundell-Fleming and portfolio balance approaches, we find that in the***
> ***short term, with free capital flows, an [[Expansionary fiscal policy|expansionary fiscal policy]] leads to domestic currency***
> ***appreciation (via high interest rates). In the long term, the government has to reverse***
> ***course (through tighter fiscal policy) leading to depreciation of the domestic currency. If***
> ***the government does not reverse course, it will have to monetize its debt (i.e., print money***
> ***—monetary [[Expansion|expansion]]), which would also lead to depreciation of the domestic currency.***
>
> ***> **LOS 5.l:** Describe objectives of central bank or government intervention and capital***
> ***controls and describe the effectiveness of intervention and capital controls.***
> ***A [[Combination|combination]] of “push” and “pull” factors determine the flow of capital into a country.***
> ***Pull factors are favorable developments that make a country an attractive destination for***
> ***foreign capital. These include [[Relative price|relative price]]ce stability|price stability]], a flexible exchange rate regime,***
> ***improved fiscal position, privatization of state-owned enterprises etc. Push factors are***
> ***largely driven by mobile international capital seeking high returns from a diversified***
> ***portfolio.***
> ***As stated earlier, capital flows can lead to excessive appreciation of a currency. This can***
> ***lead to several problems including loss of competitiveness of exports in the global markets,***
> ***asset price bubbles, and excessive consumption fueled by credit creation. Excessive capital***
> ***inflows to a country can also lead to a [[Currency crisis|currency crisis]] when such capital is eventually***
> ***withdrawn from the country. To reduce these problems, policymakers may intervene by***
> ***imposing capital controls or by direct intervention in the foreign exchange market by the***
> ***central bank.***
> ***Objectives***
> ***The objectives of capital controls or central bank intervention in FX markets are to:***
> ***Ensure that the domestic currency does not appreciate excessively.***
> ***Allow the pursuit of [[Independent|independent]] monetary policies without being hindered by their***
> ***impact on currency values. For example, an emerging market central bank seeking to***
> ***reduce inflation may pursue a restrictive monetary policy, increasing interest rates.***
> ***However, these higher rates may attract large inflows of foreign capital, pushing up the***
> ***value of the domestic currency.***
> ***Reduce the aggregate volume of inflow of foreign capital.***
> ***Effectiveness***
> ***For developed market countries, the volume of trading in a country’s currency is usually***
> ***very large relative to the foreign exchange reserves of its central bank. Evidence has shown***
>
> ***that for developed markets, [[Central banks|central banks]] are relatively ineffective at intervening in the***
> ***foreign exchange markets due to lack of sufficient resources. Evidence in the case of***
> ***emerging markets is less clear: [[Central banks|central banks]] of emerging market countries may be able to***
> ***accumulate sufficient foreign exchange reserves (relative to trading volume) to affect the***
> ***supply and demand of their currencies in the foreign exchange markets.***
>
> ***> **LOS 5.m:** Describe warning signs of a [[Currency crisis|currency crisis]].***
> ***History has shown that market participants have failed to predict crises and typically are***
> ***surprised by them. When market sentiment changes significantly, crises may occur even for***
> ***countries with sound economic [[Fundamentals|fundamentals]].***
> ***The following conditions have been identified as warning signs in the period leading up to a***
> ***[[Currency crisis|currency crisis]]:***
> ***[[Terms of trade|Terms of trade]] (i.e., ratio of exports to imports) deteriorate.***
> ***Fixed or partially-fixed exchange rates (versus floating exchange rates).***
> ***Official foreign exchange reserves dramatically decline.***
> ***Currency value that has risen above its historical mean.***
> ***Inflation increases.***
> ***Liberalized [[Capital markets|capital markets]], that allow for the free flow of capital.***
> ***Money supply relative to bank reserves increases.***
> ***Banking crises (may also be coincident).***

### Module Quiz 5.3

1. Vilasram Deshmukh is forecasting JPY/USD exchange rates based on [[Balance of payments]]
analysis. He notes that the United States is running large current account deficits relative to
Japan. Based on this information, he concludes that the JPY/USD rate should decrease. His
conclusion is most likely supported by the:
A. flow mechanism of the current account influences.
B. portfolio composition mechanism of the current account influences.
C. capital account influences.
2. Stephen Hall is forecasting USD/GBP exchange rates. He consults forecasts of the money
supply for the United States and U.K. made by his firm’s chief economist, and he notes the
following statement from a report published by the chief economist: “The U.S. money supply is
expected to grow at a much faster pace than the U.K. or European money supplies.”
Hall makes the following statement: “Under the pure monetary approach model, an increase
in the future growth rate of the money supply would lead to an immediate depreciation in the
currency’s value.” Hall’s statement is most likely:
A. correct.
B. incorrect, as the future growth rate [[In the money|in the money]] supply would not immediately affect
currency values under the pure monetary approach model.
C. incorrect, as the future growth rate in money supply would actually increase the currency
value under the pure monetary approach.
3. Chintan Rajyaguru works for a currency dealer in London. He is evaluating the implications of
changes in fiscal and monetary policies occurring in Zambola, an emerging market country
with low capital mobility. He concludes that Zambola’s central bank is pursuing a restrictive

monetary policy to curb inflation. Additionally, the Zambolan government has been reducing
budget deficits to comply with new IMF lending terms. According to the Mundell-Fleming
model, the change in monetary and fiscal policy is most likely to cause the Zambolan currency
to:
A. appreciate.
B. depreciate.
C. remain unchanged.

Use the following information to answer Questions 4 through 9.
Agnetha Poulsen works as an analyst in the foreign exchange overlay strategies department
for CFN, a large asset management firm serving institutional clients. She is concerned
about the excessive unhedged currency exposure taken on by the overlay strategies
department. She makes an appointment with Alvilda Kristensen, director of risk
management, to discuss this matter. Prior to the meeting, Poulsen collects information on
foreign currency quotes and on interest rates as shown in Figure 1 and Figure 2.

**Figure 1: Current Spot and Forward Exchange Rate Quotes**


**Figure 2: Selected Interest Rates**


Poulsen also reviews the current open forward contracts. As an example, she reviews two
contracts. Contract FX2001 is a 90-day forward contract initiated 60 days ago. The contract
calls for purchase of CHF 200 million at an all-in rate of USD 0.9832. Contract FX2051 is a
90-day contract initiated 30 days ago to purchase 100 million EUR at an all-in rate of
1.2242.
During her meeting with Kristensen, Poulsen expresses concern about traders establishing
FX [[Carry Trades|carry trades]] in several emerging market currencies. Kristensen assures Poulsen that CFN
has adequate monitoring mechanisms. She continues that these carry trades have been
generating significant positive returns for the clients and Poulsen should not worry about
it. Poulsen counters by stating that carry trade returns distributions are characterized by
negative kurtosis and excess skewness.
Poulsen reviews her notes and decides to prepare a report on currency crises. She compiles
a list of indicators of an impending [[Currency crisis|currency crisis]] based on empirical analysis.

Poulsen then turns her attention to the firm’s investments in Zambola, an emerging
market. She realizes that currently the currency overlay strategy department has no trades
involving the free-floating Zambolan currency, the Zu. Poulsen is concerned about
significant long exposure of the portfolio in Zu. Zambola is enjoying large capital inflows
drawn by Zambola’s attractive yields. Her analysis indicates that Zambola has been running
large current account deficits. A trend analysis on Zu indicates a steep upward trend
continuing above its PPP value.
1. The 30-day forward spread on USD/CHF is closest to:

### A. 0.0005.


### B. 0.0007.


### C. 0.7000.

2. The current mark-to-[[Market value|market value]] of the forward contract FX2001 in USD is closest to:

### A. –Usd460,000.


### B. –Usd451,924.


### C. –Usd357,940.

3. The current mark-to-market value of the forward contract FX2051 in USD is closest to:

### A. –Usd215,900.


### B. –Usd107,900.


### C. –Usd216,000.

4. Poulsen’s description of the carry trade return distribution is best described as:
A. correct.
B. incorrect about skewness only.
C. incorrect about both skewness and kurtosis.
5. Which of the following indicators of impending currency crises should Poulsen exclude from
her report?
A. [[Terms of trade|Terms of trade]] improve.
B. Increase in money supply relative to bank reserves.
C. Increase in inflation.
6. If Zambolan government wanted to reduce the inflow of foreign capital, it should:
A. pursue expansionary monetary policies.
B. pursue policies [[Consistent|consistent]] with currency appreciation.
C. reduce inflation by increasing interest rates.


> [!abstract] Key Concepts
> LOS 5.a

[[Bid–ask spread|bid–ask spread]] (for base currency) = ask quote − bid quote
Dealer spreads depend on spreads in the interbank market, the transaction size, and the
dealer-client relationship. Interbank spreads depend on the currencies involved, time of
day, and volatility in the currency pair. Forward spreads increase with maturities.
LOS 5.b

To calculate the profits from triangular arbitrage, start in the [[Home currency|home currency]] and go around
the triangle by exchanging the [[Home currency|home currency]] for the first foreign currency, then
exchanging the first foreign currency for the second foreign currency, and then exchanging
the second foreign currency back into the [[Home currency|home currency]]. If we end up with more money

than what we had when we started, we’ve earned an arbitrage profit. The [[Bid–ask spread|bid–ask spread]]
forces us to buy a currency at a higher rate going one way than we can sell it for going the
other way.
LOS 5.c

A spot exchange rate is for immediate delivery, while a forward exchange rate is for future
delivery.
premium (discount) for base currency = [[Forward price|forward price]] − [[Spot price|spot price]]
LOS 5.d

The mark-to-market value of a forward contract reflects the profit that would be realized
by closing out the position at current market prices, which is equivalent to offsetting the
contract with an equal and opposite forward position:

LOS 5.e

Covered interest arbitrage:

Uncovered interest rate parity:
International Fisher relation:
Relative PPP:
Forward rate parity:

LOS 5.f

LOS 5.g, 5.h

Future [[Spot rates|spot rates]] can be forecasted using PPP or by uncovered interest rate parity.
However, neither relationship is bound by arbitrage, nor do these relationships necessarily
work in the short term. Forward exchange rates, on the other hand, can be estimated using
covered interest parity, and this relationship is bound by arbitrage. If uncovered interest
parity holds, then we say that the forward rate parity holds, i.e., the forward rate is an
unbiased estimate of the future spot rate.
LOS 5.i

The [[FX carry trade|FX carry trade]] seeks to profit from the failure of uncovered interest rate parity to work
in the short run. In an FX carry trade, the investor invests in a high-yielding currency while
borrowing in a low-yielding currency. If the higher yielding currency does not depreciate by
the interest rate differential, the investor makes a profit. Carry trade has exposure to crash
risk.
profit on carry trade = interest differential − change in the spot rate of the investment
currency
LOS 5.j

BOP influence on exchange rate can be analyzed based on current account influence and
capital account influence. Current account influences include flow mechanism, portfolio
composition mechanism, and debt sustainability mechanism. Capital account inflows
(outflows) are one of the major causes of increases (decreases) in exchange rates.
LOS 5.k

The Mundell-Fleming model of exchange rate determination evaluates the impact of
monetary and fiscal policies on interest rates and consequently on exchange rates.
Under monetary models, we assume that output is fixed and, hence, monetary policies
primarily affect inflation, which in turn affects exchange rates.
The portfolio balance (asset market) model evaluates the long-term implications of
sustained fiscal policy (deficit or surplus) on currency values.

Monetary and Fiscal Policy and Exchange Rates

Under the pure monetary approach, PPP holds at any point in time.
Under the Dornbusch overshooting model, a restrictive (expansionary) monetary leads to
an appreciation (depreciation) of domestic currency in the short term, and then slow
depreciation (appreciation) towards the long-term PPP value.
Combining the Mundell-Fleming and portfolio balance approaches, we find that in the
short term, an expansionary (restrictive) fiscal policy leads to domestic currency
appreciation (depreciation). In the long term, the impact on currency values is opposite.
LOS 5.l

Capital controls and central bank intervention aim to reduce excessive capital inflows,
which could lead to speculative bubbles. The success of central bank intervention depends
on the size of official FX reserves at the disposal of the central bank relative to the average
trading volume in the country’s currency. For developed markets, the central bank
resources on a relative basis are too insignificant to be effective at managing exchange
rates. However, some emerging market countries with large FX reserves relative to trading
volume have been somewhat effective.
LOS 5.m

Warning signs of currency crises include: deterioration in [[Terms of trade|terms of trade]], a dramatic decline
in official foreign exchange reserves, an exchange rate substantially higher than its meanreverting level, increases in the inflation rate, a fixed- or partially-fixed exchange rate, an
increase in money supply relative to bank reserves, and banking crises.

### Answer Key For Module Quizzes

Module Quiz 5.1
1. C Dealer spreads are lower for smaller orders as compared to larger orders. Dealer
spreads are larger when spreads in the interbank market are higher. An increase in
spot rate volatility will increase spreads in the interbank market. (LOS 5.a)
2. C Here is what the triangle looks like with the bid–ask quotes filled in:

If we start with 1 million USD and move clockwise around the triangle (USD to GBP to
EUR to USD), we first convert 1 million USD into GBP at the ask:

Then we sell the GBP for EUR at the bid:

Finally, we purchase USD at the ask in euros:

Arbitrage profits are 1,006,372 USD – 1,000,000 USD = 6,372 USD. (LOS 5.b)
Module Quiz 5.2
1. A Because of a lower interest rate, the USD (base currency) will appreciate by 2% to
$1.012 × 1.02 = C$1.0322. (LOS 5.e)
2. C Combining all parity relationships indicates that the expected return on risk-free
securities should be the same in all countries and exchange rate risk is really just
inflation risk. There are four practical implications from this framework:
1. The real, risk-free return will be the same in all countries.
2. Investing in countries with high nominal interest rates will not generate excess returns
because the high nominal interest rates will be accompanied by [[Local currency|local currency]]
depreciation.
3. All investors will earn the same expected return in their own currency on any
investment denominated in a foreign currency.
4. Exchange rate risk is simply inflation risk, so investors interested in real returns will not
face exchange rate risk.
(LOS 5.f)
3. A Covered interest parity is forced by arbitrage, which is not the case for uncovered
interest rate parity. If the forward rate is equal to the expected future spot rate, we
say that the forward rate is an unbiased predictor of the future spot rate: F = E(S1). In
this special case, given that covered interest parity holds, uncovered interest parity

would also hold (and vice versa). In other words, if uncovered interest rate parity
(and covered interest parity) holds, the forward rate is unbiased predictor of future
spot rate (i.e., forward rate parity holds). (LOS 5.e)
4. A According to the international Fisher relation:

(LOS 5.e)
5. A Since inflation in Europe is higher than the inflation in the U.S. by 1%, the Euro is
expected to depreciate by 1% annually against the dollar.
The current spot rate is $(1/0.74) per Euro or $1.3513/€.
expected exchange rate in 1 year = 1.3513(0.99) = $1.3378/€
(LOS 5.e)
6. C Using covered interest parity, the forward rate in one year (in $ per €) can be
calculated as follows:
Spot rate = €0.74 per $ = $( 1 _ 0.74 ) per €

(LOS 5.e)
7. B Franklin is correct with respect to both of his statements: the rand should depreciate
relative to the franc and the euro should depreciate relative to the dollar.
The relative form of purchasing power parity predicts that countries with higher
expected inflation will experience a depreciation of their currencies. South Africa’s
expected inflation rate (5%) is higher than the expected inflation rate in Switzerland
(3%). The expected inflation rate in Europe (2%) is higher than the expected inflation
rate in the United States (1%). According to purchasing power parity, the rand should
depreciate relative to the franc, and the euro should depreciate relative to the U.S.
dollar.
Uncovered interest parity makes the same predictions with regard to relative interest
rates: countries with higher nominal interest rates can be expected to experience
currency depreciation. The South African interest rate (7%) is higher than the Swiss
rate (5%), so uncovered interest rate parity predicts that the rand will depreciate with
respect to the franc. The interest rate in Europe (4%) is higher than the interest rate
in the United States (3%), so the euro should depreciate relative to the U.S. dollar.
(LOS 5.e)

8. C According to the international Fisher relation, the real interest rate is equal to the
nominal interest rate minus the expected inflation rate. The real interest rate in each
of the four countries is 2%. (LOS 5.e)
9. B The 1-year expected spot rate should be equal to the current 1-year forward rate if
uncovered interest rate parity holds. One of the assumptions of uncovered interest
rate parity is that investors are risk neutral. Real interest rate parity states that real
interest rates are equal across countries. Uncovered interest rate parity also would
hold if both (1) relative (not absolute) PPP holds and (2) the international Fisher
relationship holds. (LOS 5.e)
Module Quiz 5.3
1. A The flow mechanism of current account influences supports the view that current
account deficits lead to depreciation of currency. In this example, the reduction in
the JPY/USD rate implies depreciation of the USD. Under capital account influences,
current account deficits imply capital account inflows and, hence, would lead to an
appreciation of USD. The portfolio composition mechanism of current account
influences supports the flow mechanism if investors rebalance a portion of their
portfolio out of USD assets due to gradual buildup of USD assets over time in their
portfolios. The question does not provide information to support this reallocation.
(Module 5.3, LOS 5.j)
2. B Under the pure monetary approach, growth [[In the money|in the money]] supply leads to
depreciation in currency. However, the future growth rate in money supply affects
the trajectory of FX rates but not the [[Current exchange rate|current exchange rate]]. (Module 5.3, LOS 5.k)
3. A Under the Mundell-Fleming framework, low capital mobility and restrictive monetary
and fiscal policy leads to better trade balance and appreciation of the country’s
currency. (Module 5.3, LOS 5.k)
4. A (0.9821 – 0.00069) – (0.9817 – 0.00076) = 0.00047
(Module 5.1, LOS 5.c)
5. B The contract calls for purchase of 200 million CHF in 30 days. To compute the markto-market value, we would have to use the quote on 30-day forward contract to sell
CHF. Given USD/CHF quote structure, we should use the bid price (going up the
quote).

(Module 5.2, LOS 5.d)
6. A The contract calls for purchase of 100 million EUR in 60 days. To compute the markto-market value, we would have to use the quote on 60-day forward contract to sell
EUR. Given USD/EUR quote structure, we should use the bid price (going up the
quote).
all-in bid price for 60-day USD/EUR forward contract = 1.2235 – 14.56 / 10,000 =
1.22204

(Module 5.2, LOS 5.d)
7. C Poulsen incorrectly described both the skewness as well as the kurtosis of carry trade
returns. Carry trade return distributions generally have negative skewness and excess
kurtosis. (Module 5.3, LOS 5.i)
8. A Deterioration (and not improvement) in [[Terms of trade|terms of trade]] is an indicator of currency
crisis. (Module 5.3, LOS 5.m)
9. A The Zu is overvalued per PPP, and Zambola is running a current account deficit. A
depreciation of Zu would bring it closer to its long-run [[Fair value]]. An increase in
interest rates would lead to appreciation of Zu. Expansionary monetary policy would
reduce interest rates and make Zambolan yields less attractive to foreign investors.
(Module 5.3, LOS 5.j)


---

# Reading 6 — Economic Growth


> [!tip] Exam Focus
> Forecasts of [[Economic growth|economic growth]] rates have important implications for investment decisions.
> Understand the preconditions of growth, how the growth rate can be increased, and what
> drives [[Economic growth|economic growth]]. Be able to compare and contrast competing theories of growth.
> Finally, be able to use [[Growth Accounting|growth accounting]] equations to forecast the potential growth rate of
> an economy.


## Module 6.1: Growth Factors and Production Function


> **LOS 6.a:** Compare factors favoring and limiting economic growth in
developed and developing economies.


Economists measure the economic output of a country by [[GDP]] (GDP). A
country’s standard of living, however, is best measured by GDP per capita. Of particular
concern to investors is not just the level of economic output but the growth rate of output.
Historically, there have been large variations in both GDP growth rates and per capita GDP
across countries. Research has identified several factors that influence both the growth of
GDP and the level of GDP.

Preconditions for Growth
1. Savings and investment are positively correlated with economic development. For
countries to grow, private and public sector investment must provide a sufficient level of
capital per worker. If a country has insufficient domestic savings, it must attract foreign
investment in order to grow.
2. Financial markets and intermediaries augment economic growth by efficiently
allocating resources in several ways. First, financial markets determine which potential
users of capital offer the best returns on a risk-adjusted basis. Second, financial
instruments are created by intermediaries that provide investors with [[Liquidity|liquidity]] and
opportunities for risk reduction. Finally, by pooling small amounts of savings from
investors, intermediaries can finance projects on larger scales than would otherwise be
possible.

Some caution is in order, however. Financial sector intermediation may lead to declining
credit standards and/or increases in leverage, increasing risk but not economic growth.
3. The political stability, rule of law, and property rights environment of a country also
influence economic growth. Countries that have not developed a system of property
rights for both physical and intellectual property will have difficulty attracting capital.
Similarly, economic uncertainty caused by wars, corruption, and other disruptions poses
unacceptable risk to many investors, reducing potential economic growth.
4. Investment in [[Human capital|human capital]], the investment in skills and well-being of workers, is
thought to be complementary to growth in physical capital. Consequently, countries that
invest in education and health care systems tend to have higher growth rates.
Developed countries benefit the most from post-secondary education spending, which
has been shown to foster innovation. Less-developed countries benefit the most from
spending on primary and secondary education, which enables the workforce to apply
the [[Technology|technology]] developed elsewhere.
5. Tax and regulatory systems need to be favorable for economies to develop. All else
equal, the lower the tax and regulatory burdens, the higher the rate of economic
growth. Lower levels of regulation foster entrepreneurial activity (startups), which have
been shown to be positively related to the overall level of [[Productivity|productivity]].
6. [[Free trade|Free trade]] and unrestricted capital flows are also positively related to economic
growth. [[Free trade|Free trade]] promotes growth by providing competition for domestic firms, thus
increasing overall efficiency and reducing costs. Additionally, [[Free trade|free trade]] opens up new
markets for domestic producers. Unrestricted capital flows mitigate the problem of
insufficient domestic savings as foreign capital can increase a country’s capital, allowing
for greater growth. Foreign capital can be invested directly in assets such as property,
physical plant, and equipment ([[Foreign direct investment|foreign direct investment]]), or invested indirectly in
financial assets such as stocks and bonds.

> **LOS 6.b:** Describe the relation between the long-run rate of stock market appreciation
and the [[Sustainable growth rate]] of the economy.
Equity prices are positively related to earnings growth. Economy-wide, aggregate corporate
earnings can grow if GDP grows or if the share of corporate earnings in GDP grows.
However, the share of corporate profits in the GDP cannot increase indefinitely, because
labor will be unwilling to work for a lower and lower proportion of the GDP. Therefore, the
[[Potential GDP|potential GDP]] of a country—the upper limit of real growth for an economy—is the longrun limit of earnings growth, and is an important factor in predicting returns on aggregate
equity markets.
The Grinold-Kroner (2002) model provides the appropriate framework to understand this:
E(R) = [[Dividend yield|dividend yield]] (DY) + expected capital gains yield (CGY)
We can further decompose the capital gains yield into EPS growth and growth in the P/E
ratio:
expected capital gains yield = EPS growth (Δ EPS) + expected repricing (ΔP/E)

EPS growth can be decomposed into real EPS growth, inflation, and change in the number
of shares outstanding via stock buybacks (i.e., the dilution effect).

The full model then is:
E(R) = DY + ΔEPSR + π – ΔS + ΔP/E
[[Dividend yield|Dividend yield]] tends to be stable over time. The repricing term (change in P/E) does
fluctuate with the [[Business cycle|business cycle]]: when GDP growth is high, market multiples rise as
perception of risk declines. The repricing term, however, cannot continue to grow.
Therefore, in the long-run, the key factor driving equity returns is ΔEPSR which is itself
subject to an upper limit of [[Potential GDP|potential GDP]] growth.
The dilution effect (ΔS) sometimes plays a role in determining equity returns, but its impact
differs by country depending on its level of development and the sophistication of its
financial markets. Recognize that on an aggregate basis, the dilution effect is comprised of
net stock buybacks (nbb) as well as issuance by privately held small and medium
entrepreneurial companies (it would actually be more appropriate to call nbb “net
issuance,” where net issuance = new issuance – buybacks). We call the role of these small
and medium entrepreneurial companies the relative dynamism (rd) of the economy.
Therefore, ΔS = nbb + rd
Relative dynamism captures the difference between the overall economic growth of the
country and the earnings growth of listed companies.

> **LOS 6.c:** Explain why [[Potential GDP|potential GDP]] and its growth rate matter for equity and fixed
income investors.
As indicated earlier, all else equal, higher GDP growth will be associated with higher equity
returns. However, equity returns are significantly affected by dilution (due to share
buybacks, mergers, privatizations of public companies, etc.). Economic growth can also be
attributed to privately held companies. [[Potential GDP|Potential GDP]] also has implications for real interest
rates. Positive growth in potential GDP indicates that future income will rise relative to
current income. When consumers expect their incomes to rise, they increase current
consumption and save less for future consumption (i.e., they are less likely to worry about
funding their future consumption). To encourage consumers to delay consumption (i.e., to
encourage savings), investments would have to offer a higher real rate of return. Therefore,
higher potential GDP growth implies higher real interest rates and higher real asset returns
in general.
In the short term, the relationship between actual GDP and potential GDP may provide
insight to both equity and fixed-income investors as to the state of the economy. For

### Example: , since actual GDP in excess of potential GDP results in rising prices, the gap

between the two can be used as a forecast of inflationary pressures—useful to all investors
but of particular concern to fixed-income investors. Furthermore, [[Central banks|central banks]] are likely to
adopt monetary policies [[Consistent|consistent]] with the gap between [[Potential output|potential output]] and actual
output. When actual GDP growth rate is higher (lower) than potential GDP growth rate,

concerns about inflation increase (decrease) and the central bank is more likely to follow a
restrictive (expansionary) monetary policy.
In addition to predicting monetary policy, the relationship between actual and potential
GDP can also be useful in analyzing fiscal policies. It is more likely for a government to run a
fiscal deficit when actual GDP growth rate is lower than its potential growth rate.
Finally, because of the [[Credit risk|credit risk]] assumed by fixed-income investors, growth in GDP may
be used to gauge [[Credit risk|credit risk]] of both corporate and government debt. A higher potential
GDP growth rate reduces expected [[Credit risk|credit risk]] and generally increases the credit quality of
all debt issues.

> **LOS 6.d:** Contrast [[Capital Deepening|capital deepening]]ng investment|[[Capital Deepening|capital deepening]] investment]] and technological progress and explain
how each affects economic growth and [[Labor productivity|labor productivity]].

Factor Inputs and Economic Growth
Economies are complex systems of many economic inputs. To simplify analysis, we examine
a 2-factor (labor and capital) aggregate [[Production function|production function]] in which output (Y) is a
function of labor (L) and capital (K), given a level of [[Technology|technology]] (T).
To examine the effect of capital investment on economic growth and [[Labor productivity|labor productivity]]ty|productivity]],
consider a [[CFA_Glossary/Cobb-Douglas production function]], which takes the form:

$$
Y = TK\alphaL(1–\alpha)
$$


The [[CFA_Glossary/Cobb-Douglas production function]] function essentially states that output (GDP) is a function of labor and
capital inputs and their [[Productivity|productivity]]. It exhibits [[Constant returns to scale|constant returns to scale]]; increasing both
inputs by a fixed percentage leads to the same percentage increase in output.
Dividing both sides by L in the [[Cobb-Douglas Production Function|Cobb-Douglas production function]], we can obtain the output
per worker ([[Labor productivity|labor productivity]]).
output per worker = Y/L = T(K/L)α
[[Labor productivity|Labor productivity]]ty|productivity]] is similar to GDP per capita, a standard of living measure. The previous
equation has important implications about the effect of capital investment on the standard
of living. Assuming the number of workers and α remain constant, increases in output can
be gained by increasing capital per worker ([[Capital Deepening|capital deepening]]) or by improving [[Technology|technology]]
(increasing TFP).
However, since α is less than one, additional capital has a diminishing effect on
productivity: the lower the value of α, the lower the benefit of [[Capital Deepening|capital deepening]].
Developed markets typically have a high capital to labor ratio and a lower α compared to

developing markets, and therefore developed markets stand to gain less in increased
productivity from capital deepening.

> [!pnote] Professor's Note
> ***We need to distinguish between [[Marginal product|marginal product]] of capital and marginal***
> ***productivity of capital. [[Marginal product|Marginal product]] of capital is the additional output for***
> ***one additional unit of capital. Marginal productivity of capital is the increase in***
> ***output per worker for one additional unit of capital per labor (i.e., increasing***
> ***capital while keeping labor constant).***
> ***In [[Steady State]] (i.e., [[Equilibrium|equilibrium]]), the [[Marginal product|marginal product]] of capital (MPK = αY/K) and***
> ***marginal [[Cost of capital]] (i.e., the [[Rental Price of Capital|rental price of capital]], r) are equal; hence:***
> ***αY/K = r***
> ***or***
>
> ***$$***
> ***\alpha = rK/Y***
> ***$$***

> [!pnote] Professor's Note
> ***In the previous equation, r is rate of return and K is amount of capital. rK***
> ***measures the amount of return to providers of capital. The ratio of rK to output***
> ***(Y) measures the amount of output that is allocated to providers of capital. This is***
> ***precisely our definition of α.***
> ***The productivity curves in Figure 6.1 show the effect of increasing capital per worker on***
> ***output per worker. Capital deepening is a movement along the productivity curve. The***
> ***[[Curvature|curvature]] of the relationship derives from the [[Diminishing marginal productivity|diminishing marginal productivity]] of capital.***
> ***Economies will increase investment in capital as long as MPK > r. At the level of K/L for***
> ***which MPK = r, capital deepening stops and labor productivity becomes stagnant.***
> ***However, as technological progress occurs, both capital and labor can produce a higher***
> ***level of output. An investment in capital leading to technological progress enhances the***
> ***productivity of existing labor and capital. Technological progress, therefore, can lead to***
> ***continued increases in output despite [[Diminishing marginal productivity|diminishing marginal productivity]] of capital.***
> ***Technological progress shifts the productivity curve upward and will lead to increased***
> ***productivity at all levels of capital per worker.***
> ***labor productivity growth rate***
> ***= growth due to technological change + growth due to capital deepening***
>
>
> *****Figure 6.1: Productivity Curves*****
>
>
> ***As stated earlier, for developed countries, the capital per worker ratio is relatively high***
> ***(e.g., level C1 in Figure 6.1), so those countries gain little from capital deepening and must***
> ***rely on technological progress for growth in productivity. In contrast, developing nations***
> ***often have low capital per worker ratios (e.g., C0 in Figure 6.1), so capital deepening can***
> ***lead to at least a short-term increase in productivity.***

## Module 6.2: Growth Accounting and Influencing Factors


> **LOS 6.e:** Demonstrate forecasting potential GDP based on growth
accounting relations.


[[Growth Accounting|Growth Accounting]] Relations
Using the [[Cobb-Douglas Production Function|Cobb-Douglas production function]]on|production function]], the growth in potential GDP can be
expressed using the [[Growth Accounting|growth accounting]] relation as:
∆Y/Y = ∆T/T + α×(∆K/K) + (1−α)×(∆L/L)

In practice, levels of capital and labor are forecasted from their long-term trends, and the
shares of capital and labor determined from [[National income|national income]] accounts. The change in total
factor productivity ([[Technology|technology]]) is not directly observable. Therefore, it must be estimated
as a residual: the ex-post (realized) change in output minus the output implied by ex-post
changes in labor and capital.
The [[Growth accounting equation|growth accounting equation]] is also useful in determining the comparative effects of
increasing different inputs. If labor growth accounts for the majority of economic growth,
for example, analysts should be concerned with a country’s ability to continue to increase
its [[Labor force|labor force]]. The relation can also be used to estimate [[Potential output|potential output]], as illustrated in
the following example.

### Example: Estimating potential GDP growth rate


Azikland is an emerging market economy where labor cost accounts for 60% of total
factor cost. The long-term trend of labor growth of 1.5% is expected to continue. Capital
investment has been growing at 3%. The country has benefited greatly from borrowing
the technology of more developed countries; [[Total factor productivity]] is expected to
increase by 2% annually. Compute the potential GDP growth rate for Azikland.
Answer:
Using the [[Growth accounting equation|growth accounting equation]]:
growth rate in potential GDP = 2% + (0.4)(3%) + (0.6)(1.5%) = 4.1%
Another approach to forecasting potential GDP growth is the labor productivity growth
accounting equation, which focuses on changes in labor as follows:
The long-term growth rate in labor productivity reflects both capital deepening and
technological progress.

> **LOS 6.f:** Explain how natural resources affect economic growth and evaluate the
argument that limited availability of natural resources constrains economic growth.
Natural resources include both [[Renewable resources|renewable resources]], such as timber, and non-renewable
resources, such as oil and gas. The role of natural resources in economic growth is complex.
In some instances, countries with abundant natural resources (e.g., Brazil) have grown
rapidly. Yet other countries (e.g., some of the resource-rich countries of Africa) have not.
Conversely, some resource-poor countries have managed impressive growth.
One reason that limited natural resources do not necessarily constrain economic growth is
that access to natural resources does not require ownership of resources. Resource-poor
countries may be able to access resources via trade. Japan, for example, has managed
impressive growth and high per capita GDP despite having limited ownership of natural
resources.

Other theories contend that ownership of natural resources may actually inhibit growth,
because the economic energy of a country rich in natural resources may be focused on
recovering those resources rather than developing other industries. Furthermore,
countries that own valuable resources can find their currency appreciating as the demand
for those resources increases. The so-called “[[Dutch disease|Dutch disease]]” refers to a situation where
global demand for a country’s natural resources drives up the country’s currency values,
making all exports more expensive and rendering other domestic industries uncompetitive
in the global markets.

> **LOS 6.g:** Explain how demographics, immigration, and [[Labor force|labor force]] participation affect the
rate and sustainability of economic growth.
As stated previously, an increase in the quantity of labor will increase output, but not per
capita output. Quantity of labor is defined as the size of the [[Labor force|labor force]] multiplied by
average hours worked. [[Labor force|Labor force]] is defined as the number of working age (ages 16–64)
people available to work, both employed and [[Unemployed|unemployed]].

Labor Supply Factors
1. Demographics. A country’s demographics strongly influence its potential economic
growth. As a country’s [[Population|population]] ages and individuals live beyond working age, the
labor force declines. Conversely, countries with younger populations have higher
potential growth. Furthermore, fertility rates drive [[Population|population]] growth and thereby affect
potential future economic output. Countries with low or declining fertility rates will
likely face growth challenges from labor force declines.
2. Labor force participation. Labor force participation is defined as the proportion of
working age [[Population|population]] in the labor force.

Labor force participation can increase as more women enter the workforce.
3. Immigration. Immigration poses a potential solution to a declining labor force. Countries
with low [[Population|population]] growth or adverse demographic shifts (older population) may find
their growth constrained. Since developed countries tend to have lower fertility rates
than less developed countries, immigration represents a potential source of continued
economic growth in developed countries.
4. Average hours worked. For most countries, the general trend in average hours worked
is downward. Possible explanations include legislation limiting the number of hours
worked, the “[[Wealth effect|wealth effect]]” which induces individuals to take more leisure time, high
tax rates on labor income, and an increase in part-time and temporary workers.

### Example: Impact of demographics on economic growth


Data for Cangoria, a country in Asia, is shown here. Based upon this data, comment on
the likely impact of Cangoria’s demographic changes on its economic growth. Assume
average world population growth rate is 1.2% per year.

Answer:
Cangoria’s population grew at an average annual compound growth rate of
approximately 1.8% per year over those 10 years. Combined with the increase in labor
force participation, labor supply growth should be above average in the future for
Cangoria if those trends continue. The young median age of the population also
indicates an expected increase in the labor pool in the future.
Changes in per capita GDP are difficult to predict. Output is expected to be higher due
an increasing labor pool, but the larger population may mean there is no impact on per
capita GDP.


> **LOS 6.h:** Explain how investment in physical capital, [[Human capital|human capital]], and technological
development affects economic growth.
[[Human capital|Human capital]]. [[Human capital|Human capital]] is knowledge and skills individuals possess. Unlike
quantitative labor metrics, such as hours worked, human capital is a qualitative measure of
the labor force. Increasing human capital through education or work experience increases
productivity and economic growth. Furthermore, human capital may have external
spillover effects as knowledgeable workers innovate. Innovations are then used by society
in general creating greater efficiencies economy wide.
Physical capital. Physical capital is generally separated into infrastructure, computers, and
telecommunications capital (ICT) and non-ICT capital (i.e., machinery, transportation, and
non-residential construction). Empirical research has found a strong positive [[Correlation|correlation]]
between investment in physical capital and GDP growth rates.
This result may seem inconsistent given our previous discussion about capital deepening
and diminishing marginal returns to capital. Several explanations exist to explain why
capital increases may still result in economic growth. First, many countries (e.g., developing
economies) have relatively low capital to labor ratios, so increases in capital may still have
significant impact on economic growth. Second, capital investment can take different
forms. Some capital investment actually influences technological progress, thereby
increasing TFP and economic growth. For example, acceleration of spending in the IT sector
has created what are termed [[Network externalities|network externalities]]. Investment in IT networks may have
multiplicative effects on productivity since IT network investment actually becomes more
valuable as more people are connected to the network.
Technological development. Investment in technology includes investment in both physical
and human capital. Technological innovation can manifest itself in processes, knowledge,
information, machinery, and software, among other things. Researchers have examined
proxies for investment in technology such as research and development (R&D) spending or

number of patents issued. Developed countries tend to spend the most on R&D since they
rely on technological progress for growth given their high existing [[Capital Stock|capital stock]] and slower
population growth. In contrast, less developed countries often copy the technological
innovations of developed countries and thus invest less in R&D as a percentage of GDP.
Ultimately, technological development should lead to increases in productivity as
measured by GDP per worker. Developed countries tend to have very high levels of
productivity by this measure while less developed countries tend to have greater potential
for growth in productivity.
Public infrastructure. Investments in public infrastructure such as the construction of
public roads, bridges, and municipal facilities, provide additional benefits to private
investment. For example, an investment in distribution facilities by a private company
would do little good without an interstate highway grid. The highway system, therefore,
enhances total productivity for the economy by complementing the private investment and
increasing [[Total factor productivity|total factor productivity]].

### Module Quiz 6.1, 6.2

Use the following information to answer Questions 1 through 6.
Jay Smith, an analyst for Mako Capital, is evaluating investment prospects in Minikaz, an
emerging market economy. Minikaz has experienced moderate growth in the past four years,
after decades of stagnation. Smith is evaluating changes in government policies that would foster
a higher level of growth. Figure 1 shows the summary of his findings.

**Figure 1: Proposed Changes in Minikaz Government Policies**

1. Consumer protection will be at the forefront of government’s agenda.
2. The government will lower the entry barriers for foreign financial institutions to
operate as intermediaries in Minikaz [[Capital markets|capital markets]].
3. The government will expand public domain legislation to acquire private property for
public works projects.
Smith reviews a report published by the Minikaz commerce department. The report indicates
that the long-term real growth rate of Minikaz GDP is 2.5%, corporate profits as a percentage of
GDP increased by 2% last year, and the [[Price-to-earnings ratio|P/E ratio]] increased from 17 to 19 over the last two years.
Separately, Smith also reviews World Bank reports indicating that Minikaz’s potential GDP
growth is 4% and that it has been experiencing actual GDP growth of approximately 2.5%.
Finally, Smith reviews Minikaz’s [[National income|national income]] accounts and finds that Minikaz is experiencing
both technological progress and making increased capital expenditures.
Separately, Smith evaluates the performance of Kinimaz, a neighboring republic. Kinimaz has had
labor growth of 2% over the last several years and capital growth of 3%. Labor’s share of total
output is estimated to be 60%. Over the same period, Kinimaz’s [[Real GDP|real GDP]] has grown by 3.7%.
Comparing the two countries, Smith notes that Kinimaz has substantially higher amounts of
natural resource [[Endowments|endowments]]. He concludes that Minikaz’s relatively lower GDP growth is due to
lack of natural resources.
1. Which of the following actions by Minikaz’s government is most likely to increase Minikaz’s
economic growth rate?
A. Increasing protection for consumers through regulations.
B. Allowing foreign financial institutions to enter the market.

C. Expanding public domain legislation.
2. Based on the commerce department report, what would be the most likely forecast for the
long-term aggregate stock market appreciation?

### A. 2.5%.


### B. 4.5%.


### C. 11.5%.

3. Based on World Bank report, which of the following conclusions is most likely regarding
Minikaz?
A. Inflation is 1.5%.
B. Minikaz’s government is likely to follow a restrictive fiscal policy.
C. Minikaz’s central bank is not likely to be worried about inflation.
4. Using the [[Cobb-Douglas Production Function|Cobb-Douglas production function]]on|production function]] and the concepts of capital deepening and total
factor productivity, which of the following outcomes is most likely?
A. Minikaz will experience an increase in sustainable growth of per capita output due to the
increased capital expenditures.
B. There will be no short-term increase in per capita output.
C. There will be both short-term and long-term increases in Minikaz’s GDP growth rate.
5. Using the Cobb-Douglas relation, [[Total factor productivity|total factor productivity]] growth for Kinimaz is closest to:

### A. 0.5%.


### B. 1.3%.


### C. 1.7%.

6. Smith’s conclusion about Minikaz’s relatively lower GDP growth is most likely:
A. correct.
B. correct because in some cases, natural resources may inhibit economic growth.
C. incorrect because access to natural resources is more important than ownership.
7. Data for the labor market of countries X and Y over the past year appears next:

Both countries are expected to have moderate economic expansions over the next several
years. Which of the following statements is most accurate regarding labor input of the
countries in the next several years?
A. Country X will have greater opportunities to increase labor input.
B. Country Y will have greater opportunities to increase labor input.
C. Neither Country X nor Country Y will be able to increase labor input.
8. Which of the following would least likely have [[Externality|externality]] effects on output growth for an
economy?
A. Human capital investment.
B. ICT investment.
C. Non-ICT investment.


## Module 6.3: Growth and Convergence Theories


> **LOS 6.i:** Compare [[Classical growth theory|classical growth theory]], [[Neoclassical growth theory|neoclassical growth theory]], and


[[Endogenous growth theory|endogenous growth theory]].
Theories of economic growth are largely separated into three models with differing views
on the steady state growth potential of an economy.

[[Classical growth theory|Classical Growth Theory]]
Based on Malthusian economics, [[Classical growth theory|classical growth theory]] posits that, in the long-term,
population growth increases whenever there are increases in per capita income above
subsistence level due to an increase in capital or technological progress. Subsistence level is
the minimum income needed to maintain life. [[Classical growth theory|Classical growth theory]] contends that
growth in [[Real GDP|real GDP]] per capita is not permanent, because when [[Real GDP|real GDP]] per capita rises
above the subsistence level, a population explosion occurs. Population growth leads to
diminishing marginal returns to labor, which reduces productivity and drives GDP per
capita back to the subsistence level. This mechanism would prevent long-term growth in
per capita income. Classical growth theory is not supported by empirical evidence.

[[Neoclassical growth theory|Neoclassical Growth Theory]]
[[Neoclassical growth theory|Neoclassical growth theory]]’s primary focus is on estimating the economy’s long-term
steady state growth rate ([[Sustainable growth rate|sustainable growth rate]] or [[Equilibrium|equilibrium]] growth rate). The
economy is at equilibrium when the output-to-capital ratio is constant. When the outputto-capital ratio is constant, the capital-to-labor ratio and output per capita also grow at the
equilibrium growth rate, g*. Under neoclassical theory, population growth is [[Independent|independent]]
of economic growth.

> [!pnote] Professor's Note
> ***Steady state growth rate for the purpose of [[Neoclassical growth theory|neoclassical growth theory]] does not***
> ***assume a constant level of technology and hence differs from the definition of***
> ***steady state discussed earlier.***
> ***Based on the Cobb-Douglas function discussed earlier, neoclassical growth theory states***
> ***that:***
> ***Sustainable growth of output per capita (or output per worker)(g*) is equal to the***
> ***growth rate in technology (θ) divided by labor’s share of GDP (1 – α).***
>
> ***[[Sustainable growth rate|Sustainable growth rate]] of output (G*) is equal to the [[Sustainable growth rate|sustainable growth rate]] of output***
> ***per capita, plus the growth of labor (ΔL).***

> [!pnote] Professor's Note
> ***In the equations for sustainable growth (per capita or total), growth rate is not***
> ***affected by capital (K). Hence, we say that capital deepening is occurring but it***
> ***does not affect growth rate once steady state is achieved.***

### Example: Estimating steady state growth rate


An analyst is forecasting steady state growth rates for Country X and Country Y and has
collected the following estimates:

Calculate and comment on sustainable growth rates for the two countries.
Answer:
Sustainable growth rates:
Country X = (2.0% / 0.60) + 1.2% = 4.53%
Country Y = (1.0% / 0.52) + 2.6% = 4.52%
Thus, the sustainable growth rates for the two countries are comparable. Country X’s
[[Sustainable growth rate|sustainable growth rate]] is primarily driven by higher growth rate in TFP. Country Y’s
[[Sustainable growth rate|sustainable growth rate]] is mostly driven by a higher population growth rate.
Under neoclassical theory:
Capital deepening affects the level of output but not the growth rate in the long run.
Capital deepening may temporarily increase the growth rate, but the growth rate will
revert back to the sustainable level if there is no technological progress.
An economy’s growth rate will move towards its steady state regardless of the initial
capital to labor ratio or level of technology.
In the steady state, the growth rate in productivity (i.e., output per worker) is a function
only of the growth rate of technology (θ) and labor’s share of total output (1 − α).
In the steady state, [[Marginal product|marginal product]] of capital (MPK) = αY/K is constant, but marginal
productivity is diminishing.
An increase in savings will only temporarily raise economic growth. However, countries
with higher savings rates will enjoy higher capital to labor ratio and higher productivity.
Developing countries (with a lower level of capital per worker) will be impacted less by
[[Diminishing marginal productivity|diminishing marginal productivity]] of capital, and hence have higher growth rates as
compared to developed countries; there will be eventual [[Convergence]] of growth rates.

[[Endogenous growth theory|Endogenous Growth Theory]]
In contrast to the neoclassical model, [[Endogenous growth theory|endogenous growth theory]] contends that
technological growth emerges as a result of investment in both physical and human capital
(hence the name endogenous which means coming from within). Technological progress

enhances productivity of both labor and capital. Unlike the neoclassical model, there is no
steady state growth rate, so that increased investment can permanently increase the rate
of growth.
The driving force behind the [[Endogenous growth theory|endogenous growth theory]] result is the assumption that
certain investments increase TFP (i.e., lead to technological progress) from a societal
standpoint. Increasing R&D investments, for example, results in benefits that are also
external to the firm making the R&D investments. Those benefits raise the level of growth
for the entire economy.
The endogenous growth model theorizes that returns to capital are constant. The key
implication of constant returns to capital is the effect of an increase in savings: unlike the
neoclassical model, the endogenous growth model implies that an increase in savings will
permanently increase the growth rate.
The difference between neoclassical and endogenous growth theory relates to total factor
productivity. Neoclassical theory assumes that capital investment will expand as
technology improves (i.e., growth comes from increases in TFP not related to the
investment in capital within the model). Endogenous growth theory, on the other hand,
assumes that capital investment (R&D expenditures) may actually improve total factor
productivity.

> **LOS 6.j:** Explain and evaluate [[Convergence|convergence]]ce Hypotheses|[[Convergence|convergence]] hypotheses]].
Empirical evidence indicates that there are large differences between productivity (output
per capita) of different countries, with less developed countries experiencing much lower
output per capita than their developed counterparts. The economic question is whether
productivity, and hence, living standards tend to converge over time. Will less developed
countries experience productivity growth to match the productivity of developed nations?
The absolute [[Convergence hypothesis|convergence hypothesis]] states that less-developed countries will converge to
the level of per capita output of more-developed countries. The neoclassical model
assumes that every country has access to the same technology. This leads to countries
having the same growth rates but not the same per capita income and as such, the
neoclassical model does not imply [[Absolute convergence|absolute convergence]]. The neoclassical model supports
the [[Conditional convergence|conditional convergence]] [[Hypothesis|hypothesis]], which states that the [[Convergence|convergence]] in living
standards will only occur for countries with the same savings rates, population growth
rates, and production functions. Under the [[Conditional convergence|conditional convergence]] [[Hypothesis|hypothesis]], the growth
rate will be higher for less developed countries until they catch up and achieve a similar
standard of living. Under the neoclassical model, once a developing country’s standard of
living converges with that of developed countries, the growth rate will then stabilize to the
same steady state growth rate as that of developed countries.
An additional [[Hypothesis|hypothesis]] is [[Club convergence|club convergence]]. Under this [[Hypothesis|hypothesis]], countries may be part
of a “club” (i.e., countries with similar institutional features such as savings rates, financial
markets, property rights, health and educational services, etc.). Under [[Club convergence|club convergence]],
poorer countries that are part of the club will grow rapidly to catch up with their richer
peers. Countries can “join” the club by making appropriate institutional changes. Those
countries that are not part of the club may never achieve the higher standard of living.

Empirical evidence shows that developing economies often (but not always) reach the
standard of living of more developed ones. Over the past half century, about two-thirds of
economies with a lower standard of living than the United States grew at a faster pace than
the United States. Though they have not converged to standard of living of the United
States, their more rapid growth provides at least some support for the [[Convergence|convergence]]
hypothesis. The [[Club convergence|club convergence]] theory may explain why some countries that have not
implemented appropriate economic or political reforms still lag behind.

> **LOS 6.k:** Describe the economic rationale for governments to provide incentives to
private investment in technology and knowledge.
Firms accept projects when they provide an expected return greater than their riskadjusted [[Cost of capital|cost of capital]]. Under endogenous growth theory, private sector investments in
R&D and knowledge capital benefit the society overall. For example, a new technology may
initially benefit the firm that developed it but may also boost the country’s overall
productivity. The effects of “social returns” or externalities are captured in the endogenous
growth theory model, which concludes that economies may not reach a steady state
growth but may permanently increase growth by expenditures that provide both benefits
to the company (private benefits) and benefits to society (externalities).
When the external benefits to the economy (the social returns) of investing in R&D are not
considered, many possible R&D projects do not have expected returns (private benefits)
high enough to compensate firms for the inherent riskiness of R&D investments. From an
aggregate, economy-wide viewpoint, the resultant level of R&D investment will be suboptimal or too low. Government incentives that effectively subsidize R&D investments can
theoretically increase private spending on R&D investments to its optimal level.

> **LOS 6.l:** Describe the expected impact of removing trade barriers on capital investment
and profits, employment and wages, and growth in the economies involved.
None of the growth theories that we have discussed account for potential trade and capital
flows between countries. Removing trade barriers and allowing for free flow of capital is
likely to have the following benefits for countries:
Increased investment from foreign savings.
Allows focus on industries where the country has a [[Comparative advantage|comparative advantage]].
Increased markets for domestic products, resulting in [[Economies of scale|economies of scale]].
Increased sharing of technology and higher [[Total factor productivity|total factor productivity]] growth.
Increased competition leading to failure of inefficient firms and reallocation of their
assets to more efficient uses.
The neoclassical model’s predictions in an [[Open economy|open economy]] (i.e., an economy without any
barriers to trade or capital flow) focus on the convergence. Since developing economies
have not reached the point of significant diminishing returns on capital, they can attract
capital through foreign investment and experience productivity growth as a result.
Eventually, these economies will develop; their growth will slow and will converge to the
steady state growth rate of developed economies.

The endogenous growth model also predicts greater growth with [[Free trade|free trade]] and high
mobility of capital since open markets foster increased innovation. As foreign competition
increases, more efficient and innovative firms will survive. Those firms permanently
increase the growth rate of the international economy by providing benefits beyond those
simply captured by the firm. [[Economies of scale|Economies of scale]] also increase output as firms serve larger
markets and become more efficient.
In terms of convergence, removing barriers on capital and trade flows may speed the
convergence of standard of living of less developed countries to that of developed
countries. Research has shown that as long as countries follow outward-oriented policies of
integrating their industries with the world economy and increasing exports, their standard
of living tends to converge to that of more developed countries. Countries following
inward-oriented policies and protecting domestic industries, can expect slower GDP growth
and convergence may not occur.

### Module Quiz 6.3

1. Country X has output [[Elasticity|elasticity]] of capital of 0.6 and population growth of 2%. If total factor
productivity growth is 1%, what is the sustainable growth rate in output according to
neoclassical theory?

### A. 2.0%.


### B. 2.7%.


### C. 4.5%.

2. Which of the following is the most accurate description of [[Club convergence|club convergence]]?
A. Less developed countries will converge to living standards of other less developed
countries.
B. More developed countries may see their standard of living drop due to competition from
less developed countries.
C. Some less developed countries may converge to developed country living standards while
others may not.
3. A chief economist argues that government policy should include an additional tax break for
research and development expenses. The economist most likely agrees with:
A. endogenous growth theory.
B. neoclassical theory.
C. classical theory.
Use the following information to answer Questions 4 through 5.
Jignesh Sangani, an economist with a large asset management firm, makes the following
statements about removal of barriers to trade and capital flows:
Statement 1: Removal of barriers is likely to lead to permanently higher global economic growth
under the neoclassical theory.
Statement 2: Removal of barriers is likely to lead to permanently higher economic growth for
developing countries only under the endogenous growth theory.
4. Sangani’s Statement 1 is most likely:
A. correct.
B. incorrect due to economic growth being permanent.
C. incorrect due to economic growth being global.
5. Sangani’s Statement 2 is most likely:
A. correct.

B. incorrect due to economic growth being permanent.
C. incorrect due to economic growth being limited to developing countries only.
6. Which of the following is least likely to be associated with the [[Law of diminishing returns|law of diminishing returns]]?
A. Investment in labor.
B. Investment in knowledge capital.
C. Investment in physical capital.


> [!abstract] Key Concepts
> LOS 6.a

Significant differences in growth rates exist between economies. The following factors are
positively related to growth rate:
Sufficient level of savings and investment.
Development of financial markets and financial intermediaries.
Political stability, sound laws, and property rights.
Investment in education and health care systems.
Lower taxes and regulatory burdens.
Free trade and unrestricted capital flows.
LOS 6.b

In the long-run, the rate of aggregate stock market appreciation is limited to the
sustainable growth rate of the economy.
LOS 6.c

Potential GDP represents the maximum output of an economy without putting upward
pressure on prices. Higher potential GDP growth increases the potential for stock returns
but also increases the credit quality of all fixed-income investments, all else equal.
In the short term, the difference between potential GDP and actual GDP may be useful for
predicting fiscal and monetary policy. If actual GDP is less than potential GDP, inflation is
unlikely and the government may follow an expansionary monetary/fiscal policy.
LOS 6.d

Capital deepening is an increase in the [[Capital Stock|capital stock]] and the capital to labor ratio. Due to
[[Diminishing marginal productivity|diminishing marginal productivity]] of capital, capital deepening will lead to only limited
increases in output and labor productivity if the capital to labor ratio is already high.
Technological progress enhances the productivity of both labor and capital but not the
relative productivity of either. The long-term growth rate can be increased by technological
progress (also called [[Total factor productivity|total factor productivity]]) since output and labor efficiency are
increased at all levels of capital to labor ratios. TFP is a scale factor. It however does not
alter the productivity function (alpha value).

LOS 6.e

LOS 6.f

Natural resources are essential to economic growth. Empirical evidence has shown,
however, that ownership of natural resources is not necessary for growth. As long as
nations can acquire natural resources through trade, they can experience substantial
growth. In some cases, ownership of natural resources may even inhibit growth since
countries with abundant natural resources may not develop other industries.
LOS 6.g

Quantity of labor is a function of population growth, workforce participation, immigration,
and average hours worked. All else equal, countries with higher population growth, higher
workforce participation, younger working-age populations, higher average hours worked,
and higher net immigration can grow faster due to higher labor input.
LOS 6.h

The economic growth rate of a country is positively correlated with investments in both
physical and human capital. Furthermore, technological development (as evidenced by
spending on R&D) is critical for economic growth. This is especially true for developed
countries that already have large [[Capital Stock|capital stock]] and a slower population growth rate.
LOS 6.i

Classical growth theory states that growth in [[Real GDP|real GDP]] per capita is temporary—when the
GDP per capita rises above the subsistence level, a population explosion occurs, and GDP
per capita is driven back to the subsistence level.
Neoclassical growth theory states that the sustainable growth rate of GDP is a function of
population growth, labor’s share of income, and the rate of technological advancement.
Growth gains from other means such as increased savings are only temporary.
Endogenous growth theory includes the impact of technological progress within the model.
Under endogenous growth theory, investment in capital can have constant returns, unlike
neoclassical theory that assumes diminishing returns to capital. This assumption allows for
a permanent increase in growth rate attributable to an increase in savings rate. Research
and development expenditures are often cited as examples of capital investment that
increase technological progress.
LOS 6.j

[[Absolute convergence|Absolute convergence]] states that the per capita growth rates (not growth level) will
converge (i.e., be the same across all countries). The [[Conditional convergence|conditional convergence]] hypothesis
assumes that convergence in living standards (i.e., level of per capita output) will only

occur for countries with the same savings rate, population growth, and production
functions.
The club convergence hypothesis contends that living standards in some less developed
countries may converge to living standards of developed standards if they are in the same
“club.” A club comprises countries with similar institutional structures (such as property
rights and political stability). Countries outside of the club (without the appropriate
institutional structures) will not see their living standards converge.
LOS 6.k

Under the endogenous growth theory, investments in R&D, though risky, often enhance
the productivity of the entire economy. Since the private investor only reaps part of the
benefit of those investments, it is likely that private sector investments in R&D will be less
than what would be optimal for the economy. Government subsidies can make these
investments more attractive to private businesses.
LOS 6.l

Economies grow faster in an environment of no trade barriers and free capital flows. Higher
growth rates are possible because foreign investment can provide capital to less developed
countries (neoclassical theory). The larger markets and greater opportunity to take
advantage of innovation will also increase the growth rate in open economies (endogenous
growth theory).
Finally, convergence of living standards is likely to be quicker in an [[Open economy|open economy]].

### Answer Key For Module Quizzes

Module Quiz 6.1, 6.2
1. B Financial intermediary development helps foster economic growth by allowing more
efficient allocation of capital and risk. (Module 6.1, LOS 6.a)
2. A Long-term growth in the stock market is a function of GDP growth. The other factors
—profits as a percentage of GDP and P/E ratios—will have a long-term growth rate of
approximately zero and will not impact a forecast of long-term growth in the stock
market. (Module 6.1, LOS 6.a)
3. C Potential GDP can be interpreted as the highest growth that can be obtained without
pressure on prices. Since actual GDP is lower than potential, there is little risk of
inflation. (Module 6.1, LOS 6.b)
4. C Since Minikaz is a developing country, it is likely to have a low capital base. With a low
capital base, increased capital expenditures will still have an impact on output per
worker. Technological progress always has a positive impact on output per worker.
(Module 6.1, LOS 6.d)

5. B Use the [[Growth Accounting|growth accounting]] relations and solving for growth in TFP.

6. C Empirical evidence has shown that for economic growth, access to natural resources
is more important than ownership. Natural resources may inhibit growth if countries
that own them do not develop other industries. However, that is not the conclusion
Smith reaches. (Module 6.2, LOS 6.f)
7. A Country X will have the greater opportunity due to the younger workforce, potential
labor input from [[Unemployed|unemployed]] workers, and immigration. (Module 6.2, LOS 6.g)
8. C Both human capital and ICT investment tend to have societal benefits. This spillover
effect enhances overall growth rate. (Module 6.2, LOS 6.h)
Module Quiz 6.3
1. C Using the equation from neoclassical theory, 1% / (1 − 0.6) + 2% = 4.5%. (LOS 6.i)
2. C The notion of the club is that some nations are not in the club and will not converge.
(LOS 6.j)
3. A Endogenous growth theory includes the concept that R&D may have external
benefits, and, therefore, should be subsidized by the government. (LOS 6.i)
4. B Under the neoclassical growth theory, the benefit of open markets is temporary. (LOS
6.i)
5. C Under the endogenous growth theory, open markets lead to higher rate of growth
permanently for all markets. (LOS 6.i)
6. B Knowledge capital is a special type of [[Public good|public good]] that is not subject to the law of
diminishing returns. Investment in labor and physical capital do exhibit diminishing
returns, which are reflected in the shape of the productivity curve. (LOS 6.k)

Topic Quiz: Economics
You have now finished the Economics topic section. Please log into your Schweser online
dashboard and take the Topic Quiz on this section. The Topic Quiz provides immediate
feedback on how effective your study has been for this material. Questions are more examlike than typical Module Quiz or QBank questions; a score of less than 70% indicates that
your study likely needs improvement. These tests are best taken timed; allow three minutes
per question.


### Formulas

Quantitative Methods
Multiple Regression

Economics


### Appendix A: Student’S Tdistribution


### Appendix B: F-Table At 5% (Upper


### Tail)


### Appendix C: Chi-Squared Table


### Index

A
[[Absolute convergence|absolute convergence]], 167
absolute purchasing power parity, 128
accuracy, 104
activation function, 85
[[Adjusted R2|adjusted R2]], 8
agglomerative clustering, 84
analysis of variance, 7
application programming interface (API), 95
[[ARCH Model]] model, 63
[[Autocorrelation]], 19
autoregressive conditional [[Heteroskedasticity]] (ARCH), 63
autoregressive models (AR), 48
average hours worked, 160

B
backward propagation, 85
bagging, 82
bag-of-words (BOW), 97
balance-of-payments, 134
base error, 78
bias error, 78, 106
bid-ask spread, 115, 118
bid-offer spread, 115
big data, 93
bootstrap aggregating, 82
Breusch–Godfrey (BG) test, 20
Breusch–Pagan (BP), 18

C

capital account, 134
capital controls, 135
capital deepening, 157
carry trade, 132
ceiling analysis, 107
centroid, 84
[[Chain rule of forecasting|chain rule of forecasting]], 48
chi-square, 100
chi square test, 17
classical growth theory, 164
[[Classification and Regression Trees (CART)|classification and regression trees (CART)]], 81
class imbalance, 103
club convergence, 167
clustering, 84
[[Cobb-Douglas Production Function|Cobb-Douglas production function]]on|production function]], 156
coefficient of determination, 8
[[Cointegration]], 65
[[Conditional convergence|conditional convergence]], 167
[[Conditional heteroskedasticity|conditional heteroskedasticity]]ty|heteroskedasticity]], 16
[[Confusion Matrix|confusion matrix]], 104
[[Constant returns to scale|constant returns to scale]], 156
[[Convergence Hypotheses|convergence hypotheses]], 167
co-occurrence, 99
[[Covariance|covariance]]ce [[Stationary|stationary]]|[[Covariance|covariance]] stationary]]ry|stationary]], 47, 65
[[Covered interest rate parity|covered interest rate parity]], 124
crash risk, 133
cross rate, 117
cross validation, 79
currency crisis, 139
current account, 134

D
data cleansing, 95
data wrangling, 95
debt sustainability mechanism, 135
[[Deep Learning]], 76
degree of freedom, 18
demographics, 160
[[Dependent|dependent]]nt variable|[[Dependent|dependent]] variable]], 12

predicting, 12
DF–EG test, 65
Dickey and Fuller (DF), 55, 65
Dickey Fuller, 65
divisive clustering, 85
document frequency (DF), 100
document term matrix, 97
Dornbusch overshooting model, 137
dummy variables, 25, 27
Durbin–Watson (DW) [[Statistic|statistic]], 20

E
economic growth, 156
endogenous growth theory, 166
Engle and Granger (EG), 65
ex-ante version of PPP, 128
exchange rate, 115
exploratory data analysis (EDA), 98

F
F1 score, 104
feature engineering (FE), 99
feature extraction, 98
features, 75
feature selection, 98, 99, 100
[[Financial account|financial account]], 134
first differencing, 55
fiscal policy, 136
fitting curve, 106
flow mechanism, 134
forecasting, 51
forward contract, 116
forward discount, 120
forward exchange rate, 116
forward premium, 120
forward propagation, 85
[[F-Statistic]], 12

full model, 10

G
generalize, 78
generalized linear models (GLMs), 102
grid search, 107
ground truth, 102
growth accounting relation, 158

H
[[Heteroskedasticity|heteroskedasticity]], 16
[[Heteroskedasticity-consistent standard errors|heteroskedasticity-consistent standard errors]], 19, 20
[[Hierarchical Clustering|hierarchical clustering]], 84
high-leverage points, 23
human capital, 161
hyperparameters, 75, 107

I
immigration, 160
incentives to private investment, 167
influential data points, 23
in-sample forecasts, 51
instability, 52
intercept dummy, 25
intercept term, 3
[[International Fisher Effect|international Fisher effect]]ct|Fisher effect]], 127
intervention in the FX market, 139

K
k-fold cross validation, 79
[[K-Means Clustering|k-means clustering]], 84
[[k-Nearest Neighbor (KNN)|k-nearest neighbor (KNN)]], 81
kurtosis, 133

L
labor force, 160
labor force participation, 160
labor productivity, 156
lag, 60
learning curve, 78
least absolute shrinkage and selection operator ([[LASSO]]), 80
lemmatization, 97
[[Likelihood|likelihood]] ratio (LR), 29
[[Linear trend|linear trend]], 39
logistic regression model, 27
[[Logit model|logit model]], 27
log-[[Linear trend|linear trend]] model, 43, 67

M
[[Machine Learning]] (ML), 75
mark-to-market value, 122
maximum [[Likelihood|likelihood]] [[Estimation|estimation]], 27
[[Mean reversion|mean reversion]], 50
mean-reverting level, 50
metadata, 95
method selection, 102
model fit, 49
model misspecification, 13
monetary approach, 137
monetary policy, 136
[[CFA_Glossary/Multicollinearity]], 20
[[Multiple Regression]], 1, 16
assumptions, 4
assumption violation, 16
formulation, 3
interpretation, 3
Mundell-Fleming model, 135
mutual information (MI), 100

N

name entity recognition (NER), 101
natural resources, 159
negative [[Autocorrelation]], 19
neoclassical growth theory, 164
nested models, 10
[[Neural Networks|neural networks]] (NNs), 76, 85, 102
neurons, 85
Newey-West corrected standard errors, 20
N-grams, 97, 101
[[Nonstationarity|nonstationarity]], 52
normalization, 96

O
omitting a variable, 15
one-hot encoding (OHE), 99
ordinary least squares (OLS), 40
outliers, 23
out-of-sample forecasts, 51
[[Overfitting]], 8, 78

P
parameters, 107
parity conditions, 129
partial slope coefficient, 3
parts of speech (POS), 101
penalized regressions, 80
physical capital, 161
pooling data, 16
portfolio balance (asset market) approach, 138
portfolio balance mechanism, 135
positive [[Serial Correlation|serial correlation]], 19
potential GDP, 154
precision, 104
[[Principal Component Analysis]] ([[Principal Component Analysis]]), 84, 99
pruned, 82
public infrastructure, 162
[[Purchasing power parity (PPP)|purchasing power parity (PPP)]], 127

pure monetary model, 137
[[P-Value]], 2

Q
qualitative [[Dependent variable|dependent variable]], 27

R
[[Random Forest]], 83
[[Random walk]] process, 53
README files, 95
real interest rate parity, 127
recall, 104
receiver operating characteristic (ROC), 104
regression analysis, 16, 17
[[Heteroskedasticity|heteroskedasticity]], 17
model misspecification, 13
regression assumptions, 16
regression [[Model specification|model specification]], 13
regular expression (regex), 96
[[Regularization]], 80
reinforced learning, 76
reinforcement learning (RL), 86
relative dynamism (rd), 155
relative purchasing power parity, 128
residual, 2
residual plot, 17
restricted model, 10
[[Robust standard errors|robust standard errors]], 19, 20
[[Root Mean Squared Error (RMSE)|root mean squared error (RMSE)]], 52, 68
root mean square error (RMSE), 105

### R2 , 8

adjusted, 8
coefficient of determination, 8

S

Savings and investment, 153
scaling, 96
scaling variables, 15
[[Seasonality|seasonality]], 59
seasonal lag, 60
[[Serial Correlation|serial correlation]], 19
skewness, 133
slope dummy, 25
spot exchange rate, 116
standardization, 96
statistical inferences, 47
steady state growth rate, 164
stemming, 97
structural change, 66
structured data, 93
[[Studentized Residuals|studentized residuals]], 23
summation operator, 85
[[Supervised Learning]], 76
[[Support Vector Machine]] ([[Support Vector Machine]]), 81, 102
sustainability of economic growth, 160
sustainable growth rate, 154

T
target variable, 75
technological development, 162
technological progress, 156
term frequency, 99
test sample, 78
text preparation or cleansing, 96
text processing, 96
text wrangling, 97
[[Time series]], 39
token, 97
tokenization, 97
total factor cost, 156
[[Total Factor Productivity (TFP)|total factor productivity (TFP)]], 156
trade barriers, 168
training dataset, 75
training sample, 78

transforming variables, 15
trend model, 39
triangular arbitrage, 118
trimming, 96
tuning, 103
Type I errors, 19, 23

U
unbiased predictor, 126
[[Unconditional heteroskedasticity|unconditional heteroskedasticity]], 16
uncovered interest rate parity, 125
[[Unit root]], 54
unrestricted model, 10
unstructured data, 93
[[Unsupervised Learning]], 76

V
validation sample, 78
variance error, 78, 106
[[Variance Inflation Factor (VIF)|variance inflation factor (VIF)]], 21
veracity, 93
violations of regression assumptions, 16
voting classifier, 82

W
[[White-corrected standard errors|white-corrected standard errors]], 19
winsorization, 96
word cloud, 99


---

