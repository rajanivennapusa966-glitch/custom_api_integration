# SRC007 - Purchase Order API Specification

## Purpose

Provides Purchase Order information from SAP.

---

## Endpoint

GET /api/v1/purchase-orders

---

## Parameters

- companyCode
- vendorId
- purchaseOrder
- fromDate
- toDate

---

## Sample Response

```json
{
  "purchaseOrder":"4500001234",
  "vendor":"ABC Suppliers",
  "orderDate":"2026-01-15",
  "currency":"INR",
  "amount":250000
}
```

---

## Business Rules

- Purchase Order unique.
- Vendor mandatory.
- Currency ISO4217.

---

## Errors

400,401,404,409,500