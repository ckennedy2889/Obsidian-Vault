---
title: Unit Root
subject: 02 - Quantitative Methods
tags: [CFA-L2, CFA, glossary, time-series, stationarity, AR-models, random-walk]
aliases: [unit roots, unit-root process, integrated of order 1, I(1)]
---

# Unit root

**Program:** CFA® Program
**Level:** Level II

## Definition

A time series that is not covariance stationary is said to have a unit root. Algebraically, in an AR(1) representation $x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$, a unit root is the condition $b_1 = 1$.

---

## The Real-World Analogy

Picture a drunk walking home on a perfectly flat sidewalk with no streetlights. Every step, he stumbles a little to the left or a little to the right, randomly. Where will he be after 1,000 steps?

**You have no idea.** The center of his probable location might still be roughly where he started, but the *spread* of where he could plausibly be is enormous — he might be a block north, a block south, half a mile east, anywhere. And critically, where he was 500 steps ago tells you almost nothing useful about constraining where he is now, because every random stumble is *permanent* — it never gets undone.

That's a unit-root process. Each random shock is absorbed forever into the level of the series, never decaying away. The series has *infinite memory of its noise*. Contrast this with a stationary AR(1) where shocks fade geometrically — that drunk would be on a leash tied to a lamppost, and no matter how he stumbles, he keeps getting tugged back toward the lamppost.

The unit root is the mathematical statement that **the leash has been cut**.

---

## Algebraic Definition — Where the Name Comes From

Start with the AR(1) model:

$$x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$$

Rewrite using the lag operator $L$, where $L x_t = x_{t-1}$:

$$x_t - b_1 L x_t = b_0 + \varepsilon_t$$
$$(1 - b_1 L) x_t = b_0 + \varepsilon_t$$

The **characteristic equation** is $1 - b_1 z = 0$, whose root (solution for $z$) is:

$$z = \frac{1}{b_1}$$

A "unit root" literally means **the root of this equation equals 1** — i.e., $z = 1$, which forces $b_1 = 1$. That's where the name comes from.

| Condition on $b_1$ | Root $z$ | Behavior |
|---------------------|----------|----------|
| $\lvert b_1 \rvert < 1$ | $\lvert z \rvert > 1$ ("outside the unit circle") | **Stationary** — shocks decay, series mean-reverts |
| $b_1 = 1$ | $z = 1$ ("on the unit circle") | **Unit root** — non-stationary, shocks permanent |
| $\lvert b_1 \rvert > 1$ | $\lvert z \rvert < 1$ | **Explosive** — shocks amplify, series diverges |

For CFA Level 2, you only need to recognize **$b_1 = 1$ ⇒ unit root ⇒ non-stationary**. The lag-operator derivation just shows you *why* the property is named that way.

---

## Why a Unit Root Forces Non-Stationarity

A covariance-stationary series needs a constant mean, a constant finite variance, and lag-only covariances (see [[Covariance stationary]]). A unit root breaks the first two simultaneously.

### The mean becomes undefined

For a stationary AR(1), the long-run mean is:

$$\mu = \frac{b_0}{1 - b_1}$$

This is the value the series gravitates toward. **Why?** Because at the long-run mean, on average $x_t = x_{t-1} = \mu$, so $\mu = b_0 + b_1 \mu$, which solves to the formula above.

If $b_1 = 1$:

$$\mu = \frac{b_0}{1 - 1} = \frac{b_0}{0} \quad \text{(undefined)}$$

There is no fixed value the series tends toward. It has no anchor, no home base, no mean to revert to.

### The variance grows without bound

This is the killer. In a stationary AR(1), variance is finite and constant:

$$\text{Var}(x_t) = \frac{\sigma_\varepsilon^2}{1 - b_1^2}$$

When $b_1 = 1$, this formula also blows up ($\sigma_\varepsilon^2 / 0$), but the *correct* derivation for a unit-root process gives a different — and more revealing — answer. Start from the simplest unit-root case, the random walk without drift ($b_0 = 0$, $b_1 = 1$, $x_0 = 0$):

$$x_t = x_{t-1} + \varepsilon_t$$

Recursing back to time 0:

$$x_t = \varepsilon_1 + \varepsilon_2 + \cdots + \varepsilon_t = \sum_{i=1}^{t} \varepsilon_i$$

The series at time $t$ is just the cumulative sum of all past shocks. Since the shocks are independent with variance $\sigma_\varepsilon^2$ each:

$$\boxed{\text{Var}(x_t) = t \cdot \sigma_\varepsilon^2}$$

**The variance grows linearly with time.** At $t = 100$ it is 100× the shock variance; at $t = 10{,}000$ it is 10,000×. There is no bound. A series whose variance keeps expanding cannot have a constant variance — and therefore cannot be covariance stationary.

---

## The Two Faces of a Unit Root: Random Walks

Every random walk has a unit root. There are two flavors:

### Random walk without drift ($b_0 = 0$, $b_1 = 1$)

