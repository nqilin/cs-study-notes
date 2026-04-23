# Request Validation
Validation is the first defense against invalid data and attacks.
All enterprise APIs validate inputs *before* business logic.

## What to Validate
- Required fields exist
- Data type is correct (string, number, boolean)
- Format is valid (email, phone, date)
- Value ranges and lengths
- No dangerous characters

## Example with FastAPI + Pydantic
```python
from pydantic import BaseModel, EmailStr, constr

class UserCreate(BaseModel):
    # Must be valid email format
    email: EmailStr
    # Min 8, max 50 characters
    username: constr(min_length=3, max_length=50)
    # Password at least 8 chars
    password: constr(min_length=8)

# Validate automatically
@app.post("/users")
def create_user(user: UserCreate):
    return {"message": "User created safely"}
```

## Enterprise Scenario
APIs are attacked automatically by bots.
Validation blocks most malicious traffic early.

## Pro Tips
- Never trust frontend validation alone.
- Validate everything on the backend.
- Return clear error messages for debugging.
