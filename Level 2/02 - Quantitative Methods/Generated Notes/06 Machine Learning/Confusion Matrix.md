---
title: Confusion Matrix
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, classification, model-evaluation]
aliases: [Confusion matrix, Classification matrix, TP FP TN FN, Error analysis matrix]
---

# Confusion Matrix

> A [[Confusion Matrix]] is a grid used to evaluate a classification model by comparing predicted classes with actual classes. For binary classification, it summarizes four outcomes: [[true positive]] (TP), [[false positive]] (FP), [[true negative]] (TN), and [[false negative]] (FN).

## The Real-World Analogy

Imagine airport security screening bags.

Each bag is either actually dangerous or actually safe.

The scanner predicts either:

```text
Flag the bag
or
Do not flag the bag
```

Now there are four possible outcomes:

| Outcome | Meaning |
|---|---|
| Dangerous bag flagged | Correct alarm |
| Safe bag not flagged | Correct non-alarm |
| Safe bag flagged | False alarm |
| Dangerous bag not flagged | Miss |

That is the whole confusion matrix.

It is called "confusion" because it shows where the model confuses one class for another.

The deep idea:

```text
Classification model
  |
  v
Predicts labels
  |
  v
Predicted labels compared with actual labels
  |
  v
Four-cell error map
  |
  v
Precision, recall, accuracy, F1, ROC analysis
```

## One-Minute Version

A confusion matrix evaluates classification predictions.

For binary classification:

|  | Actual Positive | Actual Negative |
|---|---:|---:|
| Predicted Positive | TP | FP |
| Predicted Negative | FN | TN |

The cells mean:

| Cell | Full name | Plain English |
|---|---|---|
| TP | True positive | Model predicted positive and actual was positive |
| FP | False positive | Model predicted positive but actual was negative |
| TN | True negative | Model predicted negative and actual was negative |
| FN | False negative | Model predicted negative but actual was positive |

From those four cells, you calculate:

$$
\text{Accuracy} = \frac{TP + TN}{TP + FP + FN + TN}
$$

$$
\text{Precision} = \frac{TP}{TP + FP}
$$

$$
\text{Recall} = \frac{TP}{TP + FN}
$$

$$
F1 = \frac{2PR}{P + R}
$$

where $P$ is precision and $R$ is recall.

## LOS Coverage

The confusion matrix appears in the CFA Level II Quantitative Methods machine learning / big data model-evaluation material.

| Source language | What you must be able to do |
|---|---|
| Evaluate classification model performance using error analysis | Build/interpret TP, FP, TN, FN |
| Calculate precision, recall, accuracy, and F1 score | Know formulas and when each metric matters |
| Understand Type I and Type II classification errors | FP is Type I error; FN is Type II error |
| Evaluate classification models under class imbalance | Know why F1 may be better than accuracy |
| Tune model thresholds | Understand precision/recall trade-offs when cutoff probabilities change |

## The Big Idea

A classification model does not forecast a continuous number like RMSE does.

It assigns a class:

```text
Default / No default
Fraud / Not fraud
Positive sentiment / Negative sentiment
Winner / Average / Loser
Defective / Not defective
```

For binary classification, the model has two possible predictions and reality has two possible states.

That creates a 2x2 grid:

```text
                 Actual class
              Positive   Negative
Pred Positive    TP         FP
Pred Negative    FN         TN
```

The confusion matrix is the raw material.

Precision, recall, accuracy, and F1 score are summaries built from that raw material.

## The Deep Why: Why Four Cells Exist

Start with the model's decision:

```text
Positive or Negative?
```

Then compare it with reality:

```text
Actually Positive or Actually Negative?
```

Two possible predictions times two possible realities gives four outcomes:

```text
2 predictions x 2 actual states = 4 cells
```

Each cell answers a different business question.

| Question | Matrix cell |
|---|---|
| How many positives did we correctly catch? | TP |
| How many negatives did we correctly leave alone? | TN |
| How many negatives did we wrongly flag as positive? | FP |
| How many positives did we wrongly miss? | FN |

The exam loves this because not all mistakes have the same cost.

In fraud detection:

```text
False positive = legitimate transaction flagged
False negative = fraudulent transaction missed
```

In credit default prediction:

```text
False positive = good borrower wrongly labeled default risk
False negative = bad borrower wrongly approved
```

In sentiment analysis:

```text
False positive = negative news wrongly classified as positive
False negative = positive news wrongly classified as negative
```

The model choice depends on which mistake is more costly.

## The Matrix Layout

Use this layout unless the exam gives a different one:

|  | Actual Positive | Actual Negative |
|---|---:|---:|
| Predicted Positive | True Positive (TP) | False Positive (FP) |
| Predicted Negative | False Negative (FN) | True Negative (TN) |

The trick:

```text
True = prediction matches actual.
False = prediction does not match actual.
Positive/Negative = what the model predicted.
```

So:

```text
False positive = model predicted positive, but actual was negative.
False negative = model predicted negative, but actual was positive.
```

## Type I and Type II Errors

CFA maps classification errors this way:

