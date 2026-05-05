# Chain of Responsibility Pattern
## Overview
The Chain of Responsibility Pattern is a behavioral design pattern. It connects multiple processing objects into a chain structure. The request is transmitted along the chain until a suitable processor processes it.

This pattern decouples request sender and request processor, and multiple objects can compete or cooperate to process requests.

## Core Intent
- Avoid tight coupling between request sender and receiver
- Multiple processors dynamically undertake request processing
- Realize flexible switching of processing responsibilities
- Support dynamic assembly of processing chain

## Core Composition
1. Abstract Handler: Define unified processing interface and chain passing rules
2. Concrete Handler: Specific processor implementation
3. Request: Business request object

## Application Scenarios
- Multiple processors can process the same request
- Request processing rules are dynamic and uncertain
- Permission verification chain, parameter check chain
- Log level processing, exception interception

## Pattern Advantages
- Decouple request sending and processing
- Dynamic assembly and adjustment of processing chain
- Flexible addition and deletion of processors
- Comply with Single Responsibility Principle

## Pattern Disadvantages
- Uncertain request processing result
- Long chain may affect processing efficiency
- Easy to cause request leakage

## Interview Key Points
- Responsibility chain passing mechanism
- Enterprise interceptor and validator chain scenarios

## Summary
The responsibility chain pattern realizes dynamic distributed processing of requests, which is widely used in interception verification, layered approval and multi-level rule judgment.
