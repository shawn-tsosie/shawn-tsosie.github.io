---
layout: post
title: "Linear Regression Part 1"
date: 2019-01-08
---

This will be a series of three posts.
The first post will cover the idea behind linear regression (at least my
interpretation of it).
The second will cover the theory behind linear regression and some
refinements.
The final post will give some python implementation for linear regression and
its variants.

# The Idea

Suppose that we have a large number of points (any kind of numerical data will
work).
We either know or suspect that there is some predictable or function generating
these points.
What we would like to do is determine what form this function takes.
For example, suppose that we have the average housing price per year for the
last several years.
We want to predict what the prices will be next year.
How would we do that?

One way is to begin by making the assumption that the predictive function is as
simple as possible.
So, we would use the simplest function that we know of: a line.
As a line is defined by several parameters, this begs the question: how do we
pick the best line?

We want a line that is as 'close' as to all of the points as possible.
Again, we run into a problem: what do we mean by 'close'?

Usually, when we think of numerical data, we think of it as living in some higher-dimensional space, which is usually referred to as __Euclidean Space__.
In Euclidean space, closeness is defined by the square-root of the sum of
squares, called the __Euclidean norm__ or just __norm__.

We can now make our idea of choosing the best line by choosing the line closest
to all of the points simultaneously.
We can now work on figuring out how to make the line close.
The closeness of a line can be thought of as a function of the parameters that
define a line.
We will call this function $J$ and we will denote the parameters by ${\bf a}$.
This function $J({\bf a})$ is often called an __objective function__ and a
sizable portion of machine learning is concerned with minimizing objective
functions.

There are explicit solutions to determining the **$a$** that minimizes $J$, but
these solutions involve calculating the inverse of a matrix.
This is fine for small examples, but when our data has an incredibly large
number of points, then this becomes computationally expensive.
We need a different method and that method is called __gradient descent__.

The gradient tells us which direction the steepest slope of the function lies.
We wish to minimize the function above, so we go in the opposite direction to
obtain a smaller value of $J$.
We calculate the gradient again and then step again.
We repeat this as many times as we desire.

We will make this more explicit, but first, we'll look at a toy example.
Hopefully this will clarify the preceding discussion.

# A Toy Example

Suppose that we have the following five points:
$$
(4, 6), (1, 1), (6, 5), (8, 7), (2, 2).
$$
We want to find $a$ and $b$ such that $y = ax + b$ fits the line as closely as
possible.
In practice, this means that we want to minimize the following function:
$$
J(a, b) = \frac{1}{10}\sqrt{(6 - 4a - b)^2 + (1 - a - b)^2 + (5 - 6a - b)^2 + (7 - 8a - b)^2 + (2 - 2a - b)^2}
$$

If we apply the theory from the following section, the $a$ and $b$ that
minimize the function $J(a, b)$ above will be $a = 0.817$ and $b = 0.768$
(rounded to 3 decimal places).
This gives us the following line:
$$
y = 0.817x + 0.768.
$$

All of this is visualized in the following picture:
![Linear Regression Toy Example](/_images/2019-01-08-linear-regression.png)
