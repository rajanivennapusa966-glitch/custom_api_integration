# SRC008 - Sales Order API Specification

## Purpose

Provides Sales Order information for customer order analytics.

---

## Endpoint

GET /api/v1/sales-orders

---

## Parameters

- customerId
- companyCode
- salesOrder
- fromDate
- toDate

---

## Sample Response

```json
{
  "salesOrder":"5000000123",
  "customer":"XYZ Retail",
  "amount":500000,
  "currency":"INR",
  "status":"OPEN"
}
```

---

## Business Rules

- Customer mandatory.
- Sales Order unique.

---

## Errors

400,401,404,409,500