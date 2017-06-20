---
layout: post
title: "Phase 1 Mid Month Summary"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: bonding.jpg
  teaser: bonding-teaser.jpg
  credit: 
  creditlink: ""
---

Hey there Guys!, I hope you are doing well. In this blog I will summarizing my GSoC'17 work till now. So it's been 18 days of `Coding Phase-I` and I have been moving forward with all I have, to make this project come to life. So Let's begin!

## Summary
Since, I learnt my lesson well from `Bonding Phase` :P so I started solving the big issues first. As they takes up a lot of time in review phase. Firstly I began adding additional functionalities to `DocumentationComment`. `DocumentationComment` is the core of `DocumentationAPI` which mainly dissociated the whole documentation into it's sub-parts (i.e. params,exceptions and return descriptions).
  1. Previous `assemble()` function was not accounting for a case in which middle and ending markers are same. Eg. `marker[1]==marker[2]` which is a type of case in python docstring.
```python
def docstring_find(filename):
    ## This is dummy docstring find function.
    #
    #  @param filename contains filename
    #  @raises FileNotFoundError raises when filename is not found
    #  @return nothing
        return None
```
Hence I completed the work over this and a patch is submitted and [merged](https://github.com/coala/coala/pull/4319).
  2. `DocumentationComment` accepts `range` as an argument we will be shifting it to `position`. Since `TextRange` is constructed from `TextPosition` it's just a simplification of constructor but important indeed. A patch is currectly in the [review phase](https://github.com/coala/coala/issues/2646) right now. I guess it will be merged in 2 review iterations or so.

So these were the two major changes which I had done, making about 60% completion of the milestones in my opinion. I guess this time I will be able to achieve 100%. 100% or not my patches should be good in quality thats my inner objective ;)

There's one more thing, the [big patch](https://github.com/coala/coala-bears/pull/1506) `DocumentationStyleBear` finally got accepted. It's not fully complete at the moment. Requires lot of additional functionalities but that's the basic functionality which we have longed for.
## What's up ahead?
Next, I have 4 additions lined up for `DocumentationExtraction` out of which only 2 are solvable at the moment and the rest will be moved ahead to `Coding Phase-II`. I will be writing more about them in my next blog.

That's all guys. Till next time See YAA!!
