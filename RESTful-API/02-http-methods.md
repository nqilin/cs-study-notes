# HTTP Methods in REST
REST uses standard HTTP methods to perform CRUD operations.
Using them correctly makes APIs predictable and professional.

## HTTP Methods Overview
| Method | Behavior | Use Case | Idempotent |
|--------|----------|----------|------------|
| GET    | Read data | Fetch resources | Yes |
| POST   | Create new | Add a record | No |
| PUT    | Full update | Overwrite a resource | Yes |
| PATCH  | Partial update | Change one field | No |
| DELETE | Remove | Delete a resource | Yes |

## What Idempotent Means
If you send the same request multiple times,
the result remains the same.
This is critical for reliable systems.

## Enterprise Usage
Big companies strictly enforce:
- GET never changes data
- POST only creates resources
- PUT replaces entire objects
- PATCH is used for small changes

## Pro Tips
- Never use GET for deleting or modifying data.
- Stick to these rules — frontend developers will thank you.
- In large teams, inconsistent methods cause serious bugs.
