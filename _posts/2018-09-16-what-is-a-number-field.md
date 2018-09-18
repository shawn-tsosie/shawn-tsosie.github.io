---
layout: post
title: "What is a Number Field?"
date: 2018-09-16
---

Pierre de Fermat was one of the premier mathematicians of his time, despite being a lawyer.
His most famous result was not actually a result, but a conjecture: Fermat's Last Theorem (eventually proven by Andrew Wiles in 1994).
Fermat's Last Theorem asserts that the equation a<sup>n</sup> + b<sup>n</sup> = c<sup>n</sup> has no integer solutions if n &#8805; 3.
This equation seems simple and even Fermat thought he had a solution at one time.
Although, it's likely he realized there was an error, because the proof was never mentioned outside the margins of one of his books.

In the 19th century, Ernst Kummer attempted to solve the problem.
He had two ideas on how to tackle the problem.
The first is that over the complex numbers, the equation a<sup>n</sup> + b<sup>n</sup> can be factored into n linear factors.
The second is that the prime factors dividing the right-hand side of the equation must divide the left-hand side of the equation.
This is a result of unique factorization.
There was a problem:  unique factorization did not work in the way he thought it would.

We should step back a moment here.
Why Kummer thought he could factor a<sup>n</sup> + b<sup>n</sup> is because he was working over a number field.
A number field is a finite extension of the rational numbers.
Ok, we need to step back once more.
An extension of the rational numbers occurs when we adjoin a root of a polynomial to the equation.
A nice result is that this turns our extension into a vector space over the rational numbers.
This means that we can talk about dimension and a finite extension just means that our extension has finite dimension.

Kummer realized his error.
Through his studies he discovered what are known as rings of integers and ideal elements.
A marvelous result is that although number fields do not have unique factorization over the elements, they do have unique factorization over the ideals.

This insight led to the rich theory of algebraic number theory.
Kummer's work would also lead eventually to the development of Iwasawa Theory by Kenkichi Iwasawa.
Other work on Fermat's Last Theorem would lead to intense development of arithmetic geometry, elliptic curves, and modular forms.

Much of the history I mentioned comes from the excellent book _Introduction to Cyclotomic Fields, 2nd Edition_ by Lawrence C. Washington.
