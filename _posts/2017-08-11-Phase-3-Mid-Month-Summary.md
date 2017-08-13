---
layout: post
title: "Phase 3 Mid Month Summary"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: coding_final.jpg
  teaser: coding_final-teaser.jpg
  credit:
  creditlink: ""
---

Hey guys, It's been 2 weeks since 2nd evaluation. And this is my `Coding Phase-3` Mid Month summary. Before I begin with the summary, I just wanna share with you guys that I nearly passed my 2nd evaluation. My bad, I wasn't able to achieve my last issue, it turns out the issue's solution was designing the API rather than what I proposed earlier.

## How did I feel about failing the milestone?
It sucks!! Well at first I really got tensed what will the org. admins decide. But it turns out they understood the situation and believed in me that I will still achieve my final goal. Ofcourse! I will not let them down :) . Thanks to org. admins and my mentors for understanding why I wasn't able to achieve it. At the end it all turned out well, I'm quite happy about how the final solution turned out to be. Also this solution is the biggest patch of my GSoC experience, which introduced 2 new features to the Documentation API. Kind of an achievement for me ^_^

## Summary
Originally! the only objective for me this month was to implement `DocGrammarBear`. Which will check for grammatical errors inside the DocumentationComment's descriptions. But most of the time I spent on clearing the issue which got a bit off-scheduled from my previous milestone.
  1. First, the issue was to check and fix the blank lines before and after the Documentation for `function` vs `class`. According to [PEP-257](https://www.python.org/dev/peps/pep-0257/) `class` docstrings should be followed by a blank line and `function` docstrings should never have any blank lines before of after. This issue got so stretched that I ended up implementing 2 new features to the DocumentationAPI.
      1. **Automatic Padding**- We have a setting in DocumentationAPI which automatically tells how many lines are above and below the docstring.
      2. **Docstring Type**- We can detect & determine between docstrings, whether they are of type `function`, `class` or `others`.

     These both additions were important inorder to solve this issue perfectly. A [PR has been made](https://github.com/coala/coala/pull/4557) and is close to being merged.
  2. `DocGrammarBear` which will check for grammatical errors inside the DocumentationComment's description. [PR is ready](https://github.com/coala/coala-bears/pull/1980) and close to merge. Also I made an [asciinema](https://asciinema.org/a/132564) so you can see this bear in action.

These were the 2 major objectives of this month. I think I can achieve my final milestone. As everything is back on schedule.

## What's up next?
There are 2 bugs regarding DocumentationAPI which still needs be taken care of. First, Ignoring string literal solution kind of created a bug with its last marker being taken as the start of new docstring. Second, We kinda broke the corner case of all docstrings with java docstyle bug fix. Need to fix it or revert this and raise an error message. That's it guys!

Till next time! See Yaa!!
