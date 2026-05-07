---
title: Principal Component Analysis
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, unsupervised-learning, dimensionality-reduction]
aliases: [PCA, Principal Components Analysis, Principal Component Analysis, Principal Components, Principal Components Analysis (PCA)]
---

# Principal Component Analysis

> [[Principal Component Analysis]] (PCA) is an [[unsupervised learning]] algorithm used for [[Dimensionality Reduction]]. It transforms many correlated features into a smaller number of uncorrelated composite variables called [[principal component|principal components]], ordered by how much [[variance]] they explain.

## The Real-World Analogy

Imagine you are looking at 2,000 economic indicators.

Many are saying almost the same thing:

```text
Industrial production
Manufacturing PMI
New orders
Capacity utilization
Freight volumes
```

They are not identical, but they all partly whisper the same underlying idea:

```text
"Growth conditions"
```

Other variables whisper:

```text
"Inflation pressure"
"Financial conditions"
"Credit stress"
```

PCA is the tool that listens to the noisy crowd of variables and tries to extract the few big hidden voices.

It does not ask:

```text
Which variable predicts returns?
```

It asks:

```text
Can many correlated variables be summarized by fewer uncorrelated composite variables
while preserving most of the variation in the data?
```

That is why PCA is not prediction first. It is compression first.

## One-Minute Version

PCA reduces a high-dimensional dataset to a smaller set of [[principal component|principal components]].

Each principal component is a linear combination of the original features:

$$
PC_1 = w_1x_1 + w_2x_2 + w_3x_3 + \cdots + w_kx_k
$$

The first principal component explains the largest possible amount of variance in the original data. The second principal component explains the largest remaining variance and is uncorrelated with the first. The third explains the next-largest remaining variance, and so on.

The core CFA idea:

```text
Many correlated variables
  |
  v
PCA
  |
  v
Fewer uncorrelated composite variables
  |
  v
Most variance retained, less noise and complexity
```

PCA is useful for exploratory data analysis, reducing noise, visualizing high-dimensional data, improving model training speed, reducing overfitting from too many features, and building statistical factor models.

Its weakness: principal components are mathematical combinations of variables and often cannot be easily labeled or interpreted. That makes PCA somewhat black-box.

## LOS Coverage

PCA sits in the CFA Level II Quantitative Methods machine learning LOS:

| LOS language | What you must be able to do |
|---|---|
| Describe [[supervised learning]], [[unsupervised learning]], and [[deep learning]] | Know that PCA is unsupervised because it uses features without a target variable |
| Describe unsupervised machine learning algorithms, including PCA, [[K-Means Clustering]], and [[Hierarchical Clustering]] | Explain PCA as dimension reduction, not clustering |
| Determine the problems for which unsupervised algorithms are best suited | Choose PCA when many correlated features need to be reduced to fewer uncorrelated composite variables |

## The Big Idea

PCA solves the too-many-overlapping-variables problem.

Suppose you have 100 variables:

```text
Revenue growth
EPS growth
EBITDA growth
Operating margin growth
Capex growth
Inventory growth
Employment growth
PMI
Industrial production
...
```

Many are correlated. That creates three practical problems:

| Problem | Why it matters |
|---|---|
| Noise | Many variables may contain duplicated or weak information |
| Complexity | Too many features make models harder to train and interpret |
| Multicollinearity | Highly correlated features can make model estimates unstable |

PCA tries to replace the original crowded feature set with fewer composite variables.

Instead of:

```text
100 original correlated features
```

PCA might produce:

```text
PC1: broad growth factor
PC2: inflation factor
PC3: financial conditions factor
PC4: credit stress factor
```

Those labels are analyst interpretations. The math itself only produces components.

## The Deep Why: Why PCA Looks For Variance

PCA is trying to preserve information.

But what is "information" in this context?

CFA frames it as variation in the data.

If a variable barely moves, it does not help explain differences across observations. If a direction through the data captures a lot of movement, that direction contains a lot of information about how the observations differ.

So PCA asks:

```text
Which direction through the data captures the maximum spread?
```

That direction is the first principal component.

Then PCA asks:

```text
After removing what PC1 captured, which new uncorrelated direction captures the most remaining spread?
```

That direction is the second principal component.

Then it repeats.

This is the intuition:

