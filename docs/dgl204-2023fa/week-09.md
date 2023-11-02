# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# Functional programming - part 2
---
Week 9 code used in the videos below can be found [here](https://github.com/nic-dgl-204-fall-2023/f23-week09).

We learned last week that [declarative programming paradigm](https://en.wikipedia.org/wiki/Declarative_programming) is distinguished from [imperative programming paradigm](https://en.wikipedia.org/wiki/Imperative_programming), in part, by it's lack of _control flow_. As a subset of declarative paradigm, functional programming can be distinguished from object-oriented programming in the same way.

> **Note:** The true distinction between imperative and declarative is much more complex than simply the presence (or not) of control flow, and much of this is rooted in the theoretical underpinnings of computer science and programming language design. For our purposes, however, the control flow distinction is sufficient. 

This lack of control flow can feel quite foreign to programmers accustomed to the OOP approach; fortunately, as a multi-paradigmatic language Kotlin can accommodate both an OOP approach and a functional approach _simultaneously_. 

In the example below, a functional method is embedded _inside_ OOP-style branching control flow:
```kotlin
val list = listOf(1, 2, 3, 4, 5)
var newList = listOf<Int>()

if (!list.isEmpty()) {
    newList = list.filter { it > 2 }
}
```
You might also be interested to know that the above can be written with an `if` expression, rather than a statement. However, this does require the addition of an `else null` block since `if` expressions must be exhaustive:
```kotlin
val list = listOf(1, 2, 3, 4, 5)
val newList = if (list.size > 0) list.filter { it > 2 } else null
```
On the other hand, we can also embed OOP-style branching control _inside_ a functional method call:
```kotlin
val list = listOf(1, 2, 3, 4, 5)
val newestList = list.filter { it ->
    if (it < 3) println(it)
    it > 2
}
```
> **Note:** You might notice that the _content_ of this function is a little different from the first example. Watch the video below to see why.

Clearly, we can mix paradigms - we're not stuck with using just one. And it might even be more natural for you to think of an example with looping control flow (i.e. a `for` or `while` loop) that calls on a functional method.

This week we'll look at three characteristics of [functional programming paradigm](https://en.wikipedia.org/wiki/Functional_programming) that place it in opposition to OOP paradigm: _first-class (and higher-order) functions_, _pure functions_ and _referential transparency_. These three characteristics are not the only characteristics that define the functional paradigm, but they are the three most useful to us. We've also already seen all three of these characteristics in action, although we haven't yet put a name to them, nor have we clearly stated their importance. That's our task for this week.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YKLUmOFLJtg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

I'll stress again that although we use functional _tools_ when programming in Kotlin, we're not typically programming a purely functional way (although that is possible!) Nevertheless, understanding in detail how functional is different from OOP will help you decide on how best to use it in your programs: Sometimes using a functional tool will be the right decision, and sometimes not, but you won't really know unless you have a good base knowledge of what functional _is_.

## First-class functions
[First-class functions](https://en.wikipedia.org/wiki/First-class_function) are functions that can be used in the same way that a primitive value, like `Int` or `String`, might be used. In other words, first-class functions can be stored in variables, can be passed as arguments to functions, and can even be returned as values from other functions. This is very important for functional paradigm, since [higher-order functions](https://en.wikipedia.org/wiki/Higher-order_function), which take _other_ functions as parameters (think of those we've already seen - `map`, `filter`, `reduce`, etc.) are typically used in place of OOP-style control flow to produce composite effects.

Function _composition_ occurs when a function is passed as an argument to another function. In many situations this type of approach can both reduce code complexity and increase readability, as well as make code more portable. Nearly all the functional methods that we have previously looked at employ function composition.

### Lambdas
Functions that are passed as arguments to other functions are often written in a stripped down, or sparse, syntax in order to make writing such functions easier and more readable. These types of functions are referred to as [_lambdas_](https://en.wikipedia.org/wiki/Anonymous_function) in Kotlin (and in Java, since their introduction in Java 8), and often as _anonymous functions_ in many languages (in particular, JavaScript refers to these types of functions _only_ as anonymous functions, and does not use the term lambda).

<iframe width="560" height="315" src="https://www.youtube.com/embed/eNUDimgI_gk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> #### __Type theory and mathematical underpinnings__
> The underlying theory of types from which the term 'lambda' derives isn't really important to our understanding of the use of anonymous functions, nor of our understanding of functional paradigm. However, if you are interested in where the term comes from, it's based on the [lambda calculus](https://en.wikipedia.org/wiki/Lambda_calculus) developed by mathematician Alonzo Church in the 1930s. The development of lambda calculus precedes the development of modern computers by several decades, and modern approaches to programming by a few more. 
>
>Nevertheless, as the discipline of computer science progressed, the lambda calculus was recognized as being _effectively_ a programming language. Together with the notion of _types_ (yes, like `Int` or `String`, etc.) lambda calculus forms the basis of [type theory](https://en.wikipedia.org/wiki/Type_theory), which can be thought of as model of computation that resulted in declarative and functional programming.

## Pure functions and side effects
The functional style of programming typically produces [pure functions](https://en.wikipedia.org/wiki/Pure_function), meaning the arguments passed to the function completely determine the function output: Aside from the expected results, there are no additional results or output from the function; there are no additional processes in the function that produce unexpected (or _non-deterministic_ results); and the types of the function parameter list is identical to the type of the function return value. 

Any function that produces results outside of the stated purpose of the function (and, by _stated_ I mean what can be read off the function signature) is said to produce _side effects_. This could include state changes (i.e. the change of value of a local or global variable), or remote input to the function from outside the program, or even something as simple as a `print` statement. In functional programming side effects are to be avoided, as they have the result of making a program less verifiable, and thus less rigorous and more prone to bugs.

<iframe width="560" height="315" src="https://www.youtube.com/embed/8L75iNShW3g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### `Unit` return type
At this stage you may have seen a few Kotlin functions with a return type of `Unit`, or perhaps you've noticed `Unit` in some print statements that you've produced. `Unit` is effectively an _empty_ type (similar to `Void` in Java), and it is _primarily_ used to denote a function that has side effects. The important thing to note is that _every_ Kotlin function _must_ return something, so even when a function is declared without an explicit return type, that function will still return a `Unit`. Ideally, we would like to ensure _all_ our functions return sensible values based on the function parameter list, but that can't always be the case, so `Unit` is provided to ensure that a return is still produced.
## Referential transparency
[Referential transparency](https://en.wikipedia.org/wiki/Referential_transparency) is closely tied to the idea of pure functions and side effects. In short, a programming language _cannot be_ referentially transparent if it is not pure. A referentially transparent function is a pure function, as defined above, but the key point here is that the referentially transparent function is _deterministic_, meaning it always produces the same output for the same input, no matter if the function is run in a different environment or at a different time.

A slight nuance here is that reassignment of variables is not possible in a purely functional language. This is because in a referentially transparent system one must always be able to swap the name of an element with the associated value in any statement or expression and produce the same results; if variables can be reassigned, then this is not a reasonable assumption to make.

This idea is what makes [_immutability_](https://en.wikipedia.org/wiki/Immutable_object) in functional programming so important. Recall that in Kotlin most of our functional methods operate on collections, which encompass both mutable and immutable versions of `List`s, `Map`s and `Set`s. Recall as well that most of those functional methods `return` brand new collections, rather than modifying the existing collection - this is in service of the concept of immutability and referential transparency.

<iframe width="560" height="315" src="https://www.youtube.com/embed/fVNu8ohcojE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Homework and activities
---

## Programming challenges 7
Follow the directions below to access the first set of programming challenges and complete them according to the directions.

### To access the programming challenges:
1. Log into GitHub with your chosen account.
2. [Click here]() to accept the assignment from GitHub Classroom.
3. Once the assignment has been generated you may clone it locally to your harddrive.
4. Follow the directions in the programming challenge `README.md` file to complete the assignment.
