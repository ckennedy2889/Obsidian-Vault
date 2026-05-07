---
title: "Derivatives"
subject: "Derivatives"
tags: [CFA-L2, derivatives]
aliases: []
---

# Derivatives

*CFA Level II — Schweser Notes 2025*

---

## Readings

- [[#Reading 28 — Pricing and Valuation of Forward Commitments|Reading 28: Pricing and Valuation of Forward Commitments]]
- [[#Reading 29 — Valuation of Contingent Claims|Reading 29: Valuation of Contingent Claims]]

---

# Reading 28 — Pricing and Valuation of Forward Commitments


> [!tip] Exam Focus
> This topic review covers the calculation of price and value for forward and future contracts,
> specifically equity forward contracts, bond forward contracts, and forward (interest) rate
> agreements. This topic review also covers pricing and [[Valuation|valuation]] of different swaps,
> including [[Interest rate|interest rate]] swaps, equity swaps, and currency swaps. Be able to structure
> profitable [[Arbitrage|arbitrage]] transactions should the [[Forward price|forward price]] differs from the [[No-arbitrage pricing|no-arbitrage]]
> price. There are many formulas in this reading. However, once you realize the fundamental
> principles of no-[[Arbitrage|arbitrage]] pricing, the formulas will start becoming somewhat less
> intimidating. There is a lot of testable material from this seven-LOS reading!


## Module 28.1: Pricing and Valuation Concepts

Warm-Up: Forward Contracts


The party to the [[Forward contract]] that agrees to buy the financial or
physical asset has a long forward position and is called the long. The party to the forward
contract that agrees to sell/deliver the asset has a short forward position and is called the
short.
We will illustrate the basic [[Forward contract|forward contract]] mechanics through an example based on the
purchase and sale of a Treasury bill. Note that while forward contracts on T-bills are usually
quoted in terms of a discount percentage from [[Face value|face value]], we use dollar prices here to
make the example easy to follow.
Consider a contract under which Party A agrees to buy a $1,000 [[Face value|face value]] 90-day Treasury
bill from Party B 30 days from now at a price of $990. Party A is the long and Party B is the
short. Both parties have removed uncertainty about the price they will pay or receive for
the T-bill at the future date. If 30 days from now T-bills are trading at $992, the short must
deliver the T-bill to the long in exchange for a $990 payment. If T-bills are trading at $988
on the future date, the long must purchase the T-bill from the short for $990, the contract
price.
Typically, no money changes hands at the inception of the contract, unlike futures contracts
in which each party posts an initial deposit called the margin as a guarantee of
performance.

At any point in time, including the [[Settlement|settlement]]nt date|[[Settlement|settlement]] date]], the party to the [[Forward contract|forward contract]] with
the negative value will owe money to the other side. The other side of the contract will
have a positive value of equal amount. Following this example, if the T-bill price is $992 at
the (future) [[Settlement date|settlement date]], and the short does not deliver the T-bill for $990 as promised,
the short has defaulted.

[[Forward contract|Forward Contract]] Price Determination
The No-[[Arbitrage|Arbitrage]] Principle
The price of a [[Forward contract|forward contract]] is not the price to purchase the contract; in fact, the parties
to a [[Forward contract|forward contract]] typically pay nothing to enter into the contract at its inception. Here,
price refers to the [[Forward price|forward price]] of the [[Underlying|underlying]]. This price may be a U.S. dollar or euro
price, but it is often expressed as an [[Interest rate|interest rate]] or currency [[Exchange Rate]]. For T-bills, the
price will be expressed as an annualized percentage discount from [[Face value|face value]]; for coupon
bonds, it will usually be expressed as a [[Yield to maturity]]; for the implicit loan in a forward
rate agreement (FRA), it will be expressed as an annualized MRR; and for a currency
forward, it is expressed as an exchange rate between the two [[Currencies|currencies]] involved. However
it is expressed, this rate, yield, discount, or dollar amount is the [[Forward price|forward price]] in the
contract.
The price that we wish to determine is the [[Forward price|forward price]] that makes the values of both the
long and the short positions zero at contract initiation. We will use the no-[[Arbitrage|arbitrage]]
principle: there should be no riskless profit to be gained by a [[Combination|combination]] of a forward
contract position with positions in other assets. This principle assumes that (1) transactions
costs are zero, (2) there are no restrictions on short sales or on the use of short sale
proceeds, and (3) both borrowing and lending can be done in unlimited amounts at the
[[Risk-Free Rate]] of interest. This concept is so important that we’ll express it in a formula:
forward price = price that prevents profitable riskless arbitrage in frictionless markets

> [!pnote] Professor's Note
> ***We cover the first two LOS out of curriculum order for ease of exposition.***
>
> ***> **LOS 28.b:** Describe the [[Carry arbitrage model|carry arbitrage model]] without [[Underlying|underlying]] cashflows and with***
> ***[[Underlying|underlying]] cashflows.***
>
> ***A Simple Version of the Cost-of-Carry Model***
> ***In order to explain the no-arbitrage condition as it applies to the determination of forward***
> ***prices, we will first consider a forward contract on an asset that costs nothing to store and***
> ***makes no payments to its owner over the life of the forward contract. A zero-coupon (pure***
> ***discount) bond meets these criteria. Unlike gold or wheat, it has no storage costs; unlike***
> ***stocks, there are no dividend payments to consider; and unlike coupon bonds, it makes no***
> ***periodic interest payments.***
> ***The general form for the calculation of the forward contract price can be stated as follows:***

### Example: Calculating the no-arbitrage forward price


Consider a 3-month forward contract on a [[Zero-coupon bond|zero-coupon bond]] with a [[Face value|face value]] of $1,000
that is currently quoted at $500, and suppose that the annual risk-free rate is 6%.
Determine the price of the forward contract under the no-arbitrage principle.
Answer:

Now, let’s explore in more detail why $507.34 is the no-arbitrage price of the forward
contract.
Cash and Carry Arbitrage When the Forward Contract Is Overpriced
Suppose the forward contract is actually trading at $510 rather than the no-arbitrage price
of $507.34. A [[Short position|short position]] in the forward contract requires the delivery of this bond three
months from now. The arbitrage that we examine in this case amounts to borrowing $500
at the risk-free rate of 6%, buying the bond for $500, and simultaneously taking the short
position in the forward contract on the [[Zero-coupon bond|zero-coupon bond]] so that we are obligated to
deliver the bond at the expiration of the contract for the forward price of $510.
At the [[Settlement|settlement]]nt date|[[Settlement|settlement]] date]], we can satisfy our obligation under the terms of the forward
contract by delivering the [[Zero-coupon bond|zero-coupon bond]] for a payment of $510, regardless of its
[[Market value|market value]] at that time. We will use the $510 payment we receive at settlement from the
forward contract (the forward contract price) to repay the $500 loan. The total amount to
repay the loan, since the term of the loan is three months, is:
loan repayment = $500 × (1.06)0.25 = $507.34
The payment of $510 we receive when we deliver the bond at the forward price is greater
than our loan payoff of $507.34, and we will have earned an arbitrage profit of $510 –
$507.34 = $2.66. Notice that this is equal to the difference between the actual forward
price and the no-arbitrage forward price. The transactions are illustrated in Figure 28.1.


**Figure 28.1: Cash and Carry Arbitrage When Forward Is Overpriced**


> [!pnote] Professor's Note
> ***Here’s a couple hints to help you remember which transactions to undertake***
> ***for cash and carry arbitrage: (1) always start with nothing (no cash, no***
> ***securities), (2) buy underpriced assets and sell overpriced assets (“buy low, sell***
> ***high”), and (3) take opposite positions in the spot and forward markets.***
> ***So, if the [[Futures contract]] is overpriced, you want to take a [[Short position|short position]] in***
> ***those futures (which obligates you to sell at a fixed price). Because you go short***
> ***in the [[Forward market|forward market]], you take the opposite position in the spot market and***
> ***buy the asset. You need money to buy the asset, so you have to borrow.***
> ***Therefore, to set up a cash and carry arbitrage:***
> ***forward overpriced:***
>
> ***So far, the [[Underlying|underlying]] instrument was a [[Zero-coupon bond|zero-coupon bond]], and hence had no associated***
> ***cash flows during the forward contract period. If the holder of the underlying receives cash***
> ***flows (as coupon or dividends), the [[Present Value]] of those cash flows will be subtracted***
> ***from the [[Spot price|spot price]] of the underlying. We will see this later in this reading.***
> ***Reverse Cash and Carry Arbitrage When the Forward Contract Is Underpriced***
> ***Suppose the forward contract is actually trading at $502 instead of the no-arbitrage price***
> ***of $507.34. We reverse the arbitrage trades from the previous case and generate an***
> ***arbitrage profit as follows: We sell the bond short today for $500 and simultaneously take***
> ***the [[Long position|long position]] in the forward contract, which obligates us to purchase the bond in 90***
> ***days at the forward price of $502. We invest the $500 proceeds from the short sale at the***
> ***6% annual rate for three months.***
> ***In this case, at the [[Settlement date|settlement date]], we receive the investment proceeds of $507.34, accept***
> ***delivery of the bond in return for a payment of $502, and close out our [[Short position|short position]] by***
> ***delivering the bond we just purchased at the forward price.***
> ***The payment of $502 we make as the [[Long position|long position]] in the contract is less than the***
> ***investment proceeds of $507.34, and we have earned an arbitrage profit of $507.34 – $502***
> ***= $5.34. The transactions are illustrated in Figure 28.2.***
>
>
> *****Figure 28.2: Reverse Cash and Carry Arbitrage When Forward Is Underpriced*****
>
>
> ***In this case, because the forward contract is underpriced, the trades are reversed from***
> ***cash and carry arbitrage. To set up the reverse cash-and-carry arbitrage:***
> ***forward underpriced:***
> ***From the calculations just listed, we can see that the no-arbitrage forward price that yields***
> ***a zero value for both the long and short positions in the forward contract at inception is the***
> ***no-arbitrage price of $507.34.***

> [!pnote] Professor's Note
> ***Day count and [[Compounding|compounding]] conventions vary among different financial***
> ***instruments. There are three variations used in the CFA curriculum:***
> ***All MRR-based contracts such as FRAs, swaps, caps, floors, etc.:***
> ***– 360 days per year and [[Simple interest|simple interest]]***
> ***– Multiply “r” by days/360***
>
> ***Equities, bonds, and stock options:***
> ***– 365 days per year and periodic compound interest***
> ***– Raise (1 + r) to an exponent of days/365***
>
> ***Equity indexes:***
> ***– 365 days per year and continuous [[Compounding|compounding]]***
> ***– Raise Euler’s number “e” to an exponent of “r” times days/365***

## Module 28.2: Pricing and Valuation of Equity Forwards


> **LOS 28.a:** Describe how equity forwards and futures are priced, and calculate and
interpret their no-arbitrage value.

Equity Forward Contracts With Discrete Dividends
Recall that the no-arbitrage forward price in our earlier example was calculated for an asset
with no periodic payments. A stock, a stock portfolio, or an equity index may have expected

dividend payments over the life of the contract. In order to price such a contract, we must
either adjust the [[Spot price|spot price]] for the present value of the expected dividends (PVD) over the
life of the contract, or adjust the forward price for the [[Future Value]] of the dividends (FVD)
over the life of the contract. The no-arbitrage price of an equity forward contract in either
case is:

For equity contracts, use a 365-day basis for calculating T. For example, if it is a 60-day
contract, T = 60 / 365.

### Example: Calculating the price of a forward contract on a stock


Calculate the no-arbitrage forward price for a 100-day forward on a stock that is
currently priced at $30.00 and is expected to pay a dividend of $0.40 in 15 days, $0.40 in
85 days, and $0.50 in 175 days. The annual risk-free rate is 5%, and the [[Yield curve]] is flat.
Answer:
Ignore the dividend in 175 days because it occurs after the maturity of the forward
contract.

The timeline of cash flows is shown in the following figure.
Pricing a 100-Day Forward Contract on Dividend-Paying Stock

To calculate the value of the [[Long position|long position]] in a forward contract on a dividend-paying
stock, we make the adjustment for the present value of the remaining expected discrete
dividends at time t (PVDt) to get:


