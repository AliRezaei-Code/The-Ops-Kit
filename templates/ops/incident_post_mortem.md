# Incident Post-Mortem (The "Learning" Doc)

<!--
REDUCES FRICTION: Blameless account of "what happened" vs "what we will do". 
Prevents recurring incidents by forcing structured root cause analysis and actionable follow-up.
-->

| Incident ID | Date (UTC) | Severity | Duration | Lead |
| :--- | :--- | :--- | :--- | :--- |
| `INC-1234` | `YYYY-MM-DD` | `SEV-1` | `45m` | `@user` |

## Summary
>
> Two-sentence overview of the impact and failure mode.
> *Example: core-api 500 error rate spiked to 100% due to redis connection saturation.*

## Impact

- **Services Affected**: `[Service A]`, `[Service B]`
- **User Impact**: `15% of users (cannot checkout)`
- **Revenue Impact**: `~$10k (estimated)`

## Timeline (UTC)

- **`10:00`**: Alert `HighErrorRate` fired.
- **`10:05`**: Engineer acknowledged.
- **`10:15`**: Rolled back deployment `v1.2.3`.
- **`10:45`**: Service recovered.

## Root Cause (5 Whys)

1. **Why?** Redis pool exhausted.
2. **Why?** New feature failed to close connections efficiently.
3. **Why?** Missing timeout in connection config.
4. **Why?** Default client settings used.
5. **Why?** Linter does not catch missing timeouts.

## Action Items (Prevent Recurrence)

- [ ] Fix connection leak in code (Link to PR).
- [ ] Add linter rule for Redis client config.
- [ ] Alert on connection pool saturation > 80%.
