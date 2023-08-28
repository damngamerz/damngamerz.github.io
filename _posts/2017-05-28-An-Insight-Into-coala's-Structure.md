---
layout: post
title: "An Insight Into coala's Structure"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: coala_intro.jpg
  teaser: coala_intro-teaser.jpg
  credit: 
  creditlink: ""
---

Hi Guys!! Its been a long since my last post. This blog post is intended for all newcomer's who would like to contribute to coala. So, I will give you an insight into coala's Structure in a bit detail to actually get you started.

## An Insight Into coala's Structure.
coala's code base can be found here at [github](https://github.com/coala/coala). It's directory tree looks like:
![coala's tree]({{ site.url }}/images/coala_tree.png)

You can see, this tree has 3 major parts.

 1. **coalib**: Which is the homeground of coala API. This is the place where most of the important technical aspects goes.
 2. **docs**: Contains generated documention of coala API, which is built and beautifully displayed over [`api.coala.io`](https://api.coala.io)
 3. **tests**: Contains all the test files over coalib directory.

Since, `docs` and `tests` are established over `coalib`, so `coalib` is the star directory. And hence, I would be only explaining about it.

## coalib
`coalib` is the collection of various subpackages regarding writing, executing, editing bears, formatting, settings and much more. So let's dig in boys!!

`coalib` is further divided into 11 parts:

 1. **bearlib**: Which contains bear utilities, `aspects`'s API, `abstractions` like linter bears and also `languages` which contains various language definitions(such as identifying different languages with their versions) to provide unified language experience to coala.
 2. **bears**: Provides the base bear class i.e. `LocalBear` and `GlobalBear`. Without which bears that exists in coala-bears [repo](https://github.com/coala/coala-bears) wouldn't exist.
 3. **collecting**: provides collector routines which collects all bears, dependencies and file directories for coala. The collection works on the basis of 2 factors inputs provided at `CLI` and at `.coafile`.
 4. **core**: `core` module contains the chronological order about what coala has to do with a bear. It takes care of all the step's involved(like having a complete schedule), when a bear runs over a given file.
 5. **misc**: Provides all the other utilities like `cachingUtilities`, `DictUtilities`, `BuildManPage` module and `Shell` module. `Shell` module is the important aspect here, as it helps coala to run in an interactive shell mode.
 6. **output**: Provides the API for making coala interactive with its users via `CLI`. The `ConsoleInteraction` module provides the utilities about user provided `Actions` like `Show_Patch`, `Apply_Patch`, `Ignore_Patch`..etc. It acts as a mediator between coala and the user, helps coala in providing the user important information by printing generated diff's, messages, list of bears..etc.
 7. **parsing**: The name itself suggests this is the `parsing` module. It contains all the routines about parsing important information from a string of characters. Most of them support regex pattern matching. For example: Parsing `CLI` arguments and creating sections out of it.
 8. **processes**: Provides the processing utilities and routines which takes decisive actions when a bear is in running state. It has routines which works like a control centre for processes. It takes care of process execution's tasks such as:
     * preparing a process -> loading files -> creating queues
     * spawn up one or more processes
     * yielding results from the processes
     * finally joining all the processes
 9. **results**: This section works closely with the `output` section. `results` provides routines like `Diff` module, `LineDiff` module, `TextRange` module and `ApplyAction`'s module(user defined actions like ApplyPatch, IgnorePatch, ResultAction and ShowPatchAction). `Diff` and `LineDiff` modules are similar, they both generates a unified diff corresponding to a generated patch by coala. The only difference between them is `LineDiff` generates diffs over two strings wheareas `Diff` generates it over two files. When a `Diff` is being generated or we have a yielded `Result`, it is supplied to the `output` section, which in turn is being commuted to the user.
 10. **settings**: A `setting` in coala consists of a key and a value. It mainly offers many conversions into common data types. It provides important modules like `Section` module which holds all the set of settings and `ConfigurationGathering` module which plays two important roles: 
     * finds user configs(`.coafile` ofcourse)
     * gathers configuration(such as loading configs, retrieves bears and all needed settings, saves the settings back if needed and warns about non existent targets)
 11. **testing**: The last and final section is the `testing`, which contains the API for bear testing. It provides `LocalBearTestHelper` module which contains routines like `check_results`, `check_validity` and `verify_local_bear`. These basically test a bear by doing a simple assertion test, between the given result and to the actual yielded result from the bear over a given file.

If you will dive deep enough, it's working is even more interesting. If it sounds interesting to you as well, you can start contributing right away by following our [newcomer's guide](https://coala.io/newcomer).

Till next time see ya!!
