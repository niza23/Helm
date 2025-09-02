
# 📂 Chart Structure & Templates

A **Helm Chart** is a directory with a predefined structure that contains all the resources required to deploy an application to Kubernetes.

---

## 🏗️ Chart Directory Structure

```

mychart/
Chart.yaml        # Metadata about the chart
values.yaml       # Default values
templates/        # Kubernetes manifests (templated)
charts/           # Dependencies (subcharts)
\_helpers.tpl      # Template helpers (functions/macros)

````

---

## 📌 Chart.yaml
Contains metadata about the chart.

Example:
```yaml
apiVersion: v2           # Chart API version (v1 for Helm v2, v2 for Helm v3)
name: mychart            # Chart name
version: 0.1.0           # Chart version (SemVer)
appVersion: "1.16.0"     # Application version (container image version)
description: A Helm chart for Kubernetes
````

---

## 📌 values.yaml

Holds default configuration values that templates can reference.

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
```

---

## 📌 templates/

Contains Kubernetes manifests written as Go templates.
These templates pull values from `values.yaml`.

Example: **Deployment**

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ include "mychart.fullname" . }}
spec:
  replicas: {{ .Values.replicaCount }}
  template:
    spec:
      containers:
      - name: app
        image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
        ports:
        - containerPort: {{ .Values.service.port }}
```

---

## 📌 \_helpers.tpl

Holds reusable template helpers (functions).

Example:

```yaml
{{- define "mychart.fullname" -}}
{{ .Release.Name }}-{{ .Chart.Name }}
{{- end -}}
```

Usage in template:

```yaml
metadata:
  name: {{ include "mychart.fullname" . }}
```

---

## 📌 charts/

This folder stores **dependencies** (other charts).
Defined in `Chart.yaml` under `dependencies:`.

Example:

```yaml
dependencies:
  - name: mysql
    version: "8.8.*"
    repository: "https://charts.bitnami.com/bitnami"
```

---

## 🧪 Rendering Templates

You can render templates locally to see how they expand:

```bash
helm template ./mychart
```



