---
layout: post
title: "Zeta Functions"
date: 2018-09-17
---

The most basic incarnation of the Riemann zeta function is the infinite series
$$\zeta(s) = \sum_{n = 1}^{\infty}n^{-s},$$  
where \( s \) is a complex number.
It is often an exercise near the end of a first class in Complex Analysis to show the following identity
$$\sum_{n = 1}^{\infty} n^{-2} = \frac{\pi^{2}}{6}.$$

We run into a problem, because this function is only defined when the real part of \(s \) is greater than 1.
This is denoted by \( \operatorname{Re}(s) > 1\).
There is a theorem that gives a hint that we may be able to define \(\zeta(s)\) for almost all complex numbers (there will always be a pole at \(s = 1\)).
The theorem states that if two functions agree on an open set, then they agree wherever the two functions are defined.
If our functions have the same values on a grain of rice, then they have the same value all over the world.

Now, the problem is finding out if there are any functions that allow us to extend the Riemann zeta function.
Thankfully, there is a method to determine this function.
That method is called the Mellin transform.

The Mellin transform is an example of an integral transform and is related to the Fourier transform.
We won't go into details, but the Mellin transform sends complex-valued functions to complex valued functions.
This gives us the completed zeta function, whose values when the real part of s is greater than 1 is given by
$$Z(s) = \pi^{-s/2} \Gamma(s/2) \zeta(s).$$
Here, the Gamma function is defined by an integral equation:
$$\Gamma(s) = \int_{0}^{\infty} \, e^{-y} y^{s} \frac{dy}{y}.$$

We can now determine the values of the zeta function at values where the real part of \( s\) is less than 1 via the following functional equation:
$$Z(s) = Z(1-s).$$
Now that we can evaluate at negative integers, we make an interesting discovery:  \(zeta(1-k)\) is a rational number when \(k\) is a non-negative integer.
Finally, we are led to some amazing congruence conditions called **Kummer's Congruences**.

There is much more to the Riemann zeta function and the numerous generalizations.  For more information see:
Chapter 7 of _Algebraic Number Theory_ by J&#252;rgen Neukirch and Chapter 5 of _Introduction to Cyclotomic Fields, 2nd Edition_ by Lawrence C. Washington.
