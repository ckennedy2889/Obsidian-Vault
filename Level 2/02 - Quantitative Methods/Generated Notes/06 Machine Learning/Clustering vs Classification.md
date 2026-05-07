---
title: Clustering vs Classification
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, unsupervised-learning, classification, clustering]
aliases: [Classification vs Clustering, Clustering versus Classification, Classification versus Clustering, Clustering and Classification]
---

# Clustering vs Classification

## The Real-World Analogy

Imagine you are organizing a room full of people.

In one case, every person is already wearing a name tag:

```text
Analyst
Portfolio manager
Trader
Risk manager
```

Your job is to learn what makes each type different so that when a new person walks in, you can predict which name tag they should get.

That is [[classification]].

In the other case, nobody has a name tag.

You are just looking around the room and noticing natural groups:

```text
These people all seem to know each other.
These people are discussing risk.
These people are gathered around the trading screen.
These people are comparing financial statements.
```

Your job is not to predict a known label. Your job is to discover hidden groupings.

That is [[clustering]].

The deepest difference:

```text
Classification = known labels are provided.
Clustering     = labels are not provided.
```

## One-Minute Version

Classification and clustering both put observations into categories or groups, but they do it for different reasons.

[[Classification]] is [[supervised learning]]. It uses labeled data. The target variable is known during training. The model learns how features map to known categories.

[[Clustering]] is [[unsupervised learning]]. It uses unlabeled data. There is no target variable. The model searches for natural groups based on similarity.

| Question | Classification | Clustering |
|---|---|---|
| Learning type | Supervised | Unsupervised |
| Uses labeled target $Y$? | Yes | No |
| Main goal | Predict a known class label | Discover natural groups |
| Output | Predicted label | Cluster assignment |
| Example | Predict default vs no default | Group bonds with similar risk/return behavior |
| Evaluation | [[Confusion Matrix]], accuracy, [[precision]], [[recall]], [[F1 score]] | Cohesion, separation, dendrogram, business usefulness |

The exam shortcut:

```text
Known answer labels -> classification.
No answer labels -> clustering.
```

## LOS Coverage

This distinction sits inside the CFA Level II [[Quantitative Methods]] machine learning reading.

The relevant LOS asks you to:

| LOS idea | What this note helps you do |
|---|---|
| Describe supervised, unsupervised, and deep learning | Know that classification is supervised and clustering is unsupervised |
| Describe supervised ML algorithms | Recognize classification methods such as [[logistic regression]], [[Support Vector Machines]], [[k-nearest neighbor]], [[CART]], and [[Random Forests]] |
| Describe unsupervised ML algorithms | Recognize clustering methods such as [[K-Means Clustering]] and [[Hierarchical Clustering]] |
| Determine best-suited problems | Choose classification for labeled category prediction and clustering for unlabeled grouping |

## The Big Idea

Both classification and clustering deal with categories.

That is why they are easy to confuse.

But the category means something different in each case.

In classification, the categories already exist.

```text
Default
No default
```

or:

```text
Positive sentiment
Negative sentiment
```

or:

```text
Investment grade
High yield
```

The model's job is to learn the rule that predicts the correct category for new observations.

In clustering, the categories are not given.

The model looks at the observations and says:

```text
These observations are close together.
Those observations are far away.
This looks like a natural group.
That looks like another natural group.
```

The analyst may label the discovered groups afterward, but the labels are not known in advance.

That is the heart of the distinction.

## Classification: Predicting a Known Label

Classification is used when the target variable is categorical or ordinal.

Examples:

| Problem | Target label |
|---|---|
| Will this bond default? | Default / no default |
| Is this stock likely to outperform? | Outperform / underperform |
| What is this bond's rating class? | AAA, AA, A, BBB, BB, etc. |
| Is this text positive or negative? | Positive / negative sentiment |
| Is this transaction fraudulent? | Fraud / no fraud |

The model sees training examples like this:

```text
Features X                         Known label Y
Leverage, coverage, cash flow  ->  Default / no default
Valuation, growth, margins     ->  Outperform / underperform
Text tokens                    ->  Positive / negative sentiment
```

The model learns:

```text
X pattern -> Y label
```

Then it applies that learned mapping to new observations.

## Why Classification Is Supervised

Classification is supervised because the model is trained with correct answers.

