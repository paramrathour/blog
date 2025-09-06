---
title: Philosophy of Artificial Intelligence
description: 
categories: [Philosophy]
tags: [philosophy, computer-science]
math: true
---

With the advent of ChatGPT, Artificial Intelligence (AI) has become a household name. As AI becomes more and more deeply integrated with humans and their everyday life, it raises many questions about its working and usability. Here are my takes on it. 
## What is AI?
Firstly, what even is AI, according to wikipedia, AI is an umbrella term which refers to computational systems capable to perform tasks typically associated with human intelligence, such as learning, reasoning, problem-solving, perception, and decision-making.[^aidefinition] As you can see, this is a very wide definition and more often than not, it results in people misunderstanding the conversations when AI is involved. So before we get started, let's see some examples of AI, from the very basic to the advanced.
### Linear Regression
![](/linear-regression-light.svg){: .light }
![](/linear-regression-dark.svg){: .dark }
_$$y=3x/20 + 5 + \mathcal{N}(0, 1.5^2)$$ ([Image](https://commons.wikimedia.org/wiki/File:Linear_regression.svg) by Sewaqu licensed under Public Domain)_
Linear Regression is a simple way to estimate the relationship between two variables. In its purest form, we have a dependent variable $$y$$, an independent variable $$x$$, and the goal is to find the "best-fit" for the relationship between these two variables. 
In the above image, the blue dots represent our samples $$(x_1, y_1),\ldots,(x_n, y_n)$$, which are sometimes called the _dataset_ and the red line represents the best-fit. To find the line, we find its slope $$(m)$$ and $$y$$-intercept $$(c)$$ such that the estimate $$\hat{y}=mx+c$$ is "close" to our original samples. In formal terms, we solve the below optimisation problem which minimises the _mean squared deviation_ as shown below,

$$\displaystyle\min_{m,c\in \mathbb{R}}\frac{1}{n}\sum_{i=1}^{n}(y-\hat{y})^2 \equiv \min_{m,c\in \mathbb{R}}\frac{1}{n}\sum_{i=1}^{n}(y-(mx+c))^2 $$

### Principal Component Analysis

### Compressed Sensing
### Deep Learning

### Reinforcement Learning
### Generalised Linear Model

## What does AI do?
### Epicycles connection

## Why is it hard?
### Nonlinearity
richness
### Explainability

## How does AI gets it power
## What can AI do?
### Chess/Go

## Thought Experiments
### Classification Formula
### 

## Footnotes
[^aidefinition]: [Artificial Intelligence -- Wikipedia]({{ site.url_prefixes.wikipedia }}/Artificial_intelligence)
