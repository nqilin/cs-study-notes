# Pagination, Filtering, Sorting
APIs must handle large datasets efficiently.
Without these features, apps will crash.

## Pagination
```
/posts?page=1&limit=20
```
- page: which page
- limit: items per page

## Sorting
```
/posts?sort=created_at&order=desc
```

## Filtering
```
/posts?status=published&category=tech
```

## Example Response Structure
```json
{
  "data": [...],
  "pagination": {
    "total": 120,
    "page": 1,
    "limit": 20,
    "pages": 6
  }
}
```

## Enterprise Usage
Used by Taobao, TikTok, Amazon product lists.

## Pro Tips
- Set a default limit (e.g., 20)
- Do not allow extremely large limits
- Validate sort/filter fields to avoid injection
