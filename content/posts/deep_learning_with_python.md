+++
title = "Deep Learning with Python"
date = 2019-12-06T20:45:13Z
draft = false
tags = ["Book review"]
+++

{{< figure src="/images/book_deep_learning_with_python.jpg"  class="sml" width="50">}}

Book by the author of Keras, F. Chollet about what is deep learning how to apply it to common tasks. Very well written and easy to follow, it focuses on practical teaching rather than theory. I read it two years ago and as the field is moving very fast content is a bit dated, best to wait for the second edition in Q2 2020.

<kbd>95%</kbd>

<!--more-->

***

* Intro
  * in 2016 Deep Learning replaces Support Vector Machines and other methods for most problems
  * Deep Learning need nearly no feature engineering anymore
  * Now competitions on Kaggle are won with Deep Learning for perception and XGB for organised data

* Basics
  * Gradient is derivative for multi-dimensions functions
  * Dimensions are often 2D ( ID, Features), 4D for images (ID, H, W, channels), 5D for video (ID, H, W, channels, frame)
  * Learning Back propagation by hand useless now that TensorFlow can do formal computation of gradient function directly
  * Main goal is to minimize Loss function by using an optimizer. For each mini-batch Loss optimizer compute new weights based on current Loss.
  * MNIST can be solved in 10 lines to a 97% accuracy!

  * Type of layers to use
    * Dense - fully connected
    * Sequence - recurrent, LSTM
    * Image - convolution

  * Model is usually represented by acyclic graph
  * Normalize test data with training data values to avoid spilling information
  * Small dataset --> Use (iterated) K-fold validation

* Fundamentals of ML
  * Supervised learning
    * Most prevalent for now
    * Given a set of input/output predict new output with new inputs
    * Need big annotated datasets
    * Where DL shines the most

  * Unsupervised learning
    * Given a set of data, find what is interesting
    * Butter and bread of analytics
    * Dimensionality reduction and clustering often used

  * Self-supervised learning
    * Special type of supervised whereby label are generated with heuristics
    * Autoencoders
    * E.g. predicting next frame in a video, next word in a sequence

  * Reinforcement learning
    * Agent-based
    * Actions lead to environment changes
    * Reward function judge changes
    * Agent optimize to get best reward
    * E.g. Model beating video games

* How-to
  * Define the problem
  * Define the metric to optimize
  * Define an evaluation protocol
  * Prepare Data
  * Pick a base model architecture that does better than baseline e.g. random
  * Make the model overfit
  * Regularize (L1, L2, dropout) and tune hyperparameters
  * Maybe try other model architectures

* Computer Vision
  * Skipped as nothing new on CN for me

* Text and sequences
  * 1D CNN when order does not matter, e.g. translation
  * RNN when order matters e.g. time series analysis
  * Bag of words and n-gram only for shallow networks
  * DL and its multi-layers can learn long sequences without a need for feature engineering
  * Using pre-trained embedding for text is rarely a good idea
  * Word embeddings 
    * (256, 512, 1024) are a way to condense one-hot (20k+)
    * Need to be learned from data with aim that distance between words is representative of closeness of meaning
    * Very hard to find universal one, Word2vec is OK, best to compute a new embedding for each problem

* Functional API
  * Enable more topologies such as multiple inputs, outputs, residual, inception type networks…
  * Only requirements is to create Directed acyclic graphs (DAGs)
  * Residual help fighting vanishing gradients and representational bottlenecks

* Advanced ML
  * Callback to print status, early stopping, changing optimizer parameters during training…
  * Tensor Board to visualize model performances in details
  * Batch normalization  ensure data is mean 0 and variance 1, important as usually done on input data but no sure after layers --> Layers.BatchNorm(a), a=1 except for conv2D channel first where a=-1
  * New approach using selu and lecun_rand for self-normalizing NN, only working on Dense so far
  * Move towards Separable conv2d as cheaper and as good as conv2d, base for Xception model
  * Hyper-parameters space is discrete, so it is hard to find a good way to tune them, Hyperas and Hyperopt for Python can help

* Ensembling
  * Always better, especially with model of different approach as capture different part of the latent information
  * Use weighted averages vs. accuracy, can use Nelder-Mead optimisation to choose weights.
  * DNN + Trees (Random forest or gradient boost) is great combination of Deep + Wide

* Trees
  * Works best on structured data
  * Random forests --> ensemble of uncorrelated weak predictor gives strong predictor, works by sampling input data  e.g. [1,2,3,3,4,5,5] and [1,2,2,2,4,5] and randomizing features that tree can choose from
  * Gradient boost --> start with tree, then compute loss and gradients, add second tree and so on, until happy with results.

* Libraries for Kaggle, the simpler the winner
  * Keras now 40%
  * lightGBM by MSFT leaf-based addition, faster than XGB?
  * XGBoost, level-based additions
  * TensorFlow

* Generative approaches
  * Text generation
    * Reuse sequence model, give softmax of all output but we want to control randomness temperature to go from random to predictible
    * Build network with its input the first part of a sequence and its output the other part

  * Style transfer
    * 3 different loss with weighted average
    * Use optimisation over the pixel to iterate over input and change output
    * DNN is used to compute loss here
    * Good result when style is space-invariant and input simple shape
    * Ultimately, one could generate lots of good examples and learn the functions as a filter with a fairly simple CNN

  * Deep Dreams
    * Same idea than style transfer but for style running a CNN backward to see how to maximize activations on what has been learned before such as cats, dogs, building and anything in ImageNet

  * VAE
    * Describe latent space based on some input
    * Then give new input and generate output for space described
    * Tend to work best when axis are well-defined parameters, continuity of change along them
    * Basic encoder-decoder does not lead to interesting results, working on distributions instead
    * VAE ensure input sample of distribution with same mean and variance learned. The decoder then sample the distribution to get output
    * Out = mean + small_epsilon * exp(log var)

  * GAN
    * Similar base idea than VAE
    * Much more unpredictable output than VAE, no continuous structure of latent space!
    * Use of generators
    * Notoriously hard to train
    * Generator and discriminator battling, not optimal solution but an equilibrium
    * Lots of gotchas, see code in book e.g. learning rate decay, gradient clipping

* Future of DL
  * DNN can only do very local generalization for now
  * DNN often started from scratch, will become part of program
  * Merging of DNN and program synthesizer, with use of non-differentiable networks with loops
  * Algo (formal, reasoning) vs. Geometric (informal, pattern matching) modules
  * Extreme generalization: learn from very little or no data at all, like human
  * How to progress: arxiv, kaggle, practice, practice, practice