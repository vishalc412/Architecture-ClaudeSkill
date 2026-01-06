# API Documentation Workflow

Create comprehensive API documentation with **endpoint specifications**, **request/response schemas**, and optional **sequence diagrams** for complex flows.

---

## Mandatory Deliverables

**You MUST generate TWO files:**

1. **`[api-name]-api.drawio`** - API flow diagram (optional if simple)
2. **`[api-name]-api-docs.md`** - Complete API documentation

**The documentation file is ALWAYS required.**

---

## When to Use

- REST API documentation
- GraphQL API documentation
- Microservice API contracts
- OpenAPI/Swagger-style specs
- API design reviews
- Developer onboarding

---

## Process

### Step 1: Gather Requirements

Ask for:

- What is the API purpose?
- What are the main endpoints?
- What are the request/response formats?
- Authentication method?
- Any complex flows that need diagrams?

### Step 2: Generate Documentation

Create comprehensive Markdown documentation with:

- Overview
- Authentication
- Endpoints
- Request/Response schemas
- Error codes
- Examples

### Step 3: Generate Diagram (if needed)

For complex flows, create a sequence diagram showing:

- Client → API → Service → Database
- Authentication flows
- Multi-step processes

---

## Documentation Template

**Save as: `[api-name]-api-docs.md`**

```markdown
# [API Name] API Documentation

**Version:** 1.0.0  
**Base URL:** `https://api.example.com/v1`  
**Last Updated:** [Date]

---

## Table of Contents

