

# 🛠️ Helm Commands (Basics)

This section covers the most common Helm commands used in daily work and interviews.  

---

## 📦 Installing Charts
```bash
# Install a chart from a repository
helm install myapp bitnami/nginx

# Install a chart from local path
helm install myapp ./mychart
````

---

## 🔄 Upgrading Releases

```bash
# Upgrade release with new values
helm upgrade myapp bitnami/nginx --set service.type=LoadBalancer

# Upgrade or install if release does not exist
helm upgrade --install myapp ./mychart -f values-prod.yaml
```

---

## ↩️ Rollback

```bash
# Rollback to a specific revision
helm rollback myapp 1
```

---

## 🗑️ Uninstall Release

```bash
helm uninstall myapp
```

---

## 🔍 Searching Charts

```bash
# Search in configured repositories
helm search repo nginx

# Search across ArtifactHub
helm search hub mysql
```

---

## 📋 Listing Installed Releases

```bash
helm list
```

---

## 📝 Show Chart Information

```bash
# Show chart metadata
helm show chart bitnami/nginx

# Show chart values
helm show values bitnami/nginx

# Show all available chart details
helm show all bitnami/nginx
```

---

## 🧪 Linting a Chart

```bash
# Validate chart structure and templates
helm lint ./mychart
```

---

## 🧰 Debugging

```bash
# Render templates locally without installing
helm template ./mychart

# Debug installation with verbose output
helm install myapp ./mychart --dry-run --debug
```

