# Stateless Design in REST
Stateless means:
**The server stores no client state between requests.**

Every request must include all information needed to process it.

## Why Stateless?
- Easy to scale across many servers
- Servers can restart without breaking users
- Works well with load balancers
- Required for microservices

## How It Works
1. User logs in → gets a token (JWT)
2. Client sends token in every request
3. Server verifies token and processes
4. No session stored on the server

## Example (Request Header)
```
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

## Enterprise Usage
All large-scale systems (Alibaba, cloud services, apps)
use stateless auth to support millions of users.

## Pro Tips
- Tokens > server sessions for modern apps
- Short-lived tokens are safer
- Never rely on server-side storage for user state
