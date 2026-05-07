---
title: Hierarchical Clustering
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, unsupervised-learning, clustering]
aliases: [Hierarchical clustering, Agglomerative clustering, Divisive clustering, Dendrogram clustering, Heirarchical clustering]
---

# Hierarchical Clustering

## The Real-World Analogy

Imagine you are organizing a family reunion photo.

At the lowest level, every person is an individual.

Then you group siblings together.

Then families.

Then branches of the family tree.

Then eventually everyone belongs to one big family.

That is the intuition behind [[Hierarchical Clustering]].

It does not just create one flat set of groups. It creates a hierarchy:

```text
Individuals
  |
  v
Small clusters
  |
  v
Larger clusters
  |
  v
One full dataset cluster
```

In finance, instead of family members, the observations might be stocks, bonds, funds, companies, or clients.

The algorithm asks:

> Which observations are similar, and how do small similarity groups combine into larger similarity groups?

That is why hierarchical clustering is often visualized as a tree called a [[dendrogram]].

## One-Minute Version

[[Hierarchical Clustering]] is an [[unsupervised learning]] algorithm that builds a hierarchy of clusters.

It is a clustering method, so it groups observations, not features.

It is unsupervised because there is no target variable. The model is not told the correct group labels. It must infer structure from the features.

There are two main approaches:

| Approach | Direction | How it works |
|---|---|---|
| Agglomerative clustering | Bottom-up | Start with each observation as its own cluster, then merge closest clusters |
| Divisive clustering | Top-down | Start with all observations in one cluster, then split into smaller clusters |

The most common version is agglomerative, bottom-up hierarchical clustering.

The big CFA distinction:

```text
K-means:
Choose k first, then cluster.

Hierarchical clustering:
Build the hierarchy first, then choose how many clusters by cutting the dendrogram.
```

## LOS Coverage

Hierarchical clustering belongs in the CFA Level II [[Quantitative Methods]] machine learning reading.

The relevant LOS asks you to describe unsupervised machine learning algorithms, including [[Principal Component Analysis]], [[K-Means Clustering]], and [[Hierarchical Clustering]], and determine the problems for which they are best suited.

For hierarchical clustering, you should be able to:

| CFA task | What you need to know |
|---|---|
| Identify the learning type | Unsupervised learning |
| Identify the task | Clustering, not classification or regression |
| Explain the output | A hierarchy of clusters, often shown with a dendrogram |
| Explain agglomerative clustering | Bottom-up merging of closest clusters |
| Explain divisive clustering | Top-down splitting of one large cluster |
| Compare with K-means | Hierarchical does not require pre-specifying $k$ |
| Explain use cases | Diversification, risk concentration, hidden peer groups |

## The Big Idea

Clustering means grouping observations based on similarity.

The word "observations" matters.

If the dataset is stocks, clustering groups stocks.

If the dataset is bonds, clustering groups bonds.

If the dataset is clients, clustering groups clients.

It does not reduce the number of variables. That is [[Dimensionality Reduction]].

```text
Clustering:
Rows / observations are grouped.

Dimensionality reduction:
Columns / features are reduced.
```

Hierarchical clustering is one type of clustering.

It builds nested clusters, which means small clusters can sit inside bigger clusters.

```text
Stock A
Stock B
  |
  v
Bank-stock cluster
  |
  v
Financial-stock cluster
  |
  v
Large equity-market cluster
```

This is useful because similarity can exist at different levels.

Two bank stocks may be very similar to each other. They may also be somewhat similar to insurance stocks. Together, banks and insurers may be part of a broader financials cluster.

Hierarchical clustering can show that layered structure.

## Why Clustering Exists

Analysts often need to discover groups that are not obvious from labels.

For example, industry labels might say:

```text
Technology
Healthcare
Financials
Energy
```

But actual return behavior might reveal different groups:

```text
Interest-rate-sensitive stocks
High-growth stocks
Defensive cash-flow stocks
Commodity-sensitive stocks
Distressed balance sheet stocks
```

The point is not just to label things.

The point is to discover hidden structure.

For clustering to be useful, it should have:

| Property | Meaning | Why it matters |
|---|---|---|
| Cohesion | Observations inside a cluster are similar | A cluster should be internally coherent |
| Separation | Different clusters are dissimilar | Clusters should not all blur together |

Good clustering:

```text
Cluster A      Cluster B      Cluster C
o o o          x x x          + + +
 o o            x x            + +
```

Bad clustering:

```text
o x + o x + o x +
x + o x + o x + o
```

If observations inside clusters are not similar, the groups are not meaningful.

If different clusters are not separate, the grouping adds little information.

## Why Hierarchical Clustering Is Unsupervised

Hierarchical clustering is [[unsupervised learning]] because there is no labeled target variable.

It does not use:

```text
Y = known answer
```

It only uses:

```text
X variables = features / attributes
```

The algorithm is not told:

```text
This stock belongs to group 1.
This bond belongs to group 2.
This company is a default risk.
```

Instead, it is given observations and features, then asked to infer similarity.

The deep reason this matters:

Supervised learning evaluates predictions against known answers.

Unsupervised learning does not have known answers, so judgment matters more. The analyst must decide whether the discovered clusters are economically meaningful.

## Agglomerative Clustering: Bottom-Up

Agglomerative hierarchical clustering starts with each observation as its own cluster.

Then it repeatedly merges the closest clusters.

The flow:

```text
Start:
A   B   C   D   E

Merge closest:
(A,B)   C   D   E

Merge next closest:
(A,B)   (C,D)   E

Merge next:
(A,B)   (C,D,E)

Final:
(A,B,C,D,E)
```

Step-by-step:

| Step | What happens |
|---|---|
| 1 | Treat every observation as its own cluster |
| 2 | Measure distance between observations or clusters |
| 3 | Merge the two closest clusters |
| 4 | Recalculate distances between the new cluster and other clusters |
| 5 | Repeat until all observations are in one cluster |

This is called bottom-up because the algorithm begins with the smallest possible clusters and builds upward.

Why is this common?

Because it is intuitive and produces a full record of how observations combine.

The final output is not just one answer. It is the whole hierarchy.

## Divisive Clustering: Top-Down

Divisive hierarchical clustering works in the opposite direction.

It starts with all observations in one cluster.

Then it repeatedly splits clusters into smaller clusters.

The flow:

```text
Start:
(A,B,C,D,E)

Split:
(A,B)   (C,D,E)

Split again:
(A,B)   (C,D)   E

Split again:
A   B   C   D   E
```

This is called top-down because the algorithm starts with the global structure and partitions downward.

CFA contrast:

| Method | Starting point | Direction |
|---|---|---|
| Agglomerative | Each observation alone | Bottom-up |
| Divisive | All observations together | Top-down |

The curriculum emphasizes both, but agglomerative is usually the more commonly discussed approach.

## Dendrogram

A [[dendrogram]] is a tree diagram that shows the hierarchy of clusters.

It shows:

| Dendrogram feature | Meaning |
|---|---|
| Leaves | Individual observations |
| Branches | Cluster relationships |
| Merge height | Distance or dissimilarity at which clusters merge |
| Horizontal cut | Chosen number of clusters |

Simple example:

```text
Distance
  8 |                 +--------- A,B,C,D
    |                 |
  5 |        +--------+
    |        |        |
  2 |   +----+        +---- C,D
    |   |    |
  1 |   A    B
    |
    +--------------------------------
        A    B        C    D
```

The lower the merge, the more similar the observations or clusters are.

The higher the merge, the more dissimilar they are.

If two observations merge at distance 1, they are closer than two clusters that merge at distance 8.

The dendrogram gives the analyst a visual way to choose the cluster count.

