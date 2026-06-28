# SRC011 - Budget API Specification

## Purpose

Provides budget allocation information.

---

## Endpoint

GET /api/v1/budgets

---

## Sample Response

```json
{
  "budgetId":"BG100",
  "department":"Sales",
  "allocated":10000000,
  "used":3500000
}
```

---

## Business Rules

- Budget positive.
- Department mandatory.

---

## Errors

400,401,404,500