## Neural Networks:
## Origami Shaped by Data


--

## Basics: Modeling

- Models are used to predict things
- They learn from data
- Input (features): `n` numbers
- Output (targets): `m` numbers

--

## Setups

- Config 1
    - 1D Input -> 1D Output
    - `x -> y`
- Config 2
    - 2D Input -> 1D Output
    - `(x0, x1) -> y`
- Config 3
    - 3D Input Sequence -> 3D Output
    - `[(x0, x1, x2)] -> (x0, x1, x2)`

---

## NN's Building Block: ReLU

- a.k.a. the "activation" or "nonlinearity"
    - `ReLU(x) = max(x, 0)`
- A "Neuron" is a tunable `ReLU`:
    - `y = ReLU(w*x + b)`
    - `w` and `b` are freely tunable
- The effect: straight lines get folded once

[Play!](viz/00-relu.html)

--

## Two Neurons = Two Folds

- Multiple neurons can be added up
    - 2 neurons: `y = ReLU(w0*x + b0) + ReLU(w1*x + b1)`
- 2 knobs to be tuned
- 2 folds to be created
- Also shown:
    - fake data points with prediction error
    - approx. number of folds, or knee points

[Play!](viz/01-2relus.html)

--

## More Neurons = More Folds

- More knobs to be tuned
- More folds to be created
- Only summing up positive neurons => output always positive

[Play!](viz/02-4relus.html)

--

## Simplest NN: Perceptron


- Output layer now tunable => outputs can be negative now
- 4 hidden neurons, creates 4 folds

![Perceptron of size 4](imgs/perceptron4.png)

[Play!](viz/03-nn1x4.html)

--

## Widening the Perceptron

- 12 hidden neurons: 12 folds
- More "budget" to smooth the curve
- More freedom to fold a line into the shape of data
- Widening the hidden layer to ∞
    => Universal Approximation Theorem

[Play!](viz/04-nn1x12.html)

--

## Adding More Layers

- 2 hidden layers with 6 neurons each: still 12 folds
- Little qualitative difference vs. Perceptron

[Play!](viz/05-nn2x6.html)

--

## Keep Deepening

- 4 hidden layers with 3 neurons each
- More "expressive" yet also more "inhibited"
    => ability to model finer and more localized features

[Play!](viz/06-nn4x3.html)

--

## Even Deeper

- 6 hidden layers with 2 neurons each
- High chance of inhibition
- High chance of sharp folds
- Easier to fold into local and complex shapes

[Play!](viz/07-nn6x2.html)

---

## 2D Input

- Still a perceptron, but with two inputs
- 2 hidden layers with 6 neurons each
- NNs get to make straight creases on "a sheet of paper"

[Play!](viz/08-input2d-nn2x6.html)

--

## 2D Input with Deeper NN

- 4 hidden layers with 3 neurons each
- Similar effect of deepening: harder creases and finer wrinkles

[Play!](viz/09-input2d-nn4x3.html)

--

## Toy Transformer (No ReLU)

- Single transformer block
- ReLU not needed since Attention is All You Need
- 2D input treated as sequences
- Straight and hard creases -> smooth curls

[Play!](viz/10-input2d-transformer1.html)

--

## Deeper Transformer

- 5 Transformer blocks
- Lots of knobs to tune
- Very expressive yet also very inhibitive folds
- Can construct sparsely localized fine 2D structures

[Play!](viz/11-input2d-transformer4.html)

---

## ChatGPT as Curve Growth

- 3D word embedding:
    - a word is represented by a point (3 numbers)
    - A curve is a string of words
- An LLM is used to "grow" the curve:
    - The initial curve is your prompt
    - curve is grown by iteratively adding 1 more point to the curve (autoregressive inference)
    - The "grown" part of the curve is ChatGPT's response
- Curve's growth is guided by wrinkles on a high dimensional NN "origami"

[Play!](viz/12-autoregressive3d.html)

--

## ChatGPT as Stochastic Curve Growth

- Next word prediction is typically stochastic
- The growth of the curve is also random

[Play!](viz/13-stochastic-autoregressive3d.html) 