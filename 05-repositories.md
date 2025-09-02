
# 📦 Helm Repositories

A **Helm repository** is a collection of packaged charts (`.tgz` files) and an `index.yaml` that describes them.  
Repositories can be **public** (e.g., Bitnami, ArtifactHub) or **private** (self-hosted using ChartMuseum, Harbor, or OCI registries).

---

## 📥 Adding a Repository
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
````

---

## 🔍 Searching a Repository

```bash
# Search charts in configured repos
helm search repo mysql

# Search ArtifactHub (official Helm hub)
helm search hub nginx
```

---

## 📋 Listing Installed Repos

```bash
helm repo list
```

---

## 🗑️ Removing a Repo

```bash
helm repo remove bitnami
```

---

## 📦 Packaging & Hosting Charts

### Package a chart

```bash
helm package ./mychart
# Output: mychart-0.1.0.tgz
```

### Push chart to an OCI registry (Helm v3.7+)

```bash
helm registry login myregistry.io
helm push mychart-0.1.0.tgz oci://myregistry.io/my-namespace
```

### Using ChartMuseum (self-hosted)

```bash
helm plugin install https://github.com/chartmuseum/helm-push.git
helm push mychart-0.1.0.tgz chartmuseum
```

---

## 📂 Repository Types

* **Public** → Bitnami, ArtifactHub, Helm stable charts (deprecated but archived)
* **Private** → Internal company repos (ChartMuseum, Harbor, Nexus)
* **OCI-based registries** → DockerHub, AWS ECR, GCP Artifact Registry, Azure ACR

