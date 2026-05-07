---
title: Text Feature Selection
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, big-data, text-analytics, feature-selection]
aliases: [Document frequency, Mutual information, Chi-square feature selection, Token selection, Bag-of-words feature selection]
---

# Text Feature Selection

## The Real-World Analogy

A bag-of-words model can create thousands of possible word features. That is like giving an analyst a spreadsheet with every word ever seen in a filing, transcript, or article. Most of those words are useless. Some are too common to distinguish anything. Others are so rare that they only describe one weird document. Feature selection is the process of keeping the words that actually help classify or forecast.

The goal is a smaller, cleaner, more predictive vocabulary.

## The Big Idea

[[Feature selection]] for text means selecting a useful subset of tokens from the [[Text-Based Data for Financial Forecasting|bag of words]].

It helps by:

| Benefit | Why it matters |
|---|---|
| Reduces model complexity | Fewer token columns in the document-term matrix |
| Reduces noise | Removes words that do not help prediction |
| Improves generalization | Avoids memorizing rare accidents |
| Speeds computation | Smaller matrix is easier to train |

Feature selection keeps or removes existing features. It is not the same as dimensionality reduction, which creates new transformed features.

## Frequency Extremes Are Usually Bad

Text features are often least useful at the extremes.

| Token type | Problem | Model risk |
|---|---|---|
| Very high frequency | Appears in almost every document, does not separate classes | Underfitting |
| Very low frequency | Appears in only one or a few documents, often noise or typo | Overfitting |
| Intermediate frequency | Appears often enough to learn but selectively enough to discriminate | Useful signal |

Example:

| Token | Interpretation |
|---|---|
| `the` | Too common |
| `Zahariev` | Too rare, likely idiosyncratic |
| `downgrade` | Potentially useful for credit-risk classification |

## Document Frequency

[[Document frequency]] is:

$$
DF =
\frac{\text{number of documents containing the token}}
{\text{total number of documents}}
$$

If a token appears in 9,800 out of 10,000 documents:

$$
DF=\frac{9{,}800}{10{,}000}=0.98
$$

That token is probably too common to be useful.

If a token appears in 1 out of 10,000 documents:

$$
DF=\frac{1}{10{,}000}=0.0001
$$

That token is probably too rare to generalize.

## Chi-Square Feature Selection

The chi-square test ranks tokens by how strongly token occurrence is associated with a class.

For example, if the token "default" appears much more frequently in bankrupt-company filings than in non-bankrupt-company filings, it will have a high chi-square statistic.

High chi-square means:

```text
Token occurrence is not independent of class
  |
  v
Token may help classification
```

Low chi-square means the token does not help distinguish the classes.

## Mutual Information

[[Mutual information]] measures how much information a token contributes to identifying a class.

| MI value | Interpretation |
|---:|---|
| Near 0 | Token appears similarly across classes; not discriminative |
| Closer to 1 | Token is strongly associated with one or a few classes |

If a token appears in all classes, its MI is close to zero. If it appears mainly in one class, its MI is higher.

## Worked Conceptual Example

Suppose you classify 10,000 articles as Sports or Politics.

| Token | Document frequency | MI | Decision |
|---|---:|---:|---|
| `the` | 0.98 | 0.0001 | Remove; too common |
| `Zahariev` | 0.0001 | 0.0005 | Remove; too rare |
| `soccer` | 0.08 | 0.0781 | Keep; discriminates Sports |

The useful token is not the most frequent or the rarest. It is the token with enough appearances to be learnable and enough class concentration to be informative.

## Feature Selection Versus Feature Engineering

| Process | What it does | Example |
|---|---|---|
| Feature selection | Keeps or removes existing tokens | Drop tokens with DF > 0.95 |
| Feature engineering | Creates new token features | Combine `not` and `good` into `not_good` |
| Dimensionality reduction | Creates new transformed factors | PCA on a document-term matrix |

This distinction matters because CFA often asks whether the analyst is selecting features or creating new ones.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Most frequent means most important | Keeps stop words | Very common tokens are usually not discriminative |
| Rarest means most powerful | Keeps one-off noise | Rare tokens often overfit |
| Confusing DF and term frequency | Uses within-document count when cross-document presence is needed | DF is documents containing token divided by total documents |
| Confusing chi-square and MI | Treats all feature-selection metrics as identical | Chi-square tests association; MI measures information contribution |
| Confusing feature selection with PCA | Says token filtering creates new variables | Selection keeps/removes; PCA transforms |

## Memory Hooks

**Useful text features live in the middle: not everywhere, not nowhere.**

**High-frequency tokens underfit; low-frequency tokens overfit.**

**DF counts documents, not word repetitions inside one document.**

## Related Concepts

- [[Text-Based Data for Financial Forecasting]]
- [[Data Cleansing Wrangling and Scaling]]
- [[Dimensionality Reduction]]
- [[Principal Component Analysis]]
- [[Support Vector Machines]]
- [[Logistic Regression]]
- [[Confusion Matrix]]
