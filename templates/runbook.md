# Runbook / Playbook (The "Action" Guide)

<!--
REDUCES FRICTION: "Don't make me think" during a fire. 
Provides a linear, deterministic path to mitigation to reduce MTTR (Mean Time To Recovery).
-->

| Alert Name | Severity | Service Owner |
| :--- | :--- | :--- |
| `HighCpuUsage` | `SEV-2` | `@platform-team` |

## Impact

- Latency increase > 500ms.
- Potential dropped requests if > 90% CPU.

## Diagnostic Steps (Verify It's Real)

1. Check Dashboards: `[Link to Grafana]`
2. Run command:

   ```bash
   kubectl top pod -l app=my-service
   ```

3. Check logs for error spikes: `[Link to Splunk/Datadog]`

## Remediation Steps (Fix It)

### 1. Vertical Scale (Quick Fix)

   ```bash
   kubectl patch deployment my-service -p '{"spec":{"template":{"spec":{"containers":[{"name":"my-service","resources":{"limits":{"cpu":"2000m"}}}]}}}}'
   ```

### 2. Restart Pods (Memory Leak?)

   ```bash
   kubectl rollout restart deployment/my-service
   ```

## Rollback Plan

If scaling causes issues, revert:

```bash
kubectl rollout undo deployment/my-service
```

## Escalation Policy

- If unmitigated after **30 mins**, page: `@senior-sre`
- If affecting payments, page: `@engineering-manager`
