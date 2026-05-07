---
title: "Fixed Income"
subject: "Fixed Income"
tags: [CFA-L2, fixed-income]
aliases: []
---

# Fixed Income

*CFA Level II — Schweser Notes 2025*

---

## Readings

- [[#Reading 23 — The Term Structure and Interest Rate Dynamics|Reading 23: The Term Structure and Interest Rate Dynamics]]
- [[#Reading 24 — The Arbitrage-Free Valuation Framework|Reading 24: The Arbitrage-Free Valuation Framework]]
- [[#Reading 25 — Valuation and Analysis of Bonds with Embedded Options|Reading 25: Valuation and Analysis of Bonds with Embedded Options]]
- [[#Reading 27 — Credit Default Swaps|Reading 27: Credit Default Swaps]]

---

# Reading 23 — The Term Structure and Interest Rate Dynamics


> [!tip] Exam Focus
> This topic review discusses the theories and implications of the [[Term structure]] of interest
> rates. In addition to understanding the relationships between [[Spot rates|spot rates]], forward rates,
> [[Yield to maturity]], and the shape of the [[Yield curve]], be sure you become familiar with
> concepts like the [[Z-Spread]], the [[TED spread]] and the MRR-OIS spread. Interpreting the shape
> of the [[Yield curve|yield curve]] in the context of the theories of the [[Term structure|term structure]] of interest rates is
> always important for the exam. Also pay close attention to the concept of key rate
> [[Duration]].


### Introduction

The financial markets both impact and are controlled by interest rates. Understanding the
[[Term structure|term structure]] of interest rates (i.e., the graph of interest rates at different maturities) is
one key to understanding the performance of an economy. In this reading, we explain how
and why the [[Term structure|term structure]] changes over time.
[[Spot rates|Spot rates]] are the annualized market interest rates for a single payment to be received in
the future. Generally, we use [[Spot rates|spot rates]] for government securities (risk-free) to generate
the [[Spot rate]] curve. [[Spot rates|Spot rates]] can be interpreted as the yields on [[Zero-coupon bonds|zero-coupon bonds]], and
for this reason we sometimes refer to spot rates as zero-coupon rates. A [[Forward rate]] is an
[[Interest rate|interest rate]] (agreed to today) for a loan to be made at some future date.

> [!pnote] Professor's Note
> ***While most of the LOS in this topic review have describe or explain as the***
> ***command words, we will still delve into numerous calculations, as it is difficult***
> ***to really understand some of these concepts without getting in to the***
> ***mathematics behind them.***

## Module 23.1: Spot and Forward Rates, Part 1


> **LOS 23.a:** Describe relationships among spot rates, forward rates, yield to
maturity, expected and realized returns on bonds, and the shape of the
[[Yield curve|yield curve]].

Spot Rates
The price today of $1 par, [[Zero-coupon bond|zero-coupon bond]] is known as the [[Discount factor|discount factor]], which we will
call PT. Because it is a [[Zero-coupon bond|zero-coupon bond]], the spot [[Interest rate|interest rate]] is the [[Yield to maturity|yield to maturity]] of
this payment, which we represent as ST. The relationship between the [[Discount factor|discount factor]] PT
and the [[Spot rate|spot rate]] ST for maturity T can be expressed as:

The term structure of spot rates—the graph of the [[Spot rate|spot rate]] ST versus the maturity T—is
known as the [[Spot yield curve|spot yield curve]] or [[Spot curve|spot curve]]. The shape and level of the [[Spot curve|spot curve]] changes
continuously with the market prices of bonds.

Forward Rates
The annualized [[Interest rate|interest rate]] on a loan to be initiated at a future period is called the
[[Forward rate|forward rate]] for that period. The term structure of forward rates is called the forward
curve. (Note that forward curves and spot curves are mathematically related—we can
derive one from the other.)
We will use the following notation:

[[Yield to maturity|Yield to Maturity]]
As we’ve discussed, the [[Yield to maturity|yield to maturity]] (YTM) or yield of a [[Zero-coupon bond|zero-coupon bond]] with
maturity T is the spot interest rate for a maturity of T. However, for a coupon bond, if the
[[Spot rate|spot rate]] curve is not flat, the YTM will not be the same as the [[Spot rate|spot rate]].

### Example: Spot rates and yield for a coupon bond


Compute the price and [[Yield to maturity|yield to maturity]] of a three-year, 4% annual-pay, $1,000 face
value bond given the following [[Spot rate|spot rate]] curve: S1 = 5%, S2 = 6%, and S3 = 7%.

Answer:
1. Calculate the price of the bond using the spot rate curve:

2. Calculate the [[Yield to maturity|yield to maturity]] (y3):

Note that the yield on a three-year bond is a weighted average of three spot rates, so in
this case we would expect S1 < y3 < S3. The yield to maturity y3 is closest to S3 because
the par value dominates the value of the bond and therefore S3 has the highest weight.

Expected and Realized Returns on Bonds
Expected return is the ex-ante holding period return that a bond investor expects to earn.
The [[Expected Return]] will be equal to the bond’s yield only when all three of the following
are true:
The bond is held to maturity.
All payments (coupon and principal) are made on time and in full.
All coupons are reinvested at the original YTM.
The second requirement implies that the bond is option-free and there is no default risk.
The last requirement, reinvesting coupons at the YTM, is the least realistic assumption. If
the yield curve is not flat, the coupon payments will not be reinvested at the YTM and the
expected return will differ from the yield.
Realized return on a bond refers to the actual return that the investor experiences over the
investment’s holding period. Realized return is based on actual reinvestment rates.

The Forward Pricing Model
The forward pricing model values forward contracts based on arbitrage-free pricing.
Consider two investors.
Investor A purchases a $1 face value, zero-coupon bond maturing in j+k years at a price of
P(j+k).
Investor B enters into a j-year [[Forward contract]] to purchase a $1 face value, zero-coupon
bond maturing in k years at a price of F(j,k). Investor B’s cost today is the [[Present Value]] of
the cost: PV[F(j,k)] or PjF(j,k).
Because the $1 cash flows at j+k are the same, these two investments should have the
same price, which leads to the forward pricing model:

Therefore:


### Example: Forward pricing


Calculate the forward price two years from now for a $1 par, zero-coupon, three-year
bond given the following spot rates.
The two-year spot rate, S2 = 4%.
The five-year spot rate, S5 = 6%.
Answer:
Calculate discount factors Pj and P(j+k).

The forward price of a three-year bond in two years is represented as F(2,3)

In other words, $0.8082 is the price agreed to today, to pay in two years, for a three-year
bond that will pay $1 at maturity.

> [!pnote] Professor's Note
> ***In the [[Derivatives|Derivatives]] portion of the curriculum, the [[Forward price|forward price]] is computed as***
> ***the [[Future Value]] (for j periods) of P(j+k). It gives the same result and can be***
> ***verified using the data in the previous example by computing the future value***
> ***of P5 (i.e., [[Compounding|compounding]] for two periods at S2). FV = 0.7473(1.04)2 = $0.8082.***
>
> ***The [[Forward rate|Forward Rate]]te model|[[Forward rate|Forward Rate]] Model]]***
> ***The [[Forward rate model|forward rate model]] relates forward and spot rates as follows:***
> ***or***
> ***This model is useful because it illustrates how forward rates and spot rates are interrelated.***
> ***This equation suggests that the [[Forward rate|forward rate]] f(2,3) should make investors indifferent***
> ***between buying a five-year [[Zero-coupon bond|zero-coupon bond]] versus buying a two-year zero-coupon bond***
> ***and at maturity reinvesting the [[Principal|principal]] for three additional years.***

### Example: Forward rates


Suppose that the two-year and five-year spot rates are S2 = 4% and S5 = 6%.
Calculate the implied three-year [[Forward rate|forward rate]] for a loan starting two years from now
[i.e., f(2,3)].
Answer:

Note that the forward rate f(2,3) > S5 because the [[Yield curve|yield curve]] is upward sloping.
If the [[Yield curve|yield curve]] is upward sloping, [i.e., S(j+k) > Sj], then the forward rate corresponding to
the period from j to k [i.e., f(j,k)] will be greater than the spot rate for maturity j+k [i.e.,
S(j+k)]. The opposite is true if the curve is downward sloping.

> **LOS 23.b:** Describe how zero-coupon rates (spot rates) may be obtained
from the [[Par curve|par curve]] by [[Bootstrapping|bootstrapping]].
A [[Par Rate]] is the yield to maturity of a bond trading at par. Par rates for bonds with
different maturities make up the par rate curve or simply the [[Par curve|par curve]]. By definition, the
par rate will be equal to the [[Coupon rate]] on the bond. Generally, [[Par curve|par curve]] refers to the par
rates for government or [[Benchmark|benchmark]] bonds.
By using a process called [[Bootstrapping|bootstrapping]], spot rates or zero-coupon rates can be derived
from the [[Par curve|par curve]]. [[Bootstrapping|Bootstrapping]] involves using the output of one step as an input to the
next step. We first recognize that (for annual-pay bonds) the one-year spot rate (S1) is the
same as the one-year par rate. We can then compute S2 using S1 as one of the inputs.
Continuing the process, we can compute the three-year spot rate S3 using S1 and S2
computed earlier. Let’s clarify this with an example.

### Example: Bootstrapping spot rates


Given the following (annual-pay) [[Par curve|par curve]], compute the corresponding spot rate curve:

Answer:
S1 = 1.00% (given directly).
If we discount each cash flow of the bond using its yield, we get the market price of the
bond. Here, the market price is the [[Par value|par value]]. Consider the 2-year bond.

Alternatively, we can also value the 2-year bond using spot rates:

Multiplying both sides by

, we get (1 + S2)2 = 1.0252.

Taking square roots, we get (1 + S2) = 1.01252. S2 = 0.01252 or 1.252%

Using the values of S1 and S2 computed earlier,


### Module Quiz 23.1

1. When the yield curve is downward sloping, the forward curves are most likely to lie:
A. above the [[Spot curve|spot curve]].
B. below the [[Spot curve|spot curve]].
C. either above or below the spot curve.
2. The model that equates buying a long-maturity zero-coupon bond to entering into a forward
contract to buy a zero-coupon bond that matures at the same time is known as the:
A. [[Forward rate model|forward rate model]].
B. [[Forward pricing model|forward pricing model]].
C. forward [[Arbitrage|arbitrage]] model.


## Module 23.2: Spot and Forward Rates, Part 2


> **LOS 23.c:** Describe the assumptions concerning the evolution of spot rates
in relation to forward rates implicit in active bond portfolio management.

Relationships Between Spot and Forward Rates
For an upward-sloping spot curve, the forward rate rises as j increases. (For a downwardsloping yield curve, the forward rate declines as j increases.) For an upward-sloping spot
curve, the [[Forward curve|forward curve]] will be above the spot curve as shown in Figure 23.1. Conversely,
when the spot curve is downward sloping, the [[Forward curve|forward curve]] will be below it.

**Figure 23.1 shows spot and forward curves as of July 2013. Because the [[Spot yield curve|spot yield curve]] is**

upward sloping, the forward curves lie above the spot curve.

**Figure 23.1: Spot Curve and Forward Curves**


From the [[Forward rate model|forward rate model]]:
which can be expanded to:
In other words, the spot rate for a long-maturity security will equal the [[Geometric mean|geometric mean]] of
the one period spot rate and a series of one-year forward rates.
[[Forward price|Forward Price]] Evolution
If the future spot rates actually evolve as forecasted by the [[Forward curve|forward curve]], the forward
price will remain unchanged. Therefore, a change in the [[Forward price|forward price]] indicates that the
future spot rate(s) did not conform to the [[Forward curve|forward curve]]. When spot rates turn out to be
lower (higher) than implied by the forward curve, the [[Forward price|forward price]] will increase

(decrease). A trader expecting lower future spot rates (than implied by the current forward
rates) would purchase the [[Forward contract|forward contract]] to profit from its appreciation.
For a bond investor, the return on a bond over a one-year horizon is always equal to the
one-year [[Risk-Free Rate]] if the spot rates evolve as predicted by today’s forward curve. If the
spot curve one year from today is not the same as that predicted by today’s forward curve,
the return over the one-year period will differ, with the return depending on the bond’s
maturity.
An active portfolio manager will try to outperform the overall bond market by predicting
how the future spot rates will differ from those predicted by the current forward curve.

### Example: Spot rate evolution


Jane Dash, CFA, has collected [[Benchmark|benchmark]] spot rates as shown here:

The expected spot rates at the end of one year are as follows:

Calculate the one-year [[Holding period return|holding period return]] of a:
1. 1-year zero-coupon bond.
2. 2-year zero-coupon bond.
3. 3-year zero-coupon bond.
Answer:
First, note that the expected spot rates provided just happen to be the forward rates
implied by the current spot rate curve.
Recall that:

Hence:

1. The price of a one-year zero-coupon bond given the one-year spot rate of 3% is 1 /
(1.03) or 0.9709.

After one year, the bond is at maturity and pays $1 regardless of the spot rates.
Hence the [[Holding period return|holding period return]] =
2. The price of a two-year zero-coupon bond given the two-year spot rate of 4%:

After one year, the bond will have one year remaining to maturity, and based on a
one-year expected spot rate of 5.01%, the bond’s price will be 1 / (1.0501) = $0.9523
Hence, the [[Holding period return|holding period return]] =
3. The price of three-year zero-coupon bond given the three-year spot rate of 5%:

After one year, the bond will have two years remaining to maturity. Based on a twoyear expected spot rate of 6.01%, the bond’s price will be 1 / (1.0601)2 = $0.8898
Hence, the [[Holding period return|holding period return]] =
Hence, regardless of the maturity of the bond, the holding period return will be the oneyear spot rate if the spot rates evolve [[Consistent|consistent]] with the forward curve (as it existed
when the trade was initiated).
If an investor believes that future spot rates will be lower than corresponding forward
rates, then she will purchase bonds (at a presumably attractive price) because the market
appears to be discounting future cash flows at “too high” of a [[Discount rate]].

> **LOS 23.d:** Describe the strategy of [[Rolling Down the Yield Curve|rolling down the yield curve]].

“[[Rolling Down the Yield Curve|Rolling Down the Yield Curve]]”
The most straightforward strategy for a bond investor is maturity matching—purchasing
bonds that have a maturity equal to the investor’s investment horizon.
However, with an upward-sloping interest rate term structure, investors seeking superior
returns may pursue a strategy called [[Riding the yield curve|riding the yield curve]] (also known as rolling down the
yield curve). Under this strategy, an investor will purchase bonds with maturities longer
than his investment horizon. In an upward-sloping yield curve, shorter maturity bonds have
lower yields than longer maturity bonds. As the bond approaches maturity (i.e., rolls down
the yield curve), it is valued using successively lower yields and, therefore, at successively
higher prices.
If the yield curve remains unchanged over the investment horizon, [[Riding the yield curve|riding the yield curve]]
strategy will produce higher returns than a simple maturity [[Matching strategy|matching strategy]], increasing
the [[Total return|total return]] of a bond portfolio. The greater the difference between the forward rate
and the spot rate, and the longer the maturity of the bond, the higher the [[Total return|total return]].

Consider Figure 23.2, which shows a hypothetical upward-sloping yield curve and the price
of a 3% annual-pay coupon bond (as a percentage of par).

**Figure 23.2: Price of a 3%, Annual Pay Bond**


A bond investor with an investment horizon of five years could purchase a bond maturing
in five years and earn the 3% coupon but no capital gains (the bond can be currently
purchased at par and will be redeemed at par at maturity). However, assuming no change
in the yield curve over the investment horizon, the investor could instead purchase a 30year bond for $63.67, hold it for five years, and sell it for $71.81, earning an additional
return beyond the 3% coupon over the same period.
In the aftermath of the financial crisis of 2007–08, [[Central banks|central banks]] kept short-term rates low,
giving yield curves a steep upward slope. Many active managers took advantage by
borrowing at short-term rates and buying long maturity bonds. The risk of such a leveraged
strategy is the possibility of an increase in spot rates.

### Module Quiz 23.2

1. If the future spot rates are expected to be lower than the current forward rates for the same
maturities, bonds are most likely to be:
A. overvalued.
B. undervalued.
C. correctly valued.
2. The strategy of [[Rolling Down the Yield Curve|rolling down the yield curve]] is most likely to produce superior returns for a
fixed income portfolio manager investing in bonds with maturity higher than the manager’s
investment horizon when the spot rate curve:
A. is downward sloping.
B. in the future matches that projected by today’s forward curves.
C. is upward sloping.


## Module 23.3: The Swap Rate Curve


> **LOS 23.e:** Explain the [[Swap rate|swap rate]]te curve|[[Swap rate|swap rate]] curve]] and why and how market
participants use it in [[Valuation|valuation]].


The [[Swap rate curve|Swap Rate Curve]]
In a plain vanilla [[Interest rate swap]], one party makes payments based on a fixed rate while
the counterparty makes payments based on a floating rate. The fixed rate in an interest
rate swap is called the swap fixed rate or [[Swap rate]].

If we consider how swap rates vary for various maturities, we get the [[Swap rate|swap rate]]te curve|[[Swap rate|swap rate]] curve]],
which has become an important interest-rate [[Benchmark|benchmark]] for credit markets.
Market participants prefer the [[Swap rate curve|swap rate curve]] as a [[Benchmark|benchmark]] interest rate curve rather
than a government bond yield curve for the following reasons:
Swap rates reflect the [[Credit risk]] of commercial banks rather than the [[Credit risk|credit risk]] of
governments.
The swap market is not regulated by any government, which makes swap rates in
different countries more comparable. (Government bond yield curves additionally reflect
[[Sovereign risk|sovereign risk]] unique to each country.)
The [[Swap curve|swap curve]] typically has yield quotes at many maturities, while the U.S. government
bond yield curve has [[On-the-run|on-the-run]] issues trading at only a small number of maturities.
Wholesale banks that manage [[Interest rate risk]] with swap contracts are more likely to use
swap curves to value their assets and [[Liabilities|liabilities]]. Retail banks, on the other hand, are more
likely to use a government bond yield curve.
Given a [[Notional principal|notional principal]] of $1 and a swap fixed rate SFRT, the value of the fixed rate
payments on a swap can be computed using the relevant (e.g., MRR) spot rate curve. For a
given swap tenor T, we can solve for SFR in the following equation.

In the equation, SFR can be thought of as the [[Coupon rate|coupon rate]] of a $1 [[Par value|par value]] bond given the
[[Underlying|underlying]] spot rate curve.

> [!pnote] Professor's Note
> ***Prior to the 2023 curriculum, CFA Institute referenced LIBOR (the “London***
> ***Interbank Offered Rate”) as the [[Underlying|underlying]] interest rate for [[Derivative|derivative]]***
> ***instruments. However, concerns about LIBOR being manipulated have led to***
> ***LIBOR being replaced in recent years with other reference rates, such as the***
> ***Federal Reserve Bank of New York’s “SOFR” (Secured Overnight Financing Rate),***
> ***and the Bank of England’s “SONIA” (Sterling Overnight Index Average).***
> ***To reflect this change, the CFA curriculum now uses the generic term MRR***
> ***(“market reference rate”) to refer to these various LIBOR replacements.***

### Example: Swap rate curve


Given the following MRR spot rate curve, compute the swap fixed rate for a tenor of 1,
2, and 3 years (i.e., compute the swap rate curve).

Answer:
1. SFR1 can be computed using the equation:

2. SFR2 can be similarly computed:

3. Finally, SFR3 can be computed as:


> [!pnote] Professor's Note
> ***A different (and better) method of computing swap fixed rates is discussed in***
> ***detail in the [[Derivatives|Derivatives]] portion of the curriculum.***

### Module Quiz 23.3

1. Which of the following statements about the swap rate curve is most accurate?
A. The swap rate reflects the interest rate for the floating-rate leg of an [[Interest rate swap|interest rate swap]].
B. Retail banks are more likely to use the swap rate curve as a benchmark than the
government spot curve.
C. Swap rates are comparable across different countries because the swap market is not
controlled by governments.


## Module 23.4: Spread Measures


> **LOS 23.f:** Calculate and interpret the [[Swap spread|swap spread]] for a given maturity.


[[Swap spread|Swap spread]] refers to the amount by which the swap rate exceeds the yield of a
government bond with the same maturity.
For example, if the fixed rate of a one-year fixed-for-floating MRR swap is 0.57% and the
one-year Treasury is yielding 0.11%, the 1-year [[Swap spread|swap spread]] is 0.57% − 0.11% = 0.46%, or
46 bps.
Swap spreads are almost always positive, reflecting the lower [[Credit risk|credit risk]] of governments
compared to the [[Credit risk|credit risk]] of surveyed banks that determines the swap rate.
The swap rate curve is arguably the most commonly used interest rate curve. This rate
curve roughly reflects the [[Default risk|default risk]] of a commercial bank with a credit rating of A1/A+.


### Example: Swap spread


The two-year fixed-for-floating swap rate is 2.02% and the two-year U.S. Treasury bond
is yielding 1.61%. What is the [[Swap spread|swap spread]]?
Answer:


> **LOS 23.g:** Describe short-term interest rate spreads used to gauge e
­ conomywide [[Credit risk|credit risk]] and [[Liquidity|liquidity]]ty risk|[[Liquidity|liquidity]] risk]].

