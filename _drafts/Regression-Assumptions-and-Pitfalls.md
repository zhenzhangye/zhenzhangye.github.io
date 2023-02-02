---
layout: post
title: Regression Assumptions and Pitfalls
---

Linear regression is overused, and all too often it's used inappropriately.  Here's a list of the assumptions underpinning linear regression, and an explanation of what goes wrong when each rule is violated.  A common theme is that violating these laws will cause the p-values of our coefficients to be artificially low, and us to have an unwarranted amount of confidence in our model.  

A general caveat: even if one of these assumptions fails globally, it might hold true (or almost hold true) when we restrict x to a certain domain.  That's fine; just make sure not to extrapolate beyond the restricted region. 


1. Linearity of the data  
2. Error terms must be uncorrelated   
3. Homoscedasticity - constant variance of error terms
