# Functional Programming (FP)

Functional Programming is a programming paradigm that takes functions as the core and mathematical thinking as the guidance. It regards functions as first-class citizens, advocates immutable data and pure functions, and avoids complex state changes and side effects.

In recent years, functional programming ideas have been widely integrated into mainstream languages. Python, Java, JavaScript and other languages have added a large number of functional features, which have become an indispensable supplement to modern development.

## Core Idea
Functional programming originates from mathematical logic calculation. Its core concept is to regard the whole program as a combination of functions. The output of a function only depends on the input parameters, without relying on external global variables.

Core design concepts:
- Take function as the smallest independent unit
- Minimize variable state changes
- Deduplicate business logic through function combination
- Focus on "what to implement", not "how to implement"

## Core Features
### 1. Pure Function
A pure function has no side effects. Under the same input parameters, it must produce fixed output results. It does not modify external data, nor does it depend on uncertain external environment.

### 2. Immutability
Advocate immutable data objects. Once the data is created, it cannot be modified. If adjustment is needed, new data will be generated to avoid hidden dangers caused by state confusion.

### 3. First-Class Function
Functions can be assigned to variables, passed as parameters, returned as return values, and stored in data structures, which greatly improves code flexibility.

### 4. No Side Effects
All data changes are predictable. The function will not modify global variables, operate files or databases at will, ensuring the stability of program operation.

## Advantages
- The logic is concise and the amount of code is greatly reduced
- The program is stateless, which is convenient for concurrent and parallel processing
- Pure functions are easy to test and debug
- Suitable for data processing, stream calculation and scene analysis

## Disadvantages
- It is inconsistent with people’s daily logical thinking habits
- Excessive use will reduce code readability
- Immutable design may bring additional memory overhead
- Not friendly to complex business processes with frequent state changes

## Typical Application Scenarios
- Data cleaning, statistical analysis and numerical calculation
- Front-end state management and reactive programming
- Stream processing, big data calculation and distributed tasks
- Tool class development and general data conversion logic

## Mainstream Language Support
- Native strong support: Haskell, Scala
- Partial integration support: Python, Java, Go, JavaScript
- Common tools: lambda, map, filter, reduce

## Interview Key Points
Interviewers often examine the concepts of pure functions, side effects and the difference between functional programming and object-oriented programming. In actual development, most projects adopt a mixed paradigm, combining OOP business modeling with FP data processing to give play to their respective advantages.
