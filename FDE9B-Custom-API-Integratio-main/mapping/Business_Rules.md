Business Rules
Objective

Define accounting rules enforced before integration with FinSight.

Rule 1

Each Journal Entry must contain a valid Company Code.

Rule 2

Every Journal Entry must contain at least one GL Account.

Rule 3

Amounts must balance according to accounting principles.

Rule 4

Posting Date must belong to an open fiscal period.

Rule 5

Currencies must comply with ISO 4217.

Rule 6

Duplicate Journal Entries shall not be created.

If the payload is identical, processing should be idempotent.

Rule 7

Master data references must exist before transactional data is processed.

Rule 8

Every successful integration shall generate an audit log entry.

Rule 9

Every failed integration shall be logged with complete error details.

Rule 10

All API requests and responses shall be traceable using a unique Correlation ID.