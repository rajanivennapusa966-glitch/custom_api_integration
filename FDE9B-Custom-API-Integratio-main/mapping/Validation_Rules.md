Validation Rules
Purpose

Ensure data quality before sending records to FinSight.

Mandatory Fields
Company Code
Fiscal Year
Posting Date
GL Account
Amount
Currency
Document Number
Date Validation
Posting Date must be valid.
Document Date cannot exceed Posting Date beyond configured business limits.
Currency Validation

Only ISO 4217 currency codes are accepted.

Numeric Validation

Amounts must

be numeric
contain two decimal places
remain within supported financial limits
Master Data Validation

Validate

GL Account
Cost Center
Profit Center
Company Code

against master data.

Duplicate Validation

Document IDs must be unique.

Duplicate records shall follow the idempotency policy.

Business Rule Validation

Validate all mandatory accounting rules before transmission