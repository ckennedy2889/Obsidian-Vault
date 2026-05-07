---
title: Dimensionality Reduction
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, unsupervised-learning, dimensionality-reduction]
aliases: [Dimension reduction, Dimensional reduction, Reducing dimensionality, Feature dimension reduction]
---

# Dimensionality Reduction

## The Real-World Analogy

Imagine you are listening to an orchestra with 100 instruments.

You could track every single violin, flute, trumpet, and drum separately. But if you are trying to understand the music quickly, that is too much detail.

Instead, you might summarize the sound into a few big forces:

```text
Melody
Harmony
Rhythm
Volume
```

You lose some detail, but you keep the main structure.

That is [[Dimensionality Reduction]].

In finance, the "orchestra" might be 2,000 economic indicators, hundreds of stock characteristics, or thousands of text-based features. Many of those variables overlap. Some are noisy. Some are redundant. Some are saying almost the same thing in different units.

Dimensionality reduction asks:

> Can we replace many features with fewer features while preserving most of the important information?

The CFA version is usually:

```text
Many correlated features
  |
  v
Dimensionality reduction
  |
  v
Fewer composite features
  |
  v
Most variance retained, less noise and complexity
```

## One-Minute Version

[[Dimensionality Reduction]] is an [[unsupervised learning]] technique that reduces the number of features in a dataset.

It is used when a dataset has too many variables, especially when many of those variables are correlated, redundant, noisy, or hard to visualize.

The primary CFA method is [[Principal Component Analysis]] (PCA).

PCA transforms many correlated original features into fewer uncorrelated composite variables called [[principal component|principal components]].

The goal is not to predict a target variable directly.

The goal is to simplify the feature space while preserving most of the variation in the original data.

```text
Original data:
X1, X2, X3, X4, X5, ..., X500

After dimensionality reduction:
PC1, PC2, PC3

Result:
Fewer inputs, most information retained
```

The core exam distinctions:

| Concept | What it does |
|---|---|
| Dimensionality reduction | Reduces features or columns |
| [[Clustering]] | Groups observations or rows |
| [[Principal Component Analysis]] | Main CFA dimensionality reduction method |
| [[LASSO]] | Supervised feature selection by shrinking coefficients to zero |
| [[Feature selection]] | Keeps a subset of original variables |
| PCA | Creates new composite variables |

## LOS Coverage

Dimensionality reduction belongs in the CFA Level II [[Quantitative Methods]] machine learning reading.

The relevant LOS asks you to describe unsupervised machine learning algorithms, including [[Principal Component Analysis]], [[K-Means Clustering]], and [[Hierarchical Clustering]], and determine the problems for which they are best suited.

For dimensionality reduction, you should be able to:

| CFA task | What you need to know |
|---|---|
| Identify the learning type | Unsupervised learning |
| Identify the main algorithm | PCA |
| Explain the problem solved | Too many correlated, noisy, or redundant features |
| Explain the output | Fewer composite variables, usually principal components |
| Explain the benefit | Easier visualization, faster model training, less overfitting |
| Explain the cost | Some information loss and lower interpretability |
| Distinguish from clustering | Reduction changes feature space; clustering groups observations |

## The Big Idea

Dimensionality means the number of features in the dataset.

If a dataset has 5 features, it has 5 dimensions.

If a dataset has 500 features, it has 500 dimensions.

In machine learning, a feature is an input variable:

```text
Features = X variables
Target   = Y variable
```

Examples of features:

| Dataset | Possible features |
|---|---|
| Equity model | P/E, P/B, ROE, margins, leverage, momentum |
| Bond model | duration, spread, rating, leverage, maturity, coupon |
| Macro model | GDP growth, CPI, unemployment, PMI, credit spreads |
| Text model | word counts, phrase counts, sentiment scores |

The problem is that modern datasets can have hundreds or thousands of features.

That creates complexity.

But the deeper issue is not just "many variables."

The deeper issue is:

> Many variables may not contain independent information.

They may overlap.

For example:

```text
Revenue growth
EBITDA growth
EPS growth
Operating cash flow growth
Industrial production
PMI
New orders
```

These are different variables, but they may all partly reflect the same underlying idea:

