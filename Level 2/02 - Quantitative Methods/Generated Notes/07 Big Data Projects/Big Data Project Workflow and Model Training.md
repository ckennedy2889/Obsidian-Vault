---
title: Big Data Project Workflow and Model Training
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, big-data, machine-learning, model-training]
aliases: [Data analysis project steps, Model training workflow, Training validation test split, Cross-validation, Big data project lifecycle]
---

# Big Data Project Workflow and Model Training

## The Real-World Analogy

A big data project is not "throw data into an algorithm." It is closer to building an investment process. You define the decision, collect relevant information, clean it, explore it, engineer better signals, train a model, test whether it generalizes, and only then consider deployment.

The model is only one step in the workflow. A brilliant algorithm trained on badly defined, dirty, or biased data is still a bad forecasting system.

## The Big Idea

The CFA big data workflow is:

```text
Conceptualization
  |
  v
Data collection / curation
  |
  v
Data preparation and wrangling
  |
  v
Data exploration
  |
  v
Feature engineering and selection
  |
  v
Model training
  |
  v
Validation, tuning, and testing
```

The workflow is iterative. A model failure may send the analyst back to feature engineering, data cleaning, or even the original problem definition.

## Step 1: Conceptualization

Conceptualization defines the problem and the target output.

Examples:

| Business problem | Modeling target |
|---|---|
| Credit risk | Default versus no default |
| Equity selection | Future return or outperformer label |
| Fraud detection | Fraudulent versus legitimate transaction |
| Sentiment signal | Positive or negative earnings-call tone |

This step also defines how model output will be used. A trading signal, credit-screening tool, and compliance alert have different costs for false positives and false negatives.

## Step 2: Data Collection And Curation

Data may be:

| Data type | Example |
|---|---|
| Structured | Financial statements, prices, ratios |
| Unstructured | Text, audio, satellite images |
| Internal | Client transactions, loan performance |
| External | News, filings, web-scraped data |

For text data, curation may include web scraping, document labeling, and building a corpus.

## Step 3: Preparation And Wrangling

This is often the most time-consuming step.

See [[Data Cleansing Wrangling and Scaling]] for the detailed mechanics:

- missing values
- duplicate records
- invalid and inconsistent data
- outliers
- extraction, aggregation, filtration, selection, conversion
- normalization and standardization

## Step 4: Data Exploration

Exploratory data analysis looks for patterns, errors, and candidate relationships before model training.

Examples:

| Tool | Use |
|---|---|
| Summary statistics | Mean, variance, skewness, missingness |
| Histograms | Distribution shape |
| Heat maps | Correlations and missing-data patterns |
| Word clouds | Common text tokens |
| Box plots | Outliers and dispersion |

EDA helps decide whether features need transformation, whether classes are imbalanced, and whether outliers or regime shifts are present.

## Step 5: Feature Engineering And Selection

Feature engineering creates better inputs. Feature selection chooses useful inputs.

| Process | Example |
|---|---|
| Feature engineering | Convert date of birth into age |
| One-hot encoding | Convert industry category into dummy variables |
| Text feature engineering | Create `not_good` bigram |
| Feature selection | Drop high-noise tokens or irrelevant variables |

Good features reduce underfitting by helping the model see the relevant structure. Good selection reduces overfitting by removing noisy inputs.

## Step 6: Model Training

Model training has three tasks:

| Task | Question |
|---|---|
| Method selection | Which algorithm fits the objective and data? |
| Performance evaluation | How well does the model work? |
| Tuning | Which hyperparameters improve validation performance? |

Supervised learning uses labeled data. Unsupervised learning does not.

## Training, Validation, And Test Sets

For supervised learning, split the data into:

| Sample | Purpose |
|---|---|
| Training set | Fit model parameters |
| Validation set | Tune hyperparameters |
| Test set | Final out-of-sample evaluation |

A common split is roughly 60% training, 20% validation, and 20% testing, though the exact split depends on sample size and project needs.

The test set should remain untouched until final evaluation. If you repeatedly tune using the test set, it stops being a true out-of-sample test.

## Cross-Validation

In $k$-fold cross-validation:

1. Divide data into $k$ folds.
2. Train on $k-1$ folds.
3. Validate on the remaining fold.
4. Repeat until every fold has served as validation once.
5. Average the validation errors.

Cross-validation gives a more robust estimate of out-of-sample performance when data is limited.

Exam caveat: ordinary random $k$-fold cross-validation is not appropriate for time-series data if it destroys chronological order.

## Overfitting And Underfitting

| Problem | Error type | What happens |
|---|---|---|
| Underfitting | High bias | Model too simple; misses real pattern |
| Overfitting | High variance | Model too complex; memorizes noise |

Overfit models can have excellent in-sample performance and poor out-of-sample performance. This is why validation and test samples matter.

## Worked Financial Example

Suppose a model predicts high-yield bond default. On a validation sample of 1,000 bonds:

| Outcome | Count |
|---|---:|
| True positives, TP | 45 |
| False positives, FP | 15 |
| True negatives, TN | 930 |
| False negatives, FN | 10 |

Precision:

$$
Precision=\frac{TP}{TP+FP}
=
\frac{45}{45+15}
=
0.75
$$

Recall:

$$
Recall=\frac{TP}{TP+FN}
=
\frac{45}{45+10}
=
0.818
$$

F1 score:

$$
F1=
\frac{2(Precision)(Recall)}
{Precision+Recall}
$$

$$
F1=
\frac{2(0.75)(0.818)}
{0.75+0.818}
=
0.782
$$

The F1 score is useful because default prediction is often class-imbalanced. Accuracy alone can be misleading if defaults are rare.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating model training as the whole project | Ignores problem definition and data preparation | Follow the full workflow |
| Confusing parameters and hyperparameters | Says the algorithm learns analyst-chosen settings | Parameters are learned; hyperparameters are set/tuned |
| Tuning on the test set | Contaminates out-of-sample evaluation | Tune on validation; reserve test for final check |
| Using accuracy for imbalanced data | Model predicts majority class and looks good | Use precision, recall, F1, ROC/AUC |
| Random cross-validation for time series | Leaks future information into training | Preserve chronological order |

## Memory Hooks

**Define, collect, clean, explore, engineer, train, validate, test.**

**Validation tunes; test verifies.**

**High accuracy can be worthless when classes are imbalanced.**

## Related Concepts

- [[Data Cleansing Wrangling and Scaling]]
- [[Text-Based Data for Financial Forecasting]]
- [[Text Feature Selection]]
- [[Confusion Matrix]]
- [[Logistic Regression]]
- [[Random Forests]]
- [[Support Vector Machines]]
- [[Overfitting]]
