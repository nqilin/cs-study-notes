# Common Design Thoughts

In addition to basic thinking and OOP principles, there are a number of general design thoughts precipitated by the industry for a long time. These thoughts are not limited to a certain programming paradigm. They run through system design, module splitting, performance optimization and team collaboration, and are universal core knowledge for intermediate and senior developers.

## 1. Separation of Concerns
Separation of concerns is one of the most classic design thoughts. It requires splitting complex systems into multiple independent modules according to different responsibilities. Each module only focuses on its own professional field.

Typical separation methods:
- Separate data layer, business layer and presentation layer
- Separate core business and auxiliary tool logic
- Separate synchronous processing and asynchronous tasks

The core benefit is to isolate the impact of changes, so that the adjustment of a single module will not affect the overall system.

## 2. Low Coupling, High Cohesion
### High Cohesion
The internal elements of the same module are closely related, and the functions are highly concentrated. A module only completes related businesses to avoid miscellaneous logic.

### Low Coupling
The dependency between different modules is minimized. Modules communicate through unified abstract interfaces instead of directly relying on internal details.

This pair of standards is the most intuitive evaluation index of code structure quality in enterprise code review.

## 3. Fail Fast Thought
Fail fast means that once an error, illegal parameter or abnormal state is found, it will be intercepted and reported immediately, instead of continuing to run the wrong logic.

Specific performance:
- Verify input parameters at the method entrance
- Timely capture abnormal data and illegal status
- Avoid hiding errors through redundant compatibility logic

Fail fast can quickly locate problems in the early stage of operation and avoid the spread of hidden errors to the bottom layer.

## 4. Space-Time Trade-off
In program operation, time efficiency and memory space are often mutually restricted. Developers need to make reasonable trade-offs according to business characteristics.

Common strategies:
- Use more memory caching to reduce repeated calculation and improve speed
- Compress data storage to save space at the cost of calculation time
- Balance resource consumption according to server hardware conditions

## 5. Defensive Programming
Defensive programming requires developers to take the initiative to assume that various abnormal situations will occur, and make preventive design in advance.

Main measures:
- Rational use of exception capture and parameter judgment
- Avoid null pointer and illegal index access
- Do not trust external incoming data and interface parameters

## Core Contrast Table
| Design Thought | Core Goal |
|----------------|-----------|
| Separation of Concerns | Clear responsibility division |
| Low Coupling & High Cohesion | Optimize module collaboration |
| Fail Fast | Early error exposure |
| Space-Time Trade-off | Reasonable resource allocation |
| Defensive Programming | Improve program robustness |

These general design thoughts are invisible in daily coding, but they determine the long-term life cycle and maintenance cost of the project. Learning to take the initiative to apply these thoughts is an important breakthrough point for programmers to improve their comprehensive capabilities.
