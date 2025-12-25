# On-Call Handover (The "Pass the Torch" Note)

<!--
REDUCES FRICTION: Ensures the incoming on-call knows exactly what is burning.
Prevents dropped context and zombie alerts.
-->

| Departing | Incoming | Period (UTC) |
| :--- | :--- | :--- |
| `@ali` | `@bob` | `Jan 01 - Jan 08` |

## BLUF (Shift Summary)
>
> "Quiet shift, mostly valid alerts." OR "Total chaos, see INC-101."

## 🔥 Key Incidents (Closed)

- `INC-101`: Database failover. Stabilized. Post-mortem scheduled.
- `INC-102`: Flaky test in CI blocked deploys for 2h. Fixed.

## ⚠️ Ongoing Issues (Watchlist)

- **Europe Region**: Latency is slightly elevated (+10%). Network team investigating.
- **Backup Jobs**: Job #45 failed last night, retrying manually.

## 📝 Pending Maintenance / Scheduled Work

- **Tonight 23:00 UTC**: DB version upgrade (No downtime expected).