I-Spread
The I-spread, or [[Interpolated spread|interpolated spread]], for a credit-risky bond is the amount by which the
yield on the risky bond exceeds the swap rate for the same maturity. In a case where the
swap rate for a specific maturity is not available, the missing swap rate can be estimated
from the swap rate curve using [[Linear interpolation|linear interpolation]].

### Example: I-spread


6% Zinni, Inc., bonds are currently yielding 2.35% and mature in 1.6 years. From the
provided [[Swap curve|swap curve]], compute the I-spread.
[[Swap curve|Swap curve]]:

Answer:
[[Linear interpolation|Linear interpolation]]:
First, recognize that 1.6 years falls in the 1.5-to-2-year interval.
Interpolated rate = rate for [[Lower bound|lower bound]] + (# of years for interpolated rate − # of
years for [[Lower bound|lower bound]])(higher bound rate − [[Lower bound|lower bound]] rate) / (# of years for upper
bound − # of years for [[Lower bound|lower bound]])
1.6-year swap rate =

I-spread = yield on the bond − swap rate = 2.35% − 1.38% = 0.97% or 97 bps

While a bond’s yield reflects [[Time value|time value]] as well as compensation for credit and [[Liquidity risk|liquidity risk]],
I-spread only reflects compensation for credit and [[Liquidity|liquidity]] risks. The higher the I-spread,
the higher the compensation for [[Liquidity|liquidity]] and credit risk.

The Z-Spread
The Z-spread is the spread that, when added to each spot rate on the default-free spot
curve, makes the present value of a bond’s cash flows equal to the bond’s market price.
Therefore, the Z-spread is a spread over the entire spot rate curve.
For example, suppose the one-year spot rate is 4% and the two-year spot rate is 5%. The
market price of a two-year bond with annual coupon payments of 8% is $104.12. The Zspread is the spread that balances the following equality:

In this case, the Z-spread is 0.008, or 80 basis points. (Plug Z = 0.008 into the right-handside of the equation just listed to reassure yourself that the present value of the bond’s
cash flows equals $104.12).
The term zero [[Volatility|volatility]] in the Z-spread refers to the assumption of zero interest rate
[[Volatility|volatility]]. Z-spread is not appropriate to use to value bonds with [[Embedded options|embedded options]];
without any interest rate [[Volatility|volatility]] options are meaningless. If we ignore the embedded
options for a bond and estimate the Z-spread, the estimated Z-spread will include the cost
of the [[Embedded option]] (i.e., it will reflect compensation for option risk as well as
compensation for credit and [[Liquidity risk|liquidity risk]]).

### Example: Computing the price of an option-free risky bond using Z-spread


A three-year, 5% annual-pay ABC, Inc., bond trades at a Z-spread of 100 bps over the
benchmark spot rate curve.
The benchmark one-year spot rate, one-year forward rate in one year and one-year
forward rate in year 2 are 3%, 5.051%, and 7.198%, respectively.
Compute the bond’s price.
Answer:
First derive the spot rates:

value (with Z-spread) =

[[TED spread|TED Spread]]
The “TED” in “[[TED spread|TED spread]]” is an acronym that combines the “T” in “T-bill” with “ED” (the
ticker symbol for the Eurodollar [[Futures contract]]).
Conceptually, the [[TED spread|TED spread]] is the amount by which the MRR exceeds the interest rate on
short-term U.S. government debt of the same maturity.
For example, if three-month MRR is 0.33% and the three-month T-bill rate is 0.03%, then:

Because T-bills are considered to be risk free while MRR reflects the risk of lending to
commercial banks, the [[TED spread|TED spread]] is seen as an indication of the credit and [[Liquidity risk|liquidity risk]] in
the banking sector. A rising TED spread indicates that market participants believe banks are
increasingly likely to default on loans and that risk-free T-bills are becoming more valuable
in comparison. The TED spread captures the risk in the banking system more accurately
than does the 10-year [[Swap spread|swap spread]].

MRR-OIS Spread
OIS stands for overnight indexed swap and represents interest rate on unsecured overnight
lending between banks. The OIS rate roughly reflects the [[Federal funds rate|federal funds rate]] and includes
minimal counterparty credit risk.
The MRR-OIS spread (formerly the LIBOR-OIS spread) is the amount by which the MRR
(which includes some credit risk) exceeds the OIS rate (which includes only minimal credit
risk) and also indicates the level of credit and liquidity risk in the banking system.

### Module Quiz 23.4

1. The swap spread for a default-free bond is least likely to reflect the bond’s:
A. [[Mispricing|mispricing]] in the market.
B. illiquidity.
C. [[Time value|time value]].
2. Which of the following statements about the Z-spread is most accurate? The Z-spread is the:
A. difference between the yield to maturity of a bond and the linearly interpolated swap
rate.
B. spread over the Treasury spot curve that a bond would trade at if it had zero embedded
options.
C. spread over the Treasury spot curve required to match the value of a bond to its current
market price.
3. The TED spread is calculated as the difference between:
A. the three-month MRR and the three-month T-bill rate.
B. MRR and the overnight indexed swap rate.

C. the three-month T-bill rate and the overnight indexed swap rate.


## Module 23.5: Term Structure Theory


> **LOS 23.h:** Explain traditional theories of the term structure of interest
rates and describe the implications of each theory for forward rates and
the shape of the yield curve.


We’ll explain each of the theories of the term structure of interest rates, paying particular
attention to the implications of each theory for the shape of the yield curve and the
interpretation of forward rates.

[[Unbiased expectations theory|Unbiased Expectations Theory]]
Under the [[Unbiased expectations theory|unbiased expectations theory]] or the [[Pure expectations theory|pure expectations theory]], we hypothesize
that it is investors’ expectations that determine the shape of the interest rate term
structure.
Specifically, this theory suggests that forward rates are solely a function of expected future
spot rates, and that every maturity strategy has the same expected return over a given
investment horizon. In other words, long-term interest rates equal the mean of future
expected short-term rates. This implies that an investor should earn the same return by
investing in a five-year bond or by investing in a three-year bond and then a two-year bond
after the three-year bond matures. Similarly, an investor with a three-year investment
horizon would be indifferent between investing in a three-year bond or in a five-year bond
that will be sold two years prior to maturity. The [[Underlying|underlying]] principle behind the pure
expectations theory is risk neutrality: Investors don’t demand a [[Risk premium]] for maturity
strategies that differ from their investment horizon.
For example, suppose the one-year spot rate is 5% and the two-year spot rate is 7%. Under
the [[Unbiased expectations theory|unbiased expectations theory]], the one-year forward rate in one year must be 9%
because investing for two years at 7% yields approximately the same annual return as
investing for the first year at 5% and the second year at 9%. In other words, the two-year
rate of 7% is the average of the expected future one-year rates of 5% and 9%. This is shown
in Figure 23.3.

**Figure 23.3: Spot and Future Rates**


Notice that in this example, because short-term rates are expected to rise (from 5% to 9%),
the yield curve will be upward sloping.

Therefore, the implications for the shape of the yield curve under the pure expectations
theory are:
If the yield curve is upward sloping, short-term rates are expected to rise.
If the curve is downward sloping, short-term rates are expected to fall.
A flat yield curve implies that the market expects short-term rates to remain constant.

[[Local expectations theory|Local Expectations Theory]]
The [[Local expectations theory|local expectations theory]] is similar to the [[Unbiased expectations theory|unbiased expectations theory]] with one
major difference: the [[Local expectations theory|local expectations theory]] preserves the risk-neutrality assumption
only for short holding periods. In other words, over longer periods, risk premiums should
exist. This implies that over short time periods, every bond (even long-maturity risky
bonds) should earn the risk-free rate.
The [[Local expectations theory|local expectations theory]] can be shown not to hold because the short-holding-period
returns of long-maturity bonds can be shown to be higher than short-holding-period
returns on short-maturity bonds due to liquidity premiums and hedging concerns.

[[Liquidity preference theory|Liquidity Preference Theory]]
The [[Liquidity preference theory|liquidity preference theory]] of the term structure addresses the shortcomings of the
[[Pure expectations theory|pure expectations theory]] by proposing that forward rates reflect investors’ expectations of
future spot rates, plus a [[Liquidity premium|liquidity premium]] to compensate investors for exposure to interest
rate risk. Furthermore, the theory suggests that this [[Liquidity premium|liquidity premium]] is positively related
to maturity: a 25-year bond should have a larger [[Liquidity premium|liquidity premium]] than a five-year bond.
Thus, the [[Liquidity preference theory|liquidity preference theory]] states that forward rates are biased estimates of the
market’s expectation of future rates because they include a [[Liquidity premium|liquidity premium]]. Therefore, a
positive-sloping yield curve may indicate that either: (1) the market expects future interest
rates to rise or (2) rates are expected to remain constant (or even fall), but the addition of
the liquidity premium results in a positive slope. A downward-sloping yield curve indicates
steeply falling short-term rates according to the [[Liquidity preference theory|liquidity preference theory]].
The size of the liquidity premiums need not be constant over time. They may be larger
during periods of greater economic uncertainty when [[Risk aversion|risk aversion]] among investors is
higher.

[[Segmented markets theory|Segmented Markets Theory]]
Under the [[Segmented markets theory|segmented markets theory]], yields are not determined by liquidity premiums
and expected spot rates. Rather, the shape of the yield curve is determined by the
preferences of borrowers and lenders, which drives the balance between supply of and
demand for loans of different maturities. This is called the [[Segmented markets theory|segmented markets theory]]
because the theory suggests that the yield at each maturity is determined independently
of the yields at other maturities; we can think of each maturity to be essentially unrelated
to other maturities.
The [[Segmented markets theory|segmented markets theory]] supposes that various market participants only deal in
securities of a particular maturity because they are prevented from operating at different

maturities. For example, pension plans and insurance companies primarily purchase longmaturity bonds for asset-liability matching reasons and are unlikely to participate in the
market for short-term funds.

[[Preferred habitat theory|Preferred Habitat Theory]]
The [[Preferred habitat theory|preferred habitat theory]] also proposes that forward rates represent expected future
spot rates plus a premium, but it does not support the view that this premium is directly
related to maturity.
Instead, the [[Preferred habitat theory|preferred habitat theory]] suggests that the existence of an imbalance between
the supply and demand for funds in a given maturity range will induce lenders and
borrowers to shift from their preferred habitats (maturity range) to one that has the
opposite imbalance. However, to entice investors to do so, the investors must be offered an
incentive to compensate for the exposure to price and/or reinvestment rate risk in the lessthan-preferred habitat. Borrowers require cost savings (i.e., lower yields) and lenders
require a yield premium (i.e., higher yields) to move out of their preferred habitats.
Under this theory, premiums are related to supply and demand for funds at various
maturities. Unlike the liquidity preference theory, under the [[Preferred habitat theory|preferred habitat theory]] a 10year bond might have a higher or lower [[Risk premium|risk premium]] than the 25-year bond. It also means
that the preferred habitat theory can be used to explain almost any yield curve shape.

### Module Quiz 23.5

1. Which of the following statements regarding the traditional theories of the term structure of
interest rates is most accurate?
A. The segmented markets theory proposes that market participants have strong
preferences for specific maturities.
B. The liquidity preference theory hypothesizes that the yield curve must always be upward
sloping.
C. The preferred habitat theory states that yields at different maturities are determined
independently of each other.


## Module 23.6: Yield Curve Risks and Economic Factors


> **LOS 23.i:** Explain how a bond’s exposure to each of the factors driving the
yield curve can be measured and how these exposures can be used to
manage yield curve risks.

Managing Yield Curve Risks
Yield curve risk refers to risk to the value of a bond portfolio due to unexpected changes in
the yield curve.
To counter yield curve risk, we first identify our portfolio’s sensitivity to yield curve changes
using one or more measures. Yield curve sensitivity can be generally measured by effective

duration, or more precisely using [[CFA_Glossary/Key rate duration]], or a three-[[Factor Model]] that
decomposes changes in the yield curve into changes in level, [[Steepness|steepness]], and [[Curvature|curvature]].
[[Effective Duration|effective duration]]
[[Effective Duration|Effective duration]] measures price sensitivity to small parallel shifts in the yield curve. It is
important to note that [[CFA_Glossary/Effective duration]] is not an accurate measure of interest rate
sensitivity to non-parallel shifts in the yield curve like those described by [[Shaping risk|shaping risk]].
[[Shaping risk|Shaping risk]] refers to changes in portfolio value due to changes in the shape of the
benchmark yield curve. (Note, however, that parallel shifts explain more than 75% of the
variation in bond portfolio returns.)
[[Key Rate Duration|key rate duration]]
A more precise method used to quantify bond price sensitivity to interest rates is key rate
duration. Compared to [[Effective Duration|effective duration]], [[Key Rate Duration|key rate duration]] is superior for measuring the
impact of nonparallel yield curve shifts.
[[Key Rate Duration|Key rate duration]] is the sensitivity of the value of a security (or a bond portfolio) to changes
in a single par rate, holding all other par rates constant. In other words, [[Key Rate Duration|key rate duration]]
isolates price sensitivity to a change in the yield at a particular maturity only.
Numerically, [[Key Rate Duration|key rate duration]] is defined as the approximate percentage change in the
value of a bond portfolio in response to a 100 [[Basis point|basis point]] change in the corresponding key
par rate, holding all other par rates constant. Conceptually, we could determine the key
rate duration for the five-year segment of the yield curve by changing only the five-year par
rate and observing the change in value of the portfolio. Keep in mind that every security or
portfolio has a set of [[Key rate durations|key rate durations]]—one for each key rate.
For example, a bond portfolio has [[Interest rate risk|interest rate risk]]sk exposure|risk exposure]] to only three maturity points
on the par rate curve: the 1-year, 5-year, and 25-year maturities, with [[Key rate durations|key rate durations]]
represented by D1 = 0.7, D5 = 3.5, and D25 = 9.5, respectively. The sum total of these key
rate durations is the [[Effective Duration|effective duration]] of the portfolio.
The model for yield curve risk using these [[Key rate durations|key rate durations]] would be:

Sensitivity to Parallel, [[Steepness|Steepness]], and [[Curvature|Curvature]] Movements
An alternative to decomposing yield curve risk into sensitivity to changes at various
maturities (key rate duration) is to decompose the risk into sensitivity to the following
three categories of yield curve movements:
Level (ΔxL). A parallel increase or decrease of interest rates.
[[Steepness|Steepness]] (ΔxS). Long-term interest rates increase while short-term rates decrease.
[[Curvature|Curvature]] (ΔxC). Increasing [[Curvature|curvature]] means short- and long-term interest rates increase
while intermediate rates do not change.

It has been found that all yield curve movements can be described using a [[Combination|combination]] of
one or more of these movements.
We can then model the change in the value of our portfolio as follows:

where DL, DS, and DC are respectively the portfolio’s sensitivities to changes in the yield
curve’s level, [[Steepness|steepness]], and curvature.
For example, for a particular portfolio, yield curve risk can be described as:

If the following changes in the yield curve occurred: ΔxL = –0.004, ΔxS = 0.001, and ΔxC =
0.002, then the percentage change in portfolio value could be calculated as:

This predicts a +0.5% increase in the portfolio value resulting from the yield curve
movements.

> **LOS 23.j:** Explain the [[Maturity structure|maturity structure]] of yield volatilities and their effect
on price [[Volatility|volatility]].

[[Maturity structure|Maturity Structure]] of Yield Curve Volatilities
Interest rate volatility is a key concern for bond managers because interest rate volatility
drives price volatility in a fixed income portfolio. Interest rate volatility becomes
particularly important when securities have [[Embedded options|embedded options]], which are especially
sensitive to volatility.
The term structure of interest rate volatility is the graph of yield volatility versus maturity.

**Figure 23.4 shows a typical term structure of interest rate volatility. Note that, as shown**

here, short-term interest rates are generally more volatile than are long-term rates.

**Figure 23.4: Historical Volatility Term Structure: U.S. Treasuries, August 2005–December**

2007

Volatility at the long-maturity end is thought to be associated with uncertainty regarding
the real economy and [[Inflation|inflation]], while volatility at the short-maturity end reflects risks

regarding [[Monetary policy|monetary policy]].
Interest rate volatility at time t for a security with maturity of T is denoted as σ(t,T). This
variable measures the annualized [[Standard deviation|standard deviation]] of the change in bond yield.

> **LOS 23.k:** Explain how key economic factors are used to establish a view on
benchmark rates, spreads, and yield curve changes.
[[Macroeconomic factors|Macroeconomic factors]] that affect bond yields include [[Inflation|inflation]] forecasts, [[GDP]] growth, and
[[Monetary policy|monetary policy]]. Two-thirds of the variation in short- and intermediate-term yields is
explained by [[Monetary policy|monetary policy]], and the remaining is explained by the other factors. In
contrast, [[Inflation|inflation]] explains two-thirds of the variation in long-term yields, with the
remaining mostly explained by [[Monetary policy|monetary policy]].
Bond [[Risk premium|risk premium]] is the [[Excess return|excess return]] (over the one-year risk-free rate) earned by
investors for investing in long-term government bonds. Bond [[Risk premium|risk premium]] (also known as
the [[Term premium|term premium]] or duration premium) is a forward-looking expectation. For example,
suppose that the expected one-year holding period return on a 5-year government bond is
4%, while the one-year risk-free rate is 1%. The 5-year bond [[Risk premium|risk premium]] in this example
would be 4% – 1% = 3%.
Monetary policy influences the shape of the yield curve. During economic expansions, to
combat rising [[Inflation|inflation]], [[Central banks|central banks]] may raise short-term rates, leading to a bearish
flattening of the yield curve. During recessionary times, [[Central banks|central banks]] may reduce shortterm rates, leading to a bullish steepening. The U.S. Federal Reserve has dramatically
expanded its [[Balance sheet|balance sheet]] in recent years, purchasing U.S. Treasuries and mortgagebacked and municipal securities, reducing long-term bond yields.
Other factors affecting bond prices include the following:
[[Fiscal policy|Fiscal policy]]. [[Expansionary|Expansionary]] (restrictive) fiscal policies increase (decrease) yields.
[[Maturity structure|Maturity structure]]. The government’s choice of maturity when issuing new securities
affects the supply (and yield) of bonds in those maturity segments. An increase in
offerings in a specific segment of the market increases the supply and increases the yield
in that segment (the [[Market segmentation|market segmentation]]on|segmentation]] theory).
Investor demand. Domestic and foreign investor demand and preferences for specific
maturity segments affect the yield in that segment. For example, pension plans and
insurance companies may prefer longer maturity bonds, driving down longer-term
yields. During periods of market turmoil, a flight to safety may reduce long-term
government bond yields, resulting in a bullish flattening of the yield curve.


**Figure 23.5: Categories of Shifts in the Yield Curve**