```text
PC1 = direction of maximum variance
PC2 = next-best direction, uncorrelated with PC1
PC3 = next-best direction, uncorrelated with PC1 and PC2
```

Why uncorrelated?

Because PCA is trying to remove redundancy. If PC2 were highly correlated with PC1, it would be repeating information PC1 already captured.

## Geometric Intuition

Imagine data points scattered in two dimensions:

```text
       *
     *
   *
 *
*
```

The points mostly stretch along a diagonal direction.

PCA says:

```text
Use the diagonal as PC1.
```

Why?

Because projecting the points onto that diagonal preserves most of the spread.

```text
Data cloud:

       *
     *
   *
 *
*

PC1 direction:

      /
     /
    /
   /
  /
```

The direction perpendicular to PC1 captures the leftover variation. That becomes PC2.

```text
PC2 is at right angles to PC1.
That makes PC2 uncorrelated with PC1.
```

In three dimensions, PCA can find a plane. In 100 dimensions, you cannot visualize it, but the same logic holds.

## Projection Error and Spread

CFA describes PCA as balancing two linked ideas:

| Idea | Meaning |
|---|---|
| Minimize projection error | Keep each point close to its lower-dimensional representation |
| Maximize spread/variance along the component | Preserve as much information as possible |

If you reduce a 3D dataset to one line, each point gets projected onto the line. The vertical distance from the point to the line is projection error.

PCA chooses the line that:

```text
Minimizes projection error
and
Maximizes spread along the line
```

Those are two sides of the same idea: choose the lower-dimensional representation that loses the least information.

## Covariance Matrix Intuition

PCA works through the [[covariance matrix]] of the features.

The covariance matrix tells us how variables move together.

For three variables:

```text
Revenue growth
EPS growth
EBITDA growth
```

the covariance matrix asks:

```text
Does revenue growth move with EPS growth?
Does EPS growth move with EBITDA growth?
Does revenue growth move with EBITDA growth?
```

If many variables move together, PCA tries to summarize that common movement with fewer components.

That is why PCA is especially useful when features are highly correlated.

## Eigenvectors and Eigenvalues

PCA has two key mathematical objects:

| Term | CFA meaning | Intuition |
|---|---|---|
| [[Eigenvector]] | Defines a new uncorrelated composite variable | A direction through the data |
| [[Eigenvalue]] | Proportion or amount of total variance explained by the eigenvector | How important that direction is |

An eigenvector gives the weights used to combine the original variables into a principal component.

An eigenvalue tells how much variance that component explains.

The first principal component has the largest eigenvalue.

The second principal component has the second-largest eigenvalue.

The algorithm orders components by eigenvalue:

```text
Largest eigenvalue -> PC1
Second largest -> PC2
Third largest -> PC3
```

## What A Principal Component Actually Is

A principal component is a weighted linear combination of the original variables.

Suppose the original variables are:

```text
x1 = revenue growth
x2 = EPS growth
x3 = EBITDA growth
```

A principal component could look like:

$$
PC_1 = 0.50x_1 + 0.60x_2 + 0.62x_3
$$

Interpretation:

The component loads positively on all three growth variables, so an analyst might call it a "growth factor."

But be careful:

PCA does not name it "growth factor." The analyst names it after inspecting the loadings.

That is why PCA can be hard to interpret.

## Worked Numerical Example: Variance Explained

Suppose PCA produces four principal components with these eigenvalues:

| Component | Eigenvalue |
|---|---:|
| PC1 | 4.8 |
| PC2 | 2.7 |
| PC3 | 1.5 |
| PC4 | 1.0 |

Total eigenvalues:

$$
4.8 + 2.7 + 1.5 + 1.0 = 10.0
$$

The proportion of variance explained by each component is:

$$
\text{Variance explained by PC}_i
= \frac{\lambda_i}{\sum \lambda}
$$

PC1:

$$
\frac{4.8}{10.0} = 0.48 = 48\%
$$

PC2:

$$
\frac{2.7}{10.0} = 0.27 = 27\%
$$

PC3:

$$
\frac{1.5}{10.0} = 0.15 = 15\%
$$

PC4:

$$
\frac{1.0}{10.0} = 0.10 = 10\%
$$

Cumulative variance:

