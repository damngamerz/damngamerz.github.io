---
layout: post
title: "Souvenir of GSoC'2017!"
categories: gsoc
tags: [journey,open-source,coala,gsoc]
image:
  feature: gsoc.jpg
  teaser: gsoc-teaser.jpg
  credit:
  creditlink: ""
---

So this it guys. The day I have worked for is finally here. This marks the end of my Google Summer of Code'2017. It's been an awesome journey of 4 months.

## Thanks!
Firstly, Thanks to both of my mentors [SanketDG](https://github.com/SanketDG) & [NiklasMM](https://github.com/NiklasMM). Thanks for everything! It's been an awesome journey for me, I couldn't have asked for better mentors than you guys. Secondly, Thanks to Org. admins and other mentors of coala.

Thank you guys, for not losing hope on me when I nearly failed my `PHASE-2` milestone. Somewhere this was the sole reason which drived me to recover my work and complete my final milestone in time :)

Finally, Thanks Google! for such a wonderful programme.

## How this all begin?
I came across coala while surfing on the internet. Though those were the initial days where I wanted to learn only python, but my ideology is if you want to learn something then do a project on it ;)  
The welcoming nature of the community thrived me to contribute towards this wonderful project. I continued to contribute in coala and in 2 weeks I was promoted to `core-developer`. This was the first ever experience of me contributing to an opensource community. Later I continued to contribute more and more. Although I already knew about Google Summer of Code but I wasn't sure if I'm surely gonna try a shot. Until I started talking with some of the mentors of coala. First was [NiklasMM](https://github.com/NiklasMM), the project Handle Nested Programming language was sounding interesting. Meanwhile I was doing an issue with [SanketDG](https://github.com/SanketDG). I came to know that he was an Ex-GSoCer at coala. So I started investigating with him about the process, reading his blogs, investing about how did he started....etc. At the end I got more interested towards **Documentation Extraction and Parsing**. We scheduled a skype call where he answered some of my doubts one on one.  

And the rest, It all just happened ;)

## What I have achieved with this project?
Coming back to my project **Documentation Extraction and Parsing**, The final goal was to develop an analyzing routine at least for python and java that will find all documentation strings in a file, parse them into specific groups and check them against a specified documentation style given by the user. The functionality can be extended so that the analyzing routine provides a patch that re-formats the documentation correctly, checks for grammatical errors (like spell checking).  

***Specifics of DocStyleBear***  
DocStyleBear supports following style:

Python:
 * Sphinx, The DocStyle followed is in below format:
   ```python
        def xyz_function(param1, param2, param3):
            """
            This is functions main description.

            :param param1:
                Param1 desc.
            :param param2:
                Param2 desc.
            :param param3:
                Param3 desc.
            :return:
                Nothing.
            """
            return None
    ```
    For further info [check here](https://www.sphinx-doc.org/en/stable/domains.html#info-field-lists).

Java:  
 * Default style, The DocString followed is in below format:
   ```java
   class HelloWorld {

       /**
        * Returns an String that says Hello with the name argument.
        *
        * @param  name
        *     the name to which to say hello
        * @raises
        *     IOException throws IOException
        * @return  
        *     the concatenated string
        */
        public String sayHello(String name) throws IOException {
            return "Hello, " + name;
        }
    }
    ```
    For further info [check here](https://www.oracle.com/technetwork/articles/java/index-137868.html).

***Specifics of DocGrammarBear***  
DocGrammarBear should atleast be able to lint basic spell checking over: Main descriptions and Comments descriptions.
For example: If we have a malformed docstring.
```python
def some_func(param1, param2):
    """
    This is thet main descrpton.

    :param param1:
        This is param1 description.
    :param param2
        Thiss is param2 descripton.
    :return:
        Nothing
    """
```

This has incorrect spelling mistakes. The DocGrammarBear should be able to correct it.
```python
def some_func(param1, param2):
    """
    This is the main description.

    :param param1:
        This is param1 description.
    :param param2
        This is param2 description.
    :return:
        Nothing    
    """
```
Now, if I see the whole evolution of DocumentationAPI in these past 4 months. There are many things which I achieved:
 1. Earlier DocumentationAPI was not being in use by any bear. `DocStyleBear` was in `Work-In-Progress` mode, from past 1 year. So I took over that PR and with some quirks I was able to merge it in time.
 2. DocumentationAPI still wasn't stable. It longed for an stable design. Which `DocBaseClass` fulfilled it. `DocBaseClass` have 3 static methods:
       1. `extract` - Used for extracting documentation.
       2. `process_documentation` - Used to change the original instance of `DocumentationComment` according to the needed style.
       3. `generate_diff` - If desired instance of `DocumentationComment` is not obtained. Applies a diff.
 3. Later added 2 new features: `automatic_padding` and `docstring_type` which made it possible for the DocumentationAPI to actually check the `docstring_type` and amend blanklines before and after the docstring according to [PEP-257](https://www.python.org/dev/peps/pep-0257/).
       1. `docstring_type` of `function` should have paddings `(top_padding=0, bottom_padding=0)`. Which means function level docstrings should never be followed by a line before or after.
       2. `docstring_type` of `class` should have paddings `(top_padding=0, bottom_padding=1)`. Which means class level docstrings should be followed by a line below.
 4. Adding `DocGrammarBear`, which used to analyze and fix basic spellings and grammar inside the descriptions of DocComments.

**Stretch Goal**
 1. Adding an error handling mechanism to DocumentationAPI. `MalformedComment` which will be returned instead of `DocumentationComment`, if any part of DocumentationAPI(DocumentationExtraction.py, DocstyleDefinition, DocBaseClass.py and DocumentationComment.py) will be unable handle a docstring. This is important so that we can yield a `RESULT` with a beautiful message in the bear.

These were the biggest achievements which I consider the completion factor of this project. Hence, achieving the final/stretch goal as mentioned above.

## What has been done till now?

**coala**

[**e41d6b5**](https://github.com/coala/coala/commit/e41d6b5) DocumentationExtraction.py: Diff cut-off fix  
[**c79ec5a**](https://github.com/coala/coala/commit/c79ec5a) DocumentationComment.py: Improve `assemble()`  
[**fa26911**](https://github.com/coala/coala/commit/fa26911) DocumentationAPI: Support for :raises xyz:  
[**6abf8a0**](https://github.com/coala/coala/commit/6abf8a0) DocumentationComment.py: Add in-line comment  
[**bac0c3e**](https://github.com/coala/coala/commit/bac0c3e) DocumentationComment.py: Pass `indent`  
[**526af97**](https://github.com/coala/coala/commit/526af97) DocumentationComment: Add conditional for `None`  
[**f3f613a**](https://github.com/coala/coala/commit/f3f613a) DocumentationComment.py: Accept `position`  
[**fa7bd17**](https://github.com/coala/coala/commit/fa7bd17) DocumentationComment: Fix missing ending colon  
[**d79e497**](https://github.com/coala/coala/commit/d79e497) DocBaseClass: Add DocBaseClass  
[**ffba831**](https://github.com/coala/coala/commit/ffba831) DocumentationComment.py: Add blankline padding  
[**cebe4f2**](https://github.com/coala/coala/commit/cebe4f2) DocumentationAPI: Ignore triple quote strings  
[**0f81583**](https://github.com/coala/coala/commit/0f81583) DocumentationAPI: Add `MalformedComment`  
[**070a19e**](https://github.com/coala/coala/commit/070a19e) DocumentationAPI: Add `padding` and `type`  

**coala-bears**

[**7ad62fb**](https://github.com/coala/coala-bears/commit/7ad62fb) Add allow_missing_func_desc  
[**40de247**](https://github.com/coala/coala-bears/commit/40de247) DocumentationStyleBear.py: Amend `position`  
[**314dfdf**](https://github.com/coala/coala-bears/commit/314dfdf) DocumentationStyleBear: Use DocBaseClass  
[**40cd086**](https://github.com/coala/coala-bears/commit/40cd086) DocumentationStyleBear: Add expand_one_liners  
[**112fa7d**](https://github.com/coala/coala-bears/commit/112fa7d) Add DocGrammarBear for docstrings  
[**dccce31**](https://github.com/coala/coala-bears/commit/dccce31) DocStyleBear: Add `MalformedComment` support  
[**89b5913**](https://github.com/coala/coala-bears/commit/89b5913) DocumentationStyleBear: Add blankline support  

## What's up ahead?
There are still some quirks need to be done with `DocStyleBear` and `DocGrammarBear`.
 1. `DocStyleBear` is adding `r` if the docstring is a raw string. See [here for info](https://gitlab.com/coala/GSoC-2017/issues/33).
 2. `DocGrammarBear` doesn't works with well if there are some acronyms.

Next is, if everything is sorted I will add `DocStyleBear` and `DocGrammarBear` into `.coafile` of coala. I really want that my work should be used somewhere(at least in coala and coala-bears repo).

## How did I feel after completing my final milestone?
Well I felt awesome to get everything done in time. But now Im feeling jobless xD. I guess I will go on a review sprint and help my other GSoC coalians.

## GSoC coalians.
Lastly, I wanna speak about my other GSoC collegues. They had also done a great job with their projects. You can read alot about us [@blog.coala.io](https://blog.coala.io/). Also If any of this sounds interesting to you. How about joining us next? [@coala.io/newcomer](https://coala.io/newcomer).

That's it folks!

Till next time see yaa!!
