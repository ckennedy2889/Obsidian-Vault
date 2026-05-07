---
title: Data Cleansing Wrangling and Scaling
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, big-data, data-wrangling, preprocessing]
aliases: [Data cleansing, Data wrangling, Data preprocessing, Normalization, Standardization, Winsorization, Trimming]
---

# Data Cleansing Wrangling and Scaling

## The Real-World Analogy

Raw data is like ingredients dumped on a kitchen counter. Some ingredients are missing labels, some are duplicated, some are spoiled, and some are measured in cups while others are measured in grams. A model cannot cook with that. Data cleansing and wrangling turn the messy pile into a clean, measured, model-ready dataset.

In big data projects, this work often takes more time than the model itself.

## The Big Idea

There are two broad stages:

| Stage | Purpose |
|---|---|
| Data cleansing | Identify and fix errors in the raw data |
| Data wrangling or preprocessing | Transform clean data into model-ready features |

The model can only learn from the structure you give it. Bad data preparation means the model learns noise, errors, duplicates, or scale artifacts.

## Data Cleansing

Common raw-data problems:

| Problem | Example | Typical response |
|---|---|---|
| Missing values | P/E ratio is blank | Omit row, impute mean/median/mode, or flag missing |
| Duplicate records | Same loan application appears twice | Remove duplicate |
| Invalid data | Negative revenue for a normal company | Correct or remove |
| Inaccurate data | Wrong ticker mapped to company | Correct source mapping |
| Inconsistent data | US ZIP code with Canadian country code | Reconcile fields |
| Non-uniform format | Dates stored as `Jan 15 2026` and `15/01/26` | Convert to common format |

The exam often asks what should happen first. Clean the data before training the model and before scaling.

## Handling Outliers

Outliers can distort model training, especially algorithms sensitive to scale or distance.

Common approaches:

| Method | What it does | When it may fit |
|---|---|---|
| Trimming or truncation | Removes extreme observations | Extreme values are errors or outside project scope |
| Winsorization | Replaces extremes with capped values | Extremes are valid but too influential |
| Investigation | Checks source records | Always needed before mechanical treatment |

Do not remove outliers blindly. A valid extreme value may contain exactly the signal the model needs.

## Data Wrangling And Preprocessing

Once data is clean, wrangling transforms it into features usable by the model.

| Transformation | Meaning | Example |
|---|---|---|
| Extraction | Create a variable from part of another field | Age from date of birth |
| Aggregation | Combine variables | Salary + bonus = total income |
| Filtration | Remove rows | Exclude non-US companies |
| Selection | Remove columns | Drop irrelevant ID field |
| Conversion | Change type or format | Convert `$5.2m` to numeric 5.2 |

The filtration versus selection distinction is a common CFA wording trap:

```text
Filtration = rows
Selection = columns
```

## Scaling

Scaling puts features on comparable numerical ranges.

This matters because some algorithms treat distance or magnitude literally. A model comparing income and age may accidentally treat income as more important simply because it is measured in larger units.

## Normalization

Normalization rescales data to the interval from 0 to 1:

$$
X_{normalized}
=
\frac{X_i-X_{min}}{X_{max}-X_{min}}
$$

Normalization is useful when the distribution is unknown, but it is sensitive to outliers because the minimum and maximum define the scale.

## Standardization

Standardization converts observations into z-scores:

$$
X_{standardized}
=
\frac{X_i-\mu}{\sigma}
$$

The transformed variable has mean 0 and standard deviation 1.

Standardization is less sensitive to outliers than normalization, but it assumes the variable distribution is reasonably normal.

## Worked Numerical Example

Suppose the interest expense feature has:

| Statistic | Value |
|---|---:|
| Minimum, $X_{min}$ | 0.2 |
| Maximum, $X_{max}$ | 12.2 |
| Mean, $\mu$ | 1.1 |
| Standard deviation, $\sigma$ | 0.4 |

Company HIJ has:

$$
X_i=1.2
$$

Normalize:

$$
X_{normalized}
=
\frac{1.2-0.2}{12.2-0.2}
$$

$$
X_{normalized}
=
\frac{1.0}{12.0}
=
0.0833
$$

Standardize:

$$
X_{standardized}
=
\frac{1.2-1.1}{0.4}
$$

$$
X_{standardized}
=
\frac{0.1}{0.4}
=
0.25
$$

The normalized value says HIJ is close to the sample minimum on a 0-to-1 scale. The standardized value says HIJ is 0.25 standard deviations above the mean.

## Correct Workflow

Use this order:

```text
Raw data
  |
  v
Clean missing, invalid, inaccurate, duplicate, inconsistent data
  |
  v
Investigate and treat outliers
  |
  v
Transform features
  |
  v
Scale variables if needed
  |
  v
Train model
```

Scaling before handling outliers is risky because outliers can set the min/max and compress the valid observations.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Scaling before outlier treatment | Outliers dominate min/max or standard deviation | Clean and treat outliers first |
| Confusing normalization and standardization | Uses wrong formula | Normalize to 0-1; standardize to z-score |
| Applying standardization to non-normal data | Violates the method's assumption | Use normalization if distribution is unknown/non-normal |
| Confusing filtration and selection | Removes columns when rows were meant, or vice versa | Filtration removes rows; selection removes columns |
| Deleting all missing data automatically | Shrinks or biases sample | Consider imputation, missing flags, or justified deletion |

## Memory Hooks

**Clean first, transform second, scale third.**

**Normalization uses min and max. Standardization uses mean and standard deviation.**

**Filtration is rows; selection is columns.**

## Related Concepts

- [[Big Data Projects]]
- [[Text-Based Data for Financial Forecasting]]
- [[Influence Analysis]]
- [[Studentized Residuals]]
- [[Machine Learning]]
- [[k-Nearest Neighbor (KNN)]]
- [[Support Vector Machines]]
