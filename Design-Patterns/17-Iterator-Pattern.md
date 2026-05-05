# Iterator Pattern
## Overview
The Iterator Pattern is a classic behavioral pattern. It provides a unified traversal interface for different aggregate data structures, shielding the internal structure differences of containers.

It enables clients to traverse container elements uniformly without understanding the underlying storage structure of containers.

## Core Intent
- Unify traversal rules of different containers
- Shield internal container structure details
- Decouple container storage and element traversal
- Provide consistent iterative access interface

## Core Composition
1. Iterator: Unified traversal abstract interface
2. Concrete Iterator: Specific traversal implementation
3. Aggregate: Container abstract interface
4. Concrete Aggregate: Specific data container

## Application Scenarios
- Different data containers need unified traversal
- Need to shield underlying container differences
- Custom collection container traversal

## Pattern Advantages
- Unified traversal specification
- Decouple container and traversal logic
- Convenient expansion of new traversal rules

## Pattern Disadvantages
- Increase iterator class quantity
- Redundant for simple containers

## Interview Key Points
- Core decoupling idea of iterator pattern

## Summary
The iterator pattern standardizes container traversal behavior and is the underlying design basis of all collection traversal mechanisms.