## Choosing the Number of Clusters

K-means requires the analyst to choose $k$ before running the algorithm.

Hierarchical clustering does not.

Instead, hierarchical clustering builds the full tree. Then the analyst chooses the number of clusters by cutting the dendrogram at a chosen height.

```text
Build tree first.
Cut tree second.
Count clusters third.
```

If you cut the tree high, you get fewer broad clusters.

If you cut the tree low, you get more detailed clusters.

```text
High cut:
Few broad groups

Low cut:
Many narrow groups
```

Why does this matter?

Because sometimes the analyst does not know how many clusters should exist before seeing the data.

Hierarchical clustering is useful when the number of natural groups is unknown.

## Distance and Similarity

Hierarchical clustering needs a measure of distance or similarity.

Common ideas:

| Measure | Meaning | Finance use |
|---|---|---|
| Euclidean distance | Straight-line distance between observations | Numeric financial ratios |
| Correlation similarity | Similar movement patterns | Return-based security clustering |
| Domain-specific distance | Analyst-defined similarity | Credit, risk, or business-model comparability |

Why does distance matter?

Because distance determines which observations merge first.

If the distance measure is poor, the hierarchy is poor.

Mechanism:

```text
Bad distance metric
  |
  v
Wrong observations appear "close"
  |
  v
Wrong clusters merge early
  |
  v
Dendrogram suggests misleading structure
```

This is why CFA emphasizes judgment. Human understanding of the data and the business objective matters.

## Linkage: Distance Between Clusters

After the first merge, the algorithm must measure distance between clusters, not just individual observations.

Suppose A and B have merged into one cluster:

```text
(A,B)
```

Now the algorithm must ask:

> How far is cluster (A,B) from observation C?

There are different linkage rules.

| Linkage idea | How it thinks |
|---|---|
| Single linkage | Distance between closest members |
| Complete linkage | Distance between farthest members |
| Average linkage | Average distance across members |

CFA usually does not require heavy linkage calculations, but the intuition is important:

> Different linkage choices can produce different cluster trees.

Why?

Because "distance between groups" is not automatically obvious once groups contain more than one observation.

## Worked Numerical Example: Merge Sequence

Suppose an analyst clusters four stocks based on return similarity.

The distance matrix is:

| Pair | Distance |
|---|---:|
| A-B | 1 |
| C-D | 2 |
| A-C | 6 |
| A-D | 7 |
| B-C | 5 |
| B-D | 8 |

Lower distance means more similar.

### Step 1: Start With Each Observation Alone

```text
A   B   C   D
```

Each stock is its own cluster.

### Step 2: Merge the Closest Pair

The smallest distance is:

```text
A-B = 1
```

So A and B merge first.

```text
(A,B)   C   D
```

In the dendrogram, A and B merge at height 1.

### Step 3: Merge the Next Closest Pair

The next smallest distance is:

```text
C-D = 2
```

So C and D merge.

```text
(A,B)   (C,D)
```

In the dendrogram, C and D merge at height 2.

### Step 4: Merge the Two Larger Clusters

Now the algorithm merges:

```text
(A,B) with (C,D)
```

Suppose the linkage rule gives a cluster distance of 6.5.

Then the final merge occurs at height 6.5.

```text
((A,B),(C,D))
```

### Dendrogram Interpretation

```text
Distance
  7 |             +----------------+
    |             |                |
  2 |      +------+          +-----+
    |      |                 |
  1 |  +---+                 |
    |  |                     |
    +--------------------------------
       A      B              C     D
```

Interpretation:

| Merge | Height | Meaning |
|---|---:|---|
| A with B | 1 | A and B are very similar |
| C with D | 2 | C and D are similar, but less close than A-B |
| (A,B) with (C,D) | 6.5 | The two groups are much less similar to each other |

If the analyst wants two clusters, cut the dendrogram between height 2 and 6.5.

The result:

