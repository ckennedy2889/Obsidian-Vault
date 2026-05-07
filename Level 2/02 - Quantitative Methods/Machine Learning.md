---
title: "CFA L2 - Machine Learning"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, unsupervised-learning, LASSO, random-forest, neural-networks]
aliases: ["Module 3", "ML", "Supervised Learning", "Unsupervised Learning", "LASSO", "Random Forest"]
---

# Module 3 — Machine Learning

## The Pattern-Finding Revolution

Traditional finance models require a human analyst to specify the relationship: "I think earnings growth, interest rates, and leverage predict stock returns, so I'll build a regression with those three variables." The analyst decides what matters before looking at the data.

**[[Machine Learning]]** flips this approach. Instead of hand-coding relationships, you feed the algorithm massive amounts of data and let it discover the patterns on its own. You don't tell it what to look for — it figures out what predicts what, often finding relationships no human analyst thought to test.

Think of it this way: traditional regression is like giving a child a recipe book and having them follow instructions. Machine learning is like letting that child taste thousands of dishes and gradually learn what flavors go together, without ever reading a recipe.

---

## The Fundamental Split: Supervised vs. Unsupervised

All machine learning algorithms divide into two philosophies depending on whether they learn from "labeled" examples.

### Supervised Learning: Learning with a Teacher

You give the algorithm a dataset where you already know the answers — the **target variable (Y)** is labeled.

```
Training data:
  Company | Debt/Equity | Revenue Growth | ROE | → Outcome
  ────────┼─────────────┼────────────────┼─────┼──────────
  Firm A  |    0.3      |     15%        | 18% | → No default (0)
  Firm B  |    2.8      |     -5%        |  3% | → Default (1)
  Firm C  |    1.1      |     8%         | 11% | → No default (0)
  ...

The algorithm learns the pattern: high D/E + negative growth + low ROE → default
When it sees a new firm, it applies that learned pattern to predict the outcome.
```

The algorithm's job: learn the mapping from **features (X)** to **target (Y)** well enough to predict Y for new observations it has never seen.

**Finance examples of supervised learning:**
- Predicting whether a bond will default (classification: yes/no)
- Forecasting next quarter's earnings (regression: a number)
- Identifying which analyst estimates will be the most accurate (ranking)
- Classifying whether an earnings call transcript is positive or negative (classification)

### Unsupervised Learning: Discovery Without Labels

You give the algorithm data with no labels — no "correct answer." Its job is to find **hidden structure**: natural groupings, patterns, or relationships within the data itself.

```
Input data (no labels):
  Company | P/E | Debt | Revenue Growth | Volatility
  ────────┼─────┼──────┼────────────────┼──────────
  Firm A  | 35  | Low  |    20%         |  High
  Firm B  |  8  | High |    -2%         |  Low
  Firm C  | 32  | Low  |    18%         |  High
  Firm D  |  9  | High |    -4%         |  Low
  ...

Algorithm discovers two natural clusters:
  Group 1 (A, C): High P/E, Low debt, High growth, High volatility → "Growth stocks"
  Group 2 (B, D): Low P/E, High debt, Negative growth, Low volatility → "Value stocks"
```

Nobody told the algorithm "these are growth stocks." It discovered the natural groupings from the data patterns.

**Finance examples of unsupervised learning:**
- Clustering stocks into peer groups based on actual price behavior (not predefined sectors)
- Reducing 2,000 economic variables to a few key underlying "factors" (PCA)
- Finding unusual trading patterns that don't fit any known cluster (anomaly detection)

---

## The Bias-Variance Tradeoff: The Central Challenge

### What Is Overfitting?

The biggest danger in machine learning is building a model that is **too fitted to the specific quirks of your training data**. It learns the signal AND the noise — it memorizes the past instead of understanding it.

```
Stock return prediction:

Underfitting (too simple):          Overfitting (too complex):
Y │                                 Y │    ●  ●
  │                                   │  ●    ●    ●
  │     ─────────────────             │● ● ●    ●   ●●● ●
  │   ●  ● ●  ●  ●  ●   ●            │●          ●
  │ ●      ●       ●  ●              │●
  └──────────────────── X            └──────────────────── X
  Flat line — misses real trend      Wiggles through every point
  Low training error?  No            Low training error?  Very low!
  Low test error?  No                Low test error?  No! It memorized noise

Just right (generalization):
Y │
  │       ───────────
  │   ───           ───
  │─── ●  ●  ● ●  ●    ─
  └──────────────────── X
  Captures the trend without
  chasing individual data points
```

### Bias Error vs. Variance Error

Every model's prediction error consists of two components:

**Bias error** — error from wrong assumptions (underfitting)
- The model is too simple to capture the real pattern
- It consistently misses in the same direction
- Example: using a straight line to fit a curved relationship

**Variance error** — error from sensitivity to small fluctuations ([[Overfitting|overfitting]])
- The model is too complex; it flits around with every new dataset
- Small changes in training data cause large changes in predictions
- Example: a complex polynomial that fits the training set perfectly but fails on new data

