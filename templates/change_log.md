# Change Log (The "Diff" Tracker)

<!-- 
REDUCES FRICTION: Moves beyond git history to capture operational context ("The Why"). Standardizes impact assessment to prevent "alert fatigue" or accidental high-severity incidents.
-->

| Date (UTC) | Author | Type | Impact | The "Why" (Context) | Rollback |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `2024-01-01` | `@user` | `Config` | `Low` | Enable debug logs for investigation | `[Link]` |
| `2024-01-02` | `@user` | `Infra` | `High` | Vertical scaling of RDS instance | `[Link]` |
| `...` | `...` | `...` | `...` | ... | `...` |

**Legend:**

- **Type**: `Config`, `Infra`, `Code`, `Data`
- **Impact**:
  - `Low`: No downtime, internal only.
  - `Med`: Potential degradation, requires monitoring.
  - `High`: Downtime expected or critical path change.
