---
title: Support Vector Machines
subject: Quantitative Methods
tags: [CFA-L2, machine-learning, supervised-learning, classification, SVM]
aliases: [SVM, Support Vector Classifier, Maximum Margin Classifier]
---

# Support Vector Machines (SVM)

## The Hallway Bouncer — An Analogy First

Picture a long, narrow school hallway with two rival fan clubs walking through it — one wearing red, the other wearing blue. The principal needs to paint a single straight line down the floor of the hallway to keep them apart. A *lazy* principal would draw any line that happens to keep red on one side and blue on the other — even if that line skims right past someone's shoes. A *smart* principal would paint the line so that the **widest possible empty corridor** opens up between the two groups. That way, if a new student walks in tomorrow and stands a little off-center, there is no doubt which side they belong on.

That smart principal is what a Support Vector Machine does. It does not just find *a* boundary between two groups in your data — it finds the boundary with the **widest neutral zone** around it. The wider the neutral zone, the more confidently the model will classify a *new* observation that lands somewhere near the edge.

The students standing closest to the painted line — the ones whose toes the principal had to measure carefully to figure out where the line could go — are called the **support vectors**. Every other student in the hallway is irrelevant to where the line ends up. That is the algorithm's most distinctive trait: only a handful of borderline observations actually determine the model. Everything else is decoration.

---

## What Problem Does SVM Solve?

SVM is a [[Supervised Learning]] algorithm. "Supervised" means the training data is already labeled — for every observation we already know the correct answer (e.g., this bond *was* investment grade; this loan *did* default). The algorithm's job is to learn a rule that maps the **features** (X variables) to the **target** (Y label) so that it can classify *new*, unlabeled observations.

Within the supervised family, SVM is primarily a **classifier** — its target is categorical, typically binary (default / no default, IG / HY, fraud / clean, positive / negative sentiment). Variants exist for regression (Support Vector Regression) and for outlier detection, but on the CFA curriculum SVM lives squarely in the classification box.

> **Why a classifier and not regression?** The whole geometric setup — drawing a boundary to separate categories with the widest possible margin — only makes sense when the target is "which side?" not "how much?"

---

## The Geometric Heart: Hyperplane, Margin, and Support Vectors

Think of every observation as a dot plotted in feature space. With **two** features — say *Interest Coverage Ratio* on the x-axis and *Debt-to-Equity* on the y-axis — every bond is a point on a 2-D chart. With **three** features, every observation is a point in 3-D space. With **n** features, every observation is a point in n-dimensional space (which we cannot visualize but the math handles fine).

The boundary SVM draws between the two classes is called a **hyperplane**:

| Feature space dimension | The hyperplane is... |
|---|---|
| 2 features | a straight line |
| 3 features | a flat plane |
| n features (n ≥ 4) | a flat (n−1)-dimensional surface — generically called a *hyperplane* |

The hyperplane has the equation $\mathbf{w}^\top \mathbf{x} + b = 0$, where $\mathbf{w}$ is a vector perpendicular to the boundary and $b$ shifts it from the origin. To classify a new observation $\mathbf{x}_{\text{new}}$, we plug it in: if $\mathbf{w}^\top \mathbf{x}_{\text{new}} + b > 0$, predict class +1; if $< 0$, predict class −1.

The **margin** is the perpendicular distance from the hyperplane to the *nearest* training point on either side. SVM picks among all valid hyperplanes the one that **maximizes the margin** — hence the name *maximum margin classifier*.

```
        Class A (●)                       Class B (○)
            ●                                  ○
       ●          ●                       ○         ○
  ●         ●●  ←─── margin ───→  ○○         ○
        ●        |════════════════|       ○      ○
               (support vectors  on margin lines)
                    ↑
              Maximum-margin hyperplane
```

The two parallel dashed boundaries that just graze the closest points are the **margin boundaries**. The points that sit *on* those boundaries are the **support vectors** — the only observations that actually constrain where the hyperplane goes. Slide a non-support-vector point around and the hyperplane doesn't move. Slide a support vector and the whole model shifts.

> **Why this is powerful:** the model's complexity does not scale with the size of your dataset, only with the number of support vectors. Most of your data is, in a sense, ignored once training is done.

---

## Hard Margin vs. Soft Margin — and the Cost Parameter $C$

If the two classes are **linearly separable** — meaning some straight line (or hyperplane) cleanly puts every red point on one side and every blue point on the other — we can use a **hard margin** SVM that allows zero misclassifications. Pretty, but unrealistic. Real financial data is messy: a few investment-grade bonds will look like junk and vice versa. Insisting on perfect separation forces the margin to shrink to almost nothing, hurting out-of-sample performance.

The fix is the **soft margin** SVM, which lets some training points sit *inside* the margin or even on the wrong side of the hyperplane — at a *cost*. Each misclassified or margin-violating point contributes a slack penalty $\xi_i \geq 0$. The optimization becomes:

$$\min_{\mathbf{w}, b, \boldsymbol{\xi}} \quad \tfrac{1}{2}\|\mathbf{w}\|^2 + C\sum_{i=1}^{n} \xi_i$$