```
Bias-Variance Tradeoff:

Error
│ ●  Total Error
│  ● ● ●
│      ● ● ●
│           ● ● ●
│      ────       ──── Variance
│ ────              ──── Bias
└───────────────────────── Model Complexity
  Simple →          ← Complex
  High bias          High variance
  (underfitting)     (overfitting)
         ↑
     Sweet spot
```

The goal is to find the **sweet spot** where the model captures the real structure without memorizing the noise.

### Regularization: Adding a Penalty for Complexity

**[[Regularization]]** is the main weapon against overfitting. It adds a mathematical **penalty** to the model's objective function for each additional variable or coefficient:

$$\text{Objective} = \text{Fit the data} - \text{Penalty for complexity}$$

Two dominant regularization approaches:

**[[Ridge regression]] (L2 regularization):**
$$\text{Minimize: } \sum(Y_i - \hat{Y}_i)^2 + \lambda\sum b_j^2$$

Penalizes large coefficients. Shrinks all coefficients toward zero but doesn't eliminate any.

**[[LASSO]] (Least Absolute Shrinkage and Selection Operator — L1 regularization):**
$$\text{Minimize: } \sum(Y_i - \hat{Y}_i)^2 + \lambda\sum |b_j|$$

Penalizes the absolute value of coefficients. Can shrink some coefficients **all the way to zero**, effectively performing automatic **variable selection**. LASSO chooses the most important variables for you.

| Method | Effect | When to Use |
|--------|--------|-------------|
| **Ridge** | Shrinks all coefficients toward zero | All variables might matter, but you want smaller coefficients |
| **LASSO** | Sets unimportant coefficients exactly to zero | You have many potential variables and want automatic selection |

**Finance example:** You have 500 potential factors that might explain [[Hedge fund|hedge fund]] returns. LASSO automatically zeroes out the 490 irrelevant ones, leaving you with the 10 that actually matter — without you having to specify which.

---

## Key Supervised Learning Algorithms

### 1. Penalized Regression (LASSO/Ridge)

**The problem it solves:** When you have many correlated predictors (hundreds of financial ratios), traditional OLS breaks down due to [[CFA_Glossary/Multicollinearity]] and overfitting.

**How it works:** Standard linear regression with an added complexity penalty that shrinks or eliminates useless variables.

**Finance use:** Factor model construction — start with 100 candidate factors, let LASSO select the 5–10 that actually matter.

### 2. Support Vector Machines (SVM)

**The problem it solves:** Classifying data into two groups when the boundary between groups isn't obvious.

**How it works:** Find the **hyperplane** (a line in 2D, a plane in 3D, etc.) that separates the two groups with the **widest possible margin** — the largest "no man's land" between the two classes.

```
SVM Decision Boundary:

       ●●●                         ● = Class 1 (Default)
     ●●   ●●                       ○ = Class 2 (No Default)
    ●●     ●●   ← Maximum margin
  ─────────────── ← Decision boundary
    ○○     ○○
     ○○   ○○
       ○○○
```

**Finance use:** Credit risk classification — the SVM finds the clearest boundary separating companies that pay their debt from those that default.

### 3. CART — Classification and Regression Trees

**The problem it solves:** Capturing complex, nonlinear relationships through a series of yes/no decision rules.

**How it works:** The algorithm recursively splits the data into smaller subsets using simple threshold rules ("Is P/E > 25? If yes, go left. If no, go right.") until it reaches relatively pure groups.

```
Is D/E > 2.0?
      │
   ┌──┴──┐
  Yes    No
   │      │
Default   Is Revenue Growth < 0?
               │
           ┌───┴───┐
          Yes      No
           │        │
        Default    Safe
```

**Finance use:** Identifying "value traps" — stocks with low P/E but high debt. The tree structure naturally captures these interaction effects.

### 4. Random Forests

**The problem it solves:** A single CART decision tree is sensitive to the specific data it sees — small changes in training data can produce a very different tree. This is high variance.

**How it works:** Train hundreds of different decision trees (each on a slightly different random sample of the data and random subset of variables), then have them **vote** on the final prediction:

```
Training data
      │
 ┌────┼────┐ ← Randomly sample 3 different subsets
 │    │    │
Tree₁ Tree₂ Tree₃  ← Each trained independently
 │    │    │
 └────┼────┘
      │
  Majority vote (classification) or average (regression)
      │
   Final prediction  ← Much more stable than any single tree
```

The averaging effect dramatically reduces variance (overfitting) while maintaining low bias.

**Finance use:** Any complex classification or prediction problem where single models overfit — credit scoring, factor return prediction, ESG risk assessment.

### 5. Neural Networks (Brief Overview)

**Inspired by:** The human brain's network of neurons.

**Structure:** Input layer → hidden layers → output layer. Each "neuron" applies a non-linear transformation and passes the result to the next layer. Deep networks (many layers) can capture extraordinarily complex patterns.

**Finance use:** Image recognition (satellite data of retail foot traffic), speech recognition (earnings call transcripts), high-frequency price pattern detection.

**Trade-off:** Extremely powerful but computationally intensive and hard to interpret ("black box").

---

