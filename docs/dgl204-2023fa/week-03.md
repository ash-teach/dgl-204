# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# More fundamental syntax, null safety and idiomatic Kotlin
---
This week is the last week of introduction and review, culminating with the introduction of basic class syntax, destructuring and some commonly used `String` methods. Up to and including this point much of what you've learned should be relatively familiar, or at least relatable in some way to a prior language that you have studied. That said, just reading and watching isn't enough when it comes to programming, so hopefully you've been taking advantage of all the recommended exercises as well.

You can find the code for this week's lectures on in the [f23-week03 repository](https://github.com/nic-dgl-204-fall-2023/f23-week03) on our [DGL 204 organization](https://github.com/nic-dgl-204-fall-2023).

## Classes and basic syntax
Kotlin class syntax is very stripped down and efficient. If you come from the world of Java, you'll quite quickly see the advantage of working with Kotlin. The video below demonstrates some of the differences between the standard class declaration in Java and various approaches to class declaration in Kotlin, from highly verbose, to extremely concise. We'll tend to favour a concise coding style as we progress through the semester, so make sure you have a good understanding of how these relate. 

You can consider this video a very light introduction to object-oriented programming (OOP), which we'll dive into over a couple weeks starting in week 4. Many of the conventions of OOP in Kotlin will be familiar to those of you who have programmed in Java, but there may be some of you with alternative backgrounds who have less familiarity. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/BoVarI5C2yk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Destructuring & strings
Destructuring is a really cool language feature that you may have seen elsewhere (possibly [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)). While you probably won't have a huge number of use-cases for it in the short term, it's a great feature to have in your back pocket.

`String` manipulation is a huge part of any programming langauge; some even languages make text processing their primary purpose (see [Perl](https://en.wikipedia.org/wiki/Perl)). Kotlin is no exception to this, as evidenced by the _very_ long list of [`String` methods available](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/) in the standard library. I encourage you to take a scan through this list of methods so that you understand the scope of what is available. In short though, almost anything you might consider doing with a `String` has already been implemented in the standard library - so don't reinvent the wheel! 

We'll more deeply examine some `String` methods as we move into functional programming paradigm after midterms.
<iframe width="560" height="315" src="https://www.youtube.com/embed/eRvez-DQoHs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Null safety 
Null and nullable identifiers are a pretty important concept to wrap your head around, as you'll definitely work increasingly with nullables, especially as you move towards interfacing with remote endpoints, or with 3rd part APIs. This video is fairly light introduction, but nullables will continue to feature throughout the semester.

<iframe width="560" height="315" src="https://youtube.com/embed/fR85bHuOhLE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Idiomatic Kotlin
We're going to try as much as possible to write our Kotlin code according to published [conventions](https://kotlinlang.org/docs/coding-conventions.html) and [idioms](https://kotlinlang.org/docs/idioms.html). While I don't expect you to have a full grasp of all coding conventions from today forward, I want you to be aware of the resources available (see the links in this paragraph and the video below), and especially to take advantage of all the hints, suggestions and warnings (and errors!) surfaced in IntelliJ IDEA as you write, compile and run your code. Taking an intentional approach to writing clean code is one of the most important things you can do to improve your skills as a developer.

<iframe width="560" height="315" src="https://youtube.com/embed/gHf05A_kbCY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Homework and activities
---
## Programming challenges 
Follow the directions below to access the first set of programming challenges and complete them according to the directions.

### To access the programming challenges:
1. Log into GitHub with your chosen account.
2. [Click here](https://classroom.github.com/a/zRHdBuBX) to accept the assignment from GitHub Classroom.
3. Once the assignment has been generated you may clone it locally to your harddrive.
4. Follow the directions in the programming challenge `README.md` file to complete the assignment.

## Recommended practice exercises
The following exercises are highly recommended as practice problems to get you oriented to using Kotlin.
### learnCS.online
- [Object with Public Value](https://www.learncs.online/practice/kotlin/object-with-public-value/challen@illinois.edu#object-with-public-value)
- [Kotlin Simple Object Field](https://www.learncs.online/practice/kotlin/kotlin-simple-object-field/challen@illinois.edu)
- [Kotlin Simple Object Field 2](https://www.learncs.online/practice/kotlin/kotlin-simple-object-field-2/challen@illinois.edu)
- [Simple Object Method](https://www.learncs.online/practice/kotlin/simple-object-method/challen@illinois.edu#simple-object-method)
- [Simple Object Method 2](https://www.learncs.online/practice/kotlin/simple-object-method-2/challen@illinois.edu)
- [Object with Public Value](https://www.learncs.online/practice/kotlin/object-with-public-value/challen@illinois.edu)
- [Counter Object](https://www.learncs.online/practice/kotlin/counter-object/challen@illinois.edu)
- [Back Around](https://www.learncs.online/practice/kotlin/back-around/challen@illinois.edu?returnTo=strings)
- [Endsly](https://www.learncs.online/practice/kotlin/endsly/challen@illinois.edu?returnTo=strings)
- [Make Tags](https://www.learncs.online/practice/kotlin/make-tags/challen@illinois.edu?returnTo=strings)
- [Middle Two](https://www.learncs.online/practice/kotlin/middle-two/challen@illinois.edu?returnTo=strings)
- [Missing Char](https://www.learncs.online/practice/kotlin/missing-char/challen@illinois.edu?returnTo=strings)
- [Repeat End](https://www.learncs.online/practice/kotlin/repeat-end/challen@illinois.edu?returnTo=strings)
- [String Equality](https://www.learncs.online/practice/kotlin/string-equality/challen@illinois.edu#string-equality)
- [Array Max (1D)](https://www.learncs.online/practice/kotlin/array-max-1d/challen@illinois.edu?returnTo=null)
- [Array Sum (Two Dimensional)](https://www.learncs.online/practice/kotlin/array-sum-two-dimensional/challen@illinois.edu?returnTo=null)
- [String Rotate Right](https://www.learncs.online/practice/kotlin/string-rotate-right/challen@illinois.edu#string-rotate-right)


### Kotlin by Example
- [Classes](https://play.kotlinlang.org/byExample/01_introduction/05_Classes)
- [Named Arguments](https://play.kotlinlang.org/byExample/08_productivity_boosters/01_namedArguments)
- [String Templates](https://play.kotlinlang.org/byExample/08_productivity_boosters/02_String%20Templates)
- [Destructuring Declarations](https://play.kotlinlang.org/byExample/08_productivity_boosters/03_Destructuring%20Declarations)
- [Null Safety](https://play.kotlinlang.org/byExample/01_introduction/04_Null%20Safety)

### Kotlin Koans
- [Named arguments](https://play.kotlinlang.org/koans/Introduction/Named%20arguments/Task.kt)
- [Default arguments](https://play.kotlinlang.org/koans/Introduction/Named%20arguments/Task.kt)
- [Triple-quoted strings](https://play.kotlinlang.org/koans/Introduction/Triple-quoted%20strings/Task.kt)
- [String templates](https://play.kotlinlang.org/koans/Introduction/String%20templates/Task.kt)
- [Nullable types](https://play.kotlinlang.org/koans/Introduction/Nullable%20types/Task.kt)