```text
Cluster 1: A, B
Cluster 2: C, D
```

The exam idea:

> Large vertical gaps in the dendrogram often indicate natural separation between clusters.

## Investment Applications

Hierarchical clustering can help in investment management because observed behavior may reveal hidden groupings.

| Application | How hierarchical clustering helps |
|---|---|
| [[Diversification]] | Choose assets from different clusters instead of accidentally holding similar exposures |
| Portfolio risk concentration | Detect whether holdings are concentrated in one hidden cluster |
| Peer group analysis | Identify economically similar firms beyond industry labels |
| Security grouping | Cluster stocks or bonds based on returns, fundamentals, or risk attributes |
| Regime or behavior analysis | Detect layered similarity patterns across observations |

Example:

Two stocks may belong to different official sectors but move similarly because both are sensitive to interest rates.

Hierarchical clustering may put them in the same cluster.

That matters because a portfolio that looks diversified by sector may not be diversified by actual return behavior.

## Hierarchical Clustering vs K-Means

Both [[Hierarchical Clustering]] and [[K-Means Clustering]] are unsupervised clustering methods.

They both group observations.

But they differ in how the clustering is created.

| Feature | Hierarchical clustering | K-means clustering |
|---|---|---|
| Learning type | Unsupervised | Unsupervised |
| Groups rows or columns? | Rows / observations | Rows / observations |
| Need to choose $k$ first? | No | Yes |
| Output | Hierarchy / dendrogram | $k$ flat clusters |
| Main logic | Merge or split clusters by distance | Assign observations to nearest centroid |
| Best when | Number of clusters is unknown or hierarchy matters | Large datasets with known desired $k$ |
| Visualization | Dendrogram | Cluster plot / centroids |

Memory hook:

```text
K-means asks:
How do I split data into exactly k groups?

Hierarchical clustering asks:
What does the whole family tree of similarity look like?
```

## Hierarchical Clustering vs PCA

Hierarchical clustering and [[Principal Component Analysis]] are both unsupervised, but they solve different problems.

| Feature | Hierarchical clustering | PCA |
|---|---|---|
| Main task | Clustering | Dimensionality reduction |
| Acts on | Observations / rows | Features / columns |
| Output | Dendrogram and clusters | Principal components |
| Goal | Group similar observations | Reduce many correlated features |

Memory hook:

```text
PCA reduces columns.
Clustering groups rows.
```

This is a high-probability exam distinction.

If a question says "reduce many correlated features," think PCA.

If a question says "group observations into similar categories," think clustering.

## Hierarchical Clustering vs KNN

Hierarchical clustering and [[k-nearest neighbor]] both use similarity, but they are not the same.

| Feature | Hierarchical clustering | KNN |
|---|---|---|
| Learning type | Unsupervised | Supervised |
| Uses labels? | No | Yes |
| Main output | Clusters | Predicted class or value |
| Similarity role | Builds groups from unlabeled observations | Finds labeled neighbors for prediction |

The easy trap:

```text
Similarity alone does not mean supervised.
Labels decide supervised vs unsupervised.
```

## Strengths

| Strength | Why it helps |
|---|---|
| Does not require pre-specifying $k$ | Useful when natural number of groups is unknown |
| Dendrogram is visual | Helps analyst inspect nested structure |
| Reveals layered relationships | Shows small groups inside broader groups |
| Useful for exploration | Good for discovering hidden similarity patterns |

Hierarchical clustering is especially helpful when the analyst wants to understand the structure of the dataset, not just force observations into a pre-chosen number of groups.

## Limitations

| Limitation | Why it matters |
|---|---|
| Sensitive to distance metric | Different similarity definitions can change results |
| Sensitive to linkage method | Different merge rules can produce different trees |
| Can be computationally intensive | Less convenient for very large datasets than K-means |
| Clusters may lack clear labels | Analyst must interpret what the groups mean |
| Early merge/split decisions can matter | The hierarchy can preserve earlier choices |