1. [Overview](#overview)
2. [Authentication](#authentication)
3. [Endpoints](#endpoints)
4. [Error Handling](#error-handling)
5. [Rate Limiting](#rate-limiting)
6. [Changelog](#changelog)

---

## 1. Overview

### Description
Brief description of what this API does and its main use cases.

### Base URL
```

Production: <https://api.example.com/v1>
Staging: <https://api-staging.example.com/v1>

```

### Content Type
All requests and responses use JSON:
```

Content-Type: application/json

```

---

## 2. Authentication

### Bearer Token (JWT)

All authenticated endpoints require a Bearer token in the Authorization header:

```http
Authorization: Bearer <token>
```

### Obtaining a Token

```http
POST /auth/login
```

**Request:**

```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

**Response:**

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIs...",
  "refresh_token": "eyJhbGciOiJIUzI1NiIs...",
  "token_type": "Bearer",
  "expires_in": 3600
}
```

### Refreshing a Token

```http
POST /auth/refresh
```

**Request:**

```json
{
  "refresh_token": "eyJhbGciOiJIUzI1NiIs..."
}
```

---

## 3. Endpoints

### 3.1 Users

#### Get Current User

Retrieves the authenticated user's profile.

```http
GET /users/me
```

**Headers:**

| Header | Value | Required |
|--------|-------|----------|
| Authorization | Bearer <token> | Yes |

**Response: 200 OK**

```json
{
  "id": "usr_123abc",
  "email": "user@example.com",
  "name": "John Doe",
  "avatar_url": "https://cdn.example.com/avatars/123.jpg",
  "created_at": "2024-01-15T10:30:00Z",
  "updated_at": "2024-01-20T14:45:00Z"
}
```

**Errors:**

| Code | Description |
|------|-------------|
| 401 | Unauthorized - Invalid or expired token |
| 404 | User not found |

---

#### Update User

Updates the authenticated user's profile.

```http
PUT /users/me
```

**Headers:**

| Header | Value | Required |
|--------|-------|----------|
| Authorization | Bearer <token> | Yes |
| Content-Type | application/json | Yes |

**Request Body:**

```json
{
  "name": "John Updated",
  "avatar_url": "https://cdn.example.com/avatars/new.jpg"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | No | User's display name (2-100 chars) |
| avatar_url | string | No | URL to avatar image |

**Response: 200 OK**

```json
{
  "id": "usr_123abc",
  "email": "user@example.com",
  "name": "John Updated",
  "avatar_url": "https://cdn.example.com/avatars/new.jpg",
  "updated_at": "2024-01-21T09:00:00Z"
}
```

**Errors:**

| Code | Description |
|------|-------------|
| 400 | Bad Request - Validation error |
| 401 | Unauthorized |

---

### 3.2 Orders

#### List Orders

Retrieves a paginated list of orders for the authenticated user.

```http
GET /orders
```

**Query Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| page | integer | No | 1 | Page number |
| limit | integer | No | 20 | Items per page (max 100) |
| status | string | No | all | Filter by status: pending, processing, completed, cancelled |
| sort | string | No | created_at | Sort field |
| order | string | No | desc | Sort order: asc, desc |

**Example Request:**

```http
GET /orders?page=1&limit=10&status=completed&sort=created_at&order=desc
```

**Response: 200 OK**

```json
{
  "data": [
    {
      "id": "ord_abc123",
      "status": "completed",
      "total": 99.99,
      "currency": "USD",
      "items_count": 3,
      "created_at": "2024-01-20T10:00:00Z",
      "completed_at": "2024-01-21T15:30:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total_items": 45,
    "total_pages": 5,
    "has_next": true,
    "has_prev": false
  }
}
```

---

#### Get Order

Retrieves a specific order by ID.

```http
GET /orders/:id
```

**Path Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| id | string | Order ID (ord_xxxxx) |

**Response: 200 OK**

```json
{
  "id": "ord_abc123",
  "status": "completed",
  "total": 99.99,
  "subtotal": 89.99,
  "tax": 5.00,
  "shipping": 5.00,
  "currency": "USD",
  "items": [
    {
      "id": "itm_001",
      "product_id": "prod_xyz",
      "name": "Widget Pro",
      "quantity": 2,
      "unit_price": 29.99,
      "total": 59.98
    },
    {
      "id": "itm_002",
      "product_id": "prod_abc",
      "name": "Widget Basic",
      "quantity": 1,
      "unit_price": 30.01,
      "total": 30.01
    }
  ],
  "shipping_address": {
    "name": "John Doe",
    "street": "123 Main St",
    "city": "New York",
    "state": "NY",
    "postal_code": "10001",
    "country": "US"
  },
  "created_at": "2024-01-20T10:00:00Z",
  "updated_at": "2024-01-21T15:30:00Z",
  "completed_at": "2024-01-21T15:30:00Z"
}
```

**Errors:**

| Code | Description |
|------|-------------|
| 401 | Unauthorized |
| 403 | Forbidden - Order belongs to another user |
| 404 | Order not found |

---

#### Create Order

Creates a new order.

```http
POST /orders
```

**Request Body:**

```json
{
  "items": [
    {
      "product_id": "prod_xyz",
      "quantity": 2
    },
    {
      "product_id": "prod_abc",
      "quantity": 1
    }
  ],
  "shipping_address": {
    "name": "John Doe",
    "street": "123 Main St",
    "city": "New York",
    "state": "NY",
    "postal_code": "10001",
    "country": "US"
  },
  "payment_method_id": "pm_card_visa"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| items | array | Yes | List of items to order |
| items[].product_id | string | Yes | Product ID |
| items[].quantity | integer | Yes | Quantity (1-99) |
| shipping_address | object | Yes | Delivery address |
| payment_method_id | string | Yes | Payment method ID |

**Response: 201 Created**

```json
{
  "id": "ord_new456",
  "status": "pending",
  "total": 99.99,
  "created_at": "2024-01-22T10:00:00Z"
}
```

**Errors:**

| Code | Description |
|------|-------------|
| 400 | Invalid request body |
| 402 | Payment failed |
| 422 | Insufficient inventory |

---

#### Update Order Status

Updates an order's status (admin only).

```http
PATCH /orders/:id/status
```

**Request Body:**

```json
{
  "status": "processing"
}
```

| Field | Type | Required | Values |
|-------|------|----------|--------|
| status | string | Yes | pending, processing, shipped, completed, cancelled |

**Response: 200 OK**

```json
{
  "id": "ord_abc123",
  "status": "processing",
  "updated_at": "2024-01-22T11:00:00Z"
}
```

---

#### Cancel Order

Cancels an order (if not yet shipped).

```http
POST /orders/:id/cancel
```

**Request Body:**

```json
{
  "reason": "Customer changed mind"
}
```

**Response: 200 OK**

```json
{
  "id": "ord_abc123",
  "status": "cancelled",
  "cancelled_at": "2024-01-22T12:00:00Z",
  "refund": {
    "id": "ref_001",
    "amount": 99.99,
    "status": "pending"
  }
}
```

**Errors:**

| Code | Description |
|------|-------------|
| 400 | Order cannot be cancelled (already shipped) |
| 404 | Order not found |

---

### 3.3 Products

#### List Products

Retrieves a paginated list of products.

```http
GET /products
```

**Query Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| page | integer | No | 1 | Page number |
| limit | integer | No | 20 | Items per page |
| category | string | No | - | Filter by category slug |
| search | string | No | - | Search in name and description |
| min_price | number | No | - | Minimum price |
| max_price | number | No | - | Maximum price |
| in_stock | boolean | No | - | Filter to only show in-stock items |

**Response: 200 OK**

```json
{
  "data": [
    {
      "id": "prod_xyz",
      "name": "Widget Pro",
      "slug": "widget-pro",
      "description": "The best widget for professionals",
      "price": 29.99,
      "currency": "USD",
      "images": [
        "https://cdn.example.com/products/widget-pro-1.jpg"
      ],
      "category": {
        "id": "cat_001",
        "name": "Widgets",
        "slug": "widgets"
      },
      "in_stock": true,
      "stock_quantity": 150
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total_items": 100,
    "total_pages": 5
  }
}
```

---

## 4. Error Handling

### Error Response Format

All errors return a consistent JSON structure:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "The request body is invalid",
    "details": [
      {
        "field": "email",
        "message": "Email is required"
      },
      {
        "field": "password",
        "message": "Password must be at least 8 characters"
      }
    ]
  },
  "request_id": "req_abc123xyz"
}
```

### HTTP Status Codes

| Code | Meaning | When Used |
|------|---------|-----------|
| 200 | OK | Successful GET, PUT, PATCH |
| 201 | Created | Successful POST (resource created) |
| 204 | No Content | Successful DELETE |
| 400 | Bad Request | Invalid request body or parameters |
| 401 | Unauthorized | Missing or invalid authentication |
| 403 | Forbidden | Authenticated but not authorized |
| 404 | Not Found | Resource doesn't exist |
| 409 | Conflict | Resource already exists |
| 422 | Unprocessable Entity | Business logic error |
| 429 | Too Many Requests | Rate limit exceeded |
| 500 | Internal Server Error | Server-side error |

### Error Codes

| Code | Description |
|------|-------------|
| VALIDATION_ERROR | Request validation failed |
| AUTHENTICATION_ERROR | Invalid credentials |
| TOKEN_EXPIRED | JWT token has expired |
| RESOURCE_NOT_FOUND | Requested resource doesn't exist |
| PERMISSION_DENIED | User lacks required permissions |
| RATE_LIMIT_EXCEEDED | Too many requests |
| PAYMENT_FAILED | Payment processing error |
| INSUFFICIENT_STOCK | Product out of stock |

---

## 5. Rate Limiting

### Limits

| Tier | Requests/Hour | Requests/Minute |
|------|---------------|-----------------|
| Free | 100 | 10 |
| Pro | 1,000 | 60 |
| Enterprise | 10,000 | 600 |

### Headers

Rate limit information is included in response headers:

```http
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 999
X-RateLimit-Reset: 1706097600
```

### Rate Limit Exceeded

**Response: 429 Too Many Requests**

```json
{
  "error": {
    "code": "RATE_LIMIT_EXCEEDED",
    "message": "Rate limit exceeded. Try again in 60 seconds.",
    "retry_after": 60
  }
}
```

---

## 6. Webhooks

### Supported Events

| Event | Description |
|-------|-------------|
| order.created | New order placed |
| order.completed | Order fulfilled |
| order.cancelled | Order cancelled |
| payment.succeeded | Payment completed |
| payment.failed | Payment failed |

### Webhook Payload

```json
{
  "id": "evt_abc123",
  "type": "order.completed",
  "created_at": "2024-01-22T10:00:00Z",
  "data": {
    "order_id": "ord_abc123",
    "total": 99.99
  }
}
```

### Signature Verification

Webhooks include an `X-Webhook-Signature` header for verification:

```python
import hmac
import hashlib

def verify_signature(payload, signature, secret):
    expected = hmac.new(
        secret.encode(),
        payload.encode(),
        hashlib.sha256
    ).hexdigest()
    return hmac.compare_digest(expected, signature)
```

---

## 7. SDKs and Libraries

### Official SDKs

| Language | Package | Installation |
|----------|---------|--------------|
| JavaScript | @example/api-sdk | `npm install @example/api-sdk` |
| Python | example-api | `pip install example-api` |
| Ruby | example_api | `gem install example_api` |
| Go | github.com/example/api-go | `go get github.com/example/api-go` |

### JavaScript Example

```javascript
import { ExampleAPI } from '@example/api-sdk';

const client = new ExampleAPI({
  apiKey: 'your_api_key',
  environment: 'production'
});

// Get orders
const orders = await client.orders.list({ limit: 10 });

// Create order
const newOrder = await client.orders.create({
  items: [{ product_id: 'prod_xyz', quantity: 2 }],
  shipping_address: { ... }
});
```

---

## 8. Changelog

### v1.0.0 (2024-01-22)

- Initial API release
- User management endpoints
- Order CRUD operations
- Product catalog

### v1.1.0 (Coming Soon)

- Subscription support
- Bulk operations
- GraphQL endpoint

---

## 9. Support

- **Documentation:** <https://docs.example.com>
- **Status Page:** <https://status.example.com>
- **Support Email:** <api-support@example.com>
- **GitHub Issues:** <https://github.com/example/api/issues>

---

*API Documentation generated by Architecture Diagrams Skill*

```

---

## API Flow Diagram Example

For complex APIs, generate a sequence diagram:

```xml
<mxfile host="app.diagrams.net">
  <diagram name="API Flow" id="api-flow">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- Lifelines -->
        <mxCell id="client" value="&lt;b&gt;Client&lt;/b&gt;" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#f8cecc;strokeColor=#b85450;fontSize=12;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="100" y="80" width="100" height="500" as="geometry"/>
        </mxCell>
        
        <mxCell id="api" value="&lt;b&gt;API Gateway&lt;/b&gt;" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#d5e8d4;strokeColor=#82b366;fontSize=12;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="300" y="80" width="100" height="500" as="geometry"/>
        </mxCell>
        
        <mxCell id="auth" value="&lt;b&gt;Auth Service&lt;/b&gt;" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#dae8fc;strokeColor=#6c8ebf;fontSize=12;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="500" y="80" width="100" height="500" as="geometry"/>
        </mxCell>
        
        <mxCell id="order" value="&lt;b&gt;Order Service&lt;/b&gt;" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#dae8fc;strokeColor=#6c8ebf;fontSize=12;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="700" y="80" width="100" height="500" as="geometry"/>
        </mxCell>
        
        <mxCell id="db" value="&lt;b&gt;Database&lt;/b&gt;" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#e1d5e7;strokeColor=#9673a6;fontSize=12;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="900" y="80" width="100" height="500" as="geometry"/>
        </mxCell>
        
        <!-- Messages -->
        <mxCell id="msg1" value="POST /orders" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="150" y="180" as="sourcePoint"/>
            <mxPoint x="350" y="180" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg2" value="Validate JWT" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="350" y="220" as="sourcePoint"/>
            <mxPoint x="550" y="220" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg3" value="Valid" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;strokeColor=#82b366;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="550" y="260" as="sourcePoint"/>
            <mxPoint x="350" y="260" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg4" value="Create Order" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="350" y="300" as="sourcePoint"/>
            <mxPoint x="750" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg5" value="INSERT order" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="750" y="340" as="sourcePoint"/>
            <mxPoint x="950" y="340" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg6" value="Order ID" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;strokeColor=#82b366;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="950" y="380" as="sourcePoint"/>
            <mxPoint x="750" y="380" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg7" value="Order Created" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;strokeColor=#82b366;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="750" y="420" as="sourcePoint"/>
            <mxPoint x="350" y="420" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="msg8" value="201 Created" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;fontSize=11;labelBackgroundColor=#ffffff;strokeColor=#82b366;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="350" y="460" as="sourcePoint"/>
            <mxPoint x="150" y="460" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## Output Files

**For an API documentation request:**

1. ✅ `[api-name]-api-docs.md` - **ALWAYS required**
2. 📊 `[api-name]-api-flow.drawio` - Optional for complex flows

---

*API Documentation - Complete endpoint specifications*