| Classification error | CFA/statistics name | Meaning |
|---|---|---|
| FP | [[Type I error]] | False positive |
| FN | [[Type II error]] | False negative |

Do not overcomplicate it:

```text
FP = Type I
FN = Type II
```

Why?

In both cases, the model makes a wrong decision.

The important exam issue is the cost.

If false positives are costly, focus on precision.

If false negatives are costly, focus on recall.

## Accuracy

Accuracy answers:

> Of all predictions, what fraction were correct?

Formula:

$$
\text{Accuracy}
= \frac{TP + TN}{TP + FP + FN + TN}
$$

It counts both types of correct classification:

```text
Correct positives + correct negatives
```

Accuracy is intuitive, but dangerous under class imbalance.

If 99% of transactions are legitimate and a model predicts "legitimate" for everything, it gets 99% accuracy while catching zero fraud.

That is why CFA warns that accuracy can mislead when classes are unequal.

## Precision

Precision answers:

> Of everything the model predicted as positive, how many were actually positive?

Formula:

$$
\text{Precision}
= \frac{TP}{TP + FP}
$$

The denominator is all predicted positives:

```text
TP + FP
```

So precision is about false alarms.

High precision means:

```text
When the model says positive, it is usually right.
```

Precision is useful when the cost of a [[false positive]] is high.

Example:

```text
Model says a product is defective.
Company scraps it.
But product was actually fine.
```

That is a costly false positive. You want high precision.

## Recall

Recall answers:

> Of all actual positives, how many did the model correctly catch?

Formula:

$$
\text{Recall}
= \frac{TP}{TP + FN}
$$

The denominator is all actual positives:

```text
TP + FN
```

So recall is about misses.

High recall means:

```text
The model catches most of the actual positives.
```

Recall is useful when the cost of a [[false negative]] is high.

Example:

```text
Product is defective.
Model says not defective.
Product is sent to customer.
```

That is a costly false negative. You want high recall.

Recall is also called sensitivity or true positive rate:

$$
TPR = \frac{TP}{TP + FN}
$$

## False Positive Rate

The false positive rate is used in [[ROC]] analysis.

Formula:

$$
FPR = \frac{FP}{FP + TN}
$$

It answers:

> Of all actual negatives, how many did the model incorrectly flag as positive?

ROC curves plot:

```text
x-axis: False positive rate
y-axis: True positive rate / Recall
```

## F1 Score

F1 score combines precision and recall.

Formula:

$$
F1 = \frac{2PR}{P + R}
$$

where:

$$
P = \text{Precision}
$$

and:

$$
R = \text{Recall}
$$

F1 is the harmonic mean of precision and recall.

Why harmonic mean?

Because it punishes imbalance. If one of precision or recall is weak, F1 stays closer to the weaker number.

That is exactly what CFA wants you to remember:

```text
F1 is more appropriate than accuracy when class distribution is unequal
and the analyst wants balance between precision and recall.
```

## Worked Numerical Example

Suppose a classification model produces this confusion matrix:

|  | Actual Class 1 | Actual Class 0 |
|---|---:|---:|
| Predicted Class 1 | 3 (TP) | 1 (FP) |
| Predicted Class 0 | 2 (FN) | 4 (TN) |

So:

```text
TP = 3
FP = 1
FN = 2
TN = 4
```

### Accuracy

$$
\text{Accuracy}
= \frac{TP + TN}{TP + FP + FN + TN}
$$

Substitute:

$$
\text{Accuracy}
= \frac{3 + 4}{3 + 1 + 2 + 4}
$$

Calculate:

$$
\text{Accuracy}
= \frac{7}{10} = 0.70 = 70\%
$$

### Precision

$$
\text{Precision}
= \frac{TP}{TP + FP}
$$

Substitute:

$$
\text{Precision}
= \frac{3}{3 + 1}
$$

Calculate:

$$
\text{Precision}
= \frac{3}{4} = 0.75 = 75\%
$$

Interpretation:

```text
Of the four observations predicted as Class 1, three were actually Class 1.
```

### Recall

$$
\text{Recall}
= \frac{TP}{TP + FN}
$$

Substitute:

$$
\text{Recall}
= \frac{3}{3 + 2}
$$

Calculate:

$$
\text{Recall}
= \frac{3}{5} = 0.60 = 60\%
$$

Interpretation:

```text
Of the five actual Class 1 observations, the model caught three.
```

### F1 Score

$$
F1 = \frac{2PR}{P + R}
$$

Substitute:

$$
F1 = \frac{2(0.75)(0.60)}{0.75 + 0.60}
$$

Calculate numerator:

$$
2(0.75)(0.60) = 0.90
$$

Calculate denominator:

$$
0.75 + 0.60 = 1.35
$$

Divide:

$$
F1 = \frac{0.90}{1.35} = 0.6667 \approx 0.67
$$

Interpretation:

```text
The model's balanced precision-recall score is about 0.67.
```

## Precision vs Recall Trade-Off

Many classification models produce a probability first.

Example:

```text
Probability of positive sentiment = 0.62
```

Then the analyst chooses a threshold:

```text
If p > 0.50, classify as positive.
If p <= 0.50, classify as negative.
```

