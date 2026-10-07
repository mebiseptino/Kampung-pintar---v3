Kampung Pintar v3 - Secure Data Platform for 909 Nagari

Security focused data platform for West Sumatra nagari governments.

Architecture - Meta Applied AI Pattern
- Modular Python FastAPI services with rigid Pydantic validators to sanitize KK NIK
- Isolated container sandboxes Docker for Excel normalization
- Latency and security tightly controlled

Security
- RBAC + AES-256 at rest + TLS in transit + audit logs
- PDP Law compliance
- p95 latency under 250ms

LLM Security
- Secure LLM-assist for Wali Nagari with prompt injection guardrails

Stack
Python, FastAPI, Pydantic, Docker, PostgreSQL
