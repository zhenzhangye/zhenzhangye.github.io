---
layout: post
title: Feeling Blue
---

In statistics, the acronym BLUE stands for Best Linear Unbiased Estimator.  For a while I didn't know this and wondered why the stats paper I was reading kept using capitalized colors to describe a regression.  

What exactly is meant by 'unbiased'?  The bias of an estimator is the difference between the estimator's expected value and the true value of the parameter.  An estimator with zero bias is called unbiased.  An unbiased estimator may wildly overshoot or undershoot on any particular sample, but over many samples large positive errors will cancel out large negative errors and the average error will tend towards zero.

So which unbiased estimator is the best? The one which varies the least from zero over many samples is the best - that is, the estimator with the lowest mean squared error.

The **Gauss-Markov Theorem** states that under certain conditions, the ordinary least squares estimate that we all love and overuse is BLUE.  If *heteroskedasticity* or *auto-correlation* are present, then OLS is still unbiased but it is no longer best - that distinction belongs to a variation on OLS called *generalized least squares*. 

The text that inspired this post is an 80-page paper called *Understanding Regression Assumptions* by William D. Berry.  I can't recommend it strongly enough, especially if you care about understanding every single detail of regressions.  He uses a lot of equations, but also somehow explains everything in an extremely intuitive manner. I learned something new on almost every page.    
