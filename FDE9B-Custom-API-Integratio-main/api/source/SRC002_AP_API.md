# SRC002 - Accounts Payable API Specification

## API Information

| Property       | Value                  |
| -------------- | ---------------------- |
| API Name       | Accounts Payable API   |
| API Code       | SRC002                 |
| Version        | v1                     |
| Protocol       | HTTPS                  |
| Data Format    | JSON                   |
| Authentication | OAuth 2.0 Bearer Token |

---

# Purpose

The Accounts Payable (AP) API provides vendor invoice, payment, and liability information from SAP S/4HANA to the FinSight Analytics platform.

The API supports financial reporting, vendor analysis, cash flow monitoring, and payable aging reports.

---

# Endpoint

```http
GET /api/v1/accounts-payable
```

---

# HTTP Method

GET

---

# Authentication

OAuth 2.0 Bearer Token

---

# Request Parameters

| Parameter     | Type    | Required | Description           |
| ------------- | ------- | -------- | --------------------- |
| companyCode   | String  | Yes      | SAP Company Code      |
| vendorId      | String  | No       | Vendor Number         |
| fromDate      | Date    | Yes      | Invoice Start Date    |
| toDate        | Date    | Yes      | Invoice End Date      |
| invoiceStatus | String  | No       | OPEN / PAID / OVERDUE |
| page          | Integer | No       | Page Number           |
| pageSize      | Integer | No       | Number of Records     |

---

# Sample Request

```http
GET /api/v1/accounts-payable?companyCode=1000&fromDate=2026-01-01&toDate=2026-01-31&invoiceStatus=OPEN&page=1&pageSize=100
```

---

# Sample Success Response

HTTP Status

```text
200 OK
```

Example Response

```json
{
  "invoiceId": "INV-100001",
  "vendorId": "V10045",
  "vendorName": "ABC Suppliers Pvt Ltd",
  "companyCode": "1000",
  "invoiceDate": "2026-01-10",
  "dueDate": "2026-02-09",
  "currency": "INR",
  "invoiceAmount": 125000.50,
  "paidAmount": 25000.00,
  "balanceAmount": 100000.50,
  "status": "OPEN"
}
```

---

# Error Responses

| HTTP Status | Description             |
| ----------- | ----------------------- |
| 400         | Invalid Request         |
| 401         | Unauthorized            |
| 403         | Forbidden               |
| 404         | Vendor Not Found        |
| 409         | Duplicate Invoice       |
| 422         | Business Rule Violation |
| 429         | Too Many Requests       |
| 500         | Internal Server Error   |
| 503         | Service Unavailable     |

---

# Business Rules

* Company Code is mandatory.
* Vendor must exist in Vendor Master.
* Invoice Amount cannot be negative.
* Due Date must be greater than or equal to Invoice Date.
* Duplicate invoices are rejected.
* Currency must follow ISO 4217.

---

# Security

* OAuth 2.0 Authentication
* HTTPS Only
* TLS 1.2+
* JWT Access Token

---

# Rate Limiting

100 API requests per minute.

---

# Pagination

Default Page Size: 100

Maximum Page Size: 1000

---

# Response Time SLA

Average Response Time

Less than 2 seconds.

---

# Audit Logging

Every request shall log:

* Correlation ID
* Timestamp
* Vendor ID
* Company Code
* Processing Time
* Status Code

---

# Version History

| Version | Date      | Description     |
| ------- | --------- | --------------- |
| v1.0    | June 2026 | Initial Version |