> [!pnote] Professor's Note
> ***This formula still looks like the standard [[Spot price|spot price]] minus present value of***
> ***forward price. However, now the “[[Spot price|spot price]]” has been adjusted by subtracting***
> ***out the present value of the dividends because the [[Long position|long position]] in the forward***
>
> ***contract does not receive the dividends paid on the underlying stock. So, now***
> ***think adjusted spot price less present value of forward price.***
> ***If given the current forward price (FPt) on the same underlying and with the same***
> ***maturity:***

### Example: Calculating the value of an equity forward contract on a stock


After 60 days, the value of the stock in the previous example is $36.00. Calculate the
value of the equity forward contract on the stock to the long position, assuming the riskfree rate is still 5% and the [[Yield curve|yield curve]] is flat.
Answer:
There’s only one dividend remaining (in 25 days) before the contract matures (in 40
days) as shown here, so:

Valuing a 100-Day Forward Contract After 60 Days

Equity Forward Contracts With Continuous Dividends
To calculate the price of an equity index forward contract, rather than take the present
value of each dividend on (possibly) hundreds of stocks, we can make the calculation as if
the dividends are paid continuously (rather than at discrete times) at the [[Dividend yield|dividend yield]]
rate on the index. Using [[Continuous time|continuous time]] discounting, we can calculate the no-arbitrage
forward price as:


> [!pnote] Professor's Note
> ***The relationship between the periodically compounded risk-free rate Rf and the***
> ***continuously compounded rate is***
> ***For example, 5%***
> ***compounded annually is equal to ln(1.05) = 0.04879 = 4.879% compounded***
> ***continuously. The 2-year 5% future value factor can then be calculated as either***
> ***1.052 = 1.1025 or e0.04879×2 = 1.1025.***

### Example: Calculating the price of a forward contract on an equity index


The value of the S&P 500 Index is 1,140. The continuously compounded risk-free rate is
4.6% and the continuous [[Dividend yield|dividend yield]] is 2.1%. Calculate the no-arbitrage price of a
140-day forward contract on the index.
Answer:
On a TI BA II PLUS calculator, use the following keystrokes:


### Module Quiz 28.1, 28.2

1. A stock is currently priced at $30 and is expected to pay a dividend of $0.30 20 days and 65
days from now. The contract price for a 60-day forward contract when the [[Interest rate|interest rate]] is 5%
is closest to:

### A. $29.46.


### B. $29.70.


### C. $29.94.

2. After 37 days, the stock in Question 1 is priced at $21, and the risk-free rate is still 5%. The
value of the forward contract on the stock to the [[Short position|short position]] is:

### A. –$8.85.

B. +$8.85.
C. +$9.00.
3. The forward price of a 200-day stock index [[Futures contract|futures contract]] when the spot index is 540, the
continuous [[Dividend yield|dividend yield]] is 1.8%, and the continuously compounded risk-free rate is 7%
(with a flat [[Yield curve|yield curve]]) is closest to:

### A. 545.72.


### B. 555.61.


### C. 568.08.

4. An analyst who mistakenly ignores the dividends when valuing a short position in a forward
contract on a stock that pays dividends will most likely:
A. overvalue the position by the present value of the dividends.
B. undervalue the position by the present value of the dividends.
C. overvalue the position by the future value of the dividends.
5. A portfolio manager owns Macrogrow, Inc., which is currently trading at $35 per share. She
plans to sell the stock in 120 days, but is concerned about a possible price decline. She
decides to take a short position in a 120-day forward contract on the stock. The stock will
pay a $0.50 per share dividend in 35 days and $0.50 again in 125 days. The risk-free rate is
4%. The value of the trader’s position in the forward contract in 45 days, assuming in 45 days
the stock price is $27.50 and the risk-free rate has not changed, is closest to:


### A. $7.17.


### B. $7.50.


### C. $7.92.


## Module 28.3: Pricing and Valuation of Fixed Income Forwards


> **LOS 28.d:** Describe how fixed-income forwards and futures are priced, and calculate and
interpret their no-arbitrage value.

Forwards and Futures on Fixed Income Securities
In order to calculate the no-arbitrage forward price on a coupon-paying bond, we can use
the same formula as we used for a dividend-paying stock or portfolio, simply substituting
the present value of the expected coupon payments (PVC) over the life of the contract for
PVD, or the future value of the coupon payments (FVC) for FVD, to get the following
formulas:

The value of the forward contract prior to expiration is as follows:

If given the current forward price (FPt) on the same underlying and with the same
maturity:

In our examples, we assume that the spot price of the underlying coupon-paying bond
includes [[Accrued interest|accrued interest]]. For fixed income contracts, use a 365-day basis to calculate T if
the contract maturity is given in days.

### Example: Calculating the price of a forward on a fixed income security


Calculate the price of a 250-day forward contract on a 7% U.S. Treasury bond with a spot
price of $1,050 (including [[Accrued interest|accrued interest]]) that has just paid a coupon and will make
another coupon payment in 182 days. The annual risk-free rate is 6%.
Answer:
Remember that U.S. Treasury bonds make semiannual coupon payments, so:

The forward price of the contract is therefore:


### Example: Calculating the value of a forward on a fixed income security


After 100 days, the value of the bond in the previous example is $1,090. Calculate the
value of the forward contract on the bond to the long position, assuming the risk-free
rate is 6.0%.
Answer:
There is only one coupon remaining (in 82 days) before the contract matures (in 150
days), so:

If given the forward price directly, the value (to the long party) is simply the present value
of the difference between the current forward price and the original, locked-in forward
price.

### Example: Value of a fixed-income forward contract after inception


Louise Michelle entered into a 250-day forward contract on a 7% U.S. Treasury bond at a
forward price of $1057.37. 100 days later, the forward price has changed to $1081.04.
The risk-free rate is 6%.
Calculate the value to Michelle of the forward contract.
Answer:

Bond futures contracts often allow the short an option to deliver any of several bonds,
which will satisfy the delivery terms of the contract. This is called a delivery option and is
valuable to the short. Each bond is given a conversion factor that is used to adjust the
long’s payment at delivery so the more valuable bonds receive a larger payment. These
factors are multipliers for the [[Futures price|futures price]] at settlement. The long pays the [[Futures price|futures price]] at
expiration, multiplied by the conversion factor (CF).
Bond prices in some countries are quoted as clean prices. At settlement, the buyer actually
pays the clean price plus an [[Accrued interest|accrued interest]], or the [[Full price|full price]].

The [[Futures price|futures price]] can then be calculated as:

The quoted [[Futures price|futures price]] adjusts this price based on the conversion factor (CF) as follows:


### Example: Calculating the price of a Treasury bond futures contract


Suppose that you need to calculate the quoted futures price of a 1.2-year Treasury bond
[[Futures contract|futures contract]]. The [[Cheapest-to-deliver|cheapest-to-deliver]] bond is a 7% T-bond with exactly 10 years
remaining to maturity and a quoted price of $1,040 with a conversion factor of 1.13.
There is currently no [[Accrued interest|accrued interest]] because the bond has just paid a coupon. The
annual risk-free rate is 5%. The accrued interest on the bond at maturity of the futures
contract will be $14.
Answer:
The [[Full price|full price]] of the bond = $1,040 quoted price + $0 accrued interest = $1,040. The
semiannual coupon on a single, $1,000 face-value 7% bond is $35. A bondholder will
receive one payment 0.5 years from now (when there are 0.7 years left to maturity of
the [[Futures contract|futures contract]]) and one payment 1 year from now (when there are 0.2 years until
maturity). The future value of these coupons at the end of 1.2 years (the expiration
date) is:

The quoted futures price is then:


### Module Quiz 28.3

1. A 6% Treasury bond is trading at $1,044 (including accrued interest) per $1,000 of face
value. It will make a coupon payment 98 days from now. The [[Yield curve|yield curve]] is flat at 5% over the
next 150 days. The forward price per $1,000 of face value for a 120-day forward contract, is
closest to:

### A. $1,014.52.


### B. $1,030.79.


### C. $1,037.13.


## Module 28.4: Pricing Forward Rate Agreements


> **LOS 28.c:** Describe how [[Interest rate|interest rate]] forwards and futures are priced, and calculate and
interpret their no-arbitrage value.

Warm-Up: MRR-Based Loans and [[Forward rate|forward rate]] Agreements
Eurodollar deposit is the term for deposits in large banks outside the United States
denominated in U.S. dollars. The lending rate on dollar-denominated loans between banks
is based on the secured overnight funding rate (SOFR), hereafter referred to generically as
the MRR (“market reference rate”). It is quoted as an annualized rate based on a 360-day
year. In contrast to T-bill discount yields, MRR is an add-on rate, like a yield quote on a
short-term [[Certificate of deposit|certificate of deposit]].

### Example: MRR-based loans


Compute the amount that must be repaid on a $1 million loan for 30 days if 30-day MRR
is quoted at 6%.
Answer:
The add-on interest is calculated as $1 million × 0.06 × (30 / 360) = $5,000. The borrower
would repay $1,000,000 + $5,000 = $1,005,000 at the end of 30 days.
The long position in a [[Forward rate]] agreement (FRA) is the party that is effectively
borrowing money (long the loan, with the contract price being the interest rate on the
loan). If the floating rate at contract expiration is above the rate specified in the forward
agreement, the long position in the contract can be viewed as the right to borrow at belowmarket rates, and the long will receive a payment. If the floating rate at the expiration date
is below the rate specified in the forward agreement, the short will receive a cash payment
from the long. (The right to lend at above-market rates has a positive value.)

> [!pnote] Professor's Note
> ***We say “can be viewed as” because an FRA is settled in cash, so there is no***
> ***requirement to lend or borrow the amount stated in the contract. For this***
> ***reason, the creditworthiness of the long position is not a factor in the***
> ***determination of the interest rate on an FRA. However, to understand the***
> ***pricing and calculation of value for an FRA, viewing the contract as a***
> ***commitment to lend or borrow at a certain interest rate at a future date is***
> ***helpful.***
> ***The notation for FRAs is unique. There are two numbers associated with an FRA: the***
> ***number of months until the contract expires, and the number of months until the***
> ***underlying loan is settled. The difference between these two is the maturity of the***
>
> ***underlying loan. For example, a 2 × 3 FRA is a contract that expires in two months (60***
> ***days), and the underlying loan is settled in three months (90 days). The underlying rate is 1month (30-day) MRR on a 30-day loan in 60 days. See Figure 28.3.***
>
> *****Figure 28.3: Illustration of a 2 × 3 FRA*****
>
>
> ***Pricing FRAs***
> ***There are three important things to remember about FRAs when we’re pricing and valuing***
> ***them:***
> ***1. MRR rates in the Eurodollar market are [[Add-on rates|add-on rates]] and are always quoted on a 30/360***
> ***day basis in annual terms. For example, if the MRR quote on a 30-day loan is 6%, the***
> ***actual unannualized monthly rate is 6% × (30/360) = 0.5%.***
> ***2. The long position in an FRA is, in effect, long the rate and benefits when the rate***
> ***increases.***
> ***3. Although the interest on the underlying loan won’t be paid until the end of the loan***
> ***(e.g., in three months in Figure 28.3, the payoff on the FRA occurs at the expiration of***
> ***the FRA (e.g., in two months). Therefore, the payoff on the FRA is the present value of***
> ***the interest savings on the loan (e.g., discounted one month in Figure 28.3).***
> ***The forward “price” in an FRA is actually a forward interest rate. The calculation of a***
> ***forward interest rate is presented in Level I as the computation of forward rates from spot***
> ***rates. We will illustrate this calculation with an example.***

### Example: Calculating the price of an FRA


Calculate the price of a 1 × 4 FRA (i.e., a 90-day loan, 30 days from now). The current 30day MRR is 4% and 120-day MRR is 5%.
Answer:
The actual (unannualized) rate on the 30-day loan is:

The actual (unannualized) rate on the 120-day loan is:

We wish to calculate the actual rate on a 90-day loan from day 30 to day 120:

We can annualize this rate as:

This is the no-arbitrage [[Forward rate|forward rate]]—the [[Forward rate|forward rate]] that will make the values of the
long and the short positions in the FRA both zero at the initiation of the contract.
The time line is shown in the following figure.
Pricing a 1 × 4 FRA


### Module Quiz 28.4

1. The [[Contract rate|contract rate]] (annualized) for a 3 × 5 FRA if the current 60-day rate is 4%, the current
90-day rate is 5%, and the current 150-day rate is 6%, is closest to:

### A. 6.0%.


### B. 6.9%.


### C. 7.4%.

2. The CFO of Yellow River Company wishes to hedge borrowing costs on a 90-day loan that
starts in 90 days. The current [[Term structure]] indicates the following: 30-day MRR is 4.5%,
90-day MRR is 4.7%, and 180-day MRR is 4.9%.
The appropriate hedging position to take, and the corresponding fair market rate, would best
be described as:
A. long 3 × 3 FRA at a rate of 4.48%.
B. long 3 × 6 FRA at a rate of 4.48%.
C. long 3 × 6 FRA at a rate of 5.02%.


## Module 28.5: Valuation of Forward Rate Agreements

Valuing an FRA at Maturity
To understand the calculation of the value of the FRA after the initiation of the contract,
recall that in the previous example the long in the FRA has the “right” to borrow money 30
days from inception for a period of 90 days at the [[Forward rate|forward rate]]. If interest rates increase
(specifically the 90-day forward [[Contract rate|contract rate]]), the long will profit as the contract has fixed
a borrowing rate below the now-current market rate. These “savings” will come at the end
of the loan term, so to value the FRA we need to take the present value of these savings.
An example incorporating this fact will illustrate the [[Cash settlement|cash settlement]] value of an FRA at
expiration.

### Example: Calculating the value of an FRA at maturity (i.e., cash payment at


settlement)

