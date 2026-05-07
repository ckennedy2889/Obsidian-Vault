---
title: LASSO
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, supervised-learning, penalized-regression, regularization, LASSO]
aliases: [Least Absolute Shrinkage and Selection Operator, L1 Regularization, Penalized Regression, LASSO Regression]
---

# LASSO

## One-Minute Version

[[LASSO]] stands for **Least Absolute Shrinkage and Selection Operator**. It is a [[penalized regression]] method used in [[Supervised Learning]] to reduce [[Overfitting]] when a model has many possible features.

Ordinary least squares tries only to minimize prediction errors:

$$\min \sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2$$

LASSO adds a penalty for using large or unnecessary coefficients:

$$\min \left[\sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2 + \lambda \sum_{j=1}^{k} |\hat{b}_j|\right]$$

The first term rewards fit. The second term punishes complexity. If a feature does not improve prediction enough to justify its penalty, LASSO can shrink its coefficient all the way to **zero**, effectively removing it from the model.

> [!tip] One-Line Rule
> LASSO makes variables pay rent: if a feature does not improve out-of-sample prediction enough, its coefficient gets pushed to zero and it leaves the model.

---

## LOS Coverage

| CFA task | What you must be able to do |
|---|---|
| Describe supervised machine learning algorithms | Classify LASSO as a supervised [[penalized regression]] method |
| Determine problems for which algorithms are best suited | Use LASSO when there are many features and risk of overfitting |
| Explain overfitting and regularization | Explain how $\lambda$ controls the tradeoff between fit and parsimony |
| Evaluate model fit | Recognize that good LASSO tuning should reduce the gap between training and cross-validation performance |

---

## Real-World Analogy: A Portfolio Manager With Too Many Analysts

Imagine a portfolio manager has 500 junior analysts, and each analyst proposes one factor that might predict stock returns:

```text
P/E ratio
momentum
earnings surprise
CEO sentiment
weather patterns
Twitter mood
the CFO's shoe color
...
```

If the manager listens to everyone, the model may fit the past beautifully. But many "signals" are just noise. The model starts memorizing historical quirks instead of learning durable relationships.

LASSO acts like a strict budget committee. Every factor must justify its seat. If a factor improves prediction enough, it stays. If not, LASSO sets its coefficient to zero and kicks it out.

That is why the name contains both words:

```text
Shrinkage  = pull coefficients toward zero
Selection  = set some coefficients exactly to zero
```

---

## The Deep Why: Why Penalize Regression At All?

OLS is hungry. If you give it more variables, it will almost always use them to reduce in-sample error.

Why? Because OLS minimizes:

$$SSE = \sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2$$

Adding another variable gives the model another lever to bend the fitted line or surface closer to the training data. The training error can fall even if the new variable is meaningless.

That creates the core [[Machine Learning]] problem:

```text
More features
  |
  v
Lower training error
  |
  v
Higher model complexity
  |
  v
Risk of memorizing noise
  |
  v
Poor out-of-sample prediction
```

This is [[Overfitting]]. The model looks brilliant on the training set but weak on cross-validation or test data.

LASSO changes the optimization problem. It says:

```text
You may reduce SSE,
but every coefficient you use creates a penalty.
```

So a variable is included only if the reduction in SSE is worth more than the penalty it adds.

That is the mechanism underneath the CFA phrase "build a parsimonious model." Parsimony does not mean "small for aesthetic reasons." It means "small enough to generalize."

---

## The LASSO Objective Function

The LASSO objective is:

$$\min_{\hat{b}} \left[\sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2 + \lambda \sum_{j=1}^{k} |\hat{b}_j|\right]$$

Break it apart:

| Piece | Meaning | Why It Matters |
|---|---|---|
| $\sum(Y_i-\hat{Y}_i)^2$ | Training error / lack of fit | Lower is better |
| $\sum|\hat{b}_j|$ | Total absolute coefficient size | Measures model complexity |
| $\lambda$ | Regularization strength | Controls how harsh the penalty is |

The intercept is typically not the conceptual focus of the penalty. CFA cares about the slope coefficients on features.

### Why Absolute Values?

LASSO uses the absolute value penalty:

$$\sum |\hat{b}_j|$$

This is called an $L_1$ penalty.

The absolute value matters because it punishes coefficient size regardless of sign:

```text
+3 and -3 are both "large" coefficients.
```

The model does not care whether a variable pushes the prediction up or down. It cares whether that variable is earning its complexity cost.

---

## What Lambda Does

