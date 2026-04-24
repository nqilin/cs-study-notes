# Authentication & Authorization for REST
- **Authentication**: Who are you? (Login)
- **Authorization**: What can you do? (Permissions)

## Common Methods
### 1. JWT (Most Common)
- Stateless
- Works across services
- Used in mobile & web apps

### 2. API Keys (For server-to-server)
- Simple
- Secure when used with HTTPS

### 3. OAuth2.0 (For third-party login)
- Google, Facebook, GitHub login

## Example Auth Flow
1. User sends username / password
2. Server validates and returns JWT
3. Client includes JWT in every request
4. Server verifies JWT and checks permissions

## Enterprise Permission Model
Large companies use **RBAC**:
- Admin
- Editor
- User
- Guest

## Pro Tips
- Always use HTTPS
- Set short expiration for JWT
- Store tokens in HttpOnly cookies
- Apply least privilege principle
