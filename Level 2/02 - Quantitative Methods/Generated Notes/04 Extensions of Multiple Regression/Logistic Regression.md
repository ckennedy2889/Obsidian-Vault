---
title: Logistic Regression
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, logistic-regression]
aliases: [Logit model, Log odds model, Binary dependent variable regression, Logistic model]
---

# Logistic Regression

## The Real-World Analogy

[[Logistic regression]] is what you use when the answer is not "how much?" but "will it happen?" A credit analyst may want to estimate whether a bond issuer defaults. An equity analyst may want to estimate whether a company increases its dividend. A fraud model may estimate whether a transaction is fraudulent. The dependent variable is usually binary:

$$
Y =
\begin{cases}
1, & \text{event occurs} \\
0, & \text{event does not occur}
\end{cases}
$$

Ordinary least squares is built for a continuous dependent variable. Logistic regression is built for probabilities.

## Why OLS Is Not Appropriate

If you regress a binary variable directly on predictors using OLS, you create a linear probability model. That creates two exam-relevant problems:

| Problem | Why it matters |
|---|---|
| Predicted values can be below 0 or above 1 | Probabilities outside $[0,1]$ are impossible |
| Constant slope assumption | The effect of a predictor on probability is not realistically constant near 0%, 50%, and 100% |

Logistic regression fixes this by modeling **log odds** instead of modeling probability directly.

## Odds And Log Odds

If the probability of an event is $P$, the odds are:

$$
\text{Odds} = \frac{P}{1-P}
$$

If $P=0.75$:

$$
\text{Odds} = \frac{0.75}{0.25}=3
$$

That means the event is three times as likely to occur as not occur.

The log odds, or logit, is:

$$
\ln\left(\frac{P}{1-P}\right)
$$

Log odds can range from negative infinity to positive infinity, so they are suitable for a regression-style linear equation.

## The Logistic Regression Model

The model is:

$$
\ln\left(\frac{P}{1-P}\right)
=
b_0+b_1X_1+b_2X_2+\cdots+b_kX_k
$$

To convert the fitted logit value back into a probability:

$$
\hat{P}
=
\frac{1}{1+e^{-\hat{Y}}}
$$

where:

$$
\hat{Y}=b_0+b_1X_1+\cdots+b_kX_k
$$

This transformation forces predicted probabilities to stay between 0 and 1.

## Coefficient Interpretation

A slope coefficient in logistic regression is not a direct change in probability. It is a change in log odds.

If $b_1=0.30$, then a one-unit increase in $X_1$ increases the log odds by 0.30, holding other variables constant.

The effect on actual probability depends on the starting point. Moving from 50% to 57% is easier than moving from 97% to 104%, which is impossible. This is why the logistic curve is S-shaped:

```text
Probability
1.0 |                         ______
    |                     ___/
0.5 |              ______/
    |          ___/
0.0 |_________/
       Low X       Mid X       High X
```

The curve is steepest around $P=0.50$ and flattens near 0 and 1.

## Maximum Likelihood Estimation

Logistic regression coefficients are estimated using [[Maximum likelihood estimation|maximum likelihood estimation]] rather than least squares.

The intuition:

1. Pick trial coefficients.
2. Convert each observation's predictors into a predicted probability.
3. Ask: how likely is the observed pattern of 1s and 0s under those probabilities?
4. Choose the coefficients that maximize that likelihood.

This is different from OLS, which minimizes squared residuals.

## Likelihood Ratio Test

Because logistic regression is estimated with maximum likelihood, the usual overall F-test is not the right joint test. CFA uses the [[Likelihood ratio test|likelihood ratio]] test.

$$
LR =
-2
\left[
\ln L_{restricted}
-
\ln L_{unrestricted}
\right]
$$

The LR statistic follows a chi-square distribution with degrees of freedom equal to the number of restrictions.

| Model | Meaning |
|---|---|
| Restricted model | Simpler model, often intercept-only |
| Unrestricted model | Full model with predictors |

Log-likelihoods are usually negative. A value closer to zero means better fit. The LR test asks whether the improvement in log-likelihood is large enough to justify the added variables.

## Worked Numerical Example

Suppose a logistic regression estimates whether an ETF is a winning fund:

$$
\hat{Y} = -1.9589 + 0.3453(\text{Price-to-sales})
$$

For an ETF with price-to-sales of 4.0:

$$
\hat{Y}
=
-1.9589+0.3453(4.0)
$$

$$
\hat{Y}
=
-1.9589+1.3812
=
-0.5777
$$

Convert log odds to probability:

$$
\hat{P}
=
\frac{1}{1+e^{-(-0.5777)}}
$$

$$
\hat{P}
=
\frac{1}{1+e^{0.5777}}
$$

$$
\hat{P}
=
\frac{1}{1+1.7819}
=
0.3595
$$

The model estimates a 35.95% probability that the ETF is a winning fund.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Interpreting coefficients as probability changes | Says $b_1=0.30$ means probability rises by 30% | Coefficients change log odds, not probability directly |
| Forgetting the inverse-logit conversion | Reports $\hat{Y}$ as the probability | Use $\hat{P}=1/(1+e^{-\hat{Y}})$ |
| Using an F-test | Applies OLS model-fit logic | Logistic regression uses LR test with chi-square distribution |
| Looking for ordinary $R^2$ | Treats pseudo-$R^2$ like OLS $R^2$ | Pseudo-$R^2$ is only a rough model-comparison measure |
| Ignoring the binary dependent variable | Uses linear regression by habit | Binary/categorical outcome calls for logit or related classification model |

## Memory Hooks

**Logistic regression predicts probabilities by modeling log odds.**

**Coefficient = log-odds effect, not probability effect.**

**OLS uses F-tests; logit uses likelihood ratio tests.**

## Related Concepts

- [[Multiple Regression - Basics and Assumptions]]
- [[Extensions of Multiple Regression]]
- [[Likelihood ratio test]]
- [[Maximum likelihood estimation]]
- [[Probability of Default]]
- [[Dummy variable]]
- [[Confusion Matrix]]
- [[Machine Learning]]
