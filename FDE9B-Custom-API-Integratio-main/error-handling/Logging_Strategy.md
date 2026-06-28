Logging Strategy
Purpose

Every API request and response must be logged for auditing and troubleshooting.

Log Levels
Level	Purpose
INFO	Successful processing
WARN	Recoverable issues
ERROR	Processing failures
DEBUG	Developer diagnostics
FATAL	Critical system failure
Log Contents

Every log entry should include:

Timestamp
Correlation ID
Request ID
Company Code
API Name
Processing Time
Status Code
Error Code (if any)
Sample Log
{
  "timestamp":"2026-07-01T10:30:15Z",
  "correlationId":"INT-100001",
  "api":"GeneralLedgerAPI",
  "status":"SUCCESS",
  "duration":"420ms"
}