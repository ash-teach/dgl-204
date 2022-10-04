# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# A deeper look at some Kotlin-specific language features
---
We're continuing our review of fundamentals this week, with an eye towards some more uniquely Kotlin (or, at least, *not* Java) features of the language. Our main focus this week is some basic object-oriented programming syntax (to be expanded on in *much* more detail in weeks to come) and Kotlin `string`s and string manipulation. We'll also take a look at some things that are likely new to you, and need to be introduced early, but don't really fit under any other topic heading, namely: destructuring (a *very* useful tool!) and `null` safety (an extremely important topic!)

## Creating a new IntelliJ IDEA project
<iframe width="560" height="315" src="https://www.youtube.com/embed/7wXqAi6GDu0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Kotlin classes and syntax
<iframe width="560" height="315" src="https://www.youtube.com/embed/BoVarI5C2yk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Declaring arrays
<iframe width="560" height="315" src="https://www.youtube.com/embed/N2sXdAVlFmo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Destructuring & strings
<iframe width="560" height="315" src="https://www.youtube.com/embed/eRvez-DQoHs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Null safety 
<iframe width="560" height="315" src="https://www.youtube.com/embed/8YIJxehv0PA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Kotlin core development and evolution
---
## Kotlin history and evolution
Kotlin is a young, but constantly evolving language. If you want to learn a bit about Kotlin's history, you can check out the [Kotlin Wikipedia article](https://en.wikipedia.org/wiki/Kotlin_(programming_language)), also did you know Kotlin is [named after an island](https://en.wikipedia.org/wiki/Kotlin_Island)? Kinda like [Java](https://en.wikipedia.org/wiki/Java). [Or maybe not...](https://www.infoworld.com/article/2077265/so-why-did-they-decide-to-call-it-java.html)?