Continuing the prior example for a 1 × 4 FRA, assume a [[Notional principal|notional principal]]al|principal]] of $1 million.
Suppose that, at contract expiration, the 90-day rate has increased to 6%, which is above
the [[Contract rate|contract rate]] of 5.32%. Calculate the value of the FRA at maturity, which is equal to
the cash payment at settlement.
Answer:
The interest savings at the end of the loan term (compared to the market rate of 6%) will
be:

The present value of this amount at the FRA settlement date (90 days prior to the end of
the loan term) discounted at the current rate of 6% is:

This will be the [[Cash settlement|cash settlement]] payment from the short to the long at the expiration of
the contract. Note that we have discounted the savings in interest at the end of the loan
term by the market rate of 6% that prevails at the contract settlement date for a 90-day
term, as shown in the following figure.
Valuing a 1 × 4 FRA at Maturity

Valuing an FRA Before Maturity
To value an FRA before the settlement date, we need to know the number of days that
have passed since the initiation of the contract. For example, let’s suppose we want to
value the same 1 × 4 FRA 10 days after initiation. Originally, it was a 1 × 4 FRA, which
means the FRA now expires in 20 days. The calculation of the “savings” on the loan will be
the same as in our previous example, except that we need to use the “new” FRA price that
would be quoted on a contract covering the same period as the original “loan.” In this case
the “new” FRA price is the now-current market [[Forward rate|forward rate]] for a 90-day loan made at the
settlement date (20 days in the future). Also, we need to discount the interest savings
implicit in the FRA back 110 days (i.e., an extra 20 days) instead of 90 days as we did for the
value at the settlement date.

### Example: Calculating value of an FRA before settlement


Value a 5.32% 1 × 4 FRA with a [[Principal amount|principal amount]] of $1 million 10 days after initiation if
110-day MRR is 5.9% and 20-day MRR is 5.7%.
Answer:
Step 1: Find the “new” FRA price on a 90-day loan 20 days from today. This is the current
90-day forward rate at the settlement date, 20 days from now.

Step 2: Calculate the interest difference on a $1 million, 90-day loan made 20 days from
now at the forward rate calculated previously compared to the FRA rate of 5.32%.

Step 3: Discount this amount at the current 110-day rate.

Valuing a 1 × 4 FRA Before Settlement


> [!pnote] Professor's Note
> ***I have tried to explain these calculations in such a way that you can value an***
> ***FRA at any date from initiation to settlement using basic tools that you already***
> ***know. Once you understand where the value of an FRA comes from (the***
> ***interest savings on a loan to be made at the settlement date) and when this***
> ***value is to be received (at the end of the loan), you can calculate the present***
> ***value of these savings even under somewhat stressful test conditions. Just***
> ***remember that if the rate in the future is less than the FRA rate, the long is***
> ***“obligated to borrow” at above-market rates and will have to make a payment***
> ***to the short. If the rate is greater than the FRA rate, the long will receive a***
> ***payment from the short.***
>
> ***Futures Contracts***
> ***Futures contracts are very much like the forward contracts except that they trade on***
> ***organized [[Exchanges|exchanges]]. Each exchange has a [[Clearinghouse|clearinghouse]]. The [[Clearinghouse|clearinghouse]] guarantees***
> ***that traders in the futures market will honor their obligations. The [[Clearinghouse|clearinghouse]] does this***
> ***by splitting each trade once it is made and acting as the opposite side of each position. To***
> ***safeguard the [[Clearinghouse|clearinghouse]], the exchange requires both sides of the trade to post margin***
> ***and settle their accounts on a daily basis. Thus, the margin in the futures markets is a***
> ***performance guarantee.***
> ***[[Marking to market|Marking to market]] is the process of adjusting the margin balance in a futures account each***
> ***day for the change in the value of the contract from the previous trading day, based on the***
> ***[[Settlement price|settlement price]].***
> ***The pricing relationship discussed earlier also generally applies to futures contracts as well***
> ***(see for example, our earlier discussion on Treasury bond [[Futures contract|futures contract]]). Like forward***
> ***contracts, futures contracts have no value at contract initiation. Unlike forward contracts,***
> ***futures contracts do not accumulate value changes over the term of the contract. Since***
> ***futures accounts are marked to market daily, the value after the margin deposit has been***
> ***adjusted for the day’s gains and losses in contract value is always zero. The futures price at***
> ***any point in time is the price that makes the value of a new contract equal to zero. The***
> ***value of a [[Futures contract|futures contract]] strays from zero only during the trading periods between the***
> ***times at which the account is marked to market:***
>
> ***If the futures price increases, the value of the long position increases. The value is set back***
> ***to zero by the mark-to-market at the end of the mark-to-market period.***

### Module Quiz 28.5

1. Ina bank entered into a 3×6 FRA at a rate of 3% on a $10 million notional 30 days ago.
Current MRR [[Term structure|term structure]] is as follows:

The value of the long position in the FRA is closest to:

### A. 14,407.


### B. 14,612.


### C. 57,678.


## Module 28.6: Pricing and Valuation of Interest Rate Swaps


> **LOS 28.e:** Describe how interest rate swaps are priced, and calculate and interpret their
no-arbitrage value.

The distinction between the price and the value of a swap is the same one we made for
forward contracts. Remember that the price of a forward contract is the forward rate that
yields a zero value for the contract at initiation. After contract initiation, as rates or prices
change, the contract will likely have value to either the long or the short.
Consider an [[Interest rate swap]]. One party agrees to pay floating (borrow at the floating
rate) and receive fixed (lend at a fixed rate). At initiation of the swap, the fixed rate is
selected so that the present value of the floating-rate payments is equal to the present
value of the fixed-rate payments, which means the swap value is zero to both parties. This
fixed rate is called the [[Swap rate]] or the swap fixed rate. Determining the [[Swap rate|swap rate]] is
equivalent to “pricing” the swap.
As short-term rates (and expected future short-term rates) change over the term of the
swap, the value of the swap to one of the parties will be positive. The swap position is an
asset to that party.
If market interest rates increase during the life of the swap, the swap will take on a positive
value from the perspective of the fixed-rate payer. The value of the [[Swap contract|swap contract]] to the
other party (the pay-floating side) will thus be negative.

Computing the Swap Fixed Rate
The swap fixed rate is derived from the MRR curve corresponding to the swap tenor.
Consider a two-year, semiannual [[Interest rate swap|interest rate swap]]. The swap fixed rate underlying this
swap will be determined based on the MRR rates corresponding to the four settlement
dates of this swap.
Using those four MRRs, we calculate the discount factors (Zs) for each.

The periodic swap fixed rate SFR(periodic) can then be calculated as:


### Example: Calculating the fixed rate on a swap with quarterly payments


Annualized MRR [[Spot rates|spot rates]] today are:

You’re analyzing a 1-year swap with quarterly payments and a [[Notional principal|notional principal]]al|principal]]al amount|[[Principal|principal]] amount]]
of $5,000,000. Calculate:
The fixed rate in percentage terms.
The quarterly fixed payments in $.
The first net payment.
Answer:
First calculate the discount factors. Don’t forget to convert from annualized rates to perperiod rates.


> [!pnote] Professor's Note
> ***It is likely that on the exam you will be given a table of discount factors to***
> ***use in pricing a swap, as in the next example. We’ve provided the***
> ***calculations here so you know where the discount factors come from.***
> ***The quarterly fixed rate on the swap is:***
>
> ***The quarterly fixed-rate payments, assuming a [[Notional principal|notional principal]] of $5,000,000, are:***
> ***$5,000,000 × 0.011 = $55,000***
> ***The fixed rate on the swap in annual terms is:***
>
> ***We have priced a swap in which one side pays quarterly MRR and the other side pays***
> ***4.4% fixed annually (1.1% quarterly).***
> ***The first floating rate payment will be based on the 90-day rate known at inception (i.e.,***
> ***3%). So the first net payment of 1.4% adjusted for quarterly time interval will be paid by***
> ***the fixed-rate payer:***
> ***(0.014) × (90/360) × 5,000,000 = $17,500***
> ***The amount of the first net payment will simply be the difference between the periodic***
> ***fixed payment and the first floating-rate payment:***
> ***$55,000 – $17,500 = $37,500***
> ***Thus, the first net payment will be $37,500 paid by the fixed rate payer.***
>
> ***Calculating the [[Market value|Market Value]] of an [[Interest rate swap|Interest Rate Swap]]***
> ***For the purpose of the exam, we are only responsible for [[Valuation|valuation]] of an [[Interest rate swap|interest rate swap]]***
> ***on settlement dates (after settlement has occurred), and not between settlement dates.***
> ***After the initiation of an [[Interest rate swap|interest rate swap]], the swap will take on a positive or negative***
> ***value as interest rates change. The party that is the fixed-rate payer benefits if rates***
> ***increase because they are paying the older (and lower) fixed rate and receiving the newer***
> ***(and higher) floating rate. Similarly, the fixed-rate receiver benefits if rates decrease***
> ***because they are receiving the older (and higher) fixed rate while paying a newer (and***
> ***lower) floating rate. The value is calculated as present value of the difference in payments***
> ***(under the new current rate, relative to the payments under the older, locked-in rate).***

### Example: Valuing a swap on payment date


Let’s continue our previous example of a one-year, quarterly settlement, $5 million
notional swap with a swap fixed rate at initiation of 4.4%. Suppose that after 180 days,
the MRR [[Term structure|term structure]] is flat at 3.5% over the next year. Calculate the value of the
swap to the fixed-rate receiver.
Answer:
Because the MRR [[Term structure|term structure]] is flat at 3.5%, the new swap fixed rate must be 3.5%.
At t = 180, there are two more settlement dates remaining: 90 and 180 days in the
future.


### Module Quiz 28.6

1. Consider a one-year, quarterly settlement interest rate swap. Annualized MRR [[Spot rates|spot rates]] and
the present value factors today are the following.

The annualized [[Swap rate|swap rate]] is closest to:

### A. 1.27%.


### B. 2.54%.


### C. 5.08%.

Use the following information to answer Questions 2 and 3.
Two parties enter into a 2-year [[Fixed-for-floating interest rate swap|fixed-for-floating interest rate swap]] with semiannual payments.
The floating-rate payments are based on MRR. The 180-, 360-, 540-, and 720-day annualized

MRR rates and present value factors are:

2. The [[Swap rate|swap rate]] is closest to:

### A. 6.62%.


### B. 6.87%.


### C. 7.03%.

3. After 180 days, the swap is marked-to-market when the 180-, 360-, and 540-day annualized
MRRs are 4.5%, 5%, and 6%, respectively. The present value factors, respectively, are 0.9780,
0.9524, and 0.9174. What is the [[Market value|market value]] of the swap per $1 [[Notional principal|notional principal]]al|principal]], and which
of the two counterparties (the fixed-rate payer or the fixed-rate receiver) would make the
payment to mark the swap to market?


## Module 28.7: Currency Swaps


> **LOS 28.f:** Describe how currency swaps are priced, and calculate and interpret their noarbitrage value.


