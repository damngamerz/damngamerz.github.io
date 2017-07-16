---
layout: post
title: "Phase 2 Mid Month Summary"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: coding.jpg
  teaser: coding-teaser.jpg
  credit:
  creditlink: ""
---

Hi guys, It's been 2 weeks since 1st evaluation. And this is my `Coding Phase-2` Mid Month summary.

## Summary
This part of GSoC I felt was the toughest and interesting. Cause it was all designing which took a mere time but I finally did it ^_^
  1. In coala we have `BearBaseClass` so as to create new bears and which also is the back-bone of coala-bears repo. I had to design something similar called `DocBaseClass` which will take care of extraction, parsing of fixed documentation and diff generation. So it looks like this.
```python
class DocBaseClass:
  extraction():
    ...
  fix_parse_data():
    ...
  diff_generation():
    ...
```
The main objective for this base class to exist is that. The `fix_parse_data()` member function can be overided by the user according to their needs. A [PR is opened](https://github.com/coala/coala/pull/4465) and is currently in a review phase.
  2. `DocumetationStyleBear` is ported to use this new `DocBaseClass`. The [PR is opened](https://github.com/coala/coala-bears/pull/1928) and is currently waiting for the upstream merge, after which it will get reviewed.

So these were the two major changes which I had done, making about 70% completion of the milestones in my opinion. I guess this time too I will be able to achieve 100% in time.

## What's up next?
Though my mentors agreed upon to only implement this functionality for this month. But I will be moving to bugs as there're few in my opinion which definitely needs to be fixed. And then I will be testing this new `DocumentationStyleBear` over coala-repo.

## EuroPython Update!
Ahh It's been a long amazing week beer, beach, a lot of tasty food and what not :P Im still in rimini, Italy and will write a blog soon after I return back to India summarizing my experience of it ^_^

Till next time! See Yaa!!
