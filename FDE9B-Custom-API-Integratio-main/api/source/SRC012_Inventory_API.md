# SRC012 - Inventory API Specification

## Purpose

Provides inventory stock information.

---

## Endpoint

GET /api/v1/inventory

---

## Sample Response

```json
{
  "material":"MAT1001",
  "plant":"PL01",
  "availableStock":1250,
  "unit":"EA"
}
```

---

## Business Rules

- Material mandatory.
- Plant mandatory.
- Stock cannot be negative.

---

## Errors

400,401,404,500