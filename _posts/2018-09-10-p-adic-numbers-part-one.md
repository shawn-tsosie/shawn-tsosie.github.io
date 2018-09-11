---
layout: post
title: "p-adic Numbers Part One"
date: 2018-09-10
---

One of the first major theorems learned in elementary number theory is the Fundamental Theorem of Arithmetic. The theorem states that every positive number can be factored uniquely, up to rearrangement of factors. Well, what does that even mean?

Let's take a step back. We start with the concept of divisibility. We say a divides b if we can write b = ac, where c is an integer (the integer requirement is important). For example, 5 divides 10, because 10 = 5 * 2.

There are some numbers that are unique and they end up being the basic building blocks of all numbers. We find that there are some numbers that are only divisible by themselves and 1. These numbers are called prime numbers.

One of the earliest theorems, attributed to Euclid, states that there are infinitely many primes. This is bad and good. Bad, because to understand the natural numbers, we have to understand an infinitely large set. Good, because to understand the natural numbers, we have to understand an infinitely large set.

To put it another way, we have to put in a lot of work to understand the natural numbers. But, this opens up the possibility of a rich theory. We will find that the theory is vast and (depending on your personality) beautiful.

Back to prime numbers. We have infinitely many of them and we also know that every integer is a unique product of them. We also know a little bit about divisibility. 

One major object of study for mathematics is polynomials. If we wish to study the integral solutions of polynomials, then we are led to modular arithmetic. The primary reason is that if a polynomial lacks a solution modulo a number then it lacks a solution within the integers. 

Modular arithmetic is commonly referred to as clock arithmetic, because clock arithmetic is the most readily available example of modular arithmetic. If we are given three numbers, say 1, 13, and 12. Then 13 &#8801; 1 modulo 12, because 13 - 1 = 12 and 12 is divisible by 12. Put another way, 13 hours beyond noon or midnight is 1 am or 1 pm.

There is a wonderful theorem that allows us to just consider the modular solutions for just prime numbers and powers of prime numbers (for example we just have to consider a solution modulo 3, 9, 27, etc.). This theorem is called the Chinese Remainder Theorem. It gets its name from a Chinese general who used it to quickly count how many soldiers were left in his army after a battle. The general would tell his soldiers to arrange themselves in columns of 3 and he noted the remainder. Then he ordered his soldiers to arrange themselves in columns of 5 and he noted the remainder. He kept going for a few more columns and then used the theorem to obtain an accurate count of his soldiers. (This is easier than aranging them in multiples if you have an incredibly large amount of disciplined soldiers.)

Much later, Kurt Hensel studied the modular solutions of polynomials and was led to a famous theorem that now bears his name: Hensel's Lemma. His lemma tells us that under certain conditions if we have a solution modulo a prime p, then we also have a solution modulo p<sup>2</sup> and p</sup>3</sup>, etc. What's more the solution modulo higher powers of the prime p were consistent with the solutions of the other powers of the prime p.

If you take all the solutions, then there is a limiting process involved. This limiting process just says that higher and higher powers of the prime p divide some of the solutions. So, you can bundle all of the solutions together and obtain a new number. This number is called a p-adic number.

As an example, -1 is always a p-adic number. If we look at it as a 3-adic number, then it is 2 + 2 * 3 + 2 * 3<sup>2</sup> + 2 * 3<sup>3</sup> + ... It looks remarkably different! There are analogies between the integers and polynomials and p-adic numbers and power series, but that will have to wait for another day.
