# Reconciliation Rules

## Record Count

The total number of records extracted from SAP must equal the number of records loaded into FinSight.

---

## Financial Totals

The total debit amount and credit amount must match exactly.

---

## Mandatory Fields

The following fields must always match:

- Company Code
- Fiscal Year
- Fiscal Period
- Document Number
- Posting Date
- Currency
- Amount

---

## Duplicate Records

Duplicate document numbers are not allowed.

---

## Missing Records

Any missing record must be reported immediately.

---

## Timestamp Validation

All records must contain valid processing timestamps.

---

## Currency Validation

Currencies must comply with ISO 4217 standards.