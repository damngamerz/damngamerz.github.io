---
layout: post
title: "Phase 2 Month End Summary"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: coding.jpg
  teaser: coding-teaser.jpg
  credit:
  creditlink: ""
---

Hi Guys!, How you doing?
It's been 4 weeks of `CODING PHASE-2` and it's evaluation time again. So from 24th 9:30pm, Evaluation links will become active both me and my mentor have to fill a Q & A form ^_^. So in this blog I will be sumarizing my GSoC'2017's work of last 2 weeks. Let's begin!!

## Summary
The deadline of achieving the milestones set by my organization is 24th July. The big thing was `DocBaseClass` got merged which now takes care of extraction, parsing and diff generation of documentation. Developers now only have to inherit this class in order to work on documentation linters. Following are the issues on which I have worked upon in last 2 weeks. These are mostly bugs fixes and quirks to DocumentationAPI and DocStyleBear:

 1. DocStyleBear now has a setting to expand one-liners. By default it will convert all the docstrings which only have main description to one-liners. In order to expand it as multi-line docstring, you have to set `expand_one_liners=True`. A patch has been implemented and [merged](https://github.com/coala/coala-bears/pull/1940).
 2. DocumentationAPI was returning nothing when JavaDoctyle was written with malformed docstyle markers. We now use `markers.strip()` to extract documentation. A patch has been implemented and [merged](https://github.com/coala/coala/pull/4530).
 3. The official standard of writing a documentation includes a blank line before and after a docstring. Hence this was important and `DocumentationComment` class now has padding option to include a blank line. A patch is implemented and in [review](https://github.com/coala/coala/pull/4549). I hope It will get merged before the deadline.

This was it!! Im close to achieving my milestone of `PHASE-2`. You can see my progress [here](https://gitlab.com/coala/GSoC-2017/milestones/10). And here's how my burndown chart looks like.

![bonding chart]({{ site.url }}/images/chart_phase2.png)
sweeeet!! ^_^

## PARTY TIME!!
Kudos to....Both of my mentors [SanketDG](https://github.com/SanketDG) & [NiklasMM](https://github.com/NiklasMM) for achieving this milestone together. I'm really enjoying working with them. We sometimes even have disagreements with each other about somethings :D , which always turns out to be fruitful at the end. We still have 1 more month ;) and I think we can complete this project in time.

## What's up Next?
Next up I have to implement is DocGrammarBear which will be doing spell checking, grammar checking..etc over documentation. Also there're some quirks and bugs related to DocStyleBear, which I will be fixing in next Coding Phase.

Till next time. See Yaa!!
