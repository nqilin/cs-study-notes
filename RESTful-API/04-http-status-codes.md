# HTTP Status Codes for REST APIs
Status codes tell clients whether a request succeeded or failed.
Using proper codes is required in enterprise development.

## Most Used Status Codes
### Success (2xx)
- 200 OK – Request successful
- 201 Created – Resource created
- 204 No Content – Deleted successfully

### Client Errors (4xx)
- 400 Bad Request – Invalid input
- 401 Unauthorized – Not logged in
- 403 Forbidden – Logged in but no permission
- 404 Not Found – Resource does not exist
- 429 Too Many Requests – Rate limited

### Server Errors (5xx)
- 500 Internal Server Error – Server crashed
- 502 Bad Gateway – Service unavailable

## Example Response
```json
// Example of 400 error response
{
  "error": "Validation failed",
  "details": {
    "email": "Must be a valid email address"
  }
}
```

## Enterprise Rule
Status code + message must match.
Do NOT return 200 OK for failed operations.

## Pro Tips
- Create a global error handler in your backend.
- Always return machine-readable errors.
- Frontend teams rely on correct status codes.
