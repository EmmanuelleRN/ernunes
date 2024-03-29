---
title: Basic Statistics - Part 2
author: Emmanuelle R. Nunes
date: '2021-09-16'
slug: basic-statistics-part-2
categories: 
  - Statistics
  - R
  - Analysis
tags: 
  - introduction
  - statistics
  - R
  - correlation
  - bidimensional analysis
subtitle: ''
summary: ''
authors: []
lastmod: '2021-09-16T19:03:29+01:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---




## Bidimensional Analysis

Previously we talked about understanding the distribution of a single variable, i.e., to get a summary of the data set. Still, frequently we are interested in understanding how two or more variables behave together.

When interested in two variables, we can have three scenarios:

* Both variables are qualitative
  * Data is summarised as a **contingency table**
* Both variables are quantitative
  * Analysis based on scatterplots and **correlation**
* One variable is qualitative, and the other one is quantitative
  * Analysis can be based on boxplots

In the end, in every situation, our aim is to find possible relationships and associations between any two variables that can be found through charts or metrics.

We can think about **association** as a ‘change in opinion’ about the behaviour of a variable in the presence (or not) of another variable. For example, if we ask ourselves, ‘Is there an association between height and sex in a particular community?’ To answer that, we can think about ‘what is the expected frequency of males above, for example, 170cm?’, we also need to think about ‘what is the expected frequency of females above 170cm?’ If the answer to both questions is approximately the same, there is no association between height and sex. Still, if the answers differ, there is likely an association between those two variables, and we need to incorporate this to better understand them.

### Association between quantitative variables

To understand the association between two quantitative variables, we can use *scatterplots*. For example, the following data set shows us the years in service and the number of clients of different insurance agents.


```r
insurance <- data.frame(agency = c(LETTERS[1:6]),
                        years_in_service = c(2, 4, 5, 10, 12, 15),
                        clients = c(40, 52, 60, 70, 71, 88))

insurance %>% 
  knitr::kable()
```



|agency | years_in_service| clients|
|:------|----------------:|-------:|
|A      |                2|      40|
|B      |                4|      52|
|C      |                5|      60|
|D      |               10|      70|
|E      |               12|      71|
|F      |               15|      88|

We can create a scatterplot to better understand the relationship of the variables. As suspected, the more years in service and agency has, the more clients it has, so the chart shows us a positive association between both variables.


```r
insurance %>%
  ggplot(aes(x = years_in_service, y = clients)) +
  geom_point()
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-3-1.png" width="672" />

We can have 3 types of association between two variables: 

<img src="https://statistics.laerd.com/statistical-guides/img/pearson-1-small.png"/>

1. Positive association
2. Negative association
3. No association

We can numerically measure the association between two variables by calculating their correlation.

`$$corr(X, Y) = \frac{\sum{x_iy_i - n\bar{x}\bar{y}}}{\sqrt{(\sum{x_i^2 - n\bar{x}^2})(\sum{y_i^2 - n\bar{y}^2})}},$$`

where `\(-1 \leq corr(X, Y) \leq 1\)`.

The closer to -1, the stronger is the negative correlation between two variables; the closer to 1, the stronger is the positive correlation; and if corr = 0, then there is no correlation between the variables.