Currency Swaps
Determining the Fixed Rate and Foreign Notional Principal
Consider two [[Currencies|currencies]], the U.S. dollar ($) and the British pound (£), where the exchange
rate is currently $2 per £ or £0.5 per $. The interest rates in a [[Currency swap]] are simply the
swap rates calculated from each country’s [[Yield curve|yield curve]] in the relevant country’s currency.
Don’t forget: With currency swaps, there are two yield curves and two swap fixed rates,
one for each currency.
The principal amounts of the fixed-rate obligations must be adjusted for the current
exchange rate. We need $2.00 to equal £1.00, so these are the notional amounts,
exchanged at the inception of the swap and returned at the termination of the swap. For

### Example: , if the notional principal amount of the $ side of the swap is $25 million, the £

notional [[Principal amount|principal amount]] will be £12.5 million.

### Example: Calculating the fixed rate and notional principal on a currency swap


In a previous example, we determined that the fixed rate on a 1-year quarterly
$5,000,000 interest rate swap, given the following set of spot MRRs, was 1.1% quarterly,
or 4.4% on an annual basis.

The comparable set of £ rates are:

The [[Current exchange rate|current exchange rate]] is £0.50 per $.
Determine the fixed rate on a 1-year £ interest rate swap. Then determine the notional £
[[Principal amount|principal amount]] and the quarterly cash flows on a Pay $ fixed, receive £ fixed currency
swap.
Answer:
First calculate the £ discount factors. Don’t forget to convert from annualized rates to
per-period rates.

The quarterly fixed rate on the £ swap is:

The fixed rate on the £ swap in annual terms is:

The notional £ principal amount of the swap would be:

At the initiation of the swap, we would exchange £2,500,000 for $5,000,000. We would
pay 1.1% quarterly on the $5,000,000 notional principal ($55,000) and receive 1.7% on

£2,500,000 quarterly (£42,500). At the end of one year, we would exchange the original
principal amounts.
The value to any party in a [[Currency swap|currency swap]] is the present value of the cash flows they expect
to receive minus the present value of the cash flows they are obligated to pay.

### Example: Calculating the value of a currency swap after initiation


Use the data on the $ and £ interest rate swaps in the previous examples to answer this
question. After 300 days, the 60-day $ interest rate is 5.4%, the 60-day £ interest rate is
6.6%, and the exchange rate is £0.52 per $. Calculate the value of a $5,000,000 swap to
the counterparty that receives $ fixed and pays £ fixed.
Answer:
Recall that the $ fixed rate was calculated as 4.4% (or 1.1% per quarter) and the £ fixed
rate was calculated as 6.8% (or 1.7% per quarter). After 300 days, the only cash flows
remaining are the last interest payments and the principal payments in 60 days. We
want to find the present value of those cash flows, so we need the 60-day discount
factors based on the current 60-day rates:

First calculate the value after 300 days of the $ fixed payments. It is equivalent to the
value of a $5,000,000 bond that matures in 60 days and makes a coupon payment in 60
days of $55,000 ($5,000,000 × 0.011). The value in $ of the $ fixed side is the present
value of $5,055,000 discounted using the 60-day $ [[Discount factor|discount factor]] of 0.99108:
value of $ fixed side (in $) = 0.99108 × $5,055,000 = $5,009,909
Next, calculate the value after 300 days of the £ fixed payments. The value in £ of the £
fixed side is the present value of £2,542,500 discounted using the 60-day £ discount
factor of 0.98912:
value of £ fixed side (in £) = 0.98912 × £2,542,500 = £2,514,838
This last step is to convert that amount into $ at the current spot exchange rate of £0.52
per $, to find the value of the £ fixed side in $:
value of £ fixed side (in $) = £2,514,838 / 0.52 = $4,836,227
Finally, the value of the receive $ fixed, pay £ fixed side of the swap is equal to the value
of the $ fixed side minus the £ fixed side, or $5,009,909 − $4,836,227 = $173,682.


### Module Quiz 28.7

1. The [[Current exchange rate|current exchange rate]] is 0.70 USD/CAD. In a US$1 million fixed-for-floating currency
swap, the party that is entering the swap to hedge an existing exposure to a C$-denominated
fixed-rate liability will:
A. receive $1 million at the termination of the swap.
B. pay a fixed rate based on the yield curve in the United States.
C. receive a fixed rate based on the yield curve in Canada.
2. A bank entered into a 1-year [[Currency swap|currency swap]] with quarterly payments 200 days ago by
agreeing to swap $1,000,000 for €800,000. The bank agreed to pay an annual fixed rate of
5% on the €800,000 and receive a fixed rate of 4.2% on the $1,000,000. Current USD and
euro MRRs and present value factors are shown in the following table.

The current spot exchange rate is €0.75 per $1.00. The value of the swap to the bank today is
closest to:

### A. –$64,888.


### B. –$42,049.


### C. $42,049.


## Module 28.8: Equity Swaps


> **LOS 28.g:** Describe how equity swaps are priced, and calculate and interpret their noarbitrage value.


Equity Swaps
To price an N-period pay-fixed [[Equity swap|equity swap]], we can use the same formula as for a plain
vanilla swap:

To value this swap, consider two scenarios:
1. [[Valuation|Valuation]] on settlement date (immediately after settlement): We can continue to use
the valuation formula discussed for valuation of interest rate swaps.
2. Valuation between settlement dates (for equity swaps, this is covered in the curriculum):
We calculate the values of the two sides of the swap separately as shown in the
following example.


### Example: Valuing a pay-fixed, receive-equity-returns swap


A $10 million principal, one-year, quarterly settlement [[Equity swap|equity swap]] has a fixed rate of
6.05%. The index at inception is 985. After 30 days have passed, the index stands at 996
and the [[Term structure|term structure]] of MRR is 6%, 6.5%, 7%, and 7.5% for terms of 60, 150, 240, and
330 days, respectively. The respective discount factors are 0.99010, 0.97363, 0.95541,
and 0.93567. Calculate the value of the swap to the fixed-rate payer on Day 30.
Answer:

The value of $10,000,000 invested in the index after 30 days is:

From the standpoint of the fixed-rate payer, the value of the swap after 30 days is:

A swap of returns on two different stocks can be viewed as buying one stock (receiving the
returns) and shorting an equal value of a different stock (paying the returns). There is no
“pricing” at swap initiation, and we can value the swap at any point in time by taking the
difference in returns (since the last [[Payment date|payment date]]) times the notional principal.

### Example: Valuing a “one-equity-return-for-another” swap


An investor is the Stock A returns payer (and Stock B returns receiver) in a $1 million
quarterly-pay swap. After one month, Stock A is up 1.3% and Stock B is down 0.8%.
Calculate the value of the swap to the investor.
Answer:
The investor pays the Stock A returns and receives Stock B returns. However, the Stock B
returns are negative, so he pays those as well:


### Module Quiz 28.8

1. A bank entered into a $5,000,000, 1-year [[Equity swap|equity swap]] with quarterly payments 300 days ago.
The bank agreed to pay an annual fixed rate of 4% and receive the return on an international
equity index. The index was trading at 3,000 at the end of the third quarter, 30 days ago. The
current 60-day MRR rate is 3.6%, the [[Discount factor|discount factor]] is 0.9940, and the index is now at 3,150.
The value of the swap to the bank is closest to:

### A. –$257,795.


### B. –$114,676.


### C. $230,300.


> [!abstract] Key Concepts
> LOS 28.a

The calculation of the forward price for an equity forward contract is different because the
periodic dividend payments affect the no-arbitrage price calculation. The forward price is
reduced by the future value of the expected dividend payments; alternatively, the spot
price is reduced by the present value of the dividends.

The value of an equity forward contract to the long is the spot equity price minus the
present value of the forward price minus the present value of any dividends expected over
the term of the contract:

If given the current forward price (FPt) on the same underlying and with the same
maturity:

We typically use the [[Continuous time|continuous time]] versions to calculate the price and value of a forward
contract on an equity index using a continuously compounded [[Dividend yield|dividend yield]].

LOS 28.b

Forward price = spot price + net [[Cost of carry|cost of carry]]
For a security without underlying cash flows:

$$
FP = S0 (1+Rf)T
$$

For a security with underlying cash flows:

$$
FP = (S0 – PVC)  \times  (1+Rf)T
$$

where PVC = present value of the cash flow on the security.
LOS 28.c

The “price” of an FRA is the implied forward rate for the period beginning when the FRA
expires to the maturity of the underlying “loan.”
The value of an FRA at maturity is the interest savings to be realized at maturity of the
underlying “loan” discounted back to the date of the expiration of the FRA at the current

MRR. The value of an FRA before maturity is the interest savings estimated by the implied
forward rate discounted back to the valuation date at the current MRR.
LOS 28.d

For forwards on coupon-paying bonds, the price is calculated as the spot price minus the
present value of the coupons times the quantity one plus the risk-free rate:
The value of a forward on a coupon-paying bond t years after inception is the spot bond
price minus the present value of the forward price minus the present value of any coupon
payments expected over the term of the contract:

If given the current forward price (FPt) on the same underlying and with the same
maturity:

In a futures contract, the short may have delivery options (to decide which bond to
deliver). In such a case, the quoted futures price is adjusted using the conversion factor for
the [[Cheapest-to-deliver|cheapest-to-deliver]] bond:

LOS 28.e

The fixed periodic-rate on an n-period swap at initiation (as a percentage of the principal
value) can be calculated as:

The value of a swap on a [[Payment date|payment date]] has a simple relationship to the difference between
the new swap fixed rate and the original swap fixed rate:

LOS 28.f

The fixed rates in a fixed-for-fixed [[Currency swap|currency swap]] are determined using the yield curves for
the relevant [[Currencies|currencies]]. The notional principal amounts in the two [[Currencies|currencies]] are of equal
value, based on the exchange rate at inception of the swap. Use the difference in values to
value the [[Currency swap|currency swap]]. The conversion of value from one of the two currencies into the
common currency is based on the exchange rate on the valuation date.
LOS 28.g

The fixed-rate side of an [[Equity swap|equity swap]] is priced and valued just like an interest rate swap.
The equity side can be valued by multiplying the [[Notional amount|notional amount]] of the contract by 1 + the
percentage equity appreciation since the last [[Payment date|payment date]]. Use the difference in values to
value the swap.

### Answer Key For Module Quizzes

Module Quiz 28.1, 28.2
1. C The dividend in 65 days occurs after the contract has matured, so it’s not relevant to
computing the forward price.

(Module 28.2, LOS 28.a)
2. B

(Module 28.2, LOS 28.a)
3. B Use the [[Dividend rate|dividend rate]] as a continuously compounded rate to get:
(Module 28.2, LOS 28.a)
4. B The value of the long position in a forward contract on a stock at time t is:

If the dividends are ignored, the long position will be overvalued by the present
value of the dividends; that means the short position (which is what the question
asks for) will be undervalued by the same amount. (Module 28.2, LOS 28.a)

5. A The dividend in 125 days is irrelevant because it occurs after the forward contract
matures.

(Module 28.2, LOS 28.a)
Module Quiz 28.3
1. B Remember that U.S. Treasury bonds make semiannual coupon payments, so:

The forward price of the contract is therefore:

(LOS 28.d)
Module Quiz 28.4
1. C The actual (unannualized) rate on the 90-day loan is:

The actual rate on the 150-day loan is:
The price of the 3 × 5 FRA (the 60-day forward rate in 90 days) is:
(LOS 28.c)
2. C A 3 × 6 FRA expires in 90 days and is based on 90-day MRR, so it is the appropriate
hedge for 90-day MRR 90 days from today. The rate is calculated as:

(LOS 28.c)

Module Quiz 28.5
1. A The original FRA will now be a 2×5 FRA (as 1 month has passed).

(LOS 28.c)
Module Quiz 28.6
1. C The quarterly fixed rate on the swap is:
The fixed rate on the swap in annual terms is:
(LOS 28.e)
2. A Calculate the [[Swap rate|swap rate]]:

(LOS 28.e)
3. A Based on new rates,

Because the value is negative, payer makes the payment. (LOS 28.e)
Module Quiz 28.7
1. C A receive-fixed C$ position will hedge the liability risk. That party would receive $1
million at swap inception (in exchange for
) and pay it back at
termination. The fixed-rate received will be calculated using the yield curve in
Canada at the initiation of the swap. Because this is a fixed-for-floating currency
swap, the receive-fixed position will pay a floating rate based on the U.S. yield curve.
(LOS 28.f)
2. A coupon on $ fixed side = $1,000,000 × (0.042 / 4) = $10,500