Investor Actions
In expectation of a rise (fall) in rates, investors will lower (extend) the duration of their
bond portfolios. Expectations of a steepening of the yield curve may lead to investors going
long short-term bonds and short longer-term bonds. Trades may be designed to be
duration-neutral so that a change in the level of interest rates does not affect the value of
the portfolio. Investors with long-only mandates may rotate between a bullet portfolio (a
portfolio concentrated in a single maturity) and a barbell portfolio (a portfolio with short
and long maturities). An investor that expects a bullish flattening of the yield curve may
rotate out of a bullet portfolio and into a barbell portfolio.

### Module Quiz 23.6

1. The least appropriate measure to use to identify and manage “[[Shaping risk|shaping risk]]” is a portfolio’s:
A. [[Effective Duration|effective duration]].
B. [[Key rate durations|key rate durations]].
C. sensitivities to level, steepness, and curvature factors.
2. Regarding the volatility term structure, research indicates that volatility in short-term rates
is most strongly linked to uncertainty regarding:
A. the real economy.
B. monetary policy.
C. inflation.
3. Restrictive monetary policy is most likely to be associated with:
A. bearish flattening.
B. bullish steepening.
C. bullish flattening.


> [!abstract] Key Concepts
> LOS 23.a

The spot rate for a particular maturity is equal to a geometric average of the one-period
spot rate and a series of one-period forward rates.

When the spot curve is flat, forward rates will equal spot rates and yields. When the spot
curve is upward sloping (downward sloping), forward rate curves will be above (below) the
spot curve and the yield for a maturity of T will be less than (greater than) the spot rate ST.
The [[Forward pricing model|forward pricing model]] values forward contracts by using an arbitrage-free framework
that equates buying a zero-coupon bond to entering into a [[Forward contract|forward contract]] to buy a zerocoupon bond in the future that matures at the same time:
The forward rate model tells us that the investors will be indifferent between buying a
long-maturity zero-coupon bond versus buying a shorter-maturity zero-coupon bond and
reinvesting the [[Principal|principal]] at the locked in forward rate f(j,k).

LOS 23.b

By using a process called [[Bootstrapping|bootstrapping]], spot rates (i.e., zero-coupon rates) can be derived
from the par curve iteratively—one spot rate at a time.
LOS 23.c

If spot rates evolve as predicted by forward rates, bonds of all maturities will realize a oneperiod return equal to the one-period spot rate and the forward price will remain
unchanged.
Active bond portfolio management is built on the presumption that the current forward
curve may not accurately predict future spot rates. Managers attempt to outperform the
market by making predictions about how spot rates will change relative to the rates
suggested by forward rate curves.
If an investor believes that future spot rates will be lower than corresponding forward
rates, then the investor will purchase bonds (at a presumably attractive price) because the
market appears to be discounting future cash flows at “too high” of a [[Discount rate|discount rate]].
LOS 23.d

When the yield curve is upward sloping, bond managers may use the strategy of “rolling
down the yield curve” to chase above-market returns. By holding long-maturity rather than
short-maturity bonds, the manager earns an [[Excess return|excess return]] as the bond “rolls down the
yield curve” (i.e., approaches maturity and increases in price). As long as the yield curve
remains upward sloping and the spot rates continue to be lower than previously implied by
their corresponding forward rates, this strategy will add to the return of a bond portfolio.
LOS 23.e

The swap rate curve provides a benchmark measure of interest rates. It is similar to the
yield curve except that the rates used represent the interest rates of the fixed-rate leg in an
[[Interest rate swap|interest rate swap]].
Market participants prefer the swap rate curve as a benchmark interest rate curve rather
than a government bond yield curve for the following reasons:
1. Swap rates reflect the credit risk of commercial banks rather than that of governments.

2. The swap market is not regulated by any government.
3. The [[Swap curve|swap curve]] typically has yield quotes at many maturities.
LOS 23.f

We define swap spread as the additional interest rate paid by the fixed-rate payer of an
[[Interest rate swap|interest rate swap]] over the rate of the “[[On-the-run|on-the-run]]” government bond of the same
maturity.
swap spread = (swap rate) − (Treasury bond yield)
Investors use the swap spread to separate the [[Time value|time value]] portion of a bond’s yield from the
risk premiums for credit and liquidity risk. The higher the swap spread, the higher the
compensation for liquidity and credit risk.
For a default-free bond, the swap spread provides an indication of (1) the bond’s liquidity
and/or (2) possible [[Mispricing|mispricing]].
LOS 23.g

The Z-spread is the spread that when added to each spot rate on the yield curve makes the
present value of a bond’s cash flows equal to the bond’s market price. The Z refers to zero
volatility—a reference to the fact that the Z-spread assumes interest rate volatility is zero.
Z-spread is not appropriate to use to value bonds with [[Embedded options|embedded options]].
TED spreads
TED is an acronym that combines T-bill and ED (“ED” is the ticker symbol for the Eurodollar
[[Futures contract|futures contract]]).
TED spread = (MRR) − (T-bill rate)
The TED spread is used as an indication of the perceived credit and liquidity risk in the
economy. Because it captures the spread between rates paid by large banks and those paid
by the U.S. Treasury, the TED spread reflects the [[Default risk|default risk]] in the banking sector.
MRR-OIS spread
The MRR-OIS spread is the amount by which the MRR (which includes some credit risk)
exceeds the overnight indexed swap (OIS) rate (which includes only minimal credit risk).
LOS 23.h

There are several traditional theories that attempt to explain the term structure of interest
rates:
Unbiased expectations theory—Forward rates are an unbiased predictor of future spot
rates. Also known as the [[Pure expectations theory|pure expectations theory]].
Local expectations theory—Bond maturity does not influence returns for short holding
periods.
Liquidity preference theory—Investors demand a liquidity premium that is positively
related to a bond’s maturity.

Segmented markets theory—The shape of the yield curve is the result of the interactions
of supply and demand for funds in different market (i.e., maturity) segments.
Preferred habitat theory—Similar to the segmented markets theory, but recognizes that
market participants will deviate from their preferred maturity habitat if compensated
adequately.
LOS 23.i

We can measure a bond’s exposures to the factors driving the yield curve in a number of
ways:
1. Effective duration—Measures the sensitivity of a bond’s price to parallel shifts in the
benchmark yield curve.
2. Key rate duration—Measures bond price sensitivity to a change in a specific spot rate
keeping everything else constant.
3. Sensitivity to parallel, steepness, and curvature movements—Measures sensitivity to
three distinct categories of changes in the shape of the benchmark yield curve.
LOS 23.j

The [[Maturity structure|maturity structure]] of yield volatilities indicates the level of yield volatilities at different
maturities. This term structure thus provides an indication of yield curve risk. The volatility
term structure usually indicates that short-term rates (which are linked to uncertainty over
monetary policy) are more volatile than long-term rates (which are driven by uncertainty
related to the real economy and inflation). Fixed income instruments with embedded
options can be especially sensitive to interest rate volatility.
LOS 23.k

Inflation forecasts, GDP growth, and monetary policy affect bond yields. Bond risk premium
is the [[Excess return|excess return]] (over the one-year risk-free rate) from investing in longer-term
government bonds. Additionally, [[Fiscal policy|fiscal policy]], maturity structure, and investor demand all
affect yields.
In expectation of a rise (fall) in rates, investors will lower (extend) the duration of their
bond portfolios. An investor will rotate out of a bullet portfolio and into a barbell portfolio
in expectation of a bullish flattening of the yield curve.

### Answer Key For Module Quizzes

Module Quiz 23.1
1. B When the yield curve is upward sloping, the forward curves will lie above the spot
curve. The opposite is true when the yield curve is downward sloping. (LOS 23.a)
2. B The [[Forward pricing model|forward pricing model]] values forward contracts by using an arbitrage argument
that equates buying a zero-coupon bond to entering into a [[Forward contract|forward contract]] to buy a
zero-coupon bond that matures at the same time:

The forward rate model tells us that the forward rate f(j,k) should make investors
indifferent between buying a long-maturity zero-coupon bond versus buying a
shorter-maturity zero-coupon bond and reinvesting the [[Principal|principal]]. (LOS 23.a)
Module Quiz 23.2
1. B If an investor believes that future spot rates will be lower than the current forward
rates, then the investor will perceive an opportunity to purchase bonds at an
attractive price, as the market is discounting future cash flows at “too high” a
[[Discount rate|discount rate]]. The bonds are thus undervalued in the market. (LOS 23.c)
2. C Fixed income managers will earn an extra return through [[Rolling Down the Yield Curve|rolling down the yield curve]]
if the spot rate curve is upward sloping and remains unchanged over time. (LOS 23.d)
Module Quiz 23.3
1. C The swap market is not controlled by governments, which makes swap rates more
comparable across different countries. The swap rate is the interest rate for the fixedrate leg of an [[Interest rate swap|interest rate swap]]. Wholesale banks frequently use the swap curve to
value their assets and [[Liabilities|liabilities]], while retail banks with little exposure to the swap
market are more likely to use the government spot curve as their benchmark. (LOS
23.e)
Module Quiz 23.4
1. C The swap spread of a default free bond should provide an indication of the bond’s
illiquidity—or, alternatively, that the bond is mispriced. [[Time value|Time value]] is reflected in the
government bond yield curve; the swap spread is an additional amount of interest
above this benchmark. (LOS 23.f)
2. C The Z-spread is the constant spread that must be added to the default-free spot curve
to match the valuation of a risky bond to its market price. A higher Z-spread implies a
riskier bond. (LOS 23.g)
3. A The TED spread (from T-bill and Eurodollar) is computed as the difference between
the three-month MRR and the three-month T-bill rate. The MRR-OIS spread is the
difference between MRR and the overnight indexed swap rate (OIS) rates. (LOS 23.g)
Module Quiz 23.5
1. A The segmented markets theory (and the preferred habitat theory) propose that
borrowers and lenders have strong preferences for particular maturities. The liquidity
preference theory argues that there are liquidity premiums that increase with
maturity; however, the liquidity preference theory does not preclude the existence of
other factors that could lead to an overall downward-sloping yield curve. The
segmented markets theory—not the preferred habitat theory—proposes that yields
at different maturities are determined independently of each other. (LOS 23.h)

Module Quiz 23.6
1. A Effective duration is an inappropriate measure for identifying and managing shaping
risk. [[Shaping risk|Shaping risk]] refers to risk to portfolio value from changes in the shape of the
benchmark yield curve. Effective duration can be used to accurately measure the risk
associated with parallel yield curve changes but is not appropriate for measuring the
risk from other changes in the yield curve. (LOS 23.i)
2. B It is believed that short-term volatility reflects uncertainty regarding monetary policy
while long-term volatility is most closely associated with uncertainty regarding the
real economy and inflation. Short-term rates in the volatility term structure tend to
be more volatile than long-term rates. (LOS 23.j)
3. A During economic expansions, restrictive monetary policy to control inflation leads to
an increase in short-term rates and a bearish flattening of the yield curve. (LOS 23.k)


---

# Reading 24 — The Arbitrage-Free Valuation Framework


> [!tip] Exam Focus
> This topic review discusses valuation of fixed-income securities using spot rates as well as
> using the [[Backward Induction]] methodology in a [[Binomial Interest Rate Tree|binomial interest rate tree]] framework.
> Understand how embedded options impact the suitability of the [[Binomial model]] or the
> [[Monte Carlo simulation]] method.


## Module 24.1: Binomial Trees, Part 1


> **LOS 24.a:** Explain what is meant by [[Arbitrage-free valuation|arbitrage-free valuation]] of a fixedincome instrument.


The [[Arbitrage-free valuation]] framework is used extensively in the pricing of
securities. The basic principle of the “[[Law of one price|law of one price]]” in freely functioning markets drives
this analytical framework.
Arbitrage-free valuation methods value securities such that no market participant can earn
an arbitrage profit in a trade involving that security. An arbitrage transaction involves no
initial cash outlay but a positive riskless profit (cash flow) at some point in the future.
There are two types of arbitrage opportunities: [[Value additivity|value additivity]] (when the value of whole
differs from the sum of the values of parts) and [[Dominance|dominance]] (when one asset trades at a
lower price than another asset with identical characteristics).
If the principle of [[Value additivity|value additivity]] does not hold, arbitrage profits can be earned by
[[Stripping|stripping]] or [[Reconstitution|reconstitution]]. A five-year, 5% Treasury bond should be worth the same as a
portfolio of its coupon and [[Principal|principal]] strips. If the portfolio of strips is trading for less than
an intact bond, one can purchase the strips, combine them (reconstituting), and sell them
as a bond. Similarly, if the bond is worth less than its component parts, one could purchase
the bond, break it into a portfolio of strips ([[Stripping|stripping]]), and sell those components.

### Example: Arbitrage opportunities


The following information has been collected:

Securities A and B are identical in every respect other than as noted. Similarly, securities
C and D are identical in every other respect.
Demonstrate the exploitation of any arbitrage opportunities.
Answer:
1. Arbitrage due to violation of the [[Value additivity|value additivity]] principle:

2. Arbitrage due to the occurrence of [[Dominance|dominance]]:


> **LOS 24.b:** Calculate the arbitrage-free value of an option-free, fixed-rate
coupon bond.
Arbitrage-free valuation of a fixed-rate, option-free bond entails discounting each of the
bond’s future cash flows (i.e., each coupon payment and the [[Par value|par value]] at maturity) using
the corresponding spot rate.

### Example: Arbitrage-free valuation


Sam Givens, a fixed income analyst at GBO Bank, has been asked to value a three-year,
3% annual pay, €100 par bond with the same liquidity and risk as the benchmark. What
is the value of the bond using the spot rates provided in the following?
€ Benchmark Spot Rate Curve:

Answer:

While we can value option-free bonds with a simple spot rate curve, for bonds with
embedded options, changes in future rates will affect the [[Probability|probability]] of the option being
exercised and the [[Underlying|underlying]] future cash flows. Thus, a model that allows both rates and
the underlying cash flows to vary should be used to value bonds with embedded options.
One such model, the [[Binomial Interest Rate Tree|binomial interest rate tree]] framework, is discussed next.

> **LOS 24.c:** Describe a [[Binomial Interest Rate Tree|binomial interest rate tree]] framework.
The [[Binomial Interest Rate Tree|binomial interest rate tree]] framework assumes that interest rates have an equal
[[Probability|probability]] of taking one of two possible values in the next period (hence the term
binomial).
Over multiple periods, the set of possible interest rate paths that are used to value bonds
with a [[Binomial model|binomial model]] is called a binomial interest rate tree. The diagram in Figure 24.1
depicts a binomial interest rate tree.


**Figure 24.1: Binomial Interest Rate Tree**


The starting point i0 in this tree is the current 1-period spot rate and is called the root of
the tree. The future nodes are indicated with the bold dots (♦). A node is a point in time
when interest rates can take one of two possible paths, an upper path, U, or a lower path,
L. Now, consider the node on the right side of the diagram where the interest rate i2,LU
appears. This is the rate that will occur if the initial rate, i0, follows the lower path from
node 0 to node 1 to become i1,L, then follows the upper of the two possible paths to node
2, where it takes on the value i2,LU. At the risk of stating the obvious, the upper path from a
given node leads to a higher rate than the lower path. In fact,

Note that an upward move followed by a downward move, or a down-then-up move,
produces the same result: i2,LU = i2,UL (the math term for this is lattice).
The interest rates at each node in this interest rate tree are one-period forward rates
corresponding to the nodal period. Each forward rate is related to (i.e., is a multiple of) the
other forward rates in the same nodal period. Adjacent forward rates (at the same period)
are two standard deviations apart. For the first period, there are two forward rates and
hence:


> [!pnote] Professor's Note
> ***[[Consistent|Consistent]] with the curriculum, I use the term “forward rates” to denote the***
> ***“future one-period expected spot rates,” even though they are not the same.***
> ***Beyond the first nodal period, non-adjacent forward rates are a multiple of the two***
> ***standard deviations (depending on how separated the forward rates are).***
> ***For example,***
> ***The relationship among the set of rates associated with each individual nodal period is a***
> ***function of the interest rate volatility assumed to generate the tree. Volatility estimates can***
> ***be based on historical data or can be [[Implied volatility|implied volatility]] derived from interest rate***
> ***[[Derivatives|derivatives]].***
>
> ***The binomial interest rate tree framework is a lognormal [[Random walk]] model with two***
> ***properties: (1) higher volatility at higher rates and (2) non-negative interest rates.***
>
> ***> **LOS 24.e:** Describe the [[Backward Induction|backward induction]] valuation methodology and***
> ***calculate the value of a fixed-income instrument given its cash flow at each***
> ***node.***
>
> ***Valuing an Option-Free Bond with the [[Binomial model|Binomial Model]]***
> ***[[Backward Induction|Backward induction]] refers to the process of valuing a bond using a binomial interest rate***
> ***tree. The term “backward” is used because in order to determine the value of a bond today***
> ***at Node 0, you need to know the values that the bond can take at the Year 1 node. But to***
> ***determine the values of the bond at the Year 1 nodes, you need to know the possible***
> ***values of the bond at the Year 2 nodes. Thus, for a bond that has N [[Compounding|compounding]] periods,***
> ***the current value of the bond is determined by computing the bond’s possible values at***
> ***Period N and working backwards to Node 0.***
> ***Because the probabilities of an up move and a down move are both 50%, the value of a***
> ***bond at a given node in a [[Binomial tree]] is the average of the present values of the two***
> ***possible values from the next period. The appropriate [[Discount rate|discount rate]] is the forward rate***
> ***associated with the node.***
> ***The following example should make this all clear.***

### Example: Valuing an option-free bond with the binomial model


A 7% annual coupon bond has two years to maturity. The interest rate tree is shown in
the following figure. Fill in the tree and calculate the value of the bond today.
Valuing a 2-Year, 7.0% Coupon, Option-Free Bond

Answer:
Consider the value of the bond at the upper node for Period 1 (V1,U ):

Similarly, the value of the bond at the lower node for Period 1 (V1,L ) is:

Now calculate V0, the current value of the bond at Node 0.

The completed [[Binomial tree|binomial tree]] is shown as follows:
Valuing a 2-Year, 7.0% Coupon, Option-Free Bond


### Module Quiz 24.1

Use the following information to answer Questions 1 through 5.
Dan Green, CFA, is currently working for FIData, a company specializing in the provision of price
data for fixed-income instruments.
Green heads a team that inputs raw data into an instructional area on FIData’s website. FIData
uses these pages to provide hypothetical bond information along with a description of how to
read and interpret the information.
One of FIData’s customers has questioned whether some of the data used to demonstrate
pricing concepts is correct. The customer’s email stated, “The prices of the three bonds used are
not [[Consistent|consistent]] with each other and hence may not be accurate. If they were, I would be able to
make a significant arbitrage profit (i.e., I could secure the current risk-free rate of return with
zero net investment).” Green thinks the customer is misinformed regarding arbitrage gains, but

wants to check the data anyway.
The relevant data for three hypothetical risk-free bonds is shown in Figure 1 given that the
benchmark yield curve is flat at 1.50%. (FFPQ is an annual-pay bond.)

**Figure 1: Bond Pricing Data**


In another area of the company’s instructional website, FIData has an explanation of the
binomial interest rate tree framework that its analysts use in their valuation process. All of
FIData’s models populate a binomial interest rate tree assuming interest rates follow a
lognormal [[Random walk|random walk]].
The web page makes two statements regarding the assumptions that underpin the construction
and [[Population|population]] of such trees:
Assumption 1: The lognormal model ensures that interest rates are non-negative.
Assumption 2: The lognormal model ensures a constant volatility of interest rates at all levels of
interest rates.
An example of a standard tree used by FIData is given in Figure 2.

**Figure 2: Binomial Interest Rate Tree**


