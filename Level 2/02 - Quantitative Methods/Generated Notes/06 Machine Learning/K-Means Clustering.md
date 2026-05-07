---
title: K-Means Clustering
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, unsupervised-learning, clustering]
aliases: [K-means, K means, K-means clustering, k-means]
---

# K-Means Clustering

> [[K-Means Clustering]] is an [[unsupervised learning]] algorithm that partitions observations into exactly $k$ non-overlapping clusters by repeatedly assigning each observation to the nearest cluster center, called a [[centroid]], and then recalculating the centroids.

## The Real-World Analogy

Imagine you walk into a room with 1,000 investment funds, but nobody has labeled them as value, growth, momentum, defensive, macro, credit-sensitive, or rates-sensitive.

You are not trying to predict next year's return. You are trying to discover natural peer groups.

So you look at observable characteristics:

- Volatility
- Average return
- Drawdown
- Exposure to interest rates
- Exposure to credit spreads
- Sector weights
- Valuation ratios

Then you ask:

> Which funds are actually similar to each other, even if their marketing labels are different?

That is clustering.

K-means is one specific clustering method. It says:

```text
Pick the number of groups you want.
Find the center of each group.
Assign each observation to its closest center.
Move the centers.
Repeat until the groups stop changing.
```

The deeper point:

```text
No target variable
  |
  v
No "correct answer" label
  |
  v
Algorithm searches for structure in X variables
  |
  v
Similar observations are grouped together
```

## One-Minute Version

K-means clustering is an [[unsupervised learning]] algorithm. It does not use a labeled [[target variable]]. Instead, it uses features $X$ to group observations into $k$ clusters.

The researcher must choose $k$ before the algorithm runs. That makes $k$ a [[hyperparameter]].

The algorithm starts with $k$ initial centroids, assigns each observation to the nearest centroid, recalculates each centroid as the mean of the observations assigned to it, and repeats until no observations are reassigned.

The goal is:

```text
High cohesion within clusters
+ High separation between clusters
= Useful clustering
```

K-means is useful for discovering patterns in high-dimensional data, creating peer groups, visualizing data, identifying outliers, and finding alternatives to standard industry or sector classifications.

## LOS Coverage

K-means sits in the CFA Level II Quantitative Methods machine learning LOS:

| LOS language | What you must be able to do |
|---|---|
| Describe [[supervised learning]], [[unsupervised learning]], and [[deep learning]] | Know that K-means is unsupervised because it has no labeled target variable |
| Describe unsupervised machine learning algorithms, including [[principal components analysis]], K-means clustering, and [[Hierarchical Clustering]] | Explain how K-means partitions observations into $k$ clusters using centroids |
| Determine the problems for which unsupervised algorithms are best suited | Use K-means when the goal is grouping, segmentation, similarity analysis, or discovering hidden structure |

## The Big Idea

K-means answers this question:

> Given observations with features, can we divide them into $k$ groups so that observations inside each group are similar and observations in different groups are dissimilar?

That sentence contains the whole algorithm.

It has four key terms:

| Term | Meaning |
|---|---|
| Observation | The thing being grouped: stock, fund, company, bond issuer, customer, transaction |
| Feature | A measurable attribute: return, volatility, leverage, profitability, size, duration, spread |
| Cluster | A group of observations judged similar |
| Centroid | The center or average point of a cluster |

The word "means" in K-means comes from the centroid calculation. Each centroid is the mean of the observations assigned to that cluster.

If a cluster contains three one-dimensional observations:

```text
2, 4, 6
```

The centroid is:

$$
\frac{2 + 4 + 6}{3} = \frac{12}{3} = 4
$$

In two dimensions, if a cluster contains:

```text
(2, 4), (4, 6), (6, 8)
```

The centroid is the coordinate-wise mean:

$$
\bar{x} = \frac{2 + 4 + 6}{3} = 4
$$

