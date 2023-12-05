# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# Recursion and tail recursion
---
Recursion is when something is defined in terms of _itself_. Recursion is a pretty important topic in computer science and programming (although you could probably find disputes regarding its value in very specific situations), which is typically introduced in first-year computer science courses. In this course I will assume that you've seen recursion before, but we'll take some time to ground the idea in practical examples and then to introduce _tail recursion_, a specific type of optimized recursion that can be used in Kotlin. 

Recursion - as a thing defined in terms of itself - is related to the idea of a _circular definition_. For example, I could define the word _computer_ as _a thing that computes_. While this is technically accurate it's not very useful to anyone who doesn't understand the root word _compute_. a more helpful definition, especially for those learning a language, might be something like _a device used to run programs in a particular environment_. 

More broadly speaking, there are examples of recursion to be found in other disciplines as well, particularly in mathematics and logic. But there are processes in life - and humour - that might be thought of as recursive as well. The [Wikipedia page on recursion](https://en.wikipedia.org/wiki/Recursion) has some great examples, including: [sourdough starter](https://en.wikipedia.org/wiki/Recursion#Informal_definition), [visual recursion](https://en.wikipedia.org/wiki/Droste_effect), and [other humorous examples](https://en.wikipedia.org/wiki/Recursion#/media/File:Web_Page.png). See if you can think of any other activities that you conduct in life that could be thought of as recursive.

In recursion in computer science and programming we think less about _definition_ and more about _calling_ functions. So a recursive function is one that _calls_ itself (note: the definitional angle is still valid here: a function is defined by its associated code block). The key difference between the computer science understanding of recursion and the other examples above is in the concept of _termination_. In programming, we must ensure that our recursive functions terminate - meaning have a way to stop - else our programs could cause some significant memory errors. 

## The recursive problem space
Not all problems naturally lend themselves to a recursive solution. However, when a recursive solution _is_ available it tends to be "obvious"; or, at least, "obvious" to those who are experienced. 

It might take a bit of practice to recognize when a problem has recursive potential, but there are certain problems that can almost always be addressed by recursion: those involving recursive definitions (see below); anything involving traversing a graph; or problems that involving taking smaller and smaller chunks of some input.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/s4ExU4vaes8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> ### Recursive definitions
> There are some mathematics objects that are particularly well-known by their recursive definitions. Key among these are the [fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number) and [factorial](https://en.wikipedia.org/wiki/Factorial). 
>
> The _nth_ fibonacci number is calculated by summing the _previous two_ fibonacci numbers, and we _define_ the first two fibonacci numbers as 1 and 1. Thus from the above we know the third fibonacci is 2, the fourth is 3, the fifth is 5, the sixth is 8 and so on.  

## Refactoring for recursion
Recursion is all about breaking down a problem into a smaller chunks that can be repeated. In all cases, breaking down that problem into smaller chunks should _eventually_ result in the _base case_. If you're working towards a recursive solution the base case _should_ be fairly obvious (and that's a global obvious, in contrast to the "obvious" above); if the base case _isn't_ obvious, or is not easy to articulate, then a recursive solution might not be the right approach.

<iframe width="560" height="315" src="https://www.youtube.com/embed/zv7t7rwa87I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Tail recursion and optimality
Kotlin provides a special `tailrec` keyword that can be applied to recursive functions that meet certain conditions: the function must have a [tail call](https://en.wikipedia.org/wiki/Tail_call) as its final operation, and that tail call must not include any additional operations. In other words, the final `return` in the recursive function must *only* call the recursive function itself (with a new - smaller - input), with no other operations.

The benefit of using `tailrec` is that the Kotlin compiler will be able to optimize the compiled code (actually to a fast efficient `while` loop) that will have a lower time and space complexity than a comparable `while` or `for` loop, or even than a non-`tailrec` recursive function. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qlc7AoPHXhM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>