# Airport Luggage API - Portal Changelog

This document tracks all changes to the Airport Luggage API that are visible through the developer portal at https://domcrosbie.portal.swaggerhub.com/luggage

---

## Version 1.1.0 - November 2025

### 🎉 Major Feature: Pagination Support

#### Overview
Added comprehensive pagination support to the luggage listing endpoint, enabling efficient retrieval of large datasets and improved API performance.

### Changes to GET /luggage

#### ✨ New Features

**Query Parameters Added:**

| Parameter | Type | Default | Range | Description |
|-----------|------|---------|-------|-------------|
| `limit` | integer | 20 | 1-100 | Maximum number of items to return per page |
| `offset` | integer | 0 | 0+ | Number of items to skip before starting collection |

**New Response Structure:**

The endpoint now returns a `PaginatedLuggageResponse` object instead of a simple array:

```json
{
  "data": [
    {
      "id": "LUG001",
      "ownerName": "John Doe",
      "flightNumber": "AA123",
      "weight": 23.5,
      "status": "checked-in"
    }
  ],
  "pagination": {
    "total": 150,
    "limit": 20,
    "offset": 0,
    "hasMore": true
  }
}
```

**Pagination Metadata Fields:**

- `total` - Total count of all luggage items in the system
- `limit` - Page size used for this request
- `offset` - Starting position of the current page
- `hasMore` - Boolean indicating if more pages are available

#### 📖 Usage Examples

**Get the first page (default):**
```bash
GET /luggage
# Returns first 20 items (offset 0)
```

**Get first page with custom page size:**
```bash
GET /luggage?limit=50
# Returns first 50 items
```

**Get second page:**
```bash
GET /luggage?limit=20&offset=20
# Returns items 21-40
```

**Get third page with larger page size:**
```bash
GET /luggage?limit=50&offset=100
# Returns items 101-150
```

#### 🔄 Migration Guide

**Before (v1.0.0):**
```javascript
// Old response was a simple array
const response = await fetch('/luggage');
const luggageItems = await response.json();
// luggageItems = [{ id: "LUG001", ... }, ...]
```

**After (v1.1.0):**
```javascript
// New response includes data and pagination
const response = await fetch('/luggage?limit=20&offset=0');
const result = await response.json();
const luggageItems = result.data;
const { total, hasMore } = result.pagination;

// Implement pagination
while (hasMore) {
  // Fetch next page
}
```

#### 💡 Benefits

- **Performance**: Reduced response payload size for large datasets
- **Scalability**: Server-side performance improvements
- **Bandwidth**: Lower network usage, especially on mobile
- **UX**: Enables progressive loading and better user experience
- **Flexibility**: Clients can control page size based on their needs

#### ⚠️ Breaking Changes

**Response Structure:**
- The GET /luggage endpoint no longer returns a simple array
- Response is now wrapped in an object with `data` and `pagination` properties
- **Action Required**: Update client code to access `response.data` instead of using response directly

**Backward Compatibility:**
- Clients using v1.0.0 will need to update their integration
- The default behavior (no query parameters) returns the first 20 items
- Consider implementing a transition period or versioned endpoints if needed

#### 🐛 Known Issues

None reported.

---

## Version 1.0.0 - Initial Release

### Features
- ✅ OAuth2 Password Flow authentication
- ✅ Rate limiting on all endpoints
- ✅ CRUD operations for luggage management:
  - `POST /luggage` - Create luggage item
  - `GET /luggage` - List all luggage items (no pagination)
  - `GET /luggage/{id}` - Get specific luggage item
  - `PUT /luggage/{id}` - Update luggage item
  - `DELETE /luggage/{id}` - Delete luggage item
- ✅ Luggage status tracking (checked-in, in-transit, delivered, lost)
- ✅ Weight and flight number tracking

### Endpoints
- `GET /ping` - Health check (public, no auth required)
- `GET /example` - Example secured endpoint

---

## Support

For questions or issues:
- **API Documentation**: https://app.swaggerhub.com/apis/domcrosbie-cc0/AirportLuggageAPI/1.1.0
- **Portal Documentation**: https://domcrosbie.portal.swaggerhub.com/luggage/docs/luggage-overview-page
- **Organization**: domcrosbie-cc0

## Version History

| Version | Release Date | Major Changes |
|---------|--------------|---------------|
| 1.1.0 | November 2025 | Added pagination to GET /luggage |
| 1.0.0 | 2025 | Initial release |
