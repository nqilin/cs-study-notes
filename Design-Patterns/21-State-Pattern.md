# State Pattern
## Overview
The State Pattern is a behavioral pattern specially used to solve complex state switching business. It encapsulates different state behaviors into independent state classes, and the object behavior changes dynamically with state switching.

It replaces massive if-else state judgment logic with object state switching.

## Core Intent
- Solve bloated multi-state conditional judgment
- Encapsulate independent state behaviors
- Realize dynamic state switching and behavior change
- Simplify complex state transition logic

## Core Composition
1. Context: Business object containing state
2. Abstract State: Unified state abstract interface
3. Concrete State: Specific independent state class

## Application Scenarios
- Business with numerous complex states
- Frequent state switching and different state behaviors
- Workflow and order status management

## Pattern Advantages
- Eliminate massive if-else judgment
- Comply with Single Responsibility Principle
- Convenient for new state expansion

## Pattern Disadvantages
- Each state corresponds to one class, increasing class quantity
- Increased state management complexity

## State vs Strategy Pattern
| Dimension | State Pattern | Strategy Pattern |
|-----------|---------------|------------------|
| Switch trigger | Internal automatic state transition | External manual strategy selection |
| Correlation | States are mutually restricted | Strategies are independent |

## Interview Key Points
- Difference between state pattern and strategy pattern

## Summary
The state pattern is the best optimization scheme for multi-state complex business, completely replacing traditional conditional branch judgment.
