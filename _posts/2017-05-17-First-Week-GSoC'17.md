---
layout: post
title: "First Week GSoC'17"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: 1stweek.jpg
  teaser: 1stweek-teaser.jpg
  credit: 
  creditlink: ""
---

Hey people!! This is the end of my first week at GSoC'2017 (Google Summer of Code). The programme kicks off with the start of community bonding. Which is probably the period where students and mentors break the ice between them. So, I will be summarizing what all has been done till now, and what lies on the road ahead. In this blog Im gonna explain about my project in little more detail, followed by my objective for the upcoming week. This is gonna be a lengthy one so hold on tight!!

### What's my project about?
I have already been through with the description of my project twice, in my previous blogs. So rather than repeating the same Im gonna explain you in a bit detail what exactly my project will be acheiving after it's completion. So my project deals with the documentation of different languages

For java, the idea for the docstyle to be followed is defined [here](https://www.oracle.com/technetwork/articles/java/index-137868.html). In general it will look like:
```
/**
 * <main_description>
 *
 * @param <param_name> <param_description>
 * @return             <return_description>
 */
```
Similarly for python, the idea for the docstring to be followed is defined in [PEP-257](https://www.python.org/dev/peps/pep-0257/). And this looks like:
```
"""
<main_description>

:param <param_name>:
    <param_description>
:return:
    <return_description>
"""
```

So, I have to basically design an efficient API and later DocStyleBear & DocGrammarBear(using the API), which will contain analyzing routines over the documentation of python and java files according to the above defined format.

### How did the 1st week go?
Start of the week was full of joyness and excitement among all of the selected students. Which is because most of the bachelors (including me) are having first time experience as an intern and we are very much excited to begin our work. So we started our bonding period with a nice chat, setting everything up. Everything is going as smooth as it can ever be. We discussed about what all has to be done in the recent upcoming days, and what all will be done for the big picture. SO! LET'S ROLLLL!!

My first task was to create a detailed schedule over gitlab. We have done this through creating milestones according to official [GSoC Timeline](https://developers.google.com/open-source/gsoc/timeline). Which are as follows:

Objectives:
* [BONDING PERIOD](https://gitlab.com/coala/GSoC-2017/milestones/4)
* [CODING PHASE-1](https://gitlab.com/coala/GSoC-2017/milestones/5)
* [CODING PHASE-2](https://gitlab.com/coala/GSoC-2017/milestones/10)
* [CODING PHASE-3](https://gitlab.com/coala/GSoC-2017/milestones/11)

Second, was to introduce myself to the whole community on the coala-dev & coala-newcomers mailing lists.

And Final, was that I have get my feed.xml for this blog-page to be aggregated with [blog.coala.io](https://blog.coala.io/). You guys can now also access my blogs @coala's official [blog-page](https://blog.coala.io/).

### What's for the upcoming week?
Finally my exams are over and summer vacation has begun. Now I can devote my full time to this project. So probably Im gonna start completing my BONDING PERIOD: Milestones. Which right now has 4 issues. Also, I will be diving deep into the coala's codebase to understand its voodoo, and will be writing about it's working in the near future.

That's it for this week folks!! See yaa!!
