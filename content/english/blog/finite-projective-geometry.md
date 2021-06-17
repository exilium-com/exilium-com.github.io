---
title: Finite Projective Geometry
date: 2021-05-22
author: Warped Pixel    # author should exist in the author folder
image: images/blog/fano-plane.png
# image_webp: images/blog/generic.webp
description : "Quick introduction to Finite Projective Geometry, which is a useful combinatorics tool"
categories:
  - Games
  - Math
hasMath: true # define this to be able to use math typesetting between $ $ or $$ $$
draft: true
---

# Finite Projective Geometry

I studied abstract algebra and abstract geometry in college. Even though I did well, it really felt pretty, well, abstract. Probably because it is. These things have similar concepts to what you already understand: zero, addition, lines, intersections, etc. But they do not follow all the rules you know, from grade school algebra and real-world geometry of tangible objects. Breaking those rules is *precisely* what makes these abstractions interesting. I didn't really appreciate it at the time, they seemed just like formal ways to distill properties of familiar mathematical entities into their basic ingredients, and reconstruct them into something else.

Group theory can be used to model things like cryptographic key exchanges and the space of solutions to the Rubik's Cube. They *look* like regular algebra but are more general and once you map an existing problem to an abstract algebra you can leverage all the properties of these algebras to your existing problem.

Taking a pragmatic approach, you just need to go deep into the math you need to model your existing problem. Of course, the hard part is knowing which part of math that is! At least without understanding the full range, for that, it is valuable to read an introductory text in Combinatorics and Finite/Discrete Projective Geometry.

## What is Projective Geometry?

Projective Geometry is a geometry where the properties are invariant with projective transformations. In other words, a set of rules and concepts for constructs like points and lines that hold true as they are projected. This is a general concept, not a specific geometry. We know that regular, real-world geometry (what you learn in high-school, technically Euclidean geometry) is *not* projective: a typical perspective drawing shows that projections do not preserve angles or distances. But some concepts can be carried over.

A **Finite Projective Geometry** is one that has a finite number of points and lines, unlike the infinite number of points in Euclidean geometry.

The key structure for us is a Finite Projective Plane. It is the equivalent of a plane, in a Finite Projective Geometry. It can be defined by a few axiomatic properties:

1. Any two lines $L$ and $M$ intersect at exactly one point $P$. This is true for *all* lines. Clearly that is not true in Euclidean Geometry for parallel lines. Ok, so we're not in Kansas anymore.
2. For two distinct points on a plane, there is exactly one line containing both points.
3. There is at least one line on a plane, and each line has at least three points of the plane.
4. All the points of the plane do not belong to the same line

## The Fano Plane

The Fano Plane is the smallest Finite Projective Plane. It is often represented by the pictured diagram below. Let's look at each of the numbered properties above, do each of them hold for the pictured plane? It's quite simple to verify they do. Note that one of the lines is represented as a circle in the center of the picture. That's a line. It may not be straight, but nowhere in our geometry definition we said they had to be.

{{< figure src="/images/blog/fano-plane.png" title="Fano Plane" >}}

The existence of this plane with 7 points and 7 lines is evident, but determining whether a plane of a given dimension exists is actually a **very hard** problem. In fact it is an unsolved Mathematical problem for arbitrary sizes! This is a good topic for a future conversation.

## Some Historical Context

Mathematics may seem eternal, something that either the greek or the renascence scientists have figured all out. Fano after which the plane above is named, died in the 50's. The proof that no finite projective plane of order 10 exists was only done in the 90's, with brute force computer algorithms. The general problem of existence of finite projective plane of various sizes is still a conjecture, unproven by any modern mathematician or computer system.[^wolfram]

## Graphs and Incidence Matrix

## Future <!-- Duality: Cards, Symbols, Symbol sets, Lines, Points -->

## Duality

Now, a really cool property of Projective Geometries is that of *duality*: it basically means that points and lines are interchangeable in all properties and theorems. They are *dual* structures, if you replace all instances of point(s) by line(s) and all instances of line(s) by point(s), all relationships still hold just the same. Does it matter? In fact this symmetry is key to the problem we want to solve.

[^wolfram]: https://mathworld.wolfram.com/ProjectivePlane.html
