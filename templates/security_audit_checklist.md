# Security Audit Checklist (Pre-Flight)

**Target**: `[Service/Application Name]` - `[Version/Tag]`

## 1. Authentication & Authorization

- [ ] **MFA**: Multi-Factor Authentication enabled for all admin access?
- [ ] **Least Privilege**: Service accounts have minimal permissions?
- [ ] **Secrets**: No secrets in code/git history (checked via `git-secrets`)?
- [ ] **Rotation**: Keys/Passwords rotated within last 90 days?

## 2. Infrastructure & Network

- [ ] **Public Access**: No DB/Internal/Dashboard ports exposed to 0.0.0.0/0?
- [ ] **Encryption**: TLS 1.2+ enforced? (No HTTP).
- [ ] **WAF**: Web Application Firewall enabled?
- [ ] **Patching**: OS/Container images patched (last 30 days)?

## 3. Application Security (AppSec)

- [ ] **Dependencies**: `npm audit` / `snyk` run? (0 Critical/High CVEs).
- [ ] **Input Validation**: All user inputs sanitized? (SQLi/XSS checks).
- [ ] **Headers**: Security headers set? (HSTS, CSP, X-Frame-Options).

## 4. Logging & Monitoring

- [ ] **PII Redaction**: Logs do NOT contain passwords/tokens/PII.
- [ ] **Audit Trails**: Critical actions (login, delete, config change) logged?
- [ ] **Alerting**: Alerts configured for unusual patterns (e.g. 50 failed logins)?

## 5. Compliance / Governance

- [ ] **Data Residency**: Data stored in correct region?
- [ ] **Backups**: Backups verified and tested restore recently?

## Sign-off

| Role | Name | Date |
| :--- | :--- | :--- |
| **Security Engineer** | `[Name]` | `YYYY-MM-DD` |
| **Tech Lead** | `[Name]` | `YYYY-MM-DD` |