## Key Unsupervised Learning Algorithms

### K-Means Clustering

**Goal:** Sort data points into $K$ groups (clusters) where each point belongs to the cluster with the nearest "center" (centroid).

**How it works:**
1. Choose $K$ (number of clusters)
2. Randomly place $K$ centroids
3. Assign each data point to the nearest centroid
4. Recalculate each centroid as the mean of its assigned points
5. Repeat steps 3–4 until assignments stop changing

```
Before clustering:          After K=3 clustering:
  ●●●●      ■■■■              ●●●●      ■■■■
  ●●●●      ■■■■     →        ●●●●      ■■■■
            ▲▲▲▲                        ▲▲▲▲
            ▲▲▲▲                        ▲▲▲▲
  All mixed together          Three natural groups emerge
```

**Finance use:** A portfolio manager uses K-means to group stocks based on actual daily return patterns rather than sector labels. Two tech stocks that actually behave differently (one moves with interest rates, one moves with growth) end up in different clusters — a more honest picture of diversification.

### PCA — Principal Component Analysis

**Goal:** Reduce a large number of variables into a smaller number of "composite" factors (**principal components**) that capture most of the information.

**The problem it solves:** If you have 2,000 economic indicators, you can't use them all as regression inputs. Many are redundant (highly correlated). PCA finds the underlying structure.

**How it works:** PCA finds combinations of the original variables that explain the maximum variance in the data, in decreasing order. The first principal component explains the most variance, the second explains the next most, and so on.

```
Original variables: 100 financial ratios
      │
      ▼ PCA
PC₁: "Growth factor" = 0.4×Revenue Growth + 0.3×EPS Growth + 0.2×EBITDA Growth + ...
PC₂: "Leverage factor" = 0.5×Debt/Equity + 0.3×Interest Coverage + ...
PC₃: "Valuation factor" = 0.4×P/E + 0.3×P/B + 0.2×EV/EBITDA + ...

Three components explain 80% of variance across all 100 ratios
```

**Finance use:** Global macro analysis — 2,000 economic indicators reduced to 3 principal components: Growth, Inflation, and Financial Conditions. These three composite factors explain most of what drives market returns.

---

## Cross-Validation: Honest Model Evaluation

A model that memorizes training data will look great on training data but fail on new data. **Cross-validation** forces the model to be evaluated on data it has never seen.

### Hold-Out Method (Train/Validation/Test Split)

```
Full Dataset
├── Training Set (60%) → Model learns from this
├── Validation Set (20%) → Model is tuned using this (hyperparameter selection)
└── Test Set (20%) → Final exam — model sees this ONCE
```

The test set is sacred — you look at it only once, to get an unbiased final performance estimate.

### K-Fold Cross-Validation

A more robust approach when data is limited:

```
Dataset split into K=5 folds:
│  Fold 1  │  Fold 2  │  Fold 3  │  Fold 4  │  Fold 5  │

Round 1: Train on 2,3,4,5 → Validate on 1
Round 2: Train on 1,3,4,5 → Validate on 2
Round 3: Train on 1,2,4,5 → Validate on 3
Round 4: Train on 1,2,3,5 → Validate on 4
Round 5: Train on 1,2,3,4 → Validate on 5

Final performance = Average of 5 validation scores
```

Every data point is used for validation exactly once. This gives a much more reliable estimate of how the model will perform on new data.

---

## Selecting the Right Algorithm

| Algorithm | Best For | Interpretable? | Handles Nonlinearity? |
|-----------|---------|---------------|----------------------|
| LASSO/Ridge | High-dimensional data, variable selection | Yes | No |
| SVM | Binary classification with a clear boundary | No | With kernels |
| CART | Interpretable rules, nonlinear interactions | Yes | Yes |
| Random Forest | Accuracy, robustness, large datasets | No | Yes |
| Neural Networks | Complex patterns, image/text data | No | Yes (very) |
| K-Means | Finding clusters, peer groups | Yes | Yes |
| PCA | Dimensionality reduction, factor discovery | Partial | No |

---

## Exam Traps

> [!danger] Common Mistakes
> - **Supervised vs. unsupervised**: Supervised = labeled target variable exists; unsupervised = no labels
> - **Overfitting = high training accuracy, low test accuracy** — the model memorized noise
> - **LASSO can zero out variables** (unlike Ridge, which only shrinks them)
> - **Random Forest = many trees voting** — reduces variance compared to a single tree
> - **Cross-validation prevents overfitting evaluation** — always evaluate on held-out data
> - **AUC = 0.5 is useless** — no better than random; higher is better

---

## Related Concepts

- [[Big Data Projects]] — the practical pipeline for deploying ML in finance
- [[Logistic Regression]] — the simplest supervised classification algorithm
- [[Extensions of Multiple Regression]] — the bridge between classical regression and ML
- [[Overfitting]] — the central challenge in ML
- [[LASSO]] — penalized regression for variable selection
- [[Model Misspecification]] — what can go wrong in classical models (ML tries to avoid the same)
- [[Time-Series Analysis]] — classical time-series methods vs. ML alternatives
