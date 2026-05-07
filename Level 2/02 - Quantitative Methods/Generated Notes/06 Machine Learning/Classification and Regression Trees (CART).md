---
title: Classification and Regression Trees (CART)
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, classification, regression]
aliases: [CART, CART models, Classification and Regression Tree, Classification and Regression Trees, Decision tree, Decision trees, Classification tree, Regression tree]
---

# Classification and Regression Trees (CART)

## The Real-World Analogy

Imagine an experienced credit analyst reviewing a company.

The analyst does not begin with one giant equation.

The analyst asks a sequence of practical yes/no questions:

```text
Is leverage high?
  |
  +-- Yes: Is interest coverage weak?
  |       |
  |       +-- Yes: likely high credit risk
  |       +-- No: moderate credit risk
  |
  +-- No: Is cash flow stable?
          |
          +-- Yes: likely lower credit risk
          +-- No: moderate credit risk
```

That is the intuition behind [[CART]].

It is a machine-learning version of a structured decision checklist.

The model learns which question to ask first, which cutoff to use, and which question to ask next.

Instead of forcing the relationship into one smooth equation, CART breaks the data into smaller and smaller regions using if/then rules.

## One-Minute Version

[[CART]] stands for [[classification and regression tree]].

It is a [[supervised learning]] algorithm because it trains on labeled data where the target variable is known.

It can handle two kinds of target variables:

| Target type | CART model | Terminal-node prediction |
|---|---|---|
| Categorical target | Classification tree | Majority class in the terminal node |
| Continuous target | Regression tree | Mean target value in the terminal node |

CART works by recursively splitting the dataset.

At each node, it chooses:

```text
One feature f
One cutoff value c
```

Then it asks a yes/no question:

```text
Is f > c?
```

The split is chosen because it reduces prediction error or classification error.

The tree keeps splitting until a stopping rule is reached. The final endpoints are terminal nodes, also called leaves.

Core memory hook:

```text
CART = one interpretable decision tree

Classification tree:
leaf predicts majority class

Regression tree:
leaf predicts mean value

Strength:
visual if/then explanation

Weakness:
can overfit if unconstrained
```

## LOS Coverage

CART belongs in the CFA Level II [[Quantitative Methods]] machine learning reading.

The relevant LOS asks you to describe supervised machine learning algorithms, including [[penalized regression]], [[support vector machine]], [[k-nearest neighbor]], [[classification and regression tree]], [[ensemble learning]], and [[random forest]], and determine the problems for which they are best suited.

For CART, you should be able to:

| CFA task | What you need to know |
|---|---|
| Identify the learning type | Supervised learning |
| Distinguish classification vs regression trees | Categorical target vs continuous target |
| Explain tree anatomy | Root node, decision nodes, terminal nodes |
| Explain splitting | One feature and one cutoff value at each node |
| Explain predictions | Majority class for classification; mean value for regression |
| Explain overfitting risk | Unconstrained trees can memorize training data |
| Explain regularization/pruning | Limit tree depth, node size, number of nodes, or prune weak branches |
| Compare with random forest | CART is more interpretable; random forest is usually more robust |

## The Big Idea

CART partitions the feature space.

That phrase sounds abstract, so make it concrete.

Suppose the model uses two features:

```text
X1 = investment opportunities growth
X2 = free cash flow growth
```

A CART tree might ask:

```text
Is X1 > 10%?
```

That splits the dataset into two groups.

Then, within one branch, it might ask:

```text
Is X2 > 20%?
```

That splits one group into two smaller groups.

The tree is repeatedly carving up the feature space into regions.

```text
All observations
  |
  v
Split by X1 cutoff
  |
  v
Smaller groups
  |
  v
Split by X2 cutoff
  |
  v
Even smaller groups
  |
  v
Terminal leaves with predictions
```

The prediction depends on which final region the new observation falls into.

That is why CART is easy to explain:

> Follow the path from root node to terminal node.

## Why CART Is Supervised

CART is supervised because it learns from examples with known targets.

For classification:

```text
Features: leverage, cash flow, profitability
Known target: default / no default
```

For regression:

```text
Features: growth, valuation, profitability
Known target: future return
```

The model needs the known target values so it can judge whether a split improves prediction.

Without a target variable, CART would not know what a "good" split means.

That is the deep reason CART is supervised:

```text
Split quality depends on reducing target prediction error.
No target -> no supervised split objective.
```

## Tree Anatomy

CART has three basic node types.

| Node type | Meaning | Exam phrase |
|---|---|---|
| Root node | First split at the top of the tree | Initial question |
| Decision node | Intermediate split | Another feature/cutoff question |
| Terminal node / leaf | Final endpoint | Prediction is made here |

Visual:

```text
Root node
Is ROE > 12%?
  |
  +-- Yes -> Decision node
  |         Is Debt/Capital > 50%?
  |           |
  |           +-- Yes -> Terminal node: Value trap
  |           +-- No  -> Terminal node: Attractive
  |
  +-- No -> Terminal node: Not attractive
```

Each internal node asks one yes/no question.

Each terminal node gives one prediction.

## Binary Splits

CART uses binary splits.

Binary means two branches.

At each split, the model chooses:

```text
Feature f
Cutoff c
```

Then it creates two groups:

```text
f <= c
f > c
```

For example:

```text
P/E <= 15
P/E > 15
```

Why binary splits?

Because binary splits create a simple tree of if/then logic.

Each split is easy to interpret. The price of that simplicity is that the tree may need many splits to approximate complex relationships.

## How CART Chooses Splits

At each node, CART searches for the feature and cutoff that best reduce error.

The CFA phrasing:

> CART chooses the feature and cutoff value at each node that generates the widest separation of the labeled data and minimizes classification error or prediction error.

For classification, the tree wants leaves that are as pure as possible.

Pure means most observations in a leaf belong to the same class.

For regression, the tree wants leaves where target values are close to their leaf mean.

The mechanism:

```text
Candidate split
  |
  v
Separates observations into two groups
  |
  v
Calculate error inside each group
  |
  v
Choose split with greatest error reduction
```

The algorithm repeats this process at each new node.

That is why CART is recursive.

It keeps applying the same splitting logic to smaller and smaller subsets of the data.

## Classification Tree Prediction

A classification tree is used when the target is categorical.

Examples:

```text
Default / no default
Dividend increase / no dividend increase
Fraud / no fraud
Attractive investment / value trap
```

At a terminal node, the prediction is the majority class.

Suppose a terminal node contains:

| Class | Count |
|---|---:|
| Dividend increase | 15 |
| No dividend increase | 5 |

The prediction is:

```text
Dividend increase
```

Why?

Because among the training observations that followed the same path, most ended in that class.

The hidden assumption:

> New observations that fall into the same terminal region will behave like the training observations in that region.

## Regression Tree Prediction

A regression tree is used when the target is continuous.

Examples:

```text
Future return
Credit spread
Stock price
Earnings growth
```

At a terminal node, the prediction is the mean target value of training observations in that leaf.

Suppose a terminal node contains three observations with future returns:

| Observation | Future return |
|---|---:|
| A | 8% |
| B | 10% |
| C | 14% |

The regression tree prediction is:

$$
\frac{8\% + 10\% + 14\%}{3}
$$

Add the numerator:

$$
8\% + 10\% + 14\% = 32\%
$$

Divide by 3:

$$
\frac{32\%}{3} = 10.67\%
$$

So the predicted return is:

$$
10.67\%
$$

Why use the mean?

Because within that terminal node, the tree treats the observations as comparable. The mean is the simplest prediction that minimizes squared error inside that leaf.

## Worked Classification Example

Suppose an analyst wants to predict whether a company will increase its dividend.

The tree uses two features:

```text
IOG = investment opportunities growth
FCFG = free cash flow growth
```

The tree:

```text
Root: Is IOG > 10%?
  |
  +-- No  -> Terminal node: No dividend increase
  |
  +-- Yes -> Is FCFG > 20%?
              |
              +-- Yes -> Terminal node: Dividend increase
              |
              +-- No  -> Terminal node: No dividend increase
```

Now classify a company:

```text
IOG = 14%
FCFG = 25%
```

Step 1:

```text
Is IOG > 10%?
14% > 10% -> Yes
```

Move to the next decision node.

Step 2:

```text
Is FCFG > 20%?
25% > 20% -> Yes
```

Prediction:

```text
Dividend increase
```

Now classify another company:

```text
IOG = 14%
FCFG = 12%
```

Step 1:

```text
14% > 10% -> Yes
```

Step 2:

```text
12% > 20% -> No
```

Prediction:

```text
No dividend increase
```

The important idea is not the dividend example itself. The important idea is the path:

```text
Feature values
  |
  v
Follow yes/no branches
  |
  v
Reach terminal node
  |
  v
Use terminal-node prediction
```

## Feature Space Partitioning

CART turns the feature space into boxes.

With two features, you can visualize the tree as cutting a chart into rectangles.

```text
FCFG
 ^
 |          Dividend increase
 |          if IOG > 10 and FCFG > 20
 |
20% -------------------------------
 |          No dividend increase
 |
 |
 +------------------------------->
              10%              IOG
```

Each split draws a vertical or horizontal boundary because each split uses one feature at a time.

This is different from [[Support Vector Machines]], where the boundary can be a slanted hyperplane or more complex kernel-transformed boundary.

CART boundaries are easy to explain:

```text
If X1 is above this cutoff, go right.
If X1 is below this cutoff, go left.
```

