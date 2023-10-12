# ![Programming for Mobile App Development](images/1366x768-kotlin2022_2.png )

# Data persistence with Ktor
---
This week we're building on our previous work with Ktor to take it one step further and add data persistence. The following video demonstrates a second tutorial to produce a version of the Ktor Journal site with a local database store provided by Exposed and H2. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/rTyeLC38DNc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Exposed database
[Exposed](https://github.com/JetBrains/Exposed) is a JetBrains-developed SQL library for Kotlin that permit database interactions either via the [Exposed DSL](https://github.com/JetBrains/Exposed/wiki/DSL) or via the [Exposed DAO](https://github.com/JetBrains/Exposed/wiki/DAO). You may recall that a DSL, or Domain-Specific Language, is a programming language built to address a very specific problem, or domain. A DAO, or Data Access Object, is a tool used to encapsulate database interactions and it might be familiar to you from DGL 114 and the [Room Persistence Library](https://developer.android.com/jetpack/androidx/releases/room).

For this project, we'll use the DAO approach. The DAO acts as an interface to the database and thus provides a layer abstraction between your app code and the database itself. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/UdJMqKHiv84" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### JDBC
JDBC, or [Java Database Connectivity](https://en.wikipedia.org/wiki/Java_Database_Connectivity), is a Java API that allows facilitates database connections to a variety of database types. Exposed uses JDBC because Kotlin is built on Java and because JDBC is a well-established API that is very broadly used. We'll be using the JDBC API [H2](https://h2database.com/html/main.html) in connection with Exposed. [JDBC Drivers](https://en.wikipedia.org/wiki/JDBC_driver) are used by a client application to ensure that it has the correct API on hand for communication with a remote database. These are typically defined by the server application and downloaded by the client application during the initial database connection. 

## Coroutines
[Kotlin documentation](https://kotlinlang.org/docs/coroutines-basics.html#your-first-coroutine) defines *coroutine* as "an instance of suspendable computation". For our purposes, we'll think of coroutines as a tool for handling potentially fallible network requests, although they do have an older history and a [broader applicability](https://en.wikipedia.org/wiki/Coroutine).

Kotlin coroutines are available in a [JetBrains developed library](https://kotlinlang.org/docs/coroutines-guide.html), so like Ktor, are not part of the Kotlin standard library. We'll most commonly see the use of coroutines via the [`suspend` function](https://kotlinlang.org/docs/coroutines-basics.html#extract-function-refactoring/).

<iframe width="560" height="315" src="https://www.youtube.com/embed/RqoiSehwdHQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Examining the database
[IntelliJ IDEA Ultimate](https://www.jetbrains.com/idea/) provides a [Database tool window](https://www.jetbrains.com/help/idea/database-tool-window.html) that can be used to inspect the contents of a database. If you are using IntelliJ IDEA CE then you can optionally use a third-party database tool, such as [DBSchema](https://dbschema.com/), to examine the contents of your database.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EHizbL9JtCs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


# Homework and activities
---
## Project 1
**Due** Oct. 25th at 11:59pm. [Click here](https://classroom.github.com/a/A1RmJEwr) to read assignment details and directions and to accept the assignment. 
## Recommended practice exercises
The main [Ktor](https://ktor.io/) site includes an [extensive set of sample applications](https://ktor.io/learn/). Most of these do not include any tutorial components, but the code is maintained and the sample applications should be buildable, if you'd like to examine them. Of particular interest are:
- \[**Simpler**\] [Chat](https://github.com/ktorio/ktor-samples/tree/main/chat) - A chat application written with Ktor using WebSockets and Sessions.
- \[**Challenging**\] [Full-stack multiplatform application](https://github.com/ktorio/ktor-samples/tree/main/fullstack-mpp) - A full-stack sample project for Ktor running as an embedded application and serving a static folder with kotlin-js code sharing code with the backend.
