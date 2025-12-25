# Configuration Capture (State Snapshot)

<!-- 
REDUCES FRICTION: Decouples "what code" from "what config". Eliminates "it works on my machine" by forcing explicit state documentation for every environment variable key and dependency.
-->

| Scope | Details |
| :--- | :--- |
| **Environment** | `[Dev / Staging / Prod]` |
| **Deployment Time** | `YYYY-MM-DD HH:MM UTC` |
| **Commit Hash** | `[Full SHA]` |
| **DB Schema Ver** | `vX.Y.Z` |

## Infrastructure State

| Component | Version / Tag | Status |
| :--- | :--- | :--- |
| **Orchestrator** | `[e.g., K8s 1.28]` | `[Healthy]` |
| **Database** | `[e.g., PG 15.3]` | `[Healthy]` |

## Feature Flags

| Flag Name | State | Purpose |
| :--- | :--- | :--- |
| `ENABLE_NEW_UI` | `[ON/OFF]` | Rollout new dashboard |
| `BETA_SEARCH` | `[ON/OFF]` | ElasticSearch tuning |

## Environment Variables (Keys Only)
>
> **SECURITY NOTE**: Do NOT paste actual secrets/values. Verify presence only.

- [ ] `DB_HOST`
- [ ] `API_KEY_STRIPE`
- [ ] `REDIS_URL`
- [ ] `LOG_LEVEL`

## Dependency Versions (`package.json` / `go.mod` top-level)

- **Primary Lib:** `[Name] @ [Version]`
- **Framework:** `[Name] @ [Version]`