## Nonlinear Relationships and Interactions

CART is useful when relationships are nonlinear.

A linear model might say:

```text
Higher profitability always increases attractiveness by the same amount.
```

CART can say:

```text
Profitability matters only if the stock is cheap
and leverage is high
and sales are expanding.
```

That is an interaction.

The effect of one feature depends on the values of other features.

The CFA source gives this idea with value traps:

```text
High profitability may matter only after conditions involving valuation,
leverage, and sales growth have already been met.
```

This is hard for simple linear models because linear models usually impose one average relationship across the whole dataset unless interaction terms are explicitly added.

CART finds interactions naturally through sequential splits.

## Same Feature Can Appear More Than Once

A feature can appear multiple times in a tree with different cutoff values.

Example:

```text
Root: Is IOG > 10%?

Later branch:
Is IOG > 5%?
```

Why would that happen?

Because a feature may matter differently in different regions of the data.

The first split might separate high-growth firms from others.

A later split might refine a lower-growth subgroup.

This is another way CART captures nonlinear structure.

The same variable does not need to have one single global effect.

## Why CART Overfits

CART can overfit badly if unconstrained.

Why?

Because it can keep splitting until the terminal nodes become tiny.

Tiny leaves can perfectly fit quirks in the training data.

```text
More splits
  |
  v
Smaller terminal nodes
  |
  v
Lower training error
  |
  v
Higher risk of memorizing noise
  |
  v
Worse out-of-sample performance
```

This is the same bias-variance trade-off.

| Tree size | Bias | Variance | Risk |
|---|---:|---:|---|
| Too shallow | High | Low | Underfitting |
| Too deep | Low | High | Overfitting |
| Properly constrained | Balanced | Balanced | Better generalization |

An unconstrained tree can look brilliant in-sample and fail out-of-sample.

That is the CART danger.

## Regularization and Pruning

CART controls overfitting through constraints and pruning.

Common controls:

| Control | What it does | Why it helps |
|---|---|---|
| Maximum tree depth | Limits how many levels the tree can grow | Prevents overly specific rules |
| Minimum observations per node/leaf | Requires enough data in a node | Avoids tiny leaves built on noise |
| Maximum number of decision nodes | Limits total complexity | Keeps tree simpler |
| Pruning | Removes branches with little predictive value | Cuts back overgrown tree |

Regularization means limiting model complexity.

Pruning means cutting back parts of the tree after growth.

The deep reason both help:

```text
Tree complexity
  |
  v
Training fit improves
  |
  v
But variance rises
  |
  v
Regularization/pruning sacrifices some training fit
  |
  v
Out-of-sample generalization may improve
```

## Why CART Is Interpretable

CART is popular because the tree gives a visual explanation.

You can show an investment committee:

```text
This company was classified as attractive because:
P/E < 15
Debt/Capital <= 50%
Sales growth > 15%
Profitability high
```

That is different from many black-box algorithms.

With CART, the reasoning path is visible.

This matters when the user of the model needs to understand or defend the decision.

But there is a trade-off.

A single CART is interpretable, but it can be unstable and high variance.

A [[random forest]] is usually more stable, but less interpretable.

## Investment Applications

| Application | How CART helps |
|---|---|
| Fraud detection | Identify if/then patterns in financial statement data |
| Equity selection | Build transparent rules for attractive vs unattractive securities |
| Fixed-income selection | Classify bonds using issuer and issue characteristics |
| Default prediction | Classify firms into default-risk groups |
| Investment committee communication | Show visual decision paths |
| Expert systems | Create consistent decision processes |

CART is especially useful when the analyst wants a model that can capture nonlinear interactions but still be explained.

## CART vs Logistic Regression

| Feature | CART | [[Logistic regression]] |
|---|---|---|
| Main use | Classification or regression | Mainly binary classification in CFA ML context |
| Form | Tree of if/then rules | Smooth probability model |
| Handles nonlinear interactions | Naturally through splits | Requires explicit interaction/nonlinear terms |
| Interpretability | Visual path | Coefficients/odds/probabilities |
| Boundary shape | Axis-aligned boxes | Smooth linear boundary in transformed log-odds space |

Logistic regression is useful when the relationship can be represented well by a parametric probability model.

CART is useful when the decision logic is conditional and nonlinear:

```text
This variable matters only after that condition is met.
```

## CART vs KNN

| Feature | CART | [[k-nearest neighbor]] |
|---|---|---|
| Learning type | Supervised | Supervised |
| Main logic | Split data using feature cutoffs | Predict using nearest labeled neighbors |
| Needs distance metric? | No | Yes |
| Needs $k$ neighbors? | No | Yes |
| Explanation | Follow tree path | Neighbor-based, less global rule structure |

CFA exam hook:

> CART can be preferable to KNN when the analyst wants a visual explanation and does not want to specify a distance measure or initial $k$.

## CART vs SVM

| Feature | CART | [[Support Vector Machines]] |
|---|---|---|
| Main logic | Recursive if/then splits | Maximum-margin boundary |
| Boundary | Axis-aligned splits | Hyperplane or kernel boundary |
| Interpretability | High | Lower |
| Nonlinearity | Captured with multiple splits | Captured with kernels or soft margin extensions |

Memory hook:

```text
CART asks:
Which feature split cleans up the groups?

SVM asks:
Where is the widest separating margin?
```

## CART vs Random Forest

| Feature | [[CART]] | [[Random forest]] |
|---|---|---|
| Number of trees | One | Many |
| Prediction | One path to one leaf | Majority vote or average across many trees |
| Interpretability | High | Lower |
| Variance | Higher | Lower |
| Overfitting risk | Higher if unconstrained | Lower because bagging/averaging reduces variance |
| Best use | Explanation and transparent rules | Predictive accuracy and robustness |

The clean exam sentence:

> CART is easier to interpret; random forest usually generalizes better.

## Common Wrong Reasoning

### Wrong: "CART is unsupervised because it creates groups."

Why it is wrong: CART uses labeled training data. The target is known during training.

Correct idea:

```text
CART = supervised
Clustering = unsupervised
```

### Wrong: "CART can only classify."

Why it is wrong: CART stands for classification and regression tree. It can handle categorical or continuous targets.

Correct idea:

```text
Categorical target -> classification tree
Continuous target -> regression tree
```

### Wrong: "A regression tree predicts the majority class."

Why it is wrong: Majority class is for classification. A regression tree predicts the mean target value in the terminal node.

Correct idea:

```text
Classification leaf -> majority class
Regression leaf -> mean value
```

### Wrong: "A deeper tree is always better."

Why it is wrong: A deeper tree may reduce training error by memorizing noise, increasing variance and overfitting risk.

Correct idea:

```text
More depth -> lower in-sample error, higher overfitting risk
```

### Wrong: "Random forest is more interpretable than CART."

Why it is wrong: A single CART tree gives a visible decision path. A random forest combines many trees, which usually improves robustness but reduces interpretability.

Correct idea:

```text
CART = more interpretable
Random forest = usually more robust
```

### Wrong: "A feature can appear only once in a tree."

Why it is wrong: The same feature can appear at different nodes with different cutoff values if it helps classification or prediction in different regions.

Correct idea:

```text
Same feature can reappear lower in the tree.
```

## When You See This, Do This

| If the question says... | Think... |
|---|---|
| Root node, decision node, terminal node | CART |
| If/then visual decision path | CART |
| Feature plus cutoff value | CART split |
| Categorical target | Classification tree |
| Continuous target | Regression tree |
| Majority class at leaf | Classification tree |
| Mean value at leaf | Regression tree |
| Overfitting from too many branches | Regularize/prune CART |
| Many trees, bagging, random feature subsets | Random forest |
| Need interpretability | CART may beat black-box models |
| Need more robust prediction than one tree | Random forest may beat CART |

## Minimum Memorization

```text
CART = Classification and Regression Tree

Supervised learning

At each node:
Choose one feature and one cutoff
Split into two branches

Classification tree:
terminal node predicts majority class

Regression tree:
terminal node predicts mean target value

Strength:
visual, interpretable, captures nonlinear interactions

Weakness:
can overfit if tree is too deep

Fix:
max depth, min node population, max decision nodes, pruning
```

## Can I Solve This?

You are ready if you can answer these without looking:

1. Why is CART supervised?
2. What does CART stand for?
3. When does CART produce a classification tree?
4. When does CART produce a regression tree?
5. What is a root node?
6. What is a terminal node?
7. How does CART choose a split?
8. Why does CART use one feature and one cutoff at each node?
9. How does a classification tree make a prediction at a leaf?
10. How does a regression tree make a prediction at a leaf?
11. Why can the same feature appear more than once?
12. Why can CART overfit?
13. How do max depth and pruning help?
14. Why is CART more interpretable than random forest?
15. Why might random forest predict better than a single CART?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[CART]]
- [[Decision tree]]
- [[Classification and regression tree]]
- [[Classification]]
- [[Regression]]
- [[Logistic regression]]
- [[Support Vector Machines]]
- [[k-nearest neighbor]]
- [[Random Forests]]
- [[Random forest]]
- [[Ensemble learning]]
- [[Bagging]]
- [[Overfitting]]
- [[Regularization]]
- [[Pruning]]
- [[Cross-validation]]
- [[Confusion Matrix]]
- [[Level 2/Generated Notes/02 - Quantitative Methods/Root Mean Squared Error (RMSE)]]
