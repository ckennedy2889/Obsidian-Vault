---
title: Neural Networks
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, machine-learning, neural-networks, deep-learning]
aliases: [Neural Network, Artificial Neural Network, ANN, Deep Neural Network, DNN, Deep Learning Network, DLN]
---

# Neural Networks

> A [[neural network]] is a flexible [[Machine Learning]] model made of connected nodes arranged in layers. It transforms input features through weighted sums and nonlinear activation functions so the model can learn complex, nonlinear relationships.

## The Real-World Analogy

Imagine an investment committee trying to predict whether a stock will outperform.

One analyst looks at valuation. Another looks at profitability. Another looks at momentum. Another looks at leverage. Each analyst sends a signal to a second group of analysts. That second group does not just average the signals. They transform them:

```text
If valuation is cheap AND profitability is strong, pay attention.
If leverage is high BUT cash flow is stable, reduce the warning.
If momentum is strong ONLY when revisions are positive, boost the signal.
```

Then a final decision maker combines those transformed signals into a prediction.

That is the intuition of a neural network.

It is not just:

```text
Input -> prediction
```

It is:

```text
Input features
  |
  v
Weighted combinations
  |
  v
Nonlinear transformations
  |
  v
More weighted combinations
  |
  v
Prediction
```

The magic is the middle: hidden layers create transformed features that can capture nonlinear interactions the analyst may not specify manually.

## One-Minute Version

A neural network has three types of layers:

| Layer | Job |
|---|---|
| Input layer | Receives the feature values |
| Hidden layer(s) | Learns transformed combinations of the inputs |
| Output layer | Produces the prediction or class probabilities |

Each hidden node receives inputs from prior nodes, multiplies each input by a weight, adds them up using a summation operator, and passes the result through a nonlinear activation function. The output then moves forward to the next layer. This is [[forward propagation]].

During training, the model compares predictions to actual labels, calculates error using a loss function, and adjusts weights to reduce error. When the adjustment works backward through the network, it is called [[backward propagation]].

Neural networks are powerful because they can model nonlinear relationships and interactions among features. The trade-off is that they are data-hungry, computationally intensive, prone to [[overfitting]], and often hard to interpret.

## LOS Coverage

Neural networks sit in the CFA Level II Quantitative Methods machine learning LOS:

| LOS language | What you must be able to do |
|---|---|
| Describe [[supervised learning]], [[unsupervised learning]], and [[deep learning]] | Understand where neural networks and deep neural networks fit in ML |
| Describe neural networks, deep learning nets, and [[reinforcement learning]] | Know nodes, links, layers, weights, activation functions, forward/backward propagation, and deep networks |
| Describe [[overfitting]] and identify methods of addressing it | Know that more nodes/layers increase complexity and overfitting risk |
| Determine appropriate algorithms for problems | Use neural networks for large datasets, nonlinear relationships, complex interactions, image/text/speech/pattern-recognition tasks |

## The Big Idea

A neural network is a machine that learns transformations.

A simple regression says:

$$
\hat{y} = b_0 + b_1x_1 + b_2x_2 + b_3x_3
$$

That is a weighted sum of the original inputs.

The model is asking:

```text
How much does each original feature contribute directly to y?
```

A neural network asks a deeper question:

```text
Can combinations of features be transformed into new hidden signals
that better explain y?
```

Instead of going directly from $x$ to $\hat{y}$, it goes:

```text
x variables -> hidden transformations -> output
```

That is why the hidden layer matters. The hidden layer creates intermediate learned features.

For example, in finance:

```text
x1 = valuation
x2 = profitability
x3 = leverage
x4 = momentum
```

A hidden node might learn something like:

```text
"cheap quality stock"
```

Another might learn:

```text
"levered growth trap"
```

Another might learn:

```text
"positive momentum with improving fundamentals"
```

The analyst does not explicitly label these hidden features. The network discovers useful transformations by adjusting weights during training.

## The Anatomy Of A Neural Network

Neural networks consist of nodes connected by links.

