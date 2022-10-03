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
We've already looked at [primary constructors](https://kotlinlang.org/docs/classes.html#constructors) in Kotlin. We can also declare [secondary constructors](https://kotlinlang.org/docs/classes.html#secondary-constructors) to allow for more flexibility in how class instances are created. Recall first of all that primary constructors have a concise syntax in Kotlin: 

```kotlin
class Person(name: String) {
    // Note that with this approach you have to pass the value stored in the parameter name to some other instance/member variable in the class
}
```

We can declare a constructor in the class signature and optionally declare constructor parameters as properties:

```kotlin
class Person(val name: String) {
    ...
}
```

But don't confuse constructor parameters with class properties as in the following example:

```kotlin
class Person(name: String) { /*...*/ }
val p = Person("Peter Piper")
println(p.name) // Unresolved reference! name is a parameter in this case
```

Take a look at the [Kotlin Coding Conventions for class headers](https://kotlinlang.org/docs/coding-conventions.html#class-headers) to see how best to format your class signature if it accepts many parameters.

Secondary constructors are declared using the `constructor` keyword. In fact, the Java-like constructor pattern we looked at in [Week 2](dgl204-2022fa/week-02?id=kotlin-classes-and-syntax) was really a secondary constructor in disguise (because we hadn't declared a primary constructor in the class header at all). Secondary constructors *must* at some point call the primary constructor:

```kotlin
class Person(val name: String) { 
    	constructor(name: String, age: Int) : this(name) {
            ...      
        }
    }
```

See the video below for more details:

## Properties
[Properties](https://kotlinlang.org/docs/properties.html) are class level variables, declared using `var` or `val`. As we've seen in the examples above Kotlin provides a convenient syntax for declaring these directly in the primary constructor as part of a class header.   
### Getters and setters
Properties can optionally be given custom [getters and setters](https://kotlinlang.org/docs/properties.html#getters-and-setters), depending on how they were declared: mutable `var` properties can have both a getter and a setter, whereas an immutable `val` can have only a getter. To declare a custom getter or setter write the `get()` or `set()` methods, indented below the property declaration:

```kotlin
val fullname: String
    get() = "$name $surname"

var bothTrue: Boolean
    get() = left && right
    set(value) {
        ...
    }
```
Check out the video below for some demonstrations:

## Inheritance
The idea that classes in OOP languages can have subclasses is termed [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)) and is a key feature of OOP languages. Inheritance isn't the only defining feature of OOP, but some other key OOP concepts, like [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) and [polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science)), depend on inheritance for their meaning making inheritance one of the more important concepts.

The inheritance chain allows the properties and behaviour of a parent class to be passed down to one or more child classes. Different approaches to inheritance permit different class elements to be passed down; sometimes full behaviours and state are passed along, and sometimes simply method signatures are passed along, ensuring that child classes are guaranteed to implement certain desired behaviour. 

Classes declared in Kotlin are *not* inheritable, called `final`, by default. The `open` keyword is used to make classes and their members inheritable, while the `override` keyword must be used when declaring a member of the same name in the child class as in the parent class:

```kotlin
open class Parent() {
    open fun printName() {
        println("I'm a parent!")
    }
}

class Child(): Parent() {
    override fun printName() {
        println("I'm a child!")
    }
}
```
An alternative approach to declaring a class `open` is to use the `abstract` keyword, which permits the creation of a base class that acts as a contract for subclasses: `abstract` classes have *no method implementations*, meaning they contain only method signatures. Properties in `abstract` classes can hold state (meaning, they can be initialized), or they can be declared `abstract` themselves:

```kotlin
abstract class Parent() {
    val name: String = "Parent"
    abstract val age: Int
    abstract fun printName() 
}

class Child(override val age: Int): Parent() {
    override fun printName() {
        println("I'm a $age year old child - not a $name!")
    }
}
```
The video below demonstrates some simple aspects of inheritance:

## Interfaces
[Interfaces](https://kotlinlang.org/docs/interfaces.html) are another tool of inheritance with a couple differences from the standard class-based inheritance: 

- Interfaces are lighter weight than classes - they cannot hold state or contain any implementations - so in this sense they can be used as a pure contract to bind their inheritors to certain behaviour.  
- Subclasses can inherit from only *one* other class, but any class can inherit from as many interfaces as necessary. 

Students are often confused about when to use an interface versus when to use a class to model inheritance. If you think about interfaces in one of the two following ways it might help: 

- An interface is literally an interface between a resource and your class - in other words, the interface provides the behaviour necessary to access a resource in a particular way. 
- An interface is a conceptual way to add additional qualities to a class without burdening a parent class with unnecessary behaviour. 

Watch the video below for more examples:


# The Kotlin - Java relationship

# Homework and activities