---
layout: post
title: "What Makes a Good Question?"
date: 2014-11-12 13:52:27 -0800
comments: true
categories: [culture, dev]
---

Hmm, good question! I would say it depends somewhat on the context in which the question is being asked, as well as the subject matter. For this blog post, to keep things within a manageable scope, I'll focus on what makes a good programming-related question. There's quite a lot of material out there about what makes good questions, and I echo many of the qualities that others have heralded. This post is a synthesis of outside sources with some of my own original thoughts and examples. Three overarching qualities that make good questions are:

  1. Specificity
  2. Clarity
  3. Relevance

My fellow cohortmates are generally quite good at asking specific, clear, and relevant questions, but every once in a while you'll come across a question that more or less follows this pattern:

> "Help! I can't get this to work"
>
> (insert overly large block of code here)
>
> "Why isn't it working?"

Perhaps it's obvious enough, but this is an example of a not-so-great question. Is it specific? No. Is it clear? Not at all. Is it relevant? Perhaps, but it's impossible to tell since it isn't specific or clear enough. You should evaluate a question's worthiness based on how easily you understand it, without having to run the code yourself. If anyone wanted to help out this distressed person, they would have to run the code to see what error the person is talking about, then troubleshoot it for the person. That's too much to ask of an answerer. Ideally, a good question is asked once the asker has already done a preliminary troubleshooting session, has isolated the problem somewhat, and asks a more specific question regarding the error message and the particular piece of code that causes the error, not the entire program. Odds are only a small fraction of the entire code file is causing the problem, so include only that code!

Let's quickly look at each of the three qualities I mention are key ingredients to good questions.

### Specificity

Is your question about a particular issue you are having with your code? Go into detail about the issue. Don't do what the distressed person did above and just plop the entire thing on someone else. Take time to investigate what the problem is, and explain it as specifically as you can. If you have a limited amount of characters to work with, such as in the title of a question, make sure you make it as specific as possible so potential answerers know what they're dealing with before they click your question. Here's an example of two questions, one is good and one is bad. It should be very obvious:


> "How does the math module work?"
>
> "How do you endow a class with the Math module in Ruby?"

So which one is bad? The first one, of course. It's not specific enough. How does it *"work"*? I'm not even sure what that means, or how to answer it. It's far too general. And what language are you talking about? Multiple languages might have the same math module, so you better be clear about which one you're talking about! If your question leads answerers to ask you questions in return (like that first one), it's probably not good question. Now, the second one: it's much better. It asks about how you perform a particular action in a particular language. Anyone who stumbles upon this question in forums knows exactly how to answer it, because it is clear and specific.

### Clarity

Make sure there are no ambiguities in your question. There should be one way of interpreting it, and it should be clear, understandable, and not too complex. Here are two more examples:

> "Calculating Averages in Ruby Name Error"
>
> "I have this array: [1, 2, 3, 4] and a hash {1: "one", 2: "two", 3: "three", 4: "four"}. If I want to replace the array numbers with the hash variable, how would I do that?"

Which one is bad? Both of them! The first one is incomprehensible and ambiguous. It suffers from being extremely unclear and extremely unspecific. The last one, while it is specific, is still ambiguous and almost too specific to be clear. The person could have asked: "How to replace the elements of an array with the values of a hash in Ruby"

Again, this last question is much more digestible. It is clear, unambiguous, and specific without being overwhelming with unnecessary details.

### Relevance

This last category is a bit trickier. Basically, an asker should ask a question that adds value to his or her understanding of a concept, and they should know their audience - who they are asking. In most cases, such as on Stack Overflow, this is a wold-wide network of brilliant programmers. Don't waste their time asking irrelevant or overly basic questions.

> "When was Ruby invented?"
>
> "What is the difference between an integer and a float?"

If you are seeking a fact, Google it. Why ask a team of programmers a meta-fact about Ruby that warrants, literally, a one-word response? It's not worth their time, and it's certainly not an efficient use of your time, either! And how about the second example? It's not quite as bad, but again, this is a very basic question that you are better off discovering for yourself through your own research. Read about what an integer is, what a float is, and try working with them. If you come across a specific problem regarding the use of integers and floats in a program, *that's* the time to ask a question.


I know I may have veered a bit into what makes a good question on the Internet, but the basic tenets still apply to questions asked in the physical world.