Anyway, despite Kotlin being a young language it's garnered a lot of interest and a pretty massive following. Likely in large part due to [Google's first-class support of Kotlin for Android development](https://blog.jetbrains.com/kotlin/2017/05/kotlin-on-android-now-official/). The broader [Kotlin community](https://kotlinlang.org/community/) provides a significant level of support in the form of [feature proposals](https://github.com/Kotlin/KEEP/tree/master/proposals), [feature development](https://kotlinlang.org/docs/contribute.html#contribute-to-the-compiler-and-standard-library), [user testing](https://kotlinlang.org/docs/contribute.html#participate-in-early-access-preview), [documentation and tutorials](https://kotlinlang.org/docs/contribute.html#contribute-to-the-documentation), and [bug reporting and fixes](https://github.com/JetBrains/kotlin/pulls).

Major decisions relating to the language are handled by the core Kotlin [Language Committee](https://kotlinfoundation.org/structure/) and the Lead Language Designer, [Roman Elizarov](https://github.com/elizarov). Decisions are guided by three principles outlined in the [Kotlin Evolution](https://kotlinlang.org/docs/kotlin-evolution.html) documentation. They are:
* **Keep the language modern over the years.**
* **Stay in the constant feedback loop with the users.**
* **Make updating to new versions comfortable for the users.**

## The Kotlin roadmap and future development
The cool thing about Kotlin (and other open source languages that are developed transparently) is that you can get in on the ground floor of both development and testing. You can always sign up for the [early access preview](https://kotlinlang.org/docs/eap.html) to try out new features before they're fully ready for primetime, or you can keep abreast of planned upcoming feature changes via the [Kotlin Docs - Roadmap](https://kotlinlang.org/docs/roadmap.html) and the associated [YouTrack Kotlin Roadmap](https://youtrack.jetbrains.com/agiles/153-1251/current). The following videos present the Kotlin roadmap and YouTrack board:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Iqkb6IAAi0w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/r3_j3yJUtm8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Homework and activities
---
For each row below you should read/examine/experiment with the given Kotlin by Example column, then attempt the corresponding exercises given in the LearnCS.online column, and finally the exercises given in the Kotlin Koans column.

After you've completed the exercises in the table below please watch the lectures in the LearnCS.online [Data Modelling 1](https://www.learncs.online/lessons/kotlin/datamodeling1) section. The lectures will take you through the process of building a TicTacToe class with all supporting game functionality (less the UI elements). You should also try the exercises.

We'll continue the reflective process with homework 2, using the same process as before with a [new Google document](https://docs.google.com/document/d/1nwhdbNO-d61THPKKknbNUmMVi4C-LDRmwsPPN9p7F0I/edit?usp=sharing). However, this new Google doc contains a section for you to write a paragraph or two reflecting on your experience in listening to the TicTacToe lectures. Follow the link for more details. 

When you've completed all the work submit your checklist/reflective document to the appropriate dropbox on Brightspace. Check out the video below for a bit of a homework walkthrough:

<iframe width="560" height="315" src="https://www.youtube.com/embed/xzXS43K55yo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<table class="topics">
    <tr>
        <th>Kotlin by Example</th>
        <th>LearnCS.online</th>
        <th>Kotlin Koans</th>
    </tr>
    <tr>
        <td>
            <li><a href="https://play.kotlinlang.org/byExample/01_introduction/05_Classes">Classes</a></li>
            <li><a href="https://play.kotlinlang.org/byExample/08_productivity_boosters/01_namedArguments">Named Arguments</a></li>
             <li><a href="https://play.kotlinlang.org/byExample/08_productivity_boosters/03_Destructuring%20Declarations">Destructuring Declarations</a></li>
        </td>
        <td>
            <li><a href="https://www.learncs.online/practice/kotlin/kotlin-simple-object-field">Kotlin Simple Object Field</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/kotlin-simple-object-field-2">Kotlin Simple Object Field 2</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/simple-object-method-kotlin">Kotlin Simple Object Method</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/simple-object-method-2-kotlin">Kotlin Simple Object Method 2</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/toggler-object">Toggler Object</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/counter-object">Counter Object</a></li>
        </td>
        <td>
            <li><a href="https://play.kotlinlang.org/koans/Introduction/Named%20arguments/Task.kt">Named arguments</a></li>
        </td>
    </tr>
    <tr>
        <td>
            <li><a href="https://play.kotlinlang.org/byExample/08_productivity_boosters/02_String%20Templates">String Templates</a></li>
        </td>
        <td>
            <li><a href="https://www.learncs.online/practice/kotlin/reformat-a-phone-number">Reformat a Phone Number</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/string-reverse">String Reverse</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/string-flip-halves">String Flip Halves</a></li>
        </td>
        <td>
            <li><a href="https://play.kotlinlang.org/koans/Introduction/String%20templates/Task.kt">String templates</a></li>
            <li><a href="https://play.kotlinlang.org/koans/Introduction/Triple-quoted%20strings/Task.kt">Triple-quoted strings</a></li>
        </td>
    </tr>
    <tr>
        <td>
            <li><a href="https://play.kotlinlang.org/byExample/01_introduction/04_Null%20Safety">Null Safety</a></li>
        </td>
        <td>
            <li><a href="https://www.learncs.online/practice/kotlin/array-max-1d">Array Max (1D)</a></li>
            <li><a href="https://www.learncs.online/practice/kotlin/array-count-greater-than-1d">Array Count Greater Than (1D)</a></li>
        </td>
        <td>
            <li><a href="https://play.kotlinlang.org/koans/Introduction/Nullable%20types/Task.kt">Nullable types</a></li>
        </td>
    </tr>
</table>
<br>

# Assignment due & upcoming assignments
---
## Independent Kotlin Overview Research - Part 1
The deadline for this assignment is Sept. 26th. For such an early assignment - and considering that you had a week off! :) - I would expect that you should have it completed on-time, but if you're a bit behind don't stress too much. Nevertheless, do try to get it submitted as soon as possible so that I can review and send feedback as soon as possible. 

## Independent Kotlin Overview Research - Part 2
Part 2 of the research overview assignment is due Oct. 7 and you should get started working on it as soon as you get feedback from me on part 1. The goal of this assignment is to take a deeper dive into the repository you identified in part 1 in the context of both [idiomatic](https://kotlinlang.org/docs/idioms.html) and [coding conventions](https://kotlinlang.org/docs/coding-conventions.html). Check out the video below for more info:

<iframe width="560" height="315" src="https://www.youtube.com/embed/xqeMLPNdyhI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>