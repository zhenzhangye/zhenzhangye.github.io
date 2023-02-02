---
layout: post
title: Simpson's Paradox
---

Every Simpson's paradox involves at least three variables:

* the explained (y)
* the observed explanatory (x<sub>1</sub>)
* the lurking explanatory (x<sub>2</sub>)

If the effect of the observed explanatory variable on the explained variable changes directions when you account for the lurking explanatory variable, you've got a Simpson's Paradox.

The classic example involves two doctors, A and B. Each has treated 100 patients, and doctor A has cured 90 while doctor B has cured 80.  In this case, success rate is the dependent variable, and doctor is the observed explanatory.  We conclude that doctor A is the superior doctor because he cured a higher percentage of his patients.

Only, not so fast. There's another variable lurking in our sample: severity of illness.  For simplicity, suppose each illness has one of two severities: low and high.  We dig deeper into the data and see that doctor A treated 80 patients with low severity illness and cured 72 (90%) of them.  Doctor B treated only 50 patients with a low severity illness and cured 48 (96%) of them.  So doctor B actually does better with low-severity illness patients.  

And here's the amazing part: doctor B also does better with severely ill patients! Doctor A only cured 2 out of 20 severely ill patients; doctor B cured 32 out of 50. So doctor B is an all-around better doctor; he cures a lower percentage of his patients only because they are sicker.   

In every example I've seen, both explanatory variables x<sub>1</sub> and x<sub>2</sub> are qualitative and each have a demonstrable and crucially, *opposite*, association with y.  Problems arise when dividing the sample by both factors simultaneously yields unequally-sized classes.  The unequal group sizes give a different weighted average among the classes of factor #2 for each class in factor #1, which can lead to seriously flawed conclusions. 

As fellows at the Brookings Institute point out:

>As our society grows more diverse, Simpson’s paradox may make more frequent appearances. Scholars and policy-makers will have to be mindful as they examine long-term changes of social and economic progress. It would be a shame if real progress in these areas was overlooked because of a naïve reliance on single averages.
