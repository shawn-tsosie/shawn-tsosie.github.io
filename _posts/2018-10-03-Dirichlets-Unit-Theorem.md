--
layout: post
title: "Dirichlet's Unit Theorem"
date: 2018-10-03
---

To understand the whole, it helps to understand the part.
So it is in algebraic number theory.
(We should always keep in mind that we are trying to understand the whole.)
One major goal in algebraic number theory is to understand the behavior of the prime ideals of the ring of integers of an algebraic number field.
You should think of these prime ideals as generalizations of prime numbers.

As an aside, many people take issue with the fact that we say a prime number is positive and it is only divisible by 1 and itself.
There is good reason to balk at this definition, because it is unnatural.
Unnatural here means that we are making arbitrary choices.
The prime ideal takes care of these arbitrary choices.

So, to move back to what we were talking about before, there are several constituents of an algebraic number field that come from the following exact sequence:
'\begin{equation}
1 '\to '\mathcal{O}_{K}^{'\ast} '\to K^{'\ast} '\to '\mathcal{J}_{K} '\to '\mathcal{Cl}_{K} '\to 1.
'\end{equation}
Here:
* $'\mathcal{O}_{K}^{'\ast}$ are the units of the rings of integers of $K$;
* $K^{'\ast}$ is $K$ with the $0$ element removed;
* $'\mathcal{J}_{K}$ is the set of all fractional ideals of $K$;
* $'\mathcal{Cl}_{K}$ is class group of $K$.

We will leave all of these as black boxes, except $'\mathcal{O}_{K}^{'\ast}$.
It isn't too important to know what an exact sequence is, but it helps to think of them as some kind of generalization of a subspace decomposition of a vector space.

The ring of integers $'\mathcal{O}_{K}$ is the set of elements $\alpha$, which we call *algebraic integers*, such that $\alpha$ is the root of a polynomial whose coefficients are all integers and whose leading coefficient is 1.
The set of units $'\mathcal{O}_{K}^{'\ast}$ is a subset of $'\mathcal{O}_{K}$ such that $'\alpha$ is a unit if and only if there exists an algebraic integer $'\beta$ such that $'\alpha \beta = 1$.

The first thing we note is that $'\mathcal{O}_{K}^{'\ast}$ is an abelian group.
From elementary group theory, we have the structure theorem of abelian groups that says that every finitely generated abelian group is isomorphic to the direct sum of a finite group and $'\mathbb{Z}^{n}$, where $n$ is some integer.
For details, you can see Theorem 14.7.3 in Artin's _Algebra, 2nd edition_ or Theorem 1.8.5 in Lang's _Algebra, 3rd edition_.

This means that finitely generated abelian groups have a structure that is well-understood.
AS $'\mathcal{O}_{K}$ is an abelian group, it would be nice if it was also finitely generated.
This is part of what *Dirichlet's Unit Theorem* says.
Specifically, $'\mathcal{O}_{K}^{'\ast} '\cong '\text{finite} '\oplus '\mathbb{Z}^{n}$.
But, Dirichlet's Unit Theorem gives us more.
It tells us precisely the value of $n$.
If $r$ is the number of real embeddings of $K$ and $s$ is the number of pairs of complex embeddings of $K$, then $n = r + s - 1$.

So, we are in some small way further along in our goal of understanding algebraic number fields and their prime ideals.
In the future, we'll try to discuss the ideas behind the proof of Dirichlet's Unit Theorem.
