# SRC010 - Bank Statement API Specification

## Purpose

Provides bank statement and reconciliation information.

---

## Endpoint

GET /api/v1/bank-statements

---

## Sample Response

```json
{
  "statementId":"BS1001",
  "bank":"State Bank",
  "statementDate":"2026-01-31",
  "balance":2500000
}
```

---

## Business Rules

- Statement unique.
- Balance numeric.

---

## Errors

400,401,404,500