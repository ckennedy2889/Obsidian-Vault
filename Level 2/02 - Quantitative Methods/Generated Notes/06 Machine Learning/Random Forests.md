---
title: Random Forests
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, ensemble-learning]
aliases: [Random Forest, Random Forest Classifier, Random Forest Regression, RF]
---

# Random Forests

> A [[random forest]] is a crowd of [[decision tree|decision trees]]. Each tree sees a slightly different version of the data, each tree makes a prediction, and the forest combines the predictions by majority vote for classification or by averaging for regression.

## The Real-World Analogy

Imagine you are deciding whether a company will default.

You could ask one credit analyst. That analyst might be very smart, but maybe she overweights leverage because the last default she studied had extreme leverage. A single analyst can be sharp but noisy.

Now imagine asking 500 analysts. Each analyst sees a slightly different sample of companies and is asked to focus on a different subset of variables: one sees [[leverage]], [[profitability]], and liquidity; another sees [[sales growth]], interest coverage, and size; another sees cash flow volatility and margins. Each analyst gives a vote: default or no default.

The final decision is not one analyst's fragile opinion. It is the majority vote of many imperfect analysts.

That is a random forest.

The deeper point is this:

```text
One tree
  |
  v
Can learn real nonlinear patterns, but may overfit noise
  |
  v
Many different trees
  |
  v
Noise cancels out more than signal
  |
  v
Lower variance and better out-of-sample prediction
```

## One-Minute Version

A [[random forest]] is a [[supervised learning]] algorithm and an [[ensemble learning]] method. It builds many [[CART]]-style decision trees using [[bagging]] and random subsets of features. For a classification problem, each tree votes for a class and the majority wins. For a regression problem, each tree predicts a number and the forest averages the predictions.

The point is to fix the weakness of a single [[classification and regression tree]]. A single tree is easy to interpret, but it has high [[variance]]: small changes in the training data can create a very different tree. A random forest deliberately creates many different trees and then averages away their individual mistakes. That usually improves [[out-of-sample]] performance and makes the model more robust to noisy data.

The trade-off is interpretability. One tree is a clean if-then explanation. A forest of hundreds of trees is harder to explain, so random forests are often treated as more of a [[black box]] than CART.

## LOS Coverage

Random forests sit inside the CFA Level II Quantitative Methods machine learning LOS:

| LOS language | What you must be able to do |
|---|---|
| Describe supervised machine learning algorithms, including [[penalized regression]], [[support vector machine]], [[k-nearest neighbor]], [[classification and regression tree]], [[ensemble learning]], and [[random forest]] | Know what random forests are, how they work, and why they are supervised |
| Determine the problems for which they are best suited | Choose random forests for labeled data, nonlinear relationships, noisy data, and prediction problems where accuracy matters more than simple interpretability |
| Describe [[overfitting]] and methods of addressing it | Understand why bagging, random feature subsets, and averaging reduce variance and help generalize out-of-sample |

## The Big Idea

Random forest starts with this problem:

> A single tree is powerful because it can capture nonlinear interactions, but dangerous because it can memorize the training sample.

Why can a tree memorize?

A [[CART]] model keeps splitting the data into smaller and smaller groups. At each [[node]], it asks a yes/no question:

```text
Is leverage > 60%?
Is sales growth < 0%?
Is interest coverage < 2.0x?
```

If the tree is allowed to keep splitting, it can eventually create tiny terminal nodes that fit quirks in the training data. Those quirks may not be real relationships. They may just be noise.

That is [[overfitting]]:

```text
Training sample:
  "I explain this very well."

New data:
  "I fail because I learned noise, not structure."
```

A random forest handles this by building many trees that are deliberately different from one another.

It creates diversity in two ways:

1. **Different observations**: each tree is trained on a bootstrap sample, meaning a random sample drawn with replacement from the original training data.
2. **Different features**: at each split, the tree considers only a random subset of available features.

Then it aggregates the predictions.

That aggregation is the magic. A single tree may make a noisy mistake. But if many trees make different noisy mistakes, the errors partly cancel.

## The Deep Why: Why Many Trees Beat One Tree

Start with the rule:

> Random forests reduce overfitting by averaging many different decision trees.