The deepest limitation is interpretability.

The algorithm can say:

```text
These observations are close under your distance rule.
```

But it cannot automatically say:

```text
This cluster is economically meaningful.
```

That is the analyst's job.

## Common Wrong Reasoning

### Wrong: "Hierarchical clustering is supervised because it creates categories."

Why it is wrong: The categories are discovered, not provided as labels. There is no target variable.

Correct idea:

```text
No labeled Y -> unsupervised
```

### Wrong: "Hierarchical clustering requires choosing $k$ before clustering."

Why it is wrong: That describes K-means. Hierarchical clustering builds the tree first. The analyst can choose clusters afterward by cutting the dendrogram.

Correct idea:

```text
K-means: choose k first.
Hierarchical: build tree first.
```

### Wrong: "PCA and hierarchical clustering both group observations."

Why it is wrong: PCA reduces features. Hierarchical clustering groups observations.

Correct idea:

```text
PCA -> columns/features
Hierarchical clustering -> rows/observations
```

### Wrong: "A dendrogram is just decoration."

Why it is wrong: The dendrogram shows the sequence and distance of merges. It helps choose the number of clusters.

Correct idea:

```text
Dendrogram height = dissimilarity at merge
Horizontal cut = chosen cluster count
```

### Wrong: "The clusters are automatically economically meaningful."

Why it is wrong: The clusters depend on feature choice, scaling, distance measure, and linkage rule. Human interpretation is required.

Correct idea:

```text
Algorithm finds mathematical similarity.
Analyst determines economic meaning.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Unlabeled data grouped by similarity | Clustering |
| Hierarchy of clusters | Hierarchical clustering |
| Dendrogram | Hierarchical clustering |
| Bottom-up merging | Agglomerative clustering |
| Top-down splitting | Divisive clustering |
| Need $k$ specified before clustering | K-means |
| Unknown number of natural groups | Hierarchical clustering may fit |
| Reduce many correlated variables | PCA, not clustering |
| Group securities for diversification | Clustering |
| Portfolio concentrated in one hidden group | Cluster concentration risk |

## Minimum Memorization

```text
Hierarchical clustering = unsupervised clustering

Goal:
Group observations by similarity

Output:
Hierarchy of clusters, often shown as dendrogram

Agglomerative:
Bottom-up
Start with each observation alone
Merge closest clusters

Divisive:
Top-down
Start with one big cluster
Split into smaller clusters

K-means:
Choose k before clustering

Hierarchical:
Do not need k before clustering
Choose cluster count by cutting dendrogram
```

Most important exam distinction:

```text
PCA reduces features.
Clustering groups observations.
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. Why is hierarchical clustering unsupervised?
2. What is the difference between clustering and classification?
3. What does a dendrogram show?
4. What does merge height mean in a dendrogram?
5. How does agglomerative clustering work?
6. How does divisive clustering work?
7. Why does hierarchical clustering not require pre-specifying $k$?
8. How do you choose the number of clusters from a dendrogram?
9. How is hierarchical clustering different from K-means?
10. How is hierarchical clustering different from PCA?
11. Why do distance measures matter?
12. Why can linkage choices affect the result?
13. How can clustering help diversification?
14. Why are clusters not automatically economically labeled?

## Related Concepts

- [[Machine Learning]]
- [[Unsupervised learning]]
- [[Clustering]]
- [[Hierarchical Clustering]]
- [[Dendrogram]]
- [[K-Means Clustering]]
- [[Principal Component Analysis]]
- [[Dimensionality Reduction]]
- [[k-nearest neighbor]]
- [[Cohesion]]
- [[Separation]]
- [[Euclidean distance]]
- [[Correlation]]
- [[Feature selection]]
- [[Feature engineering]]
- [[Diversification]]
- [[Portfolio risk]]
- [[Risk concentration]]
