---
layout: post
title: Correlation versus Independence 
---

If two random variables are independent, can they be correlated?  If another two random variables have zero correlation, can they be dependent?  

The answers are no and yes, and here's an example to illustrate why.  Suppose X is uniformly distributed on the interval [-1,1], and Y = X^2.  The expectation of X, conditional on Y=y, is always 0 regardless of y.  So X and Y are not correlated. However, Y is clearly not independent of X.  

This may seem weird, but it happens because when we say "correlation", we really mean "linear correlation".  Two dependent random variables may have zero linear correlation if they have a nonzero nonlinear correlation, as is the case in the above example.  Independence is the more general term; independence implies zero correlation but zero correlation does not imply independence. 