Now ask why.

A prediction error can be thought of as having three pieces:

```text
Prediction error = bias error + variance error + irreducible error
```

| Error type | Meaning | What it looks like |
|---|---|---|
| [[Bias]] error | The model is too simple and misses the true structure | Underfitting |
| [[Variance]] error | The model is too sensitive to the training sample | Overfitting |
| Irreducible error | Randomness no model can remove | Noise in the world |

A single deep tree tends to have low bias but high variance.

Low bias because it can fit complex shapes:

```text
Leverage only matters if profitability is low.
Profitability only matters if the stock is cheap.
Cash flow growth only matters if debt is high.
```

Those are interaction effects. Linear models struggle with them unless the analyst manually builds interaction terms. Trees capture them naturally.

But high variance because one tree can chase sample-specific quirks.

For example, suppose the training data show that small biotech firms with high R&D and exactly 18%-22% revenue growth tend to outperform. A tree may create a branch for that pattern. But maybe that was just a few lucky observations. If the next sample does not repeat that pattern, the tree fails out-of-sample.

Random forest keeps the low-bias benefit of trees but reduces variance through averaging.

The mechanism is the same reason diversified portfolios reduce idiosyncratic risk:

```text
One stock:
  Company-specific risk matters a lot

Many imperfectly correlated stocks:
  Company-specific risk partly diversifies away

One tree:
  Tree-specific noise matters a lot

Many imperfectly correlated trees:
  Tree-specific noise partly diversifies away
```

The key phrase is **imperfectly correlated**. If every tree were identical, voting would not help. One mistake repeated 500 times is still one mistake. Random forests force the trees to differ by changing their samples and limiting which features they can consider.

## Step-by-Step Mechanics

Assume you have labeled training data:

| Company | Leverage | Profit Margin | Sales Growth | Target |
|---|---:|---:|---:|---|
| A | 75% | 3% | -4% | Default |
| B | 20% | 14% | 9% | No default |
| C | 55% | 8% | 2% | No default |
| D | 82% | -2% | -7% | Default |

The target is known in the training data, so this is [[supervised learning]].

The random forest process:

```text
Original labeled training data
        |
        v
Bootstrap sample 1     Bootstrap sample 2     Bootstrap sample 3
        |                      |                      |
        v                      v                      v
Decision tree 1          Decision tree 2          Decision tree 3
        |                      |                      |
        v                      v                      v
Prediction 1             Prediction 2             Prediction 3
        \                      |                      /
         \                     |                     /
          v                    v                    v
       Majority vote for classification
       Average prediction for regression
```

### Step 1: Bootstrap The Data

[[Bagging]] means bootstrap aggregating.

Bootstrap sampling means sampling **with replacement**. If the original training set has 1,000 observations, each tree may also train on 1,000 observations, but because sampling is with replacement, some original observations appear multiple times and some are left out.

Why with replacement?

Because the goal is to make each tree train on a different version of the data. If every tree saw the exact same data, the trees would be too similar. Different samples create different trees, and different trees create diversification.

### Step 2: Grow Many Decision Trees

Each bootstrap sample is used to grow a [[CART]] tree.

At each node, the tree chooses a feature and cutoff value that best separates the labeled data.

For example:

```text
Root node:
Is interest coverage < 2.0x?

If yes:
  Is leverage > 70%?

If no:
  Is sales growth < 0%?
```

A tree keeps splitting until it reaches stopping rules such as maximum depth, minimum observations per leaf, or another regularization rule.

### Step 3: Randomly Limit Features At Each Split

Random forests add another layer of randomness beyond bagging.

Suppose each company has 30 features. At a given node, the tree may only be allowed to consider 5 randomly selected features.

Why restrict the features?

Because otherwise one very strong feature can dominate every tree. If every tree starts with the same top feature, the trees become correlated. Correlated trees make correlated mistakes. Correlated mistakes do not cancel well.

Feature randomness de-correlates the trees.

```text
All features available to every tree:
  Trees look similar
  Mistakes are correlated
  Less diversification benefit

Random subset of features:
  Trees look different
  Mistakes are less correlated
  More diversification benefit
```

### Step 4: Aggregate Predictions

For classification:

