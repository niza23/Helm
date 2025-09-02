
# ⚙️ Values & Overrides

Helm uses a **values system** to make charts reusable and configurable.  
- `values.yaml` → Holds default values  
- Users can **override** values at install/upgrade time  

---

## 📌 Default `values.yaml`

Example:
```yaml
replicaCount: 2

image:
  repository: nginx
  tag: "1.21"
  pullPolicy: IfNotPresent

service:
  type: ClusterIP
  port: 80
````

---

## 📥 Override Methods

### 1️⃣ Using a custom values file

```bash
helm install myapp ./mychart -f custom-values.yaml
helm upgrade myapp ./mychart -f values-prod.yaml
```

### 2️⃣ Inline with `--set`

```bash
helm install myapp ./mychart --set image.tag=1.19.0
helm upgrade myapp ./mychart --set service.type=LoadBalancer
```

### 3️⃣ Multiple `-f` files

```bash
helm install myapp ./mychart -f values-dev.yaml -f secrets.yaml
```

---

## 📌 Precedence Order

Helm resolves values in this order (highest → lowest):

1. `--set` (CLI overrides)
2. `-f custom-values.yaml` (user-provided files, last one wins if multiple)
3. `values.yaml` (default inside chart)

---

## 📥 Passing Environment-Specific Values

Maintain separate files per environment:

```
values-dev.yaml
values-staging.yaml
values-prod.yaml
```

Install with:

```bash
helm install myapp ./mychart -f values-prod.yaml
```

---

## 🧪 Debugging Values

* Render templates with chosen values:

```bash
helm template ./mychart -f values-prod.yaml
```