The known target acts like a teacher.

The model predicts.

The model compares its prediction to the actual label.

The model adjusts or is evaluated based on whether it was right.

```text
Known labels
  |
  v
Model can learn what correct means
  |
  v
Model can be scored on prediction errors
  |
  v
Classification is supervised
```

Without labels, there is no direct way to say:

```text
This predicted class is correct.
This predicted class is wrong.
```

That is why labels are the dividing line.

## Classification Algorithms in CFA

Common CFA classification algorithms include:

| Algorithm | Core idea |
|---|---|
| [[Logistic regression]] | Predicts probability of a class, often binary |
| [[Support Vector Machines]] | Finds a separating hyperplane with a wide margin |
| [[k-nearest neighbor]] | Classifies using majority vote among nearby labeled observations |
| [[CART]] | Uses if/then decision-tree splits |
| [[Random Forests]] | Combines many decision trees by voting |
| [[Neural Networks]] | Learns flexible nonlinear patterns through layers |

These are classification tools when the target is categorical.

If the target is continuous, the task is regression, not classification.

## Clustering: Discovering Natural Groups

Clustering is used when there is no known target label.

The analyst has observations and features, but no answer column.

Example:

```text
Bond | Duration | Spread | Rating proxy | Sector | Return volatility
```

There is no target like:

```text
Cluster = 1
Cluster = 2
Cluster = 3
```

The clustering algorithm creates those groupings based on similarity.

Examples:

| Problem | What clustering discovers |
|---|---|
| Group stocks by return behavior | Hidden peer groups |
| Group bonds by risk characteristics | Similar credit/rate exposures |
| Group financial institutions | Similar balance-sheet profiles |
| Group clients | Similar objectives or behavior patterns |
| Group text documents | Topic clusters |

The model is not predicting a known label.

It is finding structure.

## Why Clustering Is Unsupervised

Clustering is unsupervised because there is no target variable.

The model only sees:

```text
X variables / features
```

It does not see:

```text
Y target / correct answer
```

That means the algorithm cannot be evaluated the same way a classification model can.

There is no ground truth label to compare against.

Instead, the analyst asks:

```text
Are observations within each cluster similar?
Are different clusters meaningfully separate?
Are the clusters economically useful?
```

This is why clustering requires more judgment.

The algorithm can discover mathematical groups, but the analyst must decide whether those groups mean anything.

## Clustering Algorithms in CFA

Common CFA clustering algorithms include:

| Algorithm | Core idea |
|---|---|
| [[K-Means Clustering]] | Partition observations into exactly $k$ clusters around centroids |
| [[Hierarchical Clustering]] | Build nested clusters shown with a [[dendrogram]] |

Related unsupervised methods:

| Method | Why it is related |
|---|---|
| [[Principal Component Analysis]] | Unsupervised, but reduces features rather than grouping observations |
| [[Dimensionality Reduction]] | Reduces columns/features, not rows/observations |

Important:

```text
Clustering groups observations.
PCA reduces features.
```

## Side-by-Side Finance Example: Corporate Bonds

Suppose you have a database of corporate bonds.

Each bond has features:

```text
Duration
Credit spread
Leverage
Interest coverage
Sector
Coupon type
Return volatility
```

### Classification Version

The dataset includes known labels:

```text
Investment grade / high yield
```

or:

```text
Default / no default
```

The task:

> Predict the correct label for a new bond.

The model learns from already-labeled bonds.

```text
Known bond features + known rating class
  |
  v
Train classification model
  |
  v
New bond features
  |
  v
Predicted rating class
```

This is classification because the target label exists.

### Clustering Version

The dataset has no labels.

You only have bond characteristics and return behavior.

The task:

> Discover which bonds naturally group together.

The algorithm might find:

```text
Cluster 1: short-duration defensive bonds
Cluster 2: long-duration rate-sensitive bonds
Cluster 3: high-spread credit-risk bonds
Cluster 4: floating-rate financial bonds
```

These cluster labels are analyst interpretations.

The model did not know them beforehand.

This is clustering because the groups are discovered rather than predicted from known labels.

## Output Difference

Classification output:

```text
Predicted label:
Default
No default
Positive sentiment
Negative sentiment
Investment grade
High yield
```

Clustering output:

