# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# Functional programming - part 1
---
Earlier in the semester I briefly introduced the difference between [imperative](https://en.wikipedia.org/wiki/Imperative_programming) and [declarative](https://en.wikipedia.org/wiki/Declarative_programming) programming paradigms and how we can distinguish between them: Specifically, **imperative** programs describe _how_ a program should execute, while **declarative** programs describe _what_ a program entity is - without specifying how to obtain it. This difference between the _how_ and the _what_ is most apparent in control flow - imperative programs use control flow (e.g. `if - else` statements, `switches`, `for` loops and `while` loops), whereas declarative programs _do not_.

[Functional programming](https://en.wikipedia.org/wiki/Functional_programming) paradigm is a subset of declarative paradigm, so among other qualities (discussed next week!), functional programs take the same approach of describing the _what_ and not the _how_ of a program. This week I'll be introducing a number of foundational concepts of functional programming, and we'll examine a number of functional methods, like `map`, `reduce`, `filter` and `fold` that we can use in many cases in replacement of traditional imperative `for` loops to produce cleaner and more readable code.

If you're coming at this idea from pure imperative (and likely [OOP](https://en.wikipedia.org/wiki/Object-oriented_programming)) experience, you might wonder how one could construct a program without specifying any control flow. The key thing to remember is that the _how_ part is there somewhere, but it's deep in the _language_ implementation, meaning the language is built in such a way that _allows_ a declarative versus an imperative approach. This question of implementation is precisely why you can't just choose to use any programming paradigm you want with any programming language - only languages that support specific paradigms can be used to program in that paradigm. 

However, the distinction made here is somewhat specific to general purpose programming languages (i.e. languages that can be used for building software in a variety of contexts and platforms). Other, non-general purpose languages, like HTML (and markup languages in general) could also be considered declarative. Both Google and Apple now provide declarative UI frameworks for Android and iOS mobile app development in [Jetpack Compose](https://developer.android.com/jetpack/compose) and [SwiftUI](https://developer.apple.com/xcode/swiftui/), respectively. 

On the other hand, purely functional languages, like [Haskell](https://www.haskell.org/), are the nearly-exclusive domain of academia and programming language research. However, in recent years, more and more developers have been adopting at least a partial functional approach (see the slew of ['functional programming' YouTube videos](https://www.youtube.com/results?search_query=functional+programming) as evidence). We're going to see why this is as we explore functional more deeply in the coming weeks. 

[Kotlin is a multi-paradigmatic language](https://kotlinlang.org/education/why-teach-kotlin.html), and [many modern languages are also multi-paradigmatic](https://en.wikipedia.org/wiki/Comparison_of_multi-paradigm_programming_languages). In Kotlin, the most commonly used paradigms are likely OOP and functional, but for the most part the functional uses of the language are restricted to some functional features relating to collections and collection types that we'll learn about this week.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jA-bqiuBvbc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Collections
[Collections](https://kotlinlang.org/docs/collections-overview.html) in Kotlin are provided by the standard library (meaning, they're not part of an extra library that needs to be imported into your code). Collections provide a way to combine multiple items, or _elements_, of a single kind, or _type_, in one place. Collections are fundamental components of all general purpose programming languages, but the ways in which collections are organized and used differ greatly.

### Arrays vs Collections
We've been making a lot of use of `Array`s in this course so far, with the occasional `List` thrown in for convenience. The first thing to note about this is that `Array`s are _not_ `Collection`s - not, at least, in the sense of the standard library. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/R49QOXylPiw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Lists and mutable lists
The most commonly used type of collection in Kotlin are `List`s and `MutableList`s. `List` is a generic type that inherits from the more general `Collection` type, but with the difference that in `List`s order is important. Therefore, `List`s are indexed and so work in very much the same way that an Array does. `MutableList`s are `List`s with write abilities.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JBdnxZLRrEU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Other collection types
There are a few other  collections that are useful for specific applications: `Set` is an unordered collection of _distinct_ elements; and `Map` collects key-value pairs, where keys are guaranteed unique. Both `Set` and `Map` also have mutable versions: `MutableSet` and `MutableMap`.

> **Important note**: `Map` (the collection type) and `map` (the method/function - see below) are *different* things! It's easy to confuse them, since we're introducing them at the same time, but just remember that case matters here! Uppercase M `Map` is always the collection type and lowercase m `map` is always the function.

<iframe width="560" height="315" src="https://www.youtube.com/embed/gGcxsaaFeDw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Collection methods
There is a long list of methods common to `Collection` and it's inheritors, and also to `Array`. Many of these methods are _generic_ methods - recognizable by the generic type declarations in their signatures: 

```kotlin
fun <T> List<T>.elementAt(index: Int): T
```

`elementAt` is a method that could be applied to any `List` containing elements of type `T`, and returns an element of type `T`. If you look at the [standard library entry for `elementAt`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/element-at.html) you'll see there are generic methods for `Arrays`s, `Iterable`s and for `List`s (though there are also many specific methods for use with the primitive array types).

Generic collection methods like `elementAt` (and related `Array` implementations) provide a common base of functionality that can be relied upon no matter which collection type you might be using (with some obvious difference across subtypes, and of course between mutable and immutable subtypes). Familiarizing yourself with these methods will make you a much more effective Kotlin programmer. 

There are many more methods available on collections than could reasonably be covered here. You will find below a list of some of the methods you might be more likely to use in the short term:

### Common collection methods

<iframe width="560" height="315" src="https://www.youtube.com/embed/B-OxYRGCfLA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Manipulation 
- [chunked](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/chunked.html)
- [drop](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/drop.html)
- [reversed](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/reversed.html)
- [shuffled](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/shuffled.html)
- [slice](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/slice.html)
- [sorted](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/sorted.html)
- [take](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/take.html)

#### Element identification
- [binarySearch](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/binary-search.html)
- [contains](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/contains.html)
- [distinct](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/distinct.html)
- [elementAt](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/element-at.html)
- [first](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/first.html)
- [indexOf](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/index-of.html)
- [last](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/last.html)
- [random](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/random.html)
- [windowed](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/windowed.html)

### Functional methods
<iframe width="560" height="315" src="https://www.youtube.com/embed/OONbQk5kli4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Functional
- [filter](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/filter.html)
- [flatten](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/flatten.html)
- [fold](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/fold.html)
- [map](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/map.html)
- [reduce](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/reduce.html)

# Homework and activities
---

## Programming challenges 6
Follow the directions below to access the first set of programming challenges and complete them according to the directions.

**NOTE:** Some of the problems this week will look familiar! The goal is to revisit some problems we originally coded in imperative style, and rewrite them in a declarative/functional style so that you can compare.

### To access the programming challenges:
1. Log into GitHub with your chosen account.
2. [Click here](https://classroom.github.com/a/ti-W0808) to accept the assignment from GitHub Classroom.
3. Once the assignment has been generated you may clone it locally to your harddrive.
4. Follow the directions in the programming challenge `README.md` file to complete the assignment.

## Recommended practice exercises
Since we're moving to a different programming paradigm, I will directly recommend some good practice problems to look at this week.


### learnCS.online
- [Small Word Filter With List](https://www.learncs.online/practice/kotlin/small-word-filter-with-list/challen@illinois.edu)
- [List to Set](https://www.learncs.online/practice/kotlin/list-to-set/challen@illinois.edu)
- [Word Count with Map](https://www.learncs.online/practice/kotlin/word-count-with-map/challen@illinois.edu)
- [Word Lengths with Map](https://www.learncs.online/practice/kotlin/word-lengths-with-map/challen@illinois.edu)
- [String Duplicate Words Ignore Case](https://www.learncs.online/practice/kotlin/string-duplicate-words-ignore-case/challen@illinois.edu) - Note that you can complete this using either `Set` _or_ `Map`!
- [Double Up](https://www.learncs.online/practice/kotlin/double-up/taylor@msoe.edu)

Also the [map-reduce-filter](https://www.learncs.online/lessons/kotlin/streams#map-reduce-filter) lesson is a great one to help you wrap your head around functional, if you need some additional support (and practice).

### Kotlin by Example
- [List](https://play.kotlinlang.org/byExample/05_Collections/01_List)
- [Set](https://play.kotlinlang.org/byExample/05_Collections/02_Set)
- [Map](https://play.kotlinlang.org/byExample/05_Collections/03_Map)
- [filter](https://play.kotlinlang.org/byExample/05_Collections/04_filter)
- [map](https://play.kotlinlang.org/byExample/05_Collections/04_map)


### Kotlin Koans
- [Filter; map](https://play.kotlinlang.org/koans/Collections/Filter%20map/Task.kt)

You can also try some other Kotlin Koans in the [Collections](https://play.kotlinlang.org/koans/Collections/Introduction/Task.kt) section, if you like. Just be aware that some solutions require some language features we haven't yet discussed.