| Components retained | Cumulative variance explained |
|---|---:|
| PC1 | 48% |
| PC1 + PC2 | 48% + 27% = 75% |
| PC1 + PC2 + PC3 | 48% + 27% + 15% = 90% |
| PC1 + PC2 + PC3 + PC4 | 100% |

If the analyst wants to retain 85%-95% of total variance, then keeping the first three components is reasonable:

$$
48\% + 27\% + 15\% = 90\%
$$

So PCA reduces four original dimensions to three components while retaining 90% of the variance.

## Worked Example: Composite Factor

Suppose PCA on macro variables produces:

$$
PC_1 = 0.45(\text{Industrial Production})
+ 0.40(\text{PMI})
+ 0.35(\text{Employment Growth})
+ 0.30(\text{Retail Sales})
$$

All loadings are positive and related to real activity.

An analyst might interpret PC1 as:

```text
Growth factor
```

But the exam trap is this:

> The label is interpretation, not the mathematical output of PCA.

The component itself is just a weighted combination of variables.

## Scree Plots

A scree plot shows how much variance each principal component explains.

Example:

```text
Variance explained

50% | ████████████████████ PC1
30% | ████████████         PC2
10% | ████                 PC3
 6% | ██                   PC4
 4% | █                    PC5
```

The goal is to see where additional components stop adding much information.

CFA notes that in practice analysts often retain the smallest number of components that collectively explain 85%-95% of the total variance.

```text
Keep enough components to preserve most information.
Drop components that add little incremental explanatory power.
```

## Standardization

CFA notes that data should be standardized before PCA in many applications.

Why?

Because PCA is based on variance. If variables are measured on different scales, high-scale variables can dominate the components.

Example:

```text
Market cap: billions of dollars
Profit margin: percentage
Debt ratio: percentage
```

If market cap has much larger numerical variance, PCA may treat it as the most important variable just because of units.

Standardization commonly sets:

$$
\text{Mean} = 0
$$

and:

$$
\text{Standard deviation} = 1
$$

That makes the variables more comparable.

## Why PCA Is Unsupervised

PCA does not use a target variable.

It does not need:

```text
Actual stock return
Default / no default
Winner / loser
Positive sentiment / negative sentiment
```

It only uses the structure of the input features.

That makes PCA [[unsupervised learning]].

The model is not trying to predict $Y$.

It is trying to summarize $X$.

## PCA vs K-Means and Hierarchical Clustering

PCA, K-means, and hierarchical clustering are all unsupervised, but they answer different questions.

| Method | Main question | Output |
|---|---|---|
| [[Principal Component Analysis]] | Can many correlated features be summarized by fewer uncorrelated components? | Principal components |
| [[K-Means Clustering]] | Can observations be grouped into exactly $k$ clusters? | Cluster assignments |
| [[Hierarchical Clustering]] | Can observations be grouped into a hierarchy of clusters? | Dendrogram / nested clusters |

Exam trap:

> PCA reduces features. Clustering groups observations.

## PCA vs LASSO

Both PCA and [[LASSO]] can reduce model complexity, but they do it differently.

| Feature | PCA | LASSO |
|---|---|---|
| Learning type | Unsupervised | Supervised |
| Uses target variable? | No | Yes |
| What it reduces | Feature dimension by creating components | Coefficients by shrinking some to zero |
| Output | New composite variables | Original variables with selected/shrunk coefficients |
| Interpretability | Often lower because components are combinations | Often higher because selected variables remain original variables |

Simple distinction:

```text
PCA transforms variables.
LASSO selects/shrinks variables.
```

## PCA and Factor Models

In portfolio management, PCA appears as a statistical factor model technique.

A statistical factor model extracts factors from the data rather than starting with named economic factors.

PCA chooses factors that explain the variance of asset returns.

Example:

```text
Yield curve changes
  |
  v
PCA
  |
  v
Level, slope, curvature-like components
```

In fixed income, principal components often correspond to movements such as:

| Component | Common interpretation |
|---|---|
| PC1 | Level shift in the yield curve |
| PC2 | Slope / steepness change |
| PC3 | Curvature change |

But again, the labels are interpretations. PCA itself produces mathematical components.

## Investment Applications

