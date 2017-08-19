---
layout: post
title: "Phase 3 Month End Summary"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: coding_final.jpg
  teaser: coding_final-teaser.jpg
  credit:
  creditlink: ""
---

Hi Guys!, How you doing?
It's been 4 weeks of `CODING PHASE-3` and it's evaluation time again, this is the final one. So from 21st 9:30pm, Evaluation links will become active both me and my mentor have to fill a Q & A form ^_^. In this blog I will be sumarizing my GSoC'2017's work of last 2 weeks. Let's begin!!

## Summary
The deadline of achieving the milestones set by my organization is 21st August. The big thing was `DocumentationAPI` now has support for automatic padding and docstring type. Which tells us about the trailing no. of blank lines before or after the docstring and also about the type of docstring it is: `function` level or `class` level. By using these, now we can have blank lines detected and fixed according to [PEP-257](https://www.python.org/dev/peps/pep-0257/). Last 2 weeks was mostly about bug fixes.

 1. Triple quoted string literals which was ignored by `DocumentationAPI` was creating a bug. It's end marker was taken as the starting of a new docstring. Seems like the patch which I submitted in `PHASE-1` to ignore these string literals was creating this. So I found the other way around. We now Ignore the whole `DocComment` instead of ignoring it by regex(Which was the case previously). So a PR reverting the previous changes and applying a new solution was [made and merged.](https://github.com/coala/coala/pull/4632)
 2. There was a Java docstyle bug (you can read more about it [here](https://github.com/coala/coala/issues/4029)). The solution I proposed in `PHASE-2` was breaking a corner case. Which we thought could be fixed seperately. But it wasn't like that. So finally we came to a conclusion that `DocumentationAPI` couldn't fix docstrings if their markers are faulty. As markers are the only thing by which drives `DocumentationAPI` to find docstrings inside a file, we now just yield a `RESULT` with beautiful message which describes that markers are faulty. So a PR reverting the previous changes and applying a new solution was [made and merged](https://github.com/coala/coala/pull/4637).

This was it!! I have successfully achieved my milestone of `PHASE-3`. You can see my progress [here](https://gitlab.com/coala/GSoC-2017/milestones/11). And here's how my burndown chart looks like.

![bonding chart]({{ site.url }}/images/chart_phase3.png)
Yay! I did it!

## STRETCH GOAL
Yes you read it correctly. I completed one of the biggest stretch goal which I had a thought since `PHASE-1`. It was about giving an error handling mechanism to DocumentationAPI. So we now have `MalformedComment` class which can be yielded if there is some error in parsing the docstring by DocumentationAPI. Which contains attributes like error message and line number, so these can be yielded on the bear part. A PR has been [made and merged](https://github.com/coala/coala/pull/4637).

There's still one more week remaining for hard deadline of August 29. I was thinking about doing some more quirks to DocGrammarBear and DocStyleBear which will polish my project and a review sprint ;) You can see all progress about stretch goals [here!](https://gitlab.com/coala/GSoC-2017/milestones/44)

There were some up and downs in `PHASE-2` I nearly failed the milestone. But
> Why do we fall? So we can learn to pick ourself's up - Alfred

## PARTY TIME!!
Kudos to....Both of my mentors [SanketDG](https://github.com/SanketDG) & [NiklasMM](https://github.com/NiklasMM) for achieving this milestone together. Couldn't have done this without them. We made 2 calls a week to discuss about progress and to answer my queries one on one, which is the sole reason of this project being done in time.

## What's up Next?
I don't know where this journey ends. It's feels like it had just begun and opened up a new chapter to fill ;) I will soon write another blog wrapping up about my overall GSoC journey.

Till next time. See Yaa!!
