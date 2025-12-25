# Infrastructure & Architecture Standards (IAS)

## Infrastructure as Code (IaC)

- **Tooling**: Terraform (Infrastructure), Ansible (Configuration), Helm (Kubernetes).
- **State Management**: Remote state (S3+DynamoDB) with locking mandated.
- **Modules**: Prefer "Opinionated Modules" over raw resources.

## Naming Conventions

Follow `[environment]-[region]-[service]-[component]`.

- *Example*: `prod-us-east-1-payment-api-redis`

## Tagging Strategy

All resources must have the following tags:

| Tag Key | Value Example | Purpose |
| :--- | :--- | :--- |
| `ManagedBy` | `Terraform` | Prevent manual drift. |
| `Environment` | `Production` | Billing & Risk grouping. |
| `Owner` | `Team-Platform` | Who pays / who fixes. |
| `CostCenter` | `CC-1234` | Finance allocation. |

## Secret Management

- **NEVER** commit secrets to git.
- Use `ExternalSecrets` operator or `Vault`.
- Rotate keys automatically every 90 days.

## Directory Structure

```
infra/
├── modules/          # Reusable components
└── environments/     # State roots
    ├── dev/
    ├── staging/
    └── prod/
```
