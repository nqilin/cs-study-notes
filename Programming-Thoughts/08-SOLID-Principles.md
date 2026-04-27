# SOLID Principles

SOLID is a set of five classic object-oriented design principles summarized by the industry. It is the core standard for evaluating whether OOP code is standardized, reasonable and scalable. It is also a high-frequency knowledge point in technical interviews and enterprise code review.

Following SOLID principles can effectively reduce code coupling, improve reusability, and avoid various hidden dangers brought by later project iteration.

## 1. Single Responsibility Principle (SRP)
### Core Definition
A class or method should have only one single responsibility, and only focus on one type of business function.

### Core Meaning
- One unit corresponds to one business goal
- Avoid a single class mixing data processing, business judgment and output operation
- Reduce the impact of function modification and improve maintainability

### Common Mistake
A large number of heterogeneous logics are piled in one class. Modifying one function will affect multiple irrelevant businesses.

## 2. Open/Closed Principle (OCP)
### Core Definition
Software entities should be open for extension and closed for modification.

### Core Meaning
- When adding new functions, try to expand new code instead of modifying old code
- Use inheritance, interface and combination to realize function expansion
- Reduce the risk of modifying old code to trigger bugs

### Practical Value
Effectively avoid the collapse of stable business logic caused by iterative updates.

## 3. Liskov Substitution Principle (LSP)
### Core Definition
Subclasses can completely replace the parent class and run normally without changing the original program logic.

### Core Meaning
- Subclasses need to fully comply with the constraints of the parent class
- Do not arbitrarily overwrite and destroy the original logic of the parent class
- Ensure the consistency of upper-layer calling logic

## 4. Interface Segregation Principle (ISP)
### Core Definition
Split large and bloated general interfaces into multiple fine-grained independent interfaces.

### Core Meaning
- The interface should be refined and single-function
- The caller only needs to rely on the required interface, not redundant methods
- Avoid forced implementation of useless functions

## 5. Dependency Inversion Principle (DIP)
### Core Definition
High-level modules should not depend on low-level modules. Both should depend on abstract interfaces, not specific implementation classes.

### Core Meaning
- Face abstract programming, not face implementation programming
- Reduce the direct dependency between specific classes
- Improve the replaceability and scalability of underlying components

## Overall Summary Table
| Principle | Core Keyword | Solved Problem |
|-----------|--------------|----------------|
| SRP | Single responsibility | Bloated class & confusing logic |
| OCP | Extension first | Modification risk of old code |
| LSP | Subclass substitution | Inheritance logic confusion |
| ISP | Fine interface | Bloated redundant interface |
| DIP | Abstract dependency | High coupling between modules |

## Interview & Practical Suggestion
SOLID is not rigid constraints. In small projects, excessive adherence will lead to over-engineering.

The correct usage is:
- Strictly abide by it in medium and large enterprise projects
- Properly simplify in small tools and personal projects
- Take SOLID as the optimization direction in code reconstruction

Mastering SOLID principles is an important symbol for developers to move from simple code writing to standardized object-oriented design.