(LOS 28.f)
Module Quiz 28.8
1. C The quarterly 4% fixed-rate payment in 60 days will be in the amount of: $5,000,000 ×
(4%/4) = $50,000
So the total cash flow at that time is $50,000 + $5,000,000 = $5,050,000.

(LOS 28.g)


---

# Reading 29 — Valuation of Contingent Claims


> [!tip] Exam Focus
> This topic review covers the valuation of options. Candidates need to be able to calculate
> value of an option using the [[Binomial tree]] framework and should also understand the
> inputs into the Black-Scholes model and how they influence the value of an option. While
> this topic review is somewhat quantitative, candidates need to understand the material
> conceptually as well. This reading has a lot of testable material.

> [!pnote] Professor's Note
> ***We cover these three LOS here together, for ease of exposition.***

## Module 29.1: The Binomial Model


> **LOS 29.a:** Describe and interpret the binomial option valuation model and its
component terms.


> **LOS 29.b:** Describe how the value of a [[European option|European option]] can be analyzed as the present
value of the option’s expected payoff at expiration.

> **LOS 29.d:** Calculate the no-arbitrage values of European and American options using a twoperiod [[Binomial model|binomial model]].

[[Binomial model|Binomial Model]]
A [[Binomial model]] is based on the idea that, over the next period, the value of an asset will
change to one of two possible values (binomial). To construct a [[Binomial model|binomial model]], we need
to know the beginning asset value, the size of the two possible changes, and the
[[Probability|probability]] of each of these changes occurring.
One-Period [[Binomial model|Binomial Model]]
Consider a share of stock currently priced at $30. Suppose also that the size of the possible
price changes, and the [[Probability|probability]] of these changes occurring are as follows:

A one-period [[Binomial tree|binomial tree]] for this stock is shown in Figure 29.1. The beginning stock value
of $30 is to the left, and to the right are the two possible paths the stock can take, based
on that starting point and the size of an up- or down-move. If the stock price increases by a
factor of 1.333 (a return of 33.3%), it ends up at $40.00; if it falls by a factor of 0.75 (a
return of –25%), it ends up at $22.50.

**Figure 29.1: One-Period [[Binomial tree|Binomial Tree]]**


The probabilities of an up-move and a down-move are calculated based on the size of the
moves, as well as the risk-free rate, as:


> [!pnote] Professor's Note
> ***These up- and down-move probabilities are not the actual probabilities of upor down-moves. They are the [[Risk-neutral probabilities|risk-neutral probabilities]] that are [[Consistent|consistent]] with***
> ***investor risk-neutrality. The distinction between actual probabilities and riskneutral probabilities is not relevant for the exam.***
> ***We use the [[Expectations approach|expectations approach]] to calculate the value of an option from this binomial***
> ***tree. We do this by:***
> ***Calculating the payoff of the option at maturity in both the up-move and down-move***
> ***states.***
> ***Calculating the [[Expected value|expected value]] of the option in one year as the [[Probability|probability]]-weighted***
> ***average of the payoffs in each state.***
> ***Discounting the [[Expected value|expected value]] back to today at the risk-free rate.***

### Example: Calculating call option value with a one-period binomial tree


Calculate the value today of a one-year [[Call option]] on a stock that has an [[Exercise price]]
of $30. Assume that the periodically compounded (as opposed to continuously
compounded) risk-free rate is 7%, the current value of the stock is $30, the up-move
factor is 1.333, and the down move factor is 0.75.

Answer:
First, we have to calculate the probabilities:

Next, determine the option payoffs in each state. If the stock moves up to $40, the call
option with an [[Exercise price|exercise price]] of $30 will pay off $10. If the stock moves down to $22.50,
the [[Call option|call option]] will be worthless. The option payoffs are illustrated in the following
figure.
Let the stock values for the up-move and down-move be S+ and S– and for the call
values, C+ and C–.
With X = $30

The [[Expected value|expected value]] of the option in one period is:

The value of the option today, after discounting at the risk-free rate of 7%, is:

We can use the same framework to value a one-period [[Put option]] on the stock.

### Example: Valuing a one-period put option on a stock


Use the information in the previous example to calculate the value of a [[Put option|put option]] on
the stock that has an [[Exercise price|exercise price]] of $30.
Answer:
If the stock moves up to $40, a put option with an exercise price of $30 will be
worthless. If the stock moves down to $22.50, the put option will be worth $7.50.
The probabilities are 0.55 and 0.45 for an up- and down-move, respectively. The
[[Expected value|expected value]] of the [[Put option|put option]] in one period is thus:

The value of the option today, after discounting at the risk-free rate of 7%, is:


## Module 29.2: Two Period Binomial Model and Put-Call Parity

[[Put-call parity|put-call parity]]


[[Put option|Put option]] value can also be computed using [[Put-Call Parity]], which recognizes that the
value of a [[Fiduciary|fiduciary]]ry call|[[Fiduciary|fiduciary]] call]] (long call, plus an investment in a zero-coupon bond with a face
value equal to the [[Strike Price]]) is equal to the value of a [[Protective put|protective put]] (long stock and long
put):
Note that both options are on the same underlying stock have the same [[Exercise price|exercise price]], and
the same maturity.
In our previous example, PV(X) = 30 / 1.07 = $28.04. We can verify the put call parity as:

Put call parity can be used to create a synthetic instrument that replicates the desired
instrument.
For example, a synthetic call can be created by creating a portfolio that combines a long
position in the stock, a long position in a put and a short position in a zero- coupon bond
with a face value equal to the strike price (i.e., borrowing the present value of the exercise
price at the risk-free rate).


### Example: Using put-call parity


A 1-year [[Call option|call option]] on the [[Common stock|common stock]] of Cross Reef, Inc., with an [[Exercise price|exercise price]] of
$60 is trading for $8. The current stock price is $62. The risk-free rate is 4%. Calculate
the price of the [[Put option|put option]] implied by put-call parity.
Answer:
According to put-call parity, to prevent arbitrage, the price of the put option must be:

Two-Period Binomial Model
Valuing an option using a two-period binomial model requires more steps, but uses the
same method:
Calculate the stock values at the end of two periods (there are three possible outcomes,
because an up-then-down move gets you to the same place as a down-then-up move).
Calculate the three possible option payoffs at the end of two periods.
Calculate the expected option payoff at the end of two periods (t = 2) using the up- and
down-move probabilities.
Discount the expected option payoff (t = 2) back one period at the risk-free rate to find
the option values at the end of the first period (t = 1).
Calculate the expected option value at the end of one period (t = 1) using up- and downmove probabilities.
Discount the expected option value at the end of one period (t = 1) back one period at
the risk-free rate to find the option value today (t = 0).
Let’s look at an example to illustrate the steps involved.

### Example: Valuing a call option on a stock with a two-period model


Suppose you own a stock currently priced at $50 and that a two-period European call
option on the stock is available with a strike price of $45. The up-move factor is 1.25 and
the down-move factor is 0.80. The risk-free rate per period is 7%. Compute the value of
the [[Call option|call option]] using a two-period binomial model.
Answer:
First, compute the [[Probability|probability]] of an up-move and a down-move, and then compute the
theoretical value of the stock at the end of each period:

The two-period [[Binomial tree|binomial tree]] for the stock is shown in the following figure.
Two-Period [[Binomial tree|Binomial Tree]] for Stock Price

We know the value of the option at expiration in each state is equal to the stock price
minus the exercise price (or zero, if that difference is negative):

We will approach this problem by using the single-period binomial model for each
period. Using this method, we can compute the value of the [[Call option|call option]] in the up-state in
period one as follows:

The value of the call in the down-state at t = 1 is computed as:

Now we know the value of the option in both the up-state (C+) and the down-state (C–)
one period from now. To get the value of the option today, we simply apply our
methodology one more time. Therefore, bringing (C+) and (C–) back one more period to
the present, the value of the call option today is:

The binomial tree for the call option is shown here:
Two-Period Binomial Tree for Option Price


### Module Quiz 29.1, 29.2

1. Zepo, Inc., stock price is currently $80. The stock price will move up by 15% or down by 13%
each period. The value of a two-period European call option with an exercise price of $62 if
the risk-free rate is 4% per period is closest to:

### A. $19.17.


### B. $22.99.


### C. $27.11.


## Module 29.3: American Options

[[American-style|American-Style]] Options


Our discussion so far has been limited to [[European-style|European-style]] options (i.e., options that can only
be exercised at maturity). [[American-style|American-style]] options allow for exercise any point until maturity
of the option. While the early exercise feature is not valuable for call options on nondividend paying stocks, deep-in-the-money put options could benefit from early exercise.
When an investor exercises an option early, she captures only the [[Intrinsic value]] of the
option and forgoes the [[Time value|time value]]. While the [[Intrinsic value|intrinsic value]] can be invested at the risk-free
rate, the interest so earned is less than the [[Time value|time value]] in most cases. For a deep-in-the
money put option, the upside is limited (because the stock price cannot fall below zero). In
such cases, the interest on [[Intrinsic value|intrinsic value]] can exceed the option’s [[Time value|time value]].

### Example: Early exercise of a put option


Consider a stock currently trading at $50. The periodically compounded interest rate is
3%. Suppose that U = 1.3 and D = 0.80. Calculate the value of a two-period Europeanstyle put option on the stock that has an exercise price of $50. Also, determine if early
exercise would make economic sense.
Answer:
The following tree shows put option value at each of the nodes in the binomial tree.

The value of the option for the down node at t = 1 is calculated as:

The value of the option at time = 0 is calculated as:

For the down move at t = 1, the [[Exercise value|exercise value]] of the put option is $10, calculated as
Max(0, X-S) or Max(0, 50-40). Clearly, for this node, early exercise results in higher value
($10 as opposed to $9.44).
Had the option in the previous example been an [[American-style|American-style]] put option, the value
would be $5.24 as shown in Figure 29.2.

**Figure 29.2: Valuing an [[American-style|American-Style]] Put Option**


The value of the put option at time 0 can be calculated as the present value of the
expected value of the option at time t = 1.

American-style call options on dividend-paying stocks can be evaluated similarly:
determine at each node whether the [[Exercise value|exercise value]] is greater than the [[Intrinsic value|intrinsic value]] and,
if so, use that higher value. For dividend-paying stocks, the stock price falls when the stock
goes [[Ex-dividend|ex-dividend]], and it may make sense to exercise the call option before such a decline in
price.

### Module Quiz 29.3

1. An analyst has calculated the value of a 2-year European call option to be $0.80. The strike
price of the option is 100.00, and the underlying asset is a 7% annual coupon bond with
three years to maturity. The two-period binomial tree for the [[European option|European option]] is shown in

the following figure.

The value of the comparable 2-year American call option (exercisable after 1 year) with a
strike price of 100.00 is closest to:

### A. $1.56.


### B. $2.12.


### C. $3.80.


## Module 29.4: Hedge Ratio


> **LOS 29.c:** Identify an [[Arbitrage opportunity|arbitrage opportunity]] involving options and describe
the related arbitrage.


Arbitrage with a One-Period Binomial Model
Let’s revisit our original example of a single period binomial model. Recall that the call
option has a strike price equal to the stock’s current price of $30, U = 1.333, D = 0.75, and
the risk-free rate is 7%. We calculated that the probability of an up-move is 55% and that of
a down-move 45%.
If the market price of the one-period $30 call option were to be different from the $5.14
value calculated before, there would be an [[Arbitrage opportunity|arbitrage opportunity]]. This arbitrage will involve
the call option and shares of the stock. If the option is overpriced in the market, we would
sell the option and buy a fractional share of the stock for each option we sold. If the call
option is underpriced in the market, we could purchase the option and short a fractional
share of stock for each option purchased.
The fractional share of stock needed in the arbitrage trade (commonly referred to as the
[[Hedge ratio]] or delta), is calculated in the one-period model as:


### Example: Calculating arbitrage profit


In a previous example, a one-year call option on a $30 stock (exercise price = $30) was
valued at $5.14. We were given that the risk-free rate is 7%, and the up-move factor and
down-move factor are 1.333 and 0.75, respectively. If the market price of the call option

is $6.50, illustrate how this opportunity can be exploited to earn an arbitrage profit.
Assume we trade 100 call options.
Answer:
Given the up and down factors, the stock price would be $40 and $22.50 in the up and
down states respectively in one year. The call payoffs would accordingly be $10 and $0 in
up and down states, respectively. Because the option is overpriced, we will sell 100 call
options and purchase a number of shares of stock determined by the [[Hedge ratio|hedge ratio]]:

