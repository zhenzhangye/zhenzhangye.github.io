---
layout: post
title: Clean Code
---

I'm reading a book called *Clean Code* and it is fantastic.  

The author, a developer who inexplicably refers to himself as "Uncle Bob", is dramatic, arrogant, obsessive, and brilliant.
Here are some gems from the first couple of chapters: 
<div></div>
> Flag arguments are ugly.  Passing a boolean into a function is a truly terrible practice.

<div></div>
> Side effects are lies.  Your function promises to do one thing, but it also does other *hidden* things.  

<div></div>
> The proper use of comments is to compensate for our failure to express ourself in code.  Note that I used the word *failure*.  I meant it.  Comments are always failures.  We must have them because we cannot always figure out how to express ourselves without them, but their use is not a cause for celebration.

It takes a truly impressive amount of discipline to be so committed to simplicity: 
<div></div>
> Blocks within if statements, else statements, while statements, and so on should be one line long.  Probably that line should be a function call.

<div></div>
> Functions should not be large enough to hold nested structures.  Therefore, the indent level of a function should not be greater than one or two.  

<div></div>
> The ideal number of arguments for a function is zero (niladic).  Next comes one (monadic), followed closely by two (dyadic)... More than three (polyadic) requires a very special justification  - and shouldn't be used anyway.  

Isn't niladic a great word? And isn't it a lot easier to do unit testing on a monadic function than on a polyadic function?  

The book is written in Java, which is a bit disappointing to me as I am trying to put Java behind me and focus on What Is Really Important (i.e., python and R).  The cool part is that every couple of pages I stumble on an aspect of Java that I've never learned; I'm compiling a list, so expect that in an upcoming post!
