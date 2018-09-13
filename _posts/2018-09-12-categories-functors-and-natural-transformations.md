---
layout: post
title: "Categories, Functors, and Natural Transformations"
date: 2018-09-12
---

One of my favorite books on category theory is Saunders MacLane's _Categories for the Working Mathematician, 2nd Edition_.
Originally written in 1971 and revised in 1997, the book explains what a category is, how to use categories, and he has numerous down-to-earth examples (provided that you have an undergraduate education in mathematics).

My primary purpose in studying the book was to cover abelian categories.
Although, I had encountered categories before in an ad hoc manner, I still enjoyed reading the book.
I will go into a specific example that I enjoyed, but first, I'll try to introduce categories, functions, and natural transformations.
Or at the very least the idea of these.

A category is a collection of objects and morphisms.
The key idea behind categories is that while the objects are important, the most important thing is the morphisms between objects.
Often, categories are something we're familiar with. For example, the collection of vector spaces with the collection of linear transformations between them is an example of a category.
An example of a category that whose morphisms are not maps between the objects is the set of natural numbers.
We say there is a morphism between a natural number a and b if a &le; b.

Not that we have categories, we can talk about functors.
A functor can be thought of as a map between categories.
There are some technical considerations that we have to say to make this a sensible statement, but that is the idea behind it.

Why are we interested in functors?
We are not interested in all functors, but often the functors we are interested in preserve some essential characteristics.
For example, one class of functors that is useful is the homological functors.
These are functors from some category to an abelian category.
If our origin category is topological spaces and the target category is abelian groups, then the functor can tell us how many holes are in a surface.

Before we talk about natural transformations, we are going to make a short digression and talk about groups and groupoids.
A group is a set which has a rule that takes two elements of the set and gives you a third element of the set.
None of these elements have to be unique.

Further, there are some restrictions on the rule.
For one, if there are elements a, b, and c, then it does not matter if you put a and b into your rule first, then combine that result with c or if you combine a with the result of b and c.
This is called associativity.
Another rule is that there is one element, we denote by e, such that if you combine a and e or e and a, then you get back a.
This element is called the identity.
Finally, it says that if you have an element a, there is always an element b such that if you combine a and b, then you get back e.
We say that every element has an inverse.
Here, a is the inverse of b and b is the inverse of a.

An example is the integers with the rule being addition.
It has associativity, an identity (the identity is 0), and an inverse (if we take, say 3, then -3 is the inverse of 3).

In the category of groups, the morphisms are called homomorphisms.
The homomorphisms preserve the group structure.
The set of rational numbers where we exclude 0 is a group with the rule being multiplication.
There is a homomorphism from this set to itself if we send a rational number to its multiplicative inverse.
For example, we would send 2/3 to 3/2, 3 to 1/3, etc.

Now, a groupoid is any category whose morphisms form a group.
If we consider a groupoid with one object, then any functor is a homomorphism between the morphism groups.
The punchline is that you have a natural transformation between two functors if and only if you the functors are conjugate.
We say the elements a and b of a group are conjugate if there is a third element (not necessarily different from a and b) such that a = g * b * g<sup>-1</sup> (here g<sup>-1</sup> indicates the inverse of g).

Conjugation is an example of a group action and they are incredibly important in mathematics and are a useful tool.
The fact that conjugation is related to natural transformations gives us an indication from a higher level why it should be so important.

That is why I am fond of _Categories for the WOrking Mathematician_.
It gives concrete examples of abstract notions and it shows that important and familiar examples are important for a higher level reason.
Or that these abstract notions are actually useful, because they are important when our familiar examples are important.