```text
Input layer          Hidden layer             Output layer

x1  ----\              z1  ----\
x2  -----\             z2  -----\
x3  ------> weighted   z3  ------> prediction
x4  -----/  sums +     z4  -----/
          activation   z5  ----/
```

### Input Layer

The input layer receives the features.

If there are four features, there are four input nodes:

```text
x1 = valuation
x2 = profitability
x3 = leverage
x4 = momentum
```

The input layer does not "learn" in the same way hidden layers do. It passes feature values into the network.

### Hidden Layer

The hidden layer is where learning occurs.

Each hidden node receives values from prior nodes. Each incoming link has a weight. The hidden node:

1. Multiplies each input by its weight.
2. Adds the weighted inputs.
3. Passes the sum through an activation function.
4. Sends the transformed output onward.

### Output Layer

The output layer produces the model output.

For regression, the output may be one number:

```text
Predicted stock return = 8.2%
```

For classification, the output may be a class or a set of class probabilities:

```text
Winner: 70%
Average: 20%
Loser: 10%
```

The predicted class is the one with the highest probability.

## Node Mechanics: Summation Plus Activation

Each hidden node has two conceptual parts:

```text
Summation operator -> Activation function
```

Suppose a hidden node receives three inputs:

$$
x_1, x_2, x_3
$$

Each input has a weight:

$$
w_1, w_2, w_3
$$

The node first calculates the weighted sum:

$$
s = w_1x_1 + w_2x_2 + w_3x_3
$$

Then it applies an activation function:

$$
z = f(s)
$$

The output $z$ is passed to the next layer.

The CFA phrasing to remember:

> The summation operator multiplies each input by its weight and sums the weighted values into total net input. The activation function transforms that total net input into the node's output.

## Worked Numerical Example: One Hidden Node

Suppose a hidden node receives three scaled inputs:

| Feature | Input value | Weight |
|---|---:|---:|
| Valuation score | $x_1 = 0.80$ | $w_1 = 0.50$ |
| Profitability score | $x_2 = 0.60$ | $w_2 = 0.30$ |
| Leverage risk score | $x_3 = 0.20$ | $w_3 = -0.40$ |

The weighted sum is:

$$
s = w_1x_1 + w_2x_2 + w_3x_3
$$

Substitute:

$$
s = (0.50)(0.80) + (0.30)(0.60) + (-0.40)(0.20)
$$

Calculate each term:

$$
(0.50)(0.80) = 0.40
$$

$$
(0.30)(0.60) = 0.18
$$

$$
(-0.40)(0.20) = -0.08
$$

Add them:

$$
s = 0.40 + 0.18 - 0.08 = 0.50
$$

Now suppose the activation function is ReLU:

$$
f(s) = \max(0, s)
$$

Since:

$$
s = 0.50 > 0
$$

the hidden node output is:

$$
z = \max(0, 0.50) = 0.50
$$

Interpretation:

The node activates and passes a positive signal forward.

If the weighted sum had been negative, ReLU would output zero:

$$
f(-0.30) = \max(0, -0.30) = 0
$$

That is why activation functions can act like gates or dimmer switches.

## Activation Functions

An activation function transforms the total net input from a node.

Why do we need it?

Because if every layer only took weighted sums, then stacking many layers would still collapse into one big linear model. The model would not gain true nonlinear flexibility.

Nonlinear activation functions let the network bend the relationship.

| Activation function | Form | Intuition |
|---|---|---|
| Sigmoid | S-shaped, output between 0 and 1 | Converts very negative inputs near 0 and very positive inputs near 1 |
| ReLU | $f(x)=\max(0,x)$ | Negative inputs become 0; positive inputs pass through |

CFA describes the activation function as a light dimmer switch:

```text
Low/negative total net input -> weak or no signal
High/positive total net input -> stronger signal
```

The exam point is not to derive deep learning math. The exam point is to know that:

```text
Summation operator = weighted sum
Activation function = nonlinear transformation
```

## Forward Propagation

Forward propagation is the process of moving information through the network from inputs to output.

