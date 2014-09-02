---
layout: post
title: "Comp Sci Snippet"
date: 2014-09-01 11:24:23 -0700
comments: true
categories: [dev]
---
For my first blog post, a snippet of raw computer science: how are arrays stored in computer memory, as they relate to the Ruby programming language? First, let me marvel for a moment at the many degrees of abstraction between Ruby and what the computer processor ultimately processes: binary, or a series of 0's and 1's. Before knowing anything about computer programming, I used to think that programmers were of a rare nerdy breed of (maybe?) human who know the ins and outs of computers *so* thoroughly, they're practically computers themselves. This notion was probably influenced by a brainy elementary school classmate I had who, years after knowing him, went on to win a prestigious international coding contest. Perhaps *he* was one of those (human?) types, but one could theoretically be an excellent programmer without knowing much about how computers work. High-level programming languages---of which Ruby is an excellent example---provide that luxury, as their syntax, vocabulary, and flow are highly readable, so much so that a non-programmer could make sense of a basic Ruby program. This point is where the degrees of abstraction come in. Ruby itself is programmed using another language entirely, the C programming language, which, in its heyday, was considered a high-level, many-degrees-of-abstraction language as well. That's not to say C is obsolete — by no means! - but it is just fell in the ranks of high-level languages. And C, too, is built on other languages, which, moving down the latter of abstraction, eventually leads to assembly languages, then ultimately to machine code, which is the binary code that the CPU actually reads. Most programmers today, especially web developers, only have command over high-level languages, leaving the lower-level stuff all but unseen.
    With all these layers of abstraction between high-level languages like Ruby and machine code, the answer to how arrays
are stored in the computer's memory as they relate to Ruby might be...well, Ruby-like, in that the explanation will be understandable to the human reader, but not explain what is happening deep down in the RAM memory module, which is basically all electricity (there is actually nothing physical happening). An array is a Ruby `Class` defined by a collection of comma separated elements; you can have an array of numbers like `num_array = [1, 2, 3]`, an array of strings like `str_array = ["hi", "ho", "chitty", "chitty", "bang," "bang"] or an array of any combination of types of elements like mixed_array = [1, "chitty", :oh_my]. When an `array` is created in Ruby, in addition to storing the array elements, the identity (basically, the "address" of where that array element lives in the memory) of each array element is also stored. Each Array element is stored in consecutive memory locations as the array's organization suggests, allowing for quick, easy access, rather than being stored at random locations, which would make calling and manipulating the array more time-consuming (even though the difference would be infinitesimal and undetectable to humans).








