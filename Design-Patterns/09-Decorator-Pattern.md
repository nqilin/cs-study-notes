# Decorator Pattern
## Overview
The Decorator Pattern is a structural pattern that dynamically adds new functions to objects without modifying the original structure. It provides flexible function expansion capabilities compared with inheritance.

Decorators wrap the original object and enhance functions layer by layer, realizing dynamic, stacked function expansion.

## Core Intent
- Expand object functions dynamically without modifying source code
- Replace static inheritance with dynamic combination
- Support layered superposition of multiple enhanced functions
- Comply with Open Closed Principle

## Core Composition
1. Abstract Component: Define original object public interface
2. Concrete Component: Original basic object
3. Abstract Decorator: Hold component object and implement component interface
4. Concrete Decorator: Specific function enhancement class

## Application Scenarios
- Need to dynamically add/remove object functions
- Multi-layer function superposition requirements
- Avoid creating a large number of functional subclasses by inheritance
- Function enhancement without changing original code

## Pattern Advantages
- Dynamic function expansion at runtime
- Flexible combination and layered superposition
- No modification to original business code
- Better scalability than inheritance

## Pattern Disadvantages
- Multi-layer wrapping leads to complex object structure
- Too many decoration classes increase system complexity
- Easy to produce excessive decoration

## Decorator vs Inheritance
| Dimension | Inheritance | Decorator |
|-----------|-------------|-----------|
| Expansion method | Static compile-time expansion | Dynamic runtime expansion |
| Flexibility | Fixed and single | Flexible and stackable |
| Code quantity | Massive subclasses | Independent decoration classes |

## Interview Key Points
- Core advantages of decorator pattern
- Difference between decorator and proxy pattern

## Summary
The decorator pattern focuses on dynamic function enhancement. It is the best solution for layered function expansion and widely used in stream processing, permission enhancement and business function wrapping.
