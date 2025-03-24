# GET /api/private/v1/products

---
- [Product API methods](../../product-api.md)
- [History of Changes](#history-of-changes)
- [Summary](#summary)
- [Request](#request)
- [Response](#response)
- [Possible Response Codes](#possible-response-codes)
- [Examples](#examples)
    - [Request Example](#request-example)
    - [Response Example](#response-example)

---

## 🕘 History of Changes

| Date       | Author          | Change Description |
|------------|-----------------|--------------------|
| 2025-03-22 | Dmitriy Zheltov | Initial creation   |

---

## Summary

Returns a list of available products for display in the catalog or search results.  
Used by public-facing UI (web, mobile) to render product listings.

---

## Request

No request body is required.

### Query Parameters (optional)

| Field Name | Type   | Required | Description                                         |
|------------|--------|----------|-----------------------------------------------------|
| page       | int    |          | Page number for pagination                          |
| size       | int    |          | Number of products per page                         |
| categoryId | int    |          | Filter by category                                  |
| sort       | string |          | Sorting rule (e.g., `price_asc`, `popularity_desc`) |

---

## Response

Returns a list of products with basic details.

| Field Name  | Type    | Required | Description               |
|-------------|---------|----------|---------------------------|
| id          | int     | true     | Unique product identifier |
| name        | string  | true     | Product name              |
| description | string  |          | Short product description |
| price       | decimal | true     | Current product price     |
| popularity  | decimal |          | Popularity score          |
| imageUrl    | string  |          | Image URL                 |
| category    | string  | true     | Product category name     |

Response is a JSON array of these product objects.

---

## Possible Response Codes

| resultCode | Description                 |
|------------|-----------------------------|
| 200        | Success — products returned |
| 400        | Invalid query parameters    |
| 500        | Internal server error       |

---

## Examples

### Request Example

```http request
GET /api/private/v1/products?page=1&size=2
```

### Response Example

```json
[
  {
    "id": 1,
    "name": "Red Toaster",
    "price": 29.99,
    "category": "Appliances",
    "description": "A stylish red toaster",
    "popularity": 4.8,
    "imageUrl": "https://example.com/images/toaster.jpg"
  },
  {
    "id": 2,
    "name": "Blue Kettle",
    "price": 19.99,
    "category": "Kitchen",
    "description": "Electric blue kettle with LED",
    "popularity": 4.5,
    "imageUrl": "https://example.com/images/kettle.jpg"
  }
]
```