```text
Economic growth conditions
```

Dimensionality reduction tries to extract the smaller number of underlying signals from the large number of noisy measured variables.

## Why High Dimensionality Is a Problem

High dimensionality creates several problems.

| Problem | Why it matters |
|---|---|
| Noise | Many features may reflect random dataset-specific quirks |
| Redundancy | Correlated features repeat the same information |
| Complexity | Models become harder to train and understand |
| Visualization problem | Humans cannot visualize 50-dimensional space |
| Overfitting | Models may memorize noise rather than learn durable structure |
| Computation | More features can slow training and evaluation |

The central mechanism:

```text
Too many features
  |
  v
More ways to fit random patterns
  |
  v
Higher risk of overfitting
  |
  v
Poorer out-of-sample performance
```

Why does this happen?

Because every additional feature gives the model another axis along which it can separate, fit, or explain the training data.

Some features contain useful signal.

Some contain noise.

If the model has too many noisy inputs, it may find relationships that exist only by accident in the training sample.

This is one version of the [[curse of dimensionality]].

The phrase means that as the number of dimensions rises, data become sparse in the feature space and patterns become harder to learn reliably.

The intuition:

```text
Low dimensions:
Observations are close enough to compare.

High dimensions:
Observations spread out across many axes.
Distance, similarity, and pattern detection become harder.
```

## Why Dimensionality Reduction Is Unsupervised

Dimensionality reduction is usually classified as [[unsupervised learning]].

Why?

Because it does not require a labeled target variable.

It looks only at the features:

```text
X1, X2, X3, ..., Xp
```

It does not ask:

```text
Which variables best predict Y?
```

It asks:

```text
What structure exists among the X variables themselves?
```

That distinction is critical.

If the algorithm uses $Y$ to decide which variables matter, it is supervised feature selection.

If the algorithm does not use $Y$ and instead summarizes the structure of the features, it is unsupervised dimensionality reduction.

## PCA as the Main CFA Method

The primary CFA dimensionality reduction method is [[Principal Component Analysis]].

PCA takes many correlated features and transforms them into fewer uncorrelated composite variables.

The output variables are called principal components.

Each principal component is a weighted combination of the original variables:

$$
PC_1 = w_1X_1 + w_2X_2 + w_3X_3 + \cdots + w_pX_p
$$

The weights are chosen so that:

| Component | What it captures |
|---|---|
| PC1 | Largest possible amount of variance |
| PC2 | Largest remaining variance, uncorrelated with PC1 |
| PC3 | Next-largest remaining variance, uncorrelated with earlier PCs |

The high-level flow:

```text
Many correlated variables
  |
  v
PCA studies covariance/variance structure
  |
  v
Creates principal components
  |
  v
Ranks components by variance explained
  |
  v
Keep the first few components
```

This is dimensionality reduction because the analyst may replace 500 original features with 3 or 5 principal components.

## Why Variance Matters

PCA tries to preserve variance.

Why variance?

Because variance is a measure of how much the data move, spread, or differ.

If a direction in the data has high variance, it captures a lot of the dataset's movement.

If a direction has tiny variance, it may add little information.

The PCA logic is:

```text
Information in dataset
  |
  v
Often visible as variation
  |
  v
Find directions that explain the most variation
  |
  v
Keep those directions
```

This does not mean high variance is always economically meaningful.

That is one of the limitations.

PCA is mathematical. It does not know whether a component is "growth," "inflation," "credit stress," or "noise." The analyst must interpret the components after seeing their loadings.

## Eigenvectors and Eigenvalues

PCA uses two ideas from linear algebra: eigenvectors and eigenvalues.

For CFA, the conceptual meaning is enough.

| Term | Meaning in PCA |
|---|---|
| [[Eigenvector]] | Direction of a principal component |
| [[Eigenvalue]] | Amount or proportion of total variance explained by that component |

Think of an eigenvector as an arrow through the cloud of data.

Think of the eigenvalue as the importance score attached to that arrow.

```text
Eigenvector = direction
Eigenvalue  = variance explained
```

PCA ranks components from highest eigenvalue to lowest eigenvalue.

The first principal component has the largest eigenvalue.

