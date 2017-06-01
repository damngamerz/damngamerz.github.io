---
layout: post
title: "Bonding Period Ends"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: bonding.jpg
  teaser: bonding-teaser.jpg
  credit: 
  creditlink: ""
---

Hi Guys!! With the end of this month `Community Bonding` period finally comes to an end, which marks the beginning of `Coding Phase-I`. In which, students officially now starts coding on their projects. Before even I would start with `Coding Phase-I`, I thought about summarizing my overall objectives achieved in `Community Bonding`.

## Summary
 1. I started with testing the old `DocumentationStyleBear` over `coala` and `coala-bears` repo. My first task was to get the old [`DocStyleBear` PR](https://github.com/coala/coala-bears/pull/1506) of [SanketDG](https://github.com/SanketDG) merged, currently! I have hijacked it :P . I found 2 major issues while testing:
     * We know python has some fancy strings which are written as:
```js
arguments="""
sum= a+b+c
avg= (a+b+c)/3
"""
```
`DocumentionAPI` should ignore such strings. I had a healthy discussion with my mentors about this issue and we came to a conclusion that it required some more ideation, hence being moved to `Coding Phase-I`.
    * `DocumentationAPI` was not having support for `:raises xyz:`. Hence, it's being successfully [implemented](https://github.com/coala/coala/pull/4281). The patch right now is in review phase.
 2. There was bug in `DocumentationAPI`, which generated cut-off diffs. For example, if a docstring is written this way:
```js
        """
 This is not a cool way to write docstrings.
        """
```
The generated diff would be.
```js
        """
         not a cool way to write docstrings.
        """
```
A patch fixing this bug has been [implemented and merged](https://github.com/coala/coala/pull/4275).
 3. A new parameter `allow_missing_func_desc` needs to be added which will ignore a warning message, when `DocStyleBear` doesn't finds a function description. This has also been [implemented](https://github.com/coala/coala-bears/pull/1506).
 4. Last and Final task was to analyze coala's structure and write a blog about it. So, [here it is](https://damngamerz.github.io/gsoc/An-Insight-Into-coala's-Structure.html).

At the end here's a burnout chart depicting my working efficiency.
![bonding chart]({{ site.url }}/images/chart_bonding.png)
Although, I wasn't able to complete my `Bonding` milestone 100%. As to close an issue, the related PR should be merged beforehand. While I got my 2 PR's in review state. And both of those PR's had big updates/patches, which I submitted beforehand deadline by 2 days and hence it didn't got sufficient time to go through review phase.

## What's next?
Well `Coding Phase-I` begins now, and I can't risk my chances of staying behind schedule. The things I learned from `Community Bonding` phase will play a very crucial role in this phase, one of which is I have to submit my patches as early as possible, cause about 60% time goes in review cycle. Ofcourse, I don't blame the review process by that statement, cause it is very fruitful and it always polishes the PR to get merge ready. Although, I must say coala's review process is fast, well faster than the other open-source organisations, In which a simple patch can be in review phase for months before it finally gets accepted. Here it take a day or so. But for big patches it obviously takes weeks of review iterations to actually get it merged. Kudos!! to all my fellow devs and maintainers for making this process fast!!

## Thanks!
Special Thanks to both of my mentors [SanketDG](https://github.com/SanketDG), [NiklasMM](https://github.com/NiklasMM) and other mentors of coala. Without them this wouldn't have been possible. Thanks for understanding when I asked to code in `Bonding Period` phase and making me code in, which really gave me a taste of how `Coding Phase-I` will actually go. I will try hard to not let you guys down.

Till next time Tschüss!!