```text
Input layer
  |
  v
Hidden layer weighted sums
  |
  v
Activation functions
  |
  v
Next hidden layer, if any
  |
  v
Output layer
```

In a trained network, forward propagation is how a new prediction is made.

For example:

```text
New company features enter the input layer.
Hidden layers transform the features.
Output layer gives predicted default probability.
```

## Training and Backward Propagation

Training means finding weights that reduce prediction error.

The process:

```text
Start with initial weights
  |
  v
Forward propagate inputs to make predictions
  |
  v
Compare predictions with actual labels
  |
  v
Calculate total error using a loss function
  |
  v
Adjust weights to reduce error
  |
  v
Repeat
```

If the adjustment works backward through the layers, CFA calls this [[backward propagation]].

The informal update rule is:

$$
\text{New weight}
= \text{Old weight}
- \text{Learning rate}
\times
\frac{\partial \text{Total error}}{\partial \text{Old weight}}
$$

Why this formula?

The partial derivative tells the model how total error changes when a weight changes. If increasing a weight increases error, the model should reduce that weight. If increasing a weight reduces error, the model should increase that weight. The learning rate controls how large each adjustment is.

This is the deep reason neural networks "learn": they repeatedly adjust link weights in the direction that reduces the loss function.

## Loss Function

A loss function measures how wrong the network is.

For a regression problem, CFA mentions a performance measure such as [[mean squared error]]:

$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$

Why squared errors?

Because positive and negative errors should not cancel. Squaring makes errors positive and penalizes large mistakes more heavily.

The training goal is:

$$
\text{Choose weights to minimize loss}
$$

In plain English:

> The network changes its weights until its predictions are less wrong.

## Why Inputs Are Scaled

Neural network inputs are often scaled or standardized.

Why?

Because the model combines inputs using weights. If one feature is measured in billions of dollars and another is measured as a percent, the feature with the larger numeric scale can dominate the training process.

Example:

```text
Market cap: 500,000,000,000
Profit margin: 0.12
```

Without scaling, the network may treat market cap as overwhelming just because of its units.

CFA gives the example that if inputs are positive, they can be scaled by their maximum value so they lie between 0 and 1.

```text
Scaling makes feature values comparable.
Comparable values make training more stable.
```

## Hyperparameters

Some things are learned from the data. Other things are set by the researcher before or during model design.

Weights are learned parameters.

Network design choices are hyperparameters.

| Hyperparameter | Meaning |
|---|---|
| Number of hidden layers | How deep the network is |
| Number of nodes per hidden layer | How wide each layer is |
| Activation function | How node inputs are transformed |
| Learning rate | How aggressively weights are adjusted |
| Connectivity architecture | Which nodes connect to which other nodes |
| Regularization strength | How much complexity is penalized |

CFA example:

```text
4 input nodes, 5 hidden nodes, 1 output node
```

This structure can be described as:

```text
4-5-1
```

Those structural choices are hyperparameters.

## Deep Neural Networks

A [[deep neural network]] is a neural network with many hidden layers.

CFA wording:

> Neural networks with many hidden layers, at least 2 but often more than 20, are known as deep neural networks.

The difference:

| Model | Hidden layers | Main idea |
|---|---:|---|
| Shallow neural network | Usually one hidden layer | Learns one level of transformed features |
| Deep neural network | Many hidden layers | Learns multiple levels of transformed features |

Why does depth matter?

Each hidden layer can transform the output of the prior layer. That lets the model learn layered abstractions.

For example, in image recognition:

```text
Pixels
  |
  v
Edges
  |
  v
Shapes
  |
  v
Objects
```

In finance, the abstraction is less visible, but the idea is similar:

```text
Raw features
  |
  v
Ratios and interactions
  |
  v
Risk regimes or factor states
  |
  v
Prediction
```

DNNs are especially useful for pattern recognition, image recognition, speech recognition, natural language processing, fraud detection, and complex investment applications with large datasets.

## Neural Networks vs Reinforcement Learning

Neural networks and reinforcement learning are related but not the same.

