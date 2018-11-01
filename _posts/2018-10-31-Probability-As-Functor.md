---
layout: post
title: "Probability as a Functor"
date: 2018-10-31
---

When we think about topologies, rings, groups, algebras, or any other
mathematical object (here, we are using object in a non-mathematical sense) we
naturally focus on the elements. So, we think primarily about the open sets and
specific open sets for a topology, an element of a ring, group or algebra.
This is a good way to think about mathematical objects, but in some sense it is
only half the picture. Further, if we only think about the elements or specific
rings or topologies, then we are missing out on important mathematical tools.

What is another way to think about mathematical objects? The other fundamental
idea that goes with any mathematical object are the maps between those objects.
For topology, we have continuous maps; for rings, group, and algebras, we have
ring homomorphisms, group homomorphisms, and algebra homomorphisms,
respectively.

To cement these ideas, we will talk about what a category is, how a poset is a
category, what a functor is, what a probability measure is, and finally, how a
probability measure can be thought of as a functor.

The idea that encapsulates this focus on morphisms is called a **category**. A
**category** consists of the following information:
* a set $\text{Ob}(\mathcal{C})$ whose elements are called **objects**,
* every $X, Y \in \text{Ob}(\mathcal{C})$ has an associated set denoted by
  $\text{Hom}\_{\mathcal{C}}(X, Y)$ called the **morphisms** from $X$ to $Y$,
* every $X, Y, Z \in \text{Ob}(\mathcal{C})$ has a map called **composition**:
$$
\text{Hom}\_{\mathcal{C}}(X, Y) \times \text{Hom}\_{\mathcal{C}}(Y, Z) \to
\text{Hom}\_{\mathcal{C}}(X, Z).
$$
The objects and morphisms satisfy the following rules:
* the composition is function above is associated (that means we can compose
  multiple functions together),
* for every object $X$, there is a unique map called the **identity map** in
  $\text{Hom}\_{\mathcal{C}}(X, X)$, denoted by $I\_{X}$. Further, $I\_{X}$
satisfies the following: $I\_{X} \circ g = g$ and $f \circ I\_{X} = f$.

I have swept some details under the rug, but the interested reader should see
*Categories and Sheaves* by Masaki Kashiwara and Pierre Schapira. Any other
categorical information in these notes can be sourced from Kashiwara and
Schapira's book.

There are many categories in "nature", but without having prior knowledge, it
may be difficult to recognize them. One example, is the **poset**, a partially
ordered set. This is a set of elements $P$ along with a binary relation $\leq$  such that the elements satisfy the following properties:
* for every $a \in P$, $a \leq a$ (the reflexive property),
* if $a, b \in P$, $a \leq b$ and $b \leq a$, then $a = b$ (antisymmetry),
* if $a, b, c \in P$, $a \leq b$ and $b \leq c$, then $a \leq c$
  (transitivity).

We can actually think of a **poset** as a category. The objects are just the
elements of the set $P$ and the morphisms are defined in the following manner:
if $a \leq b$, then $\text{Hom}\_{P}(a, b)$ has one element in it, otherwise
it's empty. Through transitivity, we see that there is "function" composition
for posets. Further, since $a \leq a$ for any $a \in P$, $\text{Hom}\_{P}(a,
a)$ is nonempty and consists of a single element. Thus, we denote this element
as our identity. Checking this rigorously is a good exercise.

The main power of categories is the associated notion of a **functor**. It allows us to move between categories, while also allowing us to preserve structure
that we deem is important. Formally, if we have two categories, say
$\mathcal{C}$ and $\mathcal{D}$, then a functor $F$ consists of two pieces of
data:
* a map between the objects of $\mathcal{C}$ and $\mathcal{D}$,
* a collection of maps for every $X, Y \in \text{Ob}(\mathcal{C})$ of the form:
$$
F : \text{Hom}\_{\mathcal{C}}(X, Y) \to \text{Hom}\_{\mathcal{D}}(F(X), F(Y))
$$
such that the identities are preserved and compositions are preserved.

We now move onto what a **probability measure** is. A probability measure $P$
(we are overloading $P$, but we hope it is clear from context when we are
talking about a poset and a probability measure) is a function from a subset of the power set of a some set $\Omega$, which we denote by $\mathcal{F}$ (we note that this set satisfies some properties which we gloss over here), to the interval $[0,1]$, which satisfies the following:
* $0 \leq P(A) \leq 1$ for all $A \in \mathcal{F}$,
* $P(\emptyset) = 0$ and $P(\Omega) = 1$,
* for any disjoint sequence $A\_{1}, A\_{2}, \ldots \in \mathcal{F}$ such that
  $\cup A\_{k} \in \mathcal{F}$, then
$$
P(\cup A\_{k}) = \sum P(A\_{k}).
$$

We note that any subset of the power set is a poset, which is ordered by set
inclusion. Thus, $\mathcal{F}$ is a poset. Further, $[0,1]$ is a poset as well,
with the usual order. The set function $P$ is a **monotone** function, which
means that $P(A) \leq P(B)$ whenever $A \subset B$. So, $P$ sends an object of
$\mathcal{F}$ to an object of $[0,1]$. Further, the monotone property means
that we have a map from every set of morphisms of $\mathcal{F}$ to every set of
morphisms of $[0,1]$ (remember that we in this case a morphism is just an
element of the set $\text{Hom}\_{\mathcal{C}(X, Y)$, where $\mathcal{C}$ is a
poset category). Further, the composition preservation property just says that
if $A \subset B \subset C$, the $P(A) \leq P(B) \leq P(C)$.

Although this example may seem a bit artificial, it is a good way to gain
experience with categories and functors by working with relatively
down-to-earth mathematical objects.
