# Template Method Pattern
## Overview
The Template Method Pattern is the most basic behavioral pattern based on inheritance. It defines a fixed algorithm skeleton in the parent class and delays the implementation of variable steps to subclasses.

It realizes fixed process, variable details, standardizing the overall business process while retaining flexible expansion capabilities.

## Core Intent
- Define unified fixed business process skeleton
- Let subclasses implement personalized variable steps
- Standardize overall process and expand local details
- Avoid repeated process code

## Core Composition
1. Abstract Template Class: Define fixed skeleton and abstract steps
2. Concrete Subclass: Implement personalized business steps

## Application Scenarios
- Business process is fixed with variable internal details
- Multiple businesses share consistent overall process
- Need unified process specification and personalized expansion

## Pattern Advantages
- Standardize unified business process
- Reduce repeated process code
- Comply with Open Closed Principle

## Pattern Disadvantages
- Inheritance-based, static binding
- Subclass implementation depends on parent skeleton

## Interview Key Points
- Core scenario of template method pattern
- Difference with strategy pattern

## Summary
The template method pattern relies on inheritance to realize process unification and detail differentiation, which is the basic pattern for standardized process design.
