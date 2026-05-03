# Adapter Pattern
## Overview
The Adapter Pattern is a classic structural design pattern. It converts the interface of an existing class into another interface expected by clients, enabling incompatible interfaces to work together.

It is essentially a conversion and compatibility layer, which does not change the original business logic, but solves interface mismatch problems.

## Core Intent
- Solve interface incompatibility between old and new systems
- Realize reuse of existing incompatible components
- Shield interface differences and unify external calling specifications
- Avoid modifying stable old business code

## Two Implementation Types
### 1. Class Adapter
Implement target interface and inherit adapted class, complete interface conversion through inheritance.

### 2. Object Adapter
Hold adapted object instances internally, complete conversion through combination. More flexible and more widely used in enterprise development.

## Core Composition
1. Target Interface: Standard interface expected by clients
2. Adaptee: Existing incompatible old interface/class
3. Adapter: Conversion middleware connecting target and adaptee

## Application Scenarios
- Old system interface cannot match new business specifications
- Third-party open source library interface is inconsistent with project standard
- Need to reuse stable legacy code without modification
- Unified external entry for heterogeneous interfaces

## Pattern Advantages
- Comply with Open Closed Principle
- Realize compatibility of heterogeneous interfaces
- Protect stable legacy code
- Low transformation risk and high reusability

## Pattern Disadvantages
- Increase system adaptation layers
- Excessive use will increase system complexity
- Need additional adaptation development workload

## Interview Key Points
- Difference between class adapter and object adapter
- Actual business adaptation scenarios

## Summary
The adapter pattern is a universal compatibility solution. It does not change business functions, but solves interface incompatibility problems through middleware conversion, which is the most commonly used pattern for legacy system reconstruction.
