---
title: Influence Analysis
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, regression, diagnostics, influence-analysis]
aliases: [Influential observations, High-leverage points, Outliers in regression, Influence diagnostics]
---

# Influence Analysis

## The Real-World Analogy

Most observations in a regression are like normal votes in an election: each one matters, but no single observation controls the result. An influential observation is different. It is like a voter with a megaphone. Its $X$ values may be far from the crowd, its $Y$ value may be surprising, or both. Because OLS fits the line by minimizing squared errors, one unusual point can tilt the entire regression and change the coefficients.

[[Influence analysis]] is the process of finding those observations and deciding whether they are data errors, valid but unusual facts, or signs that the model is missing something.

## The Big Idea

There are three related but different ideas:

| Concept | Extreme in | Main diagnostic | What it tells you |
|---|---|---|---|
| High-leverage point | Independent variables, $X$ | Leverage $h_{ii}$ | The point has unusual predictor values |
| Outlier | Dependent variable, $Y$ | [[Studentized Residuals]] | The model badly misses the point's $Y$ value |
| Influential observation | Combined effect | Change in coefficients, Cook's distance | Removing the point materially changes the regression |

Not every outlier is influential. Not every high-leverage point is influential. The most dangerous case is a point that is both far out in $X$-space and poorly fit in $Y$-space.

## High-Leverage Points

A high-leverage point has unusual independent-variable values. It sits far from the center of the $X$ distribution and therefore has potential pull over the slope.

Leverage ranges from 0 to 1:

$$
0 \le h_{ii} \le 1
$$

The average leverage is:

$$
\bar{h} = \frac{k+1}{n}
$$

where $k$ is the number of independent variables and $n$ is sample size.

CFA's common high-leverage threshold is:

$$
h_{ii} > \frac{3(k+1)}{n}
$$

Leverage is about $X$, not $Y$. A high-leverage point that lies exactly on the true relationship may improve the model. A high-leverage point with a strange $Y$ value can distort the model.

## Outliers

An outlier has an unusual $Y$ value relative to what the regression predicts.

CFA emphasizes [[Studentized Residuals|studentized deleted residuals]]:

1. Estimate the model after deleting the observation.
2. Predict the deleted observation's $Y$.
3. Compare actual $Y$ to predicted $Y$.
4. Divide by the residual's standard error.

The test uses a $t$ distribution with:

$$
n-k-2
$$

degrees of freedom.

The $-2$ is a common exam trap. Deleting one observation leaves $n-1$ observations, and estimating $k$ slopes plus an intercept uses $k+1$ parameters:

$$
(n-1)-(k+1)=n-k-2
$$

## Influential Observations

An influential observation is one whose removal causes a meaningful change in estimated regression coefficients. It is not defined only by being weird. It is defined by changing the model.

```text
High leverage + large studentized residual
  |
  v
Likely influential observation
```

Cook's distance is a common combined influence measure because it blends leverage and residual size. CFA's core emphasis is conceptual: identify whether an observation is extreme enough to affect the regression, then investigate why.

## What To Do After Finding One

Do not automatically delete influential observations. The correct action depends on the cause.

| Cause | Appropriate response |
|---|---|
| Data entry or measurement error | Correct or delete the observation |
| Observation from wrong population | Exclude if justified and disclosed |
| Valid but rare event | Usually keep it, but consider whether the model needs added variables or nonlinear terms |
| Valid but distorting extreme value | Consider robust methods, winsorization, or a better model specification |

Deleting valid observations just to improve fit is not analysis. It is data mining and can create an ethics problem if undisclosed.

## Worked Numerical Example

Suppose an analyst models ROA for $n=60$ companies using $k=4$ independent variables. Software reports the following for Company Z:

| Diagnostic | Value |
|---|---:|
| Leverage, $h_{ii}$ | 0.28 |
| Studentized deleted residual, $t_i^*$ | 2.45 |
| Cook's distance | 0.35 |

Assume the relevant two-tailed critical $t$ value is 2.00.

First test leverage:

$$
\frac{3(k+1)}{n}
=
\frac{3(4+1)}{60}
=
\frac{15}{60}
=
0.25
$$

Because:

$$
0.28 > 0.25
$$

Company Z is a high-leverage point.

Now test whether it is an outlier:

$$
n-k-2=60-4-2=54
$$

Because:

$$
|2.45|>2.00
$$

Company Z is also an outlier.

Since it is both high-leverage and an outlier, it is likely influential. The analyst should investigate the data and model specification before deciding whether to correct, remove, winsorize, or retain the observation.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Confusing outlier and leverage | Says an extreme $X$ observation is a $Y$ outlier | Leverage is about $X$; outlier is about $Y$ |
| Assuming all outliers are influential | Deletes observations just because residuals are large | Influence means coefficients change materially |
| Forgetting deleted-residual degrees of freedom | Uses $n-k-1$ instead of $n-k-2$ | Deleted residuals use $n-k-2$ |
| Automatically deleting valid data | Improves fit by removing inconvenient observations | Investigate cause first |
| Ignoring model misspecification | Treats an influential point as a nuisance | It may reveal omitted variables or nonlinear structure |

## Memory Hooks

**Leverage is weird X. Outlier is weird Y. Influence is model damage.**

**Deleted residual means one observation is gone, so degrees of freedom are $n-k-2$.**

**Investigate before deleting.**

## Related Concepts

- [[Studentized Residuals]]
- [[Extensions of Multiple Regression]]
- [[Multiple Regression - Basics and Assumptions]]
- [[Model Misspecification]]
- [[Multicollinearity]]
- [[Regression Assumptions]]
- [[Ordinary Least Squares]]