| Application | Why PCA fits |
|---|---|
| High-dimensional macro data | Reduces thousands of indicators into a few composite factors |
| Risk modeling | Helps summarize common sources of return variation |
| Covariance matrix estimation | Reduces noisy covariance structure to dominant factors |
| Yield curve analysis | Extracts major movements such as level, slope, and curvature |
| Exploratory data analysis | Helps visualize data in two or three dimensions |
| Preprocessing before ML | Reduces features before training another model |
| Multicollinearity management | Combines highly correlated variables into uncorrelated components |

## Advantages

| Advantage | Why it matters |
|---|---|
| Reduces dimensionality | Fewer features make analysis easier |
| Preserves most variance | Keeps the dominant information in the data |
| Produces uncorrelated components | Reduces redundancy among features |
| Helps with noisy data | Drops low-information components |
| Useful before other models | Can improve speed and reduce overfitting risk |
| Supports visualization | High-dimensional data can be represented in two or three dimensions |

## Disadvantages

| Disadvantage | Why it matters |
|---|---|
| Components are hard to interpret | They are mathematical combinations, not named economic variables |
| Can be black-box | Users may not know what a component "means" |
| Depends on scaling | Variables with larger variance can dominate unless standardized |
| May discard useful information | Dropped components may contain signal relevant to a later prediction task |
| Linear method | Components are linear combinations of original variables |
| Not a prediction model by itself | PCA summarizes features; it does not directly predict a target |

## Common Wrong Reasoning

### Wrong: "PCA is supervised because it helps prediction models."

Why it is wrong: PCA can be used before a prediction model, but PCA itself does not use a labeled target variable. It is unsupervised.

### Wrong: "PCA clusters observations."

Why it is wrong: PCA reduces features into components. K-means and hierarchical clustering group observations.

### Wrong: "The first principal component is the most important original variable."

Why it is wrong: PC1 is not usually one original variable. It is a weighted combination of original variables and explains the most variance.

### Wrong: "Eigenvectors tell the proportion of variance explained."

Why it is wrong: Eigenvectors define component directions. Eigenvalues measure variance explained.

### Wrong: "PCA components are easy to label."

Why it is wrong: Components are mathematical combinations of original variables. Sometimes the loadings suggest an economic label, but often interpretation is difficult.

### Wrong: "Keep all components because then nothing is lost."

Why it is wrong: Keeping all components defeats dimension reduction. PCA is useful because a small number of components often preserves most variance.

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| Many correlated features | Think PCA or dimension reduction |
| Need fewer uncorrelated composite variables | Think PCA |
| Eigenvectors and eigenvalues | Think PCA |
| Scree plot | Choose number of principal components |
| 85%-95% variance retained | Keep enough components to reach that range |
| Need to group observations | Think clustering, not PCA |
| Need variable selection with target variable | Think LASSO, not PCA |
| Components cannot be easily labeled | PCA black-box limitation |
| Statistical factor model from covariance matrix | PCA may be involved |

## Minimum Memorization

Memorize this:

```text
PCA = unsupervised dimension reduction
    = many correlated features
    -> fewer uncorrelated principal components
```

And this:

```text
Eigenvector = direction / component
Eigenvalue = variance explained
```

And this:

```text
PC1 explains most variance.
PC2 explains next-most remaining variance and is uncorrelated with PC1.
Scree plot helps choose how many PCs to retain.
```

## Can I Solve This?

You are ready for PCA questions if you can answer these:

1. Why is PCA unsupervised?
2. What problem does dimension reduction solve?
3. What is a principal component?
4. Why are principal components uncorrelated?
5. What is the difference between an eigenvector and an eigenvalue?
6. Why does PC1 explain the most variance?
7. What does a scree plot show?
8. Why might PCA be considered black-box?
9. How is PCA different from K-means?
10. How is PCA different from LASSO?

## Related Concepts

- [[Machine Learning]]
- [[Unsupervised learning]]
- [[Dimensionality Reduction]]
- [[Principal Component Analysis]]
- [[Covariance matrix]]
- [[Eigenvector]]
- [[Eigenvalue]]
- [[Variance]]
- [[Scree plot]]
- [[Projection error]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Multicollinearity]]
- [[K-Means Clustering]]
- [[Hierarchical Clustering]]
- [[LASSO]]
- [[Statistical Factor Model]]
- [[Using Multifactor Models]]
- [[Yield curve]]
- [[Level]]
- [[Steepness]]
- [[Curvature]]
