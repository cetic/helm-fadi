# Helm Chart for FADI

[![CircleCI](https://circleci.com/gh/cetic/helm-fadi.svg?style=svg)](https://circleci.com/gh/cetic/helm-fadi/tree/master)

## Introduction

This [Helm](https://github.com/kubernetes/helm) chart installs [fadi](https://github.com/fadi) in a Kubernetes cluster.
You can optionally enable/disable big data frameworks of fadi.

## Prerequisites

- Kubernetes cluster 1.10+
- Helm 2.8.0+
- PV provisioner support in the underlying infrastructure.

## Chart Details

See [fadi](https://github.com/fadi) for the documentation.

## Installation

### Add Helm repository

```bash
helm repo add cetic https://cetic.github.io/helm-charts
helm repo update
```

### Install the chart

Install the fadi helm chart with a release name `my-release`:

```bash
helm install --name my-release cetic/fadi
```

## Uninstallation

To uninstall/delete the `my-release` deployment:

```bash
helm delete --purge my-release
```

Deletion of the StatefulSet doesn't cascade to deleting associated PVCs. To delete them:

```bash
kubectl delete pvc -l release=my-release,component=data
```

## Configuration

Each requirement is configured with the options provided by that Chart. Please consult the relevant charts for their configuration options.
