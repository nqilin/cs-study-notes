# Object-Oriented Programming (OOP)

Object-Oriented Programming is the most mainstream programming paradigm in current enterprise development. It takes "object" as the core carrier, abstracts things in the real world into classes and objects, and completes business interaction through the combination of attributes and behaviors.

Most large-scale commercial software, web back-end systems and client applications are designed and developed based on OOP. It is also the key content of university professional courses and technical interviews.

## Core Idea
OOP abstracts all things in the business scene into objects. Each object contains two core parts:
- Attribute: Describe the static data characteristics of things
- Behavior: Describe the dynamic functions and methods of things

The whole system is composed of multiple independent objects. The business process is completed through message passing and method calls between objects.

## Four Core Characteristics
### 1. Abstraction
Extract the core characteristics of things, ignore irrelevant details, and define standardized abstract classes and templates.

### 2. Encapsulation
Hide the internal data and complex implementation details of the object, and only expose safe and external calling interfaces to prevent arbitrary modification of core data.

### 3. Inheritance
Subclasses can reuse the attributes and methods of the parent class, expand personalized functions on the basis of the parent class, and reduce redundant code.

### 4. Polymorphism
Different subclasses rewrite the same parent class method to realize different execution effects, which improves the flexibility and scalability of the system.

## Advantages
- Close to real-world business cognition, easy to model complex scenarios
- High code reusability through inheritance and combination
- Low coupling and strong maintainability through encapsulation
- Convenient for team division of labor and modular collaborative development
- Easy to expand new business roles and new functions

## Disadvantages
- The learning cost is high, and the abstract concept is difficult for beginners to understand
- A large amount of basic template code is required, and the development speed of small functions is slow
- Excessive object design will lead to over-engineering and performance loss

## Applicable Scenarios
- Large and medium-sized enterprise-level projects
- Complex business relationships and multi-role interaction systems
- Software that needs long-term iteration and function expansion
- Team collaborative development and multi-module complex systems

## OOP vs POP
| Dimension | OOP | POP |
|-----------|-----|-----|
| Core carrier | Object & Class | Function & Process |
| Data relation | Data and behavior are integrated | Data and logic are separated |
| Coupling degree | Low coupling | High coupling |
| Expansion ability | Strong scalability | Weak scalability |
| Main application | Large complex system | Small script & simple process |

## Interview Focus
In technical interviews, the four major characteristics of OOP, the difference between OOP and POP, and the application scenarios of OOP are high-frequency questions. Mastering OOP thinking is not only to write class syntax, but to learn to use object-oriented modeling to sort out complex business relationships.
