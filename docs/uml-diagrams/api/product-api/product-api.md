# Product API

This document describes the public and administrative endpoints available in the Product API.  
The Product API handles product and category data, and serves both client-facing and admin interfaces.

---

## Endpoints

| Method | Path                                                   | Description                | Used by       |
|--------|--------------------------------------------------------|----------------------------|---------------|
| GET    | [/api/private/v1/products](private/v1/get-products.md) | Get list of products       | Clients / UI  |
| GET    | /api/private/v1/products/{id}                          | Get product details        | UI / Services |
| GET    | /api/private/v1/categories                             | Get list of categories     | UI            |
| GET    | /api/private/v1/products/popular                       | Get popular products       | UI            |
| POST   | /api/private/v1/products                               | Create a new product       | Admin Panel   |
| PUT    | /api/private/v1/products/{id}                          | Update an existing product | Admin Panel   |
| DELETE | /api/private/v1/products/{id}                          | Delete a product           | Admin Panel   |

---
[App features and requirements](docs/requirements.md)
## Notes

- Methods POST/PUT/DELETE require admin-level permissions (e.g., `ROLE_ADMIN`)

---

## Used By

- **Client Web UI** — for browsing and searching the catalog
- **Admin Interface** — for managing the product catalog
- **Order Service** — to validate product details during order creation
- **Cart Service** *(optional)* — for verifying product availability or metadata