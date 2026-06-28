# SRC004 - Cost Center API Specification

## API Information

| Property | Value |
|----------|-------|
| API Name | Cost Center API |
| API Code | SRC004 |
| Version | v1 |
| Protocol | HTTPS |
| Data Format | JSON |
| Authentication | OAuth 2.0 Bearer Token |

---

# Purpose

The Cost Center API provides organizational cost center master data from SAP S/4HANA to FinSight Analytics for financial reporting, budgeting, and cost allocation.

---

# Endpoint

GET /api/v1/cost-centers

---

# Request Parameters

| Parameter | Type | Required | Description |
|------------|------|----------|-------------|
| companyCode | String | Yes | SAP Company Code |
| costCenter | String | No | Cost Center Code |
| status | String | No | ACTIVE / INACTIVE |

---

# Sample Response

```json
{
  "costCenter": "CC100",
  "companyCode": "1000",
  "name": "Sales Department",
  "department": "Sales",
  "manager": "John Smith",
  "status": "ACTIVE"
}
```

---

# Business Rules

- Cost Center must be unique.
- Company Code is mandatory.
- Status must be ACTIVE or INACTIVE.
- Deleted Cost Centers are excluded.

---

# Error Codes

400, 401, 403, 404, 429, 500

---

# Version History

| Version | Date | Description |
|----------|------|-------------|
| v1.0 | June 2026 | Initial Release |