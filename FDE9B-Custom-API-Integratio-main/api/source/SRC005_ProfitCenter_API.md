# SRC005 - Profit Center API Specification

## API Information

| Property | Value |
|----------|-------|
| API Name | Profit Center API |
| API Code | SRC005 |
| Version | v1 |
| Protocol | HTTPS |
| Data Format | JSON |
| Authentication | OAuth 2.0 Bearer Token |

---

# Purpose

The Profit Center API exposes organizational profit center master data for profitability reporting and management accounting.

---

# Endpoint

GET /api/v1/profit-centers

---

# Request Parameters

| Parameter | Type | Required | Description |
|------------|------|----------|-------------|
| companyCode | String | Yes | Company Code |
| profitCenter | String | No | Profit Center Code |

---

# Sample Response

```json
{
  "profitCenter":"PC200",
  "companyCode":"1000",
  "description":"North Region",
  "manager":"Jane Doe",
  "status":"ACTIVE"
}
```

---

# Business Rules

- Profit Center must exist.
- Company Code mandatory.
- Duplicate records are ignored.

---

# Error Codes

400,401,403,404,500

---

# Version History

| Version | Date | Description |
|----------|------|-------------|
| v1.0 | June 2026 | Initial Version |