$\lambda$ is the regularization hyperparameter. It is not learned like a regression coefficient. The researcher sets or tunes it, usually with [[Cross-validation]] or grid search.

| $\lambda$ | Model Behavior | Main Risk |
|---|---|---|
| $\lambda = 0$ | LASSO becomes ordinary OLS | Overfitting if many features |
| Small $\lambda$ | Slight shrinkage; many features remain | Still too complex |
| Moderate $\lambda$ | Weak features shrink to zero; stronger features remain | Often the sweet spot |
| Very large $\lambda$ | Most coefficients forced to zero | Underfitting / high bias |

Why does this happen?

The objective function has two competing forces:

```text
Fit force:       reduce SSE
Penalty force:   reduce coefficient size
```

When $\lambda$ is small, the penalty force is weak, so the model mostly chases fit. When $\lambda$ is large, the penalty force is strong, so the model sacrifices fit to stay simple.

The CFA connection is the [[Bias-Variance Trade-Off]]:

```text
Too little regularization -> low bias, high variance -> overfitting
Too much regularization   -> high bias, low variance -> underfitting
Optimal regularization    -> balanced bias and variance
```

---

## Why LASSO Can Set Coefficients Exactly To Zero

This is LASSO's signature feature.

[[Ridge regression]] uses an $L_2$ penalty:

$$\lambda \sum b_j^2$$

LASSO uses an $L_1$ penalty:

$$\lambda \sum |b_j|$$

Both shrink coefficients. But LASSO can shrink coefficients all the way to exactly zero.

The intuitive reason: the $L_1$ penalty creates a sharp "corner" at zero. The optimization often lands on that corner. When it does, the coefficient becomes exactly zero.

In plain English:

```text
Ridge says: "Everyone gets smaller."
LASSO says: "Some of you are fired."
```

That is why LASSO performs **automatic feature selection**. A zero coefficient means the feature is excluded from the model.

---

## Worked Numerical Example: Why A Variable Must Earn Its Seat

Suppose a simple model has two candidate features:

```text
X1 = momentum
X2 = CFO shoe color
```

Without the penalty, adding $X_2$ reduces training SSE slightly:

| Model | SSE |
|---|---:|
| Momentum only | 100.0 |
| Momentum + shoe color | 98.5 |

OLS likes the second model because SSE fell by 1.5.

Now suppose LASSO adds a penalty:

$$\lambda \sum|\hat{b}_j|$$

Assume:

- $\lambda = 2$
- Momentum coefficient $|\hat{b}_1| = 4$
- Shoe color coefficient $|\hat{b}_2| = 1$

Penalty for momentum-only model:

$$2(4)=8$$

Total objective:

$$100 + 8 = 108$$

Penalty for two-feature model:

$$2(4+1)=10$$

Total objective:

$$98.5 + 10 = 108.5$$

Even though SSE improved, the total penalized objective got worse:

$$108.5 > 108.0$$

So LASSO rejects the extra feature. The shoe-color variable did not reduce error enough to pay for its complexity.

That is the operational heart of LASSO:

```text
A variable survives only if its predictive benefit exceeds its penalty cost.
```

---

## Finance Example: Text Sentiment Model

The CFA curriculum uses text-based machine learning as a natural LASSO setting.

Suppose you are classifying financial news sentences as positive or negative. After preprocessing, the text becomes a huge [[Document term matrix]] with thousands of token features:

```text
earnings
growth
downgrade
lawsuit
the
and
is
...
```

Most words do not help. Some are noise. Some appear rarely. A standard logistic regression using all tokens can overfit badly: it may show extremely strong training performance but weaker cross-validation performance.

LASSO regularization penalizes the logistic regression coefficients. Useful words keep nonzero coefficients. Useless words get pushed to zero and ignored.

The source intuition:

```text
Before LASSO: model memorizes noisy text features
After LASSO: model keeps predictive tokens and generalizes better
```

That is why LASSO fits naturally with high-dimensional financial text data.

---

## LASSO vs. Ridge vs. Elastic Net

| Method | Penalty | What It Does | Best When |
|---|---|---|---|
| [[LASSO]] | $\lambda\sum|b_j|$ | Shrinks some coefficients to exactly zero | You want variable selection |
| [[Ridge regression]] | $\lambda\sum b_j^2$ | Shrinks all coefficients but usually keeps them nonzero | Many variables may matter a little |
| [[Elastic net]] | Mix of $L_1$ and $L_2$ penalties | Combines selection and shrinkage | Many correlated features |

The exam-level distinction:

```text
LASSO = shrinkage + selection
Ridge = shrinkage only
Elastic net = compromise
```

If the question says "automatically eliminates less predictive features," think LASSO.

---

## When You See This, Do This

| If the question says... | Think... | Do this... |
|---|---|---|
| Many predictors / high-dimensional data | Overfitting risk | Consider penalized regression |
| Need automatic feature selection | LASSO | Use $L_1$ penalty |
| Coefficients can become exactly zero | LASSO | Distinguish from ridge |
| Training performance much better than CV performance | Overfitting / high variance | Increase regularization or simplify |
| Training and CV performance both poor | Underfitting / high bias | Decrease regularization or add features |
| $\lambda = 0$ | No penalty | Equivalent to OLS in linear regression |
| $\lambda$ very large | Heavy penalty | Model may underfit |

---

## Common Wrong Reasoning

### Wrong 1: "LASSO improves in-sample fit."

Why it feels right: LASSO is a machine learning method, so it sounds like it should make the model fit better.

Why it fails: LASSO deliberately sacrifices some in-sample fit to improve out-of-sample generalization. It adds a penalty, so the training SSE may be higher than OLS.

Correct exam rule:

```text
LASSO is about generalization, not maximizing training fit.
```

### Wrong 2: "Lambda is estimated from the regression like beta."

Why it feels right: $\lambda$ appears in the objective function next to coefficients.

Why it fails: $\lambda$ is a [[Hyperparameter]]. The analyst tunes it, often through cross-validation. The model estimates coefficients conditional on that chosen $\lambda$.

Correct exam rule:

```text
Coefficients are parameters; lambda is a hyperparameter.
```

### Wrong 3: "LASSO and ridge do the same thing."

Why it feels right: both are penalized regressions and both shrink coefficients.

Why it fails: ridge shrinks coefficients toward zero, but LASSO can set coefficients exactly to zero.

Correct exam rule:

```text
Ridge shrinks; LASSO selects.
```

### Wrong 4: "More regularization is always better."

Why it feels right: if overfitting is bad, a stronger anti-overfitting penalty sounds good.

Why it fails: too much regularization creates [[Underfitting]]. The model becomes too simple to capture real signal.

Correct exam rule:

```text
Optimal regularization balances bias and variance.
```

---

## Do Not Confuse With

| Concept | Difference |
|---|---|
| [[Ordinary Least Squares]] | Minimizes SSE only; no complexity penalty |
| [[Ridge regression]] | Uses squared-coefficient penalty; shrinks but usually does not select |
| [[Elastic net]] | Combines LASSO and ridge penalties |
| [[Principal components analysis]] | Unsupervised dimensionality reduction; transforms variables into components |
| [[Adjusted R-Squared]] / [[AIC and BIC]] | Model selection criteria; not the same as penalized estimation |
| [[Feature selection]] | General task; LASSO is one method that performs it automatically |

---

## Minimum Memorization

1. Full name:

```text
Least Absolute Shrinkage and Selection Operator
```

2. Objective:

$$\min \left[\sum_{i=1}^{n}(Y_i-\hat{Y}_i)^2 + \lambda\sum_{j=1}^{k}|\hat{b}_j|\right]$$

3. Penalty type:

```text
LASSO = L1 penalty = sum of absolute coefficients
```

4. Key effect:

```text
Can set coefficients exactly to zero -> automatic feature selection
```

5. Lambda:

```text
Higher lambda -> more shrinkage -> simpler model
Too high -> underfitting
Too low -> overfitting
```

6. Main CFA use:

```text
High-dimensional supervised learning, parsimonious models, overfitting control
```

---

## Can I Solve This?

- [ ] I can write the LASSO objective function.
- [ ] I can explain why LASSO adds a penalty to SSE.
- [ ] I can explain what $\lambda$ does.
- [ ] I can distinguish a parameter from a hyperparameter.
- [ ] I can explain why LASSO can set coefficients to zero.
- [ ] I can compare LASSO with ridge regression.
- [ ] I can identify LASSO as useful for high-dimensional data and feature selection.
- [ ] I can connect LASSO to overfitting, cross-validation, and the bias-variance trade-off.

---

## Related Concepts

- [[Machine Learning]]
- [[Supervised Learning]]
- [[Penalized regression]]
- [[Regularization]]
- [[Ridge regression]]
- [[Elastic net]]
- [[Overfitting]]
- [[Underfitting]]
- [[Bias-Variance Trade-Off]]
- [[Cross-validation]]
- [[Feature selection]]
- [[Logistic Regression]]
- [[Document term matrix]]