$$x_t = x_{t-1} + \varepsilon_t$$

The best forecast of tomorrow is *whatever today is*. That's the famous "stock prices follow a random walk" result. The series wanders aimlessly with no preferred direction.

### Random walk with drift ($b_0 \neq 0$, $b_1 = 1$)

$$x_t = b_0 + x_{t-1} + \varepsilon_t$$

Now there's a constant push of $b_0$ each period. The series climbs (or falls) by $b_0$ on average per step, with random shocks layered on top. A nominal GDP series, for instance, often looks like a random walk with a positive drift.

Both contain a unit root. Both are non-stationary. Both must be transformed before AR modeling.

---

## Why You Cannot Test $b_1 = 1$ With a Normal t-Test

Here's the subtle part — and the reason Dickey and Fuller had to invent a new test in 1979.

The naive approach: run OLS to estimate $\hat{b}_1$, then compute $t = (\hat{b}_1 - 1) / \text{SE}(\hat{b}_1)$ and compare to standard t-table critical values.

**This fails.** Here's why:

1. The OLS standard error formula assumes the regressors are stationary. When $b_1 = 1$ (the very thing you're testing), the regressor $x_{t-1}$ is itself non-stationary — its variance grows with $t$.
2. Under that violation, the sampling distribution of the t-statistic is **not** Student's t. It is skewed toward more negative values and has fatter tails.
3. Using normal t critical values would reject $H_0: b_1 = 1$ far too often — leading you to conclude "stationary" when in fact the series is a unit-root process. That false conclusion then enables [[CFA_Glossary/Spurious correlation|spurious regressions]].

This is the chicken-and-egg problem: the validity of the test depends on the answer to the test. Dickey and Fuller solved it by deriving the *correct* sampling distribution under $H_0$ and tabulating new critical values.

---

## The Dickey-Fuller Test

### The transformation

Subtract $x_{t-1}$ from both sides of the AR(1):

$$x_t - x_{t-1} = b_0 + b_1 x_{t-1} - x_{t-1} + \varepsilon_t$$
$$\Delta x_t = b_0 + (b_1 - 1) x_{t-1} + \varepsilon_t$$

Let $g_1 = b_1 - 1$. The test regression is:

$$\Delta x_t = b_0 + g_1 x_{t-1} + \varepsilon_t$$

This is the **Dickey-Fuller regression**. Notice the elegance: the dependent variable is now $\Delta x_t$, which is stationary if there's a unit root (a differenced random walk is white noise plus drift). So OLS becomes well-behaved on this transformed equation.

### Hypotheses

| | Statement | Translation |
|---|-----------|-------------|
| **$H_0$** | $g_1 = 0$ (i.e., $b_1 = 1$) | The series **has** a unit root → non-stationary |
| **$H_a$** | $g_1 < 0$ (i.e., $b_1 < 1$) | The series is stationary |

This is a **one-tailed** test (lower tail), because $b_1 > 1$ would be explosive — economically implausible — so we only worry about $b_1 \leq 1$.

### Critical values

Compute the t-statistic on $\hat{g}_1$ from the OLS output, then compare to **Dickey-Fuller critical values** (NOT standard t-table values). DF critical values are *larger in absolute magnitude* than standard t critical values. Approximate values for a typical sample size:

| Significance | Standard t (large n) | Dickey-Fuller |
|--------------|----------------------|---------------|
| 10% | −1.28 | ≈ −2.57 |
| 5% | −1.65 | ≈ −2.86 |
| 1% | −2.33 | ≈ −3.43 |

**Decision rule:** if the computed t-stat on $\hat{g}_1$ is **more negative** than the critical value, reject $H_0$ → the series is stationary.

If you fail to reject, the series has a unit root.

---

## What to Do When You Detect a Unit Root

### First-differencing — the canonical fix

Build a new series:

$$y_t = x_t - x_{t-1} = \Delta x_t$$

For a random walk with drift, this differenced series is just $b_0 + \varepsilon_t$ — constant mean, constant variance, zero autocorrelation. It's stationary white noise around the drift. Now you can run AR/MA/ARMA models on $\{y_t\}$ legitimately.

### Order of integration

A series that becomes stationary after exactly **one round** of differencing is called **integrated of order 1**, written $I(1)$. A stationary series with no differencing required is $I(0)$. Some macro series (e.g., price levels in some specifications) need two rounds and are $I(2)$.

The notation matters because you need both series in a regression to share the *same* order of integration before you can model their relationship — unless they are cointegrated (next section).

---

## Cointegration — When Two Unit-Root Series Can Still Be Modeled Together

Normally, regressing one $I(1)$ series on another produces a [[CFA_Glossary/Spurious correlation|spurious regression]] — both wander, both can look correlated by chance, the $R^2$ is huge, and the relationship is fake.

**Exception:** if two non-stationary series share a real long-run economic equilibrium, they are **cointegrated**. Examples:

- Short-term interest rates and long-term interest rates — both wander, but the spread between them is stationary.
- Spot and futures prices on the same commodity — individually random walks, but tied together by arbitrage.
- Consumption and income — both grow without bound, but the savings rate (their ratio) is roughly stable.

The mathematical signature of cointegration: a *linear combination* of the two non-stationary series is itself stationary. Geometrically, both series wander, but they wander *together* — staying tethered to each other.

### The Engle-Granger test

1. Regress $y_t$ on $x_t$: $y_t = \hat{\alpha} + \hat{\beta} x_t + \hat{u}_t$.
2. Save the residuals $\hat{u}_t$.
3. Run a Dickey-Fuller test on $\hat{u}_t$ (with adjusted critical values).
4. If you reject $H_0$ (residuals are stationary), the series are **cointegrated** — the regression coefficients describe a real long-run relationship.
5. If you fail to reject (residuals are non-stationary), the regression is spurious — discard.

If cointegrated, the level-on-level regression is meaningful. If not, work with first-differences only.

---

## Worked Numerical Example — Variance Explosion

Take the simplest unit-root process: a random walk starting at $x_1 = 0$ with shock variance $\sigma_\varepsilon^2 = 100$ (so each shock has standard deviation 10).

$$x_t = x_{t-1} + \varepsilon_t$$

Recursing: $x_t = \sum_{i=2}^{t} \varepsilon_i$. With independent shocks, variances simply add.

| Time $t$ | Number of shocks accumulated | $\text{Var}(x_t)$ | $\text{SD}(x_t)$ |
|----------|------------------------------|-------------------|------------------|
| 1 | 0 | 0 | 0 |
| 2 | 1 | 100 | 10 |
| 3 | 2 | 200 | ≈ 14.1 |
| 11 | 10 | 1,000 | ≈ 31.6 |
| 101 | 100 | 10,000 | 100 |
| 1,001 | 1,000 | 100,000 | ≈ 316 |
| 10,001 | 10,000 | 1,000,000 | 1,000 |

The standard deviation — the typical distance from where you started — grows like $\sqrt{t}$. After 10,000 steps, the drunk could plausibly be 1,000 units of distance from the lamppost. After a million steps, 10,000 units away. **There is no bound.**

Compare this to a stationary AR(1) with $b_1 = 0.5$ and $\sigma_\varepsilon^2 = 100$:

$$\text{Var}(x_t) = \frac{\sigma_\varepsilon^2}{1 - b_1^2} = \frac{100}{1 - 0.25} = 133.3$$

…no matter how far into the future you look. The leash holds.

This is the *quantitative* core of why a unit root is fatal to forecasting. A 95% prediction interval $\pm 1.96 \cdot \text{SD}(x_t)$ for a unit-root series widens every period; for a stationary series it stabilizes after a few lags. Long-horizon forecasts of a unit-root process are useless.

---

## Numerical Example — Why the Standard t-Test Misleads

Suppose you simulate a random walk for $T = 250$ periods and run OLS on $x_t = b_0 + b_1 x_{t-1} + \varepsilon_t$. A typical result:

- $\hat{b}_1 \approx 0.97$ (close to but not exactly 1)
- $\text{SE}(\hat{b}_1) \approx 0.012$
- Standard t-stat for $H_0: b_1 = 1$: $(0.97 - 1)/0.012 = -2.5$

A naive analyst checks the standard t-table: $-2.5$ is more extreme than $-1.96$, so reject $H_0$ at 5% — "the series is stationary." Run forecasts. Build a portfolio. Lose money.

The correct test using DF critical values: $-2.5$ is **less negative** than the 5% DF critical value of $\approx -2.86$, so **fail to reject**. The series has a unit root. First-difference it before modeling.

The same test statistic, two different conclusions, depending on which critical-value table you consult. That is the whole reason the Dickey-Fuller test exists.

---

## Connections

- [[Covariance stationary]] — the property a unit root violates
- [[AR(1) Model]] — the model whose lag coefficient is being tested
- [[Random Walk]] — the canonical unit-root process
- [[Dickey-Fuller Test]] — the formal test for a unit root
- [[First Differencing]] — the standard remedy
- [[Cointegration]] — the escape hatch for two unit-root series
- [[Engle-Granger Test]] — the cointegration test
- [[CFA_Glossary/Spurious correlation]] — the consequence of ignoring a unit root
- [[Mean Reversion]] — what stationary AR(1) has and unit-root processes lack
- [[Nonstationarity]]
- [[Stationary]]

---

## LOS Coverage

This note supports the Time-Series Analysis LOS:

- **Describe** the structure and behavior of a random walk → unit root sections above.
- **Explain** the implications of a unit root and how to test for it → DF section.
- **Describe** how to test and correct for non-stationarity → DF + first-differencing.
- **Describe** cointegration and explain its significance → cointegration section.

**Tags:** #CFA #glossary #CFA-L2 #time-series #stationarity #AR-models #random-walk