```text
Tree 1: Default
Tree 2: No default
Tree 3: Default
Tree 4: Default
Tree 5: No default

Majority vote = Default
```

For regression:

```text
Tree 1 predicted return: 7%
Tree 2 predicted return: 3%
Tree 3 predicted return: 5%
Tree 4 predicted return: 9%
Tree 5 predicted return: 6%

Average = (7% + 3% + 5% + 9% + 6%) / 5
        = 30% / 5
        = 6%
```

## Classification vs Regression Forests

The phrase "random forest classifier" appears often because CFA emphasizes classification examples, but the idea can be used for regression too.

| Type | Target variable | Tree output | Forest output |
|---|---|---|---|
| Classification forest | Categorical target, such as default/no default or winner/average/loser | A class label | Majority vote, or class probabilities based on vote shares |
| Regression forest | Continuous target, such as expected return or sales growth | A numerical prediction | Average of tree predictions |

If 70 of 100 trees vote "winner," the forest can classify the fund as a winner and also imply a 70% vote share for that class. CFA may frame this as a probability-like interpretation, but be careful: it is not a structural probability model in the way a carefully specified statistical model might be. It is an empirical vote share from the trained forest.

## Worked Numerical Example: Majority Vote

Suppose a random forest has 11 trees predicting whether an IPO will be successful.

Each tree votes:

| Tree | Prediction |
|---:|---|
| 1 | Successful |
| 2 | Successful |
| 3 | Unsuccessful |
| 4 | Successful |
| 5 | Successful |
| 6 | Unsuccessful |
| 7 | Successful |
| 8 | Unsuccessful |
| 9 | Successful |
| 10 | Successful |
| 11 | Unsuccessful |

Count the votes:

```text
Successful votes = 7
Unsuccessful votes = 4
Total votes = 11
```

Majority vote:

$$
\frac{7}{11} = 0.6364 = 63.64\%
$$

The forest predicts **successful IPO**.

Why does this matter?

If one tree says "unsuccessful," you do not panic. The model is designed to tolerate disagreement. The disagreement is the point: each tree is a noisy expert, and the forest aggregates the noisy experts into a more stable answer.

## Worked Numerical Example: Regression Averaging

Suppose five trees predict a bond's next-year excess return:

| Tree | Predicted excess return |
|---:|---:|
| 1 | 2.0% |
| 2 | 3.5% |
| 3 | -1.0% |
| 4 | 4.0% |
| 5 | 1.5% |

Average prediction:

$$
\text{Forest prediction}
= \frac{2.0\% + 3.5\% - 1.0\% + 4.0\% + 1.5\%}{5}
$$

Add the numerator:

$$
2.0\% + 3.5\% = 5.5\%
$$

$$
5.5\% - 1.0\% = 4.5\%
$$

$$
4.5\% + 4.0\% = 8.5\%
$$

$$
8.5\% + 1.5\% = 10.0\%
$$

Divide by five:

$$
\frac{10.0\%}{5} = 2.0\%
$$

The random forest regression prediction is **2.0% excess return**.

## Why Random Feature Subsets Matter

This part is easy to memorize and easy to misunderstand.

Bagging alone makes trees different by giving them different observations. Random forests go further by giving trees different feature choices at each split.

Suppose "profitability" is the strongest predictor in the entire dataset. If every tree is allowed to use every feature, most trees may split on profitability first. Then they start to look alike.

That reduces the benefit of having many trees.

Random feature subsets force some trees to ask different questions:

```text
Tree A sees: profitability, leverage, size
Tree B sees: sales growth, liquidity, margin volatility
Tree C sees: valuation, sector, interest coverage
```

Some of those trees will be weaker individually. That sounds bad, but it can improve the forest.

Why?

Because the forest does not need every tree to be brilliant. It needs the trees to be:

```text
Better than random
+ Different from each other
= Useful ensemble
```

This is the same logic as portfolio diversification. You do not want every asset to be the same asset. You want assets that each contribute some signal while not moving perfectly together.

## Hyperparameters

Random forest has settings the analyst chooses or tunes. CFA may call these [[hyperparameters]].

