# Architecture Decision Record (The "History" Log)

<!--
REDUCES FRICTION: Captures context for future engineers. 
Stops "why did they do this?" discussions by documenting the trade-offs accepted at the time.
-->

| ADR-ID | Status | Date | Decisions Drivers |
| :--- | :--- | :--- | :--- |
| `004` | `ACCEPTED` | `YYYY-MM-DD` | `@architect`, `@lead` |

## Context
>
> What is the problem? Why is existing solution insufficient?
> *Example: We need a message queue. Kafka is too heavy, Redis PubSub has no persistence.*

## Decision

We will use **RabbitMQ**.

## Consequences (Trade-offs)

| Attribute | Impact | Note |
| :--- | :--- | :--- |
| **Complexity** | ⬆️ Increases | Requires Erlang cluster management. |
| **Reliability** | ⬆️ Increases | Better durability than Redis. |
| **Cost** | ➡️ Neutral | similar to managed Kafka entry tier. |

## Alternatives Considered

- **Kafka**: Overkill for current throughput (<100 msg/sec).
- **Redis PubSub**: No guaranteed delivery, unacceptable for payments.