| Concept | What it means |
|---|---|
| Neural network | A model architecture made of layers, nodes, weights, and activation functions |
| Deep learning | ML based on deep neural networks with many hidden layers |
| Reinforcement learning | A learning setup where an agent learns by taking actions and receiving rewards or penalties |

The important CFA distinction:

> Neural networks are often used in supervised classification/regression. Reinforcement learning does not rely on human-labeled training data in the same way; it learns through trial and error from feedback.

Example:

```text
Neural network supervised learning:
  Input company features
  Known label: default/no default
  Learn weights to predict label

Reinforcement learning:
  Agent tries actions
  Receives rewards/penalties
  Learns policy through many trials
```

## Why Neural Networks Handle Nonlinear Relationships

The deepest reason is this:

```text
Weighted sums alone are linear.
Activation functions introduce nonlinearity.
Multiple layers compose nonlinear transformations.
Therefore neural networks can approximate complex nonlinear relationships.
```

Suppose stock returns depend on valuation only under certain conditions:

```text
Cheap valuation helps
  only when profitability is high
    and leverage is not excessive
      and momentum has not collapsed
```

A linear model has trouble unless the analyst manually creates interaction terms.

A neural network can learn hidden transformations that approximate those interactions.

That is why CFA says neural networks are useful for tasks characterized by:

- Nonlinearities
- Interactions among features
- Large datasets
- Complex patterns

## Overfitting Risk

More nodes and more layers increase flexibility.

That sounds good, but it creates risk:

```text
More flexibility
  |
  v
Better ability to fit training data
  |
  v
Higher risk of fitting noise
  |
  v
Poor out-of-sample performance
```

This is [[overfitting]].

The neural network may learn quirks of the training sample rather than stable economic relationships.

Ways to fight overfitting include:

| Method | Intuition |
|---|---|
| More training data | Real patterns are easier to separate from noise |
| Cross-validation | Tune hyperparameters based on out-of-sample performance |
| Regularization | Penalize excessive model complexity |
| Smaller architecture | Fewer layers/nodes reduce flexibility |
| Early stopping | Stop training before the model memorizes noise |

CFA specifically connects neural networks and DNNs to large data needs, high computation, and overfitting risk.

## Investment Applications

| Application | Why neural networks may fit |
|---|---|
| Equity return prediction | Captures dynamic nonlinear interactions among valuation, profitability, momentum, risk, and macro features |
| Option pricing | DNNs can approximate option pricing relationships using inputs such as spot price, strike, time to maturity, dividend yield, risk-free rate, and volatility |
| Fraud detection | Detects complex patterns in transaction data |
| Style drift detection | Processes large trading datasets to identify changing manager behavior |
| Natural language processing | Classifies or summarizes financial text, news, filings, and sentiment |
| Image, pattern, and speech recognition | Deep learning is well suited to high-dimensional unstructured data |
| Automation of internal processes | Finds complex patterns in operational data |

## Advantages

| Advantage | Why it matters |
|---|---|
| Handles nonlinear relationships | Activation functions and layers let the model bend |
| Captures interactions | Hidden nodes can combine features in complex ways |
| Flexible | Can be used for regression, classification, and pattern recognition |
| Strong with large datasets | Can exploit large amounts of machine-readable data |
| Useful for unstructured data | Especially powerful in text, image, and speech applications |

## Disadvantages

| Disadvantage | Why it matters |
|---|---|
| Black box nature | Hard to explain exactly why the model made a prediction |
| Data hungry | Often requires large training datasets |
| Computationally intensive | Training can take substantial time and resources |
| Overfitting risk | More layers/nodes can memorize noise |
| Hyperparameter complexity | Number of layers, nodes, activation functions, and learning rate must be chosen |
| Not always appropriate | If interpretability is essential, simpler models may be better |

## Neural Networks vs Other CFA ML Algorithms

