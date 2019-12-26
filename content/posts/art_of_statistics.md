+++
title = "The Art of Statistics"
date = 2019-12-26T22:23:16Z
draft = false
tags = ["Book review"]
+++

{{< figure src="/images/book_art_of_statistics.jpg"  class="sml" width="50">}}

Unfortunately, our brains have not yet adapted to our modern times, and probably never will. Our culture and livelihood are changing faster than the seasons and we need to make sense of our societies in order to understand where to go from here. Computers can crunch numbers ever so fast, and it is now down to the individual to know what to ask. This is where statistics come in handy, even if they are often portrayed as complex.

D. Spiegelhalter, statistician at Cambridge University, propose in the Art of Statistics a new approach firmly grounded in concrete examples and down-to-earth. Where there are numbers, events and probabilities statistics offer us invaluable tools to make sense of the situations and avoid fooling the easiest person to fool, ourselves.

I learned stats a few times, and do not use them often enough to keep it fresh in my mind. This time around, even if I did not learn new tools, I thought the approach was great, and the stories interesting enough to make it a great read.

<kbd>77%</kbd>

<!--more-->

***

* Basics about counting events and Randomized controlled trial
* Causality vs. causation
  * Causality --> relationship between cause and effect i.e. cause my be required
  * Causation --> process of cause to create effect i.e. cause required for effect to happen
* Regression to the mean: if some unlikely random value occurs and we take action. The next time the value is likely to be close to mean and we could wrongly interpret our action as cause for this.
* "All models are wrong, some are useful" - George Box
* ROC curve is sensitivity (% true positive) vs. specificity (% true negative)
  * Also need a calibration curve to see the situation
* Start with simple baseline in order to have a point of comparison when judging how good a model is
* Overfitting happens when model is too close to inputs --> regularization, split train/test
* Looking at different class of algorithms on a single problem can lead to different performance but can't tell why one algorithm better than another one, this could be called the Kaggle curse, winners tend to use overly complex models that are actually not useful in real life.
* Author makes point about biases issues that can come from many factors and algorithm can be opaque e.g. huskies detector was in fact detecting snowy backgrounds…
* Use of distributions can help reduce errors, test exist to know if assumed distribution is  OK to use
* 95% confidence interval does NOT mean a 95% probability that true value is in interval
* Central limit theorem --> mean and other basic statistics have normal distribution for large sample size
* Confidence interval help estimate residual random error by doing as if result is on sample of a theoretical population that does not in fact exist
* Bonferroni correction need to be used for multiple tests, divide p-value threshold by number of experiments
* Significance testing
* P-value is NOT probability is null being true!
* Things that go wrong in stats
  * Should not test until significance is attained
  * Exploratory (finding interesting hypothesis) vs. confirmatory (actually claiming findings by replicating earlier results) should be different tasks of novelty bias
  * Way to report important (10% lower PB with gene vs. 90% population at risk of high BP du to defect…)
  * Hard to avoid bad practices
    * 35% report unexpected results as predicted effects
    * 58% carry on collection data after significance test
    * 67% do not report all results
    * 94% do at least on the three above!
  * ME --> open data, open science, pre-registration, OSF
  * BEM + precognition great example of bad science
* Last chapter about good practices, check p-value distribution…
Mention new tool MRP Multi-level regression and post-signification --> small samples, many areas, between areas variability with hierarchical modelling, goof for polls estimations.
