# SRC003 - Accounts Receivable API Specification

## API Information

| Property | Value |
|----------|-------|
| API Name | Accounts Receivable API |
| API Code | SRC003 |
| Version | v1 |
| Protocol | HTTPS |
| Data Format | JSON |
| Authentication | OAuth 2.0 Bearer Token |

---

# Purpose

The Accounts Receivable (AR) API provides customer invoice, payment, outstanding balance, and receivable information from SAP S/4HANA to the FinSight Analytics platform.

The API supports customer aging analysis, receivable tracking, cash flow forecasting, and financial reporting.

---

# Endpoint

GET /api/v1/accounts-receivable

---

# HTTP Method

GET

---

# Authentication

OAuth 2.0 Bearer Token

---

# Request Parameters

| Parameter | Type | Required | Description |
|------------|------|----------|-------------|
| companyCode | String | Yes | SAP Company Code |
| customerId | String | No | Customer Number |
| fromDate | Date | Yes | Invoice Start Date |
| toDate | Date | Yes | Invoice End Date |
| invoiceStatus | String | No | OPEN / PAID / OVERDUE |
| page | Integer | No | Page Number |
| pageSize | Integer | No | Records Per Page |

---

# Sample Request

GET /api/v1/accounts-receivable?companyCode=1000&fromDate=2026-01-01&toDate=2026-01-31&invoiceStatus=OPEN&page=1&pageSize=100

---

# Sample Success Response

HTTP Status

200 OK

Example Response

```json
{
  "invoiceId": "AR-INV-100001",
  "customerId": "C10045",
  "customerName": "XYZ Retail Pvt Ltd",
  "companyCode": "1000",
  "invoiceDate": "2026-01-12",
  "dueDate": "2026-02-11",
  "currency": "INR",
  "invoiceAmount": 185000.00,
  "receivedAmount": 50000.00,
  "outstandingAmount": 135000.00,
  "status": "OPEN"
}
```

---

# Error Responses

| HTTP Status | Description |
|-------------|-------------|
| 400 | Invalid Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Customer Not Found |
| 409 | Duplicate Invoice |
| 422 | Business Rule Violation |
| 429 | Too Many Requests |
| 500 | Internal Server Error |
| 503 | Service Unavailable |

---

# Business Rules

- Company Code is mandatory.
- Customer must exist in Customer Master.
- Invoice Amount cannot be negative.
- Due Date must not be earlier than Invoice Date.
- Duplicate invoices are rejected.
- Currency must follow ISO 4217.

---

# Security

- OAuth 2.0 Authentication
- HTTPS Only
- TLS 1.2+
- JWT Access Token

---

# Rate Limiting

100 API requests per minute.

---

# Pagination

Default Page Size: 100

Maximum Page Size: 1000

---

# Response Time SLA

Average response time should be less than 2 seconds.

---

# Audit Logging

Every request shall log:

- Correlation ID
- Timestamp
- Customer ID
- Company Code
- Processing Time
- Status Code

---

# Version History

| Version | Date | Description |
|----------|------|-------------|
| v1.0 | June 2026 | Initial Version |