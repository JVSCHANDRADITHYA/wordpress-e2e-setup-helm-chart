# Wordpress-e2e-setup-helm-chart

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/woocommerce-e2e-setup)](https://artifacthub.io/packages/search?repo=woocommerce-e2e-setup)

Helm chart repository for automated end-to-end provisioning of **WordPress WooCommerce e-commerce stores** on Kubernetes.

This repository distributes versioned Helm chart artifacts and enables reproducible, infrastructure-driven store deployment.

---

## Overview

This project enables:

- Automated WordPress deployment
- WooCommerce installation and configuration
- Kubernetes-native setup
- CI/CD compatible store provisioning
- Repeatable, versioned releases

Charts are distributed via GitHub Pages as a standard Helm repository.

---

## Helm Repository

Repository URL:

```
https://jvschandradithya.github.io/wordpress-e2e-setup-helm-chart/charts
```

Add the repository:

```bash
helm repo add wordpress-e2e https://jvschandradithya.github.io/wordpress-e2e-setup-helm-chart/charts
helm repo update
```

Verify available charts:

```bash
helm search repo wordpress-e2e
```

---

## Installation

Install a chart:

```bash
helm install my-store wordpress-e2e/<chart-name>
```

Install with custom configuration:

```bash
helm install my-store wordpress-e2e/<chart-name> -f values.yaml
```

---

## Repository Structure

```
charts/
├── <chart-name>-<version>.tgz
└── index.yaml
```

- `.tgz` files are packaged Helm charts
- `index.yaml` is generated using `helm repo index`
- Hosted using GitHub Pages

---

## Releasing a New Chart Version

From the chart source directory:

```bash
helm package <chart-directory>
helm repo index charts/ \
  --url https://jvschandradithya.github.io/wordpress-e2e-setup-helm-chart/charts
```

Commit and push the updated `.tgz` files and `index.yaml`.

---

## Artifact Hub Compatibility

This repository follows standard Helm repository conventions and can be registered with Artifact Hub.

Each chart should include:

- `Chart.yaml` with proper metadata
- Chart versioning
- Documentation
- Updated `index.yaml`

---

## Deployment Target

Designed for:

- Kubernetes clusters (EKS or self-managed)
- Automated store provisioning
- Infrastructure-as-code workflows
- Multi-environment deployments

---