The second principal component has the second-largest eigenvalue.

And so on.

## Standardization

CFA notes that data should often be standardized before PCA.

Standardization usually means transforming each feature so it has:

```text
Mean = 0
Standard deviation = 1
```

Why?

Because PCA is based on variance.

If one variable is measured in billions of dollars and another is measured as a percentage, the dollar variable may have much larger raw variance.

Without standardization, PCA may treat the large-scale variable as important simply because of its units.

Example:

| Feature | Unit | Raw scale issue |
|---|---|---|
| Market capitalization | Dollars | Huge numerical range |
| Profit margin | Percent | Smaller numerical range |
| Dividend yield | Percent | Smaller numerical range |

If raw market cap dominates PC1, that may be a measurement-unit artifact, not a true information signal.

The mechanism:

```text
Unscaled variables
  |
  v
Large-unit variables dominate variance
  |
  v
PCA components reflect scale more than information
  |
  v
Misleading dimension reduction
```

## Scree Plot and the 85%-95% Rule

A [[scree plot]] shows the proportion of total variance explained by each principal component.

The analyst uses it to decide how many components to keep.

CFA notes that, in practice, analysts often retain the smallest number of principal components that collectively explain about 85% to 95% of total variance.

Why not keep every component?

Because keeping every component defeats the purpose of dimensionality reduction.

Why not keep only one component?

Because one component may throw away too much information.

The trade-off:

| Keep fewer components | Keep more components |
|---|---|
| Simpler model |
| Easier visualization |
| More information loss |
| More complete information |
| Less information loss |
| Less reduction in complexity |

The decision is a balance:

```text
Simplification benefit
vs.
Information loss cost
```

## Worked Numerical Example

Suppose an analyst starts with 20 financial ratios.

The analyst runs PCA and gets the following variance explained:

| Component | Variance explained | Cumulative variance |
|---|---:|---:|
| PC1 | 45% | 45% |
| PC2 | 25% | 70% |
| PC3 | 15% | 85% |
| PC4 | 7% | 92% |
| PC5 | 3% | 95% |
| Remaining PCs | 5% total | 100% |

If the analyst wants at least 85% of variance:

```text
PC1 + PC2 + PC3 = 45% + 25% + 15% = 85%
```

So the analyst can reduce:

```text
20 original ratios
  |
  v
3 principal components
```

while retaining 85% of the variance.

If the analyst wants at least 90%:

```text
PC1 + PC2 + PC3 = 85%
```

That is not enough.

Add PC4:

```text
85% + 7% = 92%
```

So for a 90% threshold, the analyst keeps 4 components.

The key exam move:

> Keep the smallest number of components that reaches the desired variance threshold.

## Why Dimensionality Reduction Helps Later Models

Dimensionality reduction is often performed during [[exploratory data analysis]], before training another supervised or unsupervised learning model.

It can help because lower-dimensional datasets are easier to work with.

| Benefit | Why it happens |
|---|---|
| Faster training | Fewer inputs reduce computational burden |
| Less overfitting | Fewer noisy dimensions reduce ways to memorize randomness |
| Easier visualization | Data can be plotted in 2D or 3D |
| Reduced multicollinearity | PCA components are uncorrelated |
| Better data exploration | Major patterns become easier to see |

The deep chain:

```text
Too many correlated features
  |
  v
Noise, redundancy, multicollinearity, sparse feature space
  |
  v
PCA creates fewer uncorrelated components
  |
  v
Model sees a cleaner representation of the data
  |
  v
Training may become faster and less overfit
```

Important nuance:

PCA does not guarantee better predictive performance.

It can improve a later model if the removed dimensions were mostly noise or redundancy.

It can hurt a later model if discarded components contained predictive information.

Why?

Because PCA preserves variance, not necessarily predictive power.

That is a subtle but important point.

The component that explains the most variance in $X$ is not automatically the component that best predicts $Y$.

## Visualization

Dimensionality reduction can make high-dimensional data visible.

Humans can visualize:

```text
1 dimension: line
2 dimensions: plane
3 dimensions: space
```

Humans cannot directly visualize:

```text
50 dimensions
500 dimensions
2,000 dimensions
```

