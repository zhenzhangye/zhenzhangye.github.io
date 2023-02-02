---
layout: post
title: Conditioning on a Collider
---

I'm trying to come up with a cute, terse way to illustrate the phenomenon of conditioning on a collider and I'm actually having a hard time summarizing it.  Mostly because I just read a rigorous academic paper discussing all the insiduous details of colliders, and I absolutely love rigor and details and want to tell you all about it!  But I'll suppress the urge.  This is the cliff notes version.  Enjoy.

Conditioning on a collider is a special case of selection bias, where the sample studied doesn't accurately reflect the makeup of the population that we wish to draw conclusions about.  The selection bias occurs because inclusion in the sample is determined based upon two (usually independent) factors. It's tough to conceptualize without an example so let's dive right in.

Admission to Princeton University is based upon a lot of factors, including grades, scores, recommendations, extracurriculars, and a  personal essay.  We can roll up all these factors and just call them "high school record".  Obviously, the process is complicated and subjective, but for simplicity's sake let's agree that the admission committee looks at each applicant's high school record and accepts the top 5% of students.  

Now suppose the Princeton Committee for Diversity & Inclusion surveys the student body and discovers a shocking paucity of left-handed red-heads (henceforth referred to as LRs) among the university community.  The Diversity Committee writes a strongly-worded letter to the Admissions Committee suggesting that they accept all LR applicants going forward.  

Five years later, the first batch of LR students graduates with the rest of their class. How do you think they fared academically at Princeton?

Now, I have no reason to believe that handed-ness or hair color have any correlation with academic performance or intelligence in the general population.  But the LR students aren't competing against the general population.  They are competiting against Princeton undergrads, most of whom were specifically chosen for their intelligence and past academic performance.  So I'd expect those LRs to do very, very badly at Princeton.

Let's recap what happened. Princeton admitted a sample of students, each of whom fulfilled at least one of two independent critera: 1) outstanding high school record 2) LR status.  Even though these criteria are independent in the general population, the way that the sample was chosen *induced a strong negative correlation between the LR status and academic performance within the sample*.  And that's conditioning on a collider.

The point is that admitting students for *any* reason other than academic merit will induce an artificial, negative correlation among students satisfying that criterion and academic success within the Princeton community.  Indeed, even just breaking "ties" during the admissions process using a criterion like legacy status is enough. Because then you can essentially divide the community into students whose records were so spectacular that they got in without a tie-breaker, and more marginal students who needed the legacy boost.  (Of course, there are students who qualify for inclusion in both groups, as well as marginal non-legacies, but that is irrelevant. Legacy preference will cause a disproportionate number of marginal admits to have legacy status.)  This is true for athletes, legacies, and affirmative action students.  The statistical fallacy occurs when we erronously conclude that LR students or legacies or athletes or minorities are weaker academically.  That isn't necessarily true - the sample we studied was biased due to conditioning on a collider.
