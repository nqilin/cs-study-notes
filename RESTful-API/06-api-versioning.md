# API Versioning
APIs change over time.
Versioning prevents breaking old clients.

## Common Versioning Strategies
### 1. URL Versioning (Most Popular)
- `/v1/users`
- `/v2/users`

Simple, clear, widely used in enterprise.

### 2. Header Versioning (Clean)
```
Accept: application/json; version=1
```

### 3. Query Parameter (Not Recommended)
- `/users?version=1`

## Enterprise Practice
Big companies keep old versions alive for **3–12 months**
before deprecating them.

## Versioning Rules
- Do not change response structure without version change
- Document all differences between versions
- Mark old endpoints as deprecated

## Pro Tips
- Start with `/v1/` on day one.
- Plan versioning before launching public APIs.
- Never delete old endpoints suddenly.
