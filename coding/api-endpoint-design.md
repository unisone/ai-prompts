# API Endpoint Design

## Description

Design RESTful or GraphQL API endpoints with proper structure, validation, error handling, and documentation.

## Prompt

```
Design an API endpoint for the following requirement:

## Requirement

{{requirement}}

## Tech Stack

{{tech_stack}}

---

## Design the Endpoint

### 1. Endpoint Definition

- **Method:** GET / POST / PUT / PATCH / DELETE
- **Path:** /api/v1/...
- **Purpose:** One sentence description

### 2. Request Schema

**Headers:**
```
Authorization: Bearer <token>
Content-Type: application/json
```

**Path Parameters:**
| Param | Type | Required | Description |
|-------|------|----------|-------------|

**Query Parameters:**
| Param | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|

**Request Body:**
```typescript
interface RequestBody {
  // Define with types and comments
}
```

### 3. Response Schema

**Success Response (200/201):**
```typescript
interface SuccessResponse {
  // Define structure
}
```

**Error Responses:**
| Status | Code | Description |
|--------|------|-------------|
| 400 | VALIDATION_ERROR | Invalid request body |
| 401 | UNAUTHORIZED | Missing or invalid token |
| 403 | FORBIDDEN | User lacks permission |
| 404 | NOT_FOUND | Resource doesn't exist |
| 409 | CONFLICT | Resource already exists |
| 500 | INTERNAL_ERROR | Server error |

```typescript
interface ErrorResponse {
  error: {
    code: string;
    message: string;
    details?: Record<string, string[]>; // Field-level errors
  }
}
```

### 4. Validation Rules

| Field | Rules |
|-------|-------|
| email | Required, valid email format, max 255 chars |
| ... | ... |

### 5. Authorization

- Who can access this endpoint?
- What permissions are required?
- Are there row-level restrictions?

### 6. Implementation Notes

- Rate limiting requirements
- Caching strategy
- Pagination approach (if applicable)
- Idempotency considerations

### 7. Example Request/Response

**Request:**
```bash
curl -X POST https://api.example.com/v1/users \
  -H "Authorization: Bearer xxx" \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "name": "John"}'
```

**Response:**
```json
{
  "id": "usr_123",
  "email": "user@example.com",
  "name": "John",
  "createdAt": "2024-01-15T10:30:00Z"
}
```
```

## Variables

- `{{requirement}}`: What the endpoint should do
- `{{tech_stack}}`: e.g., "Node.js + Express + PostgreSQL" or "Next.js API routes + Prisma"

## Example Usage

```
Design an API endpoint for the following requirement:

## Requirement
Users should be able to update their profile settings including display name, bio, and notification preferences.

## Tech Stack
Next.js 14 API routes with Prisma and PostgreSQL
```

## Notes

- Use plural nouns for collections (`/users` not `/user`)
- Use kebab-case for multi-word paths (`/user-preferences`)
- Version your API (`/v1/`) from the start
- Always return consistent error format
- Include pagination for list endpoints
