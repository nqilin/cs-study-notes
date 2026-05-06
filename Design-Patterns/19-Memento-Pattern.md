# Memento Pattern
## Overview
The Memento Pattern is a behavioral pattern used for state backup and rollback. It captures the internal state of an object without exposing its internal structure and saves it externally to support subsequent state recovery.

It perfectly realizes the state snapshot and undo function of business objects.

## Core Intent
- Backup object historical state
- Support object state rollback and recovery
- Isolate state storage and business object
- Avoid exposing internal private state

## Core Composition
1. Originator: Business object with state
2. Memento: State snapshot backup object
3. Caretaker: Manager responsible for saving snapshots

## Application Scenarios
- Business data needs undo and rollback
- Need to save historical operation snapshots
- Document editing and data revision

## Pattern Advantages
- Complete state backup and rollback
- Isolate state data and business logic
- Protect object internal state privacy

## Pattern Disadvantages
- Continuous backup consumes memory resources
- Too many snapshot versions increase maintenance cost

## Interview Key Points
- State isolation and backup principle of memento pattern

## Summary
The memento pattern is a dedicated state rollback solution, focusing on safe backup and recovery of object historical state.
