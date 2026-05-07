---
title: "CFA L2 - Extensions of Multiple Regression"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, regression, dummy-variables, logistic-regression, influence-analysis, outliers]
aliases: ["Module 1.4", "Dummy Variables", "Logistic Regression", "Influence Analysis"]
---

# Module 1.4 — Extensions of Multiple Regression

## Beyond the Basic Model

The standard [[Multiple Regression]] framework handles quantitative predictors predicting a quantitative outcome. But real financial data is messier than that:

- Some observations are extreme outliers that can *warp* the entire regression line
- Some predictors are *categories* ("[[Technology|Technology]]" or "Emerging Market"), not numbers
- Sometimes what you're predicting isn't a number — it's a *yes/no* decision

This module extends the toolkit to handle all three situations:
1. **Influence analysis** — identifying and handling data points that distort the model
2. **Dummy variables** — encoding categorical predictors
3. **Logistic regression** — predicting binary outcomes

---

## Part 1 — Influence Analysis: Finding the Troublemakers

### The Problem

Every regression line is pulled by every data point. Most pull gently and in a direction [[Consistent|consistent]] with the overall pattern. But occasionally, one data point has an extreme value that **bends the whole line toward itself**, forcing the model to fit that outlier at the expense of all the normal observations.

This is like letting one very loud person dominate a group meeting — their strong opinion pulls the "consensus" far from what most people actually think.

Influence analysis is the background check you run on your data to find those loud voices before they corrupt your model.

```
Without Influential Point:          With Influential Point:
   Y                                    Y
   │          ●                         │               ●
   │      ●  /                          │              /
   │    ●  /                            │            /
   │  ●  /                              │          /
   │●  /                                │   ● ● ●/
   └──────────── X                      └──────────── X
   Regression fits the crowd           Line tilts toward the outlier
```

### High-Leverage Points vs. Outliers

These are two different flavors of "problematic" observations:

**High-Leverage Point** — extreme value on an **independent variable (X)**

This is a data point that sits far from the center of the X distribution. Because it's at the edge, it has a lot of "pull" on the regression line's slope — like a long lever arm. The leverage score $h_{ii}$ measures this.

A common rule: flag any observation where:
$$h_{ii} > \frac{3(k+1)}{n}$$

Where $k$ = number of predictors, $n$ = number of observations.

**Outlier** — extreme value on the **dependent variable (Y)**

This is a data point where the model's prediction was wildly wrong — the residual is huge. Outliers are detected using **studentized residuals**:

$$e_i^* = \frac{\hat{\epsilon}_i}{s\sqrt{1-h_{ii}}}$$

Flag any observation where $|e_i^*| > 3$.

### Cook's D — Combined Influence