Two terms, in tension:
- $\tfrac{1}{2}\|\mathbf{w}\|^2$ — minimizing this **widens** the margin (a smaller $\mathbf{w}$ vector means a fatter neutral zone).
- $C\sum \xi_i$ — penalizes each violation. A bigger $C$ means each mistake hurts more.

The hyperparameter $C$ is the **cost** (or penalty) parameter and it controls the bias–variance trade-off:

| Cost parameter $C$ | Margin | Tolerance for errors | Risk |
|---|---|---|---|
| **Large $C$** | Narrow | Low — punishes every misclassification harshly | **Overfitting** — model contorts itself to fit training noise |
| **Small $C$** | Wide | High — tolerates more violations for a fatter neutral zone | **Underfitting** — model too simple, misses real structure |

You don't pick $C$ by intuition — you pick it by [[Cross-Validation]], training the model at many candidate values of $C$ and choosing the one with the lowest validation-set error.

---

## When Data Is Not Linearly Separable: The Kernel Trick

Sometimes no straight line will do — not even a soft one. Consider stocks where "good" performers cluster in the *middle* of a feature plot and "bad" ones surround them in a ring. No line separates a doughnut from its hole.

SVM's escape hatch is the **kernel trick**: lift the data into a higher-dimensional space where a flat hyperplane *can* separate them, without ever explicitly computing the high-dimensional coordinates. The trick is mathematical — a kernel function $K(\mathbf{x}_i, \mathbf{x}_j)$ silently computes the inner product of two points *as if* they had been projected into the higher space.

| Kernel | Form | Used when |
|---|---|---|
| **Linear** | $\mathbf{x}_i^\top \mathbf{x}_j$ | Data is roughly linearly separable; baseline |
| **Polynomial** | $(\mathbf{x}_i^\top \mathbf{x}_j + c)^d$ | Boundaries are curved, polynomial-shaped |
| **Radial Basis (RBF / Gaussian)** | $\exp(-\gamma\|\mathbf{x}_i - \mathbf{x}_j\|^2)$ | Most flexible — handles complex non-linear shapes |
| **Sigmoid** | $\tanh(\kappa \mathbf{x}_i^\top \mathbf{x}_j + c)$ | Neural-network-flavored boundaries |

The geometric intuition: imagine your doughnut-shaped 2-D data lifted into 3-D by adding a third coordinate $z = x^2 + y^2$. Now the inner ring sits at low $z$ and the outer ring at high $z$ — a flat horizontal plane in 3-D cleanly separates them. Project that plane back down to 2-D and it becomes a *circle*. The kernel trick does this transformation under the hood.

---

## Hyperparameters and How Analysts Tune Them

SVM has two main knobs:

1. **Cost / penalty $C$** — controls margin tightness vs. tolerance for violations.
2. **Kernel choice and its own parameters** — e.g., $\gamma$ in the RBF kernel (how "wiggly" the boundary is allowed to be), or the polynomial degree $d$.

Both are **hyperparameters** — they are not learned from the data automatically; the analyst sets them *before* training. The standard procedure:

1. Hold out a validation set (or use $k$-fold cross-validation).
2. Train SVM under a grid of candidate $(C, \gamma)$ combinations.
3. Pick the combination that minimizes the validation-set error.
4. Retrain on the full training set with that combination.
5. Report final performance on a *separate* test set.

---

## Strengths and Weaknesses — Where SVM Shines and Where It Doesn't

| Strengths | Weaknesses |
|---|---|
| Handles **high-dimensional** data well (many features, few observations) | Computationally expensive to train on **very large datasets** (poor scaling) |
| **Robust to outliers** in the bulk of the data — only support vectors matter | Choice of kernel and $C$ is critical and not obvious |
| Strong theoretical foundation; clear geometric interpretation | Often a "**black box**" — hard to explain *why* a particular boundary was chosen |
| Effective for **non-linear** problems via kernels | Native form is binary — multi-class problems require workarounds (one-vs-rest, one-vs-one) |
| Memory-efficient at prediction time (only stores support vectors) | Sensitive to feature scaling — features must usually be standardized first |

---

## SVM Compared to Other CFA-Curriculum ML Methods

| Method | What it does | How it differs from SVM |
|---|---|---|
| **[[k-Nearest Neighbors]] (kNN)** | Classifies a new point by majority vote of its $k$ closest neighbors | Local, lazy (no training); SVM is global and finds an explicit boundary |
| **[[Classification and Regression Trees]] (CART)** | Recursively splits feature space along single-feature thresholds | Tree boundaries are axis-aligned; SVM boundaries can slant in any direction |
| **[[Neural Networks]]** | Learns a hierarchy of features through layers of non-linear transforms | More flexible but more data-hungry; SVM does well with small, clean data |
| **[[Random Forests]]** | Ensemble of trees, votes for class | Less prone to overfitting than SVM with poor hyperparameters; less geometric |