FIData’s website uses rates in Figure 2 to value a two-year, 5% annual-pay coupon bond with a
[[Par value|par value]] of $1,000 using the [[Backward Induction|backward induction]] method.
1. Green is correct in stating that the customer who sent the email regarding arbitrage gains is
misinformed because:
A. an arbitrage gain always requires a net investment, although this may be small compared
to the potential gains.
B. an arbitrage gain is not constrained by the risk-free rate.
C. arbitrage gains require a net investment in proportion to returns.
2. Given the three bonds in Figure 1, it is possible to make an arbitrage gain by:
A. selling 1 FFPQ bond and simultaneously purchasing 10 DALO and 10 NKDS bonds.
B. selling 10 FFPQ bonds and simultaneously purchasing 1 DALO and 1 NKDS bond.
C. selling 1 DALO bond and 1 NKDS bond and simultaneously purchasing 10 FFPQ bonds.
3. Which of the following statements regarding the FFPQ bond in Figure 1 is most likely?
A. It is priced above its no arbitrage price.
B. It is priced at its no arbitrage price.
C. It is priced below its no arbitrage price.
4. Which of the assumptions regarding the construction of FIData’s binomial interest rate trees
is most accurate?
A. Assumption 1 only.
B. Assumption 2 only.
C. Neither assumption is correct.
5. Using the [[Backward Induction|backward induction]] method, the value of the 5% annual-pay bond using the
interest rate tree given in Figure 2 is closest to:


### A. $900.


### B. $945.


### C. $993.


## Module 24.2: Binomial Trees, Part 2


> **LOS 24.d:** Describe the process of calibrating a binomial interest rate tree to
match a specific term structure.
The construction of a binomial interest rate tree is a tedious process. In practice, the
interest rate tree is usually generated using specialized computer software. The underlying
process conforms to three rules:
1. The interest rate tree should generate arbitrage-free values for the benchmark security.
This means that the value of bonds produced by the interest rate tree must be equal to
their market price, which excludes arbitrage opportunities. This requirement is very
important because without it, the model will not properly price more complex callable
and putable securities, which is the intended purpose of the model.
2. As stated earlier, adjacent forward rates (for the same period) are two standard
deviations apart (calculated as e2σ). Hence, knowing one of the forward rates (out of
many) for a particular nodal period allows us to compute the other forward rates for
that period in the tree.
3. The middle forward rate (or mid-point in case of even number of rates) in a period is
approximately equal to the implied (from the benchmark spot rate curve) one-period
forward rate for that period.

### Example: Binomial interest rate tree


Xi Nguyen, CFA, has collected the following information on the par rate curve, spot rates,
and forward rates. Nguyen had asked a colleague, Alok Nath, to generate a binomial
interest rate tree [[Consistent|consistent]] with this data and an assumed volatility of 20%. Nath
completed a partial interest rate tree shown as follows:

[[Binomial tree|Binomial Tree]] With σ = 20% (One-Year Forward Rates)

1. Calculate the forward rate indicated by A.
2. Estimate the forward rate indicated by C.
3. Estimate forward rates B and D.
Answer:
1. Forward rate i1,L is indicated by A and is related to forward rate i1,U given as 5.7883%.

i1,L = i1,U e–2σ = (0.057883)e–(2 × 0.20) = 0.0388 or 3.88%
2. Forward rate C is the middle rate for Period 3 and hence the best estimate for that
rate is the one-year forward rate in two years f(2,1).
Using the spot rates, we can bootstrap the forward rate:
(1 + S3)3 = (1 + S2)2(1 + f(2,1)) → (1.05069)3 = (1.0402)2(1 + f(2,1)) → f(2,1) = 7.199%
1. The forward rates B and D are related to C as follows (note that C = i2,LU):

$$
D = i2,LL = i2,LUe–2\sigma = (0.07199) e–0.40 = 0.0483 or 4.83%
$$


$$
B = i2,UU = i2,LUe+2\sigma = (0.07199) e+0.40 = 0.1074 or 10.74%
$$


> [!pnote] Professor's Note
> ***To calculate the value of e–0.40 on your TI BA II PLUS calculator, use the following***
> ***keystrokes: 0.4 [+|–] [2ND] [LN]***
>
> ***> **LOS 24.f:** Compare pricing using the zero-coupon yield curve with pricing***
> ***using an arbitrage-free binomial lattice.***
> ***We have already discussed arbitrage-free valuation of benchmark option-free bonds using***
> ***the zero-coupon yield curve (also known as the spot rate curve). Each known future cash***
> ***flow is discounted at the underlying spot rate (also known as the zero-coupon yield).***

### Example: Valuation of option-free bond


Samuel Favre is interested in valuing a three-year, 3% annual-pay Treasury bond. He has
compiled the following information on Treasury spot rates:
Treasury Spot Rate Curve

Compute the value of the $100 [[Face value|face value]] option-free bond.
Answer:

For bonds with embedded options, the future cash flows are uncertain as they depend on
whether the [[Embedded option|embedded option]] will be [[In the money|in the money]] (and hence exercised). Because the
value of the option depends on uncertain future interest rates, the underlying cash flows
are also [[Dependent|dependent]] on the same future interest rates. Hence, to value bonds with
embedded options, we have to allow for rates to fluctuate. One way to accomplish this is to
use the binomial interest rate tree.


> [!pnote] Professor's Note
> ***The [[Binomial tree|binomial tree]] approach can value either option-free bonds or bonds with***
> ***embedded options. Valuation of bonds with embedded options is covered in***
> ***the next topic review.***

### Example: Valuation of an option-free bond using binomial tree


Samuel Favre is interested in valuing the same three-year, 3% annual-pay Treasury bond.
The spot rate curve is as before, but this time Favre wants to use a binomial interest rate
tree with the following rates:
One-Period Forward Rate in Year

Compute the value of the $100 par option-free bond.
Answer:

Note that the underlying interest rate tree in this example was calibrated to generate
arbitrage-free values consistent with the benchmark spot rate curve and hence
produced the same value for the option-free bond as in the earlier example.


> **LOS 24.g:** Describe pathwise valuation in a binomial interest rate framework
and calculate the value of a fixed-income instrument given its cash flows
along each path.
Another mathematically identical approach to valuation using the backward induction
method in a [[Binomial tree|binomial tree]] is the pathwise valuation approach. For a binomial interest rate
tree with n periods, there will be 2(n–1) unique paths. For example, for a three-period tree,
there will be 22 or four paths comprising one known spot rate and varying combinations of
two unknown forward rates. If we use the label of S for the one-period spot rate and U and
L for upper and lower outcomes, respectively, for forward rates in our binomial framework,
the four paths would be SUU, SUL, SLU, and SLL.

### Example: Valuation of option-free bond using pathwise valuation


Samuel Favre wants to value the same three-year, 3% annual-pay Treasury bond. The
interest rate tree (shown next) is the same as before but this time, Favre wants to use a
pathwise valuation approach.
One-Period Forward Rate in Year

Compute the value of the $100 par option-free bond.
Answer:
For a three-year bond, there are four potential interest rate paths. The value of the bond
for each path is computed as the sum of the present values of each cash flow discounted
at its respective path-specified rate. Pathwise valuation discounts cash flows one year at
a time using one-year forward rates (similar to backward induction) rather than spot
rates.

For example, the value of the bond in Path 1 is computed as:


> **LOS 24.h:** Describe a Monte Carlo forward-rate [[Simulation|simulation]] and its
application.

Path Dependency
Prepayments on underlying residential [[Mortgages|mortgages]] affect the cash flows of a mortgagebacked security. [[Prepayment risk|Prepayment risk]] is similar to call risk in a [[Callable bond]]. However, unlike
call risk, [[Prepayment risk|prepayment risk]] is affected not only by the level of interest rate at a particular
point in time, but also by the path rates took to get there.
Consider a mortgage pool that was formed when rates were 6%, then interest rates
dropped to 4%, rose to 6%, and then dropped again to 4%. Many homeowners will have
refinanced when interest rates dipped the first time. On the second occurrence of 4%
interest rates, most homeowners in the pool who were able to refinance would have
already taken advantage of the opportunity, leading to lower prepayments than would be
observed had 4% interest rates not occurred previously.
An important assumption of the binomial valuation process is that the value of the cash
flows at a given point in time is [[Independent|independent]] of the path that interest rates followed up to
that point. In other words, cash flows are not path [[Dependent|dependent]]; cash flows at any node do
not depend on the path rates took to get to that node. Because of path dependency of
cash flows of [[Mortgage-backed securities|mortgage-backed securities]], the binomial tree backward induction process
cannot be used to value such securities. We instead use the [[Monte Carlo simulation|Monte Carlo simulation]]
method to value [[Mortgage-backed securities|mortgage-backed securities]].
A Monte Carlo forward-rate [[Simulation|simulation]] involves randomly generating a large number of
interest rate paths, using a model that incorporates a volatility assumption and an assumed
[[Probability distribution|probability distribution]]. A key feature of the Monte Carlo method is that the underlying
cash flows can be path [[Dependent|dependent]].
As with pathwise valuation discussed earlier, the value of the bond is the average of values
from the various paths. The simulated paths should be calibrated so benchmark interest
rate paths value benchmark securities at their market price (i.e., arbitrage-free valuation).
The calibration process entails adding (subtracting) a constant to all rates when the value
obtained from the simulated paths is too high (too low) relative to market prices. This
calibration process results in a drift adjusted model.
A [[Monte Carlo simulation|Monte Carlo simulation]] may impose upper and lower bounds on interest rates as part of
the model generating the simulated paths. These bounds are based on the notion of mean
reversion; rates tend to rise when they are too low and fall when they are too high.

### Example: Valuation of option-free bond using Monte Carlo simulation


Samuel Favre is interested in valuing the same three-year, 3% annual-pay Treasury bond
as discussed before. Favre wants to use [[Monte Carlo simulation|Monte Carlo simulation]]on|simulation]] and has generated the

following rate paths:
[[Monte Carlo simulation|Monte Carlo Simulation]]on|Simulation]] (Drift-Adjusted)

Answer:
Valuation using the simulated interest rate paths is shown as follows:

Where, for example:

Note that the interest rates in the example were calibrated to ensure that the valuation
obtained was consistent with market prices (i.e., arbitrage-free) and hence the value
obtained is the same as before.


## Module 24.3: Interest Rate Models


> **LOS 24.i:** Describe [[Term Structure Models|term structure models]] and how they are used.


[[Term Structure Models|Term structure models]] attempt to capture the statistical properties of interest rate
movements and provide us with quantitatively precise descriptions of how interest rates
will change.

[[Equilibrium|Equilibrium]] [[Term Structure Models|Term Structure Models]]
[[Equilibrium|Equilibrium]] [[Term Structure Models|term structure models]] attempt to describe changes in the term structure
through the use of fundamental economic variables that drive interest rates. While
[[Equilibrium|equilibrium]] term structure models can rely on multiple factors, the two famous models
discussed in the curriculum, the Cox-Ingersoll-Ross (CIR) model and the [[Vasicek model|Vasicek model]], are
both single-factor models. The single factor in the CIR and Vasicek models is the short-term
interest rate.
The Cox-Ingersoll-Ross Model
The Cox-Ingersoll-Ross (CIR) model is based on the idea that interest rate movements are
driven by individuals choosing between consumption today versus investing and
consuming at a later time.
Mathematically, the CIR model consists of two components: the first part of this expression
is a drift term, while the second part is the random component:

The a(b – r)dt term forces the interest rate to mean-revert toward its long-run value (b) at a
speed determined by the [[Mean reversion|mean reversion]] [[Parameter|parameter]] (a).
Under the CIR model, volatility increases with the interest rate, as can be seen in the
term. In other words, at high interest rates the amount of period-over-period fluctuation in
rates is also high.
The [[Vasicek model|Vasicek Model]]
Like the CIR model, the [[Vasicek model|Vasicek model]] suggests that interest rates are mean reverting to
some long-run value.
The [[Vasicek model|Vasicek model]] is expressed as:
The difference from the CIR model that you will notice is that no interest rate (r) term
appears in the second term σdz, meaning that volatility in this model does not increase as
the level of interest rates increases (i.e., volatility is constant).
The main disadvantage of the Vasicek model is that the model does not force interest rates
to be nonnegative.

[[Arbitrage-free models|Arbitrage-Free Models]]
[[Arbitrage-free models|Arbitrage-free models]] of the term structure of interest rates begin with the assumption
that bonds trading in the market are correctly priced, and the model is calibrated to value
such bonds consistent with their market price (hence the “arbitrage-free” label). These
models do not try to justify the [[Current yield|current yield]] curve; rather, they take this curve as given.
The ability to calibrate [[Arbitrage-free models|arbitrage-free models]] to match current market prices is one
advantage of [[Arbitrage-free models|arbitrage-free models]] over the [[Equilibrium|equilibrium]] models.
The Ho-Lee Model
The Ho-Lee model takes the following form:

Derived using the relative pricing concepts of the Black-Scholes model, this model assumes
that changes in the yield curve are consistent with a [[No-arbitrage pricing|no-arbitrage]] condition.
The Ho-Lee model is calibrated by using market prices to find the time-[[Dependent|dependent]] drift
term θt that generates the current term structure. The Ho-Lee model can then be used to
price [[Zero-coupon bonds|zero-coupon bonds]] and to determine the spot curve. The model assumes constant
volatility and produces a symmetrical (normal) distribution of future rates.
The Kalotay-Williams-Fabozzi (KWF) Model
The Kalotay-Williams-Fabozzi (KWF) model does not assume [[Mean reversion|mean reversion]] and, like the
Ho-Lee model, assumes a constant volatility. However, the KWF model assumes that the
short-term rate is lognormally distributed. The model takes the following form:
Note that the right-hand side of the equation is the same as that of the Ho-Lee model. The
only difference is that the KWF model assumes lognormal distribution of rates while the
Ho-Lee model assumed [[Normal distribution|normal distribution]].

Other Models
Gauss+ is a [[Multifactor model]] that incorporates short-, medium-, and long-term rates,
where the long-term rate is designed to be mean reverting and depends on
macroeconomic variables. Medium-term rates revert to the long-term rate, while the
short-term rate is devoid of a random component—consistent with the role of the central
bank controlling the short-term rate. This results in a hump-shaped volatility curve across
tenors, with the volatility of the medium term rates being the highest.

### Module Quiz 24.2, 24.3

Use the following information to answer Questions 1 through 6.
Farah Dane, CFA, works for Geodesic Investing, a small [[Hedge Fund]] that offers investment
services for a handful of clients known personally by the owner, Mike DeGrekker. The fund
makes few trades, preferring to wait for what it perceives to be arbitrage opportunities before
investing. Last year, the fund managed a return of more than 45%, thanks largely to a single

transaction on which the company made a profit of $9.4 million.
The transaction, which DeGrekker described as a “valuation farming exercise” involved
simultaneously purchasing a government Treasury and selling the corresponding strips for a
higher price than the cost of the Treasury.
Dane is currently using a binomial lattice and a pathwise method to value fixed-income bonds in
order to identify potential trading opportunities. She has used the binomial lattice shown in

**Figure 1 to value a three-year, annual pay, 4% coupon risk-free government bond with a par**

value of $1,000. Her pathwise valuation is also shown.

**Figure 1: Binomial Lattice**


Dane is not satisfied with this method of valuation and has put together a report for DeGrekker
on the use of the Monte Carlo method, which she feels will lead to more accurate valuations. She
quotes the following advantages of using Monte Carlo method:
Advantage 1: The Monte Carlo method will estimate the value of the bond using multiple
interest rate paths and hence there is no need to make an assumption about
volatility of rates.
Advantage 2:The method could be applied to get more accurate valuations for securities that are
interest rate path dependent.
DeGrekker is resistant to the idea as he is concerned about the amount of computing time the
model may require. He accepts, however, that the idea of using many paths is attractive. He
concedes that, “increasing the number of paths used in the model increases the statistical
accuracy of the estimated value and produces a value closer to the true [[Fundamental value|fundamental value]] of the
security.”
1. Which of the following statements regarding the valuation of an option-free bond using an
arbitrage-free binomial lattice is most accurate?
A. If the binomial lattice is correctly calibrated, it should give the same value for an optionfree bond as using the par curve used to calibrate the tree.
B. The binomial lattice will only produce the same value for an option-free bond as the par
curve that was used to calibrate it if the bond is priced at par.
C. The binomial lattice will only produce the same value for an option-free bond as the par
curve that was used to calibrate it if the yield curve is flat.
2. Which of the following statements most accurately describes the “valuation farming exercise”
undertaken by DeGrekker?
A. DeGrekker used the process of [[Stripping|stripping]] and the [[Law of one price|law of one price]] to make an arbitrage
gain.
B. DeGrekker used the process of [[Reconstitution|reconstitution]] and the [[Principle of no arbitrage|principle of no arbitrage]] to make a
risk-free gain.
C. DeGrekker’s profit is not an arbitrage profit as the securities involved are risk free.
3. Which of the following is most accurate regarding the value Dane would obtain using the
backward induction method as opposed to the pathwise valuation method for the bond in

**Figure 1?**


A. Both methods would produce the same value.
B. The pathwise valuation method will give lower values when interest rates are rising
because the backward induction method places a higher weighting on earlier cash flows.
C. The backward induction method will give a different value compared to the pathwise
method when the volatility of interest rates is high as the pathwise method uses equal
weights.
4. Dane’s pathwise valuation is:
A. correct.
B. incorrect, as the correct value is lower than $975.17.
C. incorrect, as the correct value is higher than $975.17.
5. Which of the advantages of the Monte Carlo method stated by Dane is most accurate?
A. Advantage 1 only.
B. Advantage 2 only.
C. Neither advantage is correct.
6. DeGrekker’s comment on increasing the number of paths is most likely:
A. correct.
B. incorrect in asserting that a larger number of paths will produce an estimate that is
statistically more accurate.
C. incorrect in asserting that a larger number of paths will produce a value closer to the
true [[Fundamental value|fundamental value]].
7. When calibrating a binomial interest rate tree to match a specific term structure, which of
the following statements is least accurate?
A. Interest rates in the tree should produce an arbitrage-free valuation for benchmark
securities.
B. Adjacent spot rates at each node of the tree are related by the multiplier e2σ.
C. The middle forward rate in a period is approximately equal to the implied (from the
benchmark spot rate curve) one-period forward rate for that period.
8. The modern term structure model that is most likely to precisely generate the current term
structure is the:
A. Cox-Ingersoll-Ross model.
B. Vasicek model.
C. Ho-Lee model.


> [!abstract] Key Concepts
> LOS 24.a

Arbitrage-free valuation leads to a security value such that no market participant can earn
an arbitrage profit in a trade involving that security. In other words, the valuation is
consistent with the [[Value additivity|value additivity]] principle and without [[Dominance|dominance]] of any security
relative to others in the market.
LOS 24.b

Arbitrage-free valuation of fixed-rate, option-free bonds entails discounting each of the
bond’s future cash flows at its corresponding spot rate.

LOS 24.c

The binomial interest rate tree framework is a lognormal model with two equally likely
outcomes for one-period forward rates at each node. A volatility assumption drives the
spread of the nodes in the tree.
LOS 24.d

A binomial interest rate tree is calibrated such that (1) the values of benchmark bonds
using the tree are equal to the bonds’ market prices, (2) adjacent forward rates at any
nodal period are two standard deviations apart and (3) the midpoint for each nodal period
is approximately equal to the implied one-period forward rate for that period.
LOS 24.e

Backward induction is the process of valuing a bond using a binomial interest rate tree. The
term backward is used because in order to determine the value of a bond at Node 0, we
need to know the values that the bond can take on at nodal period 1, and so on.
LOS 24.f

Valuation of bonds using a zero-coupon yield curve (also known as the spot rate curve) is
suitable for option-free bonds. However, for bonds with embedded options where the
value of the option varies with outcome of unknown forward rates, a model that allows for
variability of forward rates is necessary. One such model is the binomial interest rate tree
framework.
LOS 24.g

In the pathwise valuation approach, the value of the bond is simply the average of the
values of the bond at each path. For a n-period binomial tree, there are 2(n-1) possible
paths.
LOS 24.h

