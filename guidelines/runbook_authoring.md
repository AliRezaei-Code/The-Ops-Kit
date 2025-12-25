# Runbook Authoring Guidelines

## Philosophy

Runbooks are for **3 AM**. They must be:

1. **Deterministic**: No "investigate the logs and see what happens".
2. **Imperative**: Command-style verbiage. "Run X", not "You should try running X".
3. **Copy-Pasteable**: Commands must be ready to run.

## Structure / Template

Every runbook MUST follow the [Standard Template](../templates/runbook.md).

## Do's and Don'ts

### ✅ DO

- **Use Code Blocks**:

  ```bash
  # Good
  kubectl rollout restart deployment/api
  ```

- **Link to Telemetry**: Deep links to specific dashboards/queries.
- **Define Escalation**: Who to wake up if this fails?
- **State Impact**: What is the user experiencing?

### ❌ DON'T

- **Write Prose**: No paragraphs explaining architecture (link to docs instead).
- **Use Generic Advice**: "Check database load" (How? What is high?).
- **Bury the Lede**: Remediation steps should be accessible in < 10 seconds.

## Severity Levels

- **SEV-1**: Critical functionality down. Immediate revenue impact. (Wake up everyone).
- **SEV-2**: Degradation or high risk. (Wake up team lead).
- **SEV-3**: Minor issue / Business hours only.
