# Proxy Pattern
## Overview
The Proxy Pattern is a classic structural design pattern. It provides a proxy object to control access to the original target object. All requests from clients pass through the proxy before accessing the real object.

The proxy object and the real object implement the same interface. The proxy can enhance, intercept and control access without changing the original object logic.

## Core Intent
- Control access to target objects
- Enhance functions before and after original method execution
- Shield internal target object details
- Implement unified pre-processing and post-processing logic

## Common Proxy Classification
1. Static Proxy: Manually write proxy class, fixed agent target
2. Dynamic Proxy: Automatically generate proxy class at runtime, flexible agent

## Core Composition
1. Abstract Subject: Unified business interface
2. Real Subject: Real target object
3. Proxy Subject: Proxy control object

## Application Scenarios
- Access control and permission interception
- Method pre-verification and post-log recording
- Remote service call proxy
- Delay loading of heavy objects
- Transaction and monitoring enhancement

## Pattern Advantages
- Enhance functions without modifying original code
- Decouple control logic and business logic
- Unified cross-cutting function processing
- Comply with Open Closed Principle

## Pattern Disadvantages
- Increase proxy layer overhead
- Excessive proxy layers affect execution efficiency

## Proxy vs Decorator
| Dimension | Proxy Pattern | Decorator Pattern |
|-----------|---------------|-------------------|
| Core purpose | Control object access | Enhance object functions |
| Focus | Access interception and control | Function superposition enhancement |

## Interview Key Points
- Difference between proxy and decorator
- Static proxy and dynamic proxy principle

## Summary
The proxy pattern focuses on access control and cross-cutting enhancement, which is the underlying core pattern of AOP programming idea.