Changing the threshold changes the confusion matrix.

Higher threshold:

```text
Fewer predicted positives
Usually fewer false positives
Often lower recall because more positives are missed
```

Lower threshold:

```text
More predicted positives
Usually higher recall
Often lower precision because more negatives are falsely flagged
```

That is why CFA says the precision-recall trade-off is a business decision.

## Which Metric Should You Choose?

| Situation | Metric to emphasize | Why |
|---|---|---|
| False positives are costly | Precision | Avoid wrongly flagging negatives as positives |
| False negatives are costly | Recall | Avoid missing actual positives |
| Classes are balanced and FP/FN costs similar | Accuracy can be useful | Correct classifications are representative |
| Classes are imbalanced | F1 score often better | Accuracy can look high even with poor minority-class performance |
| Need threshold trade-off view | ROC / AUC | Shows trade-off between TPR and FPR across thresholds |

## Finance Examples

### Credit Default

Positive class:

```text
Borrower will default
```

False positive:

```text
Model predicts default, but borrower would not default.
```

Cost: lost lending opportunity.

False negative:

```text
Model predicts no default, but borrower defaults.
```

Cost: credit loss.

If credit losses are much more painful than lost opportunities, recall matters.

### Fraud Detection

Positive class:

```text
Transaction is fraudulent
```

False positive:

```text
Legitimate transaction blocked.
```

False negative:

```text
Fraudulent transaction approved.
```

The best metric depends on whether the institution cares more about customer inconvenience or fraud losses.

### Sentiment Classification

Positive class:

```text
Positive sentiment
```

False positive:

```text
Negative sentiment incorrectly classified as positive.
```

Possible result: buy a stock based on wrongly positive sentiment.

False negative:

```text
Positive sentiment incorrectly classified as negative.
```

Possible result: avoid or short a stock with truly positive sentiment.

## Confusion Matrix vs RMSE

| Problem type | Metric family |
|---|---|
| Classification target | Confusion matrix, accuracy, precision, recall, F1, ROC/AUC |
| Continuous target | [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]] |

Do not use RMSE as the main metric when the model is classifying labels.

Do not use a confusion matrix when the model is predicting a continuous number unless you first convert the prediction into classes.

## Common Wrong Reasoning

### Wrong: "Accuracy is always the best performance metric."

Why it is wrong: Accuracy can mislead under class imbalance. If 99% of observations are negative, predicting negative every time gives 99% accuracy but no useful positive detection.

### Wrong: "Precision and recall are the same."

Why it is wrong: Precision uses predicted positives in the denominator. Recall uses actual positives in the denominator.

### Wrong: "False positive means actual positive."

Why it is wrong: In "false positive," positive refers to what the model predicted. The prediction was positive, but reality was negative.

### Wrong: "High precision means the model caught all positives."

Why it is wrong: High precision means predicted positives are usually correct. It says nothing by itself about how many actual positives were missed.

### Wrong: "High recall means predicted positives are usually correct."

Why it is wrong: High recall means the model caught most actual positives. It may still produce many false positives.

### Wrong: "F1 is the arithmetic average of precision and recall."

Why it is wrong: F1 is the harmonic mean, so it is pulled toward the weaker of precision and recall.

### Wrong: "Type I and Type II errors mean the same thing here as always, so I don't need the matrix."

Why it is wrong: In classification CFA maps FP to Type I and FN to Type II. The matrix prevents mixing them up.

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| Binary classification model | Build a confusion matrix |
| Actual vs predicted labels | Count TP, FP, FN, TN |
| Cost of false positives is high | Choose precision |
| Cost of false negatives is high | Choose recall |
| Unequal class distribution | Prefer F1 over accuracy |
| Threshold changes from 0.50 to 0.60 | Recompute matrix; expect precision/recall trade-off |
| ROC curve | x-axis FPR, y-axis TPR/recall |
| Continuous target | Think RMSE, not confusion matrix |

## Minimum Memorization

Memorize this matrix:

```text
                 Actual Positive   Actual Negative
Pred Positive          TP                FP
Pred Negative          FN                TN
```

And this:

```text
Precision = TP / (TP + FP)
Recall    = TP / (TP + FN)
Accuracy  = (TP + TN) / Total
F1        = 2PR / (P + R)
```

And this:

```text
FP = Type I error
FN = Type II error
```

## Can I Solve This?

You are ready for confusion matrix questions if you can answer these:

1. What are TP, FP, FN, and TN?
2. Why is FP a Type I error?
3. Why is FN a Type II error?
4. What is the formula for precision?
5. What is the formula for recall?
6. When should you prefer precision?
7. When should you prefer recall?
8. Why can accuracy mislead under class imbalance?
9. Why is F1 closer to the weaker of precision and recall?
10. How does changing a probability threshold affect the matrix?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[Classification]]
- [[Confusion Matrix]]
- [[Type I error]]
- [[Type II error]]
- [[Precision]]
- [[Recall]]
- [[F1 score]]
- [[Accuracy]]
- [[ROC]]
- [[AUC]]
- [[Logistic regression]]
- [[Support Vector Machines]]
- [[Random Forests]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]]
