# Mediator Pattern
## Overview
The Mediator Pattern is a behavioral pattern used to solve complex multi-object interaction coupling. It introduces an independent mediator object to uniformly schedule communication between multiple objects.

All objects no longer interact directly, but communicate through the mediator, realizing complete decoupling between interactive objects.

## Core Intent
- Solve complex multi-object mutual coupling
- Centralize interactive logic into mediator
- Decouple multiple interdependent objects
- Simplify multi-party communication logic

## Core Composition
1. Mediator Abstract Class: Unified scheduling interface
2. Concrete Mediator: Specific communication scheduler
3. Colleague: Interactive business object

## Application Scenarios
- Multiple objects depend on each other strongly
- Complex multi-party collaborative interaction
- Module message scheduling and forwarding

## Pattern Advantages
- Greatly reduce object coupling
- Centralized management of interactive logic
- Simplify complex multi-party collaboration

## Pattern Disadvantages
- Mediator bears all interactive logic, easy to become god class
- High mediator maintenance cost

## Interview Key Points
- Difference between mediator and observer pattern

## Summary
The mediator pattern centralizes decentralized multi-object interaction and is the core solution for complex multi-module collaboration.
