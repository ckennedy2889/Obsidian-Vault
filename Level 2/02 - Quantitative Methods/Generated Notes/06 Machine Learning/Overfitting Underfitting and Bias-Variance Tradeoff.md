---
title: Overfitting Underfitting and Bias-Variance Tradeoff
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, overfitting, bias-variance]
aliases: [Overfitting, Underfitting, Bias error, Variance error, Learning curves, Regularization]
---

# Overfitting Underfitting and Bias-Variance Tradeoff

## The Real-World Analogy

Imagine studying for the CFA exam by memorizing the exact answer order of one mock exam. You would score perfectly on that mock, but fail when the real exam asks the same concepts in a new way. That is [[Overfitting]]: excellent in-sample performance, poor out-of-sample generalization.

Underfitting is the opposite. It is like studying only "finance is about money." The rule is too simple to explain the questions, so you perform poorly everywhere.

## The Big Idea

The goal of machine learning is generalization: a model should perform well on new data, not just the data used to train it.

| Problem | Model behavior | Error pattern |
|---|---|---|
| Underfitting | Too simple; misses real relationships | High training error and high validation/test error |
| Overfitting | Too complex; memorizes noise | Low training error but high validation/test error |
| Good fit | Captures signal without memorizing noise | Low training error and low validation/test error |

## Bias Error

Bias error comes from overly simple assumptions.

High-bias models underfit because they cannot represent the true relationship.

Examples:

| Situation | Why high bias occurs |
|---|---|
| Linear model for a nonlinear default relationship | Relationship bends sharply at high leverage |
| Too few features | Model lacks relevant explanatory variables |
| Excessive regularization | Penalty removes useful signal |

Linear models tend to be more exposed to bias error.

## Variance Error

Variance error comes from sensitivity to small changes in the training data.

High-variance models overfit because they respond too strongly to noise.

Examples:

| Situation | Why high variance occurs |
|---|---|
| Deep decision tree | Memorizes specific training observations |
| Too many features | Learns accidental correlations |
| Too little regularization | Model complexity is unconstrained |

Nonlinear and highly flexible models tend to be more exposed to variance error.

## The Tradeoff

As model complexity rises:

```text
Bias error      decreases
Variance error  increases
```

The goal is not minimum bias or minimum variance alone. The goal is minimum total expected error.

```text
Too simple          Balanced             Too complex
Underfit            Good fit             Overfit
High bias           Lower total error    High variance
```

## Learning Curves

A learning curve plots accuracy or error against training sample size.

| Pattern | Interpretation |
|---|---|
| Training and validation errors both high and close | Underfitting / high bias |
| Training error low but validation error high | Overfitting / high variance |
| Training and validation errors low and close | Good generalization |

For a robust model, validation/test performance should improve as more training data are added, and the gap between training and validation performance should narrow.

## Fitting Curves

A fitting curve plots error against model complexity.

| Complexity | Training error | Validation error |
|---|---:|---:|
| Too low | High | High |
| Moderate | Lower | Lowest |
| Too high | Very low | Rising |

The best model complexity is where validation error is minimized, not where training error is minimized.

## Reducing Overfitting

Common techniques:

| Technique | Mechanism |
|---|---|
| Regularization | Penalizes model complexity |
| Cross-validation | Estimates out-of-sample error more robustly |
| Feature selection | Removes noisy variables |
| Pruning / depth limits | Restricts trees |
| Random forests | Average many trees to reduce variance |
| More representative training data | Reduces sensitivity to quirks |

For [[LASSO]], the penalty is:

$$
\lambda \sum |\hat{b}_k|
$$

If $\lambda=0$, the penalty disappears and LASSO becomes ordinary least squares. If $\lambda$ is too high, useful features are removed and the model underfits.

## Worked Example: Tuning Regularization

Suppose a loan-default model is trained with three LASSO penalty values:

| Model | $\lambda$ | Training error | CV error | Diagnosis |
|---|---:|---:|---:|---|
| A | 0.01 | 2.1% | 18.5% | Overfitting / high variance |
| B | 1.50 | 22.4% | 23.1% | Underfitting / high bias |
| C | 0.15 | 7.2% | 7.8% | Best generalization |

Model A has a huge training-validation gap. It memorized the training set.

Model B has both errors high. It is too constrained.

Model C has low and similar errors. It is the best choice.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Choosing lowest training error | Selects overfit model | Choose based on validation/test performance |
| Confusing bias and variance | Says overfitting is high bias | Underfitting = high bias; overfitting = high variance |
| Thinking more complexity is always better | Training error falls but test error rises | Watch validation error |
| Using random k-fold CV for time series | Destroys chronological order | Use time-aware validation for time series |
| Thinking $\lambda=0$ regularizes LASSO | Penalty disappears | $\lambda=0$ means no LASSO penalty |

## Memory Hooks

**Underfit: bad everywhere. Overfit: great in training, bad in testing.**

**Bias is too simple. Variance is too sensitive.**

**Train to learn; validate to tune; test to verify.**

## Related Concepts

- [[Big Data Project Workflow and Model Training]]
- [[LASSO]]
- [[Random Forests]]
- [[Classification and Regression Trees (CART)]]
- [[Support Vector Machines]]
- [[Neural Networks]]
- [[Root Mean Squared Error (RMSE)]]
- [[Confusion Matrix]]
