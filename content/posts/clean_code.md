+++
title = "Clean code"
date = 2019-12-22T22:14:08Z
draft = false
tags = ["Book review"]
+++

{{< figure src="/images/book_clean_code.jpg"  class="sml" width="50">}}

I went through this book as other studied it as part of a regular meeting. Its tone is very similar to the pragmatic programmer and written in 2008 by an Extreme programming guru nicknamed Uncle Bob. While it contains lots of insights and tips and tricks about programming in general its tone is also quite dogmatic at times and even arbitrary when the author does not make a clear effort at explaining rational behind rules. The reader is left to blindly trust the guru or go and try it himself. In the end, this is probably the main point of the book, here is how I code after quite a big mileage. Here are the things to look for, smells, and some approaches I use when figuring out the best way to code. Now go coding and see how this pans out for you. To sum up, it is a refreshing book that gives good ideas about what to focus on when programming to hopefully progress towards writing better code faster; a must read for serious coders.

<kbd>76%</kbd>

<!--more-->

***

* Intro
  * Author Uncle Bob father-ish of SOLID principles
  * Only about object-oriented programming

* Punchlines
  * Read to write code ration is 10-to-1 so write readable code
  * Coding standards automatic in IDE i.e. format, lint, compiler rules
  * Classes should be smaller, lots of small drawer rather than three big ones
  * It is impossible to get good design first time, need multiple draft and iterative approach, even for good coders
  * Working code not enough, need to refactor further
  * Minimal comments, only docstrings for externally consumed API
  * Wrap 3rd party code to be independent, hide interface boundaries
  * Writing test for third party lib is good way to learn how to use it
  * Functions are less than 20 lines long, have less than 3 arguments and do one thing
    * Report.appendfoorter() better than appendFooter(report)

* List of Important code smells

  * Commented-out Code!
  * Comments
    * Inappropriate information
    * Obsolete
    * Redundant
  * Environment
    * Build require more than one step
    * Test require more than one step
  * Functions
    * Too many arguments
    * Output arguments
    * Flag arguments
    * Dead function
  * General
    * Obvious behaviour not implemented
    * Incorrect behaviour at the boundaries
    * Overridden safeties
    * Duplication
    * Base class depends on their derivatives
    * Too much information
    * Inconsistency
    * Artificial coupling
    * Selector arguments
    * Obscured Intent
    * Misplaced responsibility
    * Missing explanatory variables and intermediate values
    * Premature optimisation
    * Function name should say what they do
    * Polymorphism better than If-else and switch
    * Replace magic numbers with names constants
    * Structure over convention
    * Avoid negative conditional
    * Hidden temporal coupling
    * Keep configurable Data at high levels

* Concurrency
  * Server-side lock, not client-side!
  * Good way to avoid locks is to sort resources and always lock in order
  * Very hard to write tests and make them fail if conditions happen 1 in a trillion time as path of execution are many. One can use specialized tools and also run tests continuously.
