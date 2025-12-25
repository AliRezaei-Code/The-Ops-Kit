# The Ops Kit

A curated collection of operational documentation templates, guidelines, and standards designed to reduce friction and improve consistency across Engineering, Product, and Security teams.

## 📂 Repository Structure

This repository is organized into **Guidelines** (meta-documentation and standards) and **Templates** (copy-pasteable markdown files).

### 📚 Guidelines (`/guidelines`)

*Standards, philosophies, and how-to guides.*

* **[DevSecOps Standards](guidelines/devsecops_standards.md)** (`devsecops_standards.md`)
  * Overview of the security pipeline ("Golden Path"), SLA definitions for vulnerabilities, and container security rules.
* **[Infrastructure Standards](guidelines/infrastructure_standards.md)** (`infrastructure_standards.md`)
  * "IAS" (Infrastructure & Architecture Standards). Naming conventions, tagging strategies (CostCenter, Owner), and secret management.
* **[Runbook Authoring Guide](guidelines/runbook_authoring.md)** (`runbook_authoring.md`)
  * The "Style Guide" for operations. How to write deterministic, imperative, and effective runbooks.
* **[Terraform Documentation Setup](guidelines/terraform_doc_setup.md)** (`terraform_doc_setup.md`)
  * Guide for automating `README` generation for Terraform modules using `terraform-docs` and pre-commit hooks.

---

### 📝 Templates (`/templates`)

*Ready-to-use markdown templates for daily operations.*

#### 🔹 Core (`/templates/core`)

*General purpose documentation for architecture and state.*

* **[Architecture Decision Record (ADR)](templates/core/adr.md)**: Track significant technical decisions, context, and consequences.
* **[Change Log](templates/core/change_log.md)**: A manual log for tracking operational changes, config updates, and "why" things changed.
* **[Configuration Capture](templates/core/configuration_capture.md)**: A snapshot template for capturing environment state (versions, flags, env vars) during verification.
* **[Stakeholder Status Update](templates/core/stakeholder_status.md)**: High-level executive summary format (BLUF, RAG Status, Wins, Blockers).

#### 🔹 Operations (`/templates/ops`)

*Incident management and on-call tools.*

* **[Incident Post-Mortem](templates/ops/incident_post_mortem.md)**: Blameless retrospective template (Timeline, Root Cause/5-Whys, Action Items).
* **[On-Call Handover](templates/ops/oncall_handover.md)**: Structured note for passing context between on-call shifts (Key Incidents, Watchlist).
* **[Runbook](templates/ops/runbook.md)**: Standardized template for actionable alerts (Trigger, Severity, Remediation, Rollback).

#### 🔹 Security (`/templates/security`)

*DevSecOps and compliance artifacts.*

* **[Security Audit Checklist](templates/security/security_audit_checklist.md)**: Pre-flight checklist for services (Auth, Network, Logging, Compliance).
* **[Threat Model (STRIDE)](templates/security/threat_model.md)**: Template for conducting and documenting threat analysis using the STRIDE methodology.
* **[Vulnerability Report](templates/security/vulnerability_report.md)**: Format for tracking CVEs, remediation plans, and false positives.

#### 🔹 Sprint (`/templates/sprint`)

*Agile ceremonies and planning.*

* **[Sprint Planning](templates/sprint/sprint_planning.md)**: Template for defining sprint goals, capacity, and commitments.
* **[Sprint Retrospective](templates/sprint/sprint_retrospective.md)**: Team improvement format (Pulse Check, Start/Stop/Continue).
* **[Sprint Review](templates/sprint/sprint_review.md)**: Demo recap, metric review, and stakeholder feedback log.

---

## 🚀 How to Use

1. **Browse**: Navigate to the folder relevant to your current task.
2. **Copy**: Copy the raw Markdown content.
3. **Paste**: Paste it into your Wiki, Notion, Jira, or a version-controlled markdown file in your project.
4. **Fill**: Replace the bracketed placeholders `[...]` with your specifics.

> **Pro Tip**: Treat your documentation like code. Review it, version it, and keep it close to the work it describes.
