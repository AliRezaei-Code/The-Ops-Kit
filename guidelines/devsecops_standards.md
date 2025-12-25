# DevSecOps Standards & Guidelines

## 1. Shift Left Philosophy

Security is **everyone's responsibility**, not just the Security Team.

- **Developers**: Own the security of their code (SAST/SCA).
- **Ops**: Own the security of the platform (IaC/Container).
- **Security**: Provides tools, guidance, and audit.

## 2. Pipeline Controls (The "Golden Path")

Every deployment pipeline MUST include:

1. **SCA (Software Composition Analysis)**: Check dependencies (e.g., Snyk, Dependabot).
    - *Blocker*: Critical/High CVEs.
2. **SAST (Static Analysis)**: Scan source code (e.g., SonarQube, CodeQL).
    - *Blocker*: Secrets in code, SQL Injection patterns.
3. **Container Scan**: Scan Docker images (e.g., Trivy, Clair).
    - *Blocker*: OS-level vulnerabilities.
4. **IaC Scan**: Scan Terraform/K8s manifests (e.g., Checkov, tfsec).

## 3. Secret Management Standards

- **Source Code**: No secrets in Git. Use `git-secrets` pre-commit hook.
- **Runtime**: Inject secrets via Env Vars (from Vault/K8s Secrets), not hardcoded files.
- **Encryption**: Secrets MUST be encrypted at rest and in transit.

## 4. Container Security

- **Base Images**: Use minimal distroless or Alpine images.
- **User**: NEVER run as `root`. Use `USER 1001`.
- **Read-Only**: Mount root filesystem as read-only where possible.

## 5. Vulnerability Management

| Severity | SLA (Time to Fix) |
| :--- | :--- |
| **Critical** | < 24 Hours |
| **High** | < 7 Days |
| **Medium** | < 30 Days |
| **Low** | < 90 Days |

## 6. Access Control

- **Principle of Least Privilege**: Default to "Deny All".
- **JIT Access**: Prefer Just-In-Time access for production debugging over permanent admin rights.
