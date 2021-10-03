---
title: Random Variables
author: Emmanuelle R. Nunes
date: October 03 2021
slug: October 03 2021-random-variables
categories: 
  - Probability
  - Random Variables
  - Introduction
tags: 
  - Probability
  - Random Variables
  - Introduction
subtitle: ''
summary: ''
authors: []
lastmod: '2021-10-03T15:06:53+01:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

We talked before about probability using simple sample spaces, but in reality, we will map situations to probabilistic models that cater to all possible results. The variables to which we are going to construct probabilistic models are called **random variables**.

A random variable is a real-valued variable whose value is determined by an underlying random experiment. We usually show random variables by capital letters such as `\(X\)`, `\(Y\)`, and `\(Z\)`. Since a random variable is a function, we can talk about its range. The range of a random variable `\(X\)` is the set of possible values for `\(X\)`. 

## Discrete Random Variables

`\(X\)` is a discrete random variable, if its range is countable.

**Example:** Imagine that we extracted 2 balls without repositioning from an urn that initially contained 2 blue balls and 3 violet balls. Let’s define `\(X\)` as the number of violet balls obtained after both extractions. The following chart shows us the possible outcomes for `\(X\)`.

| Result | Probability | X |
| -- | -- | -- |
| BB | 1/10 | 0 |
| BV | 3/10 | 1 |
| VB | 3/10 | 1 |
| VV | 3/10 | 2 |

Each result of the experiment is associated with a value of `\(X\)`. Each of these results has a probability associated, which allow us to write the function (*x*, p(*x*)) that is a model for the distribution of `\(X\)`. The function (*x*, p(*x*)) is called **probability function** of `\(X\)`.

In the table below, we have the probability distribution of `\(X\)` for the example we just saw.

| x | p(x) |
| -- | -- | -- |
| 0 | 1/10 |
| 1 | 6/10 |
| 2 | 3/10|
