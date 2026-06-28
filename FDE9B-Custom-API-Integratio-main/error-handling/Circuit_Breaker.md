Circuit Breaker
Purpose

The Circuit Breaker prevents repeated requests to an unavailable service.

States
Closed

Everything works normally.

Requests flow normally.

Open

Too many failures detected.

No requests are sent.

Immediate failure is returned.

Half Open

System tests a small number of requests.

If successful, the breaker closes.

Otherwise, it returns to the Open state.

Threshold
Failure Rate: 50%
Evaluation Window: 60 seconds
Recovery Timeout: 30 seconds
Benefits
Prevents cascading failures
Protects downstream systems
Improves system stability