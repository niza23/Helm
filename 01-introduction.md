# 📘 Introduction to Helm & Core Concepts

## What is Helm?
- Helm is a **package manager for Kubernetes**, like:
  - `apt/yum` → Linux
  - `npm` → Node.js
- It helps you:
  - Define, install, and manage Kubernetes applications
  - Use **Charts** (packaged YAML + templates)
  - Simplify complex deployments

---

## Why Helm?
✅ Reduces YAML duplication (templating)  
✅ Provides **versioning, rollback, and release mgmt**  
✅ Enables **sharing apps** via repositories  
✅ Integrates into CI/CD pipelines  

---

## Core Concepts
- **Chart** → Package of Kubernetes resources (YAML + templates + metadata)  
- **Release** → Running instance of a chart in a cluster  
- **Repository** → Collection of charts (local/public/private)  
- **Tiller** (Helm v2 only) → Deprecated, now Helm v3 is **client-only**

---

## Helm Chart Structure (high-level)
```bash
mychart/
Chart.yaml # Metadata
values.yaml # Default config values
templates/ # Kubernetes manifests (templated)
charts/ # Dependencies (sub-charts)
_helpers.tpl # Helper templates
```
