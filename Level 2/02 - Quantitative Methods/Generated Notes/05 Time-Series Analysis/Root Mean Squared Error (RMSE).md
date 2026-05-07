---
title: Root Mean Squared Error (RMSE)
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, time-series-analysis, forecasting, model-evaluation]
aliases: [RMSE, Root Mean Squared Error, Root Mean Square Error]
---

# Root Mean Squared Error (RMSE)

> [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]] is the square root of the average squared forecast error. It is used to compare forecast accuracy, especially for [[out-of-sample forecast errors]]. Lower RMSE means smaller typical forecast errors and therefore better forecast accuracy.

## The Real-World Analogy

Imagine two weather forecasters predicting tomorrow's temperature.

Forecaster A is usually off by a little. Forecaster B is sometimes very close but occasionally wildly wrong.

You need one number that answers:

```text
Which forecaster is usually less wrong?
```

RMSE is that number.

It takes every forecast mistake, squares it so positive and negative errors do not cancel, averages the squared mistakes, and then takes the square root so the answer is back in the original units.

For temperature, RMSE is in degrees.

For inflation, RMSE is in percentage points.

For sales growth, RMSE is in growth-rate units.

That is why RMSE feels intuitive once you see it:

```text
RMSE = typical size of the model's forecast miss
```

## One-Minute Version

RMSE measures forecast error:

$$
RMSE = \sqrt{\frac{\sum_{t=1}^{n}(y_t - \hat{y}_t)^2}{n}}
$$

where:

| Symbol | Meaning |
|---|---|
| $y_t$ | Actual observed value |
| $\hat{y}_t$ | Forecast or predicted value |
| $y_t - \hat{y}_t$ | Forecast error |
| $(y_t - \hat{y}_t)^2$ | Squared forecast error |
| $n$ | Number of forecasts |

The steps:

```text
Actual - Forecast = Error
Error^2 = Squared error
Average squared errors = MSE
Square root of MSE = RMSE
```

The model with the lower out-of-sample RMSE is usually judged more accurate.

## LOS Coverage

RMSE sits in the CFA Level II Quantitative Methods Time-Series Analysis LOS:

| LOS language | What you must be able to do |
|---|---|
| Contrast [[in-sample forecast errors]] and [[out-of-sample forecast errors]] | Know whether the errors come from the estimation period or a later/test period |
| Compare forecasting accuracy of different time-series models based on the RMSE criterion | Calculate RMSE and choose the model with the lower out-of-sample RMSE |

The key CFA sentence:

> Out-of-sample forecasts are usually more valuable in evaluating forecasting performance because the future is always out of sample.

## The Big Idea

RMSE answers:

```text
How large are this model's forecast errors, on average,
after penalizing large misses more heavily?
```

It is not asking whether the model has a high $R^2$.

It is not asking whether coefficients look statistically significant.

It is asking:

```text
When the model forecasts values, how wrong is it?
```

That is why RMSE is so useful for forecasting. Forecasting is not about explaining the past beautifully. It is about being less wrong on new data.

## The Deep Why: Why Each Word Exists

The phrase "root mean squared error" tells you the entire calculation backward.

| Word | What it means |
|---|---|
| Error | Actual value minus forecast value |
| Squared | Square each error |
| Mean | Average the squared errors |
| Root | Take the square root |

So:

```text
Root mean squared error
= square root of the mean of squared errors
```

## Step 1: Error

The forecast error is:

$$
e_t = y_t - \hat{y}_t
$$

Why actual minus forecast?

Because a forecast error measures how far the forecast missed the realized value.

If:

$$
y_t = 5
$$

and:

$$
\hat{y}_t = 3
$$

then:

$$
e_t = 5 - 3 = 2
$$

The model underforecast by 2.

If:

$$
y_t = 5
$$

and:

$$
\hat{y}_t = 8
$$

then:

$$
e_t = 5 - 8 = -3
$$

The model overforecast by 3.

The sign tells direction. The magnitude tells size.

## Step 2: Squared Error

RMSE squares each error:

$$
e_t^2 = (y_t - \hat{y}_t)^2
$$

Why square errors?

First, squaring prevents positive and negative errors from canceling.

Suppose the model has two errors:

```text
+10 and -10
```

The average error is:

$$
\frac{10 + (-10)}{2} = 0
$$

That looks perfect, but it is obviously not perfect. The model missed by 10 both times.

Squaring fixes that:

