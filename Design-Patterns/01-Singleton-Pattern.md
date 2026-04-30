# Singleton Pattern
## Overview
The Singleton Pattern is the most fundamental creational design pattern. It ensures that a class has only one global instance throughout the entire application lifecycle and provides a unified global access point for this instance.

Unlike other complex patterns, the singleton pattern focuses on controlling thequantity of object instances. It is widely used in underlying framework design and daily business development, and it is a high-frequency basic question in technical interviews.

## Core Definition & Intent
### Core Definition
Restrict a class from instantiating multiple objects, ensure global uniqueness, and provide a static method to obtain the unique instance.

### Core Design Intent
- Avoid repeated creation of resource-intensive objects
- Maintain consistent global state and data
- Centralize global resource management
- Reduce unnecessary object creation overhead

## Three Essential Features
All standard singleton implementations must satisfy the following three constraints:
1. Private constructor: Prevent external classes from instantiating objects actively
2. Private static instance variable: Cache the only instance inside the class
3. Public static access method: Expose unified entry to get instance

## Common Implementation Solutions
### 1. Eager Initialization
Create the singleton instance when the class is loaded by JVM.

#### Advantages
- Naturally thread-safe
- Extremely simple implementation
- No concurrency bugs

#### Disadvantages
- Occupy memory in advance
- Resource waste if the instance is never used

### 2. Lazy Initialization
Instantiate the object only when the access method is called for the first time.

#### Advantages
- Implement lazy loading, save memory resources

#### Disadvantages
- Not thread-safe in multi-thread scenarios
- Multiple instances may be created concurrently

### 3. Double-Checked Locking (DCL)
Add thread synchronization locks and double instance judgment to optimize lazy initialization. It balances performance and thread safety, which is the most mainstream enterprise solution.

### 4. Static Inner Class
Use the static inner class loading mechanism to implement lazy loading without explicit locks. Low overhead and high stability.

### 5. Enum Singleton
The most secure singleton implementation. It inherently prevents reflection destruction and serialization replication, recognized as industry best practice.

## Application Scenarios
- Global configuration management class
- Database connection pool
- System log manager
- Thread pool scheduler
- Global cache container
- Framework context object

## Pattern Pros & Cons
### Advantages
- Greatly reduce system object creation overhead
- Ensure global unified state
- Simplify global resource invocation and management

### Disadvantages
- Introduce global coupling
- Violate single responsibility principle partially
- Poor scalability, difficult to expand functions
- Inconvenient for independent unit testing

## High-Frequency Interview Questions
1. What is the core principle of singleton pattern?
2. What is the difference between eager and lazy singleton?
3. Why does DCL need double judgment?
4. How to prevent singleton instance destruction?

## Summary
The singleton pattern is the foundation of all creational patterns. Instead of rigid coding, developers need to select different implementation methods according to business concurrency, memory cost and security requirements to achieve optimal design effects.
