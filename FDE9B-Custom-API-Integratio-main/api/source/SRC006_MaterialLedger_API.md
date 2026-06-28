# SRC006 - Material Ledger API Specification

## Purpose

Provides Material Ledger information including inventory valuation and material movement costs.

---

## Endpoint

GET /api/v1/material-ledger

---

## Parameters

- companyCode
- materialNumber
- plant
- fiscalYear

---

## Sample Response

```json
{
  "material":"MAT1001",
  "plant":"PL01",
  "valuationClass":"3000",
  "movingAveragePrice":1250.50,
  "currency":"INR"
}
```

---

## Business Rules

- Material must exist.
- Plant mandatory.
- Fiscal Year required.

---

## Errors

400,401,404,500