---
title: k-Nearest Neighbor (KNN)
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, classification]
aliases: [KNN, K-nearest neighbor, k-nearest neighbors, k nearest neighbor, k nearest neighbors]
---

# k-Nearest Neighbor (KNN)

## The Real-World Analogy

Imagine you are trying to guess the credit rating of a new corporate bond.

You do not build a full valuation model. You do not estimate a regression equation. You do not draw a decision tree.

Instead, you ask:

> Which existing bonds look most similar to this new bond?

If the closest comparable bonds are mostly BBB-rated, you classify the new bond as BBB. If the closest comparable bonds are mostly AA-rated, you classify it as AA.

That is the whole intuition of [[k-nearest neighbor]]:

```text
New observation
  |
  v
Find the k most similar labeled observations
  |
  v
Use their labels or values to predict the new observation
```

The method is powerful because it matches how analysts often think:

> Similar things should behave similarly.

But that sentence hides the entire difficulty.

Why?

Because the analyst must define what "similar" means.

Two bonds can be similar in leverage but different in maturity. Two stocks can be similar in returns but different in industry. Two companies can be similar in size but different in profitability. KNN works only if the distance measure and feature set actually capture the economic similarity that matters.

## One-Minute Version

[[k-nearest neighbor]] (KNN) is a [[supervised learning]] algorithm used mostly for [[classification]] and sometimes for [[regression]].

For classification, KNN classifies a new observation by finding the $k$ closest observations in the labeled training data and assigning the class that appears most often among those neighbors.

For regression, KNN predicts a number by averaging the values of the $k$ closest observations.

The key moving parts are:

| Component | Meaning |
|---|---|
| $k$ | Number of nearest neighbors used |
| Distance metric | Rule for deciding which observations are "near" |
| Features | Variables used to measure similarity |
| Majority vote | Classification decision rule |
| Average of neighbors | Regression prediction rule |

KNN is intuitive and non-parametric, but it is sensitive to irrelevant features, correlated features, scaling, and the choice of $k$.

The CFA exam loves the traps:

| Trap | Correct idea |
|---|---|
| KNN is unsupervised | No. KNN is supervised because it uses labeled data |
| KNN and K-means are the same | No. KNN predicts labels; K-means discovers clusters |
| $k$ is learned by the model | No. $k$ is a hyperparameter chosen by the analyst |
| More features always improve KNN | No. Irrelevant features distort distance |
| Even $k$ is always fine | Be careful. Even $k$ can create classification ties |

## LOS Coverage

KNN belongs in the CFA Level II [[Quantitative Methods]] machine learning reading.

The relevant LOS asks you to describe supervised machine learning algorithms, including [[penalized regression]], [[support vector machine]], [[k-nearest neighbor]], [[classification and regression tree]], [[ensemble learning]], and [[random forest]], and determine the problems for which they are best suited.

For KNN, you should be able to:

| CFA task | What you need to know |
|---|---|
| Identify the learning type | KNN is supervised learning |
| Identify common use | Most often classification, sometimes regression |
| Explain the decision rule | Classify by majority vote among $k$ nearest labeled observations |
| Explain $k$ | $k$ is the number of neighbors and a hyperparameter |
| Explain similarity | Similarity depends on selected features and distance metric |
| Discuss trade-offs | Small $k$ can overfit; large $k$ can underfit |
| Compare with other algorithms | Especially [[K-Means Clustering]], [[Support Vector Machines]], [[Classification and Regression Trees]], and [[Random Forests]] |

## The Big Idea

KNN is a local similarity model.

That phrase matters.

It is local because it does not try to summarize the whole dataset with one equation. It looks near the new observation and asks what nearby examples look like.

It is similarity-based because the model assumes observations close together in feature space should have similar targets.

It is supervised because the neighbors already have known labels or known target values.

```text
Training data:

Observation   Features                    Known target
Bond A        leverage, size, maturity     A
Bond B        leverage, size, maturity     BBB
Bond C        leverage, size, maturity     A

New bond:

Features known, target unknown

KNN:

Find nearest labeled bonds -> vote or average -> predicted target
```

KNN is not trying to explain causality. It is not saying leverage causes a rating in a specific parametric way. It is saying that if a new bond is close to previously observed bonds across relevant features, the new bond is likely to share their rating.

That is both the strength and weakness.

It is flexible because it does not force a straight line, a logistic curve, or a tree structure.

It is fragile because everything depends on the meaning of "near."

## Why CFA Tests This

CFA tests KNN because it is a clean example of how machine learning differs from traditional statistical modeling.

In a traditional model, you often estimate parameters:

```text
Y = b0 + b1X1 + b2X2 + error
```

The model learns coefficients. Then you use those coefficients to predict.

KNN does not work that way.

There is no fitted coefficient such as $b_1$.

There is no estimated slope.

There is no distributional assumption that the residuals must be normal.

Instead, the training data itself becomes the reference library.

When a new observation arrives, KNN searches the reference library for comparable observations.

That is why KNN is often called a lazy learning algorithm in general machine learning language. It does relatively little model-building upfront and does more work when a prediction is requested. For CFA purposes, the exam emphasis is usually simpler: KNN is intuitive, non-parametric, similarity-based, and sensitive to features and distance metrics.

## Step-by-Step Algorithm

Suppose the task is classification.

The KNN algorithm works like this:

| Step | What happens | Why it matters |
|---|---|---|
| 1 | Choose the features | These variables define the space where "near" is measured |
| 2 | Scale or standardize features when needed | Distance can be dominated by large-unit variables |
| 3 | Choose a distance metric | This defines what "similar" means |
| 4 | Choose $k$ | This controls how many neighbors vote |
| 5 | Find the $k$ closest labeled observations | These are the relevant comparables |
| 6 | For classification, use majority vote | The most common label becomes the predicted class |
| 7 | For regression, average neighbor values | The average becomes the predicted number |
| 8 | Evaluate performance | Use test data, [[Confusion Matrix]], accuracy, [[precision]], [[recall]], [[F1 score]], or [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]] depending on target type |

The mental model:

```text
Choose features
  |
  v
Define distance
  |
  v
Pick k
  |
  v
Find nearest observations
  |
  v
Vote for class or average values
  |
  v
Evaluate prediction quality
```

## What Does $k$ Mean?

In KNN, $k$ means the number of neighbors used to make the prediction.

If $k = 1$, the model uses the single nearest observation.

If $k = 5$, the model uses the five nearest observations.

If $k = 50$, the model uses the fifty nearest observations.

This is why the name is $k$-nearest neighbor:

```text
k = number of nearest labeled observations consulted
```

This is not the same as $k$ in [[K-Means Clustering]].

| Algorithm | Meaning of $k$ |
|---|---|
| [[k-nearest neighbor]] | Number of neighbors used for prediction |
| [[K-Means Clustering]] | Number of clusters created |

This is a classic CFA trap.

KNN:

```text
I already have labels.
Use nearby labels to predict the new label.
```

K-means:

```text
I do not have labels.
Discover groups in the data.
```

## Classification Decision Rule

For classification, KNN uses majority vote.

Suppose $k = 5$ and the five nearest neighbors have these labels:

```text
Neighbor 1: Investment grade
Neighbor 2: High yield
Neighbor 3: Investment grade
Neighbor 4: Investment grade
Neighbor 5: High yield
```

The vote is:

| Class | Votes |
|---|---:|
| Investment grade | 3 |
| High yield | 2 |

The model predicts:

```text
Investment grade
```

Why majority vote?

Because the core assumption is local similarity. If the nearby observations are the best available comparables, then the most common nearby class is the most likely class for the new observation.

But notice the word "if."

The vote is meaningful only if the neighbors are meaningfully near.

If the distance metric is bad, the vote is bad.

If the features are irrelevant, the vote is bad.

If the data are poorly scaled, the vote is bad.

KNN is simple, but it is not automatic wisdom.

## Regression Decision Rule

KNN can also be used for regression.

In KNN regression, the model finds the $k$ nearest neighbors and averages their target values.

Suppose an analyst wants to estimate a fair yield spread for a new bond.

The three closest comparable bonds have spreads:

| Neighbor | Spread |
|---|---:|
| 1 | 120 bps |
| 2 | 135 bps |
| 3 | 150 bps |

If $k = 3$:

$$
\text{Predicted spread} = \frac{120 + 135 + 150}{3}
$$

$$
\text{Predicted spread} = \frac{405}{3} = 135 \text{ bps}
$$

Why average?

Because for a continuous target, there is no class to vote on. The neighbors provide nearby numerical outcomes, so their central value becomes the prediction.

The same logic applies:

```text
Classification target -> vote among neighbor classes
Continuous target -> average neighbor values
```

## What Does "Nearest" Mean?

"Nearest" means closest according to a distance or similarity metric.

This is the part that sounds technical but is actually the heart of the model.

KNN needs a way to convert feature differences into a distance score.

For example, suppose you compare two companies using leverage and profit margin.

```text
Company A: leverage = 2.0x, margin = 12%
Company B: leverage = 2.5x, margin = 10%
```

The model needs to ask:

> How far apart are these two observations?

One common distance measure is Euclidean distance.

For two features:

$$
d(A,B) = \sqrt{(x_{1,A} - x_{1,B})^2 + (x_{2,A} - x_{2,B})^2}
$$

This is just the Pythagorean theorem applied to feature space.

Why squared differences?

Because raw differences can be positive or negative. Squaring makes them positive and penalizes larger differences more heavily.

Why square root?

Because after summing squared differences, the square root converts the result back into distance units.

For CFA, you usually do not need to compute Euclidean distance unless the question gives a very simple setup. The more important point is conceptual:

> KNN predictions depend heavily on how similarity is measured.

## Distance Metric Examples

| Distance or similarity idea | When it might make sense |
|---|---|
| Euclidean distance | Numeric features measured on comparable scales |
| Standardized Euclidean distance | Numeric features with different units or scales |
| Correlation-based similarity | Comparing return patterns across securities |
| Domain-specific similarity | Credit rating, bankruptcy, custom index construction |

The CFA curriculum notes that if an analyst is comparing equity market performance, correlation of historical returns may be an appropriate similarity measure.

That is an important idea.

Similarity is not always physical distance on a chart.

In finance, similarity often means economic comparability:

```text
Similar credit risk
Similar cash flow profile
Similar leverage
Similar return pattern
Similar maturity
Similar embedded option exposure
Similar industry sensitivity
```

The analyst must choose features and distance measures that match the business objective.

## Why Feature Scaling Matters

KNN is distance-based.

That means variable scale can dominate the prediction.

Suppose you compare companies using:

| Feature | Typical scale |
|---|---:|
| Total assets | $100,000,000 to $10,000,000,000 |
| Debt-to-assets ratio | 0.10 to 0.90 |

If you compute raw distance, total assets can overwhelm the debt ratio because the numbers are much larger.

The model may effectively say:

```text
Assets are huge numbers, so assets matter most.
Debt ratio is a tiny number, so debt ratio barely matters.
```

But that is not an economic conclusion.

It is a units problem.

That is why scaling or standardization is often needed.

```text
Before scaling:
Large-unit variables dominate distance.

After scaling:
Variables can contribute more comparably to distance.
```

The deep reason is that distance formulas treat numeric differences literally. If one feature is measured in dollars and another is measured in percentages, the formula does not automatically understand that a 0.10 change in leverage may be economically meaningful.

The analyst must prepare the data so the distance measure reflects economic meaning instead of arbitrary measurement units.

## Why Irrelevant Features Hurt KNN

KNN can be damaged by irrelevant features.

Suppose you want to classify a bond's credit rating and include these features:

| Feature | Relevant? |
|---|---|
| Leverage ratio | Yes |
| Interest coverage | Yes |
| Cash flow stability | Yes |
| CEO's favorite color | No |

The irrelevant feature still enters the distance calculation.

That means it can move observations closer or farther away even though it has no economic relationship to credit risk.

Mechanically:

```text
Bad feature
  |
  v
Distance gets distorted
  |
  v
Wrong neighbors are selected
  |
  v
Majority vote or average is based on bad comparables
  |
  v
Prediction gets worse
```

This is why KNN often works better with a small number of meaningful features.

More variables are not automatically better.

In KNN, every feature helps define the neighborhood. If the feature does not measure useful similarity, it pollutes the neighborhood.

## Why Correlated Features Hurt KNN

Correlated features can also hurt KNN.

Suppose you include:

```text
Sales
Revenue
Total income
```

If these variables are highly correlated, they may be measuring almost the same thing.

The distance metric may then overweight that dimension of similarity.

It is like asking the same question three times and treating the repeated answer as three independent pieces of evidence.

Mechanically:

```text
Correlated features
  |
  v
Same economic signal counted multiple times
  |
  v
Distance metric becomes unbalanced
  |
  v
Nearest neighbors reflect duplicated information
  |
  v
Prediction may be distorted
```

This is why feature selection matters.

The analyst may need to manually remove less useful or redundant features so the distance measure is more representative.

## Small $k$ vs Large $k$

Choosing $k$ is one of the most important KNN decisions.

| Choice | Effect | Risk |
|---|---|---|
| Very small $k$ | Very local, highly responsive to nearby points | Sensitive to outliers and noise |
| Very large $k$ | Smoother, uses more observations | Dilutes local similarity |

If $k$ is too small, one unusual observation can dominate.

Example:

```text
k = 1
Nearest neighbor is an outlier
Prediction follows the outlier
```

That can create high error because the model is too sensitive to local noise.

If $k$ is too large, the model includes observations that are not truly similar.

Example:

```text
k = 100
Many included observations are far away
Prediction becomes broad average
```

That dilutes the concept of nearest neighbors.

The bias-variance intuition:

| $k$ | Variance | Bias | Intuition |
|---|---:|---:|---|
| Small $k$ | Higher | Lower | Follows local patterns closely, including noise |
| Large $k$ | Lower | Higher | Smooths across more observations, may miss local structure |

You do not need to memorize this as a formal CFA formula, but the intuition helps:

```text
Small k -> too jumpy
Large k -> too diluted
```

## The Even $k$ Tie Trap

If $k$ is even, classification can produce ties.

Suppose $k = 4$:

| Class | Votes |
|---|---:|
| Default | 2 |
| No default | 2 |

There is no clear majority.

That is why exam questions may flag even $k$ as a potential issue.

This does not mean even $k$ is mathematically impossible. Real implementations can use tie-breaking rules. But for CFA exam logic, remember:

> Even $k$ can create no clear classification winner.

## Non-Parametric Meaning

KNN is non-parametric.

This means it does not assume a specific functional form for the relationship between features and the target.

It does not require:

```text
Y = b0 + b1X1 + b2X2
```

It does not require the classification boundary to be a straight line.

It does not require a normal distribution.

Instead, the data itself defines local neighborhoods.

Why is that useful?

Because financial relationships can be messy. Credit risk, bankruptcy risk, and security similarity may not follow a clean linear equation.

But why is it dangerous?

Because with fewer assumptions, the model leans more heavily on the data quality, feature choice, and distance metric. If those are poor, the model has no strong structure to save it.

## Worked Numerical Example: Classification

Suppose we want to classify a new bond as either investment grade or high yield.

We choose $k = 5$.

The five nearest bonds in the training data are:

| Neighbor | Rating class |
|---|---|
| 1 | Investment grade |
| 2 | High yield |
| 3 | Investment grade |
| 4 | Investment grade |
| 5 | High yield |

Count the votes:

| Class | Vote count |
|---|---:|
| Investment grade | 3 |
| High yield | 2 |

Decision:

$$
\text{Predicted class} = \text{Investment grade}
$$

Why?

Because among the five most similar bonds, the majority are investment grade.

What is the hidden assumption?

The hidden assumption is that the five closest bonds are economically meaningful comparables.

If the features were leverage, interest coverage, maturity, seniority, and cash flow stability, that may be reasonable.

If the features were arbitrary or poorly scaled, the vote may not mean much.

## Worked Numerical Example: Regression

Suppose we want to predict the yield spread for a new bond.

We choose $k = 3$.

The three nearest comparable bonds have spreads:

| Neighbor | Spread |
|---|---:|
| 1 | 120 bps |
| 2 | 135 bps |
| 3 | 150 bps |

KNN regression averages the neighbor values:

$$
\text{Predicted spread} = \frac{120 + 135 + 150}{3}
$$

Add the numerator:

$$
120 + 135 + 150 = 405
$$

Divide by 3:

$$
\frac{405}{3} = 135
$$

So:

$$
\text{Predicted spread} = 135 \text{ bps}
$$

Why does this make sense?

If the three nearest bonds are truly comparable, their average spread is a reasonable estimate for the new bond.

Why can this fail?

If one of the three neighbors is only "near" because of a bad distance metric, then the average includes a poor comparable.

## Investment Applications

The CFA curriculum highlights several investment applications.

| Application | How KNN helps |
|---|---|
| [[Credit]] rating assignment | Classify a new unrated bond using similar rated bonds |
| [[Bankruptcy]] prediction | Compare firm ratios to firms that did or did not fail |
| Stock price prediction | Use similar historical observations or securities |
| Customized index creation | Identify similar and dissimilar securities for index construction |
| Security similarity analysis | Find comparable bonds or equities based on relevant characteristics |

The bond rating example is especially intuitive.

Suppose a new bond has no rating. You have a database of existing bonds with issuer characteristics and issue characteristics:

| Issuer features | Issue features |
|---|---|
| Asset size | Tenor |
| Industry | Fixed or floating coupon |
| Leverage ratios | Embedded options |
| Cash flow ratios | Seniority |

KNN asks:

> Which already-rated bonds are most similar to the new bond?

Then it uses those neighbors to infer the new bond's rating.

## KNN vs K-Means

KNN and K-means sound similar because both involve $k$ and distance.

They are not the same.

| Feature | [[k-nearest neighbor]] | [[K-Means Clustering]] |
|---|---|---|
| Learning type | Supervised | Unsupervised |
| Uses labels? | Yes | No |
| Meaning of $k$ | Number of neighbors | Number of clusters |
| Main use | Classification, sometimes regression | Clustering |
| Prediction logic | Nearby labels vote or values average | Observations assigned to nearest centroid |
| CFA trap | KNN is not clustering | K-means is not classification unless labels are added afterward |

Memory hook:

```text
KNN: Who are my nearest labeled neighbors?
K-means: How many unlabeled groups should I create?
```

## KNN vs SVM

| Feature | [[k-nearest neighbor]] | [[Support Vector Machines]] |
|---|---|---|
| Main idea | Classify by nearby observations | Find a separating boundary |
| Type of logic | Local similarity | Boundary/margin |
| Key choice | $k$, features, distance metric | Kernel, margin trade-off, hyperparameters |
| Interpretability | Intuitive but can be hard to explain globally | Geometric boundary intuition |
| Good fit | Similarity-based classification | Classification where boundary separation is useful |

The key distinction:

```text
KNN asks: What are the nearby labels?
SVM asks: Where is the best separating boundary?
```

## KNN vs CART

| Feature | [[k-nearest neighbor]] | [[Classification and Regression Trees]] |
|---|---|---|
| Decision logic | Nearest neighbors vote or average | Sequential feature splits |
| Visual explanation | Limited | Strong, tree can be shown |
| Needs distance metric? | Yes | No |
| Needs $k$? | Yes | No |
| Sensitive to scaling? | Often yes | Usually less so |

CFA may ask why CART can be preferable to KNN.

CART does not require the analyst to specify a distance metric, and it can provide a visual explanation using decision nodes and cutoff values.

That is a major advantage when interpretability matters.

## KNN vs Random Forest

| Feature | [[k-nearest neighbor]] | [[Random Forests]] |
|---|---|---|
| Core idea | Local neighbor voting | Ensemble of many decision trees |
| Handles noise | Can be sensitive | Usually more robust |
| Feature issues | Irrelevant/correlated features can distort distance | Random feature selection helps reduce some feature dependence |
| Interpretability | Intuitive locally | Less transparent than one tree, but robust |
| CFA angle | Simple non-parametric classifier | Ensemble method based on bagging |

The curriculum notes that random forests are often more robust to noise than many classifiers.

KNN can be powerful, but noise and irrelevant variables can seriously degrade it.

## When KNN Is Best Suited

KNN is best suited when:

| Condition | Why it helps KNN |
|---|---|
| Target is categorical | KNN is most commonly used for classification |
| Good labeled examples exist | KNN needs known neighbors |
| Similarity is economically meaningful | The model depends on "near" meaning something real |
| Number of features is modest | Too many features can make distance less useful |
| Features can be scaled or standardized | Distance calculations become more meaningful |
| Nonlinear local patterns may exist | KNN does not force a linear boundary |