```text
Cluster assignment:
Cluster 1
Cluster 2
Cluster 3
```

The difference is subtle but important.

A classification label has a predefined meaning.

A cluster number has no automatic meaning.

The analyst must interpret it.

```text
Classification label:
"Default" means default.

Cluster label:
"Cluster 2" means whatever the analyst determines after studying the cluster.
```

## Evaluation Difference

Classification can be evaluated against known answers.

If the model predicts default and the bond defaults, that is a correct positive prediction.

If the model predicts no default and the bond defaults, that is a missed default.

That gives the [[Confusion Matrix]]:

| Actual / Predicted | Predicted Positive | Predicted Negative |
|---|---:|---:|
| Actual Positive | True Positive | False Negative |
| Actual Negative | False Positive | True Negative |

From that, the analyst calculates:

```text
Accuracy
Precision
Recall
F1 score
```

Clustering does not have that same direct right/wrong grid.

There is no actual label.

Instead, analysts look at:

| Clustering criterion | Meaning |
|---|---|
| Cohesion | Are observations within a cluster close/similar? |
| Separation | Are different clusters meaningfully far apart? |
| Dendrogram | For hierarchical clustering, where do natural splits appear? |
| Centroids | For K-means, where are cluster centers? |
| Economic meaning | Do the groups make investment sense? |

The deep difference:

```text
Classification error = wrong compared with known label.
Clustering weakness = groups are not coherent, separate, or useful.
```

## Data Split Difference

For supervised classification, CFA discusses splitting data into:

```text
Training sample
Validation sample
Test sample
```

A common split is:

```text
60% training
20% validation
20% test
```

Why?

Because labels make it possible to train, tune, and test prediction accuracy.

```text
Training data:
Learn relationship between X and Y.

Validation data:
Tune model and hyperparameters.

Test data:
Final out-of-sample check.
```

For unsupervised clustering, the CFA source notes that no supervised train/validation/test split is needed because there is no labeled training data.

Why?

Because there is no hidden correct answer to check in the same way.

This does not mean clustering has no evaluation.

It means clustering evaluation is different:

```text
No labels -> no direct prediction accuracy.
Need cohesion, separation, stability, and business meaning.
```

## Class Imbalance Applies to Classification

Class imbalance is a classification issue.

Example:

```text
1% of bonds default
99% do not default
```

A naive classifier could predict:

```text
No default for every bond
```

Accuracy:

```text
99%
```

But the model is useless for finding defaults.

That is why classification performance may need [[precision]], [[recall]], and [[F1 score]], not just accuracy.

Clustering does not have "class imbalance" in the same supervised sense because there are no known classes.

But clustering can still produce uneven cluster sizes. That is a different issue.

## Clustering Can Feed Classification

Sometimes the two methods work together.

Example workflow:

```text
Step 1: Use clustering to discover peer groups of stocks.
Step 2: Use the cluster assignment as an input feature in a supervised classification model.
Step 3: Classify which stocks are likely to outperform.
```

So clustering and classification are not enemies.

They answer different questions.

Clustering can help create structure that later improves classification.

But the methods remain different:

```text
Clustering discovers groups.
Classification predicts known labels.
```

## KNN vs K-Means Trap

This is one of the easiest traps.

[[k-nearest neighbor]] and [[K-Means Clustering]] both use the letter $k$.

They are not the same.

| Algorithm | Learning type | Meaning of $k$ | Goal |
|---|---|---|---|
| [[k-nearest neighbor]] | Supervised | Number of neighbors | Predict label/value using nearby labeled observations |
| [[K-Means Clustering]] | Unsupervised | Number of clusters | Partition observations into $k$ groups |

Memory hook:

```text
KNN k = neighbors.
K-means k = clusters.
```

If the data are labeled and the model predicts a class, think KNN or another classifier.

If the data are unlabeled and the model discovers groups, think K-means or hierarchical clustering.

## Classification vs Regression vs Clustering

It helps to place all three together.

| Task | Learning type | Target? | Target type | Example |
|---|---|---|---|---|
| Regression | Supervised | Yes | Continuous | Predict next-quarter return |
| Classification | Supervised | Yes | Categorical/ordinal | Predict default/no default |
| Clustering | Unsupervised | No | None | Group similar stocks |

The decision rule:

