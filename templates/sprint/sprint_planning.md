# Sprint Planning (The "Kickoff")

| Sprint | Goal | Capacity (Pts) | Velocity (Last 3) |
| :--- | :--- | :--- | :--- |
| `Sprint 24` | `Ship Feature X` | `40` | `38` |

## Sprint Goal
>
> **One Sentence**: *Enable users to export reports to PDF.*

## Commitments (The "What")

| ID | Title | Owner | Points | Priority |
| :--- | :--- | :--- | :--- | :--- |
| `T-101` | `Build PDF Generation Backend` | `@alice` | `8` | `High` |
| `T-102` | `Frontend Download Button` | `@bob` | `3` | `High` |
| `T-103` | `Database Indexing` | `@charlie`| `5` | `Med` |

## Risks & Mitigations

- **Risk**: External API rate limits.
- **Mitigation**: Implement caching layer first.

## Definition of Done (Checklist)

- [ ] Code reviewed & merged.
- [ ] Unit tests pass (>80% coverage).
- [ ] Deployed to Staging.
- [ ] Feature flagged OFF in Prod.
