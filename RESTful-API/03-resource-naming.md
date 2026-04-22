# Resource Naming Best Practices
URL design is the face of your API.
Professional naming shows experience and clean architecture.

## Core Rules
1. Use **plural nouns** for collections
   - Good: `/users`
   - Bad: `/getUser`, `/userList`

2. Use hierarchy for relationships
   - Good: `/posts/{id}/comments`

3. Use lowercase and hyphens
   - Good: `/user-profiles`
   - Bad: `/userProfiles`, `/UserProfiles`

4. No verbs in URLs
   - Good: `/users`
   - Bad: `/createUser`, `/deletePost`

## Example Structure
- GET `/products` – list all products
- GET `/products/12` – get one product
- POST `/products` – create product
- PUT `/products/12` – fully update
- DELETE `/products/12` – delete

## Enterprise Style
Companies like ByteDance, Tencent, and Shopify use clean, consistent URL structures
to support hundreds of internal services.

## Pro Tips
- Keep URLs simple and logical.
- Avoid deep nesting beyond 2 levels.
- Versioning can be added: `/v1/products`
