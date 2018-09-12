---
layout: post
title: "p-adic Numbers Part Two"
date: 2018-09-11
---

We mentioned that there was an analogy between polynomials and powers series and integers and p-adic numbers. At first blush, this is a surprising idea. Yet, it is a powerful idea that can lead into powerful ideas in arithmetic geometry.

Before we get into that, we must introduce the idea of topology. Put succinctly, topology is the study of how close mathematical objects are to each other and the functions that preserve this closeness. In everyday life, you would say you are close to something if there is a small distance between the objects. There are more exotic notions of closeness.

We can say that two polynomials in x are close to each other if the difference between them is a high power of x. For example, suppose that we have the three polynomials p<sub>1</sub> = x<sup>5</sup> + 3 * x<sup>2</sup> + 2, p<sub>2</sub> = x<sup>3</sup> + 3 * x<sup>2</sup> + 2, and p<sub>3</sub> = 3 * x<sup>2</sup> + 2. Then p<sub>1</sub> is closer to p<sub>3</sub> than p<sub>2</sub>, because p<sub>1</sub> - p<sub>3</sub> = x<sup>5</sup> and p<sub>2</sub> - p<sub>3</sub> = x<sup>3</sup>. We have a notion of distance among polynomials.

When you have a notion of distance, then there is a process called completion. What this does is fill in the gaps. In our case, there are gaps between any two polynomials. To return to a relatively more down to earth example, the real numbers are a completion of the rational numbers. One way to think about this is that we can approximate any real number to arbitrary precision with a rational number. In the case of polynomials, their completion is the set of power series.

We will take a short detour. In elementary number theory, there is a theorem called the Basis Representation Theorem. The theorem tells us that if we are given any positive integer, then we can write any number as a sum of powers and fixed integers uniquely. Everyone is familiar with one example of this and that is decimal numbers. The number 4,382 = 4 * 10<sup>3</sup> + 3 * 10<sup>2</sup> + 8 * 10<sup>1</sup> + 2 * 10<sup>0</sup>. The Basis Representation Theorem says that the 4, 3, 8, and 2 are their corresponding powers of 10 are unique.

If we squint at 4 * 10<sup>3</sup> + 3 * 10<sup>2</sup> + 8 * 10<sup>1</sup> + 2 * 10<sup>0</sup>, we might notice that it looks somewhat like a polynomial. It is like a polynomial in the sense that a polynomial in terms of x tells us how many zeroes the polynomial has at x = 0. If we choose a prime, then the Basis Representation Theorem gives us a good way to determine how divisible by a prime p a number is. If you continue this analogy you are led to arithmetic geometry.

We are not concerned with arithmetic geometry today. But, in terms of what we are concerned with, what pops out of this construction is that the p-adic numbers are the completion of the integers when our closeness is based on how divisible a number is by a prime p.