| Method | Core idea | Main contrast with neural networks |
|---|---|---|
| [[LASSO]] | Linear model with coefficient shrinkage and feature selection | More interpretable, less flexible for nonlinear interactions |
| [[Support Vector Machines]] | Finds a separating boundary with maximum margin | Often better for smaller classification tasks; neural networks are more flexible and data-hungry |
| [[k-Nearest Neighbor]] | Classifies based on nearby labeled observations | KNN is distance-based and local; neural networks learn weights and transformations |
| [[CART]] | One decision tree with if-then splits | More interpretable; less flexible than large neural networks |
| [[Random Forests]] | Many decision trees combined by voting/averaging | Robust ensemble; still less layered than DNNs |
| [[Principal components analysis]] | Reduces correlated features into components | Unsupervised dimension reduction, not a prediction architecture |
| [[K-Means Clustering]] | Groups observations into clusters | Unsupervised grouping, not supervised prediction |

## Common Wrong Reasoning

### Wrong: "Neural networks are exactly modeled on the human nervous system."

Why it is wrong: CFA explicitly treats that as incorrect. The name is inspired by neurons, but the model is a mathematical architecture of nodes, links, weights, and activation functions.

### Wrong: "A neural network must have at least 10 hidden layers to be deep."

Why it is wrong: CFA says deep neural networks have many hidden layers, at least 2 but often more than 20. "At least 10" is too specific and wrong.

### Wrong: "The activation function adds up the weighted inputs."

Why it is wrong: The summation operator adds weighted inputs. The activation function transforms the total net input.

### Wrong: "More layers always improve the model."

Why it is wrong: More layers increase complexity and can improve fit, but they also increase overfitting risk, training time, and hyperparameter difficulty.

### Wrong: "Neural networks are always the best choice for investment problems."

Why it is wrong: They can be powerful, but their lack of interpretability, data needs, computation cost, and overfitting risk mean they may not fit many investment applications.

### Wrong: "Neural networks do not need scaled inputs."

Why it is wrong: CFA notes that neural network feature inputs are scaled or standardized to account for differences in units.

## When You See This, Do This

| Vignette clue | Exam move |
|---|---|
| Input, hidden, output layers | Neural network |
| Nodes connected by links | Neural network |
| Summation operator plus activation function | Neural network |
| Light dimmer switch | Activation function |
| ReLU or sigmoid | Activation function |
| Many hidden layers | Deep neural network / deep learning |
| Image, speech, NLP, pattern recognition | Deep learning is likely appropriate |
| Large data, nonlinear interactions | Neural networks may fit |
| Need clear interpretability | Neural networks may be less appropriate |
| Agent learns by trial and error with rewards | Reinforcement learning |

## Minimum Memorization

Memorize this:

```text
Neural network = input layer
               + hidden layer(s)
               + output layer
               + weighted links
               + summation operators
               + activation functions
```

And this:

```text
Node:
  weighted inputs -> sum -> activation -> output
```

And this:

```text
More layers/nodes:
  more complexity
  more nonlinear power
  more overfitting risk
  more training cost
```

## Can I Solve This?

You are ready for neural network questions if you can answer these:

1. What are the three layer types in a neural network?
2. What does a hidden node do?
3. What is the difference between the summation operator and activation function?
4. Why do activation functions need to be nonlinear?
5. What is forward propagation?
6. What is backward propagation?
7. Why are inputs scaled?
8. Why do neural networks handle nonlinear relationships?
9. What makes a neural network "deep"?
10. Why are neural networks considered black boxes?

## Related Concepts

- [[Machine Learning]]
- [[Supervised learning]]
- [[Deep learning]]
- [[Deep neural network]]
- [[Neural network]]
- [[Reinforcement learning]]
- [[Activation function]]
- [[Forward propagation]]
- [[Backward propagation]]
- [[Loss function]]
- [[Mean squared error]]
- [[Hyperparameter]]
- [[Overfitting]]
- [[Regularization]]
- [[LASSO]]
- [[Support Vector Machines]]
- [[k-Nearest Neighbor]]
- [[CART]]
- [[Random Forests]]
- [[Principal components analysis]]
- [[K-Means Clustering]]
- [[Natural language processing]]
