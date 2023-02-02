---
layout: post
title: The Bias-Variance Tradeoff
---

You are probably familiar with various measures to assess the prediction accuracy of a particular model, such as R-squared or the residual sum of squares (RSS). 

Another measure that statisticians care about is the mean squared error (MSE), or the average squared residual, which is just the RSS divided by the sample size.  It turns out that the MSE can be decomposed into three components:
- irreducible error
- variance
- squared bias  

When we model a relationship between two variables, there are infinitely many possibilities from which to choose! So the first thing we do is restrict our search by picking a particular class of models; each class makes simplifying assumptions about the nature of the relationship. If we are performing regression, the assumption is that the relationship between x and y is linear.  If we are using a nearest neighbor method, the assumption is that it is locally constant. To the extent that this assumption is not exactly true, we have introduced an error into our model known as **bias**.



The irreducible error comes from noise or from variables that we are not modelling and is not of interest to us.  

It's easy to reduce either bias or variance separately by choosing a particular predictor function.  If I choose a prediction function that passes through all the points in the data set, then I've created an estimator with a low but not zero bias (some bias is introduced depending upon how I connect up the data points).  So we see that reducing either variance or bias separately is trivial; the art lies in minimizing the sum.  


The bias-variance tradeoff, like the curse of dimensionality, summarizes one of the central difficulties in modelling and statistical prediction. The more I read about statistics and machine learning, the more I understand the bias-variance tradeoff in new and different ways. 
