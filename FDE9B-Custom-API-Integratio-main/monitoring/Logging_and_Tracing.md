# Logging and Tracing

## Purpose

Logging and tracing provide complete visibility into API requests, responses, and transaction processing.

---

## Information Logged

- Timestamp
- Correlation ID
- Request ID
- API Name
- Source System
- Destination System
- Status Code
- Processing Time
- Error Message

---

## Log Levels

| Level | Description |
|---------|-------------|
| INFO | Successful processing |
| WARN | Recoverable issues |
| ERROR | Processing failure |
| DEBUG | Development diagnostics |
| FATAL | Critical failure |

---

## Traceability

Every transaction must include a unique Correlation ID for end-to-end tracking.