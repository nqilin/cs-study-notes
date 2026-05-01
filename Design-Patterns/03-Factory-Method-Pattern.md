# Factory Method Pattern
## Overview
The Factory Method Pattern is a standard GoF creational pattern, optimized and upgraded based on the simple factory pattern. It solves the Open Closed Principle violation problem of simple factory through factory abstraction.

Different from simple factory’s centralized creation, factory method delegates product creation to independent sub-factories, realizing one factory corresponding to one product.

## Core Intent
- Solve the scalability defects of simple factory
- Comply with Open Closed Principle: expand new products without modifying old code
- Further decouple product creation and business logic
- Decentralize factory responsibilities to avoid bloated single factory class

## Core Composition
Four core components constitute the factory method pattern:

| Component | Function |
|-----------|----------|
| Abstract Product | Define unified product specification interface |
| Concrete Product | Specific product implementation class |
| Abstract Factory | Define unified factory production interface |
| Concrete Factory | Independent sub-factory for producing single specific product |

## Working Principle
1. Extract abstract factory interface to standardize production behavior
2. Each concrete factory is only responsible for producing one corresponding product
3. When new products are added, only new product classes and corresponding factory classes need to be created
4. No modification to existing factory and product code

## Application Scenarios
- The system needs to expand product types frequently
- Complex object creation logic requires independent management
- Need to ensure high scalability of business system
- Strictly follow object-oriented design principles

## Pattern Advantages
- Perfectly comply with Open Closed Principle
- Comply with Single Responsibility Principle (single factory single product)
- High system scalability and flexibility
- Low coupling between modules

## Pattern Disadvantages
- Greatly increase project class volume, causing code proliferation
- Each product corresponds to one factory, increasing development cost
- Too many abstract layers, slightly improved learning cost

## Difference vs Simple Factory
| Dimension | Simple Factory | Factory Method |
|-----------|----------------|----------------|
| Scalability | Poor, modify old code for new products | Strong, expand new code only |
| Responsibility | Centralized and bloated | Decentralized and single |
| OCP Compliance | Violate | Comply |
| Class Quantity | Few | More |

## Interview Key Points
1. What problem does factory method solve compared with simple factory?
2. What are the usage scenarios of factory method pattern?

## Summary
Factory method is the standard factory creation mode. It sacrifices a small amount of code simplicity in exchange for excellent scalability and compliance with design principles, which is the most commonly used factory pattern in medium and large enterprise projects.
