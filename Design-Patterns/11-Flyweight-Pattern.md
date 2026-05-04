# Flyweight Pattern
## Overview
The Flyweight Pattern is a structural pattern optimized for system memory resources. It reuses existing object instances through object pooling, avoiding frequent creation and destruction of a large number of similar objects.

Its core is object reuse and shared cache, which greatly reduces system memory overhead.

## Core Concept
### Intrinsic State
Fixed, shareable internal object state, unchanged with business scenarios.

### Extrinsic State
Dynamic, unshareable external state, changes with business scenarios, passed in externally.

## Core Intent
- Cache reusable objects centrally
- Reduce the number of object instances in memory
- Distinguish shared and non-shared states
- Optimize system memory resource overhead

## Core Composition
1. Flyweight Abstract Class: Define shared object interface
2. Concrete Flyweight: Reusable shared object
3. Flyweight Factory: Central cache factory for managing object pools
4. Unshared Concrete Flyweight: Non-shared individual object

## Application Scenarios
- A large number of similar objects exist in the system
- Most object states can be extracted as shared intrinsic states
- Frequent object creation leads to high memory consumption
- Scenarios requiring object pooling and caching

## Pattern Advantages
- Massively reduce memory object quantity
- Reduce object creation and GC overhead
- Improve system operating efficiency

## Pattern Disadvantages
- Need to distinguish internal and external states, increasing business complexity
- Additional cache maintenance overhead
- Not suitable for completely different objects

## Interview Key Points
- Intrinsic and extrinsic state definition
- Application scenarios of flyweight pattern

## Summary
The flyweight pattern is a typical resource optimization pattern. It maximizes object reuse through pooling cache and state splitting, and is widely used in thread pools, connection pools and resource caching scenarios.
