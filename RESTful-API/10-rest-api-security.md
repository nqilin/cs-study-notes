# REST API Security Best Practices
Security is not optional in enterprise APIs.

## Top Security Rules
1. **Use HTTPS only**
   Encrypts all data in transit.

2. **Rate Limiting**
   Prevent brute force, scraping, and DDoS.

3. **Input Validation**
   Block malicious data.

4. **Authentication & Permissions**
   Ensure users only access their own data.

5. **Security Headers**
   - X-Content-Type-Options: nosniff
   - X-Frame-Options: DENY
   - Content-Security-Policy

6. **No Sensitive Data in URLs**
   Avoid tokens or passwords in path/query.

## Example Rate Limiting (FastAPI)
```python
from slowapi import Limiter
from slowapi.util import get_remote_address

limiter = Limiter(key_func=get_remote_address)

@app.get("/api/data")
@limiter.limit("100/minute")  # Max 100 requests per minute
def get_data():
    return {"data": "safe content"}
```

## Enterprise Reality
Hackers target APIs daily.
Without these protections, your system will be breached.

## Pro Tips
- Assume all inputs are dangerous
- Test APIs with security scanners
- Log all auth attempts and errors
