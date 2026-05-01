# Simple Factory Pattern
## Overview
The Simple Factory Pattern is the most basic object creation design pattern. Although it is not included in the standard 23 GoF patterns, it is the basis of all factory patterns and is widely used in actual enterprise development.

This pattern encapsulates all object creation logic inside an independent factory class. External business code only needs to pass parameter types to obtain target objects, without caring about complex instantiation details.

## Core Intent
- Decouple object creation logic and business usage logic
- Centralize unified management of object initialization rules
- Avoid massive repeated object creation code in business layer
- Shield complex initialization parameters and creation processes

## Core Composition
The simple factory pattern consists of three fixed components:

| Component | Responsibility |
|-----------|----------------|
| Abstract Product | Define unified public interfaces for all products |
| Concrete Product | Specific implementation classes that inherit abstract products |
| Factory Class | Provide unified static methods to produce different product instances |

## Working Principle
1. All concrete products implement the same abstract interface
2. The factory class contains type judgment logic
3. Clients pass type identifiers to the factory
4. The factory creates and returns corresponding product objects according to input parameters

## Typical Application Scenarios
- A large number of similar subclasses need unified creation
- Object initialization process is complex and requires centralized management
- Business layer does not want to focus on object creation details
- System products are relatively fixed with few expansion requirements

## Pattern Advantages
- Realize separation of creation and usage
- Greatly reduce code duplication in business layer
- Standardize object creation specifications
- Reduce client code complexity

## Pattern Disadvantages
- The factory class undertakes all creation logic, violating Single Responsibility Principle
- Adding new products requires modifying factory judgment logic, violating Open Closed Principle
- The factory function is too single, poor in scalability
- Not suitable for systems with frequent product iteration

## Interview Core Points
- Differences between simple factory, factory method and abstract factory
- Why simple factory violates OCP
- Applicable boundary of simple factory in enterprise projects

## Summary
The simple factory is the entry-level factory pattern. Its core value is centralized decoupling. Due to poor scalability, it is only suitable for fixed and stable product systems, and needs to be upgraded to factory method pattern when business expands.