| Hyperparameter | Meaning | If too low | If too high |
|---|---|---|---|
| Number of trees | How many trees are grown | Forest may be unstable | More computation; diminishing returns |
| Maximum tree depth | How many split levels each tree can have | Underfitting, too simple | More complex individual trees |
| Minimum observations per leaf/node | Minimum sample size needed in a terminal node or split | May allow noisy tiny leaves | May force overly broad groups |
| Number of features considered at each split | How many features are randomly available to a node | Trees may be too weak | Trees may become too similar |

The exam-level idea is not to optimize these by hand. The exam-level idea is to know what they control:

```text
Number of trees -> ensemble size
Tree depth -> individual tree complexity
Minimum node size -> regularization / overfitting control
Feature subset size -> diversity among trees
```

## Why Random Forests Are Good For Nonlinear Finance Problems

Finance data often has conditional relationships:

```text
High leverage is dangerous
  only if cash flow is weak
    and refinancing markets are tight
      and asset coverage is poor
```

That is not a simple straight-line relationship.

A linear model tries to estimate one average marginal effect:

```text
Default risk = b0 + b1(leverage) + b2(profitability) + b3(liquidity) + error
```

But a tree can say:

```text
If leverage > 70% and interest coverage < 2.0x:
  High default risk
Else if leverage > 70% and interest coverage >= 2.0x:
  Maybe not high default risk
```

That is a conditional interaction. Random forests are good at finding many such interactions without the analyst explicitly specifying them.

## Investment Applications

| Application | Why random forest fits |
|---|---|
| [[Credit risk]] and default prediction | Default often depends on nonlinear combinations of leverage, profitability, liquidity, and macro conditions |
| Fraud detection | Fraud is rare and noisy; ensemble methods can improve signal-to-noise when paired with careful sampling |
| [[Factor investing]] and asset allocation | Factor effects may interact nonlinearly across valuation, quality, momentum, size, and sector |
| Fund selection | Can classify funds into winner/average/loser groups using many fund features |
| IPO success prediction | IPO outcome may depend on issuer attributes, offer size, market conditions, underwriter quality, and valuation |
| Equity or fixed-income selection | Useful when prediction accuracy matters and rules are complex |

## Advantages

| Advantage | Why it matters |
|---|---|
| Handles nonlinear relationships | Trees naturally split feature space into regions |
| Captures interactions | A variable can matter only after another condition is met |
| More robust than a single tree | Many trees reduce sensitivity to one sample |
| Reduces variance | Averaging/voting cancels some tree-specific noise |
| Can rank feature importance | Random forests can estimate which variables provide more predictive information |
| Works for classification and regression | Can handle categorical or continuous targets |

## Disadvantages

| Disadvantage | Why it matters |
|---|---|
| Less interpretable than a single CART | One tree can be drawn; hundreds of trees are hard to explain |
| More computationally intensive | Training many trees takes more time than training one tree |
| Can still overfit if poorly tuned | No model is magic; bad data and bad design can still produce poor out-of-sample performance |
| Feature importance is not causality | A variable may help prediction without causing the outcome |
| May be inappropriate when explanation is legally or professionally required | If stakeholders need a clean decision rule, CART or logistic regression may be preferable |

## Random Forest vs CART

| Feature | [[CART]] | [[Random forest]] |
|---|---|---|
| Number of trees | One | Many |
| Prediction method | Follow one path to one terminal node | Aggregate many tree predictions |
| Interpretability | High | Lower |
| Variance | Higher | Lower |
| Overfitting risk | Higher if unconstrained | Lower because of bagging and averaging |
| Best use | Explaining decision rules | Improving predictive accuracy and robustness |

The clean exam sentence:

> CART is easier to interpret; random forest usually generalizes better.

## Random Forest vs Other CFA ML Algorithms