```text
Is there a target variable?
  |
  +-- Yes -> Supervised
  |          |
  |          +-- Continuous target -> Regression
  |          +-- Categorical target -> Classification
  |
  +-- No  -> Unsupervised
             |
             +-- Reduce features -> PCA / dimensionality reduction
             +-- Group observations -> Clustering
```

## Common Wrong Reasoning

### Wrong: "Classification and clustering are the same because both create categories."

Why it is wrong: Classification predicts predefined categories. Clustering discovers categories that were not provided.

Correct idea:

```text
Classification = known labels.
Clustering = unknown groups.
```

### Wrong: "If the output is a group number, it must be classification."

Why it is wrong: A cluster number is not a known class label. It is an assigned group discovered by the algorithm.

Correct idea:

```text
Predicted known class -> classification.
Discovered group -> clustering.
```

### Wrong: "Clustering is evaluated with a confusion matrix."

Why it is wrong: A confusion matrix requires known actual labels. Clustering usually has no ground-truth labels.

Correct idea:

```text
Classification -> confusion matrix.
Clustering -> cohesion/separation/business usefulness.
```

### Wrong: "K-means is classification because it assigns observations to clusters."

Why it is wrong: K-means assigns observations to discovered clusters without target labels. That is unsupervised clustering.

Correct idea:

```text
Assignment to discovered cluster is not the same as prediction of known label.
```

### Wrong: "A train/validation/test split is always required for every ML method."

Why it is wrong: CFA specifically distinguishes supervised learning, where labeled data are split for training/tuning/testing, from unsupervised learning, where no labeled training data exist.

Correct idea:

```text
Supervised classification -> train/validation/test.
Unsupervised clustering -> no labeled split in the same sense.
```

### Wrong: "If a clustering algorithm finds 'growth stocks,' then growth was the target label."

Why it is wrong: The label "growth stocks" is an analyst interpretation after the algorithm finds a group. It was not the target variable used to train the model.

Correct idea:

```text
Post-hoc interpretation is not supervised labeling.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Labeled data | Supervised learning |
| Target variable is categorical | Classification |
| Predict default/no default | Classification |
| Predict positive/negative sentiment | Classification |
| Confusion matrix, precision, recall, F1 | Classification |
| Class imbalance | Classification |
| No target variable | Unsupervised learning |
| Discover hidden groups | Clustering |
| Group similar securities | Clustering |
| Cohesion and separation | Clustering |
| Centroids | K-means clustering |
| Dendrogram | Hierarchical clustering |
| Reduce many correlated variables | PCA / dimensionality reduction, not clustering |

## Minimum Memorization

```text
Classification:
Supervised
Uses labeled target Y
Predicts known class labels
Evaluated with confusion matrix / accuracy / precision / recall / F1

Clustering:
Unsupervised
No target Y
Discovers natural groups
Evaluated with cohesion / separation / usefulness
```

The cleanest exam sentence:

```text
Classification assigns observations to known categories using labeled data;
clustering discovers unknown groups in unlabeled data.
```

And:

```text
Classification predicts.
Clustering discovers.
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. What is the main difference between clustering and classification?
2. Why is classification supervised?
3. Why is clustering unsupervised?
4. What role does the target variable play?
5. Why does classification use a confusion matrix?
6. Why does clustering not normally use a confusion matrix?
7. How are classification and regression different?
8. How are clustering and dimensionality reduction different?
9. What does $k$ mean in KNN?
10. What does $k$ mean in K-means?
11. Why does class imbalance matter for classification?
12. Why does cluster interpretation require analyst judgment?
13. How could clustering be used before classification?
14. Why is "Cluster 2" not automatically an economic label?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[Unsupervised learning]]
- [[Classification]]
- [[Clustering]]
- [[Regression]]
- [[Logistic regression]]
- [[Support Vector Machines]]
- [[k-nearest neighbor]]
- [[CART]]
- [[Random Forests]]
- [[K-Means Clustering]]
- [[Hierarchical Clustering]]
- [[Dimensionality Reduction]]
- [[Principal Component Analysis]]
- [[Confusion Matrix]]
- [[Precision]]
- [[Recall]]
- [[F1 score]]
- [[Class imbalance]]
- [[Cohesion]]
- [[Separation]]
- [[Centroid]]
- [[Dendrogram]]
