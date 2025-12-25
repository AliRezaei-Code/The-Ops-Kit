# Threat Model (STRIDE)

| System/Feature | Date | Owner | Reviewer |
| :--- | :--- | :--- | :--- |
| `Payment Gateway Service` | `YYYY-MM-DD` | `@alice` | `@security-team` |

## Data Flow Diagram (DFD) description
>
> *Describe how data moves. Example: User -> Web App -> API -> Database.*

## Threat Analysis (STRIDE)

| Category | Threat Description | Vulnerability | Mitigation Strategy | Status |
| :--- | :--- | :--- | :--- | :--- |
| **S**poofing | Attacker impersonates a user via stolen session token. | Weak session management. | Implement short-lived JWTs + Rotation. | `[TODO]` |
| **T**ampering | SQL Injection in legacy search field. | Unsanitized input. | Use ORM / Parameterized queries. | `[FIXED]` |
| **R**epudiation | User denies making a transaction. | Missing audit logs. | Enable comprehensive transaction logging. | `[TODO]` |
| **I**nformation Disclosure | PII leaked in error logs. | Verbose logging on. | Sanitize logs, disable debug mode in prod. | `[FIXED]` |
| **D**enial of Service | API flooded with requests. | No rate limiting. | Implement Redis-based rate limiting. | `[TODO]` |
| **E**levation | User accesses Admin API. | Broken Object Level Auth. | Enforce strict RBAC checks on every endpoint. | `[TODO]` |

## Assumptions

- TLS 1.3 is enforced on all ingress.
- Databases are unexposed to the public internet.

## Action Items

- [ ] Ticket-123: Implement Rate Limiting.
- [ ] Ticket-124: Audit Log improvements.