The Monte Carlo simulation method uses pathwise valuation and a large number of
randomly generated simulated paths. [[Mortgage-backed securities|Mortgage-backed securities]] have path-dependent
cash flows on account of the embedded [[Prepayment option|prepayment option]]. The Monte Carlo simulation
method should be used for valuing MBS as the binomial tree backward induction process is
inappropriate for securities with path-dependent cash flows.
LOS 24.i

Two major classes of term structure models are as follows:
1. Equilibrium term structure models—Attempt to model the term structure using
fundamental economic variables that are thought to determine interest rates.
a. Cox-Ingersoll-Ross model:
Assumes the economy has a natural long-run interest rate (b) that the short-term rate
(r) converges to at a speed of (a). Interest rate volatility varies with r and is not
constant. Produces non negative rates only.
b. Vasicek model:drt = a(b - r)dt + σdz

Similar to the CIR model, but assumes that the interest rate volatility level is constant
and [[Independent|independent]] of the level of short-term interest rates. Can produce negative rates.
2. Arbitrage-free models—Begin with observed market prices and the assumption that
securities are correctly priced.
a. Ho-Lee model:drt = θtdt + σdzt
Calibrated by using market prices to find the time-dependent drift term θt that
generates the current term structure. Assumes that short-term rates are normally
distributed with a constant volatility. Produces a [[Normal distribution|normal distribution]] of rates and rates
can be negative.
b. Kalotay-Williams-Fabozzi (KWF) model:dln(rt)= θtdt + σdzt
Similar to the Ho-Lee model, but assumes that short rate has a lognormal distribution.

### Answer Key For Module Quizzes

Module Quiz 24.1
1. B An arbitrage gain is a risk-free profit and hence requires no net investment. The
returns therefore are not simply the risk-free rate. As there is no initial investment,
the gains cannot be measures as percentage of initial cost. (LOS 24.a)
2. B An up-front arbitrage profit of $38.70 can be earned by selling 10 FFPQ bonds short
and purchasing 1 DALO and 1 NKDS bonds as shown here.

(LOS 24.a)
3. A FFPQ is overpriced. Based on the 1.5% benchmark yield, the other two bonds are
correctly priced.
Arbitrage-free price = (PV Year 1 Cash Flow) + (PV Year 2 Cash Flow)

(LOS 24.a)
4. A A lognormal [[Random walk|random walk]] will ensure non-negativity but will lead to higher volatility
at higher interest rates. (LOS 24.c)
5. C The value of the 5%, two-year annual pay $1000 par bond is $992.88.

(LOS 24.e)
Module Quiz 24.2, 24.3
1. A A correctly calibrated tree will value the bond at the same price as the par and spot
curves used to derive it. (Module 24.2, LOS 24.d)
2. A DeGrekker purchased the bonds and stripped them into constituent parts before
selling them. The strategy involved no initial net investment and yet results in an
arbitrage profit. (Module 24.1, LOS 24.a)
3. A The two methods are identical and will always give the same result. (Module 24.2,
LOS 24.g)
4. B This is a tricky question. There are only four possible paths that Dane should have
used. The possible paths are UU (Path 1), UD (Path 2), DU (Path 4), and DD (Path 5).
Path 3 isn’t a valid path.

So the value should be the average of the values for Paths 1, 2, 4, and 5. The correct
average value is $972.45. (Module 24.2, LOS 24.g)
5. B Monte Carlo simulation also requires an assumed level of volatility as an input.
(Module 24.2, LOS 24.h)
6. C The larger the number of paths, the more accurate the value in a statistical sense.
However, whether the value is closer to the true [[Fundamental value|fundamental value]] depends on the
accuracy of the model inputs. (Module 24.2, LOS 24.h)
7. B The stated multiplier is correct but it is important to note that the rates given at each
node of the tree are forward rates not spot rates. (Module 24.2, LOS 24.d)
8. C The Ho-Lee model is calibrated by using market prices to find the time-dependent
drift term, θt that generates the current term structure. (One of the drawbacks of the
Vasicek and Cox-Ingersoll-Ross models is that the model prices generated by these

models generally do not coincide with observed market prices.) (Module 24.3, LOS
24.i)


---

# Reading 25 — Valuation and Analysis of Bonds with Embedded Options


> [!tip] Exam Focus
> This topic review extends the [[Arbitrage-Free Valuation Framework|arbitrage-free valuation framework]] to valuation of bonds
> with embedded options. Understand the risk/return dynamics of embedded options,
> including their impact on a bond’s duration and [[Convexity]]. You should also know the
> adjustment required for the valuation of credit-risky bonds, including the process to
> estimate an [[OAS]]. Finally, understand the terminology and risk/return characteristics of
> convertibles.


## Module 25.1: Types of Embedded Options


> **LOS 25.a:** Describe fixed-income securities with embedded options.


Embedded options in a bond allow an issuer to (1) manage [[Interest rate risk|interest rate risk]] and/or (2)
issue the bonds at an attractive [[Coupon rate|coupon rate]]. The embedded options can be a simple call or
[[Put option]], or more complex options such as provisions for a sinking fund or an estate put.

Simple Options
Callable bonds give the issuer the option to call back the bond; the investor is short the call
option. Most callable bonds have a [[Call protection|call protection]] period during which the bond cannot be
called. The [[Call option]] can be a [[European-style|European-style]] option (whereby the option can only be
exercised on a single day immediately after the protection period), an [[American-style|American-style]]
option (whereby the option can be exercised at any time after the protection period), or
even a Bermudan-style option (whereby the option can be exercised at fixed dates after
the protection period).
[[Putable bonds|Putable bonds]] allow the investor to put (sell) the bond back to the issuer prior to maturity.
The investor is long the underlying [[Put option|put option]]. A related bond is an [[Extendible bond|extendible bond]], which
allows the investor to extend the maturity of the bond. An [[Extendible bond|extendible bond]] can be
evaluated as a [[Putable bond]] with longer maturity (i.e., the maturity if the bond is
extended). A two-year, 3% bond extendible for an additional year at the same [[Coupon rate|coupon rate]]
would be valued the same as an otherwise identical three-year putable (European style)
bond with a protection period of two years.

Complex Options
More complex options include:
An estate put which includes a provision that allows the heirs of an investor to put the
bond back to the issuer upon the death of the investor. The value of this contingent put
option is inversely related to the investor’s life expectancy; the shorter the life
expectancy, the higher the value.
Sinking fund bonds (sinkers) which require the issuer to set aside funds periodically to
retire the bond (a sinking fund). This provision reduces the credit risk of the bond.
Sinkers typically have several related issuer options (e.g., call provisions, acceleration
provisions, and delivery options).

> **LOS 25.b:** Explain the relationships between the values of a callable or [[Putable bond|putable bond]], the
underlying option-free (straight) bond, and the [[Embedded option|embedded option]].
In essence, the holder of a [[Callable bond|callable bond]] owns an option-free (straight) bond and is also
short a [[Call option|call option]] written on the bond. The value of the embedded [[Call option|call option]] (Vcall) is,
therefore, simply the difference between the value of a straight (Vstraight) bond and the
value of the comparable [[Callable bond|callable bond]] (Vcallable):

$$
Vcall = Vstraight − Vcallable
$$

Conversely, investors are willing to pay a premium for a [[Putable bond|putable bond]] since its holder
effectively owns an option-free bond plus a [[Put option|put option]]. The value of a [[Putable bond|putable bond]] can be
expressed as:

$$
Vputable = Vstraight + Vput
$$

Rearranging, the value of the embedded [[Put option|put option]] can be stated as:

$$
Vput = Vputable − Vstraight
$$


## Module 25.2: Valuing Bonds with Embedded Options, Part 1


> **LOS 25.c:** Describe how the arbitrage-free framework can be used to value a bond with
embedded options.

> **LOS 25.f:** Calculate the value of a callable or [[Putable bond|putable bond]] from an interest rate tree.

The basic process for valuing a callable (or putable) bond is similar to the process for
valuing a [[Straight bond|straight bond]]. However, instead of using spot rates, one-period forward rates are
used in a binomial tree framework. This change in methodology computes the value of the
bond at different points in time; these checks are necessary to determine whether the
[[Embedded option|embedded option]] is in-the-money (and exercised).
When valuing a [[Callable bond|callable bond]], the value at any node where the bond is callable must be
either the price at which the issuer will call the bond (i.e., the call price) or the computed
value if the bond is not called, whichever is lower. This is known as the call rule. Similarly,
for a [[Putable bond|putable bond]], the value used at any node corresponding to a put date must be either
the price at which the investor will put the bond (i.e., the put price) or the computed value
if the bond is not put, whichever is higher. This is known as the put rule.

> [!pnote] Professor's Note
> ***Call date and put date in this context vary depending on whether the option is***
> ***European-, American-, or Bermudan-style.***

### Example: Valuation of call and put options


Consider a two-year, 7% annual-pay, $100 par bond callable in one year at $100. Also
consider a two-year, 7% annual-pay, $100 par bond putable in one year at $100.
The interest rate tree at 15% assumed volatility is as follows:

Value the embedded call and put options.

Answer:
Value of the straight (option-free) bond:
Consider the value of the bond at the upper node for Period 1, V1,U:

Similarly, the value of the bond at the lower node for Period 1, V1,L, is:

Now calculate V0, the current value of the bond at Node 0.

The completed binomial tree is shown as follows:
Valuing a Two-Year, 7.0% Coupon, Option-Free Bond

Value of the [[Callable bond|callable bond]]:
The call rule (call the bond if the price exceeds $100) is reflected in the boxes in the
completed binomial tree, where the second line of the boxes at the one-year node is the
lower of the call price or the computed value. For example, the value of the bond in one
year at the lower node is $101.594. However, in this case, the bond will be called, and
the investor will only receive $100. Therefore, for valuation purposes, the value of the
bond in one year at this node is $100.
V1,L = $100
V1,U = (107 / 1.071826) = $99.830
The calculation for the current value of the bond at Node 0 (today), assuming the
simplified call rules of this example, is:

The completed binomial tree is shown as follows:
Valuing a Two-Year, 7.0% Coupon, [[Callable bond|Callable Bond]], Callable in One Year at 100

Value of the putable bond:
Similarly, for a putable bond, the put rule is to put the bond if the value falls below $100.
The [[Put option|put option]] would therefore be exercised at the upper-node in Year 1 and hence the
$99.830 computed value is replaced by the [[Exercise price]] of $100.

Value of the embedded options:

$$
Vcall = Vstraight − Vcallable = $102.999 − $102.238 = $0.76
$$


$$
Vput = Vputable − Vstraight = $103.081 − $102.999 = 0.082
$$


### Module Quiz 25.1, 25.2

1. Which of the following statements concerning the calculation of value at a node in a binomial
interest rate tree is most accurate? The value at each node is the:
A. present value of the two possible values from the next period.
B. average of the present values of the two possible values from the next period.

C. sum of the present values of the two possible values from the next period.
Use the following binomial interest rate tree to answer Questions 2 through 4.

2. The value today of an option-free, 12% annual coupon bond with two years remaining until
maturity is closest to:

### A. 110.525.


### B. 111.485.


### C. 112.282.

3. The value of the bond and the value of the embedded [[Call option|call option]], assuming the bond in
Question 2 is callable at $105 at the end of Year 1, are closest to:

4. The value of the bond and the value of the embedded put option, assuming the bond in
Question 2 is putable at $105 at the end of Year 1, are closest to:


## Module 25.3: Valuing Bonds with Embedded Options, Part 2


> **LOS 25.d:** Explain how interest rate volatility affects the value of a callable
or putable bond.
Option values are positively related to the volatility of their underlying. Accordingly, when
interest rate volatility increases, the values of both call and put options increase. The value
of a [[Straight bond|straight bond]] is affected by changes in the level of interest rates but is unaffected by
changes in the volatility of interest rates.
When interest rate volatility increases, the value of a callable bond (where the investor is
short the [[Call option|call option]]) decreases and the value of a putable bond (where the investor is long
the put option) increases.

> **LOS 25.e:** Explain how changes in the level and shape of the yield curve affect the value
of a callable or putable bond.

Level of Interest Rates
As interest rates decline, the short call in a callable bond limits the bond’s upside, so the
value of a callable bond rises less rapidly than the value of an otherwise-equivalent straight
bond.
As interest rates increase, the long put in a putable bond hedges against the loss in value;
the value of a putable bond falls less rapidly than the value of an otherwise-equivalent
[[Straight bond|straight bond]].
Call option value is inversely related to the level of interest rates, while put option value
varies directly with the level of interest rates.

Shape of the Yield Curve
The value of an embedded call option increases as interest rates decline. When the yield
curve is upward sloping (i.e., normal), the more distant one-period forward rates are higher
than the one-period forward rates in the near future. Because a higher interest rate
scenario limits the [[Probability|probability]] of the call option being [[In the money|in the money]], the value of a call
option will be lower for an upward sloping yield curve. As an upward-sloping yield curve
becomes flatter, the call option value increases.
The value of a put option increases with interest rates. When the yield curve is upward
sloping, the [[Probability|probability]] of the put option going [[In the money|in the money]] is higher. Put option value
therefore declines as an upward-sloping yield curve flattens.


## Module 25.4: Option-Adjusted Spread


> **LOS 25.g:** Explain the calculation and use of option-adjusted spreads.
So far our backward induction process has relied on the risk-free binomial interest rate
tree; our valuation assumed that the underlying bond was risk-free. If risk-free rates are
used to discount cash flows of a credit risky corporate bond, the calculated value will be
too high. To correct for this, a constant spread must be added to all one-period rates in the
tree such that the calculated value equals the market price of the risky bond. This constant
spread is called the option adjusted spread (OAS).

> [!pnote] Professor's Note
> ***The OAS is added to the tree after the adjustment for the [[Embedded option|embedded option]]***
> ***(i.e., the node values are adjusted according to the call/put rule). Hence the***
> ***OAS is calculated after the option risk has been removed.***

### Example: Computation of OAS


A $100-par, three-year, 6% annual-pay ABC, Inc., callable bond trades at $99.95. The
underlying call option is a Bermudan-style option that can be exercised in one or two
years at par.
The benchmark interest rate tree assuming volatility of 20% is provided here:

Compute the OAS on the bond.
Answer:
The value of the bond using the benchmark interest rate tree is $101.77, as shown here:

To force the computed value to be equal to the current market price of $99.95, a
constant spread (OAS) of 100 bps is added to each interest rate in the tree, as shown
here:


> [!pnote] Professor's Note
> ***The OAS computed using the methodology just listed is the spread implied by***
> ***the current market price and hence assumes that the bond is priced correctly.***
> ***Note that the actual [[Estimation|estimation]] of OAS is largely an iterative process and is***
> ***beyond the scope of the exam.***
> ***OAS is used by analysts in relative valuation; bonds with similar credit risk should have the***
> ***same OAS. If the OAS for a bond is higher than the OAS of its peers, it is considered to be***
> ***undervalued and hence an attractive investment (i.e., it offers a higher compensation for a***
> ***given level of risk). Conversely, bonds with low OAS (relative to peers) are considered to be***
> ***overvalued.***
>
> ***> **LOS 25.h:** Explain how interest rate volatility affects option-adjusted spreads.***
> ***Consider for a moment the difference between the calculated value of a bond that we***
> ***obtain from a tree and the bond’s actual market price. The greater this difference is, the***
> ***greater the OAS we would need to add to the rates in the tree to force the calculated bond***
> ***value down to the market price.***
> ***Suppose that a 7%, 10-year callable bond of XYZ Corp. is trading for $958.***
> ***Analyst A assumes a 15% value for future volatility in generating her benchmark interest***
> ***rate tree and calculates the value of the bond as $1,050. She then computes the OAS (the***
> ***increase in [[Discount rate|discount rate]] required to lower the calculated bond value to the market price of***
> ***$958) for this bond to be 80 bps.***
> ***Analyst B assumes a 20% value for future volatility, and because of higher assumed***
> ***volatility, the computed value of the bond turns out to be $992. (Note that this is lower***
> ***than the $1,050 calculated by A—the higher the volatility, the lower a callable bond’s***
> ***value.) The OAS calculated by B is accordingly lower at 54 bps.***
>
> ***Observe that for the same bond, the OAS calculated varied depending on the volatility***
> ***assumption used.***
> ***When we use a higher estimate of volatility to value a callable bond, the calculated value of***
> ***the call option increases, the calculated value of the [[Straight bond|straight bond]] is unaffected, and the***
> ***computed value (not the market price) of the callable bond decreases (since the***
> ***bondholder is short the option). Hence when the estimated (or assumed) volatility (of***
> ***benchmark rates) used in a binomial tree is higher, the computed value of a callable bond***
> ***will be lower—and therefore closer to its true market price. The constant spread that***
> ***needs to be added to the benchmark rates to correctly price the bond (the OAS) is***
> ***therefore lower.***
>
> *****Figure 25.1: Relationship Between Volatility and OAS*****
>
>
> ***To summarize, as the assumed level of volatility used in an interest rate tree increases, the***
> ***computed OAS (for a given market price) for a callable bond decreases. Similarly, the***
> ***computed OAS of a putable bond increases as the assumed level of volatility in the***
> ***binomial tree increases.***

> [!pnote] Professor's Note
> ***Notice that the columns for the value of callable and [[Putable bonds|putable bonds]] in the***
> ***preceding figure match the corresponding OAS columns.***

### Module Quiz 25.3, 25.4

1. The option adjusted spread (OAS) on a callable corporate bond is 73 basis points using onthe-run Treasuries as the benchmark rates in the construction of the binomial tree. The best
interpretation of this OAS is the:
A. cost of the embedded option is 73 basis points.
B. cost of the option is 73 basis points over Treasury.
C. spread that reflects the credit risk is 73 basis points over Treasury.
2. An increase in interest rate volatility increases the value of:
A. bonds with embedded call options.
B. bonds with embedded put options.
C. low-coupon bonds with embedded options, but decreases the value of high-coupon
bonds with embedded options.


## Module 25.5: Duration


> **LOS 25.i:** Calculate and interpret effective duration of a callable or
putable bond.
Recall from Level I that:


[[Modified duration|Modified duration]] measures a bond’s price sensitivity to interest rate changes, assuming
that the bond’s cash flows do not change as interest rates change.
The standard measure of [[Convexity|convexity]] can be used to improve price changes estimated
from [[Modified duration]].
[[Modified duration|Modified duration]] and [[Convexity|convexity]] are not useful for bonds with embedded options,
however, because the cash flows from these bonds will change if the option is exercised. To
overcome this problem, effective duration and [[CFA_Glossary/Effective convexity]] should be used, because
these measures take into account how changes in interest rates may alter cash flows.
The following expressions can be used to compute effective duration and effective
[[Convexity|convexity]] for any bond:

Calculating effective duration and [[Effective Convexity|effective convexity]] for bonds with embedded options is a
complicated undertaking because we must calculate values of BV+Δy and BV–Δy. Here’s how
it is done:
Step 1: Given assumptions about benchmark interest rates, interest rate volatility, and any
calls and/or puts, calculate the OAS for the issue using the current market price and
the [[Binomial model|binomial model]].
Step 2: Impose a small [[Parallel shift|parallel shift]] in the benchmark yield curve by an amount equal to
+Δy.
Step 3: Build a new binomial interest rate tree using the new yield curve.
Step 4: Add the OAS from step 1 to each of the one-year rates in the interest rate tree to
get a “modified” tree.
Step 5: Compute BV+Δy using this modified interest rate tree.
Step 6: Repeat steps 2 through 5 using a parallel rate shift of –Δy to obtain a value of BV–Δy.

> **LOS 25.j:** Compare effective durations of callable, putable, and straight bonds.
Both call and put options have the potential to reduce the life of a bond, so the duration of
callable and [[Putable bonds|putable bonds]] will be less than or equal to the duration of their straight
counterparts.
Effective duration (callable) ≤ effective duration (straight).
Effective duration (putable) ≤ effective duration (straight).

Effective duration (zero-coupon) ≈ maturity of the bond.
Effective duration of fixed-rate coupon bond < maturity of the bond.
Effective duration of floater ≈ time (in years) to next reset.
While effective duration of straight bonds is relatively unaffected by changes in interest
rates, an increase in rates would increase the effective duration of a callable bond, and
decrease the effective duration of a putable bond.

