+++
title = "The Pragmatic Programmer"
date = 2019-04-13T13:21:30+01:00
draft = false
tags = ["Book review"]
+++

{{< figure src="/images/book_pragmatic_programmer.jpg"  class="sml" width="50">}}

Book by Andy Hunt and Dave Thomas about programming written in 1999 and part of the classics of CS. It contains some good ideas, some obvious and some outdated. Overall very good, no ground-breaking but good reminder to focus on value and quality.

<kbd>76%</kbd>

<!--more-->

***

* Keizen
	* Japanese word to describe the small but regular step taken towards improving that yield great results in the long term
	
* DRY
	* Don't repeat yourself
	* One piece of data should only be declared once
	* If not practical in code, can have script to extract data from XML/JSON/TXT and populate code structures rather than copy and risk having several unlinked representations that break when the code change
	* ME --> Opposite could be WET: Write Everything Twice

* Pub/Sub
	* Push/Pull to keep modules decoupled
	* One step further is to create a blackboard of data
	
* Design
	* User centered
	* Work with user, e.g. shadowing, to understand user
	* Requirements are use cases not architecture or design
	* No tracking of requirements changes is needed, just list of current ones
	
* Automate
	* Everything
	* Reduce time and errors, replicability needs it
	* Build
	* Test
	* Dev environment
	* Release builds
	* Backups
	
* Test
	* State coverage and not code coverage
	* Include GUI, usability and performance
	* Define baseline metrics to compare against
	* Find bugs once
	
* Documentation
	* Doc and code are two views of the same model
	
* Expectations
	* Gently exceed user expectations
	
* Stance
	* Sign your work and be proud

* Architecture
	* Hexagonal, ports/adapters
	* Orthogonal
	* Modular
	* Required for any piece of code that aim as work in the long term
	
* Editors
	* Learn productivity shortcuts make coding much more efficient
	* Copy/paste by manually moving the mouse is very inefficient
	* Writing boiler plate code is also a waste of time and source of errors
	* Less is more!
	* ME --> Aim to be proficient at VSCode
	
* Contract
	* Contract driver coding, CDC
	* Write some pre and post condition for all code blocks
	* Preconditions, post conditions, side effects, errors, everything clearly defined
	* Code fails hard if contract not respected
	* Link with striving for formal specifications
	* E.g. setFont(F) + post condition GetFont() == F
	* E.g. when having derived class, how to enforce overriding produce equivalent methods?
    * Prefer composition rather than inheritance