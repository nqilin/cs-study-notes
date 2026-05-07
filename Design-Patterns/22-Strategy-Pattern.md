# Strategy Pattern
## Overview
The Strategy Pattern is a classic behavioral optimization pattern. It encapsulates multiple independent algorithm strategies into separate classes, enabling dynamic switching of different algorithms according to business scenarios.

It eliminates a large number of branch judgment statements and standardizes algorithm expansion.

## Core Intent
- Encapsulate multiple alternative business algorithms
- Realize dynamic switching of strategies
- Eliminate redundant if-else and switch branches
- Decouple business algorithm and main process

## Core Composition
1. Strategy Abstract: Unified algorithm interface
2. Concrete Strategy: Independent algorithm implementation
3. Context: Strategy scheduling container

## Application Scenarios
- Multiple alternative business algorithms
- Need dynamic switching of calculation rules
- Complex business rule judgment and selection

## Pattern Advantages
- Clean up massive branch judgment logic
- Comply with Open Closed Principle
- Independent algorithm expansion and maintenance

## Pattern Disadvantages
- Increase strategy class quantity
- Clients need to understand strategy differences for selection

## Interview Key Points
- Core optimization idea of strategy pattern
- Distinction from state pattern

## Summary
The strategy pattern focuses on external optional algorithm switching, which is the most commonly used pattern to optimize multi-rule branch business.
