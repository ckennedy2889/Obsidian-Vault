---
title: Exploratory Data Analysis
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, big-data, exploratory-data-analysis, data-exploration]
aliases: [EDA, Data exploration, Word clouds, Box plots, Heat maps, Term frequency]
---

# Exploratory Data Analysis

## The Real-World Analogy

Exploratory data analysis is the analyst walking the property before building the model. You look for missing walls, strange wiring, hidden rooms, and obvious patterns before deciding what kind of structure can safely be built. In finance, EDA helps you understand distributions, outliers, relationships, and text patterns before model training.

Skipping EDA is how models end up learning data errors, spurious relationships, or useless features.

## The Big Idea

EDA sits between data preparation and model training.

Its objectives are to:

| Objective | Why it matters |
|---|---|
| Understand data properties | Center, spread, skewness, outliers, missingness |
| Find patterns and relationships | Candidate predictors and nonlinearities |
| Evaluate hypotheses | Does the data support the analyst's intuition? |
| Guide feature selection | Remove noisy or irrelevant inputs |
| Guide feature engineering | Transform, combine, or decompose variables |
| Communicate with stakeholders | Visuals help domain experts and data scientists align |

EDA is not just visual decoration. It is model design work.

## Structured Data EDA

Structured data has rows and columns. Each row is an observation; each column is a feature.

For one feature, common tools include:

| Tool | What it shows |
|---|---|
| Summary statistics | Mean, median, standard deviation, skewness, kurtosis |
| Histogram | Frequency in equal-width bins |
| Density plot | Smoothed distribution |
| Box plot | Median, quartiles, interquartile range, outliers |
| Bar chart | Frequency distribution for categorical variables |

For multiple features:

| Tool | What it shows |
|---|---|
| Scatterplot | Relationship between two continuous variables |
| Correlation matrix | Pairwise linear relationships |
| Heat map | Color-coded intensity of relationships or missingness |
| Multiple box plots | Distribution comparisons across groups |
| ANOVA / t-tests | Parametric comparisons |
| Spearman / chi-square | Nonparametric or categorical relationships |

## Box Plot Outlier Fences

A box plot uses the interquartile range:

$$
IQR = Q3-Q1
$$

A common upper fence is:

$$
Q3+1.5(IQR)
$$

and a common lower fence is:

$$
Q1-1.5(IQR)
$$

Values outside the fences are flagged as potential outliers.

## Worked Example: Box Plot Fence

Suppose P/E ratios in a sector have:

$$
Q1=12.0
$$

$$
Q3=20.0
$$

Then:

$$
IQR=20.0-12.0=8.0
$$

Upper fence:

$$
20.0+1.5(8.0)=20.0+12.0=32.0
$$

Any P/E above 32.0 is flagged as a potential outlier.

## Text Data EDA

Unstructured text needs different exploration tools. After [[Text-Based Data for Financial Forecasting|tokenization and preprocessing]], analysts examine token-level patterns.

| Text EDA tool | Meaning |
|---|---|
| Term frequency | How often a token appears |
| Co-occurrence | Which words appear together |
| Word cloud | Visual display where word size reflects frequency |
| Average sentence length | Readability and complexity proxy |
| Token frequency by class | Which words differ across positive/negative or default/non-default labels |

Word clouds are useful for quick human inspection, but frequency alone does not prove predictive value.

## Worked Example: Term Frequency

Suppose a financial-news corpus has 50,000 total words:

| Token | Count | Term frequency | Interpretation |
|---|---:|---:|---|
| `million` | 2,100 | $2{,}100/50{,}000=4.2\%$ | Too common; likely low discrimination |
| `Zahariev` | 2 | $2/50{,}000=0.004\%$ | Too rare; likely sparse noise |
| `default` | 350 | $350/50{,}000=0.7\%$ | Potentially useful credit-risk token |

The most frequent word is not automatically the most useful feature. The rarest word is not automatically the strongest signal. EDA helps separate signal from frequency artifacts.

## EDA And Feature Work

EDA feeds directly into feature selection and feature engineering:

| EDA finding | Possible action |
|---|---|
| Highly skewed variable | Log transform |
| Many outliers | Investigate, winsorize, or use robust method |
| Highly correlated features | Remove redundant variable or use PCA |
| Categorical predictor | One-hot encode |
| Text phrase carries sentiment | Create n-gram |
| Stop words dominate text | Remove high-frequency low-signal terms |

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Treating EDA as optional | Jumps straight to model training | EDA guides feature and model choices |
| Frequency equals importance | Keeps high-frequency stop words | Check whether tokens discriminate outcomes |
| Ignoring domain expertise | Accepts spurious data-mined patterns | Use financial knowledge to judge plausibility |
| Confusing histogram and density plot | Treats smoothed distribution as raw bins | Histogram counts bins; density smooths |
| Ignoring outliers in visuals | Lets extreme values distort model | Investigate box plot and scatterplot outliers |

## Memory Hooks

**EDA tells you what the model is about to learn.**

**Structured data: distributions and relationships. Text data: tokens and co-occurrences.**

**Frequency is visibility, not necessarily usefulness.**

## Related Concepts

- [[Big Data Project Workflow and Model Training]]
- [[Data Cleansing Wrangling and Scaling]]
- [[Text-Based Data for Financial Forecasting]]
- [[Text Feature Selection]]
- [[Principal Component Analysis]]
- [[Dimensionality Reduction]]
- [[Confusion Matrix]]