A handy mental rule: **kNN asks "who are my neighbors?", CART asks "which feature splits cleanest?", SVM asks "where is the widest gap between the groups?"**

---

## Financial Applications

- **Default and bankruptcy prediction.** Classify firms as "likely to default" vs. "safe" using accounting ratios (interest coverage, debt-to-equity, current ratio, profit margin) as features.
- **Credit ratings.** Predict whether a new bond issue will land in **Investment Grade** or **High Yield**.
- **Sentiment classification on news / earnings calls.** Use [[Natural Language Processing]] features (word frequencies, embeddings) to classify text as bullish or bearish.
- **Fraud detection.** Separate suspicious transactions from clean ones in high-dimensional transaction data.
- **Style classification.** Tag funds by investment style (growth vs. value, large vs. small cap) from their holdings.

---

## Worked Conceptual Example — Investment Grade vs. High Yield Bonds

An analyst has a labeled training set of 200 bonds, each tagged either **IG** or **HY**, with two features: *Interest Coverage Ratio* (ICR) on the x-axis and *Debt-to-Equity* (D/E) on the y-axis.

**Step 1 — Plot.** IG bonds cluster in the upper-left (high ICR, low D/E). HY bonds cluster in the lower-right (low ICR, high D/E). There is some overlap in the middle — a few weak IGs and a few strong HYs blur the line.

**Step 2 — SVM training.** The algorithm searches for the straight line that best separates the two clusters with the widest margin, allowing some violations (soft margin) at cost $C$.

**Step 3 — Identify support vectors.** Suppose 12 bonds end up on the margin boundaries — 7 borderline IGs sitting just above the line and 5 borderline HYs sitting just below. Those 12 are the support vectors. The other 188 bonds are far enough from the line that they don't constrain it.

**Step 4 — The decision rule.** The fitted hyperplane might be, conceptually, $\text{ICR} - 0.4 \cdot (\text{D/E}) - 1.5 = 0$. For any new bond, plug in its ICR and D/E:
- Result $> 0$ ⇒ predict **IG**.
- Result $< 0$ ⇒ predict **HY**.

**Step 5 — Tune $C$ via cross-validation.** Try $C \in \{0.1, 1, 10, 100\}$. Suppose $C = 1$ gives the lowest 5-fold validation error of 8.2%. Use that.

**Step 6 — Out-of-sample check.** On a held-out test set of 50 bonds, the model classifies 46 correctly — 92% accuracy. The analyst now uses it on newly issued unrated bonds.

If the analyst had chosen $C = 100$ instead, training accuracy would have looked higher but test accuracy would have dropped — the classic overfitting signature.

---

## Exam Pitfalls

1. **Don't confuse SVM with kNN.** Both are supervised classifiers, but kNN is *local* (uses neighboring points at prediction time) and *lazy* (no training phase). SVM is *global* (single learned boundary) and *eager* (training is where the work happens).
2. **Remember the role of support vectors.** The model is determined by a handful of boundary points, not by the bulk of the data. Removing far-away points doesn't change the boundary.
3. **Cost parameter direction.** Large $C$ ⇒ narrow margin ⇒ overfitting risk. Small $C$ ⇒ wide margin ⇒ underfitting risk. Many students remember it backwards.
4. **Soft margin is the default.** Real financial data is rarely perfectly separable. Hard margin is a textbook idealization.
5. **Standardize features first.** SVM is distance-based, so features on different scales (e.g., D/E in tenths vs. revenue in billions) will distort the geometry.
6. **Binary by default.** SVM solves a 2-class problem natively. Multi-class requires one-vs-rest or one-vs-one wrappers.
7. **It's a black box.** Unlike CART, you can't trace a clean if-then chain explaining a prediction. Be prepared to identify this as a weakness on a vignette.

---

## LOS-Level Recap

| LOS Verb | Mastery Statement |
|---|---|
| **Describe** SVM as a supervised algorithm | A binary classifier that finds the maximum-margin hyperplane separating two classes in feature space; only the support vectors (closest training points) determine the boundary. |
| **Explain** the role of the soft margin and cost parameter | Soft margin allows controlled misclassifications via slack penalties; the cost parameter $C$ trades off margin width against training-error tolerance, tuned via cross-validation. |
| **Explain** how SVM handles non-linearity | Through the kernel trick — implicitly mapping data to a higher-dimensional space (linear, polynomial, RBF, sigmoid kernels) where a linear hyperplane can separate the classes. |
| **Distinguish** SVM from other ML methods | From kNN (local vs. global), from CART (slanting vs. axis-aligned splits, opaque vs. interpretable), from neural networks (small-data friendly vs. data-hungry). |
| **Determine** when SVM is appropriate | High-dimensional, modest-sample, binary classification problems with clean structure — e.g., default prediction, sentiment tagging, credit rating classification. |

---

## One-Sentence Summary

A Support Vector Machine draws the widest possible neutral corridor between two classes in feature space, leans entirely on the handful of borderline observations (the support vectors) that sit on the corridor's edges, and uses the kernel trick to bend the corridor into curves when a straight line won't do.