| Method | Core idea | Best for | Main contrast with random forest |
|---|---|---|---|
| [[LASSO]] | Linear regression with an absolute-value penalty that can set coefficients to zero | Feature selection in high-dimensional linear problems | LASSO is linear and interpretable; random forest captures nonlinear interactions |
| [[Support Vector Machines]] | Find a separating boundary with a maximum margin | Classification with a clear boundary | SVM focuses on a boundary; random forest aggregates many tree rules |
| [[k-Nearest Neighbors]] | Classify based on nearby observations | Local similarity classification | KNN needs a distance metric and can be distorted by irrelevant features; random forest learns splits |
| [[CART]] | One decision tree | Transparent nonlinear rules | Random forest is many trees and less transparent |
| [[Neural network]] | Layers of weighted transformations learn complex patterns | Very complex data, large datasets, images/text/speech | Neural networks can be more flexible but often more data-hungry and opaque |

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| Labeled data + nonlinear relationships + prediction goal | Consider CART, random forest, or neural network |
| Need high interpretability and visual rules | Prefer CART over random forest |
| Single tree is unstable or overfits | Random forest is a natural improvement |
| Many trees trained on bootstrap samples | Think bagging |
| Many trees + random feature subsets | Think random forest |
| Classification forest | Majority vote |
| Regression forest | Average predictions |
| Class imbalance | Accuracy may mislead; consider [[precision]], [[recall]], and [[F1 score]] |
| Need causal explanation | Be cautious; feature importance is not causality |

## Common Wrong Reasoning

### Wrong: "Random forest is unsupervised because it uses randomness."

Why it is wrong: Randomness in sampling and feature selection does not make the algorithm unsupervised. Random forest trains on labeled data. If the model learns from known outcomes, it is [[supervised learning]].

### Wrong: "Random forest is just one very deep decision tree."

Why it is wrong: A random forest is many trees. The forest improves prediction by aggregating across trees. One deep tree is exactly the object that can become unstable and overfit.

### Wrong: "Random forest reduces bias."

Better answer: Random forest primarily reduces [[variance]] by averaging many noisy trees. Individual trees can be low-bias/high-variance models. The forest keeps much of the flexibility while lowering variance.

### Wrong: "More trees always cause overfitting."

Better answer: Adding trees usually stabilizes a random forest, though benefits eventually diminish and computation increases. Overfitting is more directly controlled by tree depth, minimum node size, feature subset size, and validation performance.

### Wrong: "Random forest is more interpretable than CART."

Why it is wrong: CART is visually interpretable because one tree gives a clear if-then path. Random forest is less interpretable because the prediction comes from many trees.

### Wrong: "Feature importance proves causality."

Why it is wrong: Feature importance says a variable helped prediction in the model. It does not prove the variable caused the outcome. CFA loves this distinction because investment models often find predictive relationships that are not structural causal laws.

## Do Not Confuse With

| Concept | Do not confuse it with random forest because... |
|---|---|
| [[CART]] | CART is one tree; random forest is many trees |
| [[Bagging]] | Bagging is the bootstrap aggregation technique; random forest uses bagging plus random feature subsets |
| [[Ensemble learning]] | Ensemble learning is the broad category; random forest is one specific ensemble method |
| [[Boosting]] | Boosting trains models sequentially to focus on prior errors; random forests usually train trees in parallel on random samples |
| [[LASSO]] | LASSO selects variables by shrinking coefficients; random forest selects splits and can estimate feature importance |
| [[K-Means Clustering]] | K-means is unsupervised clustering; random forest is supervised prediction |

## Minimum Memorization

Memorize this:

> Random forest = many [[CART]] trees + [[bagging]] + random feature subsets + majority vote/averaging.

And this:

```text
Single CART:
  Interpretable but high variance

Random forest:
  Less interpretable but more robust out-of-sample
```

And this:

```text
Classification -> majority vote
Regression -> average prediction
```

## Can I Solve This?

You are ready for exam questions on random forests if you can answer these:

1. Why is random forest a [[supervised learning]] algorithm?
2. Why does bagging make trees different?
3. Why do random feature subsets make trees less correlated?
4. Why does averaging reduce variance?
5. Why is random forest less interpretable than CART?
6. When should you prefer CART over random forest?
7. When should you prefer random forest over CART?
8. Why does feature importance not prove causality?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[Ensemble learning]]
- [[Bagging]]
- [[CART]]
- [[Decision tree]]
- [[Bias-variance tradeoff]]
- [[Overfitting]]
- [[Out-of-sample]]
- [[Cross-validation]]
- [[F1 score]]
- [[Support Vector Machines]]
- [[k-Nearest Neighbors]]
- [[LASSO]]
- [[Neural network]]
