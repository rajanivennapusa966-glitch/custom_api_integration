# Reconciliation Exception Handling

## Common Exceptions

| Exception | Action |
|-----------|--------|
| Missing Record | Reprocess transaction |
| Duplicate Record | Ignore duplicate and log |
| Amount Mismatch | Investigate financial posting |
| Invalid Currency | Reject record |
| Invalid Company Code | Reject record |
| Missing Mandatory Field | Reject record |

---

## Escalation

Critical discrepancies are escalated to the Integration Support Team.

---

## Recovery Process

1. Identify failed record.
2. Review error logs.
3. Correct source data if necessary.
4. Reprocess transaction.
5. Verify successful reconciliation.