A portfolio that is long 57.14 shares of stock at $30 per share and short 100 calls at
$6.50 per call has a net cost of:

We will borrow $1,064 at 7%, and then will have to repay $1,064 × (1.07) = $1,138.48 at
the end of one year. (In an arbitrage transaction, we assume that we begin with $0.)
The values of this portfolio at maturity if the stock moves up to $40 or down to $22.50
are identical:

Profit on the portfolio at the end of one year in either state after repayment of loan =
$1,286 − $1,138.48 = $147.52.
The present value of the arbitrage profit is $147.52 / 1.07 = $137.87.
The previous calculations can be represented by the following:

Therefore, the value of the call (the arbitrage-free price)
Or equivalently,

We can value the call option using the first relationship as:

Similarly, a put option can be valued as:

And the [[Hedge ratio|hedge ratio]] based on puts is:


### Module Quiz 29.4

1. In a one-period binomial model, the [[Hedge ratio|hedge ratio]] is 0.35. To construct a riskless arbitrage
involving 1,000 call options if the option is “overpriced,” what is the appropriate portfolio?

2. A synthetic European put option is created by:
A. buying the discount bond, buying the call option, and short-selling the stock.
B. buying the call option, short-selling the discount bond, and short-selling the stock.
C. short-selling the stock, buying the discount bond, and selling the call option.


## Module 29.5: Interest Rate Options


> **LOS 29.e:** Calculate and interpret the value of an interest rate option
using a two-period binomial model.


Warm-Up: Binomial Interest Rate Trees
We can use an estimate of the [[Volatility|volatility]] of an interest rate to create a set of possible rate
paths for interest rates in the future called a [[Binomial Interest Rate Tree|binomial interest rate tree]]. The diagram in

**Figure 29.3 depicts a two-period [[Binomial Interest Rate Tree|binomial interest rate tree]].**


**Figure 29.3: Two-Period [[Binomial Interest Rate Tree|Binomial Interest Rate Tree]]**


The interest rate at each node is a one-period forward rate. Beyond the root of the tree,
there is more than one one-period forward rate for each nodal period (i.e., at Year 1, we
have two 1-year forward rates, i1,U and i1,D). The interest rates are selected so that the
(risk-neutral) probabilities of up- and down-moves are both equal to 0.5.


> [!pnote] Professor's Note
> ***You will not have to construct a tree for the exam—just be able to use the given***
> ***tree to value an interest rate option.***
>
> ***Interest Rate Options***
> ***An interest rate call option has a positive payoff when the reference rate is greater than the***
> ***exercise rate:***
> ***Interest rate call options increase in value when rates increase.***
> ***An interest rate put option has a positive payoff when the reference rate is less than the***
> ***exercise rate:***
> ***Interest rate put option values increase in value when rates decrease. Valuing interest rate***
> ***options using the binomial tree is similar to valuing stock options; the value at each node is***
> ***the present value of the expected value of the option. While MRR-based contracts pay***
> ***interest in arrears, to keep things simple, we assume that options cash settle at maturity.***

### Example: Interest rate call option valuation


Given the two-period interest rate tree shown next, what is the value of a two-period
European interest rate call option with an exercise rate of 5.50% and a notional principal
of $1 million? (Assume that options cash settle at time T = 2.)

Answer:
Given the exercise rate of 5.50%, the call option has a positive payoff for nodes C++ and
C+–.
The value of the option at node C++ can be calculated as:
[Max (0, 0.107383 – 0.055)] × $1,000,000 = $52,383
Similarly, the value at node C+– can be calculated as:
[Max (0, 0.071981 – 0.055)] × $1,000,000 = $16,981
value at node C+ = [(0.5 × 52,383) + (0.5 × 16,981)] / (1.057883) = $32,784 (note that the
[[Discount rate]] is not constant)
value at node C– = [(0.5 × 16,981) + 0] / (1.0388) = $8,173
value at node C = [(0.5 × 32,784) + (0.5 × 8,173)] / (1.03) = $19,882


## Module 29.6: Black-Scholes-Merton and Swaptions


> **LOS 29.f:** Identify assumptions of the Black–Scholes–Merton option
valuation model.


The [[Black-Scholes-Merton Model]] ([[Black-Scholes-Merton Model]]) option valuation model values options in continuous
time, but is based on the no-arbitrage condition we used in valuing options in discrete time
with a binomial model. In the binomial model, the [[Hedge portfolio|hedge portfolio]] is riskless over the next
period, and the no-arbitrage option price is the one that guarantees that the hedge
portfolio will yield the risk-free rate. To derive the BSM model, an “instantaneously”
riskless portfolio (one that is riskless over the next instant) is used to solve for the option
price.
The assumptions underlying the Black-Scholes-Merton model are:
1. The underlying asset price follows a geometric Brownian motion process. The
[[Continuously compounded return|continuously compounded return]] is normally distributed. Under this framework, change
in asset price is continuous: there are no abrupt jumps.
2. The (continuously compounded) risk-free rate is constant and known. Borrowing and
lending are both at the risk-free rate.
3. The [[Volatility|volatility]] of the returns on the underlying asset is constant and known. The price of
the underlying changes smoothly (i.e., does not jump abruptly).
4. Markets are “frictionless.” There are no taxes, no transactions costs, and no restrictions
on short sales or the use of short-sale proceeds. Continuous trading is possible, and
there are no arbitrage opportunities in the marketplace.
5. The (continuously compounded) yield on the underlying asset is constant.

6. The options are European options (i.e., they can only be exercised at expiration).

> **LOS 29.g:** Interpret the components of the Black–Scholes–Merton model as
applied to call options in terms of a leveraged position in the underlying.
The formula for valuing a [[European option|European option]] using the BSM model is:
and
where:

While the BSM model formula looks complicated, its interpretations are not:
1. The BSM value can be thought of as the present value of the expected option payoff at
expiration. For a call, that means C0 = PV {S0erTN(d1) − XN(d2)}. Similarly, for a put
option, P0 = PV {XN(–d2) − S0erTN(–d1)}.
2. Calls can be thought of as a leveraged stock investment where N(d1) units of stock are
purchased using e–rTXN(d2) of borrowed funds. (A short position in bonds can also be
interpreted as borrowing funds.) A portfolio that replicates a put option consists of a
long position in N(–d2) bonds and a short position in N(–d1) stocks.
3. N(d2) is interpreted as the [[Risk-Neutral Probability]] that a call option will expire in the
money. Similarly, N(–d2) or 1 − N(d2) is the risk-neutral probability that a put option will
expire [[In the money|in the money]].

### Example: BSM model


Stock of XZ, Inc., is currently trading at $50. Suppose that the return [[Volatility|volatility]] is 25% and
the continuously compounded risk-free rate is 3%. Calls and puts with a strike price of
$45 and expiring in 6 months (T = 0.5) are trading at $7.00 and $1.00, respectively. If
N(d1) = 0.779 and N(d2) = 0.723, calculate the value of the replicating portfolios and any
arbitrage profits on both options.

Answer:
The replicating portfolio for the call can be constructed as long 0.779 shares (0.779 ×
$50 = $38.95), and borrow 45 × e–0.03(0.5) × (0.723) = $32.05.
net cost = $38.95 − $32.05 = $6.90
Because the market price of the call is $7.00, the profitable arbitrage transaction entails
writing a call at $7.00 and buying the replicating portfolio for $6.90 to yield an arbitrage
profit of $0.10 per call.
For the put option valuation, note that N(–d1) = 1 − N(d1) = 1 − 0.779 = 0.221 and N(–d2)
= 1 − 0.723 = 0.277.
The replicating portfolio for the put option can be constructed as a long bond position of
45 × e–0.03(0.5) × (0.277) = $12.28 and a short position in 0.221 shares resulting in short
proceeds of $50 × 0.221 or $11.05.
net cost = $12.28 – $11.05 = $1.23
Because the market price of the put option is $1.00, arbitrage profits can be earned by
selling the replicating portfolio and buying puts, for an arbitrage profit of $0.23 per put.


> **LOS 29.h:** Describe how the Black–Scholes–Merton model is used to value
European options on equities and currencies.

Options on Dividend Paying Stocks
So far we have assumed that the underlying stock does not pay dividends. If it does, we can
adjust the model using a lowercase delta (δ) to represent the dividend yield, as follows:

Note that S0e–δT is the stock price, reduced by the present value of any dividends expected
to be paid during the option’s life.
The put-call parity relation must also be modified if the stock pays dividends:

Options on Currencies
We can also use the Black-Scholes-Merton model to value foreign exchange options. Here,
the underlying is the spot exchange rate instead of a stock price.

The value of an option on a currency can be thought of as being made up of two
components, a bond component and a foreign exchange component. The value can be
calculated as:
and

For currencies, the carry benefit is not a dividend but rather interest earned on a deposit of
the [[Foreign currency|foreign currency]]. The spot exchange rate, S0, is discounted at the base or foreign
currency interest rate, and the bond component, e–r(P)TX, is the exercise exchange rate
discounted at the price (or [[Domestic currency|domestic currency]]) interest rate.

> **LOS 29.i:** Describe how the Black model is used to value European options
on futures.

The Black Model
If we ignore the mark-to-market feature of the futures contract, The Black model can be
used to price European options on forwards and futures:

Note that the Black model is just the BSM model with substituted

for S0.

Analogous to the interpretations of the BSM model, an option on futures can be thought of
as follows:
The value of a call option on futures is equal to the value of a portfolio with a long
futures position (the PV of the futures price multiplied by N(d1)) and a short bond
position (the PV of the exercise price multiplied by N(d2)).
The value of a put option is equal to the value of a portfolio with a long bond and a short
futures position.
The value of a call can also be thought of as the present value of the difference between
the futures price (adjusted by N(d1)) and the exercise price (adjusted by N(d2)).


> **LOS 29.j:** Describe how the Black model is used to value European interest
rate options and European swaptions.

Interest Rate Options
Interest rate options are options on forward rates (or options on FRAs). A call option on an
FRA gains when rates rise, and a put option on an FRA gains when rates fall. Interest rates
are fixed in advance (i.e., at the beginning of the loan term) and [[Settled in arrears|settled in arrears]] (i.e., paid
at maturity of the loan). While FRAs generally use a 30/360 convention, options on FRAs
use an actual/365 convention.
Consider an interest rate call option on an (M×N) FRA expiring in M months that has a
strike rate of X. The underlying is an (N−M) month forward rate. A call option on this FRA
can be valued as:

Equivalencies in Interest Rate [[Derivative|Derivative]] Contracts
Combinations of interest rate options can be used to replicate other contracts, for example:
1. A long interest rate call and a short interest rate put (with exercise rate = current FRA
rate) can be used to replicate a long FRA (i.e., a forward contract to receive a floating
rate and pay a fixed rate).
2. Similarly, if the exercise rate = the current FRA rate, a short interest rate call and long
interest rate put can be combined to replicate a short FRA position (i.e., a pay-floating,
receive-fixed forward contract).
3. A series of interest rate call options with different maturities and the same exercise price
can be combined to form an interest rate cap. (Each of the call options in an interest rate
cap is known as a caplet.) A floating rate loan can be hedged using a long interest rate
cap.
4. Similarly, an interest rate floor is a portfolio of interest rate put options, and each of
these puts is known as a floorlet. Floors can be used to hedge a long position in a
floating rate bond.
5. If the exercise rate on a cap and floor is same, a long cap and short floor can be used to
replicate a payer swap.
6. Similarly, a short cap and long floor can replicate a receiver swap.
7. If the exercise rate on a floor and a cap are set equal to a market swap fixed rate, the
value of the cap will be equal to the value of the floor.

Swaptions
A [[Swaption|swaption]] is an option that gives the holder the right to enter into an interest rate swap. A
payer swaption is the right to enter into a specific swap at some date in the future at a

predetermined rate as the fixed-rate payer. As interest rates increase, the right to take the
pay-fixed side of a swap (a payer swaption) becomes more valuable. The holder of a payer
swaption would exercise it and enter into the swap if the market rate is greater than the
exercise rate at expiration.
A receiver swaption is the right to enter into a specific swap at some date in the future as
the fixed-rate receiver (i.e., the floating-rate payer) at the rate specified in the swaption. As
interest rates decrease, the right to enter the receive-fixed side of a swap (a receiver
swaption) becomes more valuable. The holder of a receiver swaption would exercise if
market rates are less than the exercise rate at expiration.
A swaption is equivalent to an option on a series of cash flows (annuity), one for each
settlement date of the underlying swap, equal to the difference between the exercise rate
on the swaption and the market swap fixed rate.
If PVA represents the present value of such an annuity, the value of a payer swaption using
the Black model can be calculated as:

The value of a payer swaption is essentially the present value of the expected option
payoff:
Similarly, the value of a receiver swaption (which we’ll call “REC”) can be calculated as:

Equivalencies
A receiver swap can be replicated using a long receiver swaption and a short payer
swaption with the same exercise rates. Conversely, a payer swap can be replicated using a
long payer swaption and short receiver swaption with the same exercise rates. If the
exercise rate is set such that the values of the payer and receiver swaptions are equal, then
the exercise rate must be equal to the market forward swap fixed rate.
A long [[Callable bond]] can be replicated using a long option-free bond plus a short receiver
swaption.

### Module Quiz 29.5, 29.6

1. Compare the call and put prices on a stock that doesn’t pay a dividend (NODIV) with
comparable call and put prices on another stock (DIV) that is the same in all respects except
it pays a dividend. Which of the following statements is most accurate? The price of a:

A. DIV call will be less than the price of NODIV call.
B. NODIV call will equal the price of NODIV put.
C. NODIV put will be greater than the price of DIV put.
2. Which of the following is not an assumption underlying the Black-Scholes-Merton options
pricing model?
A. The underlying asset does not generate cash flows.
B. Continuously compounded returns on the underlying are normally distributed.
C. The option can only be exercised at maturity.
Use the following information to answer Questions 3 and 4.
Stock ABC trades for $60 and has 1-year call and put options written on it with an exercise price
of $60. ABC pays no dividends. The annual [[Standard deviation|standard deviation]] estimate is 10%, and the
continuously compounded risk-free rate is 5%. The value of the call is $4.09.
Chefron, Inc., [[Common stock|common stock]] trades for $60 and has a 1-year call option written on it with an
exercise price of $60. The annual [[Standard deviation|standard deviation]] estimate is 10%, the continuous dividend
yield is 1.4%, and the continuously compounded risk-free rate is 5%.
3. The value of the put on ABC stock is closest to:

### A. $1.16.


### B. $3.28.


### C. $4.09.

4. The value of the call on Chefron stock is closest to:

### A. $3.51.


### B. $4.16.


### C. $5.61.


## Module 29.7: Option Greeks and Dynamic Hedging


> **LOS 29.k:** Interpret each of the option Greeks.


There are five inputs to the BSM model: asset price, exercise price, asset price [[Volatility|volatility]],
[[Time to expiration|time to expiration]], and the risk-free rate. The relationship between each input (except the
exercise price) and the option price is captured by sensitivity factors known as “the
Greeks.”
Delta describes the relationship between changes in asset prices and changes in option
prices. Delta is also the [[Hedge ratio|hedge ratio]]. Call option deltas are positive because as the
underlying asset price increases, call option value also increases. Conversely, the delta of a
put option is negative because the put value falls as the asset price increases. See Figure
29.4.

**Figure 29.4: Call and Put Delta: The Relationship Between Option Price and Underlying**


Asset Price

Deltas for call and put options on dividend paying stocks are given by:

However, because we’re now using a linear relationship to estimate a non-linear change,
the following relationships are only approximations:

The approximations are close for small changes in stock price, but the approximation
becomes less accurate as the ∆S becomes larger.

### Example: Calculating change in option price


from the BSM model is 0.58. Calculate the approximate change in the price of a
call option on the stock if the stock price increases by $0.75.
Answer:

Interpreting Delta
The payoff diagrams for a European call option before- and at-expiration are shown in

**Figure 29.5. The “at expiration” line represents the call option’s [[Intrinsic value|intrinsic value]], which is**

equal to:
Zero when the call option is [[Out-of-the-money|out-of-the-money]].
The stock price minus the exercise price when the option is in-the-money.
Before expiration, the option also has [[Time value|time value]], so the prior-to-expiration curve lies
above the at-expiration diagram by the amount of the time value.


**Figure 29.5: European Call Option Payoff Diagrams**


The slope of the “prior-to-expiration” curve is the change in call price per unit change in
stock price. Sound familiar? It should—that’s also the definition of delta. That means delta
is the slope of the prior-to-expiration curve. The delta of the put option is also the slope of
the prior-to-expiration put curve.
Take a closer look at Figure 29.5. When the call option is deep [[Out-of-the-money|out-of-the-money]], the slope
of the at-expiration curve is close to zero, which means the call delta will be close to zero.
For deep [[Out-of-the-money|out-of-the-money]] call options (i.e., when the stock price is low), the option price
does not change much for a given change in the underlying stock. When the call option is
in-the-money (i.e., when the stock price is high), the slope of the at-expiration curve is
close to 45 degrees, which means the call delta is close to one. In this case, the call option
price will change approximately one-for-one for a given change in the underlying stock
price.
The bottom line is that a call option’s delta will increase from 0 to e–δT as stock price
increases. For a non-dividend paying stock, the delta will increase from 0 to 1 as the stock
price increases.
For a put option, the put delta is close to zero when the put is [[Out-of-the-money|out-of-the-money]] (i.e., when
the stock price is high). When the put option is in-the-money (i.e., when the stock price is
close to zero), the put delta is close to –e–δT.
The bottom line is that a put option’s delta will increase from –e–δT to 0 as stock price
increases. For a non-dividend paying stock, the put delta increases from –1 to 0 as the
stock price increases.
Now, let’s consider what happens to delta as the option approaches maturity, assuming
that the underlying stock price doesn’t change. The effects on call and put options are
different and will depend on whether the options are in- or out-of-the-money.
Remember that a call option delta is between 0 and e–δT. Assuming that the underlying
stock price doesn’t change, if the call option is:
Out-of-the-money (the stock price is less than exercise price), the call delta moves
closer to 0 as time passes.
In-the-money (the stock price is greater than exercise price), the call delta moves closer
to e–δT as time passes.

Remember that a put option delta is between –e–δT and 0. If the put option is:
Out-of-the-money (the stock price is greater than exercise price), the put delta moves
closer to 0 as time passes.
In-the-money (the stock price is less than exercise price), the put delta moves closer to
e–δT as time passes.
Gamma measures the rate of change in delta as the underlying stock price changes.
Gamma captures the [[Curvature|curvature]] of the option-value-versus-stock-price relationship. Long
positions in calls and puts have positive gammas. For example, a gamma of 0.04 implies
that a $1.00 increase in the price of the underlying stock will cause a call option’s delta to
increase by 0.04, making the call option more sensitive to changes in the stock price.
Gamma is highest for [[At-the-money|at-the-money]] options. Deep in-the-money or deep out-of-money
options have low gamma. Gamma changes with stock price and with [[Time to expiration|time to expiration]]. To
lower (increase) the overall gamma of a portfolio, one should short (go long) options.
Recall that delta provides an approximation for change in option value in response to a
change in the price of underlying. Including gamma in our equation would improve the
precision with which change in option value would be estimated (similar to how [[Convexity]]
improves the estimate of change in a bond’s price in response to a change in interest rate).

Call and put options on the same underlying asset with the same exercise price and time to
expiration will have equal gammas.
Vega measures the sensitivity of the option price to changes in the volatility of returns on
the underlying asset, as shown in Figure 29.6. Both call and put options are more valuable,
all else equal, the higher the volatility, so vega is positive for both calls and puts. Volatility is
a very important input to any option valuation model (and thus vega is an important
sensitivity measure) because option values can be very sensitive to changes in volatility.
Note that vega gets larger as the option gets closer to being [[At-the-money|at-the-money]].

**Figure 29.6: Call and Put Vega: The Relationship Between Option Price and Volatility**


Rho measures the sensitivity of the option price to changes in the risk-free rate, as shown
in Figure 29.7. The price of a European call or put option does not change much if we use
different inputs for the risk-free rate, so rho is not a very important sensitivity measure.
Call options increase in value as the risk-free rate increases (the rho of a call option is

positive). You can see this by looking at the BSM model. As the risk-free rate increases, the
second term decreases, and the value of the call option increases.
Put options decrease in value as the risk-free rate increases (the rho of a put option is
negative).

**Figure 29.7: Call and Put Rho: The Relationship Between Option Price and the Risk-Free**

Rate

Theta measures the sensitivity of option price to the passage of time, as shown in Figure
29.8. As time passes and a call option approaches maturity, its speculative value declines,
all else equal. This is called time decay. That behavior also applies for most put options
(though deep in-the-money put options close to maturity may actually increase in value as
time passes). Notice that because it is a measure of time decay, theta is less than zero: as
time passes and the option approaches the maturity date, the option value decreases
(holding other factors constant).

**Figure 29.8: Call and Put Theta: The Relationship Between Option Price and the Time to**

Expiration


> [!pnote] Professor's Note
> ***The statement that theta is less than zero is counterintuitive to many Level II***
> ***candidates because there are two ways to state the relationship between time***
> ***and option value:***
> ***The relationship between option value and time to maturity is positive: all***
> ***else equal, shorter maturity options have lower values.***
> ***The relationship between option value and the passage of time is negative:***
> ***all else equal, as time passes and the option approaches maturity, the value***
> ***of the option decays.***
> ***The key to understanding why theta is less than zero is to recognize that it is***
> ***capturing the intuition of the second statement.***
>
> *****Figure 29.9: Direction of [[European option|European Option]] Prices for a Change in the Five Black-ScholesMerton Model Inputs*****
>
>
> **** There is an exception to the general rule that European put option thetas are negative. The put value***
> ***may increase as the option approaches maturity if the option is deep in-the-money and close to***
> ***maturity.***
>
>
> ***> **LOS 29.l:** Describe how a [[Delta hedge|delta hedge]] is executed.***
>
> ***Dynamic Hedging***
> ***The goal of a delta-neutral portfolio (or delta-neutral hedge) is to combine a long position***
> ***in a stock with a short position in a call option so that the value of the portfolio does not***
> ***change as the stock price changes. The number of calls to sell is equal to:***
>
> ***Delta-neutral portfolios can also be constructed using put options. In such a case, a long***
> ***stock position is combined with a long position in puts. (Remember that put deltas are***
> ***negative).***
>
> ***Delta neutral portfolios are best illustrated with an example.***

### Example: Hedging with call options, part 1


Suppose you own 60,000 shares of Arthurall Company [[Common stock|common stock]] that is currently
selling for $50. A call option on Arthurall with a strike price of $50 is selling for $4 and
has a delta of 0.60. Determine the number of call options necessary to create a deltaneutral hedge.
Answer:
In order to determine the number of call options necessary to hedge against
instantaneous movements in Arthurall’s stock price, we calculate:

Because we are long the stock, we need to short the options.

### Example: Hedging with call options, part 2


Calculate the effect on portfolio value of a $1 increase in the price of Arthurall stock.
Answer:
If the price of Arthurall stock increased instantly by $1.00, the value of your call option
position would decrease by $0.60 because you have sold the call option contracts.
Therefore, the net impact of the price change on the value of the hedged portfolio
would be zero:
total change in value of stock position = 60,000 × $1 = +$60,000
total change in value of option position = 100,000 × –$0.60 = –$60,000
total change in portfolio value = $60,000 – $60,000 = $0
A key consideration in delta-neutral hedging is that the delta hedged asset position is only
risk free for a very small change in the value of the underlying stock. The delta-neutral
portfolio must be continually rebalanced to maintain the hedge; for this reason, it is called
a [[Dynamic hedge|dynamic hedge]]. As the underlying stock price changes, so does the delta of the call
option, and thus too the number of calls that need to be sold to maintain a hedged
position. Hence, continuously maintaining a delta-neutral position involves significant
transaction costs.

> **LOS 29.m:** Describe the role of gamma risk in options trading.
If the assumptions of the BSM hold, changes in stock price will be continuous rather than
abrupt, and hence there will be no gamma risk. In this context, gamma can be viewed as a
measure of how poorly a [[Dynamic hedge|dynamic hedge]] will perform when it is not rebalanced in

response to a change in the asset price. Gamma risk is therefore the risk that the stock
price might abruptly “jump,” leaving an otherwise delta-hedged portfolio unhedged.
Consider a [[Delta hedge|delta hedge]] involving a long position in stock and short position in calls. If the
stock price falls abruptly, the loss in the long stock position will not equal the gain in the
short call position. This is the gamma risk of the hedge.
Because a stock’s delta is always 1, its gamma is 0. A delta-hedged portfolio with a long
position in stocks and a short position in calls will have negative net gamma exposure.

