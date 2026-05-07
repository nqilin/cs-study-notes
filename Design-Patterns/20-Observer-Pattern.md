# Observer Pattern
## Overview
The Observer Pattern is one of the most widely used behavioral patterns. It defines a one-to-many dependency relationship. When the state of the observed object changes, all dependent observer objects are automatically notified and updated.

It realizes the classic publish-subscribe idea and is the foundation of event-driven programming.

## Core Intent
- Establish one-to-many automatic linkage
- Decouple event publisher and subscriber
- Realize automatic notification and state update
- Support dynamic addition and deletion of observers

## Core Composition
1. Subject (Observable): Observed publisher
2. Observer: Subscriber monitoring object

## Application Scenarios
- Event notification and message push
- State change automatic linkage update
- System monitoring and callback notification
- Front-end responsive data update

## Pattern Advantages
- Low coupling between publisher and subscriber
- Dynamic expansion of observers
- Automatic event linkage update

## Pattern Disadvantages
- Uncontrolled notification chain may cause update storm
- Synchronous notification may block business process

## Interview Key Points
- Observer pattern implementation principle
- Difference between observer and mediator pattern

## Summary
The observer pattern is the core of event-driven design, widely used in message notification, monitoring systems and responsive programming.