PCA can reduce many variables to two or three components, allowing scatterplots or other visual exploration.

Example:

```text
500 stock features
  |
  v
PC1 and PC2
  |
  v
2D plot
```

This can reveal patterns, clusters, outliers, or regimes that were hidden in the original feature set.

## Dimensionality Reduction vs Clustering

Dimensionality reduction and clustering are both unsupervised, but they answer different questions.

| Concept | Question answered | What changes |
|---|---|---|
| Dimensionality reduction | Can we represent many features with fewer features? | Columns/features |
| [[K-Means Clustering]] | Which observations belong together? | Rows/observations |
| [[Hierarchical Clustering]] | What nested similarity groups exist? | Rows/observations |

Memory hook:

```text
Dimensionality reduction reduces columns.
Clustering groups rows.
```

Example:

Suppose you have 1,000 stocks and 200 features per stock.

Dimensionality reduction asks:

```text
Can 200 features be summarized by 5 components?
```

Clustering asks:

```text
Can 1,000 stocks be grouped into similar stock clusters?
```

They can be used together.

For example:

```text
Step 1: Use PCA to reduce 200 features to 5 components.
Step 2: Use K-means to cluster stocks using those 5 components.
```

## Dimensionality Reduction vs Feature Selection

Dimensionality reduction is not the same as feature selection.

| Concept | What happens to original features? | Uses target variable? | Output |
|---|---|---|---|
| PCA dimensionality reduction | Original features are transformed into new components | No | New composite variables |
| Feature selection | Some original features are kept, others removed | Sometimes yes | Subset of original variables |
| [[LASSO]] | Original features with zero coefficients are excluded | Yes | Selected original predictors |

Feature selection says:

```text
Keep X1, X4, X9.
Drop X2, X3, X5.
```

PCA says:

```text
Create PC1, PC2, PC3 as weighted combinations of all original X variables.
```

That is why PCA can be harder to interpret.

With feature selection, if P/E is kept, you can say P/E mattered.

With PCA, if PC2 is kept, PC2 may be a blend of P/E, P/B, ROE, leverage, and momentum.

The component may be useful, but the label is not obvious.

## Dimensionality Reduction vs LASSO

[[LASSO]] and dimensionality reduction both try to simplify models, but they are different tools.

| Feature | PCA dimensionality reduction | LASSO |
|---|---|---|
| Learning type | Unsupervised | Supervised |
| Uses target $Y$? | No | Yes |
| Main mechanism | Creates components from features | Shrinks some coefficients to zero |
| Output | New composite variables | Smaller set of original variables |
| Interpretability | Lower | Higher than PCA because selected variables remain original |
| CFA use case | Many correlated features, exploratory reduction | Prediction model with feature selection |

The deep difference:

```text
PCA asks:
What structure exists among the X variables?

LASSO asks:
Which X variables help predict Y enough to survive the penalty?
```

## The Black-Box Drawback

The main drawback of PCA-based dimensionality reduction is interpretability.

Principal components are combinations of original variables.

A component might look like:

$$
PC_1 = 0.42X_1 + 0.39X_2 + 0.31X_3 - 0.28X_4 + \cdots
$$

That component may explain a lot of variance, but it may not have a clean economic label.

The analyst might infer that PC1 represents "growth" or "financial conditions," but that label is interpretation, not the PCA algorithm's output.

This is why CFA describes PCA as potentially black-box.

The trade-off:

```text
More compression
  |
  v
Fewer variables
  |
  v
Often less direct interpretation
```

## Finance Applications

| Application | How dimensionality reduction helps |
|---|---|
| Macro modeling | Reduce thousands of indicators to a few macro factors |
| Equity modeling | Summarize many correlated fundamental and technical features |
| Portfolio risk models | Estimate covariance structure with fewer factors |
| Yield curve analysis | Summarize curve movements into level, slope, and curvature-like components |
| Text analysis | Reduce high-dimensional token features before modeling |
| Exploratory data analysis | Visualize high-dimensional datasets in 2D or 3D |

In portfolio management, PCA is also related to statistical factor models. It can extract components that explain the variance of asset returns.

