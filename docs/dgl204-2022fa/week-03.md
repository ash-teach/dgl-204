# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# Object-oriented programming - part 1
---
This week we step fully into the object-oriented programming paradigm. As a refresher from DGL 104, a [paradigm](https://en.wikipedia.org/wiki/Object-oriented_programming) is effectively a classification scheme for programming languages that helps to identify features common to that paradigm, and typically the execution model of the language. OOP is part of the broader set of paradigms known as [imperative programming](https://en.wikipedia.org/wiki/Imperative_programming), which basically means that when you program in an imperative style you are telling the computer how to proceed in a typically step by step fashion. The most obvious example is the typical `for` loop, like the following Kotlin loops that doubles the values in an array:

```kotlin
val numbers = intArrayOf(1, 2, 3, 4, 5)
val numbersDoubled = IntArray(5)
for ((index, value) in numbers.withIndex()) { // notice that (index, value) is *destructuring* the return from the .withIndex() method!
    numbersDoubled[index] = value * 2
}
```

You can see in the example above that with each iteration of the loop the program provides precise instructions on *how* the values should be modified (i.e. first grab the correct value from the array, multiply it by two, and assign it to the new array).

On the other hand, a [declarative program](https://en.wikipedia.org/wiki/Declarative_programming) declares *what* a program entity should be, rather than how to accomplish a thing on a step by step basis. For example, let's see how to accomplish the same doubling task above in a functional style:

```kotlin
val numbers = intArrayOf(1, 2, 3, 4, 5)
val numbersDoubled = numbers.map { number -> number * 2 }
```

Notice that in this case we *declare* what `numbersDoubled` is in relation to the originating `numbers` array (again with that funny `{ ... }` syntax, although you can see how it *maps* from the original `number` to `number * 2` for each element). You might be wondering how the program then knows to traverse the array and visit all its elements, as was explicit in the `for` loop. Well, the short answer is that that traversal has been implemented in the language, so you don't really need to worry about it for now (the short answer though, is that it's a [recursive](https://en.wikipedia.org/wiki/Recursion_(computer_science)) process). We'll talk more about [Functional programming](https://en.wikipedia.org/wiki/Functional_programming) in a few weeks.

Practically speaking, the distinction between the two isn't really that important for us on a day-to-day basis; it's mostly a theoretical construct, and many critics are correct when they note that most modern languages are [multi-paradigmatic](https://en.wikipedia.org/wiki/Comparison_of_multi-paradigm_programming_languages) anyway. In fact, that's part of the reason why we love Kotlin so much - we can write with equally facility in an OOP style, or in a functional style; both are valuable in a variety of instances, and you can mix paradigms at any point.

## Constructors
We've already looked at primary constructors in Kotlin. We can also declare secondary constructors to allow for more flexibility in how class instances are created:

```kotlin
val test
```

## Inheritance

## Properties

### Getters and setters

### Late initialization

## Interfaces

# The Kotlin - Java relationship

# Homework and activities