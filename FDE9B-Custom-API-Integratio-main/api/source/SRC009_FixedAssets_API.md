# SRC009 - Fixed Assets API Specification

## Purpose

Provides Fixed Asset master and depreciation information.

---

## Endpoint

GET /api/v1/fixed-assets

---

## Sample Response

```json
{
  "assetNumber":"FA10001",
  "assetClass":"Buildings",
  "acquisitionValue":15000000,
  "currency":"INR"
}
```

---

## Business Rules

- Asset must exist.
- Acquisition Value positive.

---

## Errors

400,401,404,500