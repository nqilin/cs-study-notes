# Command Pattern
## Overview
The Command Pattern is a behavioral pattern that encapsulates requests into independent command objects. It converts request sending, receiving and execution into independent modules to realize complete decoupling.

This pattern turns discrete business operations into executable command objects, supporting recording, queuing, undo and redo operations.

## Core Intent
- Encapsulate business requests as independent command objects
- Decouple requester and executor
- Support command queuing, logging and rollback
- Standardize unified operation invocation

## Core Composition
1. Command Abstract Class: Unified command execution interface
2. Concrete Command: Specific business command
3. Invoker: Command trigger and scheduler
4. Receiver: Real business executor

## Application Scenarios
- Need undo/redo operation
- Command queuing and batch execution
- Operation log recording and playback
- Remote command call

## Pattern Advantages
- Complete decoupling of operation and execution
- Support command expansion and combination
- Convenient implementation of rollback mechanism
- Unified scheduling of multiple operations

## Pattern Disadvantages
- Each operation corresponds to one command class, leading to class proliferation
- Increased system abstraction complexity

## Interview Key Points
- Core decoupling idea of command pattern
- Undo and redo implementation principle

## Summary
The command pattern converts behavior into object, realizing object-oriented management of business operations, which is the core pattern of operation rollback and task scheduling.
