Dead Letter Queue (DLQ)
Purpose

Messages that cannot be processed successfully after all retry attempts are moved to the Dead Letter Queue.

This prevents message loss while allowing operations teams to investigate failures.

Message Flow
SAP

↓

API Gateway

↓

Kafka Queue

↓

Transformation

↓

Failure

↓

Retry

↓

Retry Failed

↓

Dead Letter Queue
Information Stored
Correlation ID
Error Code
Error Message
Payload
Timestamp
Retry Count
Source System
Recovery

Operations engineers review the DLQ, correct the issue, and reprocess the message.