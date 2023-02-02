---
layout: post
title: Universality of the Uniform
---

For any continuous random variable X, if we apply the cumulative distribution function (cdf) of X to X itself we obtain a uniform random variable on the interval [0,1].

Wikipedia calls this the Probability Integral Transform, and as a mathematical statement I don't find it particularly illuminating. But after reading an example I was more excited:

Supposed X is a random variable modelling the heights of a population of women. Let's sample from X one time and call the data point x.  Then cdf(x) is the person's height percentile.  And cdf(X) is uniform on [0,1] because a randomly generated person is just as likely to fall between the 2nd and 7th percentile for height as she is to fall between the 52nd and 57th percentiles.  

Pretty neat way of expressing a concept that you probably know intuitively. Can be used: 1) to test the accuracy of a probability model  2) to generate a uniform random variable given another random variable 3) to simplify an otherwise difficult integral.