### Module Quiz 25.5

1. Ron Hyatt has been asked to do a presentation on how effective duration (ED) and effective
convexity (EC) are calculated with a binomial model. His presentation includes the following
formulas:

Are Hyatt’s formulas for effective duration and effective convexity correctly presented?
A. The formulas are both correct.
B. One formula is correct, the other incorrect.
C. Both formulas are incorrect.


## Module 25.6: Key Rate Duration


> **LOS 25.k:** Describe the use of [[One-Sided Durations|one-sided durations]] and key rate durations
to evaluate the interest rate sensitivity of bonds with embedded options.


[[One-Sided Durations|One-Sided Durations]]
The computation of effective duration discussed earlier relied on computing the value of
the bond for equal parallel shifts of the yield curve up and down (by the same amount).
This metric captures [[Interest rate risk|interest rate risk]] reasonably well for small changes in the yield curve
and for option-free bonds.
For a callable bond, when the call option is at or near the money, the change in price for a
decrease in yield will be less than the change in price for an equal amount of increase in
yield. The value of a callable bond is capped by its call price: the bond’s value will not
increase beyond the call price regardless of how low interest rates fall. Similarly, the value
of a putable bond is more sensitive to downward movements in yield curve versus upward
movements.

For bonds with embedded options, [[One-Sided Durations|one-sided durations]]—durations that apply only when
interest rates rise (or, alternatively, only when rates fall)—are better at capturing interest
rate sensitivity than simple effective duration. When the underlying option is [[At-the-money|at-the-money]]
(or near-the-money), callable bonds will have lower one-sided down-duration than onesided up-duration: the price change of a callable when rates fall is smaller than the price
change for an equal increase in rates. Conversely, a near-the-money putable bond will have
larger one-sided down-duration than one-sided up-duration.

Key Rate Duration
Key rate durations or partial durations capture the interest rate sensitivity of a bond to
changes in yields (par rates) of specific benchmark maturities. Key rate duration is used to
identify the [[Interest rate risk|interest rate risk]] from changes in the shape of the yield curve (shaping risk).
The process of computing key rate duration is similar to the process of computing effective
duration described earlier, except that instead of shifting the entire benchmark yield curve,
only one specific par rate (key rate) is shifted before the price impact is measured.

**Figure 25.2 shows the key rate durations for several 15-year option-free bonds, each with a**

different [[Coupon rate|coupon rate]] and YTM = 3%.

**Figure 25.2: Key Rate Durations of Various 15-Year Option-Free Bonds With Different**

Coupon Rates


> [!pnote] Professor's Note
> ***In these figures, the market interest rate is not changing; rather we are***
> ***considering a number of different bonds that have different coupons.***
>
> *****Figure 25.3 shows the key rate durations for several 15-year [[European-style|European-style]] callable bonds,*****
>
> ***each with a different coupon rate (callable in 10 years at par).***
>
> *****Figure 25.3: Key Rate Durations of Various 15-Year Callable Bonds With Different Coupon*****
>
> ***Rates***
>
>
> *****Figure 25.4 shows the key rate durations for several 15-year [[European-style|European-style]] [[Putable bonds|putable bonds]],*****
>
> ***each with a different coupon rate (putable in 10 years at par).***
>
> *****Figure 25.4: Key Rate Durations of Various 15-Year Putable Bonds With Different Coupon*****
>
> ***Rates***
>
> ***The following generalizations can be made about key rates:***
> ***1. If an option-free bond is trading at par, the bond’s maturity-matched rate is the only rate***
> ***that affects the bond’s value. Its maturity key rate duration is the same as its effective***
> ***duration, and all other rate durations are zero. In Figure 25.2, the 3% bond’s (i.e., the par***
> ***bond) 15-year key rate duration is same as the bond’s effective duration, and all other***
> ***rate durations are zero.***
> ***2. For an option-free bond not trading at par, the maturity-matched rate is still the most***
> ***important rate. In Figure 25.2, the 15-year key rate duration is highest.***
> ***3. A bond with a low (or zero) coupon rate may have negative key rate durations for***
> ***horizons other than the bond’s maturity. This is evidenced by some negative key rate***
> ***durations for 1% and 2% coupon bonds in all three figures.***
> ***4. A callable bond with a low coupon rate is unlikely to be called; hence, the bond’s***
> ***maturity-matched rate is the most critical rate (i.e., the highest key rate duration***
> ***corresponds to the bond’s maturity). For the 1% bond in Figure 25.3, the 15-year key***
> ***rate duration exceeds all other key rate durations.***
> ***5. All else equal, higher coupon bonds are more likely to be called, and therefore the timeto-exercise rate will tend to dominate the time-to-maturity rate. For the 8% coupon***
> ***bond in Figure 25.3, the 10-year key rate duration is highest.***
> ***6. Putable bonds with high coupon rates are unlikely to be put, and thus are most sensitive***
> ***to their maturity-matched rates. For the 8% bond in Figure 25.4, the 15-year key rate***
> ***duration is the highest.***
> ***7. All else equal, lower coupon bonds are more likely to be put, and therefore the time-toexercise rate will tend to dominate the time-to-maturity rate. For the 1% coupon bond***
> ***in Figure 25.4, the 10-year key rate duration is highest.***
>
> ***> **LOS 25.l:** Compare effective convexities of callable, putable, and straight bonds.***
> ***Straight bonds have positive [[Effective Convexity|effective convexity]]: the increase in the value of an option-free***
> ***bond is higher when rates fall than the decrease in value when rates increase by an equal***
> ***amount. When rates are high, callable bonds are unlikely to be called and will exhibit***
> ***positive [[Convexity|convexity]]. When the underlying call option is near the money, its effective***
> ***convexity turns negative; the upside potential of the bond’s price is limited due to the call***
>
> ***(while the downside is not protected). Putable bonds exhibit positive convexity***
> ***throughout.***

## Module 25.7: Capped and Floored Floaters


> **LOS 25.m:** Calculate the value of a capped or floored floating-rate bond.


A floating-rate bond (“floater”) pays a coupon that adjusts every period based on an
underlying reference rate. The coupon is typically paid in arrears, meaning the coupon rate
is determined at the beginning of a period but is paid at the end of that period.
A [[Capped floater|capped floater]] effectively contains an issuer option that prevents the coupon rate from
rising above a specified maximum rate known as the cap.

A related floating rate bond is the [[Floored floater|floored floater]], which has a coupon rate that will not fall
below a specified minimum rate known as the floor. In this instance, the embedded option
belongs to the investor and offers protection from falling interest rates.

We can use the standard backward induction methodology in a binomial interest rate tree
to value a capped or [[Floored floater|floored floater]]. As with the valuation of a bond with embedded
options, we must adjust the value of the floater at each node to reflect the exercise of an
in-the-money option (in this case, a cap or a floor).

### Example: Value of a capped and floored floating-rate bond


Susane Albright works as a fixed income analyst with Zedone Banks, NA. She has been
asked to value a $100 par, two-year, floating-rate note that pays MRR (set in arrears).
The underlying bond has the same credit quality as reflected in the swap curve. Albright
has constructed the following two-year binomial MRR tree:

How would we compute the following?
1. The value of the floater, assuming that it is an option-free bond.
2. The value of the floater, assuming that it is capped at a rate of 6%. Also compute the
value of the embedded cap.
3. The value of the floater, assuming that it is floored at a rate of 5%. Also compute the
value of the embedded floor.

Answer:
1. An option-free bond with a coupon rate equal to the [[Required rate of return]] will be
worth par value. Hence, the straight value of the floater is $100.
2. The value of the [[Capped floater|capped floater]] is $99.47, as shown here:

The upper node in Year 2 shows the exercise of the cap (the coupon is capped at $6.00
instead of rising to $7.18).
Note that when the option is not [[In the money|in the money]], the floater is valued at par.
V1,U = ($100 + $6) / (1 + 0.071826) = $98.90
V1,L = (100 + 5.3210) / (1 + 0.05321) = $100
The Year 0 value is the average of the Year 1 values (including their adjusted coupons)
discounted for one period. In this case, the Year 1 coupons require no adjustment, as
the coupon rate is below the [[Capitalization rate|cap rate]].

Thus the value of the embedded cap = $100 – $99.47 = 0.53.
3. The value of the [[Floored floater|floored floater]] is $100.41, as shown here:

The nodes for Year 2 show the coupons for that period (none of the rates are below
the floor, and hence the floor is not exercised). Strikethroughs for both nodes in Year 1
indicate that the floor was in the money; we replace the MRR = market reference rate.
Having another rate after it is redundant coupon with a coupon based on the floor
strike rate of 5%.
The Year 0 value is the average of the Year 1 values (including their adjusted coupons)
discounted for one period:

Thus the value of the embedded floor = $100.41 – $100 = $0.41.


### Module Quiz 25.6, 25.7

Use the following information to answer Questions 1 through 8.
Vincent Osagae, CFA, is the fixed income portfolio manager for Alpha Specialists, an institutional
money manager. Vanessa Alwan, an intern, has suggested a list of bonds for Osagae’s
consideration as shown in Figure 1. The benchmark yield curve is currently upward sloping.

**Figure 1: Selected Bonds for Consideration**


Bond X, a 3%, 15-year option-free bond.
Bond Y, a 3%, 15-year callable bond.
Bond Z, a 3%, 15-year putable bond.
Osagae then turns his attention to a newly issued 4%, 15-year bond issued by Suni Corp. The
bond has a Bermudan-style call option exercisable annually at any time after Year 4. Osagae
computes an OAS of 145 bps for this bond using a binomial interest rate tree. The tree was
generated with U.S. Treasury rates and an assumed volatility of 15%, which was consistent with
historical data. Option markets are currently pricing interest rate options at an [[Implied volatility|implied volatility]]
of 19%.
Every week, Alwan meets with Osagae to discuss what she had learned over the week. At one of
their weekly meetings, Alwan makes the following statements about key rate duration:
Statement 1: The highest key rate duration of a low-coupon callable bond corresponds to the
bond’s time-to-exercise.
Statement 2: The highest key rate duration of a high-coupon putable bond corresponds to the
bond’s time-to-maturity.
Beth Grange, a senior analyst reporting to Osagae has generated the following two-year MRR
tree using a 15% volatility assumption:

**Figure 2: MRR Tree**


Grange has also compiled OAS for two very similar callable corporate bonds as shown in Figure
3.

**Figure 3: OAS at 10% Volatility**

1. In Figure 1, which bond’s embedded option is most likely to increase in value if the yield
curve flattens?
A. Bond Y.
B. Bond Z.
C. Neither Bond Y nor Bond Z.
2. If Osagae had used [[Implied volatility|implied volatility]] from interest rate options to compute the OAS for Suni
Corp bond, the estimated OAS would most likely have been:
A. lower than 145 bps.
B. higher than 145 bps.
C. equal to 145 bps.
3. Which bond in Figure 1 is most likely to have the highest effective duration?
A. Bond X.
B. Bond Y.
C. Bond Z.
4. Regarding Alwan’s statements about key rate durations:
A. only one statement is correct.

B. both statements are correct.
C. neither statement is correct.
5. Which bond in Figure 1 is least likely to experience the highest increase in value, given a
parallel downward shift of 150 bps in the yield curve?
A. Bond X.
B. Bond Y.
C. Bond Z.
6. Which bond in Figure 1 is most likely to experience an increase in effective duration due to an
increase in interest rates?
A. Bond X.
B. Bond Y.
C. Bond Z.
7. In Figure 3, relative to Bond A, Bond B is most likely:
A. overpriced.
B. underpriced.
C. fairly priced.
8. Using the data in Figure 2, the value of a $100 par, two-year, 3% [[Capped floater|capped floater]] is closest to:

### A. $0.31.


### B. $98.67.


### C. $99.78.


## Module 25.8: Convertible Bonds


> **LOS 25.n:** Describe defining features of a [[Convertible bond|convertible bond]].


The owner of a [[Convertible bond]] has the right to convert the bond into a fixed number of
[[Common shares|common shares]] of the issuer during a specified timeframe ([[Conversion period|conversion period]]) and at a
fixed amount of money ([[Conversion price|conversion price]]). Convertibles allow investors to enjoy the upside
on the issuer’s stock, although this comes at a cost of lower yield. The issuer of a
[[Convertible bond|convertible bond]] benefits from a lower borrowing cost, but existing shareholders may face
dilution if the conversion option is exercised.
The [[Conversion ratio|conversion ratio]] is the number of [[Common shares|common shares]] for which a [[Convertible bond|convertible bond]] can be
exchanged. For example, a [[Convertible bond|convertible bond]] issued at par with an initial [[Conversion ratio|conversion ratio]] of
10 allows its holder to convert one $1,000 par bond into 10 shares of [[Common stock|common stock]].
Equivalently, the [[Conversion price|conversion price]] of the bond is $1,000 / 10 shares = $100. For bonds not
issued at par, the [[Conversion price|conversion price]] is the issue price divided by the [[Conversion ratio|conversion ratio]]. Offer
documents will indicate how the initial [[Conversion ratio|conversion ratio]] would be modified to account for
corporate actions such as stock splits or stock dividends.
Offer documents may also provide a contingent put option in the event of any change-ofcontrol events such as mergers. Such a contingent put option can be exercised for a specific
period of time after the change of control. Alternatively, a lower [[Conversion price|conversion price]] may be
specified in the event of a change of control. The conversion ratio may also be adjusted
upward if the company pays a dividend in excess of a specified threshold dividend. This
adjustment protects the convertible bondholders in the event that the company pays out
an unusually large dividend (which will cause the [[Ex-dividend|ex-dividend]] price of the stock to decline).
Other put options exercisable during specific periods may also be embedded with a

convertible. These put options can be hard puts (i.e., redeemable for cash) or soft puts (i.e.,
the issuer decides whether to redeem the bond for cash, stock, subordinated [[Debentures|debentures]],
or a [[Combination|combination]] of the three).

> **LOS 25.o:** Calculate and interpret the components of a [[Convertible bond|convertible bond]]’s value.
The [[Conversion value|conversion value]] of a convertible bond is the value of the [[Common stock|common stock]] into which
the bond can be converted. The conversion ratio is the number of shares the holder
receives from conversion for each bond. [[Conversion value|Conversion value]] is calculated as:
[[Conversion value|conversion value]] = market price of stock × conversion ratio
The straight value, or [[Investment value|investment value]], of a convertible bond is the value of the bond if it
were not convertible—the present value of the bond’s cash flows discounted at the return
required on a comparable option-free issue.
The minimum value of a convertible bond is the greater of its [[Conversion value|conversion value]] or its
straight value. This must be the case, or arbitrage opportunities would be possible. For

### Example: , if a convertible bond were to sell for less than its conversion value, it could be

purchased, immediately converted into [[Common stock|common stock]], and the stock could be sold for
more than the cost of the bond.
minimum value of a convertible bond = max (straight value, conversion value)

### Example: Calculating the minimum value of a convertible bond


Business Supply Company, Inc. operates retail office equipment stores in the United
States and Canada. Consider a BSC convertible bond with a 7% coupon that is currently
selling at $985 with a conversion ratio of 25 and a straight value of $950. Suppose that
the value of BSC’s [[Common stock|common stock]] is currently $35 per share, and that it pays $1 per share
in dividends annually. What is this bond’s minimum value?
Answer:
The conversion value of this bond is 25 × $35 = $875. Since the straight value of $950 is
greater than the conversion value of $875, the bond is worth at least $950.
The market conversion price, or conversion parity price, is the price that the convertible
bondholder would effectively pay for the stock if she bought the bond and immediately
converted it. The market conversion price is given as:


### Example: Calculating market conversion price


Compute and interpret the market conversion price of the BSC bond.

Answer:
The market conversion price is: $985 / 25 = $39.40. This can be viewed as the stock price
at which an investor is indifferent between selling the bond and converting it.
The [[Market conversion premium per share|market conversion premium per share]] is the difference between the market
conversion price and the stock’s current market price:


### Example: Calculating market conversion premium per share


Compute and interpret the [[Market conversion premium per share|market conversion premium per share]] of the BSC bond.
Answer:
Since BSC is selling for $35 per share, the [[Market conversion premium per share|market conversion premium per share]] for the
BSC bond is: $39.40 − $35 = $4.40. This can be interpreted as the premium that investors
are willing to pay for the opportunity to profit should the market price of the stock rise
above the market conversion price. This is done with the assurance that even if the stock
price declines, the value of the convertible bond will not fall below its straight value.
[[Market conversion premium per share|Market conversion premium per share]] is usually expressed as a ratio, appropriately called
the [[Market conversion premium ratio|market conversion premium ratio]]. Its formula is:


### Example: Calculating market conversion premium ratio


Compute the [[Market conversion premium ratio|market conversion premium ratio]] of the BSC bond.
Answer:
The BSC bond [[Market conversion premium ratio|market conversion premium ratio]] is:

The convertible bond investor’s downside risk is limited by the bond’s underlying straight
value because the price of a convertible bond will not fall below this value regardless of
what happens to the price of the issuer’s common stock.
This downside risk is measured by the premium over straight value, which is calculated as:


### Example: Calculating premium over straight value


Compute and interpret the BSC bond’s premium over straight value.

Answer:
The premium over straight value for the BSC bond is:

All else equal, the greater the premium over straight value, the less attractive the
convertible bond.
We need to recognize an obvious flaw with the premium over straight value metric—the
straight value is not constant. It varies with changes in interest rate and with the credit
spread of the bond.

> **LOS 25.p:** Describe how a convertible bond is valued in an arbitrage-free framework.
Investing in a noncallable/nonputable convertible bond is equivalent to buying:
an option-free bond, and
a call option on an amount of the common stock equal to the conversion ratio.
The value of a noncallable/nonputable convertible bond can be expressed as:

Most [[Convertible Bonds|convertible bonds]] are callable, giving the issuer the right to call the issue prior to
maturity. Incorporating this feature into the valuation of a convertible bond results in the
following expression:

To further complicate the situation (just for fun), consider a convertible bond that is both
callable and putable. The expression for value then becomes:


> **LOS 25.q:** Compare the risk–return characteristics of a convertible bond with the risk–
return characteristics of a straight bond and of the underlying common stock.
Buying [[Convertible Bonds|convertible bonds]] instead of stocks limits downside risk; the price floor set by the
straight bond value provides this downside protection. The cost of the downside protection
is reduced upside potential due to the conversion premium. Keep in mind though, that just
like investing in nonconvertible bonds, convertible bond investors must be concerned with
credit risk, call risk, interest rate risk, and liquidity risk.
Consider the following two examples based on our previous BSC example.


### Example: Risk and return of a convertible bond, part 1


Calculate the return on the convertible bond and the common stock if the market price
of BSC common stock increases to $45 per share.
Answer:
The return from investing in the convertible bond is:

The return from investing directly in the stock is:

The lower return from the convertible bond investment is attributable to the fact that
the investor effectively bought the stock at the market conversion price of $39.40 per
share.

### Example: Risk and return of a convertible bond, part 2


Calculate the return on the convertible bond and on the common stock if the market
price of BSC common stock falls to $30 per share.
Answer:
Recall that the bond will trade at the greater of its straight value or its conversion value.
The conversion value in this scenario is 25 × $30 = $750. Assuming the straight value of
the bond does not change, the bond will trade at $950. So, the return from investing in
the convertible bond is:

The return from investing directly in the stock is:

The loss is less for the convertible bond investment because we assumed that the
straight value of the bond did not change. Even if it had changed, the loss would
probably still be less than the loss on the straight stock investment, thus emphasizing
how the straight value serves as a floor to cushion a decline, even if it is a moving floor.
The following comparisons can be made between ownership of the underlying stock and
the risk-return characteristics of the convertible bond:
When the stock’s price falls, the returns on [[Convertible Bonds|convertible bonds]] exceed those of the stock,
because the convertible bond’s price has a floor equal to its straight bond value. As the

