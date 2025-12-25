# Terraform Documentation Setup

This guide sets up [terraform-docs](https://terraform-docs.io/) to automatically generate READMEs for your modules.

## 1. Installation

**MacOS:**

```bash
brew install terraform-docs
```

**Linux:**

```bash
curl -Lo ./terraform-docs.tar.gz https://github.com/terraform-docs/terraform-docs/releases/download/v0.16.0/terraform-docs-v0.16.0-$(uname)-amd64.tar.gz
tar -xzf terraform-docs.tar.gz
chmod +x terraform-docs
sudo mv terraform-docs /usr/local/bin/terraform-docs
```

## 2. Configuration (`.terraform-docs.yml`)

Place this file in the root of your repo or module.

```yaml
formatter: "markdown table"

output:
  file: README.md
  mode: inject
  template: |-
    <!-- BEGIN_TF_DOCS -->
    {{ .Content }}
    <!-- END_TF_DOCS -->

sort:
  enabled: true
  by: required

sections:
  show:
    - header
    - providers
    - requirements
    - inputs
    - outputs
```

## 3. Usage

Run this command in any directory with `.tf` files:

```bash
terraform-docs .
```

To run it via **pre-commit** (Recommended):
Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/terraform-docs/terraform-docs
  rev: v0.16.0
  hooks:
    - id: terraform-docs-go
      args: ["markdown", "table", "--output-file", "README.md", "./modules/my-module"]
```