$$
10^2 = 100
$$

$$
(-10)^2 = 100
$$

Second, squaring penalizes large errors more heavily.

An error of 10 is not twice as costly as an error of 5 under squared error. It is four times as costly:

$$
10^2 = 100
$$

$$
5^2 = 25
$$

$$
\frac{100}{25} = 4
$$

That matters because large forecast misses can be especially damaging in finance.

## Step 3: Mean Squared Error

After squaring the errors, average them:

$$
MSE = \frac{\sum_{t=1}^{n}e_t^2}{n}
$$

This gives the mean squared error.

Why average?

Because you need one summary metric for the whole forecast period. Without averaging, a model with more forecast observations would naturally have a larger sum of squared errors simply because it had more chances to be wrong.

The mean makes models comparable over the same forecast set.

## Step 4: Root

Finally, take the square root:

$$
RMSE = \sqrt{MSE}
$$

Why square root?

Because squared errors are in squared units.

If the variable is inflation measured in percentage points, squared errors are in percentage-points-squared. That is awkward.

The square root brings the metric back to the original units.

So if monthly inflation RMSE is:

$$
1.4
$$

that means the typical forecast error is about 1.4 percentage points, not 1.4 squared-percentage-points.

## Full Formula

The formula:

$$
RMSE = \sqrt{\frac{1}{n}\sum_{t=1}^{n}(y_t - \hat{y}_t)^2}
$$

Equivalent form:

$$
RMSE = \sqrt{\frac{\sum_{t=1}^{n}e_t^2}{n}}
$$

where:

$$
e_t = y_t - \hat{y}_t
$$

## Worked Numerical Example

Suppose a model forecasts quarterly sales growth.

| Quarter | Actual growth | Forecast growth | Error: Actual - Forecast | Squared error |
|---|---:|---:|---:|---:|
| Q1 | 4.0% | 3.0% | 1.0% | 1.00 |
| Q2 | 2.0% | 4.0% | -2.0% | 4.00 |
| Q3 | 5.0% | 4.0% | 1.0% | 1.00 |
| Q4 | 1.0% | 3.0% | -2.0% | 4.00 |

Step 1: Sum squared errors.

$$
1.00 + 4.00 + 1.00 + 4.00 = 10.00
$$

Step 2: Divide by number of forecasts.

$$
MSE = \frac{10.00}{4} = 2.50
$$

Step 3: Take the square root.

$$
RMSE = \sqrt{2.50} = 1.5811
$$

Interpretation:

```text
The model's typical forecast error is about 1.58 percentage points.
```

## Comparing Two Models

Suppose two models forecast the same four quarters:

| Model | RMSE |
|---|---:|
| Model A | 1.58% |
| Model B | 2.10% |

Model A has the lower RMSE.

Therefore:

```text
Model A has smaller forecast errors over this forecast period.
Model A is judged more accurate by the RMSE criterion.
```

CFA's exam logic:

> Lower RMSE means greater forecast accuracy.

## In-Sample vs Out-of-Sample Forecast Errors

This distinction is the heart of the CFA testing point.

| Error type | Meaning | Why it matters |
|---|---|---|
| [[In-sample forecast errors]] | Errors inside the period used to estimate the model | Shows fit to data the model already saw |
| [[Out-of-sample forecast errors]] | Errors outside the estimation period | Tests whether the model forecasts new data |

In-sample performance can flatter a model.

Why?

Because the model was estimated using that same data. A complex model can fit old data well by learning sample-specific noise.

Out-of-sample performance is more important because future observations are outside the sample used to estimate the model.

That is why CFA says:

```text
The future is always out of sample.
```

## AR(1) vs AR(2) Example Logic

Suppose an analyst estimates two models using monthly inflation data from 1995-2018:

```text
AR(1): uses one lag
AR(2): uses two lags
```

Then the analyst forecasts inflation from January 2019 to September 2019.

Now those 2019 forecasts are out-of-sample because 2019 was not part of the estimation period.

The analyst computes:

| Model | Out-of-sample RMSE |
|---|---:|
| AR(1) | 1.9014 |
| AR(2) | 1.4157 |

Since:

$$
1.4157 < 1.9014
$$

the AR(2) model had better out-of-sample forecast accuracy over that period.

The relative size:

$$
\frac{1.4157}{1.9014} = 0.7446 = 74.46\%
$$

Interpretation:

```text
The AR(2) model's RMSE was about 74.46% as large as the AR(1) model's RMSE.
```

So AR(2)'s typical forecast error was smaller.

## RMSE vs MSE vs SEE

These terms are related but not identical in how CFA tends to use them.

| Metric | Formula idea | Units | Common use |
|---|---|---|---|
| [[Mean squared error]] (MSE) | Average squared error | Squared units | Model loss / error calculation |
| RMSE | Square root of MSE | Original $Y$ units | Forecast accuracy comparison |
| Standard error of estimate / regression | Square root of residual variance with degrees-of-freedom adjustment | Original $Y$ units | Regression fit/inference |

The intuition:

```text
MSE is mathematically convenient.
RMSE is easier to interpret because it returns to original units.
```

## RMSE For Machine Learning

RMSE is also used in machine learning when the target variable is continuous.

| Target type | Common performance metric |
|---|---|
| Continuous target | RMSE |
| Classification target | Accuracy, precision, recall, F1 score, ROC/AUC |

Example:

```text
Predicting stock return -> continuous -> RMSE can fit.
Predicting default/no default -> classification -> confusion-matrix metrics fit better.
```

## Interpretation

RMSE is always nonnegative:

$$
RMSE \geq 0
$$

Perfect forecasts would have:

$$
RMSE = 0
$$

But in real financial data, RMSE is usually positive.

The lower the RMSE, the more accurate the model over the evaluation period.

But RMSE only makes sense relative to:

- the scale of the variable,
- the competing model's RMSE,
- whether the errors are in-sample or out-of-sample,
- the size and representativeness of the evaluation period.

An RMSE of 2 is not automatically good or bad. It depends on whether the target variable usually moves by 3, 30, or 300.

## Common Wrong Reasoning

### Wrong: "The model with the lower in-sample RMSE is always the better forecasting model."

Why it is wrong: The model may simply fit the estimation sample better. CFA emphasizes that out-of-sample RMSE is usually more valuable for evaluating real-world forecasting performance.

### Wrong: "Positive and negative forecast errors cancel in RMSE."

Why it is wrong: RMSE squares the errors before averaging. Signs disappear.

### Wrong: "RMSE is in squared units."

Why it is wrong: MSE is in squared units. RMSE takes the square root, so RMSE is back in the original units of the target variable.

### Wrong: "Higher RMSE means better accuracy."

Why it is wrong: Higher RMSE means larger average forecast errors. Lower RMSE is better.

### Wrong: "RMSE tells whether the model's coefficients are stable."

Why it is wrong: RMSE measures forecast accuracy over an evaluation period. Coefficient stability is a separate issue CFA says analysts should also examine.

### Wrong: "RMSE is best for classification."

Why it is wrong: RMSE is mainly for continuous predictions. Classification problems usually use metrics such as precision, recall, F1 score, or ROC/AUC.

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| Actual values and forecast values | Compute errors: actual minus forecast |
| Errors have positive and negative signs | Square them before averaging |
| Asked for RMSE | Average squared errors, then take square root |
| Two forecast models | Lower RMSE means more accurate forecasts |
| In-sample vs out-of-sample | Prefer out-of-sample for real forecasting performance |
| Continuous prediction target | RMSE may be appropriate |
| Classification target | Think confusion matrix metrics, not RMSE |
| Model fits past data well but forecasts badly | Overfitting / poor out-of-sample performance |

## Minimum Memorization

Memorize this:

```text
RMSE = square root of average squared forecast error
```

And this:

$$
RMSE = \sqrt{\frac{\sum(y_t - \hat{y}_t)^2}{n}}
$$

And this:

```text
Lower out-of-sample RMSE = better forecast accuracy
```

## Can I Solve This?

You are ready for RMSE questions if you can answer these:

1. What is a forecast error?
2. Why are errors squared?
3. Why is the square root taken?
4. Why is out-of-sample RMSE more important than in-sample RMSE?
5. Which model is more accurate if RMSE is lower?
6. What units is RMSE expressed in?
7. How is RMSE different from MSE?
8. Why can in-sample fit mislead?

## Related Concepts

- [[Time-Series Analysis]]
- [[Autoregressive model]]
- [[AR(1) Model]]
- [[In-sample forecast errors]]
- [[Out-of-sample forecast errors]]
- [[Forecast error]]
- [[Mean squared error]]
- [[Standard error of the estimate]]
- [[Overfitting]]
- [[Model selection]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]]
