# API Endpoints

Complete reference for all API endpoints available in WikiFruity.

## Base URL

```
https://api.wikifruity.com/v1
```

## Authentication

All API requests require authentication using an API key:

```http
Authorization: Bearer YOUR_API_KEY
```

## Endpoints

### Content Endpoints

#### GET /content

Retrieve content from the wiki.

**Request:**
```http
GET /content?page=home
```

**Response:**
```json
{
  "page": "home",
  "content": "...",
  "updated_at": "2024-01-01T00:00:00Z"
}
```

#### POST /content

Create or update wiki content.

**Request:**
```http
POST /content
Content-Type: application/json

{
  "page": "new-page",
  "content": "Page content here"
}
```

**Response:**
```json
{
  "success": true,
  "page": "new-page",
  "created_at": "2024-01-01T00:00:00Z"
}
```

### Search Endpoints

#### GET /search

Search for content across the wiki.

**Request:**
```http
GET /search?q=query&limit=10
```

**Response:**
```json
{
  "results": [
    {
      "page": "page-name",
      "title": "Page Title",
      "excerpt": "..."
    }
  ],
  "total": 42
}
```

## Rate Limits

API requests are limited to:
- 100 requests per minute for authenticated users
- 10 requests per minute for unauthenticated requests

## Error Codes

| Code | Description |
|------|-------------|
| 400 | Bad Request |
| 401 | Unauthorized |
| 404 | Not Found |
| 429 | Too Many Requests |
| 500 | Internal Server Error |

## Related Documentation

- [API Overview](overview.md) - Introduction to the API