An observation is truly *influential* only if it's both a leverage point AND an outlier. **Cook's D** (Cook's Distance) combines both dimensions into a single score:

$$D_i = \frac{e_i^{*2}}{k+1} \cdot \frac{h_{ii}}{1-h_{ii}}$$

Higher Cook's D = more influence. Common rule: $D_i > 1$ is a serious concern.

```
                     Outlier?
                  No          Yes
              ┌─────────┬───────────────┐
High          │Low       │ INFLUENTIAL   │
Leverage?  Yes│influence │ (Cook's D     │
              │          │ will be high) │
              ├─────────┼───────────────┤
           No │No issue  │ Outlier only  │
              │          │ (less concern)│
              └─────────┴───────────────┘
```

### When to Delete an Observation

This requires judgment — you should never just delete data because it "looks weird":

| Situation | Action |
|-----------|--------|
| Clear data error (typo, impossible value like negative revenue) | Fix or delete |
| Genuine extreme event (acquisition, merger, natural disaster) | Consider deleting with justification — or keep but note its effect |
| Correct data from normal operations | Keep — the model may need a structural change instead |

**Real-world example:** An analyst modeling 100 tech stock returns finds one company that returned +500% due to a takeover bid. That company is a high-leverage outlier — the takeover is a one-time event unrelated to normal sector dynamics. Keeping it distorts the model for all the other stocks.

---

## Part 2 — Dummy Variables: Teaching Regression to Speak Categories

### The Problem

A computer running [[OLS]] regression only understands numbers. But financial analysis is full of categories:
- Industry: Technology, Energy, Healthcare, Retail
- Country: US, Emerging Markets, Developed ex-US
- Status: Recession, Expansion, Crisis

How do you feed the word "Technology" into a regression equation?

**Dummy variables** (also called indicator variables) solve this by encoding categories as 0s and 1s:

$$D_i = \begin{cases} 1 & \text{if observation } i \text{ is in the target category} \\ 0 & \text{otherwise} \end{cases}$$

### Encoding: The n−1 Rule

Here's the critical rule: if your category has **$n$ groups**, you only create **$n-1$ dummy variables**.

**Example — Three industries: Technology, Energy, Retail**

| Company | Tech Dummy ($D_1$) | Energy Dummy ($D_2$) | Implied |
|---------|-------------------|---------------------|---------|
| Apple | 1 | 0 | Tech |
| ExxonMobil | 0 | 1 | Energy |
| Walmart | 0 | 0 | **Retail (base group)** |

The "missing" category (Retail) is captured by the intercept. You don't need a third dummy.

### The Dummy Variable Trap

If you create dummies for **all $n$ categories**, something breaks: the three dummies would sum to 1 for every observation, making them perfectly collinear with the intercept. This is **perfect [[CFA_Glossary/Multicollinearity]]** — the regression matrix becomes singular and the software crashes (or gives nonsensical output).

> [!danger] The Trap
> Never create dummies for all categories. Always leave one out as the **base group** (also called the reference category). The omitted category's effect is absorbed by the intercept.

### Interpreting Dummy Coefficients

A dummy coefficient tells you the **average difference in Y** between the dummy group and the base group, holding all other variables constant.

**Intercept dummy:** Shifts the entire regression line up or down for that category.

If $\hat{b}_1 = +2.50$ for an Emerging Markets dummy (with Developed Markets as base):
- EM stocks earned **2.50% more** than DM stocks on average, after controlling for other factors

**Slope dummy (interaction term):** Changes how steeply the regression line slopes for that category.

$$Y = b_0 + b_1X + b_2D + b_3(X \times D) + \epsilon$$

If $\hat{b}_3 \neq 0$, it means the relationship between X and Y is *different* for the two groups. For example, GDP growth might affect Emerging Market returns more steeply than Developed Market returns.

```
Without slope dummy:        With slope dummy:
   Y                           Y
   │    /  (one line)           │        /  EM (steeper slope)
   │   /                        │       /
   │  /                         │      /  DM (flatter slope)
   │ /                          │     /
   └──────────── X              └──────────── X
```

**Real-world example:** A [[Hedge fund|hedge fund]] manager uses a dummy $D=1$ for Emerging Markets, $D=0$ for Developed Markets. The dummy coefficient of +2.50 means that, after controlling for all other factors, EM stocks returned 2.50% more than DM stocks in the sample.

---

## Part 3 — Logistic Regression: Predicting Yes/No Outcomes

### Why Not Just Use Linear Regression?

Sometimes you don't want to predict a *number* — you want to predict a *category*:
- Will this company **default** on its debt? (Yes / No)
- Is this stock **overvalued**? (Yes / No)
- Will this earnings release **beat** analyst estimates? (Yes / No)

If you try to use ordinary [[Linear regression]] to predict a 0/1 binary outcome (called a "linear probability model"), it immediately runs into problems:

- The model might predict a probability of **120%** or **−15%** — mathematically impossible
- The OLS assumption of constant variance is automatically violated (the residuals are non-normal)
- The relationship between X and probability isn't actually linear — a slight change in a healthy company's leverage barely affects its default risk, but the same change in a nearly-bankrupt company matters enormously

### The Logistic Function: The S-Curve Solution

**[[Logistic regression]]** solves this with the **logistic function (sigmoid curve)**:

$$P(Y=1) = \frac{1}{1 + e^{-z}}$$

Where $z = b_0 + b_1X_1 + b_2X_2 + \cdots$ (the linear combination of inputs).

The sigmoid curve is S-shaped:

```
Probability
    1 │                    ·────────────
      │               ·
    0.5│           ·
      │        ·
      │   ·
    0 │────────·
      └─────────────────────────────→ z (linear predictor)

Key properties:
  • Output is always between 0 and 1 (valid probability)
  • Flat at extremes (large changes in X don't push P past 0 or 1)
  • Steep in the middle (small changes in X matter most near P = 0.5)
```

### Log-Odds and Coefficient Interpretation

The model doesn't directly predict probability — it predicts the **log-odds**:

$$\ln\left(\frac{P}{1-P}\right) = b_0 + b_1X_1 + b_2X_2 + \cdots$$

**The odds** = probability of success / probability of failure. If $P = 0.75$, odds = 0.75/0.25 = 3 (3-to-1 in favor).

**The log-odds** (logit) = natural log of the odds.

A slope coefficient $b_j$ represents the change in **log-odds** for a one-unit increase in $X_j$, holding other variables constant. To get back to probability:

$$P = \frac{1}{1 + e^{-z}} = \frac{e^z}{1 + e^z}$$

### The Confusion Matrix: Evaluating Binary Predictions

Because we're making yes/no predictions, the standard performance metrics (R², F-stat) don't apply. Instead, we use a **confusion matrix**:

```
                      ACTUAL
                  Positive    Negative
           ┌─────────────┬───────────────┐
Predicted  │True Positive│False Positive │
Positive   │    (TP)     │    (FP)       │  ← Type I Error
           ├─────────────┼───────────────┤
Predicted  │False Neg.   │True Negative  │
Negative   │    (FN)     │    (TN)       │  ← Type II Error
           └─────────────┴───────────────┘
```

From this matrix, four performance metrics:

$$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$$

$$\text{Precision} = \frac{TP}{TP + FP} \quad \text{(of all predicted positives, how many were right?)}$$

$$\text{Recall (Sensitivity)} = \frac{TP}{TP + FN} \quad \text{(of all actual positives, how many did we catch?)}$$

$$\text{F1 Score} = \frac{2 \times \text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} \quad \text{(balanced score)}$$

### The Precision-Recall Tradeoff

There's a fundamental tension between precision and recall:

- **Maximize Precision** (minimize false positives): Only flag something as fraud if you're certain — you'll miss some thieves but won't annoy innocent customers
- **Maximize Recall** (minimize false negatives): Flag anything suspicious — you'll catch almost every thief but generate many false alarms

The right balance depends on the cost of each error type. In credit risk, missing a default (false negative) is very costly — prioritize recall. In marketing, sending a message to a non-buyer (false positive) is just a nuisance — precision matters less.

### ROC Curve and AUC

The **ROC (Receiver Operating Characteristic) curve** visualizes the precision-recall tradeoff across all possible classification thresholds:

```
True Positive
  Rate (Recall)
    1│          ·─────────────────
    │       ·
    │     ·
  0.5│   ·           AUC = 0.85 (good model)
    │  ·
    │·
    └──────────────────────────────→ False Positive Rate

For reference:
  AUC = 1.0: Perfect model
  AUC = 0.8-0.9: Excellent
  AUC = 0.7-0.8: Good
  AUC = 0.5: No better than a coin flip (diagonal line)
```

**AUC (Area Under the Curve)** summarizes the ROC curve as a single number — the higher the AUC, the better the model is at distinguishing the two classes across all thresholds.

**Real-world example:** A bank uses logistic regression to classify credit card transactions as Fraud (1) or Legitimate (0). Features include transaction amount, location, and time of day. The model produces predicted probabilities for each transaction.

- Prioritizing **precision**: Only block cards above 90% fraud [[Probability|probability]] — customer satisfaction high, some fraud slips through
- Prioritizing **recall**: Block anything above 30% [[Probability|probability]] — catches most fraudsters, but many innocent customers have their cards declined
- The **AUC** tells the bank how good the overall model is at separating fraudsters from shoppers before it tunes the threshold

---

## Exam Traps

> [!danger] Common Mistakes
> - **[[Dummy variable|Dummy variable]] trap**: Including all $n$ dummies causes perfect [[Multicollinearity|multicollinearity]] — always use $n-1$
> - **Interpreting dummy coefficients**: They are differences *relative to the base group*, not absolute levels
> - **Logistic regression uses log-odds**, not [[Probability|probability]], as the left-hand side — coefficients need transformation to get predicted probabilities
> - **Accuracy vs. F1**: When classes are imbalanced (e.g., 99% negative, 1% positive), accuracy is misleading — always check precision/recall/F1
> - **AUC = 0.5 is useless** — that's random guessing
> - **Influence ≠ outlier**: A high-leverage point might not be an outlier; a Cook's D combines both

---

## Related Concepts

- [[Multiple Regression - Basics and Assumptions]] — the foundational model extended here
- [[Model Misspecification]] — violations that affect the standard model
- [[CFA_Glossary/Multicollinearity]] — the problem the [[Dummy variable|dummy variable]] trap creates
- [[Logistic Regression]] — binary outcome modeling
- [[Confusion Matrix]] — classification performance metrics
- [[Machine Learning]] — logistic regression as a supervised learning algorithm
- [[Cook's D]] — influence measure