stock’s price approaches zero, the convertible’s value will move toward the present value
of estimated recovery.
When the stock’s price rises, the bond will underperform because of the conversion
premium. This is the main drawback of investing in [[Convertible Bonds|convertible bonds]] versus investing
directly in the stock.
If the stock’s price remains stable, the return on a convertible bond may exceed the
stock return due to the coupon payments received from the bond, assuming no change
in interest rates or credit risk of the issuer.
Sometimes the price of the common stock associated with a convertible issue is so low that
it has little or no effect on the convertible’s market price, and the bond trades as though it
is a straight bond. When this happens, the convertible security is referred to as a fixedincome equivalent or a busted convertible.
Other times, the price of the stock may be high enough that the convertible behaves as
though it is an equity security. When this happens, the convertible issue is referred to as a
common stock equivalent. Most of the time, however, the convertible behaves as a hybrid
security with the characteristics of both equity and a fixed-income security.

### Module Quiz 25.8

1. An analyst has gathered the following information on a convertible bond and the common
equity of the issuer.
Market price of bond: $925.00
Annual coupon: 7.5%
Conversion ratio: 30
Market price of stock: $28.50
Annual [[Stock dividend|stock dividend]]: $2.15 per share
The [[Market conversion premium ratio|market conversion premium ratio]] for the convertible bond is closest to:

### A. 7.56%.


### B. 7.77%.


### C. 8.18%.

2. Which of the following statements concerning a comparison between the risk and return of
convertible bond investing versus common stock investing is least accurate, assuming
interest rates are stable?
A. When stock prices fall, the returns on convertible bonds are likely to exceed those of the
stock because the convertible bond’s price has a floor equal to the straight bond value.
B. The main drawback of investing in convertible bonds versus direct stock purchases is
that when stock prices rise, the convertible bond will likely underperform the stock due
to the conversion premium.
C. Buying convertible bonds instead of direct stock investing limits upside potential to that
of buying a straight bond, at the cost of increased downside risk due to the conversion
premium.
3. Data on two convertible bonds are shown in the following table.

Which factors are most likely to influence the market prices of ABC and XYZ: factors that
affect equity prices, or factors that affect option-free bond prices?
A. Both will be more affected by equity factors.
B. One will be more affected by equity factors, the other by bond factors.
C. Both will be more affected by bond factors.
4. The difference between the value of a callable convertible bond and the value of an otherwise
comparable option-free bond is closest to the value of the:
A. call option on the stock minus value of the call option on the bond.
B. put option on the stock plus value of the call option on the bond.
C. call option on the stock plus value of call option on the bond.
5. With respect to the value of a callable convertible bond, the most likely effects of a decrease
in interest rate volatility or a decrease in the underlying stock price volatility are:
A. both will result in an increase in value.
B. one will result in an increase in value, the other in a decrease.
C. both will result in a decrease in value.


> [!abstract] Key Concepts
> LOS 25.a

Bonds with embedded options allow issuers to manage their interest rate risk or issue
bonds at attractive coupon rates. The embedded options can be simple call or put options,
or more complex options such as provisions for sinking fund, estate puts, et cetera.
LOS 25.b

Value of option embedded in a callable or putable bond:

$$
Vcall = Vstraight − Vcallable
$$


$$
Vput = Vputable − Vstraight
$$

LOS 25.c

To value a callable or a putable bond, the backward induction process and a binomial
interest rate tree framework is used. The benchmark binomial interest rate tree is
calibrated to ensure that it values benchmark bonds correctly (i.e., that it generates prices
equal to their market prices).
LOS 25.d

When interest rate volatility increases, the value of both call and put options on bonds
increase. As volatility increases, the value of a callable bond decreases (remember that the
investor is short the call option) and the value of a putable bond increases (remember that
the investor is long the put option).

LOS 25.e

The short call in a callable bond limits the investor’s upside when rates decrease, while the
long put in a putable bond hedges the investor against rate increases.
The value of the call option will be lower in an environment with an upward-sloping yield
curve as the probability of the option going in the money is low. A call option gains value
when the upward-sloping yield curve flattens. A put option will have a higher probability of
going in the money when the yield curve is upward sloping; the option loses value if the
upward-sloping yield curve flattens.
LOS 25.f

A backwards induction process is used in a binomial interest rate tree framework for
valuing a callable (or putable) bond. In the binomial tree, we use one-period forward rates
for each period. For valuing a callable (putable) bond, the value used at any node
corresponding to a call (put) date must be either the price at which the issuer will call
(investor will put) the bond, or the computed value if the bond is not called (put)—
whichever is lower (higher).
LOS 25.g

The option adjusted spread (OAS) is the constant spread added to each forward rate in a
benchmark binomial interest rate tree, such that the sum of the present values of a credit
risky bond’s cash flows equals its market price.
LOS 25.h

Binomial trees generated under an assumption of high volatility will lead to higher values
for a call option and a corresponding lower value for a callable bond. Under a high volatility
assumption, we would already have a lower computed value for the callable bond, and
hence, the additional spread (i.e., the OAS) needed to force the discounted value to equal
the market price will be lower.
When an analyst uses a lower-than-actual (higher-than-actual) level of volatility, the
computed OAS for a callable bond will be too high (low) and the bond will be erroneously
classified as underpriced (overpriced).
Similarly, when the analyst uses a lower-than-actual (higher-than-actual) level of volatility,
the computed OAS for a putable bond will be too low (high) and the bond will be
erroneously classified as overpriced (underpriced).
LOS 25.i

LOS 25.j

effective duration (callable) ≤ effective duration (straight)
effective duration (putable) ≤ effective duration (straight)
effective duration (zero-coupon) ≈ maturity of the bond
effective duration of fixed-rate coupon bond < maturity of the bond

effective duration of floater ≈ time (in years) to next reset
LOS 25.k

For bonds with embedded options, one-sided durations—durations when interest rates
rise versus when they fall—are better at capturing interest rate sensitivity than the more
common effective duration. When the underlying option is at (or near) the money, callable
(putable) bonds will have lower (higher) one-sided down-duration than one-sided upduration.
Callable bonds with low coupon rates will most likely not be called and hence their
maturity matched rate is their most critical rate (and has the highest key rate duration). As
the coupon rate increases, a callable bond is more likely to be called and the time-toexercise rate will start dominating the time-to-maturity rate.
Putable bonds with high coupon rates are unlikely to be put and are most sensitive to its
maturity-matched rate. As the coupon rate decreases, a putable bond is more likely to be
put and the time-to-exercise rate will start dominating the time-to-maturity rate.
LOS 25.l

Straight and putable bonds exhibit positive convexity throughout. Callable bonds also
exhibit positive convexity when rates are high. However, at lower rates, callable bonds
exhibit negative convexity.
LOS 25.m

A capped floater contains an issuer option that prevents the coupon rate on a floater from
rising above a specified maximum (i.e., the cap) rate.

A related floating-rate bond is the floored floater where the coupon rate will not fall below
a specified minimum (i.e., the floor).

LOS 25.n

The owner of a convertible bond can exchange the bond for the common shares of the
issuer. A convertible bond includes an embedded call option giving the bondholder the
right to buy the common stock of the issuer.
LOS 25.o

The conversion ratio is the number of common shares for which a convertible bond can be
exchanged.
conversion value = market price of stock × conversion ratio
market conversion price = market price of convertible bond / conversion ratio
market conversion premium per share = market conversion price − market price
The minimum value at which a convertible bond trades is its straight value or its conversion
value, whichever is greater.

LOS 25.p

The value of a bond with embedded options is determined as the value of the straight
bond plus (minus) the value of options that the investor is long (short).

LOS 25.q

The major benefit from investing in convertible bonds is the price appreciation resulting
from an increase in the value of the common stock.
The main drawback of investing in a convertible bond versus investing directly in the
stock is that when the stock price rises, the bond will underperform the stock because of
the conversion premium of the bond.
If the stock price remains stable, the return on the bond may exceed the stock returns
due to the coupon payments received from the bond.
If the stock price falls, the straight value of the bond limits downside risk (assuming bond
yields remain stable).


### Answer Key For Module Quizzes

Module Quiz 25.1, 25.2
1. B The value at any given node in a binomial tree is the average of the present values of
the cash flows at the two possible states immediately to the right of the given node,
discounted at the one-period rate at the node under examination. (Module 25.2, LOS
25.c)
2. C The tree should look like this:

Consider the value of the bond at the upper node for Period 1, V1,U:

Similarly, the value of the bond at the lower node for Period 1, V1,L is:

Now calculate V0, the current value of the bond at Node 0:

(Module 25.2, LOS 25.f)
3. C The tree should look like this:

Consider the value of the bond at the upper node for Period 1, V1,U:

Similarly, the value of the bond at the lower node for Period 1, V1,L is:

Now calculate V0, the current value of the bond at Node 0:

The value of the embedded call option is $112.282 – $111.640 = $0.642. (Module
25.2, LOS 25.f)
4. A The tree should look like this:

Consider the value of the bond at the upper node for Period 1, V1,U:

Similarly, the value of the bond at the lower node for Period 1, V1,L, is:

Now calculate V0, the current value of the bond at Node 0:

The value of the embedded put option is $112.523 – $112.282 = $0.241. (Module
25.2, LOS 25.f)
Module Quiz 25.3, 25.4
1. C Let’s construct a table of the risk differences between the issuer’s callable bond and
on-the-run Treasuries to help us answer this question.

Therefore, the OAS reflects the credit risk of the corporate callable bond over
Treasuries since option risk has been removed. (Module 25.4, LOS 25.g)
2. B Like ordinary options, the value of an embedded option increases as volatility
increases. Furthermore, the arbitrage-free value of an option-free bond (Voption-free)
is independent of the assumed volatility. This implies that the arbitrage-free value of
a callable bond (Vcallable) decreases as volatility increases the value of the embedded
call option (Vcall). This can be seen from the expression for the value of a callable
bond:
The value of the putable bond (Vputable) increases as the assumed volatility
increases the value of the embedded put option (Vput).
(Module 25.3, LOS 25.d)
Module Quiz 25.5
1. B The duration formula is presented correctly. The convexity formula is presented
incorrectly; the “2” should not appear in the denominator of the convexity formula.

(LOS 25.i)

Module Quiz 25.6, 25.7
1. A When an upward sloping yield curve flattens, call options increase in value while put
options decrease in value. (Module 25.3, LOS 25.e)
2. A When the assumed volatility in a binomial tree increases, the computed value of OAS
will decrease. When an analyst uses a lower-than-actual level of volatility like the
15% volatility assumed here, the computed OAS for a callable bond will be too high.
Using the 19% implied volatility instead would have resulted in an estimated OAS
lower than 145 bps. (Module 25.4, LOS 25.h)
3. A Straight bonds generally have higher effective durations than bonds with embedded
options. Both call and put options have the potential to reduce the life of a bond, so
the duration of callable and putable bonds will be less than or equal to that of their
straight counterparts. (Module 25.5, LOS 25.j)
4. A Statement 1 is incorrect. Low-coupon callable bonds are unlikely to be called; hence,
their highest key rate duration corresponds to their time-to-maturity. Statement 2 is
correct. High coupon putable bonds are unlikely to be put and hence, their highest
key rate duration corresponds to their time-to-maturity. (Module 25.6, LOS 25.k)
5. B Straight and putable bonds exhibit positive convexity at all interest rate levels. The
price appreciation for a callable bond due to decline in interest rate is limited due to
the call feature; callables exhibit negative convexity at low rates. Hence a decline in
rates is least likely to result in best price performance for a callable bond. (Module
25.6, LOS 25.l)
6. B When interest rates increase, a callable bond becomes less likely to be called (its
duration will increase). The put option in a putable bond would be more likely to be
exercised in a rising interest rate scenario and hence, the duration of a putable bond
would decrease. Duration of an option-free bond would also decrease as interest
rate increases (but not as significantly). (Module 25.6, LOS 25.k)
7. A Relative to bond A, bond B has lower OAS. Given that the two bonds have similar
credit risk, bond B offers a lower OAS for the same level of risk as bond A and thus
would be considered overpriced. Alternatively, bond A is more attractive
(underpriced) relative to bond B. (Module 25.4, LOS 25.g)
8. C The value of the capped floater is $99.78, as shown here:

The upper node at Year 2 is subject to the 3% cap, and the coupon is adjusted
accordingly.

(Module 25.7, LOS 25.m)
Module Quiz 25.8
1. C The market conversion premium per share is the market conversion price per share
minus the market price per share. The market conversion price per share is
, so the conversion premium per share is $30.833 – $28.50 = $2.333.

(LOS 25.o)
2. C Buying convertible bonds in lieu of direct stock investing limits downside risk to that
of straight bond investing, at the cost of reduced upside potential due to the
conversion premium. (Note that this analysis assumes that interest rates remain
stable. Otherwise, the interest rate risk associated with the straight bond investing
must be considered.) When stock prices fall, the returns on convertible bonds are
likely to exceed those of the stock, because the convertible bond’s price has a floor
equal to the straight bond value. The main drawback of investing in convertible
bonds versus direct stock purchases is that when stock prices rise, the convertible
bond is likely to underperform due to the conversion premium. If the stock price
remains stable, the return on the bond may exceed the stock’s return if the bond’s
coupon payment exceeds the dividend income of the stock. (LOS 25.q)
3. B ABC has a conversion price much less than the current stock price, so the conversion
option is deep in the money. Bond ABC effectively trades like equity and is more
likely to be influenced by the same factors that affect equity prices, in general, than
the factors that affect bond prices.
A busted convertible like XYZ, with a stock price significantly less than the
conversion price, trades like a bond (that’s why a busted convertible is also called a
fixed-income equivalent) and is therefore more likely to be influenced by the factors
that affect bond prices. (LOS 25.q)
4. A A bond that is both callable and convertible contains two embedded options: (1) a
call option on the stock and (2) a call option on the bond. The investor has a short
position in the call option on the bond (the issuer has the right to call the bond) and
a long position in the call option on the stock (the investor has the right to convert
the bond into shares of stock). Therefore, the difference in value between the
callable convertible bond and the value of the comparable option-free bond to the

investor is equal to the value of the call option on the stock minus the value of the
call option on the bond. (LOS 25.p)
5. B A decrease in interest rate volatility will decrease the value of the embedded short
call on the bond (but have no effect on the value of the embedded call on the stock)
and increase the value of the convertible bond.
A decrease in stock price volatility will decrease the value of the embedded call on
the stock (but have no effect on the embedded call on the bond) and decrease the
value of the convertible bond. (LOS 25.p)


---

# Reading 27 — Credit Default Swaps


> [!tip] Exam Focus
> A [[CFA_Glossary/Credit default swap]] ([[CFA_Glossary/Credit default swap]]) is a contract between two parties in which one party purchases
> protection from another party against losses from the default of a borrower. For the exam,
> you should be able to describe CDS, as well as related securities like [[Index CDS|index CDS]]. You should
> know what a [[Credit event|credit event]] is and how the different protocols for [[Settlement|settlement]] work. You
> should be familiar with the principles and factors that drive market pricing of CDS. Be able
> to describe how CDS are used to manage credit exposure, and how they can be used to
> profit from anticipated changes in the [[Credit curve|credit curve]]. You should understand how CDS are
> used for arbitrage to take advantage of relative mispricings of different risky securities.


## Module 27.1: Cds Features and Terms

Credit Default Swaps


A [[Credit Default Swap|credit default swap]] (CDS) is essentially an insurance contract. If a credit
event occurs, the [[Credit protection buyer|credit protection buyer]] gets compensated by the [[Credit protection seller|credit protection seller]].
To obtain this coverage, the protection buyer pays the seller a premium called the CDS
spread. The protection seller is assuming (i.e., long) credit risk, while the protection buyer
is short credit risk. Note that the CDS does not provide protection against market-wide
interest rate risk, only against credit risk. The contract is written on a [[Face value|face value]] of
protection called the [[Notional principal|notional principal]] (or “notional”).

> [!pnote] Professor's Note
> ***The terminology related to CDS is counterintuitive: the protection buyer is the***
> ***short party (short the credit risk of the reference asset), while the seller is the***
> ***long party (long the credit risk of the reference asset).***
> ***Even though the [[CDS spread|CDS spread]] should be based on the underlying credit risk of the reference***
> ***obligation, standardization in the market has led to a fixed coupon on CDS products: 1% for***
> ***investment-grade securities and 5% for high-yield securities. Hence, the coupon rate on the***
> ***CDS and the actual [[Credit Spread]] may be different. The present value of the difference***
> ***between the standardized coupon rate and the [[Credit spread|credit spread]] on the [[Reference obligation|reference obligation]] is***
> ***paid upfront by one of the parties to the contract. For example, a CDS on an investmentgrade bond with a credit spread of 75 basis points (bps) would require a premium payment***
> ***of 100bps (CDS coupon rate) by the protection buyer. To compensate the protection buyer***
> ***(who pays a higher-than-market premium), the protection seller would then pay upfront to***
> ***the buyer the present value of 25bps of the [[Notional principal|notional principal]].***
>
> ***For a protection buyer, a CDS has some of the characteristics of a put option—when the***
> ***underlying performs poorly, the holder of the put option has a right to exercise the option.***
> ***The International Swaps and [[Derivatives|Derivatives]] Association (ISDA), the unofficial governing body***
> ***of the industry, publishes standardized contract terms and conventions in the ISDA Master***
> ***Agreement to facilitate smooth functioning of the CDS market.***
>
> ***> **LOS 27.a:** Describe credit default swaps (CDS), single-name and [[Index CDS|index CDS]],***
> ***and the parameters that define a given CDS product.***
>
> ***[[Single-name CDS|Single-Name CDS]]***
> ***In the case of a [[Single-name CDS|single-name CDS]], the [[Reference obligation|reference obligation]] is the fixed-income security on***
> ***which the swap is written, usually a senior unsecured obligation (in the case of a senior***
> ***CDS). The issuer of the [[Reference obligation|reference obligation]] is called the [[Reference entity|reference entity]]. The CDS pays off***
> ***not only when the [[Reference entity|reference entity]] defaults on the [[Reference obligation|reference obligation]] but also when the***
> ***[[Reference entity|reference entity]] defaults on any other issue that is ranked [[Pari passu|pari passu]] (i.e., same rank) or***
> ***higher. The CDS payoff is based on the [[Market value|market value]] of the [[Cheapest-to-deliver|cheapest-to-deliver]] (CTD) bond***
> ***that has the same seniority as the reference obligation.***

> [!pnote] Professor's Note
> ***The [[Cheapest-to-deliver|cheapest-to-deliver]] bond is the debt instrument with the same seniority as***
> ***the reference obligation but that can be purchased and delivered at the lowest***
> ***cost.***

### Example: Cheapest-to-deliver


Party X is a protection buyer in a $10 million [[Notional principal|notional principal]] senior CDS of Alpha, Inc.
There is a [[Credit event|credit event]] (i.e., Alpha defaults) and the market prices of Alpha’s bonds after
the [[Credit event|credit event]] are as follows:
Bond P, a subordinated unsecured debenture, is trading at 15% of par.
Bond Q, a five-year senior unsecured debenture, is trading at 25% of par.
Bond R, a three-year senior unsecured debenture, is trading at 30% of par.
What will be the payoff on the CDS?
Answer:
The [[Cheapest-to-deliver|cheapest-to-deliver]] senior unsecured debenture (i.e., same seniority as the senior
CDS) is bond Q. The payoff will be the difference between the notional principal and
[[Market value|market value]] of the CTD.

[[Index CDS|Index CDS]]
An [[Index CDS|index CDS]] covers multiple issuers, allowing market participants to take on an exposure
to the credit risk of several companies simultaneously in the same way that stock indexes
allow investors to take on an equity exposure to several companies at once. In this case,
the protection for each issuer is equal (i.e., equally weighted) and the total notional
principal is the sum of the protection on all the issuers.

### Example: Index CDS


