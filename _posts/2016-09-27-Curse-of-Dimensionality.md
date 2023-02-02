---
layout: post
title: The Curse of Dimensionality
---

Generalizing to higher dimensions is one area where mathematicians have usually excelled.  While others fear what they cannot visualize, 
mathematicians bravely add another coordinate or change a two to a three and BOOM! 

I've always been fascinated by proofs that *don't* generalize -- problems where we can perfectly characterize everything that is 
happening in two, three, or maybe even four dimensions, and after that [have no idea](https://en.wikipedia.org/wiki/Kissing_number_problem).  (Fermat's Last Theorem used to fall into this category.)

There's a parallel situation in statistics: sometimes methods that are powerful in low dimensions have much less predictive power in higher dimensional scenarios.  Statisticians call this phenomenon the curse of dimensionality, and they understand precisely why additional dimensions can make problems nearly unsolveable:  

Consider the following set-up. We are given a data set of m observations (x, y), where each x has n coordinates, each y has one coordinate, and m > n.  For simplicity's sake, suppose each coordinate of x is between 0 and 1, so each x lies in the n-dimensional hypercube of side length one. 

For a given n-dim x\* that lies in our hypercube, we wish to obtain a prediction for the corresponding y\*.  We do so by taking all the x's in our data set such that each coordinate value of x is within 0.1 of the corresponding coordinate value of x\*.  Call this set X\*. The idea is that average y value for all x's in X\* is probably a reasonable estimate for y\*.  This is called a nearest neighboor method. 

Note that the convex hull of X\* has a volume of at most (.2^n).

So for n = 1, we'd expect around 20% (or less!) of the m data points to lie in X\*.  This is enough data to make a good approximation for y\*.  

For n = 2, the space is sparser: only around 4% (i.e., 0.2^2) of the data will lie in X\*.  That's usually fine as long as m is sufficiently large.

The curse of dimensionality comes from the fact that the sequence of numbers {.2^n} converges to 0 -- and does so quickly. For more than four dimensions, we usually need too much data for the nearest neighbor method to be feasible.  

Let's close with an interesting thought experiment that illuminates the curse of dimensionality: consider an n-dimensional hypercube with an inscribed n-dimensional hypersphere.  In two dimensions, we can see that the circle takes up most of the area inside of the square. In three dimensions, the sphere takes up most of the volume inside of the cube.  But as dimension increases towards infinity, the ratio of the volume of the n-sphere to the n-cube goes to zero!  So most points in an n-cube are just very far apart - and are even far from the center.