> **LOS 29.n:** Define [[Implied volatility|implied volatility]] and explain how it is used in options
trading.
Future volatility is one of the inputs in the BSM model. Estimates based on historical
volatility are often used because future volatility is not directly observable.
[[Implied volatility|Implied volatility]] is the [[Standard deviation|standard deviation]] of continuously compounded asset returns that
is “implied” by the market price of the option. Of the five inputs into the BSM model, four
are observable: stock price, exercise price, risk-free rate, and time to maturity. If we plug
these four inputs into the BSM model, we can solve for the value of volatility that makes
the BSM model value equal the market price.
Volatility enters the BSM pricing equation in a complex way, and there is no closed-form
solution for the volatility that will produce a value equal to the market price. Rather,
[[Implied volatility|implied volatility]] must be found by iteration (i.e., trial and error).
Traders often use implied volatilities to gauge market perceptions. For example, implied
volatilities in options with different exercise prices on the same underlying may reflect
different implied volatilities (a violation of the BSM assumption of constant volatility).
Traders can also use [[Implied volatility|implied volatility]] as a mechanism to quote option prices. In this way,
options with different exercise prices and maturity dates can be quoted using the same
unit of measurement.

### Example: Implied volatility


Calls on Blue, Inc., stock are currently trading at an implied volatility of 22%. A trader
estimates that the future volatility will actually be closer to 25%. To capitalize on her
beliefs, the trader should:
A. change her model.
B. buy calls on Blue stock.
C. write calls on Blue stock.

Answer:
B. Based on the trader’s beliefs, call options on Blue stock are underpriced in the market. Accordingly,
she should buy the calls.

### Module Quiz 29.7

1. Which of the following statements is least accurate? The value of a:

A. call option will decrease as the risk-free rate increases.
B. put option will decrease as the exercise price decreases.
C. call option will decrease as the underlying stock price decreases.
2. Which of the following inputs into the Black-Scholes-Merton model is least likely to have
opposite effects on put and call prices?
A. Volatility.
B. Strike price.
C. Risk-free rate.
3. Which of the following statements is most accurate? Implied volatility:
A. requires market prices.
B. requires a series of past returns.
C. is equal for otherwise identical options with different maturities.
4. The delta of a put is –0.43. If the price of the underlying stock increases from $40 to $44, the
price of the put option:
A. increases by approximately 4.3%.
B. decreases by approximately 4.3%.
C. decreases by approximately $1.72.
5. The current stock price of Heart, Inc., is $80. Call and put options with exercise prices of $50
and 15 days to maturity are currently trading. Which of these scenarios is most likely to occur
if the stock price falls by $1?

6. A put option with an exercise price of $45 is trading for $3.50. The current stock price is $45.
What is the most likely effect on the option’s delta and gamma if the stock price increases to
$50?
A. Both delta and gamma will increase.
B. Both delta and gamma will decrease.
C. One will increase and the other will decrease.
7. From the Black-Scholes-Merton model, N(d1) = 0.42 for a 3-month call option on Panorama
Electronics [[Common stock|common stock]]. If the stock price falls by $1.00, the price of the call option will:
A. decrease by less than the increase in the price of the put option.
B. increase by more than the decrease in the price of the put option.
C. decrease by the same amount as the increase in the price of the put option.


> [!abstract] Key Concepts
> LOS 29.a

To value an option using a two-period binomial model:
Calculate the stock values at the end of two periods (there are three possible outcomes
because an up-down move gets you to the same place as a down-up move).
Calculate option payoffs at the end of two periods.
Calculate expected values at the end of two periods using the up- and down-move
probabilities. Discount these back one period at the risk-free rate to find the option
values at the end of the first period.

Calculate expected value at the end of period one using the up- and down-move
probabilities. Discount this back one period to find the option value today.
To price an option on a bond using a binomial tree, (1) price the bond at each node using
projected interest rates, (2) calculate the [[Intrinsic value|intrinsic value]] of the option at each node at
maturity of the option, and (3) calculate the value of the option today.
LOS 29.b

Option values can be calculated as present value of expected payoffs on the option,
discounted at the risk-free rate. The probabilities used to calculate the expected value are
[[Risk-neutral probabilities|risk-neutral probabilities]].
LOS 29.c

Synthetic call and put options can be created using a replicating portfolio. A [[Replication|replication]]
portfolio for a call option consists of a leveraged position in h shares where h is the hedge
ratio or delta of the option. A [[Replication|replication]] portfolio for a put option consists of a long
position in a risk-free bond and a short position in h shares. If the value of the option
exceeds the value of the replicating portfolio, an arbitrage profit can be earned by writing
the option and purchasing the replicating portfolio.
LOS 29.d

The value of a European call option using the binomial option valuation model is the
present value of the expected value of the option in the 2 states.

The value of an American-style call option on a non-dividend paying stock is the same as
the value of an equivalent [[European-style|European-style]] call option. American-style put options may be
more valuable than equivalent [[European-style|European-style]] put options due to the ability to exercise
early and earn interest on the intrinsic value.
LOS 29.e

The value of an interest rate option is computed similarly to the value of options on stocks:
as the present value of the expected future payoff. Unlike binomial stock price trees,
binomial interest rate trees have equal (risk-neutral) probabilities of the up and down
states occurring.
LOS 29.f

The assumptions underlying the BSM model are:
The price of the underlying asset changes smoothly (i.e., does not jump) and has a
normally distributed [[Continuously compounded return|continuously compounded return]].
The (continuous) risk-free rate is constant and known.
The volatility of the underlying asset is constant and known.
Markets are “frictionless.”
The continuously compounded yield on the underlying asset is constant.
The options are European.

LOS 29.g

Calls can be thought of as leveraged stock investment where N(d1) units of stock is
purchased using
of borrowed funds. A portfolio that replicates a put option can be
constructed by combining a long position in N(–d2) bonds and a short position in N(–d1)
stocks.
LOS 29.h

European options on dividend-paying stock can be valued by adjusting the model to
incorporate the yield on the stock: the current stock price is adjusted by subtracting the
present value of dividends expected up until option expiration. Options on currencies
incorporate a yield on the [[Foreign currency|foreign currency]] based on the interest rate in that currency.
LOS 29.i

The Black model is simply the BSM model with

substituted for S0.

LOS 29.j

The Black model can be used to value interest rate options by substituting the current
forward rate in place of the stock price and the exercise rate in place of exercise price. The
value is adjusted for accrual period (i.e., the period covered by the underlying rate).
A swaption is an option that gives the holder the right to enter into an interest rate swap. A
payer (receiver) swaption is the right to enter into a swap as the fixed-rate payer (receiver).
A payer (receiver) swaption gains value when interest rates increase (decrease).
LOS 29.k

Direction of BSM option value changes for an increase in the five model inputs:

Delta is the change in the price of an option for a one-unit change in the price of the
underlying security. e–δTN(d1) from the BSM model is the delta of a call option, while –e–
δT

N(–d1) is the put option delta.

As stock price increases, delta for a call option increases from 0 to e–δT, while delta for a
put option increases from –e–δT to 0.

LOS 29.l

The goal of a delta-neutral portfolio (or delta-neutral hedge) is to combine a long position
in a stock with a short position in call options (or a long position in put options) so that the
portfolio value does not change when the stock value changes. Given that delta changes
when stock price changes, a delta hedged portfolio needs to be continuously rebalanced.
Gamma measures how much delta changes as the asset price changes and, thus, offers a
measure of how poorly a fixed hedge will perform as the price of the underlying asset
changes.
LOS 29.m

When the price of the underlying stock abruptly jumps, a violation of BSM, the delta of the
option would change (captured by the option gamma), leaving a previously delta hedged
portfolio unhedged. This is the gamma risk of a delta hedged portfolio.
LOS 29.n

Implied volatility is the volatility that, when used in the Black-Scholes formula, produces
the current market price of the option. If an option is overvalued, implied volatility is too
high.

### Answer Key For Module Quizzes

Module Quiz 29.1, 29.2
1. B Stock Tree

Option Tree

(Module 29.2, LOS 29.d)
Module Quiz 29.3
1. B In the upper node at the end of the first year, the European option is worth $0.29, but
the American option can be exercised and a profit of $0.57 realized (the difference
between the bond price of $100.57 and the exercise price of $100).
In the lower node at the end of the first year, the European option is worth $1.35,
but the American option can be exercised and a profit of $3.80 realized (the
difference between the bond price of $103.80 and the exercise price of $100).
The value of the American option today is therefore:
(LOS 29.d)
Module Quiz 29.4
1. C The hedge ratio in a one-period model is equivalent to a delta, the ratio of the call
price change to the stock price change. We will sell the 1,000 calls because they are
overpriced. Buying 350 shares of stock will produce a riskless hedge. The payoff at
expiration will return more than the riskless rate on the net cost of the hedge
portfolio. Borrowing to finance the [[Hedge portfolio|hedge portfolio]] and earning a higher rate than
the borrowing rate produces arbitrage profits. (LOS 29.c)
2. A A synthetic European put option is formed by:
Buying a European call option.
Short-selling the stock.
Buying (i.e., investing) the present value of the exercise price worth of a purediscount riskless bond.
(LOS 29.c)

Module Quiz 29.5, 29.6
1. A The dividend affects option values because if you own the option, you do not have
access to the dividend. Hence, if the firm pays a dividend during the life of the
option, this must be considered in the valuation formula. Dividends decrease the
value of call options, all else equal, and they increase the value of put options.
(Module 29.6, LOS 29.h)
2. A To derive the BSM model, we need to assume no arbitrage is possible and that:
A [[Continuously compounded return|continuously compounded return]] on the underlying has a [[Normal distribution|normal distribution]].
The (continuous) risk-free rate is constant.
The volatility of the underlying asset is constant.
Markets are “frictionless.”
The (continuously compounded) yield on the underlying asset is constant (and
not necessarily zero).
The options are European (i.e., they can only be exercised at maturity).
(Module 29.6, LOS 29.f)
3. A According to put/call parity, the put’s value is:

(Module 29.6, LOS 29.h)
4. A ABC and Chefron stock are identical in all respects except Chefron pays a dividend.
Therefore, the call option on Chefron stock must be worth less than the call on ABC
(i.e., less than $4.09). $3.51 is the only possible answer. (Module 29.6, LOS 29.h)
Module Quiz 29.7
1. A The value of a call and the risk-free rate are positively related, so as the risk-free rate
increases, the value of the call will increase. (LOS 29.k)
2. A Volatility increases will increase the values of both puts and calls. (LOS 29.k)
3. A Implied volatility is the volatility that produces market option prices from the BSM
model. Its use for pricing options is limited because it is based on market prices. Past
returns are used to calculate historical volatility. (LOS 29.n)
4. C The put option will decrease in value as the underlying stock price increases: –0.43 ×
$4 = –$1.72. (LOS 29.k)
5. A The call option is deep in-the-money and must have a delta close to one. The put
option is deep out-of-the-money and will have a delta close to zero. Therefore, the
value of the in-the-money call will decrease by close to $1 (e.g., $0.94), and the value
of the out-of-the-money put will increase by a much smaller amount (e.g., $0.08).
The call price will fall by more than the put price will increase. (LOS 29.k)
6. C The put option is currently [[At-the-money|at-the-money]] because its exercise price is equal to the
stock price of $45. As stock price increases, the put option’s delta (which is less than
zero) will increase toward zero, becoming less negative. The put option’s gamma,

which measures the rate of change in delta as the stock price changes, is at a
maximum when the option is [[At-the-money|at-the-money]]. Therefore, as the option moves out-ofthe-money, its gamma will fall. (LOS 29.k)
7. A If ∆S = –$1.00, ∆C ≈ 0.42 × (–1.00) = –$0.42, and ∆P ≈ (0.42 – 1) × (–1.00) = $0.58, the
call will decrease by less ($0.42) than the increase in the price of the put ($0.58).
(LOS 29.k)

Topic Quiz: [[Derivatives|Derivatives]]
You have now finished the [[Derivatives|Derivatives]] topic section. Please log into your Schweser online
dashboard and take the Topic Quiz on this section. The Topic Quiz provides immediate
feedback on how effective your study has been for this material. Questions are more examlike than typical Module Quiz or QBank questions; a score of less than 70% indicates that
your study likely needs improvement. These tests are best taken timed; allow three minutes
per question.


---