Party X is a protection buyer in a five-year, $100 million notional principal CDS for CDXIG, which contains 125 entities. One of the index constituents, company A, defaults and
its bonds trade at 30% of par after default.
1. What will be the payoff on the CDS?
2. What will be the notional principal of the CDS after default?
Answer:
1. The notional principal attributable to entity A is $100 million / 125 = $0.8 million.
Party X should receive payment of $0.8 million – (0.3)($0.8 million) = $560,000.
2. Post the default event, the remainder of the CDS continues with a notional principal of
$99.2 million.
The pricing of an index CDS is dependent on the [[Correlation|correlation]] of default ([[Credit correlation|credit correlation]])
among the entities in the index. The higher the [[Correlation|correlation]] of default among index
constituents, the higher the spread on the index CDS.

> **LOS 27.b:** Describe credit events and [[Settlement|settlement]] protocols with respect to
CDS.
A default is defined as the occurrence of a [[Credit event|credit event]]. Common types of credit events
specified in CDS agreements include [[Bankruptcy|bankruptcy]], [[Failure to pay|failure to pay]], and [[Restructuring|restructuring]].
[[Bankruptcy|Bankruptcy]]. A [[Bankruptcy|bankruptcy]] protection filing allows the defaulting party to work with
creditors under the supervision of the court so as to avoid full [[Liquidation|liquidation]].
[[Failure to pay|Failure to pay]]. Occurs when the issuer misses a scheduled coupon or principal payment
without filing for formal [[Bankruptcy|bankruptcy]].
[[Restructuring|Restructuring]]. Occurs when the issuer forces its creditors to accept terms that are
different than those specified in the original issue. [[Restructuring|Restructuring]] is less common in the
United States as issuers prefer to go the bankruptcy protection route.
A 15-member group of the ISDA called the Determinations Committee (DC) declares when
a credit event has occurred. A supermajority vote (at least 12 members) is required for a
credit event to be declared.
When there is a credit event, the swap will be settled in cash or by physical delivery. With
physical delivery, the protection seller receives the reference obligation (i.e., the bond or
loan) and pays the protection buyer the [[Notional amount|notional amount]], as shown in Figure 27.1.


**Figure 27.1: [[Physical settlement|Physical Settlement]] on [[Credit Default Swap|Credit Default Swap]] After a Credit Event**


In the case of a [[Cash settlement|cash settlement]], the [[Payout amount|payout amount]] is the [[Payout ratio]] times the notional
principal. The [[Payout ratio|payout ratio]] depends on the [[Recovery rate]] (i.e., the proportion of par that
the bond trades at after default) as shown in Figure 27.2.


**Figure 27.2: [[Cash settlement|Cash Settlement]] on [[Credit Default Swap|Credit Default Swap]] After a Credit Event**


## Module 27.2: Factors Affecting Cds Pricing


> **LOS 27.c:** Explain the principles underlying and factors that influence the
market’s pricing of CDS.


The factors that influence the pricing of CDS (i.e., [[CDS spread|CDS spread]]) include the probability of
default, the [[CFA_Glossary/Loss given default]], and the coupon rate on the swap. The [[CDS spread|CDS spread]] is higher
for higher [[Probability of Default|probability of default]] and for higher [[Loss Given Default|loss given default]]. For this discussion, we
will focus on [[Single-name CDS|single-name CDS]]. However, the principles apply to index CDS as well.
Earlier, we showed the calculation of CVA, which is the present value of [[Expected Loss|expected loss]]. CVA,
therefore, would be the best estimate of the value of the hedging instrument to cover the
risk of the protection seller.
[[Probability of Default|Probability of default]] (POD) is the [[Likelihood|likelihood]] of default by the [[Reference entity|reference entity]] in a given
year. However, because the CDS typically covers a multi-year horizon, the probability of
default is not constant; the [[Probability of Default|probability of default]] usually increases over time. Hence, the
[[Probability of Default|probability of default]] in any given year assumes that no default has occurred in the
preceding years. We call the [[Probability of Default|probability of default]] given that it has not already occurred
the [[Conditional probability|conditional probability]] of default or [[CFA_Glossary/Hazard rate]]. The credit risk of a reference
obligation and hence the cost of protection is proportional to the [[Hazard Rate|hazard rate]]. The POD in
any year is equal to the [[Probability of survival|probability of survival]] at the end of the prior year multiplied by the
[[Hazard Rate|hazard rate]] of that year.


### Example: Hazard rate


Consider a five-year senior CDS on Xeon Corp. Xeon’s [[Hazard Rate|hazard rate]] is 2% and increases by
1% per year.

Compute the survival rate in five years.
Answer:
The hazard rates for the five years are: 2%, 3%, 4%, 5%, and 6%.

For a single-period CDS, ignoring the [[Time value of money|time value of money]], we can estimate the CDS
premium as:
For example, if the [[Recovery rate|recovery rate]] is 50% and POD is 3%, [[CDS spread|CDS spread]] = 0.5 × 0.03 = 0.015 or
150 bps.
The cash payments made by the protection buyer on the CDS (i.e., the coupon payments)
cease when there is a default (i.e., when the CDS terminates). Hence, the [[Expected value|expected value]] of
the coupon payments also depends on the [[Hazard Rate|hazard rate]].
The payments made by the protection buyer to the seller are the [[Premium leg|premium leg]]. On the
other side of the contract, the protection seller must make a payment to the protection
buyer in case of a default; these contingent payments make up the [[Protection leg|protection leg]].
The difference between the present value of the [[Premium leg|premium leg]] and the present value of the
[[Protection leg|protection leg]] determines the [[Upfront payment|upfront payment]].
We can approximate the [[Upfront premium|upfront premium]] as the difference between the CDS spread and
the CDS coupon rate, multiplied by the duration of the CDS. Again, the CDS spread is the
compensation for bearing the credit risk of the reference obligation.

> [!pnote] Professor's Note
> ***Be careful here! The formula uses duration of the CDS and not the duration of***
> ***the reference obligation.***
> ***[[Upfront premium|upfront premium]] % ≈ (CDS spread – CDS coupon) × duration***
> ***which means that:***
>
> ***We can also quote the CDS price as:***

### Example: Upfront premium and price of CDS


Aki Mutaro, bond portfolio manager for a regional bank, is considering buying protection
on one of the bank’s high-yield holdings: Alpha, Inc., bonds. Ten-year CDS on Alpha
bonds have a coupon rate of 5% while the 10-year Alpha CDS spread is 3.5%. The
duration of the CDS is 7.

Calculate the approximate [[Upfront premium|upfront premium]] and price of a 10-year Alpha Inc., CDS.
Answer:

Hence, the protection seller would pay (approximately) 10.5% of the notional to the
protection buyer upfront because the CDS coupon is higher than the credit spread.

Valuation After Inception of CDS
At inception of a CDS, the CDS spread (and the [[Upfront premium|upfront premium]]) is computed based on
the credit quality of the reference entity. After inception, the credit quality of the reference
entity (or the credit risk premium in the overall market) may change. This will lead to the
underlying CDS having a nonzero value. For example, if the credit spread declines, the
protection seller, having locked in a higher credit spread at initiation, would gain.
The change in value of a CDS after inception can be approximated by the change in spread
multiplied by the duration of the CDS:
or
Note that the protection buyer is short credit risk and hence benefits (i.e., profit is positive)
when [[Credit spreads|credit spreads]] widen.
The protection buyer (or seller) can unwind an existing CDS exposure (prior to expiration or
default) by entering into an offsetting transaction. For example, a protection buyer can
remove his exposure to the CDS by selling protection with the same terms as the original
CDS and maturity equal to the remaining maturity on the existing CDS. The difference
between the upfront premium paid and received should be (approximately) equal to the
profit for the protection buyer. This process of capturing value from an in-the-money CDS
exposure is called [[Monetizing|monetizing]] the gain.


## Module 27.3: Cds Usage


> **LOS 27.d:** Describe the use of CDS to manage credit exposures and to
express views regarding changes in the shape and/or level of the credit
curve.


[[Credit curve|Credit Curve]]
The [[Credit curve|credit curve]] is the relationship between [[Credit spreads|credit spreads]] for different bonds issued by an
entity, and the bonds’ maturities. The [[Credit curve|credit curve]] is similar to the term structure of
interest rates. If the longer maturity bonds have a higher credit spread compared to

shorter maturity bonds, the credit curve will be upward sloping. However, if the hazard rate
is constant, the credit curve will be flat.
CDS can be used to manage credit exposures of a bond portfolio. For example, in
anticipation of declining (increasing) [[Credit spreads|credit spreads]], a portfolio manager may increase
(decrease) credit exposure in the portfolio by being a protection seller (buyer).
In a naked CDS, an investor with no underlying exposure purchases (or sells)protection in
the CDS market. In a long/short trade, an investor purchases protection on one reference
entity while simultaneously selling protection on another (often related) reference entity.
The investor is betting that the difference in [[Credit spreads|credit spreads]] between the two reference
entities will change to the investor’s advantage. This is similar to going long (protection
seller exposure) in one reference entity bond and simultaneously going short (protection
buyer exposure) in the other reference entity bond.
A [[Curve trade|curve trade]] is a type of long/short trade where the investor is buying and selling
protection on the same reference entity but with a different maturity. If the investor
expects that an upward-sloping credit curve on a specific corporate issuer will flatten, she
may take the position of protection buyer in a short maturity CDS and the position of
protection seller in a long maturity CDS.
An investor concerned about the credit risk of an issuer in the near term while being more
confident of the long-term prospects of the issuer might buy protection in the short-term
CDS and offset the premium cost by selling protection in the long-term CDS. An investor
who believes that the short-term outlook for the reference entity is better than the longterm outlook can use a curve-steepening trade; buying protection in a long-term CDS and
selling protection in a short-term CDS. The investor will profit if the credit curve steepens;
that is, if long-term credit risk increases relative to short-term credit risk. Conversely, an
investor who is bearish about the reference entity’s prospects in the short term will enter
into a curve-flattening trade.

> **LOS 27.e:** Describe the use of CDS to take advantage of valuation disparities
among separate markets, such as bonds, loans, equities, and equity-linked
instruments.

Uses of CDS
Earning arbitrage profits is another motivation for trading in the CDS market. Differences in
pricing between asset and [[Derivative|derivative]] markets, or differences in pricing of different products
in the market, may offer potential arbitrage profits.
A [[Basis trade|basis trade]] is an attempt to exploit the difference in credit spreads between bond
markets and the CDS market. Basis trades rely on the idea that such [[Mispricing|mispricing]] will be
temporary and that disparity should eventually disappear after it is recognized. For

### Example: , if a specific bond is trading at a credit spread of 4% over MRR in the bond market

but the CDS spread on the same bond is 3%, a trader can profit by buying the bond and
taking the protection buyer position in the CDS market. If the expected [[Convergence]]
occurs, the trader will make a profit.

Another arbitrage transaction involves buying and selling debt instruments issued by the
same entity based on which instruments the CDS market suggests to be undervalued or
overvalued.
In a [[Leveraged buyout|leveraged buyout]] (LBO), the firm will issue a great amount of debt in order to
repurchase all of the company’s publicly traded equity. This additional debt will increase
the CDS spread because default is now more likely. An investor who anticipates an LBO
might purchase both the stock and CDS protection, both of which will increase in value
when the LBO eventually occurs.
In the case of an index CDS, the value of the index should be equal to the sum of the values
of the index components. An arbitrage transaction is possible if the credit risk of the index
constituents is priced differently than the index CDS spread.
Collateralized debt obligations (CDO) are claims against a portfolio of debt securities. A
[[Synthetic CDO|synthetic CDO]] has similar credit [[Risk exposure|risk exposure]] to that of a cash CDO but is assembled using
CDS rather than debt securities. If the [[Synthetic CDO|synthetic CDO]] can be created at a cost lower than
that of the cash CDO, investors can buy the [[Synthetic CDO|synthetic CDO]] and sell the cash CDO, engaging
in a profitable arbitrage.

### Module Quiz 27.1, 27.2, 27.3

Use the following information to answer Questions 1 through 6.
Jamshed Banaji, CFA, manages a $400 million bond portfolio for a large public pension fund.
Banaji is concerned about volatility in the credit markets and expects credit spreads to widen in
the short-term but revert back to current levels over the long-term.
Banaji has flagged two of his holdings for further scrutiny: IDG Corp. and Zeta Corp.
The portfolio currently has $10 million par value of 6% 10-year senior unsecured IDG Corp.
bonds. Because he is concerned about IDG’s credit risk, Banaji enters into a [[Credit Default Swap|credit default swap]]
as a protection buyer. Banaji selects a five-year senior CDS for IDG with a coupon rate of 5% and
a duration of 4. IDG bonds have a yield-to-maturity of 6.5%. The MRR yield curve is flat at 2%.
Banaji is also concerned about the Zeta Corp. bonds that he holds. Zeta’s management is
planning to pursue a recapitalization plan that involves a large stock buyback program financed
by new debt.
1. The most appropriate strategy for Banaji, given his expectation about changing credit
spreads, is a:
A. credit [[Curve trade|curve trade]]; selling protection in the short-term and purchasing protection in the
long-term.
B. credit [[Curve trade|curve trade]]; buying protection in the short-term and selling protection in the longterm.
C. CDS trade; buying protection in the short-term only.
2. At inception of the CDS for IDG bonds, Banaji is most likely to:
A. receive a premium of $200,000.
B. pay a premium of $300,000.
C. receive a premium of $400,000.
3. For this question only, suppose that six months after the inception of the swap, IDG declares
bankruptcy. Figure 1 shows the market prices of IDG bonds after the company files for

bankruptcy.

**Exhibit 1: Market Price of IDG Bonds Post Bankruptcy Filing**


If Banaji has a choice of [[Settlement|settlement]] procedure, he is most likely to choose:
A. [[Physical settlement|physical settlement]].
B. [[Cash settlement|cash settlement]] and the payoff would be $6 million.
C. [[Cash settlement|cash settlement]]nt|settlement]] and the payoff would be $7 million.
4. Which of the following statements about hazard rate is most accurate? Hazard rate:
A. is the probability of default given that default has already occurred in a previous period.
B. affects both the [[Premium leg|premium leg]] as well as the [[Protection leg|protection leg]] in a CDS.
C. is higher for higher [[Loss Given Default|loss given default]].
5. The most appropriate strategy for Banaji to follow in regard to Zeta Corp. would be to buy Zeta
Corp.:
A. stock and buy CDS protection on Zeta Corp. bonds.
B. bonds and sell CDS protection on Zeta Corp. bonds.
C. stock and sell CDS protection on Zeta Corp. bonds.
6. The statement “credit spreads are positively related to [[Loss Given Default|loss given default]] and to hazard rate”
is:
A. correct.
B. correct regarding [[Loss Given Default|loss given default]] but incorrect regarding hazard rate.
C. correct regarding hazard rate but incorrect regarding [[Loss Given Default|loss given default]].


> [!abstract] Key Concepts
> LOS 27.a

A [[Credit default swap (CDS)|credit default swap (CDS)]] is essentially an insurance contract wherein upon occurrence of
a credit event, the [[Credit protection buyer|credit protection buyer]] gets compensated by the [[Credit protection seller|credit protection seller]].
To obtain this coverage, the protection buyer pays the seller a premium called the CDS
spread. In the case of a [[Single-name CDS|single-name CDS]], the reference obligation is the fixed income
security on which the swap is written. An index CDS covers an equally-weighted
[[Combination|combination]] of borrowers.
LOS 27.b

A default is defined as occurrence of a credit event. Common types of credit events
specified in CDS agreements include bankruptcy, [[Failure to pay|failure to pay]], and [[Restructuring|restructuring]].
When there is a credit event, the swap will be settled in cash or by physical delivery.
LOS 27.c

The factors that influence the pricing of CDS (i.e., CDS spread) include the probability of
default, the loss given default, and the coupon rate on the swap. The CDS spread is higher
for a higher probability of default and for a higher loss given default. The conditional

probability of default (i.e., the probability of default given that default has not already
occurred) is called the hazard rate.
The upfront premium on a CDS can be computed as:
Or approximately:
The change in value for a CDS after inception can be approximated by the change in spread
multiplied by the duration of the CDS.

LOS 27.d

In a naked CDS, an investor with no exposure to the underlying purchases protection in the
CDS market.
In a long/short trade, an investor purchases protection on one reference entity while
selling protection on another reference entity.
A [[Curve trade|curve trade]] is a type of long/short trade where the investor is buying and selling
protection on the same reference entity but with different maturities. An investor who
believes the short-term outlook for the reference entity is better than the long-term
outlook can use a curve-steepening trade (buying protection in a long-term CDS and selling
protection in a short-term CDS) to profit if the credit curve steepens. Conversely, an
investor who is bearish about the reference entity’s prospects in the short term will enter
into a curve-flattening trade.
LOS 27.e

A [[Basis trade|basis trade]] is an attempt to exploit the difference in credit spreads between bond
markets and the CDS market. Basis trades rely on the idea that such mispricings will be
temporary and that disparity should eventually disappear after it is recognized.
If a [[Synthetic CDO|synthetic CDO]] can be created at a cost lower than that of the equivalent cash CDO,
investors can buy the synthetic CDO and sell the cash CDO, producing a profitable
arbitrage.

### Answer Key For Module Quizzes

Module Quiz 27.1, 27.2, 27.3
1. B Banaji expects credit spreads to widen in the short-term; therefore, the appropriate
strategy is to buy short-term CDS protection. Similarly, long-term credit spreads are
expected to revert back to current levels (narrow) and hence Banaji can sell
protection in the long-term CDS. Buying protection only would cost more money (the
protection buyer premium is not offset by premium income from selling protection)

and does not use Banaji’s entire information set and, therefore, is not most
appropriate. (Module 27.2, LOS 27.c)
2. A credit spread on IDG bonds = yield – MRR = 6.5% – 2% = 4.5%
upfront premium (paid by protection buyer) ≈ (CDS spread – CDS coupon) ×
duration × notional principal
= (0.045 – 0.05) × 4 × $10 million = –$200,000
Because the computed value is negative, $200,000 would be received by Banaji as
the protection buyer. (Module 27.2, LOS 27.c)
1. B The CDS in the question is a senior CDS, hence the reference obligation is a senior
unsecured bond. The payoff on the CDS is based on the CTD with same seniority as
reference obligation. From the three choices given, the five-year 5% senior
unsecured is the cheapest to deliver. Hence, the payoff will be notional principal –
[[Market value|market value]] of the CTD = $10 million – $4 million = $6 million.
Note that [[Physical settlement|physical settlement]] would not be advantageous to Banaji; Figure 1
indicates that the IDG bonds that Banaji is currently holding have a [[Market value|market value]] of
$4.5 million, so the implied payoff of physically delivering these bonds in exchange
for $10 million would be only $5.5 million ($10 million – $4.5 million). (Module
27.2, LOS 27.c)
1. B Hazard rate is the [[Conditional probability|conditional probability]] of default given that default has not
occurred in previous periods. The hazard rate affects the [[Protection leg|protection leg]]: the higher
the hazard rate, the higher the [[Expected value|expected value]] of payoffs made by the protection
seller upon default. Hazard rate also affects the [[Premium leg|premium leg]] because once default
occurs, the CDS ceases to exist and premium income would also cease. Loss given
default depends on the [[Recovery rate|recovery rate]] and not on hazard rate (probability of default).
(Module 27.2, LOS 27.c)
2. A Due to [[Leveraged recapitalization|leveraged recapitalization]] of Zeta Corp., it can be expected that the credit
spread on Zeta bonds would widen leading to increased value for CDS protection
buyer. Additionally, the increase in stock buyback would be expected to increase the
value of Zeta stock. Banaji should purchase both the stock and CDS protection, both
of which will increase in value when the LBO occurs. (Module 27.3, LOS 27.d)
3. A Credit spreads are positively related to hazard rates and loss given default, and
negatively related to recovery rates. (Module 27.3, LOS 27.d)

Topic Quiz: Fixed Income
You have now finished the Fixed Income topic section. Please log into your Schweser online
dashboard and take the Topic Quiz on this section. The Topic Quiz provides immediate
feedback on how effective your study has been for this material. Questions are more examlike than typical Module Quiz or QBank questions; a score of less than 70% indicates that
your study likely needs improvement. These tests are best taken timed; allow three minutes
per question.


---

