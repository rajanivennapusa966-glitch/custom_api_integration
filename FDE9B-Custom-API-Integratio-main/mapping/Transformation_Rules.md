Standard Transformation Rules
Rule 1 – Date Conversion

Convert SAP internal date format (YYYYMMDD) into ISO 8601 format (YYYY-MM-DD).

Example:

20260115

↓

2026-01-15
Rule 2 – Remove Leading Zeros

Fields such as

BELNR
RACCT
KOSTL
PRCTR

must have leading zeros removed.

Example

000012345

↓

12345
Rule 3 – Currency Validation

Validate all currencies using ISO 4217.

Example

INR

USD

EUR
Rule 4 – Decimal Formatting

Financial values shall be rounded to two decimal places.

Example

25000

↓

25000.00
Rule 5 – Text Cleanup

Trim leading and trailing spaces.

Remove unwanted special characters.

Rule 6 – Company Code Mapping

Validate Company Code against master data before sending to FinSight.

Rule 7 – Fiscal Period Conversion

SAP special periods (13–16) shall be mapped according to FinSight reporting requirements.