$$
\bar{y} = \frac{4 + 6 + 8}{3} = 6
$$

So the centroid is:

$$
(4, 6)
$$

## The Deep Why: Why Clustering Exists

In supervised learning, the model has labels.

For example:

```text
Inputs: leverage, profitability, liquidity
Target: default / no default
```

The model can learn:

```text
These features predict this known outcome.
```

K-means does not have that.

There is no known outcome.

Instead, the question is:

```text
Do the observations naturally organize into groups?
```

That is why K-means is unsupervised. The algorithm is not being told the answer. It is searching for structure in the features themselves.

Why does that matter for CFA?

Because in investment work, the standard labels are often crude.

Two companies may both be classified as technology stocks, but one behaves like a high-duration growth asset and another behaves like a mature cash-flow compounder. Two funds may both be labeled "large-cap blend," but one may behave like a momentum strategy and another like a defensive quality strategy.

K-means can uncover peer groups based on actual measured characteristics rather than labels humans already assigned.

## Cohesion and Separation

A good clustering has two properties:

| Property | Meaning | Intuition |
|---|---|---|
| Cohesion | Observations within the same cluster are close together | Members of a group should resemble each other |
| Separation | Observations in different clusters are far apart | Different groups should be meaningfully distinct |

The visual idea:

```text
Good clustering:

Cluster A        Cluster B        Cluster C
● ● ●            ■ ■ ■            ▲ ▲ ▲
 ● ●              ■ ■              ▲ ▲

High cohesion within each shape
High separation between shapes
```

Bad clustering:

```text
● ■ ▲ ● ■ ▲ ●
 ■ ▲ ● ■ ▲
▲ ● ■ ▲ ● ■

Everything is mixed together.
Clusters do not mean much.
```

The exam phrase to remember:

> K-means minimizes intra-cluster distance and tries to maximize inter-cluster separation, given the chosen $k$.

## Distance Measures

K-means needs a way to decide which centroid is closest.

The most common distance measure is [[Euclidean distance]], the straight-line distance between two points.

For two points:

$$
A = (x_1, y_1)
$$

$$
B = (x_2, y_2)
$$

Euclidean distance is:

$$
d(A,B) = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}
$$

Why squared differences?

Because distance should not depend on direction. A difference of $+3$ and a difference of $-3$ are equally far. Squaring makes both positive.

Why square root?

Because after squaring and adding, the square root brings distance back to the original units.

### Simple Distance Example

Suppose a stock has:

$$
\text{Return} = 8
$$

$$
\text{Volatility} = 12
$$

So its feature point is:

$$
(8, 12)
$$

Centroid A is:

$$
(6, 10)
$$

Centroid B is:

$$
(14, 18)
$$

Distance to A:

$$
d_A = \sqrt{(8 - 6)^2 + (12 - 10)^2}
$$

$$
d_A = \sqrt{2^2 + 2^2}
$$

$$
d_A = \sqrt{4 + 4}
$$

$$
d_A = \sqrt{8} = 2.83
$$

Distance to B:

$$
d_B = \sqrt{(8 - 14)^2 + (12 - 18)^2}
$$

$$
d_B = \sqrt{(-6)^2 + (-6)^2}
$$

$$
d_B = \sqrt{36 + 36}
$$

$$
d_B = \sqrt{72} = 8.49
$$

Because:

$$
2.83 < 8.49
$$

the observation is assigned to Cluster A.

## The K-Means Algorithm

K-means follows an iterative process:

```text
1. Choose k
2. Randomly initialize k centroids
3. Assign each observation to the nearest centroid
4. Recalculate each centroid as the mean of its assigned observations
5. Reassign observations to the nearest updated centroid
6. Repeat until assignments stop changing
```

In diagram form:

```text
Choose k
   |
   v
Place initial centroids
   |
   v
Assign observations to nearest centroid
   |
   v
Recalculate centroids as cluster means
   |
   v
Did assignments change?
   |
   +-- Yes --> repeat assignment/recalculation
   |
   +-- No --> final clusters
```

The algorithm converges when no observation needs to move to a different cluster.

## Worked Numerical Example: One-Dimensional K-Means

Suppose we have six companies measured by one feature: debt-to-capital ratio.

| Company | Debt-to-capital |
|---|---:|
| A | 10 |
| B | 12 |
| C | 14 |
| D | 40 |
| E | 42 |
| F | 44 |

We choose:

$$
k = 2
$$

That means we want exactly two clusters.

### Step 1: Initial Centroids

Assume the initial random centroids are:

$$
C_1 = 10
$$

$$
C_2 = 44
$$

### Step 2: Assign Each Observation To Nearest Centroid

Distance in one dimension is just the absolute difference.

| Company | Value | Distance to $C_1=10$ | Distance to $C_2=44$ | Assigned cluster |
|---|---:|---:|---:|---|
| A | 10 | 0 | 34 | Cluster 1 |
| B | 12 | 2 | 32 | Cluster 1 |
| C | 14 | 4 | 30 | Cluster 1 |
| D | 40 | 30 | 4 | Cluster 2 |
| E | 42 | 32 | 2 | Cluster 2 |
| F | 44 | 34 | 0 | Cluster 2 |

So:

```text
Cluster 1: 10, 12, 14
Cluster 2: 40, 42, 44
```

### Step 3: Recalculate Centroids

New centroid for Cluster 1:

$$
C_1 = \frac{10 + 12 + 14}{3}
$$

$$
C_1 = \frac{36}{3} = 12
$$

New centroid for Cluster 2:

$$
C_2 = \frac{40 + 42 + 44}{3}
$$

$$
C_2 = \frac{126}{3} = 42
$$

### Step 4: Reassign Observations

Now compare each point to:

$$
C_1 = 12
$$

$$
C_2 = 42
$$

| Company | Value | Distance to $C_1=12$ | Distance to $C_2=42$ | Assigned cluster |
|---|---:|---:|---:|---|
| A | 10 | 2 | 32 | Cluster 1 |
| B | 12 | 0 | 30 | Cluster 1 |
| C | 14 | 2 | 28 | Cluster 1 |
| D | 40 | 28 | 2 | Cluster 2 |
| E | 42 | 30 | 0 | Cluster 2 |
| F | 44 | 32 | 2 | Cluster 2 |

No assignments changed.

So the algorithm has converged.

Final clusters:

```text
Low leverage cluster: 10, 12, 14
High leverage cluster: 40, 42, 44
```

## Worked Numerical Example: Two-Dimensional Peer Groups

Suppose we cluster six stocks using two features:

```text
Feature 1 = return volatility
Feature 2 = leverage
```

| Stock | Volatility | Leverage |
|---|---:|---:|
| A | 10 | 20 |
| B | 12 | 22 |
| C | 11 | 19 |
| D | 30 | 70 |
| E | 32 | 72 |
| F | 29 | 68 |

Choose:

$$
k = 2
$$

Suppose after convergence, the centroids are:

$$
C_1 = (11, 20.33)
$$

$$
C_2 = (30.33, 70)
$$

Interpretation:

| Cluster | Interpretation |
|---|---|
| Cluster 1 | Lower volatility, lower leverage stocks |
| Cluster 2 | Higher volatility, higher leverage stocks |

This is not a prediction that Cluster 2 will underperform. K-means does not know future returns unless future returns are included as a feature. It only says the observations in Cluster 2 are similar to one another based on the selected features.

That distinction matters a lot.

## Why Choosing K Is Hard

The researcher chooses $k$ before the algorithm runs.

That is why $k$ is a [[hyperparameter]].

If $k$ is too small:

```text
Different groups get forced together.
Important structure is hidden.
```

If $k$ is too large:

```text
Natural groups get split into overly fine buckets.
The result may be noisy or hard to interpret.
```

Example:

```text
k = 2:
  Stocks split into defensive vs cyclical

k = 10:
  Stocks split into more detailed peer groups

k = 100:
  Clusters may become too granular to be useful
```

CFA emphasizes that the final choice of $k$ can be subjective and depends on the business problem. Analysts may try multiple $k$ values and choose the clustering that has good cohesion, good separation, and face validity.

Face validity means the clusters make practical sense.

For example, if a cluster contains utilities, stable consumer staples, and low-volatility healthcare firms, that may be economically interpretable. If a cluster contains a random mix with no coherent story, the clustering may be less useful even if the math technically converged.

## Why Scaling Matters

Distance-based algorithms are sensitive to scale.

Suppose you cluster companies using:

```text
Market capitalization in dollars
Profit margin in percent
```

Market capitalization may range from:

$$
1{,}000{,}000{,}000 \text{ to } 3{,}000{,}000{,}000{,}000
$$

Profit margin may range from:

$$
-20\% \text{ to } 40\%
$$

If you compute Euclidean distance directly, market capitalization dominates the distance calculation simply because it is measured in huge units.

That does not necessarily mean size is economically more important. It may just mean size has a larger numeric scale.

So features are often standardized before clustering.

The why:

```text
K-means uses distance.
Distance is affected by units.
Different units can dominate the algorithm.
Scaling makes features more comparable.
```

## K-Means vs Hierarchical Clustering

| Feature | [[K-Means Clustering]] | [[Hierarchical Clustering]] |
|---|---|---|
| Type | Unsupervised clustering | Unsupervised clustering |
| Must choose number of clusters first? | Yes, $k$ is chosen before running | Not necessarily |
| Output | Exactly $k$ non-overlapping clusters | Hierarchy of clusters |
| Cluster relationships | No defined relationship among final clusters | Shows nested relationships |
| Speed | Fast; works well on very large datasets | More computationally intensive |
| Useful when | You want a fixed number of groups | You want to examine different levels of granularity |

Exam hook:

> K-means requires pre-specifying $k$; hierarchical clustering can help examine cluster structure without pre-selecting one fixed number in the same way.

## K-Means vs PCA

| Feature | [[K-Means Clustering]] | [[Principal components analysis]] |
|---|---|---|
| ML category | Unsupervised learning | Unsupervised learning |
| Main purpose | Group observations | Reduce dimensions/features |
| Output | Clusters of observations | Principal components |
| Question answered | "Which observations are similar?" | "Can many correlated variables be summarized by fewer composite variables?" |
| CFA trap | Not supervised classification | Not clustering |

PCA and K-means can work together. PCA may first reduce a high-dimensional dataset to a few principal components. Then K-means may cluster observations using those lower-dimensional components.

## K-Means vs KNN

K-means and KNN sound similar because both use $k$ and both involve distance, but they are different tools.

| Feature | [[K-Means Clustering]] | [[k-nearest neighbor]] |
|---|---|---|
| Learning type | Unsupervised | Supervised |
| Uses target labels? | No | Yes |
| Meaning of $k$ | Number of clusters | Number of nearest neighbors |
| Goal | Discover groups | Classify or predict based on nearby labeled examples |
| Output | Cluster assignment | Predicted class or value |

The exam trap:

> K-means $k$ = number of clusters. KNN $k$ = number of neighbors.

## Investment Applications

| Application | How K-means helps |
|---|---|
| Peer group construction | Groups firms by financial and operating characteristics rather than standard sector labels |
| Portfolio diversification | Helps identify assets that are similar, so the portfolio does not accidentally concentrate in one hidden group |
| Hedge fund classification | Groups funds by actual return and risk behavior rather than manager-provided labels |
| Outlier detection | Observations far from centroids may deserve further review |
| Market segmentation | Groups issuers, customers, or securities by shared attributes |
| Data visualization | Helps summarize high-dimensional datasets into interpretable groups |

## Advantages

| Advantage | Why it matters |
|---|---|
| Simple intuition | Assign observations to nearest center |
| Fast | Works well even on very large datasets |
| Useful for exploration | Finds structure when no labels exist |
| Flexible | Can cluster stocks, funds, companies, issuers, transactions, or customers |
| Interpretable if clusters make sense | Centroids and cluster characteristics can be summarized |

## Limitations

| Limitation | Why it matters |
|---|---|
| Must choose $k$ before running | The number of clusters may not be obvious |
| Sensitive to initial centroid placement | Different random starts can produce different final clusters |
| Sensitive to feature scaling | Variables with large numeric units can dominate distance |
| Requires a meaningful distance measure | Bad distance choice creates bad clusters |
| Clusters may be subjective | Final usefulness depends on business context and interpretability |
| No target variable | K-means does not directly predict returns, defaults, or classifications |

## Common Wrong Reasoning

### Wrong: "K-means is supervised because it assigns observations to groups."

Why it is wrong: The groups are not known labels supplied before training. The algorithm creates the groups from the features. That makes it [[unsupervised learning]].

### Wrong: "K-means predicts which stock will outperform."

Why it is wrong: K-means clusters similar stocks. It does not predict future returns unless the analyst builds a separate prediction model after clustering.

### Wrong: "The algorithm chooses the best k automatically."

Why it is wrong: The researcher chooses $k$ before the algorithm runs. Analysts can test different $k$ values, but $k$ is still a hyperparameter.

### Wrong: "The initial centroid locations do not matter."

Why it is wrong: The final clusters can depend on starting centroids. That is why the algorithm may be run several times with different initial centroid locations.

### Wrong: "Cluster names are objective facts."

Why it is wrong: The algorithm outputs groups. Humans interpret and name those groups. A cluster label like "defensive quality" is an analyst interpretation, not something the algorithm inherently knows.

### Wrong: "K-means and KNN are basically the same."

Why it is wrong: K-means is unsupervised clustering. KNN is supervised classification or regression based on nearby labeled observations.

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| No target variable, no labels | Think unsupervised learning |
| Need to group similar observations | Think clustering |
| Need exactly $k$ groups | Think K-means |
| Mentions centroid | Think K-means |
| Mentions bottom-up, top-down, or dendrogram | Think hierarchical clustering |
| Need to reduce many correlated variables | Think PCA |
| Need to predict a category using labeled data | Do not choose K-means; consider supervised classification |
| Asks what $k$ is | Hyperparameter chosen by researcher |

## Minimum Memorization

Memorize this:

```text
K-means = unsupervised clustering
        = choose k
        = assign points to nearest centroid
        = recalculate centroids
        = repeat until stable
```

And this:

```text
Good clusters:
  high cohesion within clusters
  high separation between clusters
```

And this:

```text
K-means k = number of clusters
KNN k = number of neighbors
```

## Can I Solve This?

You are ready for K-means questions if you can answer these:

1. Why is K-means unsupervised?
2. What does $k$ mean in K-means?
3. Why is $k$ a hyperparameter?
4. What is a centroid?
5. Why does the algorithm recalculate centroids?
6. What does convergence mean?
7. Why does scaling matter?
8. How is K-means different from KNN?
9. How is K-means different from PCA?
10. How is K-means different from hierarchical clustering?

## Related Concepts

- [[Machine Learning]]
- [[Unsupervised learning]]
- [[Clustering]]
- [[K-Means Clustering]]
- [[Hierarchical Clustering]]
- [[Dendrogram]]
- [[Principal components analysis]]
- [[Euclidean distance]]
- [[Centroid]]
- [[Cohesion]]
- [[Separation]]
- [[Hyperparameter]]
- [[k-nearest neighbor]]
- [[Portfolio diversification]]
- [[Peer group]]