KNN is less attractive when:

| Condition | Why it hurts KNN |
|---|---|
| Many irrelevant features | Distance becomes noisy |
| Highly correlated features | Similarity dimensions may be double-counted |
| Poor feature scaling | Large-unit variables dominate |
| Very large dataset | Searching neighbors can become computationally expensive |
| Need a clean visual explanation | CART may be easier to explain |

## Common Wrong Reasoning

### Wrong: "KNN is unsupervised because it finds neighbors."

Why it is wrong: KNN uses labeled data. The labels of the neighbors determine the prediction.

The correct idea:

```text
KNN = supervised
K-means = unsupervised
```

### Wrong: "KNN learns a formula during training."

Why it is wrong: KNN does not estimate a coefficient equation like linear regression. It stores or references training examples and uses them at prediction time.

The correct idea:

```text
KNN prediction comes from nearby labeled examples, not from fitted coefficients.
```

### Wrong: "The highest possible $k$ is safest because it uses more data."

Why it is wrong: A very large $k$ may include observations that are not actually similar. That dilutes local information.

The correct idea:

```text
Small k can be noisy.
Large k can be too diluted.
```

### Wrong: "More features always make KNN better."

Why it is wrong: Every feature affects distance. Irrelevant features can move the wrong observations closer or farther away.

The correct idea:

```text
For KNN, feature quality matters more than feature quantity.
```

### Wrong: "Scaling is just cosmetic."

Why it is wrong: KNN uses distance. If variables are measured on very different scales, large-unit variables dominate the distance calculation.

The correct idea:

```text
Scaling changes who counts as a neighbor.
```

### Wrong: "KNN and K-means are basically the same."

Why it is wrong: KNN is supervised prediction. K-means is unsupervised clustering.

The correct idea:

```text
KNN k = neighbors.
K-means k = clusters.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| "Classify a new observation using nearby labeled observations" | KNN |
| "Majority vote among nearest observations" | KNN classification |
| "Average target values of nearest observations" | KNN regression |
| "Need to choose number of neighbors" | $k$ hyperparameter |
| "Even $k$" | Possible tie |
| "Too small $k$" | Sensitive to outliers/noise |
| "Too large $k$" | Dilutes nearest-neighbor idea |
| "Irrelevant or correlated features" | KNN distance gets distorted |
| "No distributional assumption" | Non-parametric |
| "Unlabeled data and clusters" | K-means, not KNN |
| "Visual decision rules and cutoff values" | CART advantage |

## Minimum Memorization

```text
KNN = supervised, mostly classification

Classification:
Find k nearest labeled observations
Use majority vote

Regression:
Find k nearest labeled observations
Average their target values

k = number of neighbors

Small k -> noisy/outlier-sensitive
Large k -> diluted/underfit
Even k -> possible tie

KNN needs:
Good features
Good scaling
Good distance metric
```

And the most important distinction:

```text
KNN k = neighbors
K-means k = clusters
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. Why is KNN a supervised learning algorithm?
2. What does $k$ mean in KNN?
3. How does KNN classify a new observation?
4. How does KNN regression make a prediction?
5. Why can small $k$ create high error?
6. Why can large $k$ dilute the prediction?
7. Why can even $k$ create a tie?
8. Why does feature scaling matter for KNN?
9. Why do irrelevant features hurt KNN?
10. Why do correlated features distort distance?
11. How is KNN different from K-means?
12. Why might CART be easier to explain than KNN?
13. Why is KNN called non-parametric?
14. What are CFA investment applications of KNN?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[Classification]]
- [[Regression]]
- [[k-nearest neighbor]]
- [[K-Means Clustering]]
- [[Support Vector Machines]]
- [[Classification and Regression Trees]]
- [[Random Forests]]
- [[Ensemble learning]]
- [[Hyperparameter]]
- [[Feature selection]]
- [[Feature engineering]]
- [[Data preprocessing]]
- [[Confusion Matrix]]
- [[Precision]]
- [[Recall]]
- [[F1 score]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]]
- [[Credit]]
- [[Bond]]
- [[Bankruptcy]]