In fixed income, PCA often reveals yield curve movements that analysts interpret as:

```text
Level
Slope
Curvature
```

But the caution remains:

PCA produces mathematical components. The analyst supplies the economic interpretation.

## Common Wrong Reasoning

### Wrong: "Dimensionality reduction groups observations."

Why it is wrong: That describes clustering. Dimensionality reduction reduces or transforms features.

Correct idea:

```text
Dimensionality reduction -> columns/features
Clustering -> rows/observations
```

### Wrong: "PCA is supervised because it can help a predictive model."

Why it is wrong: PCA itself does not use the target variable. It can be used before supervised modeling, but PCA remains unsupervised.

Correct idea:

```text
Uses Y -> supervised
Does not use Y -> unsupervised
```

### Wrong: "The first principal component is the best predictor."

Why it is wrong: The first principal component explains the most variance in the features. It is not necessarily the best predictor of the target.

Correct idea:

```text
PCA preserves variance in X, not predictive power for Y.
```

### Wrong: "PCA selects the most important original variables."

Why it is wrong: PCA creates new composite variables. It does not simply choose original variables.

Correct idea:

```text
Feature selection keeps original variables.
PCA transforms variables into components.
```

### Wrong: "Keeping all principal components is safest."

Why it is wrong: Keeping all components preserves all variance but eliminates the reduction benefit.

Correct idea:

```text
Keep the smallest number of components that captures the desired variance threshold.
```

### Wrong: "Standardization is optional trivia."

Why it is wrong: PCA is based on variance. Unstandardized high-scale variables can dominate the components.

Correct idea:

```text
Scale can change what PCA thinks is important.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Many correlated features | Dimensionality reduction or PCA |
| Too many variables make model noisy | Dimensionality reduction |
| Need fewer uncorrelated composite variables | PCA |
| Eigenvectors and eigenvalues | PCA |
| Scree plot | Choose number of components |
| 85%-95% variance retained | Keep smallest number of components reaching threshold |
| No target variable | Unsupervised learning |
| Group observations by similarity | Clustering, not dimensionality reduction |
| Select original predictors using $Y$ | Feature selection or LASSO, not PCA |
| Need easy economic interpretation | PCA may be a poor choice |

## Minimum Memorization

```text
Dimensionality reduction = reduce number of features

CFA main method = PCA

PCA:
Many correlated features
  -> fewer uncorrelated principal components
  -> ordered by variance explained

Unsupervised:
No target Y is used

Scree plot:
Choose smallest number of PCs that explain desired variance
Often 85%-95%

Main drawback:
Components can be hard to interpret
```

Most important distinction:

```text
Dimensionality reduction reduces columns.
Clustering groups rows.
```

And:

```text
PCA transforms variables.
Feature selection selects variables.
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. What does "dimensionality" mean in a dataset?
2. Why do too many features create noise and overfitting risk?
3. Why is dimensionality reduction usually unsupervised?
4. What is the main CFA algorithm for dimensionality reduction?
5. What does PCA do to correlated features?
6. Why does PCA care about variance?
7. What do eigenvectors and eigenvalues mean conceptually?
8. Why should data often be standardized before PCA?
9. How does a scree plot help choose the number of components?
10. Why is 85%-95% variance explained a common rule of thumb?
11. How is dimensionality reduction different from clustering?
12. How is PCA different from feature selection?
13. How is PCA different from LASSO?
14. Why can PCA be considered black-box?
15. Why is the first principal component not necessarily the best predictor of $Y$?

## Related Concepts

- [[Machine Learning]]
- [[Unsupervised learning]]
- [[Dimensionality Reduction]]
- [[Principal Component Analysis]]
- [[Principal Component Analysis]]
- [[Principal component]]
- [[Eigenvector]]
- [[Eigenvalue]]
- [[Variance]]
- [[Covariance matrix]]
- [[Scree plot]]
- [[Curse of dimensionality]]
- [[Feature selection]]
- [[Feature engineering]]
- [[LASSO]]
- [[K-Means Clustering]]
- [[Hierarchical Clustering]]
- [[Clustering]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- [[Overfitting]]
- [[Exploratory data analysis]]
- [[Statistical factor model]]
