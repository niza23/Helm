
# 📘 Helm Notes (Beginner → Advanced)

A complete set of **Helm and Helm Charts notes** for DevOps engineers and interview preparation.  
These notes are organized step by step — starting from basics and moving into advanced topics.  

---

## 📂 Topics Covered (so far)

1. [Introduction to Helm & Core Concepts](:01-introduction.md)  
2. [Helm Commands (Basics)](:02-basic-commands.md)  
3. [Chart Structure & Templates](:03-chart-structure.md)  
4. [Values & Overrides](:04-values-overrides.md)  
5. [Helm Repositories](:05-repositories.md)  

---

## 🗝️ Key Helm Concepts (Quick Definitions)

- **Helm** → A package manager for Kubernetes (like apt/yum for Linux).  
- **Chart** → A Helm package (templates, values, metadata) describing a Kubernetes application.  
- **Release** → A running instance of a chart deployed to a cluster.  
- **Repository** → A collection of Helm charts (can be public or private).  
- **values.yaml** → Default configuration values for a chart, can be overridden.  
- **Template** → A Kubernetes manifest file written with Go templating.  
- **Hook** → Special resources that run at certain lifecycle events (pre-install, post-upgrade, etc.).  
- **Dependency (Subchart)** → A chart that another chart relies on (declared in `Chart.yaml`).  
- **Helm v2 vs v3** → v2 had Tiller (server-side), v3 is client-only (improved security).  
- **OCI Registry** → A container registry (like DockerHub, ECR, ACR) that can also store Helm charts.  


