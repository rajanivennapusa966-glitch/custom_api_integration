# SRC001 - General Ledger API Specification

## API Information

| Property       | Value                  |
| -------------- | ---------------------- |
| API Name       | General Ledger API     |
| API Code       | SRC001                 |
| Version        | v1                     |
| Protocol       | HTTPS                  |
| Format         | JSON                   |
| Authentication | OAuth 2.0 Bearer Token |

---

## Purpose

The General Ledger API retrieves journal entries from SAP S/4HANA and exposes them to the FinSight Analytics platform for financial reporting and analysis.

---

## Endpoint

```
GET /api/v1/general-ledger
```

---

## Request Parameters

| Parameter   | Type    | Required | Description             |
| ----------- | ------- | -------- | ----------------------- |
| companyCode | String  | Yes      | SAP Company Code        |
| fromDate    | Date    | Yes      | Start Date (YYYY-MM-DD) |
| toDate      | Date    | Yes      | End Date (YYYY-MM-DD)   |
| page        | Integer | No       | Page Number             |
| pageSize    | Integer | No       | Records Per Page        |

---

## Sample Request

```
GET /api/v1/general-ledger?companyCode=1000&fromDate=2026-01-01&toDate=2026-01-31&page=1&pageSize=100
```

---

## Success Response

HTTP Status: **200 OK**

Returns a list of General Ledger journal entries.

---

## Error Responses

| Status | Description             |
| ------ | ----------------------- |
| 400    | Invalid Request         |
| 401    | Unauthorized            |
| 403    | Forbidden               |
| 404    | Resource Not Found      |
| 409    | Duplicate Entry         |
| 422    | Business Rule Violation |
| 429    | Rate Limited            |
| 500    | Internal Server Error   |
| 503    | Service Unavailable     |

---

## Security

* OAuth 2.0 Authentication
* TLS 1.2 or higher
* HTTPS Only

---

## Business Rules

* Company Code is mandatory.
* Posting Date must belong to an open fiscal period.
* Duplicate journal entries are ignored using idempotent processing.
* All requests must contain a valid OAuth access token.

---

## Rate Limiting

Maximum 100 requests per minute per client.

---

## Version History

| Version | Date      | Description               |
| ------- | --------- | ------------------------- |
| v1.0    | June 2026 | Initial API